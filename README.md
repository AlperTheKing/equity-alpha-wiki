# equity-alpha-wiki

> S&P 500 ve Nasdaq 100 evrenlerinde, 10-K/10-Q finansal tablo verilerini kullanarak yıllık-frekansta en yüksek getiriyi sağlayacak hisseleri seçen sistematik bir strateji tasarlamak — ve bu tasarımı, akademik literatürün yapılandırılmış, çapraz-referanslı, kümülatif bir sentezine dayandırmak. Wiki, Karpathy [`llm-wiki`](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) paterninin empirical asset pricing literatürüne uygulanmış halidir.

## 1. Niye böyle bir proje?

Sistematik faktör yatırımcılığı, 1990'lardan bu yana akademik literatürde patlama yaşadı. Fama-French üç-faktör modelinden (1993) başlayıp Carhart momentumu (1997), Sloan accruals anomalisi (1996), Piotroski F-Score (2000), Mohanram G-Score (2005), Novy-Marx gross profitability (2013), Asness-Frazzini-Pedersen QMJ (2019), Hou-Xue-Zhang q-factor model (2015/2020), Stambaugh-Yuan mispricing factors (2017) ve Jensen-Kelly-Pedersen Bayesian replication (2023) gibi yüzlerce paper, "hangi karakteristikler beklenen getiriyi açıklar?" sorusunun cevabını parça parça inşa etti. Ama bu literatür eş zamanlı olarak iki yıkıcı bulguyla da yüzleşti: McLean-Pontiff (2016) 82 anomalinin yayım sonrası yaklaşık %35 sönümlendiğini gösterdi; Harvey-Liu-Zhu (2016) 316 faktör sayımında çoklu-test düzeltmesi sonrası `|t| > 3.0` eşiğini önerdi; Hou-Xue-Zhang (2020) NYSE-VW + microcap-arınmış replikasyonda 447 anomalinin sadece %10'unun anlamlı kaldığını buldu.

Bu çelişkili manzarada **bireysel bir yatırımcı için pratik bir soru** ortaya çıkıyor: S&P 500 ve Nasdaq 100 gibi büyük-cap, az-likidite-sürtünmesi olan evrenlerde, yıllık rebalans yapan ve sadece kamuya açık 10-K/10-Q verilerine dayanan bir strateji bugün hâlâ pozitif bir kenar üretebilir mi? Cevap evetse, hangi faktörler? Hangi ağırlıkla? Hangi metodolojik filtrelerle? Cevap hayırsa, hangi epistemik nedenle?

Bu soruya ciddi bir şekilde cevap vermek için **literatürü ezberlemek değil, sentezlemek** gerekir. Bireysel bir okuyucunun 50+ paperı zihninde tutması, çelişen kanıtları takip etmesi, yıllar içinde değişen metodolojik tercihleri uçurmadan izlemesi pratik olarak imkânsızdır. Burada büyük dil modellerinin (LLM) **harici, yapılandırılmış bir hafıza katmanı** olarak kullanımı doğal bir çözüm sunar — yeter ki LLM'in "kendinden iddia üretmesi" sıkı disiplinle engellensin ve çıktı **kaynaklara explicit olarak bağlı** kalsın.

Bu repo, o disiplini somutlaştıran bir deneydir. Andrej Karpathy'nin `llm-wiki` paterni — `raw/` katmanında değiştirilmez kaynaklar, `wiki/` katmanında LLM-yazılı sentez, `CLAUDE.md` katmanında schema kuralları — empirical asset pricing alanına uyarlanmıştır. 41 ingest cycle'ı sonunda wiki şu anda **28 paper + 20 factor entity + 17 concept hub + 5 strategy spec + 3 methodology + 10 meta = ~88 markdown sayfa** içeriyor; her satırın bir paper sayfa atfı veya `[[wikilink]]` ile gerekçelendirildiği, çelişen kanıtların `meta/contradictions.md` içinde explicit kaydedildiği ve wiki'nin "tarafsız ama kararlı" bir bilgi tabanı olarak işlediği bir state'e ulaştı.

## 2. Üç katmanlı mimari (Karpathy `llm-wiki` paterni)

```
equity-alpha-wiki/
├── CLAUDE.md              ← Schema. Operasyon kuralları (§1-12). Audit protokolü.
├── raw/                   ← Immutable kaynaklar. LLM yazmaz; kullanıcı ekler.
│   ├── papers/            ← Akademik makale PDF/TXT
│   ├── books/             ← Kitap bölümleri
│   └── industry/          ← AQR / Research Affiliates / MSCI whitepaper'ları
├── wiki/                  ← LLM-yazılı, LLM-bakımlı markdown
│   ├── index.md           ← Sayfa kataloğu
│   ├── log.md             ← Append-only kronolojik log
│   ├── papers/      (28)  ← Ingested kaynakların özet sayfaları
│   ├── factors/     (20)  ← Sinyal/factor entity sayfaları
│   ├── concepts/    (17)  ← Kavram hub'ları (post_publication_decay, factor_zoo, …)
│   ├── comparisons/  (1)
│   ├── strategies/   (5)  ← v0/v1 historic + sp500_v1 + nasdaq100_v1 + known_weaknesses
│   ├── methodology/  (3)  ← backtest_spec + data_sources + backtest_implementation_plan
│   ├── backtests/         ← P123 geri raporları (CLAUDE.md §12.2; ilk rapor henüz yok)
│   └── meta/        (10)  ← MoC, open_questions, contradictions, data_gaps, 6 handoff, executive_summary
└── README.md              ← Bu dosya
```

**Üç katmanın sözleşmesi yalnızca dizin yapısı değil, epistemik bir taahhüttür**:

`raw/` **immutable**'dır. Kullanıcı oraya paperları koyar; Claude oradan okur ama asla yazmaz. Bu, "LLM'in halüsinasyonu kaynağa sızmasın" ilkesinin fiziksel garantisidir. Bir iddianın doğruluğu sorgulandığında, dönüş noktası `raw/`'daki orijinal PDF'tir.

`wiki/` **Claude'un alanı**'dır. Tüm yazma, güncelleme, çapraz-referans bakımı, lint, audit ve consolidation pass'leri Claude'un sorumluluğundadır. Kullanıcı bu katmanda **denetçi** rolündedir, **operatör** değil — sayfa içeriklerine doğrudan müdahale etmez; "TEMIZ devam", "KÜÇÜK fix devam", "YAPISAL fix" veya "ABORT" gibi tetikleyici cümlelerle Claude'u yönlendirir (CLAUDE.md §11.6).

`CLAUDE.md` **co-evolved**'dır. Schema 41 cycle boyunca defalarca güncellendi: §11 self-audit Cycle 9 civarında resmîleşti, §11.5 4-cycle ardışık consolidation pass Cycle 8'de eklendi, §7 sertifika tipleri Cycle 20-31 arasında üç ayrı schema_update'le sertleşti, §12 post-Faz 3 yaşayan-proje bakım protokolü Cycle 42'de eklendi. Her schema değişikliği `wiki/log.md`'de `schema_update` kategorisinde kayıtlıdır.

Bu üçleme — değişmez kaynak + LLM-bakımlı sentez + co-evolved schema — bireysel bir araştırmacının alanın derinliğine inerken kümülatif bilgi inşa etmesini mümkün kılar.

## 3. Literatürden çıkan ana tez: üç-bacak epistemik omurga ve dört darbe çerçevesi

Wiki'nin omurgasını **D bloğu** (Cycle 11-13) oluşturur. Bu bloğun tezi şudur: Akademik literatürde rapor edilen yüzlerce anomaliden yalnızca küçük bir alt-küme, üç ortogonal mekanizmanın **hepsinden** sağ çıkar.

**Birinci bacak — behavioral decay**: McLean-Pontiff (2016) 82 anomaliyi yayım öncesi ve yayım sonrası iki rejime ayırarak inceledi; aggregate decay yaklaşık %35 olarak ölçüldü (sig 1%). Daha kritik bulgu, decayin **büyük ve likit firmalarda daha agresif** olmasıdır — limited arbitrage hipotezi büyük-cap evrenler için çift bir darbedir (in-sample zayıflık + post-publication agresif sönümleme).

**İkinci bacak — statistical false discovery rate**: Harvey-Liu-Zhu (2016) 316 faktörlük bir literatür sayımı yaptı ve çoklu-test düzeltmesi (Bonferroni / Holm / BHY) sonrası önerdiği eşik `|t| > 3.0`'tür (geleneksel 1.96 değil). Bu eşik altında klasik SMB faktörü hiçbir zaman anlamlı çıkmaz — bu Q11'in (SMB post-1991 + large-cap relevance) tam cevabıdır.

**Üçüncü bacak — empirical replication**: Hou-Xue-Zhang (2020) "Replicating Anomalies", 447 anomalinin NYSE-VW (microcap-arınmış) replikasyonunu yaptı. Klasik 5% düzeyinde anomalilerin %64'ü anlamsız çıktı; q-factor model lensinde net **%10 anlamlılık** kaldı (46/447). McLean-Pontiff'in equal-weight + all-stocks methodolojisi mikrocap'i (sayıca %60+, market cap'te %3) suni şekilde şişirdiği için, HXZ'nin daha temiz NYSE-VW rakamı wiki için baseline'dır.

Bu üç bacağın **complementary** olması wiki'nin temel epistemik iddiasıdır: Behavioral decay (yatırımcı davranışı), statistical FDR (data-snooping bias) ve empirical replication (methodology choice) birbirinden bağımsız mekanizmalardır; üçü aynı sonuca varıyorsa ("factor zoo'nun büyük çoğunluğu yetersiz"), bu sonuç tek bir kaynağa bağımlı değildir. Faz 1'in epistemik tamlık kriterinin merkezi budur (CLAUDE.md §7).

D bloğunun dördüncü paperi — Bailey-López de Prado (2014) Deflated Sharpe Ratio — beşinci bir bacak (backtest overfitting) açma teklifini taşıdı, ama Cycle 14'te uygulanan **çerçeve genişleme disiplini meta-not** testi geçemedi: DSR ortogonal bir mekanizma değil (HLZ Sharpe-uygulamasının özel bir hali) ve ayrı bir aggregate tabloyu hak edecek yapısal yükü taşımıyor; çerçeve dört darbede sabitlendi. Bu sabitleme önemlidir — proliferation kontrolü olmadan kavram listesi büyür ve aggregat kararlar kaybolur.

**Dört darbe çerçevesi** (Cycle 13-14 sentez tablosu) wiki'nin operasyonel filtresidir: bir factor'ün strategy spec'e dahil edilmesi için (1) in-sample large-cap evrende anlamlı + (2) post-publication decay sonrası hayatta + (3) çoklu-test düzeltmeli + (4) replication-robust olması beklenir. Cycle 27'de Jensen-Kelly-Pedersen (2023) Bayesian Empirical Bayes hierarchical methodolojisi ile **dramatik bir karşı bulgu** geldi: ABD verisinde %85 replication, global ölçekte %84. Bu HXZ'nin %35'i ile yaklaşık 50 puan farktır. Wiki bu çelişkiyi gizlemek yerine `meta/contradictions.md` §3'te explicit dokümante etti ve **scope-dependent methodology disagreement** olarak resolution etiketi verdi: HXZ pure VW + 1-month + frequentist OLS, JKP capped VW (NYSE 80th percentile winsorize) + 1-month + Bayesian framework + global. Wiki konservatif tarafta (HXZ + MP rakamları baseline) durur ama JKP'yi anti-conservative üst sınır referansı olarak kabul eder; sensitivity range yaklaşık 2x.

## 4. Dört methodology zinciri

Wiki'nin teorik birikiminin en kümülatif çıktısı, **literatürdeki dört paralel methodology zinciri**'nin izini sürmesi ve her composite skor bileşeninin **dual origin** (paper-spesifik kaynak + literatür hattı kökü) ile etiketlenmesidir. Bu pattern Cycle 9'da Sloan zincirinin ilk halkasında doğdu ve Cycle 35-39'a kadar dört zincirde de uygulandı.

| Zincir | Paper × yıl | Origin → Modern halka |
|--------|-------------|------------------------|
| **Sloan zinciri** (mispricing/accruals) | 4 paper × 23 yıl | Sloan 1996 → Piotroski 2000 F_ACCRUAL → Mohanram 2005 G3 → Asness 2019 QMJ ACC |
| **Profitability zinciri** | 4 paper × 7 yıl | Novy-Marx 2013 GP/A → FF15 RMW Ope → Asness QMJ GPOA → Ball-GLN 2016 Cop |
| **F bloğu intangibles 4-katmanlı** | 4 paper × 24 yıl | Lev-Sougiannis 1996 (Knowledge) + Eisfeldt-Papanikolaou 2013 (Organization) + Peters-Taylor 2017 (Total) + Lev-Srivastava 2020 (Application) |
| **Composite mispricing scoring** | 4 paper × 17 yıl | Piotroski F-Score → Mohanram G-Score → Stambaugh-Yuan 2017 MGMT/PERF → JKP 2023 13 theme cluster |

**Sloan zinciri**, wiki'nin epistemik açıdan en kalıcı kemerini oluşturur: 1996'dan 2019'a, raporlanan kazançların persistence'ı ile cash flow desteği arasındaki farkın bir mispricing sinyali olduğu hipotezi, üç ayrı paper tarafından farklı evrenlerde bağımsız olarak teyit edildi. Piotroski'nin F_ACCRUAL bileşeni (CFO > NI) Sloan'ın orijinal accrual ölçümünün binary versiyonudur; Mohanram'ın G3 bileşeni aynı mantığın low-BM evreninde uygulanmasıdır; Asness'in QMJ Profitability boyutunun ACC measure'ı zincirin dördüncü halkasıdır. HXZ 2020 dört darbe çerçevesinde Sloan operating accruals (Oa) **4/4 hayatta kalan** dört factor adayından biridir (q-factor alpha −0.54%/ay sig).

**Profitability zinciri** Sloan zincirinin paraleli ama daha kısa: Novy-Marx (2013) GP/A = (REVT − COGS) / AT formülasyonunu "value'nun diğer tarafı" olarak ortaya koydu — gross profitability ile B/M arasında negatif korelasyon (Spearman −0.18) olduğu için, ikisinin birleşimi tek başına her birinden daha güçlüdür (50/50 mix Sharpe 0.85, market 0.34'ün 2.5 katı). FF15 RMW (Robust Minus Weak) operating profitability bu zincirin model-içi karşılığıdır; Asness QMJ Profitability boyutu altı measure'lık bir composite sunar; Ball-GLN (2016) "Cash-Based Operating Profitability" zincirin dördüncü halkasıdır — Cop = Ope − ΔWC formülasyonuyla working capital accruals'u çıkarır. Bu, Sloan fixation hypothesis'ini **çürütmek değil tamamlayıcı** olarak konumlandırır: Cop zaten accruals'ı subsume eder (4F+Cop tangency Sharpe 1.67 ⭐, 4F+Ope+Acc kombinasyonunun 1.54'ünden yüksek). İki paralel quality zinciri (Sloan + Profitability), QMJ'in 4-boyutlu yapısının Profitability dimension'ında **birleşim noktası** oluşturur (GPOA + ACC measure'ları yan yana).

**F bloğu intangibles 4-katmanlı methodology hierarchy**, Nasdaq 100 stratejisinin yapısal foundation'ıdır. FAANG-yoğun, R&D-ağırlıklı bir evrende GAAP muhasebesinin R&D'yi giderleştirme zorunluluğu, geleneksel B/M ve Cop ölçümlerini **yapay olarak bozar**. Lev-Sougiannis (1996) bu sorunun origin paper'ıdır — endüstri-spesifik amortizasyon oranları (pharma 9 yıl, scientific instruments 5 yıl) ile R&D harcamasını sermayeleştirme metodolojisini ortaya koyar; FF93'ün anaiz değişkeni B/M'in R&D-yoğun firmalarda mantıklı olmaktan çıkar. Eisfeldt-Papanikolaou (2013) bu fikri SG&A'nın bir alt-bölümüne (organization capital) genişletti; perpetual inventory δ=15% ile factor portfolio direct evidence sundu (Carhart α=3.9% sig 1%, 1970-2008). Peters-Taylor (2017) total intangible capital concept'ini önerdi ve q^tot proxy'sini (V / (K^phy + K^int)) standart q'ya kıyasla yaklaşık %21 daha açıklayıcı yaptı. Lev-Srivastava (2020), aynı yazar Baruch Lev'in 24 yıl sonraki güncellemesiyle, post-2010 value crisis'inin iki mekanizmasını (intangibles bias + mean reversion slowdown) decompose etti ve "adjusted HML" methodolojisinin 39 yılın 34'ünde conventional'ı geçtiğini gösterdi. Bu dört paper birlikte, NDX stratejisi için intangibles-aware Bm rebuild'in dört ayağıdır; Cycle 25 mini-consolidation'da Q41 (4-way horse race) tam cevap aldı.

**Composite mispricing scoring** zinciri, factor sayısının kontrol edilebilir kalmasını sağlayan boyut indirgeme paterninin tarihçesidir. Piotroski F-Score (2000) 9 binary bileşeni 0-9 arası tek sayıya indirir; Mohanram G-Score (2005) 8 industry-relative bileşeni low-BM evrene uyarlar; Stambaugh-Yuan (2017) 11 anomaliyi hierarchical clustering (Ward 1963) ile MGMT (6 anomaly: net stock issues + composite equity issues + accruals + NOA + asset growth + I/A) ve PERF (5 anomaly: distress + O-score + momentum + gross profitability + ROA) iki kümeye toplar; Jensen-Kelly-Pedersen (2023) 153 factor'ü 13 theme cluster'a (Accruals*, Debt Issuance*, Investment*, Leverage*, Low risk, Momentum, Profit Growth, Profitability, Quality, Seasonality, Size*, Skewness*, Value) Bayesian Empirical Bayes hierarchical model ile gruplar. Bu zincirin önemi: yatırım stratejisi tasarımı için **factor seçimi değil theme tahsisi** doğru soru olur. JKP'nin 13 theme'inden 10/13'ü >75% replicate olur ve tangency portfolio'da pozitif anlamlı katkı verir; sp500_v1 7-theme dominant + nasdaq100_v1 5-FAANG profile theme allocation'ı bu çerçevenin uygulamasıdır.

## 5. 4/4 hayatta kalan factor adayları

Dört darbe çerçevesinden geçip wiki'de **4/4 sertifikası** alan factor'ler, strategy spec'lerin omurgasını oluşturur:

| Factor | Methodology | Cycle | q-factor alpha | Yorum |
|--------|-------------|-------|----------------|-------|
| **Sloan operating accruals (Oa)** | Sloan zinciri origin | 9 | −0.54%/ay sig | F_ACCRUAL/G3 mispricing detection paradigmasının çekirdek bileşeni |
| **R&D-to-market (Rdm)** | NDX-relevant | 13 | +0.7%/ay sig | F bloğu intangibles-aware methodology'nin ampirik karşılığı |
| **Earnings announcement Abr** | PEAD | 13 | +0.66%/ay sig | Bernard-Thomas 1989 surprise return; quarterly resort zorunlu |
| **Cash-based op profits (Cop)** | Profitability zinciri 4. halka | 38 | +0.69%/ay sig | tangency Sharpe 4F+Cop=1.67 ⭐; subsumes accruals |

Bu dörtlü, aynı zamanda wiki'nin **pratik strategy pozisyonunu** belirler: S&P 500'de F&V/P combined + Cop standalone + adjusted HML + UMD long-only top 30%; Nasdaq 100'de QMJ + QARP + Mohanram NASDAQ partition + R&D-to-market + OC factor + adjusted HML 4-katmanlı. Strategy spec dokümanları (`strategies/sp500_v1.md`, `strategies/nasdaq100_v1.md`) her tasarım kararını wiki'deki paperlara `[[wikilink]]` ile gerekçelendirir; "memory'den biliyorum" tipi argüman yasaktır (CLAUDE.md §6.4).

## 6. Wiki yapısal pozisyonlar (REJECT listesi)

Faz 1-2-3 birikimi sonunda, wiki **belirli factor'leri large-cap evrene transfer için reddetti**. Bu reddedişler, kanıt yokluğundan değil **kanıt çokluğundan** doğdu — her birinin arkasında en az iki, çoğunda üç paper'lık bir delil zinciri vardır:

- **Vanilla HML reject** (Cycle 17 + 22 + 37): Lev-Srivastava 2020 post-2010 value crisis decomposition'ı + Israel-Moskowitz 2013 86-yıl size-conditional kanıt + Fama-French 2008 B/M big-stock weakness ([Tablo IV]) üçlü teyiti, vanilla HML'in büyük-cap evrene transferinin yapısal olarak bozuk olduğunu kurar. Wiki adjusted HML methodolojisini (Lev-Srivastava intangibles-aware) baseline alır.

- **SMB vanilla reject** (Cycle 12 + 19 + 22 + 39): HLZ multiple-testing analizinde SMB hiçbir zaman anlamlı değil; Asness QMJ controlling-for-quality regresyonunda SMB α=64bps t=6.39 (resurrection ama vanilla ile değil); Israel-Moskowitz 86-yıl confirmation; Stambaugh-Yuan 2017 modified SMB methodolojisi orta-grup-only ile 46 bps/ay (FF SMB'nin 25 bps'sinin yaklaşık 2 katı). Q11 ASTERISK üç-paper sertleştirme. Vanilla SMB stratejik girdi değildir; modified SMB ise belirli bir composite içinde anlamlı olabilir.

- **F-Score standalone large-cap reject** (Cycle 5 + 7 + 8): F-Score yalnızca BM-Q5 evreninde (high-book-to-market) kalibre edildi; HMXZ 2020 q5 lensinde large-cap segmentinde mispricing alpha mikrocap residual'a sınırlı. Wiki F&V/P combined'i (Li-Mohanram 2019) tercih eder.

- **Magic Formula reject** (Cycle 8): HMXZ 2020 q5 model lensinde Magic Formula'nın getirisinin çoğu factor exposure'larıyla açıklanır; standalone alpha mikrocap kalıntısıdır. Greenblatt'in popülerliğine rağmen akademik replication zayıf.

- **RMW Ope standalone reject** (Cycle 4 + 19 + 37 + 38): HXZ q-factor lensinde RMW Ope INSIG; FF 2008'in [Tablo II + IV] size-conditional analizinde sadece small-cap segmentinde anlamlı. Wiki QMJ Profitability composite'ini (6 measure) + Cop standalone'unu tercih eder.

Bu reject'ler, "literatürde yer alan her şey strateji girdisi olur" tipi naive bir agresif inclusion'a karşı **disipline edilmiş bir scope filter**'dır. Karşı tarafta, wiki'nin **dahil ettikleri** de aynı sıkılıkta sorgulanır — sp500_v1 ve nasdaq100_v1 spec'lerinin §4 (Expected Performance) bölümlerinde her sayı paper sayfa atfı taşır ve §6 (Known Weaknesses) bölümlerinde acknowledged but not addressed problemler explicit listelenir.

## 7. Strategy spec'leri (sp500_v1 + nasdaq100_v1 + known_weaknesses)

Faz 3 (Cycle 32-34) çıktısı üç formal strategy spec'idir. Her biri ~340-400 satır, "spec doc" tarzında — universe + factor inclusion + methodology + expected performance + backtest implementation roadmap + known weaknesses + cross-references başlıklarında.

[`strategies/sp500_v1.md`](wiki/strategies/sp500_v1.md), S&P 500 top 500 ex-financials evreninde 1980-2020 baseline + 2021-2024 OOS test, capped VW (NYSE 80th percentile winsorize) ağırlıklandırma, JKP'nin 13 universal theme'inden 7'si (Quality + Profitability + Profit Growth + Value + Momentum + Accruals* + Low risk) tahsis edilen, 4 path composite (F&V/P binary intersection + GP×V/P continuous rank product Fortune 500 paterni + adjusted HML intangibles-aware + UMD long-only top 30%) + Beneish M-Score `.025` forensic filter ile çalışan bir formal spec'tir. Conservative baseline 6-10%/yıl (×0.65 multiplier), anti-conservative üst sınır 14-18% (JKP %85 sensitivity reference); range 2x methodology choice'a duyarlıdır.

[`strategies/nasdaq100_v1.md`](wiki/strategies/nasdaq100_v1.md), NDX top 100 non-financial evreninde, FAANG-yoğun mega-cap konsantrasyonu (Apple/MSFT/Google/Nvidia/Meta/Tesla %15-20+) sebebiyle capped VW **zorunlu**, 5-theme FAANG dominant tahsis (Quality + Profitability + Profit Growth + Investment* + Value), 5 path composite (QMJ + QARP, G&V/P + GP/A standalone, Mohanram NASDAQ partition, R&D-to-market + OC factor NDX-spesifik kritik, adjusted HML F bloğu 4-katmanlı), Beneish M-Score `.01` conservative (Q47 tech firma high SGI/AQI false positive). F bloğu 4-katmanlı intangibles-aware Bm rebuild stratejinin **çekirdeğidir**: Lev-Sougiannis Knowledge + Eisfeldt-Papanikolaou Organization (full SG&A δ=15% **veya** Peters-Taylor θ=0.30; Q60 horse race açık) + Peters-Taylor Total q^tot + Lev-Srivastava Application. Conservative baseline 8-13%/yıl (×0.50 NDX agresif multiplier; Q29 limited arbitrage çift darbe), anti-conservative 16-21%.

[`strategies/known_weaknesses.md`](wiki/strategies/known_weaknesses.md), wiki-level **cross-strategy weakness registry**'sidir. Faz 3 implementation öncesi transparent acknowledgment olarak yazılır — over-promise riskini açıkça reddeder. 6 bölümde, sp500 ve nasdaq100 spec'lerinde inherit edilen + her iki evrene ortak weakness'ları + methodology choice sensitivity zorunluluğunu + acknowledged but not addressed (post-2020 OOS, JKP %85 anti-conservative) maddeleri formalize eder. v0_draft (Cycle 24) → v1_draft (Cycle 30 historic preservation pattern) → üç formal spec geçişinde synthesis fonksiyonu Cycle 34'te bu sayfaya absorb oldu.

## 8. Faz yapısı: 0 → 1 → 2 → 3 → yaşayan-proje

Wiki, başlangıçta üç fazdan geçeceği planlanmış bir proje olarak başladı: Faz 1 (Foundation), Faz 2 (Synthesis), Faz 3 (Strategy Design). Her faz geçişi **kullanıcı kararıyla** olur; Claude öneri sunar, kullanıcı onaylar.

**Faz 0 — scaffold** (2026-04-27): Boş yapı + Tier 1 source list + ilk commit. CLAUDE.md §1-11 schema'nın çekirdeği bu fazda yazıldı.

**Faz 1 — Foundation** (Cycle 1-20; sertifika 2026-05-01 **YUMUŞAK**): Tier 1 paper'larının 19'u (25 hedefin %76'sı) ingest edildi; epistemik tamlık tam karşılandı (4+ blok kapanış sentezi + üç-bacak omurga + dört darbe çerçevesi sentez tablosu + 4+ priori soru fully-answered + 4/4 ve 3-4/4 hayatta kalan factor adayları). YUMUŞAK sertifika, sayısal hedeflerin %76'da kalmasından doğdu — eksikler Faz 2 seçici ingest'le tamamlanır. Bu sertifika tipi Cycle 20 schema_update ile resmîleşti (eski sayısal hedefler "epistemik tamlık + sayısal minimum" çift kriterine dönüştürüldü).

**Faz 2 — Synthesis** (Cycle 21-31; sertifika 2026-05-02 **TAM**): 11 yapısal kriter (methodology infrastructure + strategy aday + replication + sertleştirme + consolidation + 3. contradictions resolution + v0 → v1 evrim) tam karşılandı. Israel-Moskowitz, Novy-Marx, Eisfeldt-Papanikolaou, FGX 2020, JKP 2023 bu fazda ingest edildi. v0_draft (Cycle 24) Cycle 30'da v1_draft'a evrildi — historic preservation pattern doğdu, bu pattern Cycle 30'dan itibaren wiki disiplinine yerleşti. methodology/backtest_spec (Cycle 21) ve methodology/data_sources (Cycle 29) açıldı; Faz 3 backtest implementation altyapısı kuruldu.

**Faz 3 — Strategy Design** (Cycle 32-41; sertifika 2026-05-02 **YUMUŞAK** Cycle 41 update): On yapısal kriterden 5'i wiki içinde tamamlandı (sp500_v1 + nasdaq100_v1 + known_weaknesses formal spec'ler + backtest_spec sertleştirme + 4/4-6 Faz 3 seçici ingest: HXZ 2015 + FF 2008 + Ball-GLN + Stambaugh-Yuan). Kriter #6-9 (backtest implementation + factor selection + tangency portfolio + DSR-corrected reporting) **wiki dışı ayrı projeye delegated** edildi (Portfolio123 Ultimate platform; `equity-alpha-backtest` repo). Kriter #10 (v1 → v2 evrim opsiyonel revize) **N/A wiki yaşayan-proje çerçevesinde** — backtest sonuçları geri rapor edilir ve gerekirse v2 spec açılır (CLAUDE.md §12.3 historic preservation).

**Yaşayan-proje** (Cycle 42+): Wiki dondurulmaz; canlı bilgi tabanı kalır. Yeni paper geldikçe ingest edilir, backtest sonuçları paper-form rapor olarak ingest edilir, lint/consolidation pass'leri 4-cycle ardışık disiplinde devam eder, cycle numarası post-Faz 3 update kategorisinde sürer. Cycle 42'de `meta/executive_summary.md` (yöneticisel özet) ve §12 (post-Faz 3 bakım protokolü) eklendi; bu §12 üç kuralla bakım disiplinini netleştirir: (a) executive_summary güncelleme kadansı, (b) backtest geri rapor `wiki/backtests/` klasörü ve `type: backtest_report` frontmatter, (c) v1 → v2 evrim historic preservation.

## 9. Backtest projesi — wiki dışı, döngüsel öğrenme

Faz 3 sertifika kriterlerinin #6-9'u (backtest implementation + factor selection methodologies + tangency portfolio + DSR-corrected reporting) **bilinçli olarak wiki dışına çıkarıldı**. Sebebi tasarımsaldır: Wiki bir **bilgi tabanı**'dır, bir **uygulama platformu** değildir. Backtest motorlarının çalıştırılması, point-in-time veri akışının yönetilmesi, walk-forward sub-period analizi ve bootstrap güven aralıklarının raporlanması — bunlar wiki'nin Markdown + cross-reference paterninin doğal kapsamının dışındadır.

Çözüm: ayrı bir `equity-alpha-backtest` repo'sunda, **Portfolio123 Ultimate** platformu ($389/ay; 20-yıl backtest + Position Sizing + Optimizer + Regression + AI Factor + Hedging/Long-Short) üzerinde implementation yürütülür. P123, point-in-time veri (CRSP + Compustat lifelong-included) sağlar; opsiyonel olarak FMP veya SEC EDGAR custom field override (örneğin F bloğu R&D capital perpetual inventory için) eklenir. Sample 2010-2024 backtest + 2025+ canlı uygulama; capital $1M, sp500_v1 + nasdaq100_v1 ~%50/%50 split; drawdown tolerance %50; rebalance annual June + quarterly drift check güvenlik valfı.

İki proje arasındaki ilişki **döngüsel öğrenmedir**:

```
   Wiki teori (yaşayan-proje, ~88 sayfa)
              │
              │ (strategy spec → P123 ranking systems + custom DSL)
              ▼
   Backtest projesi (P123 Ultimate)
              │
              │ (backtest sonuç → wiki/backtests/p123_*.md paper-form rapor)
              ▼
   Wiki sentez güçlenir (v1 → v2 evrim aday)
              │
              │ (yeni paper ingest + cycle devam)
              ▼
   Wiki teori (güncellenmiş)
```

Wiki'nin spec'leri P123'e mapping edilir: sp500_v1 §2.1 7-theme allocation → 7 P123 ranking system + Position Sizing balanced allocation; nasdaq100_v1 §2.5 F bloğu 4-katmanlı intangibles-aware Bm rebuild → P123 native'de yer almayan custom DSL formula (R&D capital perpetual inventory + SG&A %30 allocation Peters-Taylor methodology). known_weaknesses.md §3.13 NDX intangibles dörtlü konsolidasyonu (Q56+Q73+Q79+Q82) backtest implementation için kritik weakness olarak işaretlidir.

Geri rapor protokolü (CLAUDE.md §12.2 + handoff_backtest §6.1): Backtest sonucu `wiki/backtests/p123_{strategy}_{YYYY-MM-DD}.md` slug'ında, YAML `type: backtest_report` frontmatter ile, akademik paper'lardan ayrı klasörde saklanır. Anchor sayfaları (sp500_v1 §5 + nasdaq100_v1 §5 + known_weaknesses §5 + backtest_implementation_plan §8 + index.md "Backtests" bölümü) güncellenir. v1 → v2 evrim trigger değerlendirilir (handoff_backtest §6.3 kriterleri: conservative baseline range dışı sapma + methodology choice >5pp divergence + Q60 horse race açık tercih + F bloğu 4-katmanlı dörtlü konsolidasyon empirik karar). Trigger ON ise, **v1 OVERWRITE EDİLMEZ**: sp500_v2.md / nasdaq100_v2.md açılır, v1 status=historic + superseded_by ile dondurulu kalır (Cycle 30 v0 → v1 historic preservation paterni paralel).

Bu mimari, wiki'nin entelektüel ürünlerinin ampirik olarak test edilmesini mümkün kılarken, **wiki'nin epistemik bütünlüğünü koruyor** — backtest sonucu wiki'nin "doğru" olduğunu kanıtlamaz; sadece wiki'nin tahminlerinin belirli bir methodology pencere içinde gerçekleşip gerçekleşmediğini ölçer. Conservative wiki + sensitivity range raporlama disiplini bu epistemik mütevazılığın somut karşılığıdır.

## 10. Yazma ve denetim disiplini

Wiki'nin kalitesini ingest hızı değil **denetim sıkılığı** belirler. CLAUDE.md §6 NON-NEGOTIABLE yazma kuralları, §11 self-audit cycle'ları ve §12 yaşayan-proje bakım protokolü bu disiplinin operasyonel iskeletidir.

**Yazma disiplini özet** (CLAUDE.md §6):

1. Hiçbir sayısal iddia kaynaksız geçemez — her sayı paper sayfa atfı (`[Paper Year, Tablo N]`) veya `[[wikilink]]` ile gerekçelendirilir.
2. Memory veya training'den ekleme yasak — wiki yalnızca `raw/`'daki kaynaklara dayanır; "genel olarak literatürde bilinir ki..." cümlesi banned.
3. Hedge'ler yasak — "muhtemelen", "genelde", "etkili olabilir" gibi nicelleştirilmemiş ifadeler ya bir sayıya ya bir kaynağa bağlanmak zorunda.
4. Çelişen kanıtlar gizlenmez — bir factor için 5 paper varsa ve 2'si zayıf sonuç bulduysa, 2'si de yazılır; cross-reference `meta/contradictions.md`'de.
5. YAML frontmatter zorunlu — paper, factor, concept, strategy, methodology ve backtest_report şablonlarında.
6. Wikilink syntax `[[page_name]]` (Obsidian-uyumlu); `> ⚠️` uyarılar/çelişkiler için, `> 📝` editör notları için.
7. Türkçe wiki, paper isimleri/dergi isimleri İngilizce kalır.

**Self-audit cycles** (CLAUDE.md §11): Her ingest sonu Claude **kendi kendini denetler** — 6-spot audit (A factor entity integrity + B Goal Alignment 4 eksen + C concept zenginleşmesi + D inbound link maintenance + E meta dosyaları + F open_questions/data_gaps) PASS/PARTIAL/FAIL olarak raporlanır. 4-cycle ardışık consolidation pass'i (Cycle 4/8/12/16/20/24/28/32/36/40/44/...) standart audit yerine derin denetim yapar (orphan + çelişki + stale claim + MoC + broken wikilink). Kullanıcı sadece audit raporu üzerinde stratejik karar verir ("TEMIZ devam", "KÜÇÜK fix devam", "YAPISAL fix", "ABORT"); operatör Claude'dur.

**§12 yaşayan-proje bakım protokolü** (Cycle 42 schema_update): Üç kural — (1) executive_summary.md her 4 cycle'da veya büyük ingest sonrası güncellenir, (2) backtest geri raporu `wiki/backtests/p123_{strategy}_{YYYY-MM-DD}.md` (akademik paper'larla karıştırılmaz), (3) backtest sonucu strategy değiştirirse v1 OVERWRITE EDİLMEZ; v2 açılır. Bu protokol, post-Faz 3 yaşayan-proje statüsünde wiki'nin kümülatif tutarlılığını korur.

Niye bu kadar disiplin? **Wiki'nin değeri 25 paper'lık Tier 1'in son 5 paper'ında değil, ilk 5'in hatasız kalmasındadır.** Self-audit her cycle'da hatayı anında yakalar; consolidation pass yapısal stale'i 4 cycle'da fark eder; schema_update'ler değişen kuralları log'da bırakır. Kullanıcının elle her sayfayı kontrol etmesi 88 sayfada zaten imkansızdır; disiplin protokolü bu denetimi otomatize eder.

## 11. Kullanım

```bash
git clone https://github.com/AlperTheKing/equity-alpha-wiki.git
cd equity-alpha-wiki
claude
```

Claude'un ilk yapacağı şey [`CLAUDE.md`](CLAUDE.md) okumak ve son handoff dokümanı + log entry'lerinden state'i yüklemektir. Yeni Claude session açıldığında "ilk 3 dakika" talimatı `wiki/meta/handoff_post_faz3_001.md` §5'tedir.

Tipik yaşayan-proje workflow:

```
> raw/papers/ klasörüne LSV 1994 paper koydum, ingest et
  → CLAUDE.md §5.1 ingest workflow + §11.2 6-spot audit otomatik

> F bloğu intangibles-aware methodology özet ver
  → wiki/concepts/intangibles_adjusted_accounting.md + 4 paper sayfa wikilink

> Q60 horse race durumu — Eisfeldt-Papanikolaou full SG&A vs Peters-Taylor θ=0.30
  → meta/open_questions.md Q60 + ilgili strategy spec §2.5 NDX-spesifik

> consolidation pass yap (Cycle 44 §11.5)
  → 4-cycle ardışık derin denetim; orphan + çelişki + stale + MoC + broken wikilink

> P123 backtest sp500_v1 sonucu ulaştı, paper-form raporla
  → wiki/backtests/p123_sp500_v1_2026-06-15.md (CLAUDE.md §12.2)
  → anchor sayfa update; v1→v2 trigger değerlendir
```

## 12. İlgili kaynaklar ve lisans

- Karpathy `llm-wiki` pattern: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
- Claude Code: https://claude.com/claude-code
- Portfolio123 (backtest projesi platformu): https://www.portfolio123.com/
- Chen-Zimmermann Open Asset Pricing Database: https://www.openassetpricing.com/
- Jensen-Kelly-Pedersen GlobalFactor code repository: https://github.com/bkelly-lab/GlobalFactor

**Lisans**: Bu kişisel araştırma projesidir. `raw/` katmanındaki kaynak paper'lar kendi yazarlarının ve dergilerinin telif hakkındadır. `wiki/` katmanındaki sentez metni bireysel kullanım için açıktır; kullanıcı (Alper) gerektiğinde uygun bir açık lisans (MIT, CC-BY veya muadili) eklemeyi düşünebilir — şu anda formal lisans dosyası eklenmemiştir.

---
type: paper
authors: [Carhart, Mark M.]
year: 1997
title: "On Persistence in Mutual Fund Performance"
venue: "Journal of Finance, Vol. LII, No. 1 (March 1997), pp. 57-82"
url: https://onlinelibrary.wiley.com/doi/10.1111/j.1540-6261.1997.tb03808.x
local_path: raw/papers/The Journal of Finance - 2012 - Carhart - On Persistence in Mutual Fund Performance.pdf
ingested: 2026-04-27
tags: [factor_model, momentum, mutual_fund_performance, four_factor, scope_edge_fund_persistence]
status: ingested
---

# Carhart (1997) — On Persistence in Mutual Fund Performance

> 📝 **Atıf konvansiyonu:** `[Tablo N]` numaralı tablolar; `[s. X]` JF basılı sayfa
> numarası (paper s. 57-82 arası). Embedded text extract'ten okundu
> (`raw/papers/carhart_1997.txt`).

> 📝 **Scope notu:** Bu paperın ana konusu (mutual fund persistence) bu wiki'nin
> doğrudan amacı dışında — yıllık fundamental stock selection değil, fund return
> persistence analizi. **Ancak** paperın 4-faktör modeli (FF3 + PR1YR/UMD) bu
> wiki'nin factor model vocabulary'sine kritik bir ekleme olduğu için **scope
> içi** kabul edildi. Paper sayfası mutual fund bulgularına kısa değinir, ağırlık
> 4-faktör model ve PR1YR/UMD inşası üzerinedir.

## TL;DR

[[famafrench1993_three_factor]] üç-faktör modeline Jegadeesh-Titman (1993)
1-yıllık momentum anomalisini yakalayan **PR1YR** (sonradan literatürde **UMD**
veya **MOM** olarak adlandırılır) faktörü eklenir. 4-faktör model (`MKT-RF`, `SMB`,
`HML`, `PR1YR`), 27 size×B/M×momentum portföyünde ortalama mutlak pricing error'u
3-faktör modelin 0.31%/ay'ından **0.14%/ay'a** düşürür [s.62]. PR1YR mean
**0.82%/ay (t=4.46)** — örnekleminde **en yüksek t-stat'lı faktör** (Tablo II,
s.62). Ana mutual-fund bulgu (scope-edge): fund persistence common factor exposure
+ expense ratios ile büyük ölçüde açıklanır; en kötü performans decile'ı hariç
manager skill kanıtı yok [abstract, s.57]. Bu wiki için **kritik çıkarım**:
4-faktör model strateji benchmarking için FF3'ün doğal extension'ı; ancak
momentum'un yıllık-frekans + fundamental-only stratejimizle uyumu sınırlı.

## Tek Cümle Tezi

Hisse senedi getirilerindeki 1-yıllık momentum etkisi Fama-French 3-faktör model
tarafından açıklanmaz; PR1YR mimicking portföyü eklendiğinde 4-faktör model
mutual fund persistence dahil cross-sectional pricing error'ları büyük ölçüde
yakalar.

## Ortaya Konan Sinyal/Faktör

- **`PR1YR`** ("Prior 1-Year Return") — momentum mimicking faktörü.
  Wiki'de [[UMD]] (Up Minus Down) adıyla entity sayfası açıldı (sonraki
  literatürde standart isimlendirme). → [[UMD]]

### PR1YR / UMD inşası [s.61, footnote 3]

> "equal-weight average of firms with the highest 30 percent eleven-month returns
> lagged one month minus the equal-weight average of firms with the lowest 30
> percent eleven-month returns lagged one month. The portfolios include all NYSE,
> Amex, and Nasdaq stocks and are re-formed monthly."

Net olarak:
- **Lookback:** t-12 ile t-2 arası 11 aylık getiri (t-1 ayı atlanır — kısa-vadeli
  reversal'i nötrlemek için).
- **Sıralama:** Tüm NYSE/AMEX/NASDAQ hisseleri arasında 30/70 percentile.
- **Long:** üst %30 (winners). **Short:** alt %30 (losers).
- **Ağırlıklandırma:** **equal-weight** (FF93 SMB/HML value-weight'tir; bu önemli bir
  fark). [s.61, fn 3]
- **Rebalans:** **monthly** (FF93 HML/SMB annually).
- **Sıfır-yatırım:** long − short.

> 📝 PR1YR'ın equal-weighted + monthly rebalance yapısı yıllık-frekans / value-tilted
> bir strateji için doğrudan transferli **değil**. Wiki'nin amacı için
> implementation'ı yeniden tasarlanmalı (S&P 500 / Nasdaq 100 üzerinde value-weight
> + yıllık rebalance versiyonu literatürde yaygın ama Carhart 1997'de yok).

### Yazarın model motivasyonu [s.61, fn 2]

"This is motivated by the 3-factor model's inability to explain cross-sectional
variation in momentum-sorted portfolio returns (Fama and French 1996)."

Yani Carhart 4-faktör model bir "anomali kapama" hareketidir: FF3'ün bilinen bir
açığı (momentum) kapatılır.

## Empirik Sonuçlar (sayılarla)

### Faktör portföylerinin özet istatistikleri (% aylık) [Tablo II, s.62]

Örneklem: July 1963 - December 1993 (366 ay).

| Faktör | Mean | Std | t(mean) |
|---|---|---|---|
| `VWRF` | 0.44 | 4.39 | 1.93 |
| `RMRF` | 0.47 | 4.43 | 2.01 |
| `SMB` | 0.29 | 2.89 | 1.89 |
| `HML` | 0.46 | 2.59 | 3.42 |
| `PR1YR` | **0.82** | 3.49 | **4.46** |

> 📝 **PR1YR örneklemde en yüksek t-stat'a sahip faktör** [Tablo II, s.62].
> 0.82%/ay yıllık ~10.3% ham primum (compound öncesi). Bu, "momentum literatürün
> en güçlü tek-anomalisi" iddiasının kaynaklarından biri.

> 📝 **VWRF vs. RMRF ayrımı [Tablo II, s.62]:** VWRF Carhart'ın kendi inşası
> (CRSP value-weight − T-bill), RMRF Fama-French'in versiyonudur — ikisi
> korelasyon 1.00 ama mean'lerinde küçük fark var (0.44 vs. 0.47) muhtemelen
> filtre/dönem detayları. Pratikte aynı şey kabul edilir.

### Faktör korelasyonları [Tablo II, s.62]

|  | VWRF | RMRF | SMB | HML | PR1YR |
|---|---|---|---|---|---|
| VWRF | 1.00 | 1.00 | 0.35 | -0.36 | 0.01 |
| SMB |  |  | 1.00 | 0.10 | -0.29 |
| HML |  |  |  | 1.00 | -0.16 |
| PR1YR |  |  |  |  | 1.00 |

> 📝 **PR1YR ↔ piyasa = 0.01:** Momentum piyasaya **neredeyse ortogonal** — bu
> faktörün bağımsız risk premium taşıdığı iddiasının istatistiksel temelidir.
> PR1YR ↔ SMB = −0.29: momentum biraz büyük-cap eğilimli.

### Pricing error karşılaştırması [s.62, Tablo III tartışması]

27 quantitatively-managed portföy (size × B/M × momentum sortları) üzerinde mean
absolute pricing error:

| Model | Mean abs error (% / ay) |
|---|---|
| CAPM | 0.35 |
| FF3 | 0.31 |
| Carhart 4F | **0.14** |

**Anlamı:** 4-faktör model FF3'ün momentum-sorted portföylerdeki sistematik
hatalarını çözer.

### Mutual fund persistence sonuçları (scope-edge) [Tablo III, s.65]

- **Top decile vs. bottom decile mutual fund 1-yıl-sonrası spread:** ~67 bp/ay
  ham getiri.
- **CAPM alpha spread:** persistence açıklamıyor — top decile alpha +0.22%, bottom
  decile alpha −0.45% [s.64-65].
- **4F alpha spread:** top decile alpha −0.12% (t=−1.60), bottom decile alpha
  −0.40% (t=−4.33). 4F model spread'in büyük kısmını absorbe eder. Yorumu: "fund
  managers don't pick stocks, they accidentally hold momentum exposure" [s.63-64].
- **Bottom decile underperformance** sadece 4F ile açıklanmaz — bu paperın geri
  kalan **anomalous bulgu**'su [s.65, abstract].

> 📝 Bu wiki'nin amacı için kritik nokta: mutual fund persistence sonuçları
> (skip — scope-edge), ama **PR1YR/UMD'nin standalone primum'u + cross-section
> açıklayıcılığı** core kanıttır.

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Mutual fund decile sortları (top-decile vs. bottom-decile) ile persistence test edilir. Stock-level top-N selection formülasyonu yok; UMD faktörü kendisi top-30%-bottom-30% momentum spread'i [s.61, fn 3] | N/A — fund-level top-decile bağlamı; stock selection için scope-edge |
| **Annual rebalance** | UMD/PR1YR **aylık** rebalance + 11-aylık lookback + 1-ay skip [s.61]. Yıllık-rebalans varyantı paperda yok | ❌ **uyumsuz**: Carhart UMD'i olduğu gibi yıllık-rebalans stratejisine transfer edilemez |
| **Large-cap evrene transfer** | NYSE/AMEX/NASDAQ **all-stocks** evren; large-cap-only kalibrasyon yok. UMD korelasyonu SMB ile -0.29 [Tablo II, s.62] → momentum biraz büyük-cap eğilimli ama hala mikrokap-dahil | ⚠️ **UYARI: large-cap-only test yok** |
| **NDX intangibles / growth firms** | Momentum tech/growth firmalarda kuvvetli olarak bilinir (literatür yaygın bilgi) ama Carhart bu konuyu *paperda* test etmez. Mutual fund örnekleminde sektör/style breakdown yok | ⚠️ **UYARI: NDX-spesifik test yok**; Daniel-Moskowitz 2016 momentum crashes'la birlikte değerlendirilmeli |

**Strateji tasarımına net implikasyon:** Carhart 4F modeli **strateji
benchmarking için 4. faktör (UMD)** olarak kullanılır — strateji portföyünün
momentum exposure'unun istemsizce yüksek olup olmadığını kontrol etmek için.
Ancak UMD'nin **olduğu gibi** (aylık equal-weight) yıllık-frekans fundamental
stratejimize girmesi yapısal olarak uyumsuz. Eğer momentum strategy'ye dahil
edilecekse: (1) yıllık-rebalans, (2) value-weight, (3) S&P 500/NDX universe-içi
versiyon — Carhart 1997'de bu test yok, modern AQR pratiğinde benzer
adaptasyonlar var.

## Limitler ve Caveats

- **PR1YR equal-weight + aylık rebalance [s.61, fn 3]:** SMB/HML inşa
  konvansiyonundan farklı (value-weight, yıllık). Bu, paperın faktör yapısının
  **iç tutarsızlığı** olarak okunabilir; sonraki literatür (örn. AQR, FF güncel
  veri) çoğunlukla UMD'yi value-weight versiyonla yeniden inşa eder.
- **Yıllık-frekans strateji uyumsuzluğu:** Bu wiki S&P 500 / Nasdaq 100 üzerinde
  **yıllık** rebalance hedefliyor. Aylık-rebalance momentum factor'ün
  capacity ve trading cost profili çok farklı. Frazzini-Israel-Moskowitz 2018
  (Tier 3) implementation maliyeti açısından ele alır — wiki'de henüz yok.
- **NYSE/AMEX/NASDAQ universe:** S&P 500 / Nasdaq 100 evrenleri için doğrudan
  test sunmaz.
- **t-1 skip:** PR1YR'da 1-aylık skip kısa-vadeli reversal'i izole eder. Yıllık
  rebalanslı bir stratejide bu skip'in anlamı farklı.
- **Mutual fund sonuçları örneklem-dönemi spesifik (1962-1993):** Post-publication
  decay konusu tartışılmaz; bu paperın kendisi 1996'da yayımlandı, momentum
  primum'u post-1993 dönemde (özellikle 2000-2002 ve 2008 dönemlerinde) büyük
  drawdown'lar yaşadı (literatürde "momentum crashes"; Tier 3 #60
  Daniel-Moskowitz 2016 wiki'de henüz yok).
- **Davranışsal yorum belirsizliği:** Yazar "I employ the model to 'explain'
  returns, and leave risk interpretations to the reader" [s.61] — yani momentum'un
  rasyonel risk premium mu yoksa davranışsal mispricing mi olduğu açık bırakılır.

## İlgili Sayfalar

### Bu paperın ürettiği yeni faktör entity sayfası
- [[UMD]] — Up Minus Down momentum faktörü (PR1YR'ın standart literatür adı)

### Bu paperın update ettiği mevcut sayfalar
- [[factor_model]] — 4-faktör hiyerarşisi (FF3 + UMD)

### İlgili paperlar
- [[famafrench1993_three_factor]] — RMW eklenmemişti, momentum eklenmemişti;
  Carhart 4F bu modelin doğal extension'ı
- [[famafrench2015_five_factor]] — momentum dahil değil [s.14]; "for the LHS
  portfolios examined here, momentum slopes close to zero". Yani FF5 ve Carhart
  4F **paralel ama kesişmeyen** modeller — aynı core RMRF/SMB/HML üzerine farklı
  ek faktörler.
- [[cochrane2011_discount_rates]] — momentum'u factor zoo'nun en sık andığı
  anomalilerden biri olarak listeler [s.12]; "we routinely include momentum as
  a 'factor' even though we don't have a deep theory of why the momentum factor
  is priced" [s.20] — Carhart 4F'in epistemik konumunu özetler

### Cycle 12 ek (HLZ 2016 ingested)
- [[harvey_liu_zhu_2016_multiple_testing]] — UMD/MOM **sig her cutoff'ta**
  (Bonferroni / Holm / BHY hepsi sig); Carhart Tablo II t=4.46
  multiple-testing-corrected hurdle'ları geçer. HLZ Şekil 3 mark'i
  MOM'u sig her cutoff gösteriyor. Wiki'de momentum-based UMD exposure
  istatistiksel olarak en sağlam factor exposure'lardan biri.

### Cycle 13 ek (HXZ 2020 Replicating Anomalies ingested)
- [[hou_xue_zhang_2020_replicating_anomalies]] — UMD durumu [s.24]:
  **klasik 0.67% (t=3.66) sig + q-factor alpha 0.11% (t=0.43) INSIG** —
  q-factor Roe factor UMD'yi span ediyor. Üç darbe (in-sample + post-pub
  + MT) sig her cutoff; **dördüncü darbede q-factor span = Roe factor
  exposure proxy**. Yani UMD strateji baseline'da **risk premium proxy**
  olarak kullanılır, "saf alpha" değil. Momentum kategorisi 57/57
  anomaly içinde 37 sig (%65 replication rate); UMD bu kategorinin
  baseline factor'ü. Detay [[concepts/anomaly_replication]] aggregate
  tablosu; [[concepts/post_publication_decay]] dört darbe çerçevesi
  tablosu (UMD 3/4 q-factor span ile risk premium proxy).

### Henüz wiki'de olmayan, Carhart 1997'le ilgili paperlar
- Jegadeesh-Titman (1993) — 1-yıl momentum'un original keşfi (wiki tier listesinde
  yok ama PR1YR'ın temeli)
- Daniel-Moskowitz (2016) — "Momentum Crashes" (Tier 3 #60); momentum'un
  drawdown profili
- Asness-Frazzini-Pedersen 2019 (QMJ) — quality + momentum kombinasyonu

## Çelişkiler / Tartışmalar

> ⚠️ **Carhart 4F vs. Fama-French 5F**: İki paralel "post-FF3" extension. Her
> ikisi de FF3'e ek faktör koyar ama ikisi farklı: Carhart momentum'u, FF15
> profitability + investment'i ekler. **Doğrudan horse race wiki'de yok** —
> Hou-Xue-Zhang 2015 ve özellikle Hou-Xue-Zhang 2020 ingest edildiğinde
> doldurulacak. → [[meta/open_questions]] yeni Q16.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- Yıllık-frekans + value-weight + S&P 500 evren versiyonunda PR1YR/UMD primum'u
  ne ölçüde hayatta? Daniel-Moskowitz 2016 (momentum crashes) ve
  Frazzini-Israel-Moskowitz 2018 (trading costs) ingestleri ile cevaplanmalı
  → yeni Q16.
- 4F vs. 5F vs. HXZ4: Üç model arasında doğrudan horse race wiki'de yok →
  Hou-Xue-Zhang 2015/2020 ingestleri.
- Mutual fund persistence sonuçları (4F + expenses açıklar, hariç en kötü
  decile) — bu wiki'nin doğrudan amacı dışında ama "alpha" yorumu için kavramsal
  arka plan oluşturur.

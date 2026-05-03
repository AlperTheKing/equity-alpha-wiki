---
type: paper
authors: [Mohanram, Partha S.]
year: 2005
title: "Separating Winners from Losers among Low Book-to-Market Stocks using Financial Statement Analysis"
venue: "Review of Accounting Studies 10 (2-3), 133-170"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=403180
local_path: raw/papers/mohanram_2005_g_score.pdf
ingested: 2026-04-27
tags: [composite_score, fundamental_screen, growth, low_book_to_market, industry_median, R&D, conservatism, NDX_relevant, projenin_kalbi]
status: ingested
cycle_39_note: "Composite scoring paradigm literature continuity 4-paper × 17-yıl [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓: F-Score (Piotroski 2000) → G-Score (BU PAPER binary industry-median low-BM) → Stambaugh-Yuan MGMT/PERF (continuous composite 11-anomaly 2-cluster Cycle 39) → JKP 13 theme cluster (Cycle 27); G-Score industry-median methodology Stambaugh-Yuan within-cluster averaging paterni paralel"
---

# Mohanram (2005) — G-Score: Growth-Tarafı Komposit Fundamental Skor

> 📝 **Atıf konvansiyonu:** `[Tablo N]` numaralı tablolar; `[s. X]` paper iç sayfa
> numarası. Embedded text extract'ten okundu (`raw/papers/mohanram_2005_g_score.txt`).

> 📝 **Projenin kalbi paperı (B bloğu #2):** [[piotroski2000_f_score]]'un growth-tarafı
> muadili. Wiki'nin Nasdaq 100 stratejisi tasarımı için **şu anda wiki'de mevcut
> en güçlü** intangibles- ve large-cap-aware komposit skor kanıtı.

## TL;DR

8 bileşenli komposit fundamental skor (G-Score), **lowest BM quintile (growth)**
evrende winner-loser ayrımı için. 8 sinyal üç kategoride: **Profitability**
(ROA, CFO, accruals — 3) + **Naive Extrapolation / Stability** (earnings var,
sales growth var — 2) + **Conservatism / Future Growth** (R&D, capex, advertising
intensity — 3). **Tüm sinyaller endüstri medyanına göre level**'dir (2-digit SIC,
contemporaneous low-BM peer'lar) — F-Score'un "kendi geçmişine göre değişim"
yaklaşımından farklı [s.8]. Sample: 1979-1999, COMPUSTAT lowest BM, 20,866
firm-year. Headline: **High (G=6,7,8) − Low (G=0,1) = +21.2% mean size-adjusted
spread (yıl 1)** [Tablo 4, s.15-16]; tüm low-BM mean -6.0% → high group +3.3%
(yani sample mean +9.3% üstü). **Wiki için kritik 3 alt-sonuç:**
1. **Large-cap'te güçlü:** [Tablo 5 Panel A, s.17] büyük firma altgrubu spread
   **19.8% (sig 1%)** — F-Score'un large-cap zayıflığının tersine.
2. **NASDAQ'da daha güçlü:** [Tablo 5 Panel C, s.18] NASDAQ spread 26.4%, NYSE/AMEX 12.7%.
3. **Hi-tech partition'da çalışıyor:** [Tablo 5 Panel D, s.20] hi-tech firmaların
   spread 17.8%, hi-tech high group +5.2% (overall low-BM mean'in üstünde).
G-Score size, BM, momentum, accruals, equity issuance kontrol edildikten sonra
hayatta kalıyor — 1 puan G-Score = 3.9% size-adj return artışı [Tablo 7, s.22].

## Tek Cümle Tezi

Düşük BM (growth) evrende, traditional profitability sinyallerine + earnings/
growth stability sinyallerine + conservatism sinyallerine (R&D, capex,
advertising intensity) dayalı 8-bileşenli endüstri-relatif komposit skor,
mispricing-tabanlı bir sebeple geleceğin "winner" ve "loser" growth firmalarını
ayırır.

## G-Score: 8 Bileşen [s.7-11]

> 📝 **Tüm sinyaller `industry median (2-digit SIC, contemporaneous low-BM peers)`'a
> göre 0/1 binary.** F-Score'dan **methodoloji farkı**: F-Score "kendi geçmişine
> göre değişim" (Δ-based), G-Score "endüstri-medyana göre level" (industry-relative).

### Category 1 — Profitability (3 sinyal) [s.8-9]

| Sinyal | Tanım | "1" koşulu |
|---|---|---|
| `G1` | ROA = NI before extraordinary / beg. total assets | ROA > industry median |
| `G2` | Cash flow ROA = CFO / beg. total assets | CFO/Assets > industry median |
| `G3` | Accrual işareti | CFO > NI (accrual ≤ 0; Sloan paterni) |

> 📝 G1 ve G2 industry-median; G3 ise firm-spesifik (tüm firmalarda CFO > NI
> formülü).

### Category 2 — Naive Extrapolation / Stability (2 sinyal) [s.9-10]

| Sinyal | Tanım | "1" koşulu |
|---|---|---|
| `G4` | Son 5 yıl ROA varyansı | varyans **<** industry median (yani earnings stable) |
| `G5` | Son yıllar sales growth varyansı | varyans **<** industry median (yani sales growth stable) |

> 📝 Yazar [s.9-10]: "stable earnings + stable growth → mevcut performans 'şanslı yüksek
> realization' olma ihtimali daha düşük → naïve extrapolation hipotezinde
> hayal kırıklığı riski az". Earnings yerine sales growth tercih ediyor çünkü
> negatif earnings'li growth firmalarında earnings growth tanımsız [s.10 fn 5].
> Min 3 yıl geçmiş veri gereksinim; eksikse G4/G5 = 0.

### Category 3 — Conservatism / Future Growth (3 sinyal) [s.10-11]

| Sinyal | Tanım | "1" koşulu |
|---|---|---|
| `G6` | R&D / beg. assets | R&D intensity > industry median |
| `G7` | Capex / beg. assets | Capex intensity > industry median |
| `G8` | Advertising / beg. assets | Advertising intensity > industry median |

> 📝 Yazar [s.10-11]: "yüksek R&D/capex/advertising → hidden intangible asset →
> book equity yapay düşük → BE/ME yapay düşük (yani firma low-BM kategorisinde
> *muhasebe* sebebiyle, *over-valuation* sebebiyle değil)". Bu, **NDX-style
> tech firmalarda** R&D yüksekliğinin "growth-fırsat" sinyali olduğunu açıkça
> formüle eder.

### Toplam

`G_SCORE = G1 + G2 + G3 + G4 + G5 + G6 + G7 + G8`

Range: 0-8. Düşük (0-1) = "Low G", Yüksek (6-8) = "High G". Distribution
**left-skewed** çünkü G4/G5 min 3-yıl gerektiriyor + G6/G7/G8 firmalar genelde
sıfır olabilir [s.15 fn 10].

> 📝 **Equal-weighted binary toplam.** Yazar [s.14 fn 9]: "continuous değerler
> veya ağırlık ataması daha güçlü olabilir ama look-ahead bias riski yaratır
> veya holdout sample test gerekir".

## Empirik Sonuçlar (sayılarla)

### Örneklem [s.11-13]

- Evren: COMPUSTAT, **lowest BM quintile** (negatif BM'liler dahil)
- Dönem: 1979-1999 (21 yıl)
- 20,866 firm-year observations
- Returns: size-adjusted buy-and-hold, **fiscal year-end + 4 ay** itibarıyla
  başlar (Piotroski'nin 5 ay'ından bir ay daha agresif)
- Delisting Shumway (1997) yöntemiyle düzeltilmiş [s.12 fn 7]
- IPO firmaları (~%22 örneklemin) dahil

### Headline returns [Tablo 4, s.15-16]

**One-year size-adjusted returns:**

| Portföy | Mean | Median | %Positive | n |
|---|---|---|---|---|
| All low-BM | -6.0% | — | — | 20,866 |
| Low G (0-1) | **-17.9%** | -19.3% | 34.4% | ~2,000 |
| High G (6-8) | **+3.3%** | +8.0% | 60.0% | ~2,000 |

| Karşılaştırma | Mean Diff |
|---|---|
| **High − Low** | **+21.2%** (size-adj, yıl 1) |
| Yıl 2 (size-adj) | +15.8% (high +2.4%, low -13.3%) |
| Raw return spread (yıl 1) | +21.4% (high +17.4%, low -4.0%) |

> 📝 **Asimetri:** High group +9.3% sample mean üstü, low group -11.9% sample
> mean altı [s.16]. Yani strateji "torpedo'ları (loser) ayırmada" "winner'lar
> ayırmaktan" biraz daha güçlü ama her iki tarafta da çalışıyor.

### Size partition [Tablo 5 Panel A, s.17] — wiki için KRİTİK

| Size | High − Low spread | Mean (high) | Mean (low) | Anlam |
|---|---|---|---|---|
| Small | 22.8% | — | — | sig 1% |
| Medium | 23.1% | — | — | sig 1% |
| **Large** | **19.8%** | — | — | **sig 1%** |

> ⚠️ **F-Score'dan kritik fark:** [[piotroski2000_f_score]] [Tablo 4, s.19]
> large-cap spread 0.152 (t=1.88, p=0.224 — anlamlı değil). **Mohanram G-Score
> large-cap'te 19.8% spread sig 1%** — yazar yorumu [s.18]: "The strong result
> for large firms is crucial as such firms are also least likely to have illiquid
> stocks or restrictions on short-selling." **Wiki amacı için pozitif sinyal:**
> S&P 500 / Nasdaq 100 large-cap evrene transfer F-Score'a göre çok daha güçlü.

### Exchange listing partition [Tablo 5 Panel C, s.18-19]

| Exchange | High − Low spread | Mean (high) | Mean (low) |
|---|---|---|---|
| NYSE/AMEX | 12.7% | +1.8% | -10.9% |
| **NASDAQ** | **26.4%** | **+5.5%** | -21.0% |

> 📝 NASDAQ'da spread NYSE/AMEX'in 2x'ı. Yorum [s.19]: NASDAQ'da torpedo
> identification daha güçlü; long-NASDAQ-high + short-NYSE/AMEX-low strategy
> ~16.4% hedge return önerisi.

### Hi-tech partition [Tablo 5 Panel D, s.20]

Field-Hanka (2001) hi-tech SIC kodları (357, 367, 369, 382, 384, 737):

- Hi-tech firms: spread = **17.8%**; high group mean = **+5.2%** (overall low-BM
  mean +3.3%'in *üstünde*)
- Yorum [s.20]: "the strategy appears to be successful not just in identifying
  potential losers but in identifying winners as well amongst hi-tech firms."

### Time robustness [Tablo 6, s.21]

- 21 yılın **tümünde** strategy positive returns (1979-1999)
- 21 yılın 16'sında istatistiksel olarak anlamlı
- 21 yılın 17'sinde spread > 10%

### Risk-factor controls [Tablo 7, s.22]

`SRET1 = a + β·(SIZE, LBM, MOM, ACCR, EQ_OFF) + γ·G_SCORE + ε`

- **G_SCORE coefficient = 0.039 (sig 1%)**, R² 0.87% → 1.45% (G_SCORE eklenince)
- Yorum: 1 puan G_SCORE artışı = 3.9% size-adj return
- Headline 21.2% spread'in 20.3%'ı (≈%96'sı) bu kontrollerden sonra hayatta
  kalıyor [s.22-23]
- Yani G-Score size, BM, momentum, accrual, equity issuance kontrolünden
  bağımsız incremental information

### Risk vs. mispricing kanıtı [Tablo 10, s.27-28]

- High vs. Low: β neredeyse aynı (1.30 vs. 1.26) — sistematik risk farkı yok
- Return variability: low G-Score = 5.03%, high G-Score ~yarısı — yani **high
  group düşük volatil**
- Yazar yorumu [s.28]: yüksek getiri + düşük risk → mispricing açıklaması daha
  uygun (risk-based explanation çürür)

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | "Winner vs loser among low-BM stocks" başlıkta açık formüle edilmiş; G=0-1 (low) vs G=6-8 (high) extreme portfolios karşılaştırılır; size/analyst/exchange/IPO/hi-tech alt-bölümleri [Tablo 5, s.17-20] | ✅ doğrudan fit |
| **Annual rebalance** | 12-aylık buy-and-hold default; portföy formation fiscal year-end + 4 ay [s.12]; rebalans yıllık. 2-yıl horizon da test edilmiş [s.16] | ✅ doğrudan fit |
| **Large-cap evrene transfer** | [Tablo 5 Panel A, s.17] **Large size partition spread 19.8%, sig 1%** — Piotroski'nin large-cap zayıflığının tersine. Yazar [s.18]: "strong result for large firms is crucial as such firms are also least likely to have illiquid stocks or restrictions on short-selling". > ⚠️ **Asimetrik çift darbe:** Mohanram in-sample large-cap'te güçlü (F-Score'dan farklı) AMA McLean-Pontiff [Tablo 8] [[mclean_pontiff_2016_post_publication_decay]] post-pub decay büyük/likit firmalarda agresif → in-sample avantaj post-pub'da kısmen erozyona uğrayabilir. Modern replikasyon ([[li_mohanram2019_quality_value]] +6.06% all-firms continuous, 1973-2012) bu decay'i içselleştiriyor; +21.2% → +6.06% ~3.5x düşüş. | ✅ in-sample doğrudan fit; ⚠️ post-pub decay riski empirik olarak somut |
| **NDX intangibles / growth firms** | Low-BM = growth = NDX'in analog'u. Paper R&D + capex + advertising'i **explicit conservatism sinyali** olarak ekler [s.10-11]. Hi-tech partition spread 17.8%, hi-tech high group +5.2% [Tablo 5 Panel D, s.20]. NASDAQ partition'da spread 26.4% (NYSE/AMEX 12.7%'in 2x'ı) [Tablo 5 Panel C, s.18] | ✅ explicit fit |

**Strateji tasarımına net implikasyon:**

Bu paper, NDX evrene transferli komposit skorun **şu anda wiki'de mevcut** en
güçlü kanıt kaynağıdır. Ancak iki kayıt birlikte okunmalı:

1. **Test dönemi 1979-1999.** Paper'ın tamamı dot-com bubble *öncesi+içi*
   dönemde. Post-2000 tech-heavy NDX dönemi (özellikle 2008-2020 mega-cap tech
   yükselişi ve 2022 düşüşü) **out-of-sample**. Li-Mohanram 2019 (Tier 1 #12)
   ingest'i bu eksiği kısmen kapatabilir; tam doğrulama için modern data ile
   replikasyon gerek.
2. **Endüstri-medyan sinyalleri kalibrasyon riski.** G-Score'un 6 sinyali (G1,
   G2, G4, G5, G6, G7, G8) **2-digit SIC industry median**'a göre. **Nasdaq 100
   gibi 100-stock evrende** endüstri çeşitliliği zayıf (örn. çoğu firma SIC 73x
   software / 357 hardware) — endüstri medyanı az sayıda firmadan hesaplanır,
   noise yüksek olabilir. Bu kalibrasyon problemi [[meta/open_questions]] Q3
   ("Nasdaq 100'de G-Score test edildi mi?") ve Q8 (sektör nötrleştirme
   başarısızlığı) ile bağlantılı.

**Aday strateji adaptasyonları (Faz 3'te tartışılacak):**
- Industry median yerine S&P 500 / Nasdaq 100 *evren-içi* median kullanmak
- 2-digit SIC yerine GICS daha-rafine sektör seviyesi (aynı evrene yetecek
  granularite ile)
- Belli bir sektörde firma sayısı eşiğin altındaysa (örn. n<5) o sektörü
  evren medyanına agrege etmek

## Limitler ve Caveats

- **Test dönemi 1979-1999, post-2000 yok.** Yazarın kendi sınırlaması; Li-Mohanram
  2019 ile out-of-sample verisi eklenebilir. Modern NDX (özellikle FAANG dönemi
  2010-2024) **henüz wiki'de doğrulanmadı.**
- **Industry median 2-digit SIC**: GICS Level-3/4 daha rafine alternatif; modern
  endüstri sınıflandırma için yeniden test gerek.
- **Equal-weighted binary, look-ahead-aware** [s.14 fn 9]: continuous + factor-
  weighted tasarım look-ahead bias riski taşıyor (ağırlıklar nasıl belirlendi
  sorusuyla); modern cross-validation ile bu risk azaltılabilir.
- **R&D + capex + advertising'in tüm low-BM firmalarda 0 olabilmesi:**
  retail/finans firmaları gibi (low-BM olabilir) bu sinyaller meaningful değil
  → low-BM evren homogen değil. Industry-median düzeltmesi *kısmi* çözüm.
- **NASDAQ-overrepresented sample:** spread NASDAQ'da NYSE/AMEX'in 2x'ı; yani
  pure-NYSE evrenlerde performans daha zayıf olabilir.
- **Sample 20,866 firm-year ama 21 yıl boyunca → ~1,000 firma/yıl ortalama;
  S&P 500 / Nasdaq 100 evrenleri 100/500 firma → her yıl çok az gözlem ile
  decile/tercile sortları zorlaşır.**
- **Mispricing yorumu:** Yazar [s.28-30] explicit olarak risk-tabanlı açıklamayı
  reddediyor (β eşit, volatility ters orantılı). Wiki bu felsefi seçimde taraf
  tutmaz; primum'un gerçek olduğu kanıtı yeterli.
- **Reporting lag 4 ay:** Modern PIT data ile 60-90 güne kısalabilir.

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfa
- [[G_Score]] — faktör/skor entity sayfası

### Bu paperın update ettiği mevcut sayfalar
- [[F_Score]] — komplemanı; "Yumuşak Karnı" growth-evren açığını G-Score kapatır
- [[winner_loser_identification]] — paradigma value-side + growth-side ile
  tamamlandı
- [[contextual_fundamental_analysis]] — sinyal yorumu evren-bağımlılığı
  Mohanram'ın industry-median tasarım kararıyla pekiştirildi
- [[fundamental_scoring]] — "industry-median level" yöntemi yeni alt-paradigma

### İlgili paperlar (ingested)
- [[piotroski2000_f_score]] — F-Score, value-tarafı muadili; aynı author
  Piotroski Mohanram'ın acknowledgments'inde [s.1]
- [[famafrench1993_three_factor]] — low-BM (growth) faktörünün ham karşılığı
  HML kısa bacağı; Mohanram'ın "BM effect mispricing değil risk değil" tezi
  HML interpretation'a meydan okur
- [[famafrench2015_five_factor]] — Mohanram'ın R&D + capex + advertising
  conservatism sinyalleri RMW (profitability) ve CMA (investment) ile
  yapısal ortak alana sahip ama farklı parametrize

### İlgili ingested paperlar (B bloğu sentezi)
- [[li_mohanram2019_quality_value]] — G-Score'un **modern replikasyonu** (1973-2012,
  continuous rank-based, all-firms, **FF1997 48-industry**): hedge return
  +6.06% (orijinal +21.2%'den 3x düşük; sebep: sample uzatma + universe
  genişlemesi + binary→continuous + industry sınıflandırma revision).
  **Combined G&V/P 21.45%** — wiki'nin standalone+combined skor kombinasyonları
  içinde en yüksek hedge. Detay: [[comparisons/f_score_vs_g_score]].
- [[hou_mo_xue_zhang_2020_security_analysis]] — **G-Score test EDİLMEDİ**
  (kapsam dışı). Paper F-Score, V/P, Magic Formula, QMJ vb. test ediyor ama
  Mohanram G-Score yok. Bu, G-Score'un q-factor model lens'inde durumunu
  wiki'de **bilinmez** kılıyor → [[meta/open_questions]] Q25.
- [[mclean_pontiff_2016_post_publication_decay]] — 82 anomaly aggregate
  post-pub decay %35 (sig 1%). G-Score paperin explicit ref list'inde değil
  (sadece Sloan 1996, Banz 1981 vb. listed); aggregate decay multiplier
  G-Score'a uygulanır. Limited arbitrage [Tablo 8] büyük/likit firmalarda
  decay daha güçlü → G-Score'un in-sample large-cap güçlü sonucu (+19.8%
  sig 1%) post-pub'da kısmen erozyona uğrar; somut empirik kanıt
  Li-Mohanram 2019 modern replikasyon ~3.5x düşüş.

### G-Score komponentlerinin origin paperları (ingested)
- [[sloan1996_accruals_anomaly]] — **G3 (CFO > NI) bileşeninin origin paperı**.
  Mohanram s.9 fn 3'te accrual literatürüne explicit atıfla bağ. G3 firm-level
  threshold (industry-median değil) — Sloan'un original total accrual paterniyle
  doğrudan uyumlu. Sloan continuous decile → Mohanram binary CFO>NI
  simplifikasyonu, F-Score F_ACCRUAL ile ortak çekirdek.

### Cycle 12 ek (HLZ 2016 ingested)
- [[harvey_liu_zhu_2016_multiple_testing]] — G-Score "sig 1%" reported
  rakamı multiple-testing-corrected status: BM-Q1 origin (1979-99) sig
  yaklaşık |t| > 2.6 → BHY (3.0) sig yaklaşık; Bonferroni (3.78)
  borderline. Large-cap partition (+19.8%) ve NASDAQ partition
  (+26.4%) sig her cutoff'ta yaklaşık. **Asimetrik üç darbe:** in-sample
  large-cap güçlü ama MT borderline + post-pub decay agresif (Li-Mohanram
  modern 3.5x düşüş).

### Cycle 15 ek (Lev-Sougiannis 1996 ingested) — G6 literatür hattı kökü
- [[lev_sougiannis_1996_rd_capitalization]] — **G6 (R&D / Assets)
  bileşeninin literatür hattı kökü**. Mohanram'ın paper-spesifik
  conservatism yorumu (R&D = muhasebede gizli intangible → book equity
  yapay düşük) Lev-Sougiannis'in empirik kanıtı üzerine inşa edilebilir:
  R&D capitalization adjusted earnings + adjusted book equity
  value-relevant + R&D capital subsequent return prediction (RDC-
  yoğun firmalarda 4.57% yıllık [Tablo 5]). Cycle 9 Sloan F_ACCRUAL/G3
  origin pattern'inde **dual origin attribution** uygulandı: Mohanram
  paper-spesifik origin + Lev-Sougiannis literatür hattı kökü. Detay
  [[G_Score]] G6 Origin bölümü; [[concepts/intangibles_adjusted_accounting]]
  F bloğu anchor concept.

### Cycle 13 ek (HXZ 2020 ingested)
- [[hou_xue_zhang_2020_replicating_anomalies]] — Mohanram (2005)
  reference list'te (line 1567); G-Score için **specific HXZ replication
  rakamı paper extract'te yok**. Wiki için: Mohanram G-Score 447 anomaly
  census'da yer alıyor (paperdan teyit; reference list canon'unda),
  ama spesifik replication status (Mohanram'ın 8 sinyali NYSE-VW
  methodology'de hayatta mı?) Internet Appendix'te. G-Score'un
  industry-median methodology'si HXZ 2020 NYSE-VW konvansiyonundan
  farklı; replication adapte edilmiş olarak değerlendirilmesi gerekir.
  Q33 (post-2014 modern replication) ile birlikte JKP 2023 ek ingest
  G-Score-spesifik kanıtı sağlar. Detay
  [[concepts/anomaly_replication]] aggregate tablosu;
  [[concepts/post_publication_decay]] dört darbe çerçevesi tablosu
  (G-Score 2-3/4 asimetrik; Q31 ortogonal — composite scores census
  dışı).

### Henüz wiki'de olmayan, doğrudan ilgili paperlar
- Sloan (1996) — G3 accrual sinyali (Tier 1 #13)
- Lev-Sougiannis (1996) — R&D capitalization (Tier 2 #26)
- Beneish-Lee-Tarpley (2001) "Contextual Financial Statement Analysis" — Mohanram
  s.5 atfı; conditional fundamental analysis çatısı (Tier 3 / placeholder)
- Soliman (2003) — DuPont decomposition + industry adjustment; Mohanram'ın
  industry-median tasarım gerekçesi [s.8]

## Çelişkiler / Tartışmalar

> 📝 Mohanram explicit olarak "BM effect for low-BM = mispricing, not risk"
> tezini savunuyor [s.7-8, s.28-30]. Bu, FF92/FF93 [PDF p.53] "BM = financial
> distress proxy = rational risk premium" yorumuyla **felsefi** olarak çelişir
> ama empirik olarak **çelişmez** — hem risk hem mispricing yorumları aynı
> primum'la uyumludur ([[cochrane2011_discount_rates]] [s.20]). Wiki bu seçimde
> taraf tutmaz; primum'un gerçek olduğu yeterli.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q3 partial update]** "Mohanram G-Score Nasdaq 100'de test edildi mi?"
  → Mohanram 2005 NDX-spesifik test sunmuyor ama hi-tech (Field-Hanka 2001 SIC)
  altgrubu test ediyor: spread 17.8%, hi-tech high group +5.2% [Tablo 5 Panel D,
  s.20]. **Tam-NDX test post-2000 dönem için Li-Mohanram 2019 ingest'iyle
  cevaplanır.**

- **[Q19 yeni]** Mohanram 2-digit SIC industry-median kullanıyor [s.8]. **NDX
  100-stock evrende endüstri çeşitliliği zayıf** (>%70 firma SIC 73x/357/367
  altında olabilir) → industry-median "noise"lu olur. **Nasdaq 100 evrene
  transferde hangi sektör sınıflandırma kullanılmalı?** Adaylar:
  1. GICS Level-2 (çok kaba)
  2. GICS Level-4 (çok rafine, n<5 risk)
  3. Universe-içi median (sektörsüz)
  4. Hibrit: GICS-3 + min-n eşiği altında universe median'a fallback
  Bu Q19 Faz 3 tasarım kararı; doğrudan literatür kanıtı yok, çoğu paper CRSP
  all-stocks evrende çalışıyor.

- **[Q20]** G-Score 1979-1999 örneğinden post-2000 tech bubble dönemine
  hayatta mı? Özellikle 2010-2024 FAANG-dominant NDX'e transferi? Li-Mohanram
  2019 (Tier 1 #12) bu boşluğun bir kısmını adresler.

- **[Q5 partial-stronger update]** Post-publication decay aggregate cevabı
  [[mclean_pontiff_2016_post_publication_decay]] üzerinden: %35 (sig 1%);
  G-Score paper-spesifik decay rakamı paperin extract'inde tek-tek listed
  değil. Modern empirik karşılaştırma için Li-Mohanram 2019 sample
  1973-2012 spread +6.06% (all-firms continuous), orijinal +21.2%'den ~3.5x
  düşüş. Saf decay komponenti karışık etken (sample uzatma + universe
  genişlemesi + binary→continuous + industry classification revision).
  Detay: [[post_publication_decay]] decay-adjusted spread tablosu.

- **[Open question Q1 partial update]** "Value premium post-2000" — Mohanram
  low-BM (growth) tarafında 1979-1999'da G-Score'un growth firmalarda da
  pozitif size-adjusted return (high group +3.3%) ürettiğini gösteriyor; yani
  **growth firmaların tamamı negatif size-adj return üretiyor demek yanıltıcı**
  — winner/loser ayrımı her iki style'da da diferensiyel.

---
type: paper
authors: [Sloan, Richard G.]
year: 1996
title: "Do Stock Prices Fully Reflect Information in Accruals and Cash Flows About Future Earnings?"
venue: "The Accounting Review, Vol. 71, No. 3 (July 1996), pp. 289-315"
url: https://www.jstor.org/stable/248290
local_path: raw/papers/sloan_1996_accruals_anomaly.pdf
ingested: 2026-04-28
tags: [accruals_anomaly, earnings_quality, mispricing, investor_fixation, C_blok_kalbi, F_ACCRUAL_origin, G3_origin]
status: ingested
cycle_38_note: "Sloan accruals zinciri paralel + Ball-GLN cash flow + accruals decomposition methodology [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓; Ball-GLN [s.10] explicit 'inconsistent with Sloan's (1996) hypothesis that investors fixate on profitability per se' — Cop subsumption Sloan fixation hypothesis çürütme + mispricing alternative interpretation (under-reaction to cash flow gradually corrected); wiki taraf tutmaz Cochrane mathematical equivalence; Ball-GLN Profitability zinciri 4. halka Sloan zinciri paralel + QMJ 4-dimension birleşim noktası"
cycle_39_note: "Stambaugh-Yuan 11 anomaly Cluster 1 (MGMT) içinde Sloan accruals dahil [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; mispricing composite scoring P1 6 anomaly avg ranking accruals dahil; sentiment-aware short-leg asymmetry mispricing interpretation Sloan original mispricing hipotezi paralel + Ball-GLN Cop subsumption complementary methodology farkı (Cycle 38 Cop subsumes Acc + Cycle 39 Stambaugh-Yuan UMO1 includes Acc within composite); Sloan zinciri (mispricing/accruals 4 paper × 23 yıl) + Stambaugh-Yuan composite mispricing zinciri 3. halka"
---

# Sloan (1996) — Accruals Anomaly Origin Paper

> 📝 **Atıf konvansiyonu:** `[Tablo N]` ve `[s. X]`. Embedded text extract:
> `raw/papers/sloan_1996_accruals_anomaly.txt`. Sayfa numarası dergi pp.289-315
> aralığında.

> 📝 **C bloğunun #1'i** — earnings quality / accruals / investment.
> [[F_Score]] F_ACCRUAL bileşeninin ve [[G_Score]] G3 (CFO > NI) bileşeninin
> **origin paper**. Şu ana kadar Piotroski/Mohanram'a dolaylı atıflarla anılıyordu.

## TL;DR

**Earnings = Cash flow + Accruals** decomposition'ı. Cash flow component
earnings persistence'ı **yüksek**, accrual component persistence'ı **düşük**
(mean-reverting). Yatırımcılar bu farkı fiyatlamıyor — "investor fixation on
earnings". **Trade:** uzun düşük-accrual decile + kısa yüksek-accrual decile.
Sample: 1962-1991, NYSE+AMEX COMPUSTAT, 40,679 firm-year. Headline hedge return
**10.4% per year (t=4.71)** — raw [Tablo 6]. Multi-year decay: 10.4% (yıl 1) →
4.8% (yıl 2) → daha az [Tablo 6]. Quarterly earnings announcement
penceresinde abnormal return concentration: market'in **delayed reaction**'ı
explicit gözlemlenir [Tablo 7-8]. **Wiki için kritik:** F_ACCRUAL ve G3
binary versiyonları Sloan'un continuous decile sortunun simplifikasyonu;
F-Score ve G-Score'un earnings-quality omurgası bu paper.

## Tek Cümle Tezi

Cash flow ve accrual bileşenlerinin earnings persistence'ı farklı (cash flow
yüksek, accrual düşük); yatırımcılar bu farkı fiyatlamıyor; sonuç olarak
düşük-accrual / yüksek-CFO firmaları sistematik pozitif abnormal return
üretir, yüksek-accrual firmaları sistematik negatif.

## Ana mekanizma

### Earnings decomposition [s.291-292]

```
Earnings_t = CFO_t + Accruals_t
```

**Persistence farkı:**
- `CFO` component → yüksek persistence, geleceğe taşınır
- `Accrual` component → düşük persistence, mean-reverting

### "Investor fixation" [s.293, H2]

Yatırımcılar earnings'in **toplam değerine** fixate olur, alt-bileşenlere
attention etmez. Sonuç:
- Yüksek-accrual firmalar **overvalued** (earnings yüksek görünüyor ama
  sürdürülemez)
- Düşük-accrual firmalar **undervalued** (earnings düşük görünüyor ama CFO
  güçlü)

### Predictable abnormal returns [s.293-294, H2(ii)-(iii)]

- Long bottom-decile-accrual + short top-decile-accrual → **+10.4%/yıl** raw
  hedge return [Tablo 6]
- Abnormal return'lerin önemli kısmı **future earnings announcement
  pencerelerinde** realize ediyor [Tablo 8] → market'in delayed reaction
  hipotezini destekler

## Accrual hesaplama

### Sloan'ın balance-sheet-based formülü [s.293, eq.]

```
Accruals = (ΔCA − ΔCash) − (ΔCL − ΔSTD − ΔTaxesPayable) − Depreciation
```

- `ΔCA`: change in current assets
- `ΔCL`: change in current liabilities
- `ΔSTD`: change in short-term debt included in current liabilities
- `ΔTaxesPayable`: change in income taxes payable
- `Depreciation`: depreciation and amortization

Total assets ile scale edilir.

> 📝 **Modern alternatif: cash flow statement (CFS)-based:** 1988 sonrası
> Statement of Cash Flows zorunlu olduğunda doğrudan CFO raporlanır:
> `Accruals = NI − CFO`. Sloan paperı 1962-1991 sample'ı içerdiği için 1988
> öncesinde balance-sheet formülü kullanır. Methodology farkı sonuçları
> küçük ölçüde değiştirir → bkz. [[meta/data_gaps]] "accrual computation
> methodology variance".

## Empirik Sonuçlar (sayılarla)

### Örneklem [s.290, s.291, Tablo 1]

- Evren: NYSE + AMEX (NASDAQ dahil değil), COMPUSTAT
- Dönem: 1962-1991 (30 yıl)
- 71,732 firm-year initial; **40,679 firm-year** (filtreler sonrası)
- Annual rebalans (fiscal year-end + standart reporting lag)

### Persistence farkı [Tablo 2-3]

`Earnings_{t+1} = α + β·Earnings_t + ε`

**Decomposition formu** [Tablo 3]:
`Earnings_{t+1} = α + β_CFO·CFO_t + β_Accrual·Accrual_t + ε`

- `β_CFO` (cash flow persistence) **>** `β_Accrual` (accrual persistence)
- Yani aynı %1 earnings artışı, CFO kaynaklıysa daha çok geleceğe taşınır,
  accrual kaynaklıysa daha az
- H1 hipotezi destekleniyor

### Hedge return [Tablo 6, s.305]

**Raw 1-yıl returnleri (annual portfolio rebalans):**

| Decile | Annual abnormal return | t-stat |
|---|---|---|
| 1 (lowest accrual) | +4.9% | 1.17 |
| 10 (highest accrual) | -5.5% | -3.98 |
| **Hedge (1−10)** | **+10.4%** | **+4.71** |

Size-adjusted versiyonda hedge biraz düşer ama anlamlı kalır:
- Size-adj hedge: ~+2.9% (t=1.64) — *daha küçük ama explicit pattern korunur*

> 📝 Sloan'ın headline iddiası raw +10.4%; size-adjusted versiyonu daha küçük
> ama yön aynı. Bu, accruals anomaly'nin **size-loaded** olabileceği işareti
> — small-cap firmalar accrual decile uçlarında dominant. Wiki için kritik:
> S&P 500 / NDX large-cap evrene transferin sınırlı olabileceği uyarısı.

### Multi-year decay [Tablo 6 multi-yıl panel]

Hedge return'ün zaman üzerindeki düşüşü:
- Year 1 (1-yıl post-formation): **+10.4%** (t=4.42)
- Year 2: **+4.8%** (t=2.41)
- Year 3: daha küçük (paperdan teyit)

> 📝 Mean-reverting pattern: anomalies'in 1-yıl pencerede yoğunlaştığı,
> 2-3 yıllık holding period ile dilüe olduğu gözlemi. Strateji tasarımı için
> **annual rebalance optimum** — wiki amacı ile uyumlu.

### Earnings announcement window concentration [Tablo 7-8, s.310-311]

- 1973-1991 alt-örneklem (CFS data availability), 16,795 firm-year
- Yıllık abnormal hedge return'ün önemli kısmı (~10-20%) **4 quarterly
  earnings announcement window**'larında (3-day around announcement)
  realize ediyor
- Bu, market'in **delayed reaction** hipotezini destekler — earnings surprise
  yokken market accrual signal'i fiyatlamıyor; earnings raporlandığında
  pricing düzeltiliyor

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Decile sort üzerinden long-bottom + short-top hedge formülü; Sloan headline strategy explicit decile spread (top-N selection paradigmasının saf hali) | ✅ doğrudan fit |
| **Annual rebalance** | Annual report'tan accrual hesaplaması → yıllık portfolio formation; multi-year decay analizi annual horizon doğal seçim olduğunu gösterir [Tablo 6] | ✅ doğrudan fit |
| **Large-cap evrene transfer** | Sample NYSE + AMEX (NASDAQ HARİÇ) → mid-large-cap dominantlığı var ama explicit size-conditional analiz yok bu paperda. Size-adjusted hedge return raw'dan küçük → **anomaly size-loaded olabilir** | ⚠️ size-adjusted spread daha küçük; large-cap-only kanıtı yok; literatürde Bhojraj-Swaminathan 2009 vb. takip paperlar (henüz wiki'de yok) konuyu detaylandırır |
| **NDX intangibles / growth firms** | Sample 1962-1991 — modern intangibles dönemi öncesi (R&D capitalization tartışması 1990s sonrasında olgunlaştı). Tech firmalar sample'da var ama R&D giderleştirmesi accrual hesaplamasını distorts edebilir; paper bunu adresleme yok | ⚠️ kapsam dışı / scope-edge; Lev-Sougiannis 1996 (Tier 2 #26), Peters-Taylor 2017 (Tier 2 #27) ingestleri ile cevap |

**Strateji tasarımına net implikasyon:**

Bu paper, B bloğu kompositlerinin (F-Score, G-Score) earnings-quality
omurgasını sağlar — F_ACCRUAL ve G3 binary versiyonları, Sloan'un continuous
decile sortunun "winner-loser identification" çatısına simplifikasyonu.
Üç dengeli kayıt:

1. **Headline +10.4% raw hedge return (1962-1991)** large-cap evrene
   transferli değil; size-adjusted versiyonda ~2.9% (t=1.64) marjinal.
   S&P 500 / NDX strateji tasarımında accrual standalone signal yerine
   F_ACCRUAL / G3 **binary** versiyonu komposit skor içinde kullanılır
   ([[Accruals]] sayfasında detay).
2. **Modern intangibles dönemi öncesi sample**: Tech firma accrual ölçümü
   wiki amacı için (NDX) açık soru → yeni Q26.
3. **Multi-year decay pattern**: 1-yıl rebalanstan sonra 2-3 yıllık holding
   anomaly'nin gücünü sulandırır → wiki amacı için annual rebalance
   default'u empirik olarak destekleniyor.

## Limitler ve Caveats

- **NYSE + AMEX evren, NASDAQ HARİÇ:** Modern strateji tasarımı için NDX
  evrene transfer için NASDAQ-dahil replikasyon gerekli (Green-Hand-Soliman
  2011 ve diğer follow-up paperlar Tier listesinde değil).
- **Sample 1962-1991, post-1996 yok:** Sloan paperı kendi sample'ı; Green-
  Hand-Soliman 2011 "death of accruals anomaly" post-publication decay
  raporlar (henüz wiki'de yok).
- **Balance-sheet-based accrual formülü** (1988 öncesi sample-period
  zorunluluğu): Modern uygulamalarda CFS-based formül daha temiz ama
  sonuçlar büyük ölçüde benzer — bkz. [[meta/data_gaps]].
- **Total accruals decomposition yok:** Sloan total accruals kullanır.
  Discretionary vs non-discretionary accruals (Jones model 1991,
  Modified Jones Dechow vd. 1995) ile alt-decomposition sonraki literatür.
- **Mispricing yorumu explicit:** "Investor fixation" davranışsal yorum.
  HMXZ 2020 [[hou_mo_xue_zhang_2020_security_analysis]] q5 model lens'inde
  accruals'un **risk premium** yorumu mümkün — felsefi seçim, wiki taraf
  tutmaz.
- **Earnings announcement window kanıtı 1973-1991 alt-örneklem** (CFS data
  pre-1973 sınırlı): paper içi sample küçülmesi.
- **Large-cap evrene transfer için doğrudan kanıt yok:** Size-adjusted
  hedge'in raw'dan küçük olması işaret veriyor ama explicit large-cap-only
  test yok.

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfalar
- [[Accruals]] — total accrual factor entity (Sloan headline metodoloji)
- [[accruals_anomaly]] — concept sayfası (Sloan'ın spesifik mekanizması:
  fixation + persistence farkı + delayed reaction)

### Bu paperın update ettiği mevcut sayfalar
- [[F_Score]] — F_ACCRUAL bileşeninin **origin paper'ı**
- [[G_Score]] — G3 (CFO > NI) bileşeninin **origin paper'ı**
- [[earnings_quality]] — Sloan paperı bu sayfanın kanonik omurgası
- [[comparisons/f_score_vs_g_score]] — F_ACCRUAL ↔ G3 ortak Sloan referansı

### İlgili paperlar (ingested)
- [[piotroski2000_f_score]] — F_ACCRUAL Sloan'a explicit atıf
- [[mohanram2005_g_score]] — G3 Sloan paterni
- [[novy_marx_2013_gross_profitability]] — **Cycle 23**; **paralel
  quality zinciri** (Sloan = mispricing/accruals vs Novy-Marx =
  profitability/quality); Novy-Marx [s.7 fn 1] Sloan accruals cite +
  Appendix A.3 GP/A predictive power persists controlling for accruals
  → bağımsız mekanizma. İki paralel zincir QMJ 4-dimension'da
  birleşiyor (Profitability dimension 6 measure içinde ACC + GPOA).
- [[li_mohanram2019_quality_value]] — F-Score ve G-Score'da Sloan accrual
  bileşeni continuous version'da test edilmiş
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 model lens'inde Sloan
  accruals doğrudan test edilmiş değil ama Bartram-Grinblatt agnostic
  analysis ve Penman-Zhu fundamental strategies accruals bileşenleri
  içerir; q-factor modelin investment factor (I/A) accruals ile yapısal
  bağda
- [[mclean_pontiff_2016_post_publication_decay]] — 82 anomaly aggregate
  post-pub decay ≈%35; reference list'te Sloan 1996 explicit listed
  ([s.28, ref]); paper anomaly-level decay rakamlarını tek-tek raporlamaz
  → Sloan'a uygulanan decay aggregate ortalama üzerinden
  ([[post_publication_decay]] decay-adjusted spread tablosu). Limited
  arbitrage [Tablo 8]: büyük/likit/divid-payer firmalarda decay daha
  güçlü → Sloan accruals'ın size-loaded zayıflığı (size-adj +2.9%
  marjinal) ile uyumlu; large-cap'te yapısal olarak silinmesi beklenir.

### Cycle 12 ek (HLZ 2016 ingested)
- [[harvey_liu_zhu_2016_multiple_testing]] — Sloan accruals **paperin ref
  list'inde explicit listed** [s.28]. Multiple-testing-corrected status:
  **raw +10.4% hedge t=4.71 sig her cutoff'ta** (Bonferroni / Holm / BHY
  hepsi sig). **Size-adj +2.9% t=1.64 tüm cutoff'larda insig** (klasik
  düzeyde de marjinal; HLZ kesin çürütüyor).

### Cycle 15 ek (Lev-Sougiannis 1996 ingested) — Q26 mekanizma cevabı
- [[lev_sougiannis_1996_rd_capitalization]] — Sloan total accruals
  formülünün **R&D giderleştirme nedeniyle tech firmalarda yapay sinyal
  ürettiği mekanizma** [[concepts/earnings_quality]] sayfasında detay.
  R&D giderleştirme working capital değişimi azaltır → traditional
  accrual "düşük" görünür ama gerçekte capex-tipi yatırım yapılıyor
  (Lev-Sougiannis useful life 5-9 yıl). Sloan dört darbeden 4/4
  hayatta ama **manufacturing-heavy 1962-1991 sample**; modern tech-
  heavy NDX evrende bias büyür. Q26 partial-stronger cevap; tam
  intangibles-aware accruals Peters-Taylor 2017 (Cycle 16) ile.

### Cycle 13 ek (HXZ 2020 ingested) ⭐ DÖRT DARBE 4/4 HAYATTA
- [[hou_xue_zhang_2020_replicating_anomalies]] — Sloan operating
  accruals (Oa) HXZ 2020 paperin abstract'ında **explicit listed
  significant** [s.5] ("Sloan (1996) operating accruals" — replicate
  edilen "smaller in magnitude than -10.4% per annum (t=-4.71) reported
  by Sloan"). **Q-factor model lens'inde de hayatta:** [s.27]
  klasik high-minus-low -0.27% (t=-2.13) + **q-factor alpha -0.54%
  (t=-3.77) sig**. Investment factor loading tiny (-0.02 t=-0.23);
  Roe-factor loading 0.26 (t=4.13) yanlış yönde. **Sloan operating
  accruals dört darbenin TAMAMINDA hayatta kalan nadir anomaly:**
  in-sample sig + post-pub aggregate decay + MT-corrected sig +
  HXZ replication + q-factor alpha sig. Wiki C bloğu omurgasının
  **statistical güçlenmesi**. Discretionary accruals (Dac) [s.27]
  q-factor alpha -0.64% (t=-4.37) sig — Sloan'ın decompose versiyonu;
  Net operating assets, dWc, dFin paralel kanıt. **Richardson-Sloan-
  Soliman-Tuna 2005 total accruals (Ta)** explicit insig [s.5] —
  modern revisit çürütülmüş, Sloan 1996 hayatta. Detay
  [[concepts/anomaly_replication]] aggregate tablosu;
  [[concepts/post_publication_decay]] dört darbe çerçevesi tablosu.

### Henüz wiki'de olmayan, doğrudan ilgili paperlar
- Richardson-Sloan-Soliman-Tuna (2005) "Accrual Reliability, Earnings
  Persistence and Stock Prices" (Tier 2 #35) — Sloan'ın accrual
  decomposition'unu reliability'ye göre genişletir
- Hirshleifer-Hou-Teoh-Zhang (2004) "Net Operating Assets" (Tier 2 #36) —
  cumulative accruals
- Fairfield-Whisenant-Yohn (2003) — accrual + growth ayrımı (Tier 2 #37)
- Green-Hand-Soliman (2011) "death of accruals anomaly" (Tier listesi
  dışında, Cycle 10+ aday) — Sloan-spesifik post-pub decay anchor

### Cycle 19 ek (Asness QMJ 2019 ingested) — Sloan zinciri 4. halka

[[asness_frazzini_pedersen_2019_qmj]] **QMJ Profitability dimension
ACC component** (low accruals = high quality):
- Asness paper [s.7] **Sloan 1996 explicit cite ediyor** (reference list
  içinde listed) — F_ACCRUAL/G3 origin paterni paralel; M-Score TATA
  Sloan değil Healy-Jones'tu (Cycle 18 keşif).
- Methodology paralel (NI − CFO; aynı yapı); literatür hattı kökü
  **Sloan 1996** ✅ — F_ACCRUAL/G3 paterni korunuyor.

**Sloan zinciri** (4 paper, 23 yıl arayla, methodology paralel +
literatür hattı kökü Sloan):
1. Sloan 1996 (origin) — accruals anomaly
2. Piotroski 2000 F_ACCRUAL (Cycle 9; binary version)
3. Mohanram 2005 G3 (Cycle 9; firm-level threshold)
4. **Asness 2019 QMJ Profitability ACC** (Cycle 19; z-score component)

**M-Score TATA paterninden farkı**: Beneish 1999 reference list'inde
Sloan 1996 explicit listed DEĞİL (Healy 1985 + Jones 1991 cite ediyor;
earnings management research). Yani Sloan zinciri **F_ACCRUAL/G3/QMJ
ACC** üçlüsünde direct kayıt; M-Score TATA paralel paradigma ama
literatür hattı farklı.

**Wiki için**: Sloan total accruals anomaly origin literature 23 yıl
boyunca **mispricing detection paradigmasının çekirdek bileşeni**;
QMJ Profitability ACC bu paradigmanın 2019'a kadar uzanan continuity
kanıtı. Detay [[concepts/earnings_quality]] forensic boyut sub-section
+ [[QMJ]] origin attribution dual pattern tablosu.

### Cycle 18 ek (Beneish 1999 ingested) — TATA paralel methodology

[[beneish_1999_m_score]] [s.12] **TATA (Total Accruals to Total Assets)**
bileşeni Sloan total accruals ile **methodology paralel** (working
capital change - depreciation; aynı yapı) AMA **iki epistemik düzlem**:

| Boyut | Sloan 1996 | Beneish 1999 TATA |
|---|---|---|
| Hedef | Cross-section returns (mispricing) | Manipulator/non-manipulator binary (fraud) |
| Metodoloji | Decile sort + hedge return | Probit indeks bileşen (8'den 1) |
| Mekanizma | Investor fixation + persistence | GAAP violation detection |
| Sonuç tipi | Long Q5 short Q1 | M-Score component (filter) |

**Origin attribution dual pattern (Cycle 18 keşif)**:
- F_ACCRUAL/G3 origin Sloan literatür hattı kökü (Cycle 9'da işaretlendi)
- **M-Score TATA origin attribution farklı**: Beneish reference list
  [s.20-21] **Sloan 1996 explicit listed DEĞİL**; Healy 1985 + Jones
  1991 cite ediyor (earnings management research)
- Yani: TATA methodology paralel ama literatür hattı **farklı**
  (Sloan return prediction vs Healy-Jones earnings management)

**Wiki için**: Sloan accruals + M-Score TATA dual signal **complementary**
(ortogonal değil — methodology aynı temelden, epistemik düzlem farklı):
- Sloan factor exposure = mispricing detection (return prediction)
- M-Score TATA = forensic detection bileşeni (binary classification)
- Combined kullanım possible: Sloan sort + M-Score filter (high TATA
  + high M-Score eleminating manipulators)

Detay [[concepts/earnings_quality]] forensic boyut sub-section;
[[M_Score]] origin attribution dual pattern.

## Çelişkiler / Tartışmalar

> 📝 Sloan'ın "investor fixation" mispricing yorumu vs HMXZ q-factor model
> "risk premium" yorumu felsefi olarak çelişir, empirik olarak çelişmez
> (Cochrane mathematical equivalence). Wiki taraf tutmaz; pratik strateji
> tasarımı için her iki yorum aynı portföye götürür.

> 📝 **Sloan total accruals ↔ CGS asset growth korelasyonu:**
> [[cooper_gulen_ion2018_asset_growth_factor_models]] [s.6, Section 4] asset
> growth'un alt-bileşenlerini analiz eder; working capital changes hem Sloan
> accruals'ın hem CGS asset growth'un büyük bileşeni → iki anomaly **yapısal
> overlap**. Decompose için Fairfield-Whisenant-Yohn (2003) (Tier 2 #37)
> accrual + asset growth ayrımı yapar — wiki'de yok. Wiki için: F_ACCRUAL
> (binary) ile CMA / Asset_Growth factor exposure'u birlikte kullanmak
> partial redundancy.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q5 fully-answered (aggregate); partial (paper-spesifik)]**
  Post-publication decay: McLean-Pontiff 2016 ingest edildi
  [[mclean_pontiff_2016_post_publication_decay]] [Tablo 3, s.32] — 82
  anomaly aggregate **%35 post-pub decay (sig 1%)**, %10 statistical bias
  (insig). Reference list'inde Sloan 1996 explicit ([s.28]) ama paper
  individual anomaly decay rakamlarını tek-tek raporlamaz; Sloan-spesifik
  decay için aggregate baseline + Green-Hand-Soliman 2011 (Tier listesi
  dışında, "death of accruals anomaly" başlığı) ek kanıt sağlar — wiki'de
  yok. Sloan size-adj +2.9% marjinal sonucu McLean-Pontiff Tablo 8
  limited arbitrage bulgusuyla **uyumlu**: büyük/likit firmalarda decay
  agresif → Sloan accruals large-cap'te zaten zayıf, post-pub silinmesi
  beklenir. Detay [[post_publication_decay]] decay-adjusted spread
  tablosu.
- **[Q6 partial-stronger update]** ML asset pricing'de feature importance:
  Sloan accruals modern ML papers'da (Gu-Kelly-Xiu 2020, henüz ingest
  edilmedi) genelde yüksek-önemde feature olarak çıkar — Sloan baseline,
  ML ingestlerinde teyit.
- **[Yeni Q26]** Tech firmalarda accrual ölçümü: R&D giderleştirme
  geleneksel total accrual formülünü distorts ediyor mu? Tech firma'nın
  R&D'si capex gibi davransa accrual formülü pozitif olur, ama R&D
  giderleştirildiği için accrual hesabı yanlış işaret verebilir. NDX
  tech-heavy evrene transfer için kritik. Lev-Sougiannis 1996,
  Peters-Taylor 2017 ingestleri ile cevap.

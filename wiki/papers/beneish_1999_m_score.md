---
type: paper
authors: [Beneish, Messod D.]
year: 1999
title: "The Detection of Earnings Manipulation"
venue: "Financial Analysts Journal 55(5): 24-36 (Sep/Oct 1999)"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=147511
local_path: raw/papers/beneish_1999_m_score.pdf
ingested: 2026-05-01
tags: [forensic, M_Score, earnings_manipulation, fraud_detection, Faz_1_son_zorunlu, Tier_1_15, hard_kriter]
status: ingested
cycle_39_note: "Composite scoring paradigm cross-link [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; M-Score forensic 8-component manipulator detection Stambaugh-Yuan composite mispricing scoring 11-anomaly 2-cluster paterni paralel methodology evolution; Q9 partial-stronger Cycle 39 (Beneish + composite score; Stambaugh-Yuan composite scoring paradigm cross-evidence)"
---

# Beneish (1999) — M-Score: Earnings Manipulation Detection

> 📝 **Atıf konvansiyonu:** `[Tablo N]` numaralı tablolar; `[s.X]`
> SSRN working paper PDF sayfa numarası (June 1999 draft, 25 sayfa).
> Embedded text extract: `pdftotext -layout` ile lokal okuma.
> JFA 1999 yayın sayfa numaraları farklı olabilir.

> 📝 **Faz 1 son zorunlu Tier 1 ingest** — Cycle 18. **C/D hard
> kriter forensic** kategorisi tamamlandı; Cycle 19 KARAR NOKTASI
> öncesi son disiplin paperı.

## TL;DR

Beneish 1999, **earnings manipulation detection için 8-bileşenli
probit model** geliştirir: financial statement signals manipulators'ı
non-manipulators'tan ayırır. **Sample**: 74 manipulators (49 SEC AAERs
+ 25 news media, 1987-1993) + 2332 COMPUSTAT non-manipulators
(2-digit SIC matched, 1982-1992). Estimation 1982-1988 (50+1708),
holdout 1989-1992 (24+624).

**Methodology**: Probit + WESML (Weighted Exogenous Sample Maximum
Likelihood) — state-based oversampling bias correction. Pseudo-R²
30.6% (WESML) / 37.1% (unweighted).

**8 değişken — 5 sig + 3 insig** [Tablo 3]:

| Variable | Definition | Coef | t-stat | Sig? |
|---|---|---|---|---|
| **DSRI** Days Sales in Receivables Index | (AR/Sales)_t / (AR/Sales)_{t-1} | **0.920** | **6.02** | ✅ |
| **GMI** Gross Margin Index | (GM)_{t-1} / (GM)_t | **0.528** | >2σ | ✅ |
| **AQI** Asset Quality Index | (Non-current ex-PPE / TA)_t / (...)_{t-1} | **0.404** | **3.20** | ✅ |
| **SGI** Sales Growth Index | Sales_t / Sales_{t-1} | (sig pozitif) | **>5σ** | ✅ |
| **TATA** Total Accruals to TA | (ΔWC - Dep) / TA | (sig pozitif) | sig | ✅ |
| **DEPI** Depreciation Index | DepRate_{t-1} / DepRate_t | (insig) | — | ❌ |
| **SGAI** SG&A Index | (SGA/Sales)_t / (SGA/Sales)_{t-1} | (insig) | — | ❌ |
| **LVGI** Leverage Index | (Debt/TA)_t / (Debt/TA)_{t-1} | (insig) | — | ❌ |

**Headline performance**: Holdout sample model identifies **~50%
manipulators prior to public discovery**; manipulators ~10x more
likely than controls (mean probability 0.237 vs 0.022 unweighted).

**Manipulators karakteristikleri** [Tablo 1, s.21]: Smaller (median
TA $43M vs control $96M), less profitable, more levered, **higher
growth** (median sales growth 34.4% vs 9.4%), similar market value.

## Tek Cümle Tezi

Financial statement variables (8-bileşenli probit indeks) earnings
manipulators'ı non-manipulators'tan **systematic ve out-of-sample
robust** şekilde ayırır; M-Score forensic screening tool olarak
investing professionals için kullanılabilir, ama **further
investigation gereken classification errors** önemli.

## Ortaya Konan Sinyal/Faktör

**Yeni factor entity AÇILDI** (Cycle 18 plan onayı: F-Score / G-Score
paralel pattern, en eski açık placeholder'ın doldurulması):

- [[M_Score]] — Beneish 8-bileşenli forensic composite; binary
  classification (manipulator probability)

> 📝 **Paper'ın factor-level dolaylı katkıları wiki'de:**
> - [[F_Score]] — Cycle 5'ten beri açık `(sonra) [[M_Score]]`
>   placeholder doldurulur; F & M screen-and-rank yaklaşım concept
>   seviyesinde bağ
> - [[G_Score]] — forensic katman ihtiyacı + tech firma false
>   positive riski (Q47 yeni)
> - [[Accruals]] — Sloan total accruals factor entity'sine M-Score
>   TATA cross-link (methodology paralel, epistemik düzlem farklı)

## Metodoloji

### 8 değişken detaylı tanımlar [Section "8 variables" s.10-12]

**1. Days Sales in Receivables Index (DSRI)**:
- `DSRI = (Receivables_t / Sales_t) / (Receivables_{t-1} / Sales_{t-1})`
- Yorumu: AR-Sales out-of-balance'ı yakalar; revenue inflation
  signal

**2. Gross Margin Index (GMI)**:
- `GMI = ((Sales_{t-1} - COGS_{t-1}) / Sales_{t-1}) / ((Sales_t - COGS_t) / Sales_t)`
- GMI > 1 → margin deteriorate; Lev-Thiagarajan 1993 negative
  signal about firms' prospects

**3. Asset Quality Index (AQI)**:
- `AQI = ((TA_t - CA_t - PPE_t) / TA_t) / ((TA_{t-1} - CA_{t-1} - PPE_{t-1}) / TA_{t-1})`
- Non-current ex-PPE / TA = "asset realization risk" measure;
  AQI > 1 → cost deferral artışı (Siegel 1991)

**4. Sales Growth Index (SGI)**:
- `SGI = Sales_t / Sales_{t-1}`
- Growth firms manipulate ediyor varsayımı (NCFFR 1987;
  NACFE 1993; Loebbecke 1989)

**5. Depreciation Index (DEPI)**:
- `DEPI = (Depreciation_{t-1} / (Depreciation_{t-1} + PPE_{t-1})) / (Depreciation_t / (Depreciation_t + PPE_t))`
- DEPI > 1 → depreciation rate yavaşlama; useful life uzatılmış
  veya method değişmiş olabilir

**6. SGA Index (SGAI)**:
- `SGAI = (SGA_t / Sales_t) / (SGA_{t-1} / Sales_{t-1})`
- Lev-Thiagarajan 1993; disproportionate SGA increase = negative
  signal

**7. Leverage Index (LVGI)**:
- `LVGI = ((LTD_t + CL_t) / TA_t) / ((LTD_{t-1} + CL_{t-1}) / TA_{t-1})`
- LVGI > 1 → leverage artışı; debt covenant incentives

**8. Total Accruals to Total Assets (TATA)**:
- `TATA = (ΔCA - ΔCash - ΔCL + ΔLTD - Dep) / TA`
- Beneish [s.12]: "Total accruals are calculated as the change in
  working capital accounts other than cash less depreciation."

### Estimation: WESML probit [Section "Estimation" s.7-8]

**State-based sampling bias** problemi: 74 manipulators sample
oversample edilmiş; WESML weighting function according to true
proportion in population.

**Prior probability of manipulation**: paper alternative değerler
test eder (.0059, .0069, .0079, .0089, .0099, .02844); pseudo-R²
29.81%-32.65% range; sonuçlar sensitive değil.

### Sample selection sources [Section "Sample" s.4-5]

- **SEC search**: 363 AAERs (Accounting and Auditing Enforcement
  Releases) #132-#502, 1987-1993; financials hariç + auditing
  actions hariç + 10-Q only hariç + COMPUSTAT data eksik hariç
  → 49 firms violate GAAP
- **News media search**: LEXIS/NEXIS Jan 1987 - Apr 1993; 80
  firms identified; ex post restatement requirement → 25 firms
- **Final**: 74 manipulators + 2332 controls (matched 2-digit SIC)

## Empirik Sonuçlar (sayılarla)

### Coefficient estimates [Tablo 3 Panel A]

WESML probit:
- DSRI 0.920 (t=6.02) sig 1%
- GMI 0.528 (>2σ) sig 5%
- AQI 0.404 (t=3.20) sig 1%
- SGI (>5σ) sig 1%
- TATA (sig) sig 1%
- DEPI (insig)
- SGAI (insig)
- LVGI (insig)

Pseudo-R²: WESML 30.6%, unweighted 37.1%.

### Holdout sample classification [Tablo 3 Panel B]

| Group | N | Mean prob | Median prob | %p<.01 | %p<.05 |
|---|---|---|---|---|---|
| Estimation manipulators | 50 | 0.107 / 0.237 | 0.024 / 0.099 | (lower) | 38.0% (low) |
| Estimation non-mans | 1708 | 0.006 / 0.022 | 0.003 / 0.011 | (high) | 93.4% |
| **Holdout manipulators** | **24** | (similar) | (similar) | **20.8%** | (similar) |
| **Holdout non-mans** | **624** | (similar) | (similar) | **56.1%** | (similar) |

Wilcoxon + median tests reject null (manipulators ≠ non-mans
distributions).

### Robustness [Section "Robustness" s.15-16]

1. **Drop-up-to-4-variable** test: depreciation, leverage, SGA,
   accruals one-at-a-time + combinations → similar coefficients
   for remaining variables (collinearity issue yok; max Pearson
   correlation 0.25)
2. **Alternative prior probabilities** (.0059-.0099 + .02844):
   pseudo-R² 29.81%-32.65%, coefficients similar
3. **100 random splits** (50 manipulators + 1500 controls vs 24
   manipulators + 832 controls): consistent results

### Manipulators vs controls profile [Tablo 1]

| Characteristic | Treatment median | Control median | p-value |
|---|---|---|---|
| Total assets ($M) | 43.20 | **95.84** | 0.007 |
| Sales ($M) | 53.56 | 64.59 | 0.345 |
| Market value ($M) | 74.90 | 122.54 | (sig) |
| ROA | 0.03 | 0.05 | 0.078 |
| Debt/Assets | 0.58 | 0.52 | 0.027 |
| **Sales growth** | **34.4%** | **9.4%** | 0.001 |

→ Manipulators **smaller, more levered, higher growth, less
profitable** than controls. **Manipulators sample küçük-cap-tilted**
(median $43M TA).

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Paper return prediction değil — **forensic detection paper**. M-Score binary probability (manipulator/non-manipulator), decile-spread methodology yok. Wiki için Top-N entegrasyon **filter olarak (yüksek M-Score elenir)** uygun, signal olarak değil. F-Score / G-Score / F&V/P / G&V/P combined yaklaşımına ek katman: M-Score yüksek olanlar evrenden çıkarılır, sonra winner-loser scoring. | **⚠️** dolaylı — filter |
| **Annual rebalance** | Sample 1982-1992 yıllık panel (10-K data); paper [s.18-19] "two years of data (one annual report)" gerektirir. **Annual frequency natural fit**. | **✅** |
| **Large-cap evrene transfer** | Sample COMPUSTAT 2-digit SIC matched. Manipulators **smaller** than controls [Tablo 1]: TA median manipulator $43M vs control $96M. **Manipulators sample küçük-cap-tilted**; large-cap firms'da forensic patterns farklı mı belirsiz. NDX (mega-cap) + S&P 500 (large-cap) evrene transfer için size-spesifik recalibration gerekli. **Q46 yeni**: M-Score large-cap-only kalibrasyonu. Beneish-Lee-Tarpley 2001 large-cap M-Score test eder ama **paywall, wiki'de yok**. | **⚠️** sample küçük-cap-tilted |
| **NDX intangibles / growth firms** | M-Score 8 bileşeni **traditional accounting'e dayalı** — R&D capitalization yok, intangibles-aware değil. Tech firma **false positive riski yapısal**: yüksek SGI (sales growth) tech firmlarda doğal → M-Score yüksek → "manipulator" yanlış sınıflandırma; AQI (non-current ex-PPE / TA) intangibles-yoğun firmalarda doğal yüksek → false positive. Lev-Sougiannis + Peters-Taylor + Lev-Srivastava methodology M-Score'a entegre edilmemiş. **Q47 yeni**: tech firma false positive riski. | **⚠️** intangibles-aware değil |

**Strateji tasarımına net implikasyon:**

1. **Top-N ⚠️ filter olarak entegrasyon** (4 dengeleyici kayıt):
   - Faz 3 strategy spec'inde **forensic screen** baseline: M-Score
     cutoff (paper original .025 veya conservative .01) elenir,
     sonra winner-loser scoring
   - F-Score / G-Score / F&V/P / G&V/P combined yaklaşımına ek
     katman: ilk filter M-Score elimination (manipulators evrenden
     çıkar), sonra fundamental scoring
   - Quantitative Value (Gray-Carlisle 2012) Tier 3 kitap paterni —
     concept seviyesinde bağ
   - Size-spesifik cutoff recalibration (Q46) — Faz 3 design

2. **NDX intangibles ⚠️ false positive riski** (3 ek tasarım rec):
   - Tech firma high SGI + high AQI → M-Score yapay yüksek →
     intangibles-driven (manipulators değil)
   - Faz 3 NDX strategy spec'inde M-Score **intangibles-aware
     revize**: SGI sektör-medyan-relative + AQI intangibles-adjusted
     (Lev-Sougiannis + Peters-Taylor methodology)
   - Veya M-Score NDX evren için **conservative cutoff** kullanılmalı
     (false positive minimize)

3. **Large-cap ⚠️ sample küçük-cap-tilted** (caveat):
   - Beneish sample manipulators küçük firmalar; S&P 500/NDX
     large-cap evrene transfer için kalibrasyon gerekli
   - Beneish-Lee-Tarpley 2001 (paywall) large-cap M-Score test eder,
     wiki'de yok
   - **Faz 3 caveat**: M-Score wiki amaç evrenler için **dolaylı
     uygulama** — paper sample evren ile doğrudan transferli değil

## Limitler ve Caveats

1. **Forensic detection paper, return prediction değil** — Top-N
   decile-spread methodology yok; M-Score factor portfolio kanıtı
   bu paperda yok. Beneish-Lee-Tarpley 2001 (paywall) bu boşluğu
   kapatır ama wiki'de yok.

2. **Sample selection bias** — sadece **discovered** manipulators;
   "successful, unidentified manipulators" sample dışı. Paper [s.4]
   explicit caveat: "results need to be interpreted assuming that
   sample manipulators represents a substantial portion of the
   manipulators in the population".

3. **Earnings overstatement only** — Beneish [s.18-19]: "the model
   cannot be reliably used to study firms operating in circumstances
   that are conducive to decreasing earnings" (downward earnings
   management hariç).

4. **Private firms hariç** — paper [s.18-19].

5. **Large rate of classification errors** — Type I error
   (manipulator → non-mans yanlış sınıflandırma) ve Type II error
   (non-mans → manipulator yanlış sınıflandırma) trade-off; cutoff
   probability sektör/dönem-spesifik.

6. **Distortions can have alternative origins** — paper [s.18]:
   "such distortions can have an alternative origin... a material
   acquisition during the period examined, a material shift in the
   firm's value maximizing strategy, or a significant change in the
   firm's economic environment". M-Score positive ≠ manipulation.

7. **3 bileşen insig** (DEPI, SGAI, LVGI) — paper bu bileşenleri
   model robustness için tutuyor ama statistical olarak ayrımcı
   değiller. Modern uygulamalarda 5-bileşen model kullanılabilir.

## Çelişkiler/Tartışmalar

> ⚠️ **Beneish 1999 ↔ Sloan 1996 origin attribution dual pattern
> sorgulaması**:
> - **F_ACCRUAL (F-Score) origin**: Piotroski paper-spesifik +
>   Sloan literatür hattı kökü (Cycle 9'da işaretlendi)
> - **G3 (G-Score) origin**: Mohanram paper-spesifik + Sloan
>   literatür hattı kökü (Cycle 9'da işaretlendi)
> - **TATA (M-Score) origin**: Beneish 1999 paper-spesifik + ?
>   literatür hattı kökü
>
> **Beneish reference list kontrol** (paper [s.20-21]): Sloan 1996
> **explicit listed DEĞİL**. Beneish [s.12] TATA tanımında **Healy
> 1985 + Jones 1991** explicit cite ediyor (discretionary accruals
> literature). Yani:
> - **Paper-spesifik origin**: Beneish 1999
> - **Literatür hattı kökü**: Healy 1985 + Jones 1991 (earnings
>   management research) — Sloan 1996 değil
>
> **Wiki yorumu**: TATA = Sloan total accruals **methodology paralel**
> (working capital change - depreciation; aynı yapı) AMA literatür
> hattı **farklı epistemik düzlem** — Sloan return prediction
> (cross-section anomaly), Healy/Jones earnings management research
> (manager incentives + GAAP discretion). M-Score TATA Beneish'in
> Healy-Jones hattından geldiği için **F_ACCRUAL/G3 origin paterninden
> sapma**; dual pattern korunur ama literatür hattı kökü farklı.

> 📝 **Beneish 1999 ↔ Sloan 1996 epistemik düzlem ayrımı (çelişki
> değil, complementary):**
> - **Sloan 1996**: Total accruals → cross-section returns
>   (mispricing detection; investor fixation; persistence)
> - **Beneish 1999**: 8-component model → manipulator/non-manipulator
>   binary classification (fraud detection; GAAP violation)
> İki paper aynı methodology temel (working capital change - depreciation
>  accrual proxy) AMA **iki farklı epistemik düzlem**:
> mispricing detection vs fraud detection. [[meta/contradictions]]'a
> eklenmedi (paralel methodology, complementary epistemic application).

> ⚠️ **Beneish 1999 ↔ Lev-Srivastava 2020 paralel yazar continuity
> potansiyeli (Cycle 18 keşif)**:
> Beneish 1999 reference list'inde **Lev & Thiagarajan 1993**
> "Fundamental Information Analysis" (JAR) explicit cite (8 değişken
> seçiminde GMI + SGAI motivation kaynağı). Lev (Baruch Lev) F bloğu
> origin author (Lev-Sougiannis 1996 + Lev-Srivastava 2020) — Beneish
> M-Score değişkenlerinin literatür hattı **F bloğu literature'ı ile
> dolaylı ilişkili** (Lev'in fundamental signals research'i Beneish'i
> motive ediyor). Bu çelişki değil, literature continuity notu;
> [[concepts/earnings_quality]] forensic boyut sub-section'ında
> belirtilir.

## İlgili Sayfalar

### Concepts
- [[concepts/earnings_quality]] — forensic boyut sub-section eklendi
  (Cycle 18); 3-katmanlı methodology hierarchy (Sloan persistence +
  F_ACCRUAL composite + Beneish M-Score forensic); mispricing
  detection vs fraud detection epistemik düzlem ayrımı
- [[concepts/winner_loser_identification]] — "Bu paradigmanın
  boşlukları" subsection: forensic filter eksikliği KAPANDI
- [[concepts/post_publication_decay]] — M-Score forensic filter
  caveat (decay multiplier uygulanması nüanslı)
- [[concepts/fundamental_scoring]] — composite scoring paradigm;
  M-Score satırı (epistemik düzlem ayrımı: winner-loser vs forensic)

### Papers
- [[sloan1996_accruals_anomaly]] — total accruals methodology paralel
  (working capital change - depreciation); epistemik düzlem farklı
  (mispricing detection vs fraud detection); reference list'te
  explicit listed DEĞİL
- [[piotroski2000_f_score]] — F_ACCRUAL composite element; Cycle
  5'ten beri `(sonra) [[M_Score]]` placeholder doldurulur
- [[mohanram2005_g_score]] — G3 accrual composite element;
  forensic katman ihtiyacı (tech false positive riski)
- [[famafrench1993_three_factor]] — paper [s.20-21] reference
  list'te listed DEĞİL ama Lev-Thiagarajan 1993 explicit cite
  (Lev'in fundamental signals research literature continuity)
- [[lev_srivastava_2020_value_failure]] — paralel yazar continuity
  potansiyeli (Lev fundamental signals research → Beneish motivation)

### Factors
- [[M_Score]] — yeni factor entity (Cycle 18); 8-bileşenli forensic
  composite; F-Score / G-Score paralel pattern
- [[F_Score]] — Cycle 5'ten beri açık placeholder doldurulur; F & M
  screen-and-rank yaklaşım concept seviyesinde
- [[G_Score]] — forensic katman ihtiyacı + tech false positive
  riski (Q47 yeni)
- [[Accruals]] — Sloan total accruals factor entity; M-Score TATA
  cross-link (methodology paralel)

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q9 partial cevap (Cycle 18, Beneish 1999 anchor)]** Beneish
  M-Score F-Score / G-Score ile combined performansı: paper
  combined backtest yapmıyor (forensic detection paper, factor
  combination test değil). Wiki için F-Score / G-Score / F&V/P /
  G&V/P + M-Score filter Faz 3 design adayı; tam cevap için modern
  combined empirical test eksik (Beneish-Lee-Tarpley 2001 paywall;
  Gray-Carlisle 2012 Tier 3 kitap, ingest edilmemiş). Faz 2 sentez
  aşamasında modern data ile combined backtest.

- **[Q5 partial-stronger update (Cycle 18)]** Post-publication
  decay anchor: Beneish 1999 reference list'inde Sloan 1996
  explicit listed DEĞİL — composite-score-spesifik decay aggregate
  multiplier üzerinden uygulanır (Q5 fully-answered durumu korunur).
  M-Score post-pub 25 yıl (1999-2024) sample uzatma replikasyon
  eksik (Q48 yeni paralel).

- **[Q26 partial-stronger ileri (Cycle 18)]** Tech firma R&D
  distortion: Beneish M-Score 8 bileşeni traditional accounting'e
  dayalı, intangibles-aware değil. Tech firma high SGI + high AQI
  → false positive riski. F bloğu 3 ayak methodology M-Score'a
  uygulanmamış; Faz 3 design decision (NDX evren M-Score
  intangibles-aware revize).

### Yeni Q'lar (Q46, Q47, Q48):

- **[Q46 yeni]** M-Score large-cap-only kalibrasyonu: Beneish 1999
  sample manipulators küçük (median $43M TA) vs controls ($96M);
  S&P 500 / NDX large-cap evrene transfer için size-spesifik
  recalibration gerekli mi? Beneish-Lee-Tarpley 2001 (paywall hala)
  large-cap test sağlar; modern data Chen-Zimmermann 2022 + JKP
  2023 ile kalibrasyon gerekli. Faz 3 design decision.

- **[Q47 yeni]** Tech firma M-Score false positive riski: 8
  bileşeninin SGI (sales growth) + AQI (non-current ex-PPE / TA)
  **intangibles-yoğun firmalarda yapısal yüksek** → "manipulator"
  yanlış sınıflandırma. F bloğu 3 ayak methodology (Lev-Sougiannis +
  Peters-Taylor + Lev-Srivastava) M-Score'a entegre edilmesi: SGI
  sektör-medyan-relative + AQI intangibles-adjusted. NDX strategy
  spec için ön koşul.

- **[Q48 yeni]** M-Score post-publication decay (Beneish 1999 → 25
  yıl, 1999-2024): Beneish original sample 1982-1992; paper
  post-publication 25 yıl (FAANG era + COVID + AI) M-Score
  replikasyon ve decay literatürde sistematik yok. McLean-Pontiff
  aggregate %35 decay multiplier proxy uygulanır ama **forensic
  detection paper, return prediction değil** → decay multiplier
  uygulanması nüanslı (false positive rate'i decay'e tabi mi?).
  Faz 2 sentez aşamasında değerlendirme.

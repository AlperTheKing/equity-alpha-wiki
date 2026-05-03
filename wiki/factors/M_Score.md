---
type: factor
name: M_Score
category: composite_forensic  # forensic detection (manipulator/non-manipulator binary classification)
direction: long_low  # M-Score düşük = non-manipulator likely; yüksek = manipulator likely (filter olarak elenir)
data_lag_required: "Fiscal year-end + 4 ay (10-K reporting); 2 yıl annual data (year t + year t-1)"
rebalance_frequency: annual  # M-Score "two years of data (one annual report)" — Beneish [s.18-19]
universe_tested: ["COMPUSTAT 2-digit SIC matched 1982-1992; manipulators küçük-cap-tilted (median TA $43M)"]
---

# M-Score (Beneish 8-Score Forensic Composite)

> 📝 **Cycle 18 yeni factor entity** — F-Score (Piotroski) ve G-Score
> (Mohanram) paralel pattern. Wiki'nin **en eski açık placeholder'ı**:
> [[F_Score]] sayfasında Cycle 5'ten beri `(sonra) [[M_Score]]`
> bekliyor; Cycle 18'de doldurulur. **Epistemik düzlem farklı**:
> F-Score / G-Score winner-loser identification (cross-section
> returns); M-Score forensic detection (manipulator/non-manipulator
> binary classification).

## Tanım (matematiksel)

`M-Score = β·X` probit linear combination (8 indeks):

```
M = -4.84 + 0.920 × DSRI + 0.528 × GMI + 0.404 × AQI + 0.892 × SGI +
    0.115 × DEPI - 0.172 × SGAI + 4.679 × TATA - 0.327 × LVGI
```

(WESML probit coefficients [Beneish 1999 Tablo 3 Panel A])

**Sınıflandırma**: probability cutoff (paper original .025) →
M > .025: likely manipulator (elenir filter olarak); M < .025:
likely non-manipulator (uygunluk).

**8 değişkenin tanımı**:

| Variable | Definition | Sig (Beneish 1999) |
|---|---|---|
| **DSRI** Days Sales in Receivables Index | (AR_t / Sales_t) / (AR_{t-1} / Sales_{t-1}) | ✅ t=6.02 |
| **GMI** Gross Margin Index | ((Sales_{t-1} - COGS_{t-1}) / Sales_{t-1}) / ((Sales_t - COGS_t) / Sales_t) | ✅ >2σ |
| **AQI** Asset Quality Index | ((TA_t - CA_t - PPE_t) / TA_t) / ((TA_{t-1} - CA_{t-1} - PPE_{t-1}) / TA_{t-1}) | ✅ t=3.20 |
| **SGI** Sales Growth Index | Sales_t / Sales_{t-1} | ✅ >5σ |
| **TATA** Total Accruals to Total Assets | (ΔCA - ΔCash - ΔCL + ΔLTD - Dep) / TA | ✅ sig |
| **DEPI** Depreciation Index | (Dep_{t-1}/(Dep_{t-1}+PPE_{t-1})) / (Dep_t/(Dep_t+PPE_t)) | ❌ insig |
| **SGAI** SG&A Index | (SGA_t / Sales_t) / (SGA_{t-1} / Sales_{t-1}) | ❌ insig |
| **LVGI** Leverage Index | ((LTD_t + CL_t) / TA_t) / ((LTD_{t-1} + CL_{t-1}) / TA_{t-1}) | ❌ insig |

**5 sig + 3 insig** [Beneish 1999 Tablo 3]: DSRI, GMI, AQI, SGI,
TATA statistically significant; DEPI, SGAI, LVGI not significant.

## Origin

- İlk paper (anchor): [[beneish_1999_m_score]]
- Yazar: Messod D. Beneish (Indiana University, Kelley School)
- Beneish acknowledgments [s.1] Vic Bernard, Charles Lee, Cam Harvey,
  David Hsieh; Lev-Thiagarajan 1993 (fundamental signals motivation)

### TATA bileşeninin origin attribution dual pattern (Cycle 18 ek)

Wiki Cycle 9'da F_ACCRUAL (F-Score) ve G3 (G-Score) için origin
attribution dual pattern uyguladı:
- Paper-spesifik origin (F_ACCRUAL: Piotroski; G3: Mohanram)
- Literatür hattı kökü (her ikisi: Sloan 1996)

M-Score TATA için dual pattern **farklı epistemik düzlem**:
- **Paper-spesifik origin**: Beneish 1999 [s.12]
- **Literatür hattı kökü**: **Healy 1985 + Jones 1991** (earnings
  management research) — Sloan 1996 reference list'te listed DEĞİL

**Beneish reference list kontrol** [s.20-21]: Sloan 1996 explicit
yok; Healy 1985 + Jones 1991 cite ediyor. Yani:
- Sloan'a methodology paralel (working capital change - depreciation;
  aynı yapı)
- AMA literatür hattı **farklı** — Sloan return prediction
  (cross-section anomaly), Healy/Jones earnings management research
  (manager incentives + GAAP discretion)

**Wiki yorumu**: M-Score TATA = Sloan total accruals **methodology
paralel ama literatür hattı farklı**. F_ACCRUAL/G3 origin paterninden
sapma; dual pattern korunur ama literatür hattı kökü Healy-Jones.

## Reported Performance Across Studies

| Paper | Dönem | Evren | Performans | Sample size | Notlar |
|---|---|---|---|---|---|
| [[beneish_1999_m_score]] (estimation) | 1982-1988 | COMPUSTAT 2-digit SIC matched | Pseudo-R² 30.6% (WESML) / 37.1% (unweighted); manipulators ~10x more likely | 50 manipulators + 1708 controls | [Tablo 3]; mean prob mans 0.107/0.237 vs non-mans 0.006/0.022 |
| [[beneish_1999_m_score]] (holdout) | 1989-1992 | aynı | model identifies ~50% manipulators prior to public discovery; non-mans 56.1% p<.01 vs mans 20.8% | 24 manipulators + 624 controls | [Tablo 3 Panel B]; out-of-sample robust |
| Beneish-Lee-Tarpley 2001 (paywall, eksik) | (placeholder) | (placeholder) | "Predicting Extreme Returns" — M-Score → return prediction direct evidence | — | **wiki'de yok**; data_gaps boşluğu Cycle 7-8'den beri |
| Beneish-Nichols 2009 (placeholder) | (post-publication) | (placeholder) | M-Score post-publication update | — | **wiki'de yok** |

_(Modern replication papers: Chen-Zimmermann 2022 + JKP 2023 ile Faz 2'de
post-publication 25 yıl decay test edilebilir.)_

## Faktör Ailesi İçindeki Yeri

### F-Score / G-Score paralel pattern (yapısal benzerlik)

| Boyut | F-Score (Piotroski) | G-Score (Mohanram) | M-Score (Beneish) |
|---|---|---|---|
| Bileşen sayısı | 9 | 8 | 8 |
| Tip | Binary 0/1 | Binary 0/1 industry-relative | Continuous probit (5 sig + 3 insig) |
| Evren | High-BM (BM-Q5) | Low-BM (BM-Q1) | All-COMPUSTAT 2-digit SIC matched |
| Epistemik düzlem | Winner-loser identification | Winner-loser identification | **Forensic detection** |
| Hedef | Cross-section returns | Cross-section returns | Manipulator/non-manipulator binary |
| Wiki için kullanım | Long Q5 | Long Q5 | **Filter** (yüksek M elenir) |

### M-Score'un wiki composite scoring paradigm'ındaki konumu

M-Score winner-loser identification paradigm'ında **DEĞİL** —
forensic filter olarak ek katman:

```
F-Score / G-Score / F&V/P / G&V/P (winner-loser ranking)
   │
   ├─ adım 1: M-Score filter (high M-Score → evrenden çıkar)
   │
   └─ adım 2: F/G/V/P winner-loser ranking → Q5 long
```

### Subsumed by?

- HMXZ q5 lens'inde test edilmemiş — Beneish 1999 q-factor model
  öncesi (1999); HMXZ Security Analysis paper'da explicit test
  yok (kapsam dışı). **Q-factor span tahmin edilemez** (forensic
  detection ≠ factor portfolio).
- HXZ 2020 Replicating Anomalies 447 anomaly setinde **explicit
  listed DEĞİL** (return prediction değil, classification model);
  replication framework dışı.

### Methodology paralelliği

- **TATA ↔ Sloan total accruals** (working capital change -
  depreciation): aynı yapı, farklı epistemik düzlem
- **SGI ↔ G7 (Capex / Assets)** dolaylı: G-Score growth firmalar
  evrendir, SGI yapısal yüksek; **Q47 yeni**: tech firma false
  positive riski

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

> 📝 **Wiki'de doğrudan kanıt YOK**.

- Beneish 1999 sample COMPUSTAT 2-digit SIC matched; manipulators
  **küçük-cap-tilted** (median TA $43M vs control $96M).
- Large-cap forensic patterns farklı mı belirsiz; Beneish-Lee-Tarpley
  2001 (paywall, eksik) large-cap test eder ama wiki'de yok.
- **Q46 yeni**: M-Score large-cap-only kalibrasyon Faz 3 design.
- NDX (mega-cap tech) için **false positive riski yapısal** (Q47
  yeni): tech firma high SGI + high AQI → M-Score yapay yüksek →
  yanlış manipulator sınıflandırma.

## Decay / Post-Publication Performance + Multiple Testing Status

### Forensic filter caveat

M-Score **return prediction değil, forensic detection** —
post-publication decay literature (McLean-Pontiff 2016 aggregate %35)
M-Score'a doğrudan uygulanamaz:

- MP aggregate %35 decay = factor portfolio spread'inin post-pub
  zayıflaması
- M-Score = manipulator/non-manipulator binary classification
  accuracy (Type I + Type II error rates)
- **Decay multiplier nüanslı**: false positive rate'i decay'e tabi
  mi? (manipulators arbitrage edilemez — fraud detection mekanizması
  arbitrage'tan farklı)

**Q48 yeni**: M-Score post-publication 25 yıl (1999-2024) replikasyon
literatürde sistematik yok; modern data Chen-Zimmermann 2022 + JKP
2023 ile değerlendirme.

### Multiple testing (HLZ framework)

[[harvey_liu_zhu_2016_multiple_testing]] HLZ Şekil 3 mark'inde M-Score
**explicit listed DEĞİL** (paper 316 factor census individual factors;
M-Score forensic composite kapsamı dışı). Composite score multiple-
testing aware test (Q31 paralel) wiki'de yok.

### Replication (HXZ framework)

[[hou_xue_zhang_2020_replicating_anomalies]] 447 anomaly NYSE-VW
methodology'de M-Score **explicit listed DEĞİL** (forensic detection
≠ return-predictive anomaly). Replication framework dışı.

## Implementation Notes

- **Required data**: Compustat fields:
  - AR (RECT), Sales (SALE), COGS (COGS), TA (AT), CA (ACT), PPE
    (PPENT), Dep (DP), SGA (XSGA), LTD (DLTT), CL (DLC)
  - 2 yıl annual: t + t-1 (Beneish [s.18-19] "two years of data")
- **Annual rebalance**: 4 ay reporting lag (10-K filing); Haziran-end
  rebalance natural fit (FY1Q reporting after end-of-Mart)
- **Cutoff probability**: paper original .025; conservative .01 (Type
  II error minimize); aggressive .05 (Type I error minimize)
- **Calculation note**: 8 bileşenden 3 insig (DEPI, SGAI, LVGI);
  paper bunları model robustness için tutar ama modern uygulamalarda
  **5-bileşen model** (DSRI + GMI + AQI + SGI + TATA) kullanılabilir
- **Universe**: paper sample COMPUSTAT 2-digit SIC matched; large-cap-
  only kalibrasyon Q46 (Faz 3 design)

## Bu Faktörün Yumuşak Karnı

1. **Forensic detection paper, return prediction değil**:
   - Top-N decile-spread methodology yok
   - Wiki için **filter olarak (M-Score yüksek elenir)** kullanılır,
     signal olarak değil
   - Beneish-Lee-Tarpley 2001 (paywall) M-Score → return prediction
     direct evidence sağlar; wiki'de yok

2. **Sample küçük-cap-tilted**:
   - Manipulators median TA $43M vs control $96M
   - Large-cap S&P 500 / NDX'e transfer için kalibrasyon gerekli
   - Q46 yeni Faz 3 design

3. **Intangibles-aware değil**:
   - 8 bileşen traditional accounting'e dayalı
   - Tech firma high SGI + high AQI → **false positive yapısal
     riski**
   - F bloğu 3 ayak methodology entegrasyonu eksik (Q47 yeni)

4. **Sample selection bias** (paper [s.4]):
   - Sadece **discovered** manipulators — successful unidentified
     manipulators sample dışı
   - Results "assuming sample manipulators represents substantial
     portion of the manipulators in the population"

5. **Earnings overstatement only** (paper [s.18-19]):
   - Downward earnings management hariç
   - Bilanço şişirme (asset overstatement) odaklı

6. **Large rate of classification errors** (paper [s.18]):
   - Type I + Type II error trade-off
   - Cutoff probability sektör/dönem-spesifik
   - "Distortions can have alternative origins" — material acquisitions,
     strategy shifts, economic environment changes

7. **3 bileşen insig** (DEPI, SGAI, LVGI):
   - Modern uygulamalarda 5-bileşen model alternatif
   - Beneish bunları robustness için tutuyor ama statistical
     ayrımcı değiller

## İlgili

- [[beneish_1999_m_score]] — origin paper
- [[F_Score]] — Cycle 5'ten beri açık `(sonra) [[M_Score]]`
  placeholder doldurulur (Cycle 18); F & M screen-and-rank yaklaşım
  concept seviyesinde
- [[G_Score]] — forensic katman ihtiyacı + tech false positive
  riski (Q47 yeni)
- [[Accruals]] — Sloan total accruals factor entity; M-Score TATA
  cross-link (methodology paralel, epistemik düzlem farklı)
- [[sloan1996_accruals_anomaly]] — TATA methodology paralel; Beneish
  reference list'te explicit listed DEĞİL
- [[concepts/earnings_quality]] — forensic boyut sub-section (Cycle
  18); 3-katmanlı methodology hierarchy (Sloan + F_ACCRUAL + Beneish)
- [[concepts/winner_loser_identification]] — forensic filter
  eksikliği KAPANDI (Cycle 18)
- [[concepts/post_publication_decay]] — M-Score forensic filter
  caveat (decay multiplier nüanslı)
- [[concepts/fundamental_scoring]] — composite scoring paradigm;
  M-Score satırı (epistemik düzlem ayrımı)
- [[Magic_Formula]] — composite scoring paralel ama epistemik düzlem
  farklı (winner-loser vs forensic)
- (sonra) Beneish-Lee-Tarpley 2001 — return prediction direct
  evidence (paywall, hala eksik)
- (sonra) Gray-Carlisle 2012 "Quantitative Value" — Tier 3 kitap;
  F + M combined yaklaşım pratiği (akademik değil)

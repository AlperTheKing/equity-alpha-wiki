---
type: factor
name: QMJ
category: composite_quality  # 4-dimension quality factor (Profitability + Growth + Safety + Payout)
direction: long_high  # long high quality (top 30%) / short low junk (bottom 30%)
data_lag_required: "Fiscal year-end + 4-6 ay (10-K filing); 5 yıl annual data (Growth dimension için)"
rebalance_frequency: monthly  # Asness original; annual uyarlama Faz 3 spec'i
universe_tested: ["US 1956-2012 long + 24 country broad 1986-2012; large/small ayrı (NYSE median US, 80th percentile international)"]
cycle_38_note: "QMJ Profitability dimension GPOA bileşeni Ball-GLN paralel methodology [[factors/Cop]] Cycle 38 ✓ ([[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]); Profitability zinciri 3. halka (QMJ GPOA composite 5 measure) → 4. halka (Cop standalone cash-based) methodology evrim; QMJ 4-dimension Profitability + Accruals birleşim noktası (GPOA + ACC components yan yana) Ball-GLN Cop accrual-cash flow decomposition methodology link iki paralel quality zinciri köprüsü"
---

# QMJ — Quality Minus Junk (Asness-Frazzini-Pedersen 4-Dimension Composite)

> 📝 **Cycle 19 yeni factor entity** — F-Score (Cycle 5), G-Score (Cycle
> 6), Magic Formula (Cycle 8), M-Score (Cycle 18) paralel pattern.
> MoC_factors "Quality (boş — Asness QMJ ingest edildiğinde dolacak)"
> placeholder Cycle 5'ten beri açık; Cycle 19'da doldurulu. **Q2 (large-cap
> quality vs value) fully-answered ANCHOR**.

## Tanım (matematiksel)

`QMJ Score = z(Profitability) + z(Growth) + z(Safety) + z(Payout)`

Her dimension içinde z-score normalize edilmiş measure'ların ortalaması;
4 dimension z-score'u sonra averagelendirilir → composite Quality score.

**QMJ factor inşa** [Asness Eq. 7]: Fama-French 1993 paterni paralel,
intersection of 6 size×quality portfolios:
- 2 size split: NYSE median (US) / 80th percentile (international)
- 3 quality split: top 30% / mid 40% / bottom 30%
- 6 conditional sort portföy (önce size, sonra quality)
- Value-weighted; **monthly rebalance**

```
QMJ = (½ Small Quality + ½ Big Quality) − (½ Small Junk + ½ Big Junk)
```

## 4 Quality Dimension Breakdown

> 📝 **Cycle 19 plan onayı**: 4 dimension için ayrı factor entity AÇMA;
> bu sub-section yeterli. Concept/factor proliferation kontrol disiplini
> Cycle 13/16/17/18 paterni paralel.

### 1. Profitability [Asness Eq. 2]

6 measure z-score average:

| Measure | Tanım | Wiki paralel |
|---|---|---|
| **GPOA** | Gross Profits Over Assets | **Novy-Marx 2013** explicit cite [s.7]; Faz 2 ingest aday |
| **ROE** | Return on Equity (NI / BV) | F-Score F_ROA paralel (firm-level) |
| **ROA** | Return on Assets | F-Score F_ROA paralel |
| **CFOA** | Cash Flow Over Assets | F-Score F_CFO paralel |
| **GMAR** | Gross Margin (Sales-COGS)/Sales | F-Score F_∆MARGIN paralel; Beneish GMI |
| **ACC** | Accruals (NI−CFO; düşük=quality) | **Sloan 1996 explicit cite [s.7]** — F_ACCRUAL/G3/M-Score TATA Sloan zinciri 4. halka |

**RMW alternatifi**: FF15 RMW = 1 measure (operating profitability =
(REVT−COGS−XSGA−XINT)/BV); QMJ Profitability = 6 measure → **daha
kapsamlı composite**. Wiki için: factors/RMW.md "QMJ alternatif"
sub-section (Cycle 19 update).

### 2. Growth [Asness Eq. 3]

5-year prior growth in profitability measures (her measure için
numerator change / lagged denominator).

**Mohanram 2005 explicit cite [s.7]** — G-Score growth-tarafı paralel.
G-Score G6/G7/G8 (R&D, capex, advertising intensity) **direct paralel
değil**: G-Score industry-median level; QMJ Growth firm-level 5-year
trajectory.

### 3. Safety [Asness Eq. 4]

5 measure z-score average:

| Measure | Tanım | Wiki paralel |
|---|---|---|
| **BAB** | Betting Against Beta (düşük market beta) | **Frazzini-Pedersen 2013** (yazar continuity Pedersen); Tier 3 #58 |
| **IVOL** | Idiosyncratic Volatility (düşük) | (wiki'de yok, Faz 2 aday) |
| **LEV** | Leverage (düşük; LTD/TA) | F-Score F_∆LEVER paralel (yön ters) |
| **O-Score** | Ohlson 1980 bankruptcy risk (düşük) | (wiki'de yok, distress kategori boş) |
| **Z-Score** | Altman 1968 bankruptcy risk (düşük) | (wiki'de yok, distress kategori boş) |
| **EVOL** | ROE Volatility (düşük) | F-Score F_∆ROA paralel (level vs volatility) |

### 4. Payout [Asness Eq. 5]

3 measure z-score average:

| Measure | Tanım | Wiki paralel |
|---|---|---|
| **EISS** | Equity Issuance (düşük=quality) | F-Score F_EQ_OFFER paralel |
| **DISS** | Debt Issuance (düşük=quality) | F-Score F_∆LEVER paralel |
| **NPOP** | Net Payout Over Profits (yüksek=quality) | (wiki'de yok) |

**Literatür hattı kökü**: Baker-Wurgler 2002 + Pontiff-Woodgate 2008 +
McLean-Pontiff-Watanabe 2009 explicit cite [s.7].

## Origin

- İlk paper (anchor): [[asness_frazzini_pedersen_2019_qmj]]
- Yazarlar: Cliff Asness (AQR) + Andrea Frazzini (AQR) + Lasse H.
  Pedersen (NYU + AQR + CEPR + NBER)
- Acknowledgments [s.1]: Antti Ilmanen, Ronen Israel, Johnny Kang, John
  Liew, Toby Moskowitz, Per Olsson, Scott Richardson; SIFR conference

### Origin attribution dual pattern (Cycle 19 ek)

Wiki Cycle 9 (F_ACCRUAL/G3) + Cycle 18 (M-Score TATA) origin attribution
dual pattern paterni QMJ 4 dimension için:

| Composite | Component | Paper-spesifik origin | Literatür hattı kökü |
|---|---|---|---|
| QMJ Profitability | GPOA | Asness 2019 | **Novy-Marx 2013** ✅ |
| QMJ Profitability | ACC | Asness 2019 | **Sloan 1996** ✅ (Sloan zinciri 4. halka) |
| QMJ Growth | 5-year growth | Asness 2019 | **Mohanram 2005** ✅ |
| QMJ Safety | BAB | Asness 2019 | **Frazzini-Pedersen 2013** (yazar continuity) |
| QMJ Safety | O-Score | Asness 2019 | **Ohlson 1980** |
| QMJ Safety | Z-Score | Asness 2019 | **Altman 1968** |
| QMJ Payout | EISS/DISS/NPOP | Asness 2019 | **Baker-Wurgler 2002** |

**Sloan zinciri** (4 paper, 23 yıl arayla):
1. Sloan 1996 (origin)
2. Piotroski 2000 F_ACCRUAL (Cycle 9)
3. Mohanram 2005 G3 (Cycle 9)
4. **Asness 2019 QMJ Profitability ACC** (Cycle 19; Sloan explicit cite [s.7])

**Profitability zinciri** (4 paper, 7 yıl arayla; Cycle 23 dokümante):
1. **Novy-Marx 2013 GP/A** (origin; QMJ paper [s.7] explicit cite)
2. FF15 RMW Ope (FF15 paper [s.4] Novy-Marx 2013 explicit cite)
3. **Asness 2019 QMJ Profitability GPOA** (6 measure'dan biri)
4. HXZ 2020 Cop (HMXZ Tablo 5; Ball-GLN 2016 origin; cash-aware evrim)

**İki paralel quality zinciri QMJ 4-dimension'da birleşiyor**: QMJ
Profitability dimension 6 measure içinde GPOA (Profitability zinciri)
+ ACC (Sloan zinciri) yan yana — wiki için literature continuity
yapısal kazanım. QMJ Profitability composite'i **iki bağımsız mekanizmanın
sentezi**: productive efficiency signal (Novy-Marx) + earnings management
detection (Sloan).

> 📝 **Cycle 26 ek (FGX 2020 ingest) — QMJ DS-sig**:
> [[papers/feng_giglio_xiu_2020_factor_zoo]] [Tablo 1, since-2012
> factors]: QMJ Quality-Minus-Junk **DS LASSO 150-factor library
> lens'inde sig SDF loading**. HMXZ q5 captures (Cycle 8 — q-factor
> model lens'inde alpha 0.06% t=0.42 GRS p=0.12) + FGX DS-sig (Cycle
> 26 — DS LASSO model selection bias-corrected lens'inde sig)
> **paralel methodology lens; iki kullanım modu** option (q-factor
> exposure proxy + DS-sig standalone signal).
>
> Q49 (4 dimension hangisi en güçlü) Cycle 23 partial-stronger
> Novy-Marx Profitability dimension origin direct kanıt + Cycle 26
> FGX QMJ composite DS-sig **dimension-spesifik decompose paperde
> yok** (Asness orijinal Tablo VI Panel A); Q49 partial-stronger
> hala (composite sig + dimension hierarchy eksik).

## Reported Performance Across Studies

| Paper | Sample | Spec | Alpha (bps/ay) | t-stat |
|---|---|---|---|---|
| [[asness_frazzini_pedersen_2019_qmj]] | US 1956-2012 | 1-factor (CAPM) alpha | **55** | 7.27 |
| [[asness_frazzini_pedersen_2019_qmj]] | US 1956-2012 | 3-factor (FF3) alpha | **68** | 11.10 |
| [[asness_frazzini_pedersen_2019_qmj]] | US 1956-2012 | **4-factor (Carhart) alpha** | **66** | **11.20** |
| [[asness_frazzini_pedersen_2019_qmj]] | Global broad 1986-2012 | 1-factor alpha | 52 | sig |
| [[asness_frazzini_pedersen_2019_qmj]] | Global broad 1986-2012 | 3-factor alpha | 61 | sig |
| [[asness_frazzini_pedersen_2019_qmj]] | Global broad 1986-2012 | 4-factor alpha | ~60 | sig |
| [[asness_frazzini_pedersen_2019_qmj]] | 24 country | Pozitif alpha | 23/24 country | — |
| [[asness_frazzini_pedersen_2019_qmj]] | 24 country | 4-factor alpha sig | 17/24 country | — |
| [[asness_frazzini_pedersen_2019_qmj]] | US decile high-low | Excess return | 47-68 bps/ay | 2.80-3.22 |
| [[hou_mo_xue_zhang_2020_security_analysis]] (Tablo 4) | (paperdan teyit) | **q-factor REJECT** GRS p=0.00; **q5 CAPTURES** alpha 0.06% (t=0.42) GRS p=0.12 | composite QMJ test; 4 dimension breakdown bu paperde yok | — |

## Faktör Ailesi İçindeki Yeri

### Composite Score Karşılaştırma (Cycle 5-19 evolution)

| Boyut | F-Score | G-Score | Magic Formula | M-Score | **QMJ** |
|---|---|---|---|---|---|
| Bileşen sayısı | 9 binary | 8 binary industry-median | 2 (EBIT/EV + ROC) | 8 (5 sig + 3 insig) probit | **22 measure → 4 dimension z-score** |
| Tip | Binary 0/1 | Binary 0/1 industry-relative | Continuous rank | Continuous probit | **Continuous z-score composite** |
| Evren | High-BM | Low-BM | All-cap | All-cap | All-cap (large/small ayrı) |
| Epistemik düzlem | Winner-loser | Winner-loser | Winner-loser | **Forensic** (filter) | **Winner-loser** (signal) |
| Hedef | Cross-section returns | Cross-section returns | Cross-section returns | Manipulator binary | **Cross-section returns** |
| Wiki kullanım | Long Q5 | Long Q5 | Long top 30 | **Filter** (yüksek M elenir) | **Long Top 30 quality (signal)** |
| Origin paper | Piotroski 2000 | Mohanram 2005 | Greenblatt 2005 | Beneish 1999 | **Asness-Frazzini-Pedersen 2019** |

### RMW alternatifi (Cycle 19 anchor karşılaştırma)

| Boyut | RMW (FF15) | QMJ Profitability dimension |
|---|---|---|
| Measure sayısı | 1 (operating profitability) | 6 (GPOA + ROE + ROA + CFOA + GMAR + ACC) |
| Formül | (REVT − COGS − XSGA − XINT) / BV | Average of 6 z-scores |
| Sample | NYSE/AMEX/NASDAQ ex-fin 1963-2013 | US 1956-2012 + 24 country |
| Methodology | 2x3 size×OP sort, value-weighted | Same Fama-French 1993 paterni; conditional size×quality |
| Headline alpha | 0.25%/ay (t=2.92) 2x3; 2x2x2x2 t=4.09 | 4-factor alpha 66 bps/ay (t=11.20) (composite QMJ) |
| HLZ MT-corrected | BHY borderline / Bonferroni insig (2x3) | (paperde explicit MT yok; 4-factor alpha ~9 sigma) |
| HMXZ q5 lens | (paperde direct test yok) | **q5 captures** (alpha 0.06%, GRS p=0.12) |
| Wiki konum | FF5 origin paper'ın bileşeni | Yeni composite (Cycle 19); RMW'nin **kapsamlı alternative**'i |

### QARP — Quality at a Reasonable Price [Asness Section 7]

QMJ + HML kombinasyonu: `signal = quality × n − P/B`
- n yakın 1: highest alpha (US + global)
- Graham-Dodd 1934 paralel ("investment must consider price as well as quality")
- Frankel-Lee 1998 + Piotroski 2000 explicit cite (combined approach
  literatür hattı)
- **Wiki paralel**: Li-Mohanram 2019 F&V/P + G&V/P combined paradigm
  (Cycle 7); aynı paradigma Asness operationalization

Faz 3 strategy spec için QARP framework anchor; concept seviyesinde
[[concepts/value_premium]] 4. yorum boyutu sub-section (Cycle 19 update).

### Subsumed by?

- **HMXZ Tablo 4 q5 CAPTURES**: alpha 0.06% (t=0.42) GRS p=0.12 →
  q-factor model + expected growth (q5) QMJ'yi span ediyor. Risk
  premium yorumu (Cochrane 2011 mathematical equivalence ile aynı
  bulgu mispricing yorumuna eşdeğer).
- **q-factor (HXZ4) REJECT**: GRS p=0.00 → q5'in expected growth
  bileşeni QMJ açıklayıcı gücü için kritik
- **FF5 vs QMJ horse race**: paperde yok (4-factor Carhart baseline);
  Faz 2 aday (Q14 + Q15 paralel)

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

### Q2 fully-answered ANCHOR (Cycle 19)

> 📝 **Wiki priori soru**: S&P 500 evreninde quality faktörü (Asness QMJ,
> Novy-Marx GP/A) value'dan daha güçlü kanıt sunuyor mu? Hangi alt-bileşeni
> en kuvvetli?

**QMJ paper anchor cevap** (Tablo A4 + Figure A1 + Tablo VI Panel C):
- 23/24 country pozitif alpha (large-cap + small-cap ayrı)
- 17/24 country 4-factor alpha sig
- US long sample 4-factor alpha 66 bps/ay (t=11.20)
- 4 dimension breakdown: her dimension ayrı 4-factor alpha sig (US +
  global)
- Composite QMJ "the strongest of the four"

### NDX (glamour-heavy tech) için QMJ direct fit

[[lev_srivastava_2020_value_failure]] [Figure 9]: Glamour firms
2007-2018 highest profitability since 1970.

QMJ Profitability dimension (GPOA + ROE + ROA + CFOA + GMAR + ACC):
tech firmlarda yüksek değerler (FAANG profitability dominantı).

QMJ "negative HML loading" (Section "Risk Exposure"): high-quality
stocks have high prices → QMJ-HML negative correlation. NDX glamour-
heavy evren yapısal olarak QMJ "long" tarafına denk geliyor.

**⚠️ CAVEAT**: QMJ paper 4 dimension intangibles-aware **DEĞİL** —
F bloğu 3 ayak methodology (Lev-Sougiannis + Peters-Taylor + Lev-
Srivastava) QMJ'a entegre edilmemiş. Q47 + **Q49 yeni**: NDX evren
QMJ intangibles-aware revize Faz 3 design ön koşul.

## Decay / Post-Publication Performance + Multiple Testing Status

### Post-publication decay

QMJ paper sample sonu Dec 2012; **Q51 yeni**: post-2012 modern
replikasyon (FAANG era + COVID + AI 2013-2024 out-of-sample).
McLean-Pontiff aggregate %35 decay multiplier proxy uygulanır →
post-pub decay düzeyi belirsiz.

### Multiple testing (HLZ framework)

[[harvey_liu_zhu_2016_multiple_testing]] HLZ Şekil 3 mark'inde QMJ
**explicit listed DEĞİL** (paper 316 factor census 2014 sonu;
QMJ original SSRN 2013 ama RAS 2019 yayını ediyor). Ancak QMJ
4-factor alpha t=11.20 → **HLZ recommended cutoffs** (Bonferroni 3.78,
BHY 3.39 BHY-FDR-1%) **çok rahat geçer** (~9 sigma).

### Replication (HXZ framework)

[[hou_xue_zhang_2020_replicating_anomalies]] 447 anomaly NYSE-VW
methodology — QMJ explicit listed kontrol edilmedi (paper kapsamı
2017'ye kadar).

### Dört darbe çerçevesi

[[concepts/post_publication_decay]] dört darbe sentez tablosu:
1. **In-sample**: ✅ 4-factor alpha 66 bps/ay (t=11.20) US long sample
2. **Post-pub decay**: aggregate %35 multiplier proxy; modern data eksik
3. **Multiple-testing**: ✅ HLZ recommended cutoffs çok rahat geçer
4. **q-factor lens (replication)**: **q5 CAPTURES** (HMXZ Tablo 4) →
   span = risk premium proxy

**Sentez**: 3-4/4 (q-factor span = risk premium proxy; klasik 4-factor
sig çok güçlü) — F-Score (3/4 BM-Q5) + G-Score (2-3/4) + Sloan
operating accruals (4/4) ile karşılaştırılabilir.

## Implementation Notes

- **Required data** (22 measure): Compustat fields:
  - Profitability: REVT, COGS, NI, BV, AT, OANCF
  - Growth: 5-year prior values
  - Safety: market beta, IVOL (1-year daily returns), LTD/TA, O-Score
    (multi-input), Z-Score (multi-input), ROE volatility
  - Payout: STKCO (stock issuance), DLTIS (debt issuance), DV (dividends)
- **Annual rebalance** (Faz 3 wiki amacı): orijinal paper monthly
  rebalance; annual uyarlama primum sensitivity test gerekir
- **z-score normalization**: cross-sectional rank → standardize per
  measure → average within dimension → average across dimensions
- **Universe**: large/small ayrı sort; NYSE median (US) breakpoint
- **Annual data**: 5-year growth measure için 5+ yıl annual data
  gerekli

## Bu Faktörün Yumuşak Karnı

1. **Monthly rebalance orijinal — annual primum sensitivity test
   eksik**: Asness QMJ alpha aylık rebalance üzerinden raporlanmış;
   Faz 3 spec'inde annual uyarlama Q35 (Bailey-LdP DSR) ile birlikte
   değerlendirilir; primum kaybı muhtemel.

2. **Sample sonu 2012**: Modern dönem (2013-2024 FAANG/AI) out-of-
   sample. Q51 yeni Faz 2 modern data replikasyon.

3. **4 dimension intangibles-aware DEĞİL**: F bloğu 3 ayak methodology
   QMJ'a entegre edilmemiş. NDX FAANG/tech-heavy evrene transfer
   için intangibles-aware revize gerekli (Q49 yeni).

4. **HMXZ q5 CAPTURES (Tablo 4)**: q-factor + expected growth model
   QMJ'yi span ediyor → "saf alpha kaynağı" yorumu sınırlı; risk
   premium yorumuna eğilimli (Cochrane mathematical equivalence ile
   complementary mispricing yorumu).

5. **22 measure complexity**: Implementation 22 measure z-score +
   normalization gerektirir; Compustat field availability 5-year
   growth için kritik (Growth dimension survival bias riski).

6. **HLZ MT-corrected status explicit yok**: 316 factor census kapsamı
   dışı (paper 2013 SSRN, 2019 RAS); 4-factor alpha t=11.20 ham
   olarak HLZ recommended cutoffs geçer ama paper kendi MT testi
   yapmıyor. Q31 (composite scores MT-aware) paralel.

7. **24 country broad sample, US large-cap-only kalibrasyon eksik**:
   Tablo A4 large/small cap separately raporluyor ama "S&P 500-only"
   universe-spesifik test paperde yok. AQR data setleri (Tier 3 #55)
   paywall, eksik.

## İlgili

- [[asness_frazzini_pedersen_2019_qmj]] — origin paper
- [[RMW]] — QMJ Profitability boyutu wiki RMW factor'un alternatifi;
  factors/RMW.md sayfasında "QMJ alternatif" sub-section (Cycle 19
  update); 1 measure vs 6 measure
- [[F_Score]] — winner-loser paradigm paralel (high-BM evren); 9 binary
  composite vs QMJ 4-dimension continuous
- [[G_Score]] — winner-loser paradigm paralel (low-BM evren); QMJ
  Growth dimension Mohanram 2005 literatür hattı kökü
- [[Magic_Formula]] — composite scoring paralel (q5 ile tam span)
- [[M_Score]] — Cycle 18; epistemik düzlem farklı (forensic filter ≠
  QMJ winner identification signal)
- [[Accruals]] — QMJ Profitability ACC component cross-link; Sloan
  zinciri 4. halka
- [[SMB]] — Section 8 resurrection finding; Q11 alternative
  perspective
- [[HML]] — QMJ-HML negative correlation; QARP framework HML + QMJ
  kombinasyonu
- [[CMA]] — investment factor; QMJ Growth dimension dolaylı paralel
- [[concepts/winner_loser_identification]] — QMJ "quality minus junk"
  paradigm winner-loser identification quality boyutu
- [[concepts/value_premium]] — QARP framework 4. yorum boyutu (Cycle
  19 update)
- [[concepts/fundamental_scoring]] — composite scoring paradigm
  tablosu QMJ + QARP satırları
- [[concepts/post_publication_decay]] — dört darbe sentez tablosu QMJ
  satırı
- [[concepts/multiple_testing]] — HLZ aggregate sig durumu QMJ satırı
- [[hou_mo_xue_zhang_2020_security_analysis]] — Tablo 4 q5 captures
  QMJ; 4 dimension breakdown bu paperde yok
- [[famafrench2015_five_factor]] — RMW vs QMJ Profitability paralel
- [[li_mohanram2019_quality_value]] — F&V/P + G&V/P combined paradigm
  Asness QARP paralel
- [[lev_srivastava_2020_value_failure]] — glamour firms 2007-2018
  highest profitability uyumlu kanıt
- [[sloan1996_accruals_anomaly]] — QMJ Profitability ACC component
  literatür hattı kökü; Sloan zinciri 4. halka
- [[mohanram2005_g_score]] — QMJ Growth dimension literatür hattı
  kökü
- (sonra) Novy-Marx 2013 — QMJ Profitability GPOA literatür hattı
  kökü; Faz 2 ingest aday
- (sonra) Frazzini-Pedersen 2013 BAB — QMJ Safety dimension; Tier 3 #58
- (sonra) Frazzini-Israel-Moskowitz 2018 trading costs — annual
  rebalance cost analysis (paywall, Tier 3 #52)
- (sonra) AQR data setleri — large-cap-only kalibrasyon (Tier 3 #55)

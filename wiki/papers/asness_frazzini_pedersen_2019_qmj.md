---
type: paper
authors: [Asness, Clifford S., Frazzini, Andrea, Pedersen, Lasse H.]
year: 2019
title: "Quality Minus Junk"
venue: "Review of Accounting Studies 24(1): 34-112 (March 2019; SSRN draft Oct 2013, multiple revisions)"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2312432
local_path: raw/papers/asness_frazzini_pedersen_2019_qmj.pdf
ingested: 2026-05-01
tags: [quality, QMJ, large_cap, profitability, growth, safety, payout, QARP, Tier_1_6, Q2_anchor, NDX_kritik, Faz_1]
status: ingested
cycle_38_note: "QMJ Profitability dimension GPOA bileşeni Ball-GLN paralel methodology [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓; Profitability zinciri 3. halka (QMJ GPOA composite 5 measure) → 4. halka (Cop standalone) methodology evrim; **iki paralel quality zinciri QMJ 4-dimension Profitability + Accruals birleşim noktası** GPOA + ACC components yan yana QMJ; Ball-GLN Cop accrual-cash flow decomposition Sloan + Profitability zinciri köprüsü methodology link"
---

# Asness, Frazzini & Pedersen (2019) — Quality Minus Junk (QMJ)

> 📝 **Atıf konvansiyonu:** Tablolar Roman numerals (Table I-IX + Table A1-A6
> appendix); `[s.X]` SSRN working paper PDF sayfa numarası (Oct 2013 draft,
> 50+ sayfa). RAS 2019 yayın versiyon sayfa numaraları farklı olabilir.

> 📝 **Cycle 19 ingest** — Senaryo (A) onayı; Q2 (large-cap quality vs
> value) **fully-answered ANCHOR**. Cycle 5'ten beri MoC_factors "Quality
> (boş)" placeholder doldurulu. Faz 1 son ingest paperı; Cycle 20 = Faz 1
> sertifikası + §11.5 ZORUNLU 4-cycle consolidation.

## TL;DR

Asness-Frazzini-Pedersen 2019, **quality** kavramını 4 dimension üzerinden
operationalize eder ve **QMJ (Quality Minus Junk) factor**'unu tanımlar:
high-quality stocks long / junk stocks short. **Tek cümle finding**:
QMJ US 1956-2012 + 24 country 1986-2012 sample'larda significant 1/3/4-
factor alpha + 23/24 country pozitif return + flight-to-quality crisis
context'inde robust + SMB resurrection controlling for QMJ.

**4 quality dimension** [Section 1, Eq. 2-6]:
1. **Profitability** (6 measure): GPOA + ROE + ROA + CFOA + GMAR +
   ACC (low accruals = high quality)
2. **Growth** (5-year): five-year growth in profitability measures
3. **Safety** (5 measure): BAB + IVOL + LEV + bankruptcy risk
   (O-Score + Z-Score) + EVOL (ROE volatility)
4. **Payout** (3 measure): EISS + DISS + NPOP

Composite Quality = average(z-score Profitability, Growth, Safety, Payout).

**Sample**: 39,308 stocks; US long 1956-06/2012-12 + 24 country broad
1986-2012; CRSP + XpressFeed Global merged; **monthly rebalance**.

**Headline performance** [Table VI]:
- **US long sample QMJ**: 1/3/4-factor alpha **55, 68, 66 bps/ay**
  (t=7.27, 11.10, 11.20) sig 1%
- **Global broad sample QMJ**: alpha 52, 61, ~60 bps/ay sig 1%
- **23/24 countries** pozitif alpha; **17/24 sig 4-factor alpha**
- Decile high-low return difference 47-68 bps/ay (t=2.80-3.22)

**Sürpriz bulgular**:
1. **Quality price puzzle** [Section 3-4]: Quality prices are positive
   but limited explanatory power; cross-sectional R² 12% (US long) /
   6% (global) — yüksek-quality stocks have only modestly higher prices
2. **No tail risk compensation** [Section 5, Table VII]: QMJ recession/
   bear markets'da pozitif alpha; **flight-to-quality** crisis
   context'inde
3. **SMB resurrection** [Section 8]: vanilla SMB controlling for QMJ
   insig α=13bps → **sig α=64bps (t=6.39)**
4. **Time-varying price of quality predicts QMJ returns** [Section 6,
   Table VIII]: low price of quality → high future QMJ return

## Tek Cümle Tezi

Quality stocks (profitable, growing, safe, well-managed) **systematic
ve robust ekstra return** üretiyor — US'da 1956-2012 ve 24 country'de
1986-2012; QMJ factor 1/3/4-factor alpha large-cap-only ve global olarak
sig; **SMB controlling for QMJ ile resurrected** (size effect quality
control altında ortaya çıkıyor); QARP framework quality + value combined
optimal.

## Ortaya Konan Sinyal/Faktör

**Yeni factor entity AÇILDI** (Cycle 19 plan onayı; MoC_factors "Quality
(boş)" placeholder Cycle 5'ten beri açık):

- [[QMJ]] — Composite Quality score (4 dimension z-score average); QMJ
  factor inşa Fama-French 1993 paterni (intersection of 6 size×quality
  portfolios); monthly rebalance

> 📝 **4 quality dimension için ayrı entity AÇILMADI** (Cycle 19 plan
> onayı): concept/factor proliferation kontrol disiplini (Cycle 13/16/
> 17/18 paterni) sertçe uygulandı. 4 dimension QMJ paperin **kendi
> composite yapısının sub-component'leri**, ayrı factor portfolio kanıtı
> her biri için yok. factors/QMJ.md sayfasında **`## 4 Quality Dimension
> Breakdown` sub-section** + RMW/F-Score/G-Score/M-Score paralelleri
> belirtilir.

> 📝 **QARP concept ayrı sayfa AÇILMADI**: [[concepts/value_premium]]
> genişletmesi + factors/QMJ.md QARP sub-section yeterli; Cycle 7'de
> combined_quality_value açılmama paterni paralel.

## Metodoloji

### Sample [Section 1]

- **US long sample**: June 1956 - Dec 2012; CRSP common stocks (SHRCD
  10/11); 5-year growth measures için 1956 başlangıç (1951 firm-level
  data + 5 yıl)
- **Global broad sample**: Jan 1986 - Dec 2012; 24 developed countries
  (MSCI World Developed Index üyeleri); CRSP + XpressFeed Global
  merged; **39,308 stocks total**
- All returns USD excess over US Treasury bill rate
- Delisting returns CRSP (US); -30% performance-related delisting
  proxy (Shumway 1997)

### 4 Quality Dimension Detaylı [Section 1]

**Profitability (Eq. 2)** — 6 measure:
- GPOA (Gross Profits Over Assets) — Novy-Marx 2013 paralel
- ROE (Return on Equity)
- ROA (Return on Assets)
- CFOA (Cash Flow Over Assets)
- GMAR (Gross Margin)
- ACC (Accruals — düşük = yüksek quality) — **Sloan 1996 explicit cite [s.7]**

**Growth (Eq. 3)** — 5 measure:
- Profitability measure'ların **5-year prior growth** (her measure için
  numerator change / lagged denominator)
- Mohanram 2005 explicit cite [s.7]

**Safety (Eq. 4)** — 5 measure:
- BAB (Betting Against Beta — düşük beta) — Frazzini-Pedersen 2013 explicit
- IVOL (Idiosyncratic Volatility)
- LEV (Leverage — düşük)
- Bankruptcy risk: O-Score (Ohlson 1980) + Z-Score (Altman 1968)
- EVOL (ROE Volatility — düşük)

**Payout (Eq. 5)** — 3 measure:
- EISS (Equity Issuance — düşük = yüksek quality)
- DISS (Debt Issuance — düşük)
- NPOP (Net Payout Over Profits — yüksek)
- Baker-Wurgler 2002 + Pontiff-Woodgate 2008 + McLean-Pontiff-Watanabe
  2009 explicit cite [s.7]

**Composite Quality (Eq. 6)** — z-score normalize her measure içinde,
average within dimension, average across 4 dimension.

### QMJ Factor İnşa [Eq. 7]

Fama-French 1993 + Asness-Frazzini 2013 paterni:
- 2 size split: NYSE median (US); 80th percentile (international)
- 3 quality split: top 30% / mid 40% / bottom 30%
- 6 size×quality portföyü; **conditional sort** (önce size, sonra quality)
- QMJ = (½ Small Quality + ½ Big Quality) − (½ Small Junk + ½ Big Junk)
- Value-weighted; **monthly rebalance**

### Risk-factor model

**4-factor (Carhart) baseline**: MKT + SMB + HML + UMD; QMJ alpha bu
modele göre raporlanır.

> 📝 Wiki için: QMJ paper FF5 (RMW + CMA) baseline kullanmıyor — 4-factor
> Carhart paradigm; Q15 (q5 vs FF5) ile bağlantılı; FF5 vs QMJ horse
> race wiki'de yok (Faz 2 aday).

## Empirik Sonuçlar (sayılarla)

### Decile high-low [Table IV]

10 quality-sorted portfolios value-weighted; high-low difference:
- **47-68 bps/ay** (sample'a göre); t=2.80-3.22 sig 1%
- 4-factor alpha decile farkından daha büyük (because high-quality stocks
  have lower market/size/value/momentum exposures)

### QMJ Factor Performance [Table VI]

**Panel A — US long sample (1956-2012)**:
| Spec | Alpha (bps/ay) | t-stat |
|---|---|---|
| Excess return | (sig pozitif) | sig |
| 1-factor (CAPM) alpha | **55** | **7.27** |
| 3-factor (FF3) alpha | **68** | **11.10** |
| 4-factor (Carhart) alpha | **66** | **11.20** |

**Panel B — Global broad sample (1986-2012)**:
| Spec | Alpha (bps/ay) | t-stat |
|---|---|---|
| 1-factor alpha | 52 | sig |
| 3-factor alpha | 61 | sig |
| 4-factor alpha | ~60 | sig |

**Panel C — 24 country breakdown**:
- 23/24 countries pozitif return + alpha (yalnız New Zealand küçük
  negatif — smallest country)
- **17/24 country 4-factor alpha sig**
- Striking consistency

### 4 Dimension Ayrı Performance [Table VI]

Her dimension ayrı QMJ-style factor olarak inşa edilmiş (Profitability/
Growth/Safety/Payout her biri Long Top30%-Short Bottom30%):
- **Her dimension US sample sig 1/3/4-factor alpha**
- Global sample 4-factor alpha sig her dimension için
- Composite QMJ "the strongest of the four"

### Risk Exposure [Table VI]

QMJ 4-factor loadings:
- **Negatif market beta** (long low-beta + large; short high-beta +
  small)
- **Negatif size exposure** (long large + short small) — SMB resurrection
  finding'in temeli
- **Negatif HML exposure** (US sample): "high-quality stocks have high
  prices" → QMJ-HML negative correlation
- Safety factor en güçlü negatif market beta
- Payout factor pozitif HML loading (genelde)

### Pairwise Correlations [Table V]

4 dimension components arası ortalama pairwise correlation:
- **0.40 US sample** (excess returns)
- **0.45 global** (excess returns)
- **0.38** abnormal returns (4-factor alpha residuals)
- Negatif: Growth ↔ Payout (yüksek payout = düşük growth)

### No Tail Risk [Table VII]

QMJ performance:
- Recession + bear markets: **pozitif alpha** (flight-to-quality)
- High volatility + volatility increase: pozitif alpha
- Mild positive convexity (Figure 4): extreme down markets'da bile
  pozitif performans
- Risk-based explanation challenge: bad-state returns pozitif

### Time-Varying Price of Quality [Table VIII]

Cross-sectional regression P/B on Quality coefficient → time series price
of quality:
- Lowest: **Feb 2000** (internet bubble)
- Highs: late 1990 (Gulf War), late 2002 (Enron/WorldCom), early 2009
  (banking crisis)
- **Low price of quality → high future QMJ return** (negatif sig
  coefficient predictability up to 5 years)

### SMB Resurrection [Section 8]

Vanilla SMB:
- Controlling MKT + HML + UMD: **α=13 bps insig**
- **Controlling MKT + HML + UMD + QMJ**: **α=64 bps (t=6.39) sig**
- "Quality controls altında size effect resurrected"
- Wiki implication: Q11 (SMB never sig under MT) **structural
  alternative perspective** — quality-controlled SMB sig

### QARP (Quality at a Reasonable Price) [Section 7]

Combined long-short portfolio:
- Signal: `quality × n − P/B score`
- **n yakın 1**: highest alpha (US + global)
- QARP = QMJ + HML kombinasyonu; max-Sharpe quality:value ratio
- Graham-Dodd 1934 "Investment must always consider the price as well
  as the quality" referansı
- Frankel-Lee 1998 + Piotroski 2000 explicit cite (combined approach
  literatür hattı)

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Paper **decile-spread methodology kullanıyor** [Section 1, Table IV]: ten quality-sorted portfolios value-weighted; QMJ factor long top 30% / short bottom 30%. **Top-N selection için DOĞRUDAN UYUMLU**. Wiki için: QMJ score → Top-N quality-ranked portföy. F-Score / G-Score winner-loser paradigmasına paralel. | **✅** doğrudan |
| **Annual rebalance** | Paper **monthly rebalance** [Section 1]: "rebalanced every calendar month to maintain value weights". Wiki amacı yıllık. **Caveat**: Asness QMJ alpha aylık rebalance + sample 1956-2012 üzerinden raporlanmış; annual'a uyarlanırsa primum kaybı muhtemel ama 4-factor alpha düzeyinde robust beklenir. AQR Frazzini-Israel-Moskowitz 2018 trading costs perspectif'inden (paywall, eksik) annual + value-weighted natural fit. Faz 3 spec'inde DSR-aware annual uyarlama Q35 ile. | **⚠️** monthly orijinal; annual uyarlama Q35 ile |
| **Large-cap evrene transfer** | ⭐ **KRİTİK** — **Tablo A4 + Figure A1 large-cap-only ayrı raporlama**; "QMJ factor (as well as its large-cap only and small-cap only components) delivers positive returns in 23 out of 24 countries" [s.5]; size breakpoint NYSE median (US) + 80th percentile (international); 1956-2012 long sample + 24 country broad sample; **17/24 country 4-factor alpha sig** [Table VI Panel C]. **Q2 fully-answered ANCHOR**. 4 dimension breakdown + global consistency + crisis context robust + flight-to-quality. | **✅** ⭐ Q2 fully-answered |
| **NDX intangibles / growth firms** | ✅ — Glamour firms 2007-2018 highest profitability ([[lev_srivastava_2020_value_failure]] Figure 9) + QMJ "quality stocks low value exposure" (Section 8: QMJ-HML negative correlation); QMJ Profitability boyutu (GPOA + ROE + ROA + CFOA + GMAR + ACC) tech firmlarda yüksek değerler (FAANG profitability dominantı). NDX glamour-heavy evrene direct fit. **⚠️ caveat**: QMJ paper 4 dimension intangibles-aware **DEĞİL** — F bloğu 3 ayak methodology entegrasyonu eksik (Q47 paralel + Q49 yeni). Lev-Sougiannis + Peters-Taylor + Lev-Srivastava methodology QMJ Profitability/Safety/Growth dimension'larına uygulanmamış. | **✅** NDX direct fit; intangibles-aware caveat |

**Strateji tasarımına net implikasyon:**

1. **Top-N ✅ doğrudan + 4 dengeleyici kayıt:**
   - QMJ score → Top-N quality-ranked portföy doğal Faz 3 strategy spec
     implementation
   - 4 dimension breakdown sub-component scoring (sektör nötralizasyon ile)
   - QARP framework Li-Mohanram F&V/P + G&V/P paterninin Asness paralel'i
     — Faz 3 anchor
   - F-Score + QMJ kombine yaklaşım Faz 3 design adayı; F-Score (binary
     9-component) + QMJ (continuous 4-dimension) **complementary**

2. **Annual ⚠️ caveat** (3 dengeleyici kayıt):
   - Faz 3 spec'inde annual rebalance + value-weighted uyarlama; primum
     kaybı sensitivity test
   - DSR (Bailey-LdP) Sharpe scaling annual reporting frequency için ek
     düzeltme
   - Frazzini-Israel-Moskowitz 2018 trading costs (paywall, eksik) — Faz
     2'de annual reporting cost-aware analysis

3. **Large-cap ✅ ⭐ Q2 fully-answered**: 13 cycle partial sonrası
   fully-answered; wiki için sembolik kazanım. Faz 3 strategy spec için
   **quality factor anchor** S&P 500 + NDX large-cap evrenler için.

4. **NDX intangibles ✅ + caveat**: QMJ NDX glamour-heavy evrene direct
   fit (Lev-Srivastava paralel kanıt); ama F bloğu 4 ayak methodology
   entegrasyonu eksik — Q47 + Q49 yeni Faz 3 design.

## Limitler ve Caveats

1. **Monthly rebalance orijinal — annual uyarlama primum sensitivity
   test gerekir** (Section 1; wiki amacı yıllık).

2. **Sample sonu 2012** — Modern dönem (2013-2024 FAANG era + COVID +
   AI) QMJ replikasyonu paperde yok. **Q51 yeni**: post-2012 modern
   replikasyon.

3. **4 dimension intangibles-aware DEĞİL** — Profitability + Growth +
   Safety + Payout traditional accounting'e dayalı; F bloğu 4 ayak
   methodology (Lev-Sougiannis Knowledge + Eisfeldt-Papanikolaou
   Organization + Peters-Taylor Total + Lev-Srivastava Application)
   QMJ'a entegre edilmemiş. NDX FAANG/tech-heavy evrene transfer için
   intangibles-aware revize gerekli (Q49 yeni).

4. **Risk-based explanation challenge open**: Paper [Section 5]
   "alternative risk-based explanations are always possible". Mispricing
   vs risk premium yorumu mathematical equivalence (Cochrane 2011) —
   wiki taraf tutmaz.

5. **HMXZ q5 captures QMJ** ([[hou_mo_xue_zhang_2020_security_analysis]]
   Tablo 4): q5 alpha 0.06% (t=0.42) GRS p=0.12 — q5 model QMJ'yi span
   ediyor. Q15 ile paralel: factor exposure yorumu **risk premium**
   tarafına eğilimli; QMJ paper'ın "behavioral mispricing" tonu HMXZ
   ile complementary epistemik düzlem.

6. **4-factor (Carhart) baseline, FF5 değil** — RMW + CMA factor
   exposure'larıyla horse race paperde yok. Q14 + Q15 ile bağlantılı.

7. **Quality price puzzle persists** [Section 4]: low explanatory power
   of quality on prices; potansiyel açıklamalar (mispricing /
   measurement / risk) paperde explicit ayrıştırılmamış.

## Çelişkiler/Tartışmalar

> ⚠️ **QMJ ↔ HMXZ Tablo 4 q5 captures (scope-dependent, Cycle 8 işaretli):**
> - **QMJ paper 4-factor (Carhart) lens**: alpha 66 bps/ay (t=11.20) sig
> - **HMXZ Tablo 4 q5 lens**: alpha 0.06% (t=0.42) GRS p=0.12 INSIG
> İki paper farklı methodology üzerinde sonuç veriyor; **scope-dependent**:
> - QMJ behavioral mispricing yorumuna eğilimli (4-factor alpha sig)
> - HMXZ risk premium yorumuna eğilimli (q5 captures QMJ)
> Cochrane 2011 mathematical equivalence: aynı bulgu iki yorum.
> [[meta/contradictions]]'a eklenmedi (paralel methodology, complementary
> epistemic application).

> ⚠️ **QMJ ↔ FF15 RMW (Cycle 4 ek):**
> - **FF15 RMW** = operating profitability (1 measure: REVT - COGS - XSGA
>   - XINT) / book equity; primum 0.25%/ay (t=2.92, 2x3); 2x2x2x2 joint
>   t=4.09
> - **QMJ Profitability dimension** = 6 measure (GPOA + ROE + ROA + CFOA
>   + GMAR + ACC); ayrı QMJ-style factor olarak sig 1/3/4-factor alpha
> İki paper aynı concept (profitability factor) farklı operationalization;
> RMW paperde sadece 1 measure, QMJ daha kapsamlı 6-measure composite.
> Wiki için: factors/RMW.md sayfasında **QMJ alternatif sub-section**
> (Cycle 19 update). Çelişki değil — methodology hierarchy.

> ⚠️ **QMJ SMB resurrection ↔ HLZ never sig (Cycle 12 ek):**
> - **HLZ 2016**: vanilla SMB never sig under multiple testing
>   (Bonferroni / Holm / BHY hepsi insig)
> - **QMJ Section 8**: SMB controlling for QMJ insig α=13bps → **sig
>   α=64bps (t=6.39)**
> İki paper farklı epistemik düzlem:
> - HLZ: vanilla SMB statistical test (no quality control)
> - QMJ: quality-controlled SMB (resurrection finding)
> **Çelişki değil, complementary** (paralel methodology, farklı control
> set). Wiki Q11 framing'i Cycle 19'da revisit: fully-answered "vanilla";
> resurrection finding "asterisk" notu.

> ⚠️ **Sloan zinciri 4. halka — origin attribution dual pattern:**
> Cycle 9'da F_ACCRUAL/G3 origin Sloan literatür hattı kökü olarak
> işaretlendi; Cycle 18'de M-Score TATA Sloan değil (Healy-Jones); Cycle
> 19'da QMJ Profitability ACC component **Sloan 1996 explicit cite [s.7]**
> → Sloan zinciri 4. halka. Methodology paralel + literatür hattı kökü
> Sloan, F_ACCRUAL/G3 paterni paralel.

## İlgili Sayfalar

### Concepts
- [[concepts/winner_loser_identification]] — QMJ "quality minus junk"
  paradigm winner-loser identification quality boyutu; haritalama
  tablosunda QMJ satırı (signal olarak; M-Score forensic filter ≠ QMJ
  winner identification)
- [[concepts/value_premium]] — QARP framework 4. yorum boyutu /
  combined approach sub-section (Cycle 19 ek)
- [[concepts/fundamental_scoring]] — composite scoring paradigm
  tablosunda QMJ + QARP satırları
- [[concepts/post_publication_decay]] — dört darbe sentez tablosu QMJ
  satırı (in-sample US 1956-2012 + post-pub durumu + HLZ + HXZ kanıt)
- [[concepts/multiple_testing]] — HLZ aggregate sig durumu QMJ satırı
- [[concepts/factor_zoo]] — quality factor cluster Cochrane #2 cevabı
  paralel
- [[concepts/discount_rates]] — QMJ paper "When did our field stop
  being asset pricing and become asset expected returning?" Cochrane
  2011 epigraph

### Papers
- [[novy_marx_2013_gross_profitability]] — **Cycle 23**; QMJ Profitability
  dimension GPOA bileşeni **Novy-Marx 2013 literatür hattı kökü**
  (QMJ paper [s.7] explicit cite); Profitability zinciri 3. halka
  (Sloan zinciri paralel'i 4 paper × 7 yıl: Novy-Marx 2013 → FF15
  RMW → QMJ GPOA → HXZ Cop). **İki paralel quality zinciri QMJ
  4-dimension'da birleşiyor**: Profitability dimension 6 measure
  içinde GPOA (Novy-Marx) + ACC (Sloan) yan yana.
- [[feng_giglio_xiu_2020_factor_zoo]] — **Cycle 26**; QMJ **DS LASSO
  150-factor library lens'inde DS-sig** (Tablo 1, since-2012
  factors); HMXZ q5 captures (Cycle 8) + FGX DS-sig (Cycle 26)
  **paralel methodology lens iki kullanım modu** option (q-factor
  exposure proxy + DS-sig standalone signal). Q49 partial-stronger
  hala (composite QMJ DS-sig ama dimension-spesifik decompose
  paperde yok). Q2 fully-answered ANCHOR (Cycle 19) + Q55 fully-
  answered (Cycle 26) çift epistemik kazanım.
- [[famafrench2015_five_factor]] — RMW vs QMJ Profitability paralel;
  Q14 partial-stronger (FF5 başarısızlık portföyü direct test değil
  ama large-cap-only kanıt)
- [[hou_mo_xue_zhang_2020_security_analysis]] — Tablo 4 composite QMJ
  test (q5 captures); 4 dimension breakdown bu paperde yok
- [[li_mohanram2019_quality_value]] — F&V/P + G&V/P combined paradigm
  Asness QARP ile yapısal paralel; Faz 3 strategy spec anchor
- [[lev_srivastava_2020_value_failure]] — glamour firms 2007-2018
  highest profitability since 1970 + QMJ negative HML correlation
  uyumlu kanıt
- [[sloan1996_accruals_anomaly]] — QMJ Profitability ACC component
  literatür hattı kökü; Sloan zinciri 4. halka
- [[mohanram2005_g_score]] — QMJ Growth dimension literatür hattı
  kökü (Mohanram 2005 explicit cite [s.7])
- [[harvey_liu_zhu_2016_multiple_testing]] — SMB resurrection Q11
  alternative perspective
- [[mclean_pontiff_2016_post_publication_decay]] — QMJ post-pub decay
  aggregate %35 multiplier proxy

### Factors
- [[QMJ]] — yeni factor entity (Cycle 19); composite Quality (4 dimension
  z-score average) + QMJ factor inşa
- [[RMW]] — QMJ Profitability boyutu wiki RMW factor'un alternatifi;
  factors/RMW.md sayfasında "QMJ alternatif" sub-section
- [[F_Score]] — winner-loser paradigm paralel (high-BM evren); 9 binary
  composite vs 4-dimension continuous
- [[G_Score]] — winner-loser paradigm paralel (low-BM evren); QMJ
  Growth dimension Mohanram 2005 literatür hattı kökü
- [[M_Score]] — winner-loser paradigmasına ek katman (filter); QMJ
  signal olarak winner identification, M-Score filter
- [[Accruals]] — QMJ Profitability ACC component cross-link
- [[SMB]] — QMJ Section 8 resurrection finding; Q11 alternative
  perspective
- [[HML]] — QMJ-HML negative correlation; QARP framework HML + QMJ
  kombinasyonu

### Henüz wiki'de olmayan, doğrudan ilgili paperlar
- Novy-Marx 2013 "The Other Side of Value" — QMJ Profitability GPOA
  literatür hattı kökü; Faz 2 ingest aday
- Frazzini-Pedersen 2013 "Betting Against Beta" — QMJ Safety BAB
  literatür hattı kökü (yazar continuity Pedersen); Tier 3 #58
- Frazzini-Israel-Moskowitz 2018 "Trading Costs" — annual rebalance
  cost analysis (paywall, Tier 3 #52)
- AQR data setleri (Tier 3 #55) — large-cap-only kalibrasyon
- Baker-Wurgler 2002 — QMJ Payout literatür hattı kökü
- Pontiff-Woodgate 2008 — QMJ Payout literatür hattı kökü
- McLean-Pontiff-Watanabe 2009 — QMJ Payout literatür hattı kökü
- Cohen-Polk-Vuolteenaho 2009 — QMJ paper present-value relation
  paralel
- Vuolteenaho 2002 + Fama-French 2006 — paper [Section "Related
  literature"] cited

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q2 FULLY-ANSWERED (Cycle 19, QMJ anchor)]** Large-cap quality vs
  value: 13 cycle partial sonrası fully-answered. QMJ Tablo A4 + Figure
  A1 large-cap-only test; 23/24 country pozitif alpha; 17/24 country
  4-factor alpha sig; 4 dimension breakdown (Profitability + Growth +
  Safety + Payout) wiki için yeni katkı. **Caveat**: monthly rebalance
  orijinal; annual uyarlama primum sensitivity test gerekir (Q35 + Q51
  paralel). FF15 RMW (Cycle 4 partial) + HMXZ Tablo 4 (Cycle 8 partial)
  + Lev-Srivastava 2020 dolaylı (Cycle 17 partial) + **QMJ paper anchor
  (Cycle 19)** = fully-answered.

- **[Q14 partial-stronger update (Cycle 19)]** FF5 large-cap-only:
  QMJ paper FF5 başarısızlık portföyü (small × low-OP × high-Inv)
  direct test etmiyor (4-factor Carhart baseline). Tablo A4 + Figure A1
  large-cap pozitif alpha → FF5 başarısızlık portföyünden farklı
  evrene transfer mümkün. **Tam Q14 cevabı için FF5 başarısızlık
  portföyünü direct test eden paper hala eksik**; AQR data setleri
  (Tier 3 #55) ek ingest.

- **[Q11 partial-stronger update / asterisk (Cycle 19)]** SMB never
  sig under MT: QMJ paper Section 8 + Table IX **SMB resurrection
  finding**: vanilla SMB controlling for QMJ insig α=13bps → **sig
  α=64bps (t=6.39)**. Wiki için: Q11 fully-answered durumu **vanilla
  SMB için korunur**; **quality-controlled SMB ayrı boyut** —
  fully-answered "with asterisk: resurrection under QMJ control".
  Open question text güncellenir; SMB factor exposure pozisyonu Faz 3
  spec'inde quality-aware revisit.

- **[Q15 partial-stronger ileri (Cycle 19)]** q5 vs FF5 horse race:
  HMXZ Tablo 4 q5 captures QMJ + QMJ paper 4-factor (Carhart) lens'inde
  sig — iki paper farklı methodology, tam horse race hala eksik. HXZ
  2015 q-factor origin paper bekliyor.

### Yeni Q'lar (Q49, Q50, Q51):

- **[Q49 yeni]** 4 quality dimension'ın hangisi en güçlü large-cap'te:
  QMJ paper Table VI Panel A her dimension ayrı 1/3/4-factor alpha
  raporluyor; **dimension-spesifik alpha hierarchy** Faz 2 sentez
  aşamasında değerlendirilir (Profitability vs Growth vs Safety vs
  Payout). NDX-spesifik (tech firma) sektör yorumu farklı olabilir;
  intangibles-aware versiyon (F bloğu 3 ayak methodology entegrasyonu)
  Faz 3 design.

- **[Q50 yeni]** QARP NDX-spesifik kalibrasyonu: Asness QARP =
  quality × n − P/B; n yakın 1 highest alpha (US long sample). NDX
  evrende intangibles-aware Bm (Lev-Srivastava + F bloğu methodology)
  ile QARP kombinasyonu Faz 3 design decision. **Q50 + Q45
  (value-trap-avoidance filter) + Q21 (combined methodology)** üç
  paralel Faz 3 strategy spec design.

- **[Q51 yeni]** QMJ post-2012 modern replikasyonu: paper sample sonu
  Dec 2012; FAANG era + COVID + AI 2013-2024 out-of-sample. Modern
  data Chen-Zimmermann 2022 (Tier 2 #41) + JKP 2023 (Tier 2 #44) ile
  replikasyon gerekli. McLean-Pontiff aggregate %35 decay multiplier
  proxy uygulanır → QMJ post-pub decay düzeyi belirsiz.

---
type: paper
authors: [Ball, Ray; Gerakos, Joseph; Linnainmaa, Juhani T.; Nikolaev, Valeri]
year: 2016
title: "Accruals, Cash Flows, and Operating Profitability in the Cross Section of Stock Returns"
venue: "Journal of Financial Economics 121(1) (2016) 28-45 (Working Paper No. 15-12; SSRN 2587199)"
url: https://ssrn.com/abstract=2587199
local_path: raw/papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows.pdf
ingested: 2026-05-02
phase: faz_3_cycle_38
tags: [profitability_chain, cash_based_op_profitability, cop_origin, accruals_subsumption, sloan_fixation_critique, large_cap_relevant, faz_3_selective]
status: ingested
cycle_39_note: "Cop subsumes accruals + Stambaugh-Yuan composite mispricing factors complementary methodology [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; Cycle 38 Cop subsumes Acc (Tablo 2 col 6) + Cycle 39 Stambaugh-Yuan Cluster 1 accruals dahil composite (UMO1 P1 6-anomaly avg); iki paralel methodology aile (Cop single signal cash-based vs UMO1 multi-anomaly composite); sp500_v1 + nasdaq100_v1 §2.1 Path B Profitability theme Cop + PERF (Cluster 2 GP/A + ROA dahil) iki anchor Cycle 38 + 39 sertleştirme"
---

# Ball-Gerakos-Linnainmaa-Nikolaev (2016) — Accruals, Cash Flows, and Operating Profitability

> 📝 **Cycle 38 ingest (Faz 3 üçüncü seçici ingest; Tier 1 #9 priori).**
> [[meta/handoff_faz3]] §3 paywall paperlar Faz 3 seçici ingest aday;
> Cycle 38 Ball-GLN direct ingest **Profitability zinciri 4. halka
> Cop methodology origin standalone** sertleştirme; Cycle 8 HMXZ Tablo
> 5 + Cycle 13 HXZ 2020 Replicating + Cycle 26 FGX + Cycle 27 JKP
> Cop dolaylı atıflar Ball-GLN origin paper sayfası açılana kadar
> formal değildi.

## TL;DR (4 cümle)

Ball-GLN 2016 **cash-based operating profitability** (Cop = Operating profitability − working capital accruals) tanımlayarak gross profitability + operating profitability + net income tüm accruals-içeren ölçülerini outperform eden **Profitability zinciri 4. halka** önerir. Cop ↔ accruals korelasyonu **-0.252 Pearson** (Ope ↔ accruals +0.163 Pearson tersine); Cop standalone Fama-MacBeth t=9.69 (Ope t=7.04'ten 40% Sharpe artış) + Cop **subsumes accruals** (Cop t=7.4 + Acc t=0.34 [Tablo 2 col 6]) + Cop **wins horse race** vs Ope (t=5.27 vs 1.56 [Tablo 2 col 7]). Factor portfolio [Tablo 5]: RMW^CbOp 4.88%/yr t=6.29 vs RMW^Op 3.25%/yr t=3.65 vs ACC 2.7%/yr t=3.42; tangency Sharpe [Tablo 8] **4F+Cop=1.67 > 4F+Ope+Acc=1.54** (Cop alone better than Ope+Acc combined). **Sloan fixation hypothesis çürütme**: Cop subsumption "investors fixate on profitability per se" hipotezi ile uyumsuz; Cop predicts returns 10 years ahead [Section 7].

## Tek Cümle Tezi

> Cash-based operating profitability (Cop = Ope − ΔWC) profitability ailesinde en güçlü predictor; accruals anomaly Cop'un negatif korelasyonu üzerinden gerçekleşir, bu yüzden Cop accruals factor'ünü subsume eder ve Sloan'ın "investor fixation" hipotezi yerine accrual-cash flow ayrıştırmasının pricing-relevance'ı ön plana çıkar.

## Ortaya Konan Sinyal/Faktör

- **Cop = Cash-based Operating Profitability** = (REVT − COGS − SG&A) − (ΔAR + ΔInv + ΔPrepaid − ΔDeferredRev − ΔAP − ΔAccrued); scaled by lagged total assets (AT)
- Linki: [[factors/Cop]] yeni (Cycle 38) — **Profitability zinciri 4. halka factor entity**
- Operating profitability paper'ı: Ball et al. 2015 [Working Paper] — Ope methodology paralel paper (paper [s.6 + s.8] cross-cite)

## Empirik Sonuçlar (sayılarla)

### Sample [Section 3, s.5-7]

| Item | Spec |
|------|------|
| Period | July 1963 - December 2014 (51.5 yıl) |
| Universe | NYSE + Amex + NASDAQ ordinary common shares; ex-financials (1-digit SIC 6) |
| Accounting lag | 6-month (FF 2008 paterni paralel) |
| Microcap definition | <20th NYSE market cap percentile **(FF 2008 paterni explicit cite [s.7])** |
| Subsamples | All-but-microcaps + Microcaps (FF 2008 paterni paralel) |

### Korelasyon Yapısı [Tablo 1 Panel B + Section 3, s.7-8]

| Pair | Pearson | Spearman | Interpretation |
|------|---------|----------|----------------|
| Ope ↔ Cop | 0.845 | 0.805 | Highly correlated (Cop = Ope − ΔWC) |
| Ope ↔ Accruals | **+0.163** | +0.130 | **Positive** (Ope includes accruals) |
| **Cop ↔ Accruals** | **-0.252** | **-0.280** | **NEGATIVE** ⭐ key finding |

> **Key inference**: "Firms that are profitable because of high accruals are less profitable on a cash basis" [s.8]. Bu negatif korelasyon accruals anomaly'sinin altında yatan mekanizma.

### Fama-MacBeth Regressions [Tablo 2]

**All-but-microcaps Panel A**:

| Column | Spec | t-value(s) |
|--------|------|------------|
| 1 | Ope standalone | t(Ope) = **8.86** |
| 3 | Acc standalone | t(Acc) = **-3.9** (Sloan replication) |
| 4 | Ope + Acc | t(Ope) = 7.04 + t(Acc) = -5.50 (anomaly güçlenir!) |
| 5 | Cop standalone | **t(Cop) = 9.69** ⭐ (40% Sharpe artış vs Ope) |
| 6 | Cop + Acc | t(Cop) = **7.4** + t(Acc) = **0.34** ⭐ (Cop **subsumes** accruals) |
| 7 | Cop vs Ope horse race | t(Cop) = **5.27** + t(Ope) = **1.56** ⭐ (Cop wins) |

**Microcaps Panel B**: Cop t=9.62 dominant; Cop subsumes accruals + wins horse race aynı pattern.

> **Key finding** [s.10]: "Cash-based operating profitability subsumes the explanatory power of accruals... inconsistent with Sloan's (1996) hypothesis that investors 'fixate' on profitability per se."

### Factor Portfolio Returns [Tablo 5]

**Methodology**: 6-portfolio sort (FF 2015 paterni paralel; size median × profitability 30/70 NYSE breakpoints VW)

| Factor | Avg Annualized Return | t-value |
|--------|------------------------|---------|
| ACC | 2.7% | 3.42 |
| RMW^Op (operating profitability) | 3.25% | 3.65 |
| **RMW^CbOp (cash-based op)** | **4.88%** | **6.29** ⭐ |

> **Key inference**: RMW^CbOp average return + t-value substantially higher than RMW^Op + ACC.

### 3-Factor Augmentation Pricing [Tablo 7 Panel A]

3F + RMW^CbOp **subsumes** RMW^Op (alpha t=-1.15 INSIG) + accruals factor (alpha 12 bps t=1.69 INSIG).
3F + RMW^Op **does NOT subsume** RMW^CbOp (alpha 27 bps t=7.08 SIG).
3F alone: 3 profitability factors all sig (Ope α 46 bps t=7.01 + Cop α **58 bps t=10.09** + ACC α 22 bps t=3.34).

### Tangency Portfolio Sharpe Ratios [Tablo 8]

| Factor Set | Annualized Sharpe |
|------------|-------------------|
| MKT alone | 0.39 |
| 4F (MKT + SMB + HML + UMD) | 1.06 |
| 4F + ACC | 1.12 |
| 4F + Ope | 1.40 |
| **4F + Cop** | **1.67** ⭐ |
| 4F + Ope + ACC | 1.54 |
| 4F + Cop + ACC | 1.69 (Cop alone yeterli; ACC marjinal) |

> **Key inference**: **4F + Cop (1.67) > 4F + Ope + ACC (1.54)** — investor "would do better by adding just cash-based operating profitability to the investment opportunity set than by adding both accruals and operating profitability" [s.20].

### Predictive Horizon [Section 7, Fig. 2]

Cop predicts returns **10 years into the future**; Sharpe ratio difference Cop vs Ope decreases over time but stays positive.

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Decile-spread methodology + 6-portfolio factor portfolio formal tanımı (FF 2015 paterni paralel size × profitability 30/70 NYSE breakpoints VW); All-but-microcaps + Microcaps panel comparison + univariate FM regression Sharpe-proportional t-value framework | ✅ doğrudan |
| **Annual rebalance** | "In portfolio sorts, we rebalance the portfolios annually at the end of June" [s.7]; FM regressions monthly resort orijinal ama portfolio sorts annual June (FF15 paterni paralel; Cop methodology annual rebalance compatible); Q35+Q51+Q57+Q75 paralel sensitivity test partial | ⚠️ partial (annual portfolio sorts ✅ + monthly FM regressions caveat) |
| **Large-cap evrene transfer** | All-but-microcaps Panel A primary analysis + Microcaps Panel B comparison ([s.7] FF 2008 paterni explicit cite "Following Fama and French (2008), we define Microcaps as stocks with a market value of equity below the 20th percentile of the NYSE market capitalization distribution"); Cop sig in both panels (All-but-micro t=9.69 + Microcaps t=9.62); large-cap-direct test cross-evidence Q14 fully-answered FF 2008 ANCHOR cross-link | ✅ ⭐ KRITIK direct fit |
| **NDX intangibles / growth firms** | Compustat traditional accounting; Cop = Ope − ΔWC (cash-based ama balance sheet accruals working capital traditional); intangibles-aware genişletme YOK; FAANG firma R&D giderleştirme numerator etkisi (Cop = REVT − COGS − SG&A; SG&A R&D dahil olduğu için R&D-intensive firmalarda yapay düşük Cop); F bloğu 4-katmanlı methodology paralel değil | ❌ uyumsuz traditional accounting (Q56 + Q73 + Q79 yeni paralel) |

**Strateji tasarımına net implikasyon**:

Ball-GLN 2016 [[strategies/sp500_v1]] §2.1 Path B Profitability theme + [[strategies/nasdaq100_v1]] §2.1 Path B Profitability theme **canonical methodology origin paper**: (1) **Cop tercih RMW Ope reject + QMJ composite + GP/A standalone hierarchy**: Cop direct factor portfolio 4.88%/yr t=6.29 RMW^Op 3.25%/yr t=3.65'ten substantially higher; sp500_v1 + nasdaq100_v1 Path B Cop methodology origin paper anchor; (2) **Sloan fixation hypothesis çürütme**: F_ACCRUAL/G3/QMJ ACC mispricing detection paradigması Cop lens'inde subsumed (Cycle 35 HXZ 2015 q-factor Sloan accruals exception ile çelişki YOK methodology farkı; Cop accrual-cash flow decomposition vs q-factor I/A+ROE size-controlled; Sloan zinciri F_ACCRUAL/G3/QMJ ACC binary ortogonal complement); (3) **Tangency portfolio 4F+Cop=1.67** [[methodology/backtest_spec]] §5.1 4/4 hayatta kalan factor signal'ları sertleştirme; (4) **NDX-spesifik R&D R&D-intensive firmalarda Cop yapay düşük** Q79 yeni Faz 3 implementation custom modification (Cop intangibles-adjusted SG&A purging F bloğu paralel; Q56 + Q73 paterni paralel).

## Limitler ve Caveats

- **Sample 1963-2014** post-2014 10 yıl out-of-sample (FAANG era 2014-2024); JKP 2023 partial 2014-2020 6 yıl modern coverage (Q80 yeni)
- **Balance sheet accruals**: Hribar-Collins 2002 measurement errors; paper post-1988 cash flow statement alternative robustness check yapıyor [s.7]
- **R&D-intensive firma yapay düşük Cop**: Cop = REVT − COGS − SG&A; SG&A includes R&D expense → FAANG/biotech firmalarda R&D giderleştirme Cop'u yapay düşürür (Q79 yeni; F bloğu paralel intangibles-aware Cop modification Faz 3 implementation)
- **Monthly FM regressions vs annual portfolio sorts asimetri**: paper [s.7] explicit "FM regressions monthly recompute" + "portfolio sorts annual June rebalance"; wiki annual frequency hedef için Cop annual portfolio sort version kullanılır (paper Tablo 5+ direct empirical anchor); FM regression monthly orijinal HXZ 2015 r_ROE monthly resort paralel caveat
- **Traditional accounting**: Cop balance sheet working capital accruals; intangibles-aware genişletme YOK; F bloğu 4-katmanlı NDX strategy ortogonal methodology
- **Sloan fixation hypothesis çürütme**: paper investor fixation reject ama mispricing alternative (under-reaction to cash flow information gradually corrected over decade) paper [s.2 footnote]; **wiki taraf tutmaz** mispricing vs risk premium yorumu (Cochrane mathematical equivalence)
- **6-portfolio factor methodology FF 2015 paterni**: 2×3 sort decile spread değil 30/70 breakpoints; paper Tablo 5 RMW^CbOp construction FF15 paterninden farklı (Asness QMJ 4-dimension composite + HXZ 2020 Cop methodology farkları sertleştirme paterni paralel)

## İlgili Sayfalar

### Profitability Zinciri 4-Paper × 7-Yıl Methodology Hierarchy

| Halka | Paper | Methodology | Cycle |
|-------|-------|-------------|-------|
| 1 (origin) | [[papers/novy_marx_2013_gross_profitability]] | GP/A = (REVT−COGS)/AT gross profitability standalone | 23 |
| 2 | [[papers/famafrench2015_five_factor]] | RMW Ope = (REVT−COGS−SG&A−INT)/BE annual 2×3 sort | 4 |
| 3 | [[papers/asness_frazzini_pedersen_2019_qmj]] | QMJ Profitability dim GPOA composite (5 measure) | 19 |
| **4** ⭐ | **[[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]** | **Cop = Ope − ΔWC** cash-based operating profitability standalone | **38 (BU)** |

### Sloan Zinciri Paralel + Birleşim Noktası
- [[papers/sloan1996_accruals_anomaly]] — Sloan accruals anomaly origin (paper [s.2 + s.4] explicit cite + Sloan fixation hypothesis çürütme)
- [[papers/piotroski2000_f_score]] — F_ACCRUAL Sloan zinciri 1. halka (binary version)
- [[papers/mohanram2005_g_score]] — G3 Sloan zinciri 2. halka
- [[papers/asness_frazzini_pedersen_2019_qmj]] — QMJ ACC Sloan zinciri 3. halka + Profitability zinciri 3. halka **birleşim noktası**

### q-Factor Model + Replication
- [[papers/hou_xue_zhang_2015_q_factor]] (Cycle 35) — paper [s.2 + s.6] explicit cite "Hou, Xue, and Zhang (2015) q-factor model"; ROE ↔ Cop methodology paralel (cash-based vs investment-q-theoretical)
- [[papers/hou_mo_xue_zhang_2020_security_analysis]] (Cycle 8) — q5 model Tablo 5 Cop methodology validation; HMXZ Cop alpha 0.69%/ay sig (4/4 hayatta kalan)
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] (Cycle 13) — 447 anomaly NYSE-VW Cop empirical validation
- [[papers/feng_giglio_xiu_2020_factor_zoo]] (Cycle 26) — Q55 fully-answered Profitability ailesi DS-sig 150-factor library
- [[papers/jensen_kelly_pedersen_2023_replication_crisis]] (Cycle 27) — JKP Profitability theme Bayesian framework

### FF Ailesi Methodology Continuity
- [[papers/famafrench1993_three_factor]] — FF3 + 6-portfolio methodology FF 2015 paterni
- [[papers/famafrench2015_five_factor]] — FF5 RMW Ope + Ball-GLN [s.6] explicit cite "Fama and French (2015)"
- [[papers/fama_french_2008_dissecting_anomalies]] (Cycle 37) — Microcaps definition explicit cite [s.7] "Following Fama and French (2008)"; Q14 fully-answered ANCHOR cross-evidence

### Factor Entities
- [[factors/Cop]] yeni (Cycle 38) — cash-based operating profitability factor entity
- [[factors/Gross_Profitability]] — Profitability zinciri 1. halka GP/A
- [[factors/RMW]] — FF15 RMW Ope; methodology farkı dokümante
- [[factors/QMJ]] — QMJ Profitability dim GPOA + ACC birleşim noktası
- [[factors/Accruals]] — Sloan accruals zinciri; Ball-GLN cash flow + accruals decomposition
- [[factors/ROE]] — HXZ ROE methodology paralel (cash-based)

### Concepts
- [[concepts/fundamental_scoring]] — Profitability factor ailesi methodology hierarchy
- [[concepts/earnings_quality]] — Sloan zinciri + Ball-GLN accruals decomposition methodology paralel
- [[concepts/factor_zoo]] — Profitability ailesi methodology evolution Cop sertleştirme
- [[concepts/post_publication_decay]] — dört darbe sentez tablosu Cop satırı 4/4 hayatta kalan formal origin
- [[concepts/winner_loser_identification]] — B bloğu core kavramı Profitability zinciri

### Strategy Specs
- [[strategies/sp500_v1]] §2.1 Path B Profitability theme Cop methodology origin paper anchor
- [[strategies/nasdaq100_v1]] §2.1 Path B Profitability theme Cop methodology origin paper anchor
- [[methodology/backtest_spec]] §5.1 4/4 hayatta kalan tablosu Cop formal origin sertleştirme

## Çelişkiler/Tartışmalar

- **Ball-GLN Cop vs Sloan accruals fixation hypothesis**: paper [s.10] explicit "inconsistent with Sloan's (1996) hypothesis that investors 'fixate' on profitability per se"; **çelişki değil scope-dependent** — Sloan 1996 mispricing/fixation interpretation Cop subsumption ile reject edilir ama Cop alternative interpretation (under-reaction to cash flow information gradually corrected over decade) hala mispricing sınıfında; **wiki taraf tutmaz** Cochrane mathematical equivalence (rational risk premium + behavioral mispricing iki yorum birden Cop'u açıklayabilir).
- **Ball-GLN Cop vs HXZ 2015 q-factor Sloan accruals exception**: HXZ 2015 [Tablo + Section 3 + Section 6] q-factor Sloan accruals'da daha kötü (h-l alpha -0.39% t=-2.48 FF -0.29% t=-1.96'dan WORSE); Ball-GLN Cop accruals subsumption Cop direct test (FM regression t=7.4 + Acc t=0.34); **çelişki değil methodology farkı** — q-factor I/A+ROE size-controlled lens Sloan accruals exception vs Cop accrual-cash flow decomposition lens accruals subsumption; iki ayrı epistemic framework complementary.
- **Ball-GLN Cop vs FF15 RMW Ope**: paper Cop t=9.69 vs Ope t=7.04 (40% Sharpe artış) horse race Cop wins (Tablo 2 col 7 Cop t=5.27 + Ope t=1.56); **çelişki değil methodology evrim** Profitability zinciri 4. halka (FF15 RMW Ope literature continuity 2.→4. halka).
- **Ball-GLN Cop vs Novy-Marx GP/A**: paper [s.10] "Sharpe ratio for cash-based operating profitability is also higher than the Sharpe ratios for gross profitability and net income" (Ball et al. 2015 cross-cite); **çelişki değil methodology evrim** Profitability zinciri 4. halka (GP/A literature continuity 1.→4. halka).
- **Ball-GLN sample 1963-2014 vs JKP 2023 sample 1926-2020**: methodology farkı paper sample window (Ball-GLN US-only 1963+; JKP global 1986+); **çelişki YOK** literature continuity scope-dependent.

## Açık Sorular (Open Questions)

- **Q55** (Profitability zinciri horse race GP/A vs RMW Ope vs QMJ GPOA vs Cop) — **fully-answered Cycle 26 + Cycle 38 sertleştirme** (Ball-GLN Cop origin paper direct anchor; FM regression t=9.69 standalone + Sharpe 4F+Cop=1.67 ⭐ Profitability ailesinde en güçlü)
- **Q49** (QMJ 4 dimension hangisi en güçlü) — **partial-stronger Cycle 38** (Profitability dimension origin direct kanıt 5 measure içinde GPOA + ACC birleşim Ball-GLN methodology link)
- **Q9** (Beneish + composite score) — partial-stronger
- **Q79 yeni**: Cop methodology NDX-spesifik R&D-intensive firma kalibrasyonu (Cop = REVT − COGS − SG&A; SG&A R&D dahil; FAANG/biotech firmalarda R&D giderleştirme Cop'u yapay düşürür); F bloğu paralel intangibles-aware Cop modification Faz 3 implementation custom (Q56 + Q73 paterni paralel)
- **Q80 yeni**: Ball-GLN sample 1963-2014 post-2014 10 yıl modern replikasyon (JKP 2023 partial 2014-2020 6 yıl + post-2020 hala out-of-sample); FAANG era Cop pattern stabil mi yoksa değişti mi (R&D-intensive firmalarda Cop bias artıyor mu); Faz 3 custom backtest implementation Cycle 41+ hedef
- **Q15a** (Sloan accruals q-factor exception scope-dependent vs structural limit; Cycle 35 yeni) — **partial-stronger Cycle 38** (Ball-GLN Cop accruals subsumption q-factor Sloan accruals exception complementary methodology farkı; Cop accrual-cash flow decomposition lens vs q-factor I/A+ROE size-controlled lens)

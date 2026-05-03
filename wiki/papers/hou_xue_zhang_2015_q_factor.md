---
type: paper
authors: [Hou, Kewei; Xue, Chen; Zhang, Lu]
year: 2015
title: "Digesting Anomalies: An Investment Approach"
venue: "Review of Financial Studies (NBER WP 18435, October 2012)"
url: https://www.nber.org/papers/w18435
local_path: raw/papers/Digesting Anomalies An Investment Approach.pdf
ingested: 2026-05-02
phase: faz_3_cycle_35
tags: [q_factor_model, investment_q_theory, factor_model, large_cap, profitability, accruals, momentum, distress, ivol, peripheral_anomalies]
status: ingested
cycle_37_note: "HXZ 2015 [s.7] FF 2008 cross-cite ('investment effect strong in microcaps and small stocks but largely absent in big stocks') origin claim direct test paper [[papers/fama_french_2008_dissecting_anomalies]] Cycle 37 ✓; r_I/A factor literatür hattı kökü FF 2008 origin (HXZ 2015 q-theoretical implementation FF 2008 size-conditional finding'i motive; q-factor size-controlled 2×3×3 triple sort'un methodology temeli FF 2008'da); Q14 fully-answered üçlü teyit FF 2008 + Israel-Moskowitz + HXZ 2015"
cycle_38_note: "HXZ ROE methodology paralel Cop (cash-based) [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓; HXZ 2015 r_ROE = IBQ/BE_lagged (cash-based intuition Sloan accruals fixation çürütme paterni paralel); Ball-GLN Cop subsumption q-factor Sloan accruals exception (Q15a) complementary methodology farkı (q-factor I/A+ROE size-controlled lens vs Cop accrual-cash flow decomposition lens iki ayrı epistemic framework complementary)"
cycle_39_note: "HXZ q-factor model (investment-based) vs Stambaugh-Yuan mispricing factor model methodology farkı [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; Stambaugh-Yuan [s.10+] explicit '4F outperforms HXZ4' on own 11 anomaly + larger 73 anomaly (HXZ 2015a/b set); üç paralel framework methodology choice HXZ investment-based + FF15 risk-factor-based + Stambaugh-Yuan mispricing-based wiki taraf tutmaz Cochrane mathematical equivalence; Cluster 2 (PERF) ROA Stambaugh-Yuan içinde + HXZ ROE q-factor model paralel methodology"
---

# Hou-Xue-Zhang (2015) — Digesting Anomalies: An Investment Approach

> 📝 **Cycle 35 ingest (Faz 3 ilk seçici ingest; Tier 1 #3 yüksek priori).**
> q-factor model **formal origin tanımı** wiki boşluğu kapatılır
> (Cycle 8 HMXZ + Cycle 13 HXZ Replicating + Cycle 26 FGX + Cycle 27
> JKP'den dolaylı atıflar HXZ 2015 origin paper sayfası açılana kadar
> formal değildi). [[meta/handoff_faz3]] §3 yüksek priori.

## TL;DR (4 cümle)

HXZ 2015, investment-based asset pricing teorisinden ([[concepts/discount_rates]] Cochrane 1991 q-theory) motive olan **q-factor model** önerir: 4 faktör (MKT + r_ME size + r_I/A investment + r_ROE return on equity) Fama-French ve Carhart modellerinden daha geniş bir anomaly alt-kümesini açıklar. Sample 1972-2011 monthly CRSP+Compustat; 2×3×3 triple sort NYSE breakpoints VW; r_ME virtually identical SMB ile (corr 0.95), r_I/A HML-correlated (0.69), r_ROE WML-correlated (0.50). Headline performans: PEAD/SUE q-factor h-l alpha 0.14% t=0.92 (FF 0.54% sig'den insig'e), IVOL -0.04% t=-0.19 (FF -0.91%'den), distress 0.02% t=0.07 (FF -1.43%'ten); **Sloan accruals deciles q-factor model'i exception (h-l alpha -0.39% t=-2.48 FF -0.29% t=-1.96'den daha kötü)**. Paper investment-based, common risk factors, mispricing üç yorum sunar — **wiki taraf tutmaz** Cochrane mathematical equivalence (paper [s.27-29] explicit "two sides of same coin" Lin-Zhang 2012).

## Tek Cümle Tezi

> Investment-based q-theory empirical implementation olarak 4-faktör (MKT + ME + I/A + ROE) workhorse asset pricing model Fama-French/Carhart'tan ekonomik sezgi + parsimony açısından üstündür ([s.31] "Fama-French model largely an ad hoc, data mined model; q-factor model close interaction theoretical and empirical research").

## Ortaya Konan Sinyal/Faktör

- **q-factor model 4 faktör**:
  - MKT — market excess return (CAPM paterni)
  - r_ME — size factor (small minus big; SMB paralel)
  - **r_I/A — investment factor** (low minus high investment-to-assets) ⭐
  - **r_ROE — return on equity factor** (high minus low ROE) ⭐
- Linki: [[concepts/q_factor_model]] yeni (Cycle 35) + [[factors/I_A]] yeni + [[factors/ROE]] yeni
- Methodology: 2×3×3 triple sort (size × A/A × ROE) NYSE breakpoints VW; size + A/A annual June sort; ROE monthly resort (quarterly earnings announcement-based); ex-financials + ex-negative book equity

## Empirik Sonuçlar (sayılarla)

### Factor Premium [Tablo 1 Panel A, s.6]

| Factor | Mean (%/month) | t-stat | CAPM α (%/month) | t-stat | Notes |
|--------|----------------|--------|-------------------|--------|-------|
| r_ME | 0.31 | 2.09 | 0.24 | 1.64 | SMB ile virtually identical: corr 0.95 + SMB loading 0.99 (FF3 spanning) |
| r_I/A | 0.44 | 4.73 | 0.51 | sig | FF3 HML loading 0.40 + HML corr 0.69 → HML-like role |
| r_ROE | 0.60 | 4.85 | — | — | FF3 R²=19% (önemli yeni varyasyon); WML corr 0.50; rME corr -0.30; r_I/A corr 0.05 (orthogonal) |

### Anomaly Subsumption Headline [Section 3.1, Tablo 2-7]

| Anomaly | FF α (%/month) | Carhart α | **q-factor α** | Sonuç |
|---------|------------------|-----------|----------------|-------|
| PEAD/SUE high-low | 0.54 (t=4.26) | 0.32 (t=2.43) | **0.14 (t=0.92)** | INSIG → ROE factor 5.5σ + |
| IVOL high-low | -0.91 (t=-4.48) | -0.58 (t=-2.59) | **-0.04 (t=-0.19)** | INSIG → I/A + ROE both right direction |
| Distress high-low | -1.43 (t=-5.21) | -0.55 (t=-2.51) | **0.02 (t=0.07)** | INSIG → ROE factor -1.79 spread |
| Net stock issues h-l | -0.62 (sig) | -0.57 (sig) | **-0.32 (t=-2.10)** | 44% reduction (still sig) |
| 25 size×B/M m.a.e. | 0.10 | 0.11 | 0.12 | Comparable |
| 25 size×momentum m.a.e. | 0.22 | 0.11 | 0.11 | Identical to Carhart |
| **Sloan accruals h-l** | **-0.29 (t=-1.96)** | **-0.29 (t=-1.69)** | **-0.39 (t=-2.48)** | ⚠️ q-factor WORSE — exception |

**Sloan accruals exception** [s.2 Abstract + Section 3.1]: q-factor model accruals deciles'de underperform; "investment factor loading goes right direction ama ROE factor loading wrong direction. Intuitively, high accrual firms invest more but are also more profitable."

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Decile-spread methodology + 80+ anomaly cross-subsumption testing; 2×3×3 sorted factor portfolio formal tanımı | ✅ doğrudan fit |
| **Annual rebalance** | r_ME + r_I/A annual June sort; **r_ROE MONTHLY resort** ([s.7 fn 5]: "ROE forecasts future returns to extent that it forecasts future ROE; most recent ROE contains up-to-date information; constructing ROE factor with monthly sorts makes economic sense"); **Apx E [s.7 fn 5]: annually-sorted versions of momentum + PEAD + IVOL + distress DON'T EXIST — none of high-minus-low portfolios produce mean excess returns or CAPM alphas significantly different from zero** | ⚠️ kritik caveat — wiki annual frequency için ROE factor monthly construction zorunlu; Q35+Q51+Q57 paralel sensitivity (paper explicit annual-sort failure dokümante) |
| **Large-cap evrene transfer** | NYSE breakpoints + VW microcap-arınmış convention paterni explicit ([s.7]: "NYSE breakpoints to alleviate impact of microcaps and small stocks; transaction costs and lack of liquidity, portion of anomalies in microcaps and small stocks might not be exploitable in practice"); FF 2008 cross-cite "investment effect strong in microcaps and small stocks but largely absent in big stocks" → q-factor size-controlled | ✅ ⭐ KRITIK direct fit |
| **NDX intangibles / growth firms** | r_I/A = annual change in total assets / lagged total assets (traditional accounting; Compustat AT); ROE = quarterly IBQ / lagged book equity (traditional book equity SEQQ + TXDITCQ - preferred); intangibles-aware genişletme YOK; F bloğu 4-katmanlı methodology paralel değil | ❌ uyumsuz traditional accounting (Q23 + Q73 yeni paralel) |

**Strateji tasarımına net implikasyon**:

q-factor model **wiki Faz 3 strategy spec'lerinde benchmark + alpha measurement modeli**: factor inclusion için 5. paralel methodology (HLZ + FGX + JKP statistical filter + HXZ NYSE-VW + JKP capped VW replication-robust filter + **q-factor span direct test**) [[methodology/backtest_spec]] §4.4 sertleştirme. **Sloan accruals exception kritik**: F bloğu intangibles + Profitability zinciri Cop Q-factor q-factor model'in tam kapsamında değil; [[strategies/sp500_v1]] §2.1 Path A F&V/P + Path B GP×V/P + [[strategies/nasdaq100_v1]] §2.5 F bloğu 4-katmanlı q-factor span kontrolü ek katman. **Annual frequency caveat**: r_ROE monthly construction zorunlu wiki yıllık rebalans hedefi ile uyumsuz; [[meta/open_questions]] Q35+Q51+Q57 sensitivity test paralel; r_I/A annual sort + r_ROE quarterly sort hibrit Faz 3 backtest implementation kararı.

## Limitler ve Caveats

- **Sample 1972-2011** post-2011 14 yıl out-of-sample (FAANG era 2012-2024); JKP 2023 [[papers/jensen_kelly_pedersen_2023_replication_crisis]] modern data 2014-2020 partial coverage
- **Sloan accruals exception** [Tablo öğesi]: q-factor model accruals'da daha kötü; F_ACCRUAL/G3/QMJ ACC Sloan zinciri q-factor lens'inde yetersiz; mispricing yorumu Cochrane mathematical equivalence
- **r_ROE monthly resort zorunlu** [s.7 fn 5]: annual-sort version momentum/PEAD/IVOL/distress tüm anomalies INSIG; wiki annual frequency hedef için kritik caveat
- **Triple sort sample restriction**: financials + negative book equity ex-financials kuralı paralel
- **Scope-restricted to traditional accounting**: r_I/A = ΔAT/AT-lagged; intangibles-aware genişletme YOK; F bloğu 4-katmanlı NDX strategy ortogonal methodology
- **Investment-based interpretation preferred** [Section 5.1] ama paper [Section 5.2] common risk factors + mispricing alternative interpretations explicit kabul eder; **wiki taraf tutmaz** (Cochrane mathematical equivalence)
- **Factor model linear approximation nonlinear characteristics-based investment first-order condition'a** [s.26 footnote/main]: "Strictly speaking, equation does not give rise to a factor model. Nevertheless, we opt to use a linear factor approximation"
- **Size factor secondary role** [s.4]: "size factor plays only a secondary role; investment and ROE factors more prominent"

## İlgili Sayfalar

### Sister q-factor papers (4-paper × 8+ yıl literature continuity hattı)
- [[papers/hou_mo_xue_zhang_2020_security_analysis]] (Cycle 8) — q5 model security analysis uygulaması (eg+ factor; F-Score/V/P/Magic Formula/QMJ test); HXZ 2015 q-factor origin → q5 extension
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] (Cycle 13) — 447 anomaly NYSE-VW empirical replication; HXZ 2015 q-factor lens kullanır
- [[papers/jensen_kelly_pedersen_2023_replication_crisis]] (Cycle 27) — Bayesian Empirical Bayes hierarchical framework; q-factor cross-test

### Literatür hattı kökü (Origin attribution dual pattern)

**r_I/A (investment factor) origin attribution**:
- Paper-spesifik: HXZ 2015 (BU PAPER; q-factor formal origin tanımı)
- Literatür hattı kökü: Cochrane 1991 [[concepts/discount_rates]] (investment-q theory); Berk-Green-Naik 1999; Liu-Whited-Zhang 2009; Fama-French 2008 "Dissecting Anomalies" (paywall→preprint); Cooper-Gulen-Schill 2008 [[papers/cooper_gulen_ion2018_asset_growth_factor_models]] paralel paper (Cycle 10); Fairfield-Whisenant-Yohn 2003; Anderson-Garcia-Feijoo 2006; Titman-Wei-Xie 2004 — investment-return negative relation literature

**r_ROE (return on equity factor) origin attribution**:
- Paper-spesifik: HXZ 2015 (BU PAPER; ROE factor formal tanımı)
- Literatür hattı kökü: Ball-Brown 1968 (earnings announcement effect); Bernard-Thomas 1989/1990 (PEAD); Frankel-Lee 1998 (paywall); Piotroski 2000 [[papers/piotroski2000_f_score]]; Fama-French 2006; Novy-Marx 2012/2013 [[papers/novy_marx_2013_gross_profitability]] (Profitability zinciri 1. halka)

### Factor Entities
- [[factors/I_A]] yeni (Cycle 35) — investment factor entity
- [[factors/ROE]] yeni (Cycle 35) — return on equity factor entity
- [[factors/SMB]] cross-link — r_ME virtually identical (corr 0.95 + SMB loading 0.99); ME ayrı entity AÇILMADI
- [[factors/CMA]] cross-link — I/A factor methodology farkı (CMA = sort decile spread; I/A = q-theoretical 2×3×3 implementation)
- [[factors/RMW]] cross-link — ROE factor methodology farkı (RMW = operating profitability annual; ROE = quarterly IBQ monthly resort)
- [[factors/UMD]] cross-link — r_ROE corr 0.50 with WML; momentum-relevant role

### Concepts
- [[concepts/q_factor_model]] yeni (Cycle 35) — q-factor model concept hub
- [[concepts/factor_model]] cross-link — FF3/Carhart/FF5/HXZ-q5 hiyerarşisi
- [[concepts/discount_rates]] cross-link — Cochrane 1991 q-theory + investment first-order condition
- [[concepts/expected_returns_vs_cash_flows]] cross-link — Gordon Growth Model paralel ROE/Bm interpretation
- [[concepts/factor_zoo]] cross-link — Cochrane #1-#3 sorularına HXZ 2015 explicit cevap [Section 6 Conclusion]: 15 anomaly investment+ROE iki faktör K=4 dimension subsumption

### Comparisons
- [[papers/famafrench2015_five_factor]] cross-link — FF5 vs HXZ q-factor horse race (Q15 + Q24 partial-stronger / fully-answered); FF15 RMW Ope ↔ HXZ ROE methodology farkı; FF15 CMA ↔ HXZ I/A methodology farkı

### Strategy Specs
- [[strategies/sp500_v1]] §3.2 statistical filter + §3.3 replication-robust filter + Path D Investment factor (CMA passive exposure ↔ I/A direct test)
- [[strategies/nasdaq100_v1]] §3.2-3.3 + §2.5 F bloğu 4-katmanlı q-factor span kontrolü ek katman

### Methodology
- [[methodology/backtest_spec]] §4.4 darbe (4) replication-robust filter HXZ q-factor formal tanımı sertleştirme
- [[methodology/data_sources]] §1 Chen-Zimmermann + §2 JKP code repository implementation infrastructure

## Çelişkiler/Tartışmalar

- **Sloan accruals exception**: q-factor model accruals'da yetersiz (h-l alpha -0.39% t=-2.48); Sloan zinciri F_ACCRUAL/G3/QMJ ACC mispricing detection paradigması q-factor lens'inde yetersiz. **Çelişki YOK** scope-dependent (paper explicit "trouble in explaining Sloan total accrual effect" [Section 3 + Section 6 Conclusion]; investment-based theoretical limit acknowledged).
- **HXZ 2015 vs HXZ 2020 Replicating Anomalies methodology evrim**: HXZ 2015 ~15 anomaly + 4-factor model formal origin; HXZ 2020 447 anomaly + q-factor lens scaled-up. Çelişki YOK literature continuity (Cycle 13 paterni paralel).
- **HXZ 2015 vs JKP 2023 framework farkı**: HXZ 2015 frequentist factor regression + GRS test; JKP 2023 Bayesian Empirical Bayes hierarchical. Çelişki YOK methodology framework çatallanma ([[meta/contradictions]] §3 Cycle 27 entry; üç paralel statistical methodology aile).
- **Investment-based vs Common Risk Factors vs Mispricing üç yorum** [Section 5.2]: paper "neither rules out mispricing nor pursues risk factor interpretation"; **wiki taraf tutmaz** Cochrane mathematical equivalence Lin-Zhang 2012 "two sides of same coin".

## Açık Sorular (Open Questions)

- **Q15** (FF5 vs HXZ q-factor horse race) — **fully-answered candidate** (HXZ 2015 origin paper + paper [Section 3 + Conclusion] explicit FF5/Carhart vs q-factor PEAD/IVOL/distress/net issues subsumption test; q-factor outperforms FF/Carhart 5/6 anomalies; Sloan accruals exception)
- **Q24** (q5 vs FF5 horse race) — partial-stronger (HXZ 2015 4-factor origin; HMXZ 2020 q5 extension Cycle 8; FGX 2020 cross-test Cycle 26)
- **Q34** (HXZ 447 anomaly q-factor cross-subsumption) — partial-stronger (HXZ 2015 origin + 2020 empirik)
- **Q15a yeni**: q-factor Sloan accruals exception scope-dependent yorum mı yoksa structural limit mi? (Sloan zinciri q-factor span dışı; F bloğu 4-katmanlı NDX strategy paralel)
- **Q73 yeni**: q-factor intangibles-aware genişletme aday (NDX FAANG profile + F bloğu 4-katmanlı methodology paralel; r_I/A traditional ΔAT vs intangibles-adjusted ΔTotalAssets); Faz 3 implementation custom modification
- **Q74 yeni**: HXZ 2015 sample 1972-2011 post-2011 14 yıl out-of-sample modern replikasyon (JKP 2023 partial 2014-2020 6 yıl + post-2020 hala out-of-sample); custom Faz 3 backtest implementation
- **Q75 yeni**: r_ROE monthly construction zorunluluğu ([s.7 fn 5] annual-sort momentum/PEAD/IVOL/distress INSIG); wiki annual rebalance frequency hedef için ROE factor monthly resort hibrit yapı; Faz 3 backtest implementation karar (r_I/A annual + r_ROE monthly hibrit reconciliation)

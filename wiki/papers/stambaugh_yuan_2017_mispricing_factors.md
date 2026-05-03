---
type: paper
authors: [Stambaugh, Robert F.; Yuan, Yu]
year: 2017
title: "Mispricing Factors"
venue: "Review of Financial Studies 30(4), 1270-1315 (NBER WP 21533, September 2015)"
url: https://www.nber.org/papers/w21533
local_path: raw/papers/stambaugh_yuan_2017_mispricing_factors.pdf
ingested: 2026-05-02
phase: faz_3_cycle_39
tags: [mispricing_factors, composite_scoring, clustering_methodology, mgmt_perf, sentiment, arbitrage_asymmetry, faz_3_selective, tier_1_23]
status: ingested
---

# Stambaugh-Yuan (2017) — Mispricing Factors

> 📝 **Cycle 39 ingest (Faz 3 dördüncü seçici ingest; Tier 1 #23 priori).**
> [[meta/handoff_faz3]] §3 Stambaugh-Yuan placeholder (Cycle 26 FGX
> 2020 explicit cite); composite mispricing scoring literature
> continuity 4. zincir (Piotroski F-Score → Mohanram G-Score →
> Stambaugh-Yuan MGMT/PERF → JKP 13 theme cluster).

## TL;DR (4 cümle)

Stambaugh-Yuan 2017, **11 anomaly hierarchical clustering** ile **2 composite mispricing factor** önerir: P1 = cluster 1 ranking ortalaması (6 anomaly: net stock issues + composite equity issues + accruals + NOA + asset growth + I/A) ve P2 = cluster 2 ranking ortalaması (5 anomaly: distress + O-score + momentum + gross profitability + ROA); 2×3 sort size × Pi NYSE/AMEX/NASDAQ 20th/80th percentile breakpoints (FF15 NYSE 30/70'ten DEPARTURE) UMO1 + UMO2 factor portfolios. **4-factor model (MKT + SMB + UMO1 + UMO2)** HXZ 2015 q-factor + FF15'i outperform — 11 anomaly + larger 73 anomaly (HXZ 2015a/b) set'inde. **Modified SMB methodology**: middle-group only (avoiding mispricing extremes) → 46 bps/month vs 25 bps FF SMB (**~2x small-firm premium**). **Mispricing interpretation evidence**: long-short factor betas Cluster 1 UMO1 t=6.09-18.12 sig + cross-cluster insig; short-leg betas larger (-0.46 vs 0.20 cluster 1; -0.49 vs 0.30 cluster 2); **Baker-Wurgler sentiment predicts factors** (short legs especially t≈-2.06) consistent with arbitrage asymmetry.

## Tek Cümle Tezi

> Anomaly returns mispricing reflektör + mispricing common components have (sentiment); 11 anomaly clustering + averaging within clusters two composite mispricing factor (UMO1=MGMT + UMO2=PERF) elde eder ve standalone factor approaches (FF15, HXZ 2015) outperform.

## Ortaya Konan Sinyal/Faktör

- **UMO1** (paper terminology) = **MGMT** (subsequent literature) — Cluster 1 management-related composite mispricing factor
- **UMO2** (paper terminology) = **PERF** (subsequent literature) — Cluster 2 performance-related composite mispricing factor
- Linki: [[factors/MGMT]] yeni (Cycle 39) + [[factors/PERF]] yeni (Cycle 39)
- Modified SMB: paper's own SMB version (46 bps/month vs 25 bps FF SMB) — middle-group avoidance methodology

## Empirik Sonuçlar (sayılarla)

### Sample [Section 2.1, s.4-5]

| Item | Spec |
|------|------|
| Period | January 1967 - December 2013 monthly (47 yıl) |
| Universe | NYSE + AMEX + NASDAQ; **share price > $5** filter |
| Distress data start | October 1974 |
| ROA data start | November 1971 |
| Accounting lag | ≥4-month gap (annual) + RDQ (quarterly) |

### 11 Anomaly Hierarchical Clustering [Section 2.1, s.4-5]

**Methodology**: Ahn-Conrad-Dittmar 2009 + Ward 1963; correlation matrix of FF3-residuals (Stambaugh 1997 MLE for heterogeneous start dates).

| Cluster | Anomaly | Methodology Origin |
|---------|---------|---------------------|
| **1 (MGMT)** | Net stock issues | Daniel-Titman 2006; Pontiff-Woodgate 2008 |
| 1 | Composite equity issues | Daniel-Titman 2006 |
| 1 | Accruals | [[papers/sloan1996_accruals_anomaly]] |
| 1 | Net operating assets | Hirshleifer-Hou-Teoh-Zhang 2004 |
| 1 | Asset growth | [[papers/cooper_gulen_ion2018_asset_growth_factor_models]] CGS 2008 |
| 1 | Investment-to-assets | Cooper-Gulen-Schill 2008; FF 2008 |
| **2 (PERF)** | Distress | Campbell-Hilscher-Szilagyi 2008 |
| 2 | O-score | Ohlson 1980 (Tier 2 #32) |
| 2 | Momentum | Jegadeesh-Titman 1993; [[factors/UMD]] |
| 2 | Gross profitability | [[papers/novy_marx_2013_gross_profitability]] |
| 2 | Return on assets | Fama-French 2006; [[factors/ROE]] paralel |

### Composite Score Construction [Section 2.1, s.5-6]

**P1, P2 formülasyonu**:
- Each month, stock has rankings on each anomaly variable (1=lowest expected return / 100=highest)
- P1 = average ranking across 6 cluster-1 anomalies (using available measures)
- P2 = average ranking across 5 cluster-2 anomalies

**Factor Portfolio Construction** [s.5-6]:
- **2×3 sort**: size × Pi NYSE/AMEX/NASDAQ **20th/80th percentile** breakpoints (FF15 NYSE 30/70'ten DEPARTURE; "relative mispricing in cross-section likely property of extremes")
- 4 portfolios per factor (small/big × low-Pi/high-Pi)
- **UMOi** = avg(2 small low-Pi + 2 big low-Pi) − avg(2 small high-Pi + 2 big high-Pi)
- Underpriced (low Pi) minus Overpriced (high Pi) value-weighted

### Modified SMB [Section 2.2, s.6-7]

**Methodology farkı FF93**:
- Paper SMB: stocks **not used** in mispricing factor sorts (middle-group only avoiding extremes)
- Avoids mispricing-induced biases in size factor (arbitrage asymmetry)

**Premium**:
- Paper SMB: **46 bps/month** (1967-2013)
- FF SMB: 25 bps/month (~2x daha küçük)
- Difference t-stat 3.99 + 4.19 statistically + economically significant
- "Nearly twice the premium of usual estimates"

### Long-Short Factor Betas [Tablo 1]

| Cluster anomaly | UMO1 long-short β t-stat | UMO2 long-short β t-stat |
|------------------|---------------------------|---------------------------|
| **Cluster 1 (6 anomaly)** | t=**6.09 to 18.12** all sig positive ✅ | t mixed signs avg 1.27 mostly insig |
| **Cluster 2 (5 anomaly)** | t mixed signs avg -0.17 insig | t=**5.02 to 24.10** all sig positive ✅ |

**Cross-cluster insignificance** confirms clustering captures common variation within clusters.

### Short-Leg Asymmetry (Mispricing Interpretation) [s.7-8]

| Cluster | Long-leg β avg | Short-leg β avg | Asymmetry |
|---------|-----------------|------------------|-----------|
| 1 (UMO1) | +0.20 | **-0.46** | 2.3x larger |
| 2 (UMO2) | +0.30 | **-0.49** | 1.6x larger |

> **Mispricing interpretation**: arbitrage asymmetry leaves more uncorrected overpricing than underpricing → greater short-leg sensitivity to systematic mispricing.

### Baker-Wurgler Sentiment Predictability [Tablo 2]

| Factor / Leg | Sentiment β t-stat | Interpretation |
|--------------|---------------------|----------------|
| UMO1 (long-short) | sig (paper [s.8]) | Sentiment predicts factor (mispricing-consistent) |
| UMO1 short leg | **t=-2.06** sig | High sentiment → overpricing → low future returns |
| UMO1 long leg | t=-0.98 insig | Long-leg arbitrage asymmetry |
| UMO2 short leg | **t=-2.05** sig | Same pattern |
| UMO2 long leg | t=-1.29 insig | — |
| **Paper SMB** (modified) | t=**-1.60** insig | Modified SMB avoids mispricing — sentiment-immune |
| **FF SMB** | t=**-2.31** sig | FF SMB has mispricing contamination |

### 4-Factor Model Performance [Section 3, s.10+]

| Comparison | Stambaugh-Yuan 4F vs alternatives |
|------------|-------------------------------------|
| 11 anomaly (own set) | **outperforms** HXZ4 + FF5 |
| 73 anomaly (HXZ 2015a/b set) | **outperforms** HXZ4 + FF5 |
| 3-factor alternative (single composite) | **outperforms** FF3 (book-to-market replaced) |

### Single Composite Mispricing Factor [Section 4]

3-factor model (MKT + paper-SMB + single composite avg-11-anomaly) → outperforms FF3 (B/M replacement); F-Score/G-Score binary composite paradigmasının continuous evolution.

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Composite mispricing scoring P1+P2 + 4-factor model factor portfolio formal tanımı + 2×3 sort (FF15 paterni paralel ama 20/80 breakpoints DEPARTURE); 11 anomaly clustering methodology | ✅ doğrudan |
| **Annual rebalance** | "Each month we sort" [s.5] **monthly resort orijinal**; FF familisi paterni paralel; Q35+Q51+Q57+Q75 paralel sensitivity test partial; annual variant Faz 3 backtest implementation custom | ⚠️ partial monthly orijinal |
| **Large-cap evrene transfer** | NYSE+AMEX+NASDAQ universe + **share price > $5** filter (microcap partial exclusion); NYSE median size breakpoint; **20th/80th NYSE/AMEX/NASDAQ percentile breakpoints DEPARTURE FF15** "relative mispricing in cross-section likely property of extremes"; large-cap-only ayrı test direct yok ama modified SMB middle-group methodology mispricing-aware (Cycle 37 FF 2008 Q14 ANCHOR cross-evidence partial) | ⚠️ partial mispricing-aware |
| **NDX intangibles / growth firms** | Compustat traditional accounting; 11 anomaly traditional factor library; intangibles-aware genişletme YOK; F bloğu 4-katmanlı methodology paralel değil | ❌ uyumsuz traditional accounting (Q23 + Q73 + Q79 + Q82 paralel) |

**Strateji tasarımına net implikasyon**:

Stambaugh-Yuan [[strategies/sp500_v1]] §2.1 + [[strategies/nasdaq100_v1]] §2.1 **composite mispricing scoring methodology origin paper**: (1) **MGMT + PERF cluster paradigm** sp500_v1 + nasdaq100_v1 multi-theme allocation framework (JKP 2023 13 theme cluster paterni paralel evolution; Stambaugh-Yuan 2-cluster → JKP 13-theme genişletme); (2) **Sentiment-aware short-leg asymmetry** wiki **long-only strategy** kararı için kritik kanıt (sp500_v1 + nasdaq100_v1 long-only top 30-50 stocks; short legs sentiment-driven mispricing-prone CLAUDE.md §1 long-only hedef); (3) **20/80 percentile breakpoints DEPARTURE FF15** Faz 3 backtest implementation methodology choice sensitivity ([[methodology/backtest_spec]] §1.3 üç alternative weighting + Stambaugh-Yuan 20/80 breakpoint paralel); (4) **Modified SMB ~2x premium**: vanilla SMB Q11 fully-answered ASTERISK (Cycle 12+22) sertleştirme kanıt (mispricing contamination FF SMB); (5) Q82 yeni NDX-spesifik MGMT+PERF kalibrasyonu (FAANG R&D-intensive composite anomalies Q56+Q73+Q79 paralel).

## Limitler ve Caveats

- **Sample 1967-2013** post-2013 11 yıl out-of-sample (FAANG era 2014-2024); JKP 2023 partial 2014-2020 6 yıl modern coverage (Q81 yeni)
- **Monthly rebalance orijinal**: P1+P2 each-month resort; UMOi monthly resort; wiki annual frequency hedef için Q35+Q51+Q57+Q75 paralel sensitivity (Q81 yeni)
- **Share price > $5 filter** microcap partial exclusion ama complete exclusion değil (Cycle 37 FF 2008 + Cycle 38 Ball-GLN All-but-microcaps panel methodology farklı)
- **20/80 percentile breakpoints DEPARTURE**: paper [s.5-6] explicit "modifications reflect notion that relative mispricing in the cross-section is likely to be more a property of the extremes than of the middle"; FF15 NYSE 30/70 paterninden tek-faktör paper bazında ayrılma (subsequent literature paralel methodology choice)
- **11 anomaly fixed set**: paper [s.3] "use this previously specified set [SYY 2012/2014/2015] to alleviate concerns that a different set was chosen to yield especially favorable results"; ama 11-anomaly seçimi Stambaugh-Yu-Yuan 2012 dönemine özgü, post-2013 anomaly evolution sample dışı
- **Investor sentiment exogenous predictor**: Baker-Wurgler 2006 sentiment index dışsal predictor; sentiment-driven mispricing interpretation explicit ama [[concepts/discount_rates]] Cochrane mathematical equivalence framework dışı (paper [s.2] explicit acknowledgment "factor models can be useful whether expected returns reflect risk or mispricing"; "no clean distinction between mispricing and risk compensation")
- **Cluster labels MGMT/PERF post-paper**: paper terminology UMO1/UMO2 ("underpriced minus overpriced"); subsequent literature commonly uses MGMT (cluster 1 management-related: equity issuance + accounting choices + investment) + PERF (cluster 2 performance-related: distress + momentum + profitability) labels
- **Mispricing-aware methodology + traditional accounting**: 11 anomaly traditional accounting; intangibles-aware genişletme YOK F bloğu 4-katmanlı NDX strategy ortogonal methodology

## İlgili Sayfalar

### Composite Mispricing Scoring Literature Continuity (4-Paper × 17-Yıl)

| Halka | Paper | Methodology | Cycle |
|-------|-------|-------------|-------|
| 1 (origin) | [[papers/piotroski2000_f_score]] | Binary 9-component (high-BM evren) | 5 |
| 2 | [[papers/mohanram2005_g_score]] | Binary 8-component industry-median (low-BM evren) | 6 |
| **3** ⭐ | **[[papers/stambaugh_yuan_2017_mispricing_factors]]** | **Continuous composite 11-anomaly clustering 2-factor** | **39 (BU)** |
| 4 | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] | Bayesian Empirical Bayes hierarchical 13 theme cluster | 27 |

### FGX Cross-Test (Cycle 26 placeholder → live)
- [[papers/feng_giglio_xiu_2020_factor_zoo]] — FGX 150-factor library içinde Stambaugh-Yuan UMO1+UMO2 mispricing factors test (Cycle 26 placeholder formal cross-link); Q55+Q7 fully-answered Cycle 26 sertleştirme

### JKP Methodology Evolution
- [[papers/jensen_kelly_pedersen_2023_replication_crisis]] — JKP 13 theme cluster taxonomy Stambaugh-Yuan 2-cluster paterni paralel evolution (clustering methodology + factor inclusion via clustering)

### Sloan Zinciri + 11 Anomaly İçinde
- [[papers/sloan1996_accruals_anomaly]] — Cluster 1 accruals anomaly origin
- [[papers/cooper_gulen_ion2018_asset_growth_factor_models]] — Cluster 1 asset growth + I/A; CGS 2008 origin
- [[papers/novy_marx_2013_gross_profitability]] — Cluster 2 gross profitability anchor

### q-Factor Model Comparison
- [[papers/hou_xue_zhang_2015_q_factor]] — Stambaugh-Yuan 4F outperforms HXZ4; q-factor I/A + ROE direct comparison (paper [s.10+] Section 3)
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] — 73 anomaly HXZ 2015a/b set Stambaugh-Yuan 4F validation

### FF Ailesi Comparison
- [[papers/famafrench1993_three_factor]] — FF3 baseline (B/M replaced by single composite mispricing 3F outperforms FF3)
- [[papers/famafrench2015_five_factor]] — FF5 vs Stambaugh-Yuan 4F outperforms
- [[papers/fama_french_2008_dissecting_anomalies]] (Cycle 37) — size-partition methodology cross-evidence

### Composite Scoring Paradigm
- [[papers/piotroski2000_f_score]] — F-Score 9-component binary (high-BM evren)
- [[papers/mohanram2005_g_score]] — G-Score 8-component industry-median (low-BM evren)
- [[papers/beneish_1999_m_score]] — M-Score forensic composite
- [[papers/asness_frazzini_pedersen_2019_qmj]] — QMJ 4-dimension composite z-score
- [[papers/li_mohanram2019_quality_value]] — F+G+V/P+PEG combined paradigm
- [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] — Cop subsumes accruals (Stambaugh-Yuan accruals dahil cluster 1)

### Factor Entities
- [[factors/MGMT]] yeni (Cycle 39) — Cluster 1 management-related composite mispricing factor (UMO1)
- [[factors/PERF]] yeni (Cycle 39) — Cluster 2 performance-related composite mispricing factor (UMO2)
- [[factors/SMB]] — modified SMB Stambaugh-Yuan ~2x premium kanıt + Q11 ASTERISK sertleştirme
- [[factors/Accruals]] + [[factors/Asset_Growth]] + [[factors/CMA]] — cluster 1 alt-bileşenleri
- [[factors/UMD]] + [[factors/Gross_Profitability]] + [[factors/ROE]] — cluster 2 alt-bileşenleri (paralel)

### Concepts
- [[concepts/factor_zoo]] — Stambaugh-Yuan mispricing factor paradigma + clustering methodology
- [[concepts/winner_loser_identification]] — composite mispricing scoring methodology
- [[concepts/fundamental_scoring]] — F-Score/G-Score binary → Stambaugh-Yuan continuous composite evolution
- [[concepts/post_publication_decay]] — McLean-Pontiff cross-cite [s.2] "anomaly profits decline post-publication" Stambaugh-Yuan paterni paralel
- [[concepts/multiple_testing]] — FGX 150-factor library Stambaugh-Yuan validation
- [[concepts/factor_model]] — mispricing factor model vs FF + q-factor paradigm

### Strategy Specs
- [[strategies/sp500_v1]] §2.1 composite scoring paradigm formal cross-link
- [[strategies/nasdaq100_v1]] §2.1 composite scoring paradigm + Q82 NDX-spesifik
- [[methodology/backtest_spec]] §3 üç paralel statistical filter Stambaugh-Yuan composite methodology + §1.3 20/80 breakpoint paterni

## Çelişkiler/Tartışmalar

- **Stambaugh-Yuan 4F vs HXZ4 + FF5**: paper explicit "outperforms"; **çelişki YOK methodology choice** (Stambaugh-Yuan mispricing-based vs HXZ investment-based vs FF risk-factor-based; üç paralel framework Cycle 35 + 27 paterni paralel; wiki taraf tutmaz Cochrane mathematical equivalence)
- **Stambaugh-Yuan vs Ball-GLN Cop**: Ball-GLN [Tablo 8] 4F+Cop=1.67 tangency Sharpe vs Stambaugh-Yuan 4F+UMO1+UMO2 4-factor model paterni; **çelişki değil methodology farkı** (Cop single profitability factor + Stambaugh-Yuan 2-cluster mispricing composite; complementary methodology); Cycle 38 Ball-GLN Cop subsumes Sloan accruals + Stambaugh-Yuan Cluster 1 accruals dahil composite; Sloan zinciri (mispricing/accruals) + Profitability zinciri + Mispricing factor zinciri üç paralel methodology aile
- **Stambaugh-Yuan SMB ~2x premium vs FF SMB**: paper modified SMB methodology (middle-group avoidance); **çelişki değil methodology evrim**; Q11 fully-answered ASTERISK SMB resurrection paterni paralel (Cycle 19 Asness QMJ + Cycle 22 Israel-Moskowitz + Cycle 39 Stambaugh-Yuan üç-paper sertleştirme)
- **Stambaugh-Yuan FGX cross-test**: FGX 2020 [Tablo 1] Stambaugh-Yuan mispricing factors DS LASSO 150-factor library validation; **çelişki YOK** (Cycle 26 Q55+Q7 fully-answered cross-link methodology validation)
- **Stambaugh-Yuan vs JKP 13-theme**: 2-cluster vs 13-theme; **çelişki değil clustering methodology evolution** (Stambaugh-Yuan hierarchical Ward 1963 → JKP Bayesian Empirical Bayes hierarchical methodology evolution; 11 anomaly fixed set vs 153 factor library scope evolution)

## Açık Sorular (Open Questions)

- **Q9** (Beneish + composite score; Cycle 18) — **partial-stronger Cycle 39** (Stambaugh-Yuan composite scoring paradigm cross-evidence; F-Score/G-Score binary → continuous composite evolution)
- **Q55** (Profitability ailesi DS-sig; Cycle 26 fully-answered) — **sertleştirme Cycle 39** (Stambaugh-Yuan FGX validation paralel)
- **Q49** (QMJ 4 dimension hangisi en güçlü) — **partial-stronger Cycle 39** (composite scoring methodology paralel; mispricing dimension QMJ Profitability + Growth + Safety + Payout 4-dim ≠ Stambaugh-Yuan 2-cluster)
- **Q66** (ML methodology factor selection vs frequentist; Cycle 27) — **partial-stronger Cycle 39** (Stambaugh-Yuan hierarchical clustering methodology evolution → JKP Bayesian Empirical Bayes)
- **Q11** (SMB never sig under MT; fully-answered Cycle 12+19+22) — **sertleştirme Cycle 39** (Stambaugh-Yuan modified SMB ~2x premium FF SMB mispricing contamination dokümante; Asness QMJ ASTERISK + Israel-Moskowitz 86-yıl + Stambaugh-Yuan üç-paper sertleştirme)
- **Q81 yeni**: Stambaugh-Yuan 11 anomaly post-2013 11 yıl modern replikasyon (sample 2014+ JKP partial 6 yıl coverage; FAANG era anomaly evolution 11-anomaly fixed set robustness; Faz 3 custom backtest implementation Cycle 41+ hedef)
- **Q82 yeni**: MGMT + PERF NDX-spesifik R&D-intensive firma kalibrasyonu (cluster 1 asset growth + I/A FAANG R&D capitalization YOK traditional; cluster 2 gross profitability + ROA Q56+Q79 paralel; F bloğu 4-katmanlı intangibles-aware composite mispricing factor modification Faz 3 implementation custom; Q56+Q73+Q79+Q82 NDX intangibles dörtlü konsolidasyonu Cycle 40 §11.5 ZORUNLU consolidation pass'de nasdaq100_v1 §6 + known_weaknesses §3 propagation kontrol kullanıcı request)

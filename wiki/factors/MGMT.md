---
type: factor
name: MGMT
alias: UMO1
opened: 2026-05-02
phase: faz_3_cycle_39
category: composite_mispricing
direction: long_low_minus_high  # underpriced (low Pi) minus overpriced (high Pi)
data_lag_required: "≥4-month gap (annual) + RDQ (quarterly); monthly resort"
rebalance_frequency: monthly
universe_tested: ["NYSE+AMEX+NASDAQ price>$5 1967-2013 Compustat"]
---

# MGMT — Management-Related Composite Mispricing Factor (Stambaugh-Yuan UMO1)

> 📝 **Cycle 39 yeni factor entity (Composite mispricing scoring 3.
> halka).** [[papers/stambaugh_yuan_2017_mispricing_factors]] paper
> terminology UMO1 ("underpriced minus overpriced" cluster 1);
> subsequent literature commonly calls **MGMT** (management-related).
> Cycle 35 q-factor I/A + ROE + Cycle 38 Cop paterni paralel açma
> kararı.

## Tanım (matematiksel)

```
P1_t = avg(rank(stock i; anomaly j ∈ Cluster 1; month t))
       6 anomaly: Net Stock Issues + Composite Equity Issues + Accruals
                  + Net Operating Assets + Asset Growth + Investment-to-Assets

UMO1_t = avg(small low-P1 + big low-P1 returns) - avg(small high-P1 + big high-P1 returns)
       2×3 sort size × P1; NYSE+AMEX+NASDAQ 20th/80th percentile P1 breakpoints
```

- **Composite ranking**: each month, stock has ranking on each anomaly variable; P1 = average ranking across 6 cluster-1 anomalies (using available measures)
- **2×3 sort**: NYSE median size × P1 20th/80th percentile NYSE+AMEX+NASDAQ breakpoints (FF15 NYSE 30/70'ten DEPARTURE)
- **VW returns**; share price > $5 filter; monthly resort

## Origin

- **Paper-spesifik origin**: [[papers/stambaugh_yuan_2017_mispricing_factors]] (Cycle 39 BU; 11 anomaly clustering origin)
- **Literatür hattı kökü** (Origin attribution dual pattern Cycle 9+15+23+35+38 paterni paralel):
  - Stambaugh-Yu-Yuan 2012/2014/2015 — 11 anomaly previously analyzed (mispricing literature)
  - [[papers/sloan1996_accruals_anomaly]] — Sloan accruals (cluster 1 dahil)
  - [[papers/cooper_gulen_ion2018_asset_growth_factor_models]] — CGS 2008 asset growth + I/A (cluster 1 dahil)
  - Daniel-Titman 2006; Pontiff-Woodgate 2008 — net stock issues + composite equity issues
  - Hirshleifer-Hou-Teoh-Zhang 2004 — net operating assets
  - Ahn-Conrad-Dittmar 2009 + Ward 1963 — hierarchical clustering methodology

## Cluster 1 Anomalies (MGMT — Management Decisions)

| Anomaly | Methodology | Wiki cross-link |
|---------|-------------|------------------|
| Net Stock Issues | Daniel-Titman 2006; Pontiff-Woodgate 2008 (Tier 3 #49) | [[factors/SMB]] paterni paralel SMB Q11 ASTERISK |
| Composite Equity Issues | Daniel-Titman 2006 | (yeni issuance composite) |
| Accruals | [[papers/sloan1996_accruals_anomaly]] Sloan 1996 | [[factors/Accruals]] |
| Net Operating Assets | Hirshleifer-Hou-Teoh-Zhang 2004 | (NOA bloated balance sheet anomaly) |
| Asset Growth | [[papers/cooper_gulen_ion2018_asset_growth_factor_models]] CGS 2008 | [[factors/Asset_Growth]] + [[factors/CMA]] |
| Investment-to-Assets | CGS 2008; FF 2008 | [[factors/I_A]] (HXZ 2015) + [[factors/CMA]] |

> **Common theme**: management decisions affect anomalies (issuance + capital allocation + accounting choices).

## Factor Construction (Stambaugh-Yuan Methodology)

[Section 2.1, s.5-6]:

**Step 1 — Composite ranking**: P1_t = avg ranking across 6 cluster-1 anomalies
**Step 2 — 2×3 sort**: size (NYSE median) × P1 (20th/80th percentile NYSE+AMEX+NASDAQ)
**Step 3 — Factor**: UMO1_t = avg(2 low-P1 portfolios) − avg(2 high-P1 portfolios) value-weighted
**Step 4 — Universe filter**: NYSE+AMEX+NASDAQ price>$5; ex-microcap partial

## Reported Performance Across Studies

| Study | Period | Headline | Notes |
|-------|--------|----------|-------|
| Stambaugh-Yuan 2017 [Tablo 1] | 1967-2013 | Cluster 1 anomalies UMO1 long-short β t=**6.09 to 18.12** all sig | All 6 anomalies sig on UMO1 |
| Stambaugh-Yuan 2017 [Tablo 1] | 1967-2013 | Cluster 1 anomalies UMO2 t avg 1.27 mostly insig | Cross-cluster insignificance confirms clustering |
| Stambaugh-Yuan 2017 [Tablo 1] | 1967-2013 | Short-leg β avg -0.46 vs long-leg +0.20 (2.3x) | Arbitrage asymmetry mispricing-consistent |
| Stambaugh-Yuan 2017 [Tablo 2] | 1967-2013 | Baker-Wurgler sentiment short-leg t=**-2.06** sig | Sentiment-predictability mispricing-consistent |
| Stambaugh-Yuan 2017 [Section 3] | 1967-2013 | 4F (MKT+SMB+UMO1+UMO2) outperforms HXZ4 + FF5 | 11 anomaly + 73 anomaly (HXZ 2015a/b) sets |
| FGX 2020 | 1976-2017 | UMO1+UMO2 DS LASSO 150-factor library cross-test | Q55+Q7 fully-answered Cycle 26 |
| JKP 2023 | 1926-2020 US Bayesian | 13 theme cluster paterni evolution Stambaugh-Yuan 2-cluster origin | Clustering methodology continuity |

## MGMT (UMO1) vs Tek-Anomaly Factor Karşılaştırma

| Boyut | UMO1 (Stambaugh-Yuan) | Tek-anomaly (CMA, I_A, Accruals, Asset_Growth) |
|-------|------------------------|--------------------------------------------------|
| **Form** | Composite 6-anomaly avg ranking | Single anomaly factor |
| **Cluster scope** | Cluster 1 (management decisions) | Tek dimension |
| **Methodology** | 2×3 sort 20/80 NYSE+AMEX+NASDAQ percentile | 2×3 sort 30/70 NYSE percentile (FF15) |
| **Mispricing interpretation** | Explicit (sentiment-aware short-leg asymmetry) | Implicit (single anomaly hipotez) |
| **Wiki implication** | Composite mispricing 4. zincir 3. halka | Bireysel factor exposure proxy |

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

- **S&P 500 strategy implication** (sp500_v1 §2.1 multi-theme allocation):
  - MGMT cluster 1 paterni: net issues + accruals + asset growth + I/A composite tema (Investment + Accruals* themes JKP 2023 paterni paralel)
  - sp500_v1 §2.1 Path B Profitability theme + Path D Investment* theme + §6 madde 1 Sloan zinciri MGMT cluster paterni paralel (Cop subsumes accruals Cycle 38 + UMO1 cluster 1 accruals dahil composite)
  - Long-only methodology (CLAUDE.md §1) Stambaugh-Yuan short-leg sentiment-driven mispricing kanıt (uzun bacak only stratejisi mispricing exposure low — long-only tercih sertleştirme)

- **NDX strategy implication** (nasdaq100_v1 §2.1 + §2.5 F bloğu 4-katmanlı):
  - **Q82 yeni NDX-spesifik kritik caveat**: cluster 1 asset growth + I/A FAANG R&D capitalization YOK traditional accounting → R&D-intensive firmalarda yapay yüksek I/A; F bloğu paralel intangibles-aware MGMT modification Faz 3 implementation custom (Q56+Q73+Q79+Q82 NDX intangibles dörtlü konsolidasyonu)
  - Q82 Cycle 40 §11.5 ZORUNLU consolidation pass'de nasdaq100_v1 §6 + known_weaknesses §3 propagation kontrol (Q75 propagation pattern paralel)

## Implementation Notes

**Required data**:
- Compustat annual: items for 6 anomaly variables (net stock issues + composite equity issues + accruals + NOA + asset growth + I/A)
- ≥4-month gap (annual) + RDQ (quarterly) standart accounting lag
- Monthly resort

**Portfolio construction**:
- 2×3 sort size × P1 NYSE+AMEX+NASDAQ 20th/80th percentile
- VW returns; share price > $5 filter
- Modified SMB methodology paralel (middle-group avoidance)

## Bu Faktörün Yumuşak Karnı

- **Monthly resort orijinal**: wiki annual frequency hedef için Q35+Q51+Q57+Q75+Q81 paralel sensitivity test
- **20/80 percentile DEPARTURE FF15**: methodology choice sensitivity test gerekli (FF15 NYSE 30/70 vs SY 20/80 NYSE+AMEX+NASDAQ); [[methodology/backtest_spec]] §1.3 üç alternative weighting ek katman
- **11-anomaly fixed set Stambaugh-Yu-Yuan 2012-spesifik**: post-2013 anomaly evolution sample dışı (Q81 yeni post-2013 modern replikasyon)
- **Traditional accounting**: 6 cluster-1 anomalies Compustat traditional; intangibles-aware genişletme YOK; F bloğu 4-katmanlı NDX strategy ortogonal methodology (Q82 yeni NDX-spesifik)
- **Sentiment-driven mispricing dependency**: factor returns Baker-Wurgler sentiment exogenous predictor; sentiment regime-dependent (post-2013 sentiment dynamics farklı olabilir; Q81 paralel)
- **Share price > $5 filter** microcap partial exclusion ama complete değil (Cycle 37 FF 2008 + Cycle 38 Ball-GLN All-but-microcaps panel methodology farkı)

## İlgili
- [[papers/stambaugh_yuan_2017_mispricing_factors]] — origin paper (Cycle 39)
- [[factors/PERF]] — sister factor (UMO2; Cluster 2 performance-related)
- [[factors/Accruals]] + [[factors/Asset_Growth]] + [[factors/CMA]] + [[factors/I_A]] — cluster 1 alt-bileşenleri
- [[factors/SMB]] — modified SMB Stambaugh-Yuan ~2x premium kanıt
- [[concepts/factor_zoo]] — composite mispricing factor paradigma
- [[concepts/winner_loser_identification]] — composite mispricing scoring methodology
- [[concepts/fundamental_scoring]] — F-Score/G-Score binary → Stambaugh-Yuan continuous composite evolution
- [[concepts/post_publication_decay]] — McLean-Pontiff cross-cite + sentiment-driven mispricing
- [[concepts/multiple_testing]] — FGX 150-factor library Stambaugh-Yuan validation
- [[strategies/sp500_v1]] §2.1 multi-theme allocation
- [[strategies/nasdaq100_v1]] §2.1 + Q82 NDX-spesifik kalibrasyonu
- [[methodology/backtest_spec]] §3 statistical filter + §1.3 20/80 breakpoint methodology choice

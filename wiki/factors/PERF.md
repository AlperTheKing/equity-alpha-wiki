---
type: factor
name: PERF
alias: UMO2
opened: 2026-05-02
phase: faz_3_cycle_39
category: composite_mispricing
direction: long_low_minus_high  # underpriced (low Pi) minus overpriced (high Pi)
data_lag_required: "≥4-month gap (annual) + RDQ (quarterly); monthly resort"
rebalance_frequency: monthly
universe_tested: ["NYSE+AMEX+NASDAQ price>$5 1967-2013 Compustat (distress 1974+; ROA 1971+)"]
---

# PERF — Performance-Related Composite Mispricing Factor (Stambaugh-Yuan UMO2)

> 📝 **Cycle 39 yeni factor entity (Composite mispricing scoring 3.
> halka).** [[papers/stambaugh_yuan_2017_mispricing_factors]] paper
> terminology UMO2 ("underpriced minus overpriced" cluster 2);
> subsequent literature commonly calls **PERF** (performance-related).
> Sister factor [[factors/MGMT]] (cluster 1).

## Tanım (matematiksel)

```
P2_t = avg(rank(stock i; anomaly j ∈ Cluster 2; month t))
       5 anomaly: Distress + O-Score + Momentum + Gross Profitability + Return on Assets

UMO2_t = avg(small low-P2 + big low-P2 returns) - avg(small high-P2 + big high-P2 returns)
       2×3 sort size × P2; NYSE+AMEX+NASDAQ 20th/80th percentile P2 breakpoints
```

- **Composite ranking**: each month, stock has ranking on each anomaly variable; P2 = average ranking across 5 cluster-2 anomalies
- **2×3 sort**: NYSE median size × P2 20th/80th percentile NYSE+AMEX+NASDAQ breakpoints (FF15 NYSE 30/70'ten DEPARTURE)
- **VW returns**; share price > $5 filter; monthly resort

## Origin

- **Paper-spesifik origin**: [[papers/stambaugh_yuan_2017_mispricing_factors]] (Cycle 39 BU; 11 anomaly clustering origin)
- **Literatür hattı kökü** (Origin attribution dual pattern Cycle 9+15+23+35+38 paterni paralel):
  - Stambaugh-Yu-Yuan 2012/2014/2015 — 11 anomaly previously analyzed
  - Bernard-Thomas 1989/1990 — PEAD (post-earnings-announcement drift; momentum + ROA paralel)
  - Jegadeesh-Titman 1993 — momentum origin
  - [[papers/novy_marx_2013_gross_profitability]] — GP/A origin (Profitability zinciri 1. halka)
  - Campbell-Hilscher-Szilagyi 2008 — distress (Tier 2 #33)
  - Ohlson 1980 — O-score (Tier 2 #32)
  - Ahn-Conrad-Dittmar 2009 + Ward 1963 — hierarchical clustering methodology

## Cluster 2 Anomalies (PERF — Performance Indicators)

| Anomaly | Methodology | Wiki cross-link |
|---------|-------------|------------------|
| Distress | Campbell-Hilscher-Szilagyi 2008 (Tier 2 #33; failure probability) | (Cycle 35 HXZ q-factor distress subsumption Q15 fully-answered) |
| O-Score | Ohlson 1980 (Tier 2 #32; bankruptcy probability) | (Cycle 18 forensic context M-Score paralel) |
| Momentum | Jegadeesh-Titman 1993; [[papers/carhart1997_four_factor]] | [[factors/UMD]] |
| Gross Profitability | [[papers/novy_marx_2013_gross_profitability]] | [[factors/Gross_Profitability]] |
| Return on Assets | Fama-French 2006; HXZ 2015 [[factors/ROE]] paralel | [[factors/ROE]] (HXZ ROE = IBQ/BE; paper ROA traditional) |

> **Common theme**: performance indicators (financial health + earnings dynamics + profitability metrics).

## Factor Construction (Stambaugh-Yuan Methodology)

[Section 2.1, s.5-6]: aynı methodology UMO1/MGMT paterni (2×3 sort + 20/80 NYSE+AMEX+NASDAQ breakpoints + price>$5 + VW + monthly resort) ama Cluster 2 anomalies P2 composite ranking.

## Reported Performance Across Studies

| Study | Period | Headline | Notes |
|-------|--------|----------|-------|
| Stambaugh-Yuan 2017 [Tablo 1] | 1967-2013 | Cluster 2 anomalies UMO2 long-short β t=**5.02 to 24.10** all sig | All 5 anomalies sig on UMO2 |
| Stambaugh-Yuan 2017 [Tablo 1] | 1967-2013 | Cluster 2 anomalies UMO1 t avg -0.17 mostly insig | Cross-cluster insignificance confirms clustering |
| Stambaugh-Yuan 2017 [Tablo 1] | 1967-2013 | Short-leg β avg -0.49 vs long-leg +0.30 (1.6x) | Arbitrage asymmetry mispricing-consistent |
| Stambaugh-Yuan 2017 [Tablo 2] | 1967-2013 | Baker-Wurgler sentiment short-leg t=**-2.05** sig | Sentiment-predictability mispricing-consistent |
| Stambaugh-Yuan 2017 [Section 3] | 1967-2013 | 4F (MKT+SMB+UMO1+UMO2) outperforms HXZ4 + FF5 | 11 anomaly + 73 anomaly sets |
| FGX 2020 | 1976-2017 | UMO1+UMO2 DS LASSO 150-factor library cross-test | Q55+Q7 fully-answered Cycle 26 |
| JKP 2023 | 1926-2020 US Bayesian | Profitability + Quality theme paterni Stambaugh-Yuan cluster 2 paralel | Clustering methodology continuity |

## PERF (UMO2) vs Tek-Anomaly Factor Karşılaştırma

| Boyut | UMO2 (Stambaugh-Yuan) | Tek-anomaly (UMD, GP/A, ROE, RMW) |
|-------|------------------------|-------------------------------------|
| **Form** | Composite 5-anomaly avg ranking | Single anomaly factor |
| **Cluster scope** | Cluster 2 (performance indicators) | Tek dimension |
| **Profitability zinciri intersection** | GP/A + ROA dahil (Cluster 2 5 anomaly içinde 2 profitability) | Profitability zinciri 4-paper × 7-yıl tek faktör |
| **Methodology** | 2×3 sort 20/80 NYSE+AMEX+NASDAQ percentile | 2×3 sort 30/70 NYSE percentile (FF15) |
| **Mispricing interpretation** | Explicit sentiment-aware | Implicit |
| **Wiki implication** | Composite mispricing 3. halka cluster 2 | Bireysel factor exposure proxy |

## PERF vs Profitability Zinciri Karşılaştırma

| Boyut | PERF (Stambaugh-Yuan UMO2) | Profitability zinciri 4. halka Cop (Ball-GLN 2016) |
|-------|------------------------------|-----------------------------------------------------|
| **Profitability zinciri rolü** | Cluster 2 içinde 2 profitability anomaly (GP/A + ROA) | 4. halka standalone Cop |
| **Distress + Momentum dahil** | ✅ (cluster 2 5-anomaly içinde) | ❌ (Cop pure profitability) |
| **Subsumption** | Cluster 2 anomalies UMO2 sig (Tablo 1) | Cop subsumes accruals + wins horse race vs Ope (Tablo 2) |
| **Methodology farkı** | Composite cluster | Single signal cash-based |

> **Wiki implication**: PERF + Cop **complementary methodology** (multi-anomaly composite vs single signal cash-based); sp500_v1 + nasdaq100_v1 §2.1 Path B Profitability theme her iki anchor (Cycle 38 Cop + Cycle 39 PERF Cluster 2 GP/A + ROA dahil); Profitability zinciri + Composite mispricing zinciri **iki paralel methodology aile** Profitability dimension'da kesişim.

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

- **S&P 500 strategy implication** (sp500_v1 §2.1 multi-theme allocation):
  - PERF cluster 2: distress + O-score + momentum + GP/A + ROA (Quality + Momentum + Profitability themes JKP 2023 paterni paralel)
  - sp500_v1 §2.1 Path B Profitability theme + Path E Momentum theme PERF cluster paterni paralel
  - Long-only methodology kararı PERF short-leg sentiment-driven mispricing kanıt sertleştirme

- **NDX strategy implication** (nasdaq100_v1 §2.1 + §2.5 F bloğu 4-katmanlı):
  - **Q82 yeni NDX-spesifik**: cluster 2 GP/A + ROA FAANG R&D giderleştirme yapay düşük profitability (Q56 + Q79 paralel; Cop SG&A R&D dahil); F bloğu paralel intangibles-aware PERF modification Faz 3 implementation custom
  - **Q56+Q73+Q79+Q82 NDX intangibles dörtlü konsolidasyonu** Cycle 40 §11.5 ZORUNLU consolidation pass'de nasdaq100_v1 §6 + known_weaknesses §3 propagation kontrol (Q75 propagation pattern paralel kullanıcı request)

## Implementation Notes

**Required data**:
- Compustat annual + quarterly: items for 5 anomaly variables (distress + O-score + momentum + GP/A + ROA)
- Distress data start October 1974; ROA data start November 1971
- Monthly resort

**Portfolio construction**: MGMT methodology paterni paralel.

## Bu Faktörün Yumuşak Karnı

- **Monthly resort orijinal**: wiki annual frequency hedef için Q35+Q51+Q57+Q75+Q81 paralel sensitivity test
- **20/80 percentile DEPARTURE FF15**: methodology choice sensitivity test gerekli
- **5-anomaly fixed set**: post-2013 anomaly evolution sample dışı (Q81 yeni post-2013 modern replikasyon)
- **Traditional accounting + R&D giderleştirme**: GP/A + ROA Compustat traditional; FAANG R&D capitalization YOK; Q82 yeni NDX-spesifik (Q56+Q79 paralel)
- **Sentiment-driven mispricing dependency**: Baker-Wurgler sentiment exogenous predictor; regime-dependent
- **Distress + O-score wiki ingest YOK** (Tier 2 #32+33 backlog); cluster 2 dahili anomaly methodology direct empirik validation eksik

## İlgili
- [[papers/stambaugh_yuan_2017_mispricing_factors]] — origin paper (Cycle 39)
- [[factors/MGMT]] — sister factor (UMO1; Cluster 1 management-related)
- [[factors/UMD]] + [[factors/Gross_Profitability]] + [[factors/ROE]] — cluster 2 alt-bileşenleri (paralel)
- [[factors/Cop]] — Profitability zinciri 4. halka complementary (Cycle 38)
- [[factors/QMJ]] — 4-dimension composite (Cluster 2 GP/A + ROA paralel)
- [[concepts/factor_zoo]] — composite mispricing factor paradigma
- [[concepts/winner_loser_identification]] — composite mispricing scoring methodology
- [[concepts/fundamental_scoring]] — F-Score/G-Score binary → Stambaugh-Yuan continuous composite evolution
- [[concepts/earnings_quality]] — Sloan zinciri + Profitability zinciri + Composite mispricing zinciri üçlü
- [[concepts/post_publication_decay]] — McLean-Pontiff cross-cite + sentiment-driven mispricing
- [[concepts/multiple_testing]] — FGX 150-factor library Stambaugh-Yuan validation
- [[strategies/sp500_v1]] §2.1 multi-theme allocation
- [[strategies/nasdaq100_v1]] §2.1 + Q82 NDX-spesifik kalibrasyonu
- [[methodology/backtest_spec]] §3 statistical filter + §1.3 20/80 breakpoint methodology choice

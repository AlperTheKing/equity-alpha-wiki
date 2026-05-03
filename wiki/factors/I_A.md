---
type: factor
name: I_A
opened: 2026-05-02
phase: faz_3_cycle_35
category: investment
direction: long_low_minus_high
data_lag_required: "annual fiscal year-end + 4-month lag (June rebalance)"
rebalance_frequency: annual
universe_tested: ["CRSP+Compustat 1972-2011 NYSE-Amex-NASDAQ ex-financials ex-negative book equity"]
---

# I/A — Investment Factor (HXZ 2015 q-Factor Model)

> 📝 **Cycle 35 yeni factor entity.** [[papers/hou_xue_zhang_2015_q_factor]]
> q-factor model 4 faktöründen biri (MKT + ME + **I/A** + ROE).
> [[factors/CMA]] ile methodology farkı + horse race dokümantasyonu
> için ayrı entity (FF15 CMA = sort decile spread; HXZ I/A = q-theoretical
> 2×3×3 implementation).

## Tanım (matematiksel)

```
I/A_i = (AT_t - AT_{t-1}) / AT_{t-1}
```

- **AT** = Total Assets (Compustat annual item AT)
- **Annual change in total assets** divided by lagged total assets
- "Most comprehensive measure of investment" [HXZ 2015 s.4-5]
- Cooper-Gulen-Schill 2008 asset growth ölçüsü ile aynı tanım ([[factors/Asset_Growth]] CGS measure paralel)

## Origin

- **Paper-spesifik origin**: [[papers/hou_xue_zhang_2015_q_factor]] (Cycle 35; q-factor model 4-factor formal tanımı)
- **Literatür hattı kökü** (Origin attribution dual pattern Cycle 9+15+23 paterni paralel):
  - Cochrane 1991 [[concepts/discount_rates]] — investment-q theory; investment first-order condition theoretical foundation
  - Berk-Green-Naik 1999 — real options model; expansion options vs assets in place
  - Liu-Whited-Zhang 2009 — characteristics-expected return relations structural estimation
  - **[[papers/fama_french_2008_dissecting_anomalies]]** (Cycle 37 ✓ Faz 3 seçici ingest #2 anchor) — investment effect strong in microcaps absent in big stocks; HXZ 2015 [s.7] direct cross-cite; q-factor size-controlled motivation literatür hattı kökü
  - Cooper-Gulen-Schill 2008 [[papers/cooper_gulen_ion2018_asset_growth_factor_models]] (Cycle 10) — asset growth anomaly origin
  - Fairfield-Whisenant-Yohn 2003 + Anderson-Garcia-Feijoo 2006 + Titman-Wei-Xie 2004 — investment-return negative relation literature

## Factor Construction (HXZ 2015 Methodology)

[HXZ 2015 Section 2 + Eq.(3)]:

**2×3×3 triple sort**: size × A/A × ROE NYSE breakpoints VW

```
r_I/A = (1/6) × Σ p_i1k - (1/6) × Σ p_i3k
       i,k                  i,k
```

- **p_i1k** = portfolio in low-A/A group (j=1) across 2 size × 3 ROE = 6 portfolios
- **p_i3k** = portfolio in high-A/A group (j=3) across 2 size × 3 ROE = 6 portfolios
- **Annual sort**: June each year t; A/A based on fiscal year ending in calendar year t-1
- **NYSE 30/40/30 breakpoints**: low 30% / mid 40% / high 30%

## Reported Performance Across Studies

| Study | Period | Universe | Headline | Notes |
|-------|--------|----------|----------|-------|
| HXZ 2015 [Tablo 1A, s.6] | 1972-2011 monthly | NYSE/Amex/NASDAQ ex-fin | Mean 0.44%/month, t=4.73; CAPM α 0.51%; FF3 HML loading 0.40 + alpha sig | Origin paper |
| HXZ 2015 [Tablo 1B] | 1972-2011 | — | corr(I/A, HML) = 0.69 | HML-like role partial |
| HXZ 2015 [Tablo 1B] | 1972-2011 | — | corr(I/A, ROE) = 0.05 | Orthogonal triple sort başarılı |
| HXZ 2015 [Section 3] | 1972-2011 | NYSE-VW | I/A subsumes B/M + net stock issues + accruals + market leverage + long-term reversal + E/P + composite issuance in forecasting returns | Section 6 Conclusion |
| HXZ 2020 Replicating | 1967-2014 | NYSE-VW | I/A factor 447 anomaly empirical replication lens | [[papers/hou_xue_zhang_2020_replicating_anomalies]] |
| HMXZ 2020 Security Analysis | 1967-2014 | NYSE-VW | I/A factor q5 model component | [[papers/hou_mo_xue_zhang_2020_security_analysis]] |
| JKP 2023 | 1926-2020 US | Bayesian Empirical Bayes | I/A theme **displaced** (Profitability + Investment + Size 3 displaced joint modeling redundancy) | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] |

## I/A vs CMA Karşılaştırma (Methodology Farkı)

| Boyut | I/A (HXZ 2015) | CMA (FF15) |
|-------|------------------|--------------|
| **Origin paper** | HXZ 2015 [[papers/hou_xue_zhang_2015_q_factor]] | FF15 [[papers/famafrench2015_five_factor]] |
| **Sample** | 1972-2011 monthly | 1963-2013 monthly |
| **Sort** | 2×3×3 triple sort (size × A/A × ROE) | 2×3 sort (size × Inv) |
| **Breakpoints** | NYSE 30/40/30 | NYSE 30/40/30 |
| **Construction** | 18 portfolio intersection; small-vs-big across A/A buckets | 6 portfolio intersection |
| **Investment ölçüsü** | A/A = ΔAT/AT-lagged (annual change) | Inv = ΔAT/AT (paralel ama 2×3 sort'te) |
| **Theoretical foundation** | Investment-q theory Cochrane 1991 + Liu-Whited-Zhang 2009 | "Cleaner" 5-factor model (Fama-French 2015 [s.4]) |
| **Wiki implication** | Q15 horse race direct anchor; q-factor lens primary | FF15 spec; HXZ q-factor span partial proxy |

**Note**: I/A ↔ CMA korelasyon HXZ 2015'te direct rapor edilmedi; FF15 spanning regression ile dolaylı. JKP 2023 Investment* theme universal'de her iki factor implementation paralel ama displaced (joint modeling redundancy).

## I/A vs Asset_Growth Karşılaştırma

[[factors/Asset_Growth]] CGS asset growth = aynı ΔAT/AT formül ama:
- CGS 2008 single-variable decile (no size control)
- HXZ 2015 I/A = 2×3×3 size-controlled factor portfolio
- HXZ 2015 [s.5]: "asset growth is the most comprehensive measure of investment-to-assets... asset growth effect seems to be the premiere manifestation of the investment mechanism" — yani CGS asset growth I/A factor'ün univariate proxy'si

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

- **S&P 500 strategy implication**: I/A factor exposure proxy — sp500_v1 §2.1 Path D Investment* theme Accruals* + investment overlap (CGS asset growth + Sloan accruals + I/A factor)
- **NDX strategy implication**: I/A factor traditional accounting (ΔAT/AT); F bloğu 4-katmanlı intangibles-aware Bm rebuild ortogonal methodology; **Q73 yeni**: q-factor intangibles-aware genişletme aday (r_I/A traditional vs intangibles-adjusted Faz 3 implementation custom modification)
- **Large-cap relevance**: NYSE-VW + microcap-arınmış convention paterni (HXZ 2015 [s.7]); FF 2008 cross-cite "investment effect strong in microcaps absent in big stocks" → q-factor size-controlled

## Implementation Notes

**Required data**:
- Compustat annual: AT (total assets); fiscal year-end
- 4-month accounting lag: June rebalance for fiscal year ending in calendar year t-1
- Annual rebalance default

**Portfolio construction**:
- 2×3×3 size × A/A × ROE triple sort
- NYSE 30/40/30 breakpoints
- Value-weighted within each portfolio
- Monthly returns calculated; portfolios rebalanced annually for size+A/A (June), monthly for ROE

## Bu Faktörün Yumuşak Karnı

- **Sloan accruals exception** [HXZ 2015 Section 3.1]: I/A factor accrual deciles'de h-l alpha -0.05% insig (univariate), ama full q-factor model -0.39% sig daha kötü (ROE factor wrong direction); F_ACCRUAL/G3/QMJ ACC mispricing detection paradigması q-factor lens'inde yetersiz
- **Intangibles-aware genişletme yok**: ΔAT/AT traditional accounting; FAANG/tech firma R&D intangibles-aware adjustment YOK; F bloğu 4-katmanlı NDX strategy ortogonal methodology (Q73 + Q56 paralel)
- **Triple sort sample restriction**: ex-financials + ex-negative book equity standart kuralları paralel
- **Annual sort caveat indirect**: I/A annual rebalance OK ama r_ROE monthly resort zorunluluğu q-factor model bütünü için annual frequency hibrit (Q75 yeni)
- **Sample 1972-2011 post-2011 14 yıl OOS**: JKP 2023 partial 2014-2020 6 yıl modern coverage

## İlgili
- [[papers/hou_xue_zhang_2015_q_factor]] — origin paper (Cycle 35)
- [[concepts/q_factor_model]] — q-factor model concept hub
- [[factors/CMA]] — FF15 investment factor methodology farkı
- [[factors/Asset_Growth]] — CGS asset growth single-variable proxy
- [[factors/ROE]] — q-factor model ROE factor (sister)
- [[factors/SMB]] — r_ME virtually identical (sister)
- [[concepts/asset_growth_anomaly]] — investment-q vs mispricing yorumlar
- [[concepts/discount_rates]] — Cochrane 1991 q-theory
- [[strategies/sp500_v1]] §2.1 Path D Investment* theme
- [[strategies/nasdaq100_v1]] §2.5 F bloğu 4-katmanlı q-factor span kontrolü
- [[methodology/backtest_spec]] §4.4 replication-robust filter HXZ q-factor formal tanımı

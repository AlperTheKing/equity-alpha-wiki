---
type: factor
name: ROE
opened: 2026-05-02
phase: faz_3_cycle_35
category: profitability
direction: long_high_minus_low
data_lag_required: "quarterly earnings announcement date (RDQ); monthly resort"
rebalance_frequency: monthly
universe_tested: ["CRSP+Compustat 1972-2011 NYSE-Amex-NASDAQ ex-financials ex-negative book equity"]
cycle_38_note: "HXZ ROE methodology paralel Cop (cash-based) cross-link [[factors/Cop]] yeni entity Cycle 38 ✓ ([[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]); HXZ ROE = IBQ/BE_lagged quarterly + Cop = Ope-ΔWC/AT annual iki cash-based variant; Profitability zinciri 4. halka aday (HXZ ROE Cycle 35) + 4. halka standalone (Ball-GLN Cop Cycle 38) methodology paralel; HXZ q-factor Sloan accruals exception (Cycle 35 Q15a) vs Ball-GLN Cop subsumption (Cycle 38) complementary methodology farkı (q-factor I/A+ROE size-controlled lens vs Cop accrual-cash flow decomposition lens)"
cycle_39_note: "Stambaugh-Yuan 11 anomaly Cluster 2 (PERF) içinde ROA dahil [[factors/PERF]] Cycle 39 ✓ ([[papers/stambaugh_yuan_2017_mispricing_factors]]); paper Cluster 2 ROA Fama-French 2006 paterni traditional; HXZ ROE r_ROE quarterly IBQ/BE_lagged paralel methodology ama farklı (HXZ q-theoretical 2×3×3 sort + ROA traditional FM regression composite); Cluster 2 distress + O-score + momentum + GP/A + ROA performance indicators composite mispricing factor"
---

# ROE — Return on Equity Factor (HXZ 2015 q-Factor Model)

> 📝 **Cycle 35 yeni factor entity.** [[papers/hou_xue_zhang_2015_q_factor]]
> q-factor model 4 faktöründen biri (MKT + ME + I/A + **ROE**).
> [[factors/RMW]] ile methodology farkı + horse race dokümantasyonu
> için ayrı entity (FF15 RMW = operating profitability annual; HXZ ROE
> = quarterly IBQ monthly resort earnings announcement-anchored).

## Tanım (matematiksel)

```
ROE_q = IBQ_q / BE_{q-1}
```

- **IBQ** = Income Before Extraordinary Items (Compustat quarterly item IBQ)
- **BE_{q-1}** = One-quarter-lagged book equity:
  - Book equity = shareholders' equity + balance sheet deferred taxes/investment tax credit (TXDITCQ if available) - book value of preferred stock
  - Shareholders' equity priority: SEQQ → CEQQ + PSTKQ → ATQ - LTQ
  - Preferred stock: PSTKRQ if available, else carrying value
- Davis-Fama-French 2000 quarterly version of annual book equity measure

## Origin

- **Paper-spesifik origin**: [[papers/hou_xue_zhang_2015_q_factor]] (Cycle 35; q-factor model 4-factor formal tanımı)
- **Literatür hattı kökü** (Origin attribution dual pattern Cycle 9+15+23 paterni paralel):
  - Ball-Brown 1968 — earnings announcement effect literature origin
  - Bernard-Thomas 1989/1990 — post-earnings-announcement drift (PEAD) literatür hattı
  - Frankel-Lee 1998 (Tier 1; paywall; Faz 3 seçici ingest aday) — V/P intrinsic value
  - Piotroski 2000 [[papers/piotroski2000_f_score]] — F-Score F_ACCRUAL Sloan zinciri
  - Fama-French 2006 — residual income model (Bm + expected profitability + expected investment)
  - Novy-Marx 2012/2013 [[papers/novy_marx_2013_gross_profitability]] (Cycle 23) — GP/A Profitability zinciri 1. halka
  - Fama-French 2015 [[papers/famafrench2015_five_factor]] — RMW Ope (Profitability zinciri 2. halka; methodology farkı)

## Factor Construction (HXZ 2015 Methodology)

[HXZ 2015 Section 2 + Eq.(4)]:

**2×3×3 triple sort**: size × A/A × ROE NYSE breakpoints VW

```
r_ROE = (1/6) × Σ p_ij3 - (1/6) × Σ p_ij1
        i,j                  i,j
```

- **p_ij3** = portfolio in high-ROE group (k=3) across 2 size × 3 A/A = 6 portfolios
- **p_ij1** = portfolio in low-ROE group (k=1) across 2 size × 3 A/A = 6 portfolios
- **Monthly resort**: at beginning of each month based on most recent public earnings announcement (Compustat quarterly item RDQ)
- **NYSE 30/40/30 breakpoints**: low 30% / mid 40% / high 30%

> ⚠️ **Monthly resort zorunlu** [HXZ 2015 s.7 fn 5]: ROE factor monthly
> construction çünkü:
> 1. Targeted anomalies (momentum + PEAD + IVOL + distress) all monthly-sorted
> 2. ROE forecasts future returns to extent it forecasts future ROE; most recent ROE contains up-to-date information
> 3. **Annually-sorted versions of targeted anomalies DON'T EXIST** — none of high-minus-low portfolios produce mean excess returns or CAPM alphas significantly different from zero (Apx E)
>
> **Wiki annual frequency hedef için kritik caveat** — Q35+Q51+Q57+Q75
> paralel sensitivity test Faz 3 backtest implementation karar.

## Reported Performance Across Studies

| Study | Period | Universe | Headline | Notes |
|-------|--------|----------|----------|-------|
| HXZ 2015 [Tablo 1A, s.6] | 1972-2011 monthly | NYSE/Amex/NASDAQ ex-fin | Mean 0.60%/month, t=4.85 | Origin paper; "more than 4.5 standard errors from zero" |
| HXZ 2015 [Tablo 1A] | 1972-2011 | — | FF3 R²=19% | Önemli yeni varyasyon (FF3'te yok) |
| HXZ 2015 [Tablo 1B] | 1972-2011 | — | corr(ROE, WML) = 0.50 | WML/UMD-correlated; momentum-relevant role |
| HXZ 2015 [Tablo 1B] | 1972-2011 | — | corr(ROE, ME) = -0.30 | Size-correlated despite triple sort control |
| HXZ 2015 [Tablo 1B] | 1972-2011 | — | corr(ROE, I/A) = 0.05 | Orthogonal triple sort başarılı |
| HXZ 2015 [Section 3] | 1972-2011 | NYSE-VW | ROE subsumes short-term prior returns + earnings surprise + financial distress in forecasting returns | Section 6 Conclusion |
| HXZ 2020 Replicating | 1967-2014 | NYSE-VW | ROE factor 447 anomaly empirical replication lens | [[papers/hou_xue_zhang_2020_replicating_anomalies]] |
| HMXZ 2020 Security Analysis | 1967-2014 | NYSE-VW | ROE factor q5 model component (eg+ extension paralel) | [[papers/hou_mo_xue_zhang_2020_security_analysis]] |
| JKP 2023 | 1926-2020 US | Bayesian Empirical Bayes | Profitability theme **displaced** (joint modeling redundancy 3 displaced) | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] |

## ROE vs RMW Karşılaştırma (Methodology Farkı)

| Boyut | ROE (HXZ 2015) | RMW (FF15) |
|-------|------------------|--------------|
| **Origin paper** | HXZ 2015 [[papers/hou_xue_zhang_2015_q_factor]] | FF15 [[papers/famafrench2015_five_factor]] (literatür hattı kökü Novy-Marx 2013 GP/A) |
| **Sample** | 1972-2011 monthly | 1963-2013 monthly |
| **Profitability ölçüsü** | IBQ_q / BE_{q-1} (quarterly IBQ income before extraordinary items) | Operating profitability (REVT - COGS - SG&A - INT) / BE annual |
| **Frequency** | Monthly resort | Annual sort |
| **Sort** | 2×3×3 triple sort (size × A/A × ROE) | 2×3 sort (size × Profit) |
| **Methodology** | Quarterly earnings announcement-anchored (RDQ) | Annual fiscal year-end |
| **HXZ 2020 q-factor lens** | ROE factor sig | RMW Ope INSIG (q-factor alpha 0.04% t=0.42) |
| **FGX 2020 DS LASSO lens** | ROE factor DS-sig | RMW DS-sig (her iki paralel methodology bulgu farkı methodology disagreement) |
| **Profitability zinciri rolü** | 4. halka aday (Cop methodology paralel; HXZ 2020 Cop empirical) | 2. halka (Novy-Marx GP/A → FF15 RMW Ope) |

## ROE vs GP/A Karşılaştırma (Profitability Zinciri)

| Boyut | ROE (HXZ 2015) | GP/A (Novy-Marx 2013) |
|-------|------------------|--------------------------|
| **Profitability zinciri rolü** | 4. halka aday | 1. halka origin |
| **Numerator** | IBQ (income before extraordinary items quarterly) | REVT - COGS (gross profits annual) |
| **Denominator** | BE quarterly book equity | AT total assets annual |
| **Frequency** | Monthly | Annual |
| **Theoretical foundation** | Investment-q theory (Cochrane 1991) | "Other side of value" (Novy-Marx 2013) |

[[concepts/q_factor_model]] Profitability zinciri cross-link: Novy-Marx GP/A → FF15 RMW Ope → QMJ GPOA → HXZ ROE/Cop (Cycle 23 + 35 sertleştirme; iki paralel quality zinciri QMJ 4-dimension'da birleşim noktası).

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

- **S&P 500 strategy implication**: ROE factor exposure Profitability theme Path B GP/A standalone + GP×V/P Fortune 500 (sp500_v1 §2.1 Path B); ROE direct test 5. paralel methodology layer (sp500_v1 §3.2 statistical filter)
- **NDX strategy implication**: ROE factor monthly resort zorunluluğu (Q75); F bloğu 4-katmanlı intangibles-aware methodology orthogonal (Q73 yeni; tech firma high ROE interpretation R&D giderleştirilmiyor numerator avantaj Q56 paralel)
- **Large-cap relevance**: NYSE-VW + microcap-arınmış convention paterni (HXZ 2015 [s.7])
- **Distress effect explanation** [Tablo 4]: ROE factor loading -1.79 (more than 7.5σ) high-low distress decile h-l alpha 0.02% t=0.07 (FF α -1.43%); "more distressed firms less profitable load less on ROE factor"

## Implementation Notes

**Required data**:
- Compustat quarterly: IBQ, RDQ (earnings announcement date), TXDITCQ, SEQQ/CEQQ/PSTKQ/ATQ/LTQ (book equity components), PSTKRQ (preferred stock redemption value)
- Monthly resort timing: months immediately after most recent public earnings announcement date (RDQ)
- Example: Q4 t-1 earnings announced March 5 (or 25) of year t → portfolio formed beginning of April year t

**Portfolio construction**:
- 2×3×3 size × A/A × ROE triple sort
- NYSE 30/40/30 breakpoints (monthly for ROE; annual June for size+A/A)
- Value-weighted within each portfolio
- Monthly resort for ROE; annual resort for size+A/A

## Bu Faktörün Yumuşak Karnı

- **Monthly resort zorunluluğu**: wiki annual frequency hedef için kritik mismatch; r_ROE annual-sort version anomalies INSIG (Q35+Q51+Q57+Q75 paralel sensitivity test); Faz 3 backtest implementation hibrit yapı (r_I/A annual + r_ROE monthly) reconciliation karar
- **Sloan accruals exception** [HXZ 2015 Section 3.1]: ROE factor loading **wrong direction** in explaining accrual effect ("high accrual firms invest more but also more profitable load more on ROE factor"); F_ACCRUAL/G3/QMJ ACC mispricing detection paradigması q-factor lens'inde ROE channel masked
- **Intangibles-aware genişletme yok**: traditional book equity (SEQQ); FAANG/tech firma R&D giderleştirilmiyor numerator IBQ etkilenir ama denominator BE traditional; F bloğu 4-katmanlı NDX strategy ortogonal methodology (Q73 + Q56 paralel)
- **Triple sort sample restriction**: ex-financials + ex-negative book equity standart kuralları paralel
- **Sample 1972-2011 post-2011 14 yıl OOS**: JKP 2023 partial 2014-2020 6 yıl modern coverage; post-2020 hala out-of-sample
- **HXZ 2020 q-factor lens vs FGX 2020 DS LASSO methodology farkı**: ROE/RMW aile (paralel) iki paralel framework'te farklı bulgu (q-factor vs DS LASSO; methodology disagreement değil scope-dependent — Cycle 26 dokümante)

## İlgili
- [[papers/hou_xue_zhang_2015_q_factor]] — origin paper (Cycle 35)
- [[concepts/q_factor_model]] — q-factor model concept hub
- [[factors/RMW]] — FF15 operating profitability factor methodology farkı
- [[factors/Gross_Profitability]] — Novy-Marx GP/A standalone (Profitability zinciri 1. halka)
- [[factors/QMJ]] — Asness QMJ Profitability dimension (4-dimension composite)
- [[factors/I_A]] — q-factor model investment factor (sister)
- [[factors/UMD]] — momentum factor (r_ROE corr 0.50)
- [[factors/SMB]] — r_ME virtually identical (sister)
- [[concepts/earnings_quality]] — earnings persistence + cash-flow desteği
- [[concepts/winner_loser_identification]] — B bloğu core kavramı
- [[concepts/discount_rates]] — Cochrane 1991 q-theory ROE channel
- [[strategies/sp500_v1]] §2.1 Path B Profitability theme + §3.2 statistical filter
- [[strategies/nasdaq100_v1]] §2.5 F bloğu 4-katmanlı + §3.6 NDX-spesifik nüans tech R&D-arî numerator Q56
- [[methodology/backtest_spec]] §4.4 replication-robust filter HXZ q-factor formal tanımı

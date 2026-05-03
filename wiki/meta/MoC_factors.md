# Map of Content — Factors

> Faktörler kategori bazında. Her ingest'te yeni faktör eklendiğinde güncellenir.

## Market
- [[factors/MKT_RF]] — value-weighted CRSP NYSE/AMEX/NASDAQ excess return (FF93 mimicking-portföy çerçevesi)

## Size
- [[factors/SMB]] — Small Minus Big (FF93; FF15'te 3-sort ortalamasına revize)

## Value
- [[factors/HML]] — High Minus Low book-to-market (FF93; FF15'te 5F altında redundant)

## Quality (Cycle 19'da dolduruldu — Cycle 5'ten beri açık placeholder)
- [[factors/QMJ]] — **Cycle 19 ek**; Asness-Frazzini-Pedersen 2019 4-dimension composite (Profitability + Growth + Safety + Payout); 22 measure z-score; US 1956-2012 4-factor alpha 66 bps/ay (t=11.20); Q2 fully-answered ANCHOR; QARP framework Li-Mohanram F&V/P + G&V/P combined paradigm Asness paralel

## Profitability (Cycle 23 — Profitability zinciri dokümante; Cycle 38 sertleştirme)
- [[factors/Gross_Profitability]] — **Cycle 23 yeni**; Novy-Marx 2013 GP/A = (REVT−COGS)/AT; standalone profitability factor; **Profitability zinciri 1. halka (origin)**; numerator intangibles-aware (R&D ARÎ); Fortune 500 GP/V combined Sharpe 0.74 ⭐ wiki S&P 500 direct anchor; large-cap size-invariant
- [[factors/RMW]] — Robust Minus Weak operating profitability (FF15); **Profitability zinciri 2. halka** (RMW Ope methodology Novy-Marx GP/A literatür hattı kökü; FF15 [s.4] explicit cite)
- [[factors/Cop]] — **Cycle 38 yeni**; Ball-GLN 2016 cash-based operating profitability standalone; Cop = (REVT − COGS − SG&A) − ΔWC ÷ AT_lagged; **Profitability zinciri 4. halka** standalone cash-based evolution; 6-portfolio sort FF15 paterni; Ball-GLN [Tablo 5] RMW^CbOp 4.88%/yr t=6.29 (RMW^Op 3.25%/yr t=3.65'ten substantially higher); Cop subsumes accruals + wins horse race + tangency Sharpe 4F+Cop=1.67 ⭐; HMXZ Tablo 5 Cop alpha 0.69%/ay sig + HXZ 2020 dört darbe 4/4 hayatta kalan empirical validation; annual rebalance compatible

> 📝 **Profitability zinciri 4-paper × 7-yıl methodology hierarchy** (Cycle 38 sertleştirme): GP/A (origin Novy-Marx 2013) → RMW Ope (FF15 2015) → QMJ GPOA (Asness 2019 composite 5 measure) → **Cop (Ball-GLN 2016 cash-based standalone)** ⭐ en güçlü modern halka; Sloan fixation hypothesis çürütme + Cop subsumes accruals; QMJ 4-dimension Profitability + Accruals **birleşim noktası** (GPOA + ACC components yan yana) Ball-GLN methodology link iki paralel quality zinciri köprüsü.

## Composite Mispricing (Cycle 39 yeni kategori — Stambaugh-Yuan paterni)
- [[factors/MGMT]] — **Cycle 39 yeni**; Stambaugh-Yuan 2017 management-related composite mispricing factor (UMO1); P1 = avg ranking across 6 cluster-1 anomalies (net stock issues + composite equity issues + accruals + NOA + asset growth + I/A); 2×3 sort size × P1 NYSE+AMEX+NASDAQ 20th/80th percentile VW monthly; long-short β cluster-1 t=6.09-18.12 sig; sentiment short-leg t=-2.06 sig; **Composite scoring 3. halka**
- [[factors/PERF]] — **Cycle 39 yeni**; Stambaugh-Yuan 2017 performance-related composite mispricing factor (UMO2); P2 = avg ranking across 5 cluster-2 anomalies (distress + O-score + momentum + gross profitability + ROA); 2×3 sort size × P2 NYSE+AMEX+NASDAQ 20th/80th percentile VW monthly; long-short β cluster-2 t=5.02-24.10 sig; sentiment short-leg t=-2.05 sig; Cluster 2 GP/A + ROA Profitability zinciri cross-evidence

> 📝 **Composite scoring paradigm literature continuity 4-paper × 17-yıl** (Cycle 39 sertleştirme): F-Score (Piotroski 2000 binary 9-component high-BM) → G-Score (Mohanram 2005 binary industry-median low-BM) → **Stambaugh-Yuan MGMT/PERF (continuous composite 11-anomaly 2-cluster)** ⭐ → JKP 13 theme cluster (Bayesian Empirical Bayes); methodology evolution binary → continuous + single-evren → multi-anomaly aggregation + sentiment-aware factor model integration.

## Intangibles (Cycle 25 yeni kategori — F bloğu factor portfolio)
- [[factors/Organization_Capital]] — **Cycle 25 yeni**; Eisfeldt-Papanikolaou 2013 OC factor; SG&A perpetual inventory δ=15% (Lev-Radhakrishnan 2004 paterni); industry-relative within FF17; spread 4.8%/yıl Sharpe 0.58 + FF3 α 5.5% sig + Carhart α 3.9% sig 1% (1970-2008); **F bloğu 4. ayak (factor portfolio direct evidence)** ⭐ NDX strategy spec; high OC firms NDX FAANG profile birebir match (low PP&E/AT + growth-tilted + low leverage); operating leverage rejected (DOL-controlled 3.1% sig 1%)

> 📝 **F bloğu intangibles 4-katmanlı methodology hierarchy** (Cycle 25 sertleştirme):
> 1. Lev-Sougiannis 1996 R&D capital (Knowledge, methodology infrastructure)
> 2. **Eisfeldt-Papanikolaou 2013 OC factor portfolio (Organization, factor portfolio direct evidence)** ⭐
> 3. Peters-Taylor 2017 q^tot proxy (Total, methodology infrastructure)
> 4. Lev-Srivastava 2020 adjusted HML (Application, methodology infrastructure)
> Methodology infrastructure (1+3+4) + factor portfolio anchor (2) ayrımı dokümante.

> 📝 **Profitability zinciri 4 halka** (Sloan zinciri paralel, Cycle 23 dokümante):
> 1. Novy-Marx 2013 GP/A (origin) → 2. FF15 RMW Ope → 3. QMJ GPOA (composite) → 4. HXZ 2020 Cop (cash-aware evrim, 4/4 hayatta kalan)
> İki paralel quality zinciri QMJ 4-dimension'da birleşiyor (Profitability dimension 6 measure içinde GPOA + ACC yan yana).

## Investment / Asset Growth
- [[factors/CMA]] — Conservative Minus Aggressive total asset growth (FF15 mimicking-portföy version)
- [[factors/Asset_Growth]] — CGS asset growth single-variable decile (standalone version; CMA aggregate'ının altındaki temel measure)
- [[factors/I_A]] — **Cycle 35 yeni**; HXZ 2015 q-factor model investment factor (low minus high A/A); 2×3×3 triple sort NYSE breakpoints VW; A/A = ΔAT/AT-lagged (Cooper-Gulen-Schill 2008 paralel); mean 0.44%/month t=4.73 (1972-2011); HML-correlated 0.69; investment-q theoretical foundation Cochrane 1991; methodology farkı CMA ile dokümante (FF15 CMA = 2×3 sort decile spread; HXZ I/A = 2×3×3 q-theoretical implementation)

## q-Factor Model (Cycle 35 yeni kategori)
- [[factors/I_A]] (yukarıda Investment kategorisinde) — q-factor model investment factor
- [[factors/ROE]] — **Cycle 35 yeni**; HXZ 2015 q-factor model return on equity factor (high minus low ROE); 2×3×3 triple sort NYSE breakpoints VW; ROE_q = IBQ_q / BE_{q-1}; mean 0.60%/month t=4.85 (1972-2011); FF3 R²=19% önemli yeni varyasyon; WML/UMD-correlated 0.50 momentum-relevant; **monthly resort zorunlu** [HXZ 2015 s.7 fn 5] annually-sorted versions of momentum/PEAD/IVOL/distress INSIG; methodology farkı RMW ile dokümante (FF15 RMW = operating profitability annual; HXZ ROE = quarterly IBQ monthly resort earnings announcement-anchored); Profitability zinciri 4. halka aday

> 📝 **q-factor model 4 faktör** (HXZ 2015 origin Cycle 35): MKT + r_ME + r_I/A + r_ROE; r_ME virtually identical SMB ile (corr 0.95 + SMB loading 0.99 ayrı entity AÇILMADI cross-link yeterli); 4-paper × 8+ yıl q-factor literature continuity (HXZ 2015 origin → HMXZ 2020 q5 → HXZ 2020 Replicating → JKP 2023 Bayesian) [[concepts/q_factor_model]] hub.

## Earnings Quality / Accruals
- [[factors/Accruals]] — Sloan total accruals (1996 origin); long lowest-accrual decile / short highest-accrual decile

## Growth-Quality (Mohanram tipi)
- [[factors/G_Score]] — R&D / capex / advertising intensity + earnings/sales stability + ROA/CFO industry-relative (low-BM growth firmalarda)

## Distress / Failure
_(boş)_

## Forensic / Manipulation Detection (Cycle 18 yeni kategori)
- [[factors/M_Score]] — **Cycle 18 ek**; Beneish 1999 8-component probit forensic composite; manipulator/non-manipulator binary classification; **filter olarak kullanılır, signal değil** (epistemik düzlem winner-loser ≠ forensic); en eski açık placeholder (Cycle 5'ten beri F_Score sayfasında) doldurulu

## Composite Scores
- [[factors/F_Score]] — Piotroski 9-component fundamental score (high-BM evrende kalibre, firm-level eşik)
- [[factors/G_Score]] — Mohanram 8-component industry-median fundamental score (low-BM evrende kalibre, industry-median eşik)
- [[factors/Magic_Formula]] — Greenblatt EBIT/EV + ROC composite (HMXZ academic validator; q5 ile tam span)
- [[factors/M_Score]] — Beneish 8-component forensic composite (5 sig + 3 insig); F-Score / G-Score winner-loser paradigmasına ek katman
- [[factors/QMJ]] — Asness 22 measure → 4 dimension z-score composite (Cycle 19); Profitability + Growth + Safety + Payout; all-cap quality (large/small ayrı); QARP framework

## Momentum
- [[factors/UMD]] — Up Minus Down (Carhart 1997, alias PR1YR / MOM)

## ML-derived signals
_(boş)_

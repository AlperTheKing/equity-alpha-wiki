---
type: factor
name: Cop
opened: 2026-05-02
phase: faz_3_cycle_38
category: profitability
direction: long_high_minus_low
data_lag_required: "annual fiscal year-end + 6-month lag (June rebalance)"
rebalance_frequency: annual
universe_tested: ["CRSP+Compustat 1963-2014 NYSE+Amex+NASDAQ ex-financials"]
---

# Cop — Cash-Based Operating Profitability Factor (Ball-GLN 2016)

> 📝 **Cycle 38 yeni factor entity (Profitability zinciri 4. halka).**
> 3-kriter testi geçti: (1) yapısal yük 4-paper × 7-yıl evidence + 4/4
> hayatta kalan empirical validation; (2) methodology farkı gross
> (Novy-Marx GP/A) vs cash-based operating (Ball-GLN Cop) vs operating
> (FF15 RMW Ope) vs composite (QMJ GPOA); (3) mevcut entity'lere
> sığmıyor (RMW Ope ≠ Cop ≠ GP/A ≠ GPOA). Cycle 23 Gross_Profitability
> paterni paralel açma kararı.

## Tanım (matematiksel)

```
Cop_t = (REVT_t - COGS_t - SG&A_t) - (ΔAR + ΔInv + ΔPrepaid - ΔDeferredRev - ΔAP - ΔAccrued)
      / AT_{t-1}
```

- **Operating profitability bileşeni**: REVT − COGS − SG&A (Ball et al. 2015 paterni; Novy-Marx 2013 GP/A'nın SG&A çıkarılmış versiyonu)
- **Working capital accruals çıkarma**: ΔAR (Accounts Receivable) + ΔInv (Inventory) + ΔPrepaid Expenses − ΔDeferred Revenue − ΔAP (Accounts Payable) − ΔAccrued Expenses
- **Denominator**: AT (Total Assets) lagged by one year
- Davis-Fama-French 2000 paterni paralel book equity tanımları (cycle_38 paper [s.6-7])
- Balance sheet implementation primary; cash flow statement post-1988 robustness check (Hribar-Collins 2002 measurement error caveat)

## Origin

- **Paper-spesifik origin**: [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] (Cycle 38 BU; Cop standalone formal origin)
- **Literatür hattı kökü** (Origin attribution dual pattern Cycle 9+15+23+35 paterni paralel):
  - [[papers/sloan1996_accruals_anomaly]] — Sloan accruals anomaly origin; Ball-GLN [s.2 + s.4] explicit cite; cash flow + accruals decomposition methodology Sloan paterni paralel
  - [[papers/novy_marx_2013_gross_profitability]] — Profitability zinciri 1. halka methodology continuity (gross profit numerator paralel; SG&A çıkarma Ball-GLN evrim)
  - Ball et al. 2015 [Working Paper] — operating profitability paper paralel (paper [s.6 + s.8] cross-cite); Cop = Ope − ΔWC formülasyonunun direct precursor'ü
  - [[papers/famafrench2015_five_factor]] — FF15 RMW Ope methodology paralel; 6-portfolio sort FF 2015 paterninden Ball-GLN Tablo 5 RMW^CbOp construction

## Factor Construction (Ball-GLN Methodology) [Tablo 5]

**6-portfolio sort** (FF 2015 paterni paralel):

```
Step 1: Size sort — NYSE median market cap breakpoint (small + big)
Step 2: Independent Cop sort — NYSE 30/70 percentile breakpoints (weak + neutral + robust)
Step 3: 2 × 3 = 6 portfolios value-weighted
Step 4: RMW^CbOp = avg(2 robust Cop portfolios) - avg(2 weak Cop portfolios)
```

**Annual rebalance** [s.7]: "In portfolio sorts, we rebalance the portfolios annually at the end of June" — wiki annual frequency hedef için **direct uyumlu** (HXZ 2015 r_ROE monthly resort zorunluluğu Q75'in TERSİ; Cop annual rebalance compatible).

## Reported Performance Across Studies

| Study | Period | Universe | Headline | Notes |
|-------|--------|----------|----------|-------|
| Ball-GLN 2016 [Tablo 5] | 1963-07/2014-12 | NYSE+Amex+NASDAQ ex-fin | RMW^CbOp **4.88%/yr t=6.29** | Origin paper; substantially higher than RMW^Op 3.25%/yr t=3.65 + ACC 2.7%/yr t=3.42 |
| Ball-GLN 2016 [Tablo 2 col 5] | 1963-2014 monthly FM | All-but-microcaps | Cop standalone **t=9.69** | 40% Sharpe artış vs Ope t=7.04 |
| Ball-GLN 2016 [Tablo 2 col 6] | 1963-2014 | All-but-microcaps | Cop t=7.4 + Acc **t=0.34 INSIG** | **Cop subsumes accruals** |
| Ball-GLN 2016 [Tablo 2 col 7] | 1963-2014 | All-but-microcaps | Cop t=5.27 + Ope **t=1.56 INSIG** | **Cop wins horse race** vs Ope |
| Ball-GLN 2016 [Tablo 7 Panel A] | 1963-2014 | — | 3F+Cop alpha for Ope **-1.15 INSIG** + alpha for Acc **t=1.69 INSIG** | 3F+Cop subsumes Ope + Acc |
| Ball-GLN 2016 [Tablo 8] | 1963-2014 | — | Tangency Sharpe **4F+Cop=1.67** > 4F+Ope+Acc=1.54 | Cop alone better than Ope+Acc combined |
| Ball-GLN 2016 [Section 7] | 1963-2014 | — | Cop predicts returns **10 years ahead** | Long-horizon predictive power |
| HMXZ 2020 [Tablo 5] | 1967-2014 | NYSE-VW | Cop q-factor alpha **0.69%/ay sig** | 4/4 hayatta kalan; q5 model component |
| HXZ 2020 Replicating [Tablo 5] | 1967-2014 | NYSE-VW | Cop dört darbe 4/4 hayatta kalan ⭐ | Empirical validation |
| FGX 2020 | 1976-2017 | 150-factor library | Cop family DS-sig validation | Q55 fully-answered Cycle 26 |
| JKP 2023 | 1926-2020 US Bayesian | Profitability theme | Profitability theme **displaced** (joint modeling redundancy 3 displaced) | Profitability+Investment+Size |

## Cop vs RMW Karşılaştırma (Methodology Farkı)

| Boyut | Cop (Ball-GLN 2016) | RMW (FF15) |
|-------|----------------------|--------------|
| **Origin paper** | Ball-GLN 2016 [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] | FF15 [[papers/famafrench2015_five_factor]] |
| **Numerator** | Ope − ΔWC (cash-based; working capital accruals çıkarılmış) | REVT − COGS − SG&A − INT (operating profitability; accruals dahil) |
| **Denominator** | AT (total assets) lagged | BE (book equity) annual |
| **Frequency** | Annual June rebalance (portfolio sorts) | Annual fiscal year-end |
| **Construction** | 6-portfolio (FF15 paterni: 2×3 NYSE 30/70) | 6-portfolio (2×3 NYSE 30/70) — **methodology identik FF15 paterninden derive** |
| **Sample** | 1963-2014 | 1963-2013 |
| **Avg annualized return** | **4.88% t=6.29** | 3.25% t=3.65 (Ball-GLN [Tablo 5]) |
| **3F alpha** | **58 bps t=10.09** | 46 bps t=7.01 |
| **Tangency Sharpe (4F+factor)** | **1.67** ⭐ | 1.40 |
| **Subsumes Acc?** | ✅ YES (Cop t=7.4 + Acc t=0.34 INSIG) | ❌ NO (Ope t=7.04 + Acc t=-5.50 anomaly güçlenir) |
| **HXZ q-factor lens** | Cop 4/4 hayatta kalan q-factor alpha 0.69% sig | RMW Ope INSIG q-factor alpha 0.04% t=0.42 |
| **FGX DS LASSO lens** | Cop family DS-sig | RMW DS-sig (paralel methodology bulgu farkı) |

## Cop vs GP/A Karşılaştırma (Profitability Zinciri 4. halka vs 1. halka)

| Boyut | Cop (Ball-GLN 2016) | GP/A (Novy-Marx 2013) |
|-------|----------------------|--------------------------|
| **Profitability zinciri rolü** | 4. halka (cash-based evolution) | 1. halka (origin) |
| **Numerator** | Ope − ΔWC (REVT − COGS − SG&A − ΔWC) | REVT − COGS (gross profit) |
| **SG&A handling** | Çıkarılır (operating profit) | Numerator'da değil (gross) |
| **Accruals handling** | Working capital accruals çıkarılır | Accruals dahil (gross profit) |
| **Sharpe artış** | Ball-GLN [s.10]: "Sharpe ratio for Cop is also higher than the Sharpe ratios for gross profitability and net income" | Novy-Marx 2013 baseline |
| **Wiki implication** | Profitability zinciri en güçlü modern halka | Origin literatür hattı kökü |

## Cop vs QMJ GPOA Karşılaştırma

| Boyut | Cop (Ball-GLN 2016) | QMJ GPOA (Asness 2019) |
|-------|----------------------|--------------------------|
| **Profitability zinciri rolü** | 4. halka standalone | 3. halka (composite içinde) |
| **Form** | Single signal (Cop standalone) | 5-measure composite (GPOA + ROA + ROE + ACC + ...) z-score |
| **Methodology** | Cash-based operating ÷ AT | GPOA = gross profit ÷ assets composite içinde |
| **Birleşim noktası** | Ball-GLN cash flow + accruals decomposition methodology | QMJ 4-dimension Profitability + Accruals **birleşim noktası** (GPOA + ACC components yan yana) |

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

- **S&P 500 strategy implication** (sp500_v1 §2.1 Path B Profitability theme):
  - Cop direct factor portfolio 4.88%/yr t=6.29 (Ball-GLN [Tablo 5]); 4F+Cop tangency Sharpe 1.67 (Ball-GLN [Tablo 8])
  - All-but-microcaps Panel A primary analysis FF 2008 paterni paralel; Cop sig in both panels (large-cap-direct test)
  - GP/A standalone (Novy-Marx) + Cop standalone (Ball-GLN) iki paralel Profitability anchor; Q55 fully-answered Cycle 26 + Cycle 38 sertleştirme
- **NDX strategy implication** (nasdaq100_v1 §2.1 Path B + §2.5 F bloğu 4-katmanlı):
  - **Q79 yeni**: Cop methodology NDX-spesifik R&D-intensive firma kalibrasyonu (Cop = REVT − COGS − SG&A; SG&A R&D dahil → FAANG/biotech firmalarda R&D giderleştirme Cop'u yapay düşürür); F bloğu paralel intangibles-aware Cop modification Faz 3 implementation custom (Q56 + Q73 paterni paralel)
  - F bloğu intangibles-aware Bm rebuild q-factor traditional accounting'tan ortogonal methodology
- **Large-cap relevance**: Ball-GLN [s.7] FF 2008 paterni explicit cite "Following Fama and French (2008), we define Microcaps as stocks with a market value of equity below the 20th percentile of the NYSE market capitalization distribution"; All-but-microcaps Panel A primary analysis large-cap-direct test cross-evidence Q14 fully-answered FF 2008 ANCHOR cross-link

## Implementation Notes

**Required data**:
- Compustat annual: REVT, COGS, SG&A (operating profitability components)
- Balance sheet items: AR (Accounts Receivable), Inv (Inventory), Prepaid Expenses, Deferred Revenue, AP (Accounts Payable), Accrued Expenses
- AT (total assets) lagged by one year
- 6-month accounting lag (FF 2008 paterni paralel)
- Annual rebalance June default

**Portfolio construction**:
- 6-portfolio (2×3) size × Cop sort
- NYSE median market cap + NYSE 30/70 Cop breakpoints
- Value-weighted within each portfolio
- Annual June rebalance
- All-but-microcaps + Microcaps panel comparison

**Alternative cash flow statement implementation** (post-1988):
- Hribar-Collins 2002 measurement error robustness check
- Balance sheet vs cash flow statement accruals comparison

## Bu Faktörün Yumuşak Karnı

- **R&D-intensive firma yapay düşük Cop**: Cop = REVT − COGS − SG&A; SG&A R&D dahil → FAANG/biotech firmalarda R&D giderleştirme Cop'u yapay düşürür (Q79 yeni; Cycle 35 ROE numerator IBQ etkilenir paterni paralel)
- **Sample 1963-2014 post-2014 10 yıl OOS** (Q80 yeni): JKP 2023 partial 2014-2020 6 yıl + post-2020 hala out-of-sample (FAANG era 2014-2024)
- **Balance sheet measurement errors**: Hribar-Collins 2002 caveat; cash flow statement post-1988 alternative robustness check
- **Sloan fixation hypothesis çürütme spillover**: Ball-GLN Cop subsumption Sloan fixation interpretation reject ama mispricing alternative (under-reaction to cash flow gradually corrected) hala mispricing sınıfında; **wiki taraf tutmaz** Cochrane mathematical equivalence
- **6-portfolio FF 2015 paterni**: 30/70 NYSE breakpoints; 2×3 sort decile spread değil
- **Intangibles-aware genişletme yok**: traditional accounting (REVT + COGS + SG&A + balance sheet accruals); F bloğu 4-katmanlı NDX strategy ortogonal methodology

## İlgili
- [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] — origin paper (Cycle 38)
- [[factors/Gross_Profitability]] — Profitability zinciri 1. halka GP/A
- [[factors/RMW]] — Profitability zinciri 2. halka RMW Ope; methodology farkı dokümante
- [[factors/QMJ]] — Profitability zinciri 3. halka QMJ Profitability dim GPOA + 5 measure composite
- [[factors/Accruals]] — Sloan accruals zinciri; Cop subsumption acknowledgment
- [[factors/ROE]] — HXZ ROE methodology paralel (cash-based)
- [[concepts/fundamental_scoring]] — Profitability factor ailesi methodology hierarchy
- [[concepts/earnings_quality]] — Sloan zinciri + Ball-GLN methodology paralel
- [[concepts/factor_zoo]] — Profitability ailesi methodology evolution
- [[concepts/post_publication_decay]] — dört darbe sentez tablosu Cop satırı 4/4 hayatta kalan
- [[strategies/sp500_v1]] §2.1 Path B Profitability theme Cop methodology origin paper anchor
- [[strategies/nasdaq100_v1]] §2.1 Path B Profitability theme + Q79 NDX-spesifik R&D-intensive firma kalibrasyonu
- [[methodology/backtest_spec]] §5.1 4/4 hayatta kalan tablosu Cop formal origin sertleştirme

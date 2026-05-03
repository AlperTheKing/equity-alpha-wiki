---
type: methodology
name: backtest_implementation_plan
status: skeleton
opened: 2026-05-02
phase: faz_3_cycle_40
parent: methodology/backtest_spec
sister: methodology/data_sources
purpose: "Faz 3 backtest implementation Cycle 41-43 operational roadmap; Faz 3 sertifika kriter #6-9 (+#10 opsiyonel) ilerleme planı"
---

# methodology/backtest_implementation_plan — Faz 3 Backtest Implementation Operational Roadmap

> 📝 **Cycle 40 açılış (Faz 3 §11.5 ZORUNLU consolidation pass + backtest
> implementation kickoff).** methodology/ klasörünün **3. sayfası** (Cycle
> 21 [[methodology/backtest_spec]] + Cycle 29 [[methodology/data_sources]]
> sonrası); 3-kriter testi geçti (yapısal yük 7/10 sertifika + ayrı epistemic
> düzlem operational vs theoretical + mevcut backtest_spec ~1000+ satır
> theoretical infrastructure ayrı operational sub-document). Cycle 21
> backtest_spec + Cycle 29 data_sources paterni paralel skeleton statüsü.
>
> **Skeleton statüsü**: Cycle 41-43 implementation cycle'ları sırasında
> bölümler dolar; YAML status: skeleton → operational (Cycle 43 sonu) →
> completed (Cycle 45+ Faz 3 sertifika değerlendirmesi sonrası).

---

## §1 Data Pipeline

> **Faz 3 sertifika kriter #6**: Backtest implementation Chen-Zimmermann + JKP code repository.

### §1.1 Üç Paralel Data Kaynağı ([[methodology/data_sources]] §1-3)

| Kaynak | Methodology | Faz 3 rolü |
|--------|-------------|-------------|
| Chen-Zimmermann 2022 Open Asset Pricing Database | Pure replication ~100% | Reference baseline + factor return validation |
| JKP 2023 GlobalFactor code repository (GitHub bkelly-lab/GlobalFactor) | Bayesian Empirical Bayes %85 | Primary implementation framework + 153 factor library + 13 theme cluster |
| WRDS open-source access (CRSP + Compustat) | Raw feed | Custom S&P 500 + NDX subsample derivation |

### §1.2 Custom Subsample Filtering

- **S&P 500 subsample** (sp500_v1 §1.1): top 500 ex-financials reconstitution-aware survivorship correction; 1980-2020 baseline + 2021-2024 OOS
- **NDX subsample** (nasdaq100_v1 §1.1): top 100 non-financial Nasdaq + index reconstitution annual June + quarterly review; 2000-2020 baseline + 2021-2024 OOS
- **Q72 paralel**: WRDS NDX-spesifik data feed configuration custom

### §1.3 Data Harmonization

> *Skeleton — Cycle 41 implementation sırasında doldurulacak*

- Compustat field standardization (annual + quarterly)
- 4-month accounting lag (FF93 + FF 2008 + Ball-GLN paterni)
- Delisting return imputation (CRSP -30% performance-related Shumway 1997)
- Microcap definition consistency (Cycle 37 FF 2008 < 20th NYSE percentile + Cycle 38 Ball-GLN All-but-microcaps panel)

---

## §2 Code Repository Strategy

### §2.1 JKP GlobalFactor Fork + Custom Modifications

- **Fork**: GitHub bkelly-lab/GlobalFactor → custom branch
- **Modifications**:
  - Capped VW NYSE 80th percentile winsorize (sp500_v1 + nasdaq100_v1 §1.3)
  - S&P 500 / NDX subsample filtering layer
  - 7-theme (sp500) / 5-theme (NDX FAANG) allocation override
  - Stambaugh-Yuan 20/80 NYSE+AMEX+NASDAQ percentile breakpoints (Cycle 39 4. methodology choice)
  - F bloğu 4-katmanlı intangibles-aware Bm rebuild (Knowledge + Organization + Total + Application)
  - Cop SG&A R&D purging (Q79 NDX-spesifik)
  - q-factor I/A intangibles-adjusted (Q73 NDX-spesifik)

### §2.2 Stack Tercih

> *Skeleton — Cycle 41-42 implementation kararı*

- Python (JKP repo R-based; Python translation veya R native)
- pandas + numpy + statsmodels + scikit-learn (DS LASSO için FGX)
- PyMC veya Stan (Bayesian Empirical Bayes JKP)
- Version control: Git + reproducibility seed/commit pinning

---

## §3 Factor Selection — Üç Paralel Methodology

> **Faz 3 sertifika kriter #7**: HLZ + FGX + JKP üç paralel methodology factor selection implementation.

### §3.1 HLZ Frequentist Bonferroni/BHY

- Threshold: `|t| > 3.0` BHY 1% ([[papers/harvey_liu_zhu_2016_multiple_testing]])
- 316-factor census Bonferroni + Holm + BHY üç düzeltme
- Aggregate sig durumu tablosu wiki ingested factor'ler için

### §3.2 FGX Frequentist DS LASSO

- Double-selection LASSO + Fama-MacBeth two-pass + cross-validation 10-fold
- 150-factor library (FF + AQR + Pastor-Stambaugh + HXZ + He-Kelly-Manela + 135 long-short VW)
- 750 test portfolios (36 standard FF + 714 additional 3x2 bivariate)
- Belloni 2014b double-selection methodology

### §3.3 JKP Bayesian Empirical Bayes Hierarchical

- 153 factor × 93 country
- Hierarchical model + capped VW + 1-month holding + 4-month accounting lag
- 13 theme cluster taxonomy

### §3.4 Factor Inclusion Kriter

**Mandatory**: en az **iki paralel methodology'de sig** (sp500_v1 + nasdaq100_v1 §3.2)
**Replication-robust** filter: HXZ NYSE-VW + JKP capped VW iki lens'inde sig (sp500_v1 + nasdaq100_v1 §3.3)
**5. paralel methodology** (q-factor span direct test): [[concepts/q_factor_model]] (Cycle 35 sertleştirme)

---

## §4 13 Theme Cluster + Tangency Portfolio

> **Faz 3 sertifika kriter #8**: 13 theme cluster + tangency portfolio multi-theme allocation framework implementation.

### §4.1 sp500 7-Dominant Theme Subset

[[strategies/sp500_v1]] §2.1 theme allocation:
1. Quality (QMJ + F-Score)
2. Profitability (Cop + GP/A + GP×V/P Fortune 500)
3. Profit Growth (G-Score)
4. Value (Adjusted HML)
5. Momentum (UMD long-only)
6. Accruals* (Sloan Oa filter; Cycle 40 sertleştirme: Cop + Stambaugh-Yuan UMO1 complementary)
7. Low risk (BAB placeholder; Tier 3 #51 ingest sonrası)

### §4.2 NDX 5-FAANG Dominant Theme Subset

[[strategies/nasdaq100_v1]] §2.1 theme allocation (Q69 paralel):
1. Quality (QMJ + QARP)
2. Profitability (G&V/P + GP/A standalone)
3. Profit Growth (Mohanram NASDAQ partition)
4. Investment* (R&D-to-market + OC factor + adjusted Bm) — **NDX-spesifik kritik**
5. Value (Adjusted HML 4-katmanlı)

### §4.3 Tangency Portfolio Multi-Theme Allocation

- 10/13 themes >75% replicate sig+ (JKP 2023)
- 3 displaced (Profitability + Investment + Size) joint modeling redundancy
- Custom subsample re-estimation (sp500 + NDX ayrı tangency)

---

## §5 Üç (+1) Alternative Weighting Sensitivity

> **Faz 3 implementation methodology choice sensitivity test mandatory**

| # | Methodology | Anchor | Rolü |
|---|-------------|--------|------|
| 1 | Pure VW (NYSE-VW) | HXZ baseline; FF93 paterni | Conservative reference |
| 2 | FF half-weight | FF93 paterni | Mid-conservative |
| 3 | **Capped VW** (NYSE 80th percentile winsorize) ⭐ | JKP 2023; sp500 tercih + NDX **ZORUNLU** | Faz 3 implementation tercih (mega-cap concentration kontrolü) |
| 4 | **Stambaugh-Yuan 20/80** (NYSE+AMEX+NASDAQ all-exchange) ⭐ | Stambaugh-Yuan 2017 (Cycle 39 ek) | **Mispricing-aware methodology choice** — "relative mispricing in cross-section likely property of extremes"; composite mispricing factor MGMT/PERF construction |

> 📝 **Cycle 40 yapısal kazanım**: Stambaugh-Yuan 20/80 NYSE+AMEX+NASDAQ paterni 4. methodology choice eklendi ([[papers/stambaugh_yuan_2017_mispricing_factors]] [s.5-6] explicit DEPARTURE FF15 NYSE 30/70); MGMT + PERF composite mispricing factor implementation için zorunlu; Cycle 27 üç alternative weighting + Cycle 39 Stambaugh-Yuan paterni sertleştirme. [[methodology/backtest_spec]] §1.3 paralel.

**Sensitivity test sequencing**: Üçü baseline + 4. mispricing-aware overlay; methodology choice ~50pp gap kanıt ([[meta/contradictions]] §3 HXZ ↔ JKP) sensitivity range 2x reporting (sp500 6-10% ↔ 14-18%; NDX 8-13% ↔ 16-21%).

---

## §6 Reporting Protocol

> **Faz 3 sertifika kriter #9**: DSR-corrected Sharpe + walk-forward + bootstrap reporting.

### §6.1 DSR-Corrected Sharpe (Bailey-LdP 5-Input)

[[papers/bailey_lopezdeprado_2014_deflated_sharpe]]:
- N (trial count)
- V[SR] (Sharpe ratio variance)
- T (sample length)
- Skewness
- Kurtosis

### §6.2 Walk-Forward Expanding Window

- **sp500**: 5-fold (1980-1988 / 1989-1996 / 1997-2004 / 2005-2012 / 2013-2020)
- **nasdaq100**: 4-fold (2000-2005 / 2005-2010 / 2010-2015 / 2015-2020)

### §6.3 Bootstrap Confidence Intervals

- 1000-iter
- Block bootstrap for time-series autocorrelation handling

### §6.4 Üçlü + İki Metric Reporting

| Metric | Anchor |
|--------|--------|
| DSR | [[papers/bailey_lopezdeprado_2014_deflated_sharpe]] |
| Alpha t-stat (q5 + Carhart 4F) | [[methodology/backtest_spec]] §3.2 |
| Decay-adjusted spread (×0.65 sp500 / ×0.50 NDX + JKP %85 sensitivity) | sp500_v1 §4 + nasdaq100_v1 §4 |
| **Factor mean return** | [[papers/feng_giglio_xiu_2020_factor_zoo]] [s.22] |
| **SDF loading** | FGX + JKP framework |

---

## §7 NDX Intangibles Dörtlü Konsolidasyonu Implementation

> **Cycle 40 §11.5 propagation kullanıcı request** (Q75 paterni paralel).
> [[strategies/known_weaknesses]] §3.13 + [[strategies/nasdaq100_v1]] §6 madde 14 dörtlü konsolidasyon implementation eşleşmesi.

### §7.1 Q56 — Intangibles-Aware GP/A FAANG

**Methodology**: GP/A numerator R&D-aware adjustment ([[papers/novy_marx_2013_gross_profitability]] + [[papers/feng_giglio_xiu_2020_factor_zoo]] + [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] entegrasyonu)

### §7.2 Q73 — q-factor I/A Intangibles-Aware Genişletme

**Methodology**: r_I/A traditional ΔAT/AT vs intangibles-adjusted ΔTotalAssets (Knowledge + Organization + Total intangibles dahil); [[papers/hou_xue_zhang_2015_q_factor]] custom modification F bloğu paralel ([[papers/lev_sougiannis_1996_rd_capitalization]] + [[papers/peters_taylor_2017_intangible_capital]] + [[papers/eisfeldt_papanikolaou_2013_organization_capital]])

### §7.3 Q79 — Cop NDX-Spesifik R&D-Intensive Kalibrasyonu

**Methodology**: Cop = REVT − COGS − SG&A; **SG&A R&D purging** (FAANG/biotech firmalarda R&D giderleştirme yapay düşük Cop'u düzeltir); SG&A − R&D expense purged Cop variant Faz 3 implementation custom

### §7.4 Q82 — MGMT+PERF NDX-Spesifik R&D-Intensive

**Methodology**: 
- Cluster 1 (MGMT): asset growth + I/A FAANG R&D capitalization YOK → yapay yüksek; intangibles-aware ΔTotalAssets adjustment
- Cluster 2 (PERF): GP/A + ROA FAANG R&D giderleştirme → yapay düşük; numerator R&D-aware adjustment

### §7.5 F Bloğu 4-Katmanlı Paralel Implementation

| Katman | Methodology | Q kanal |
|--------|-------------|---------|
| Knowledge | Lev-Sougiannis perpetual inventory R&D capital industry-spesifik δ | Q73 + Q79 + Q82 |
| Organization | Eisfeldt-Papanikolaou full SG&A δ=15% **VEYA** Peters-Taylor θ=0.30 (Q60 horse race) | Q73 + Q79 |
| Total | Peters-Taylor q^tot proxy V/(K_phy + K_int) | Q73 |
| Application | Lev-Srivastava adjusted HML methodology | Q56 |

---

## §8 Faz 3 Sertifika Kriter #6-9 İlerleme Planı

| Cycle | İş | Sertifika kriter |
|-------|-----|-------------------|
| **Cycle 41** | Data pipeline §1 + Code repository §2 başlangıç | #6 (Chen-Zimmermann + JKP + WRDS) |
| **Cycle 42** | Factor selection §3 üç paralel methodology + 13 theme cluster §4 | #7 + #8 |
| **Cycle 43** | Reporting §6 DSR + walk-forward + bootstrap + üç (+1) alternative weighting §5 sensitivity | #9 |
| **Cycle 44** | LSV 1994 ingest (opsiyonel; Tier 1 #7) + post-2020 OOS protocol | (kriter yok; Faz 3 seçici ingest 5. paper opsiyonel) |
| **Cycle 45+** | Backtest sonuç değerlendirmesi + v1 → v2 evrim revize karar | **#10 opsiyonel** + Faz 3 sertifika TAM/YUMUŞAK karar |

### §8.1 Faz 3 Sertifika Kriter Mapping

[[CLAUDE.md]] §7 Faz 3 schema 10/10 yapısal kriter:
- 1 (sp500_v1) ✅ Cycle 32
- 2 (nasdaq100_v1) ✅ Cycle 33
- 3 (known_weaknesses) ✅ Cycle 34
- 4 (backtest_spec finalize) → progressive (Cycle 35-39 sertleştirme; Cycle 40 §11.5 + skeleton açma)
- 5 (Faz 3 seçici ingest 4-6 paper) → 4/4-6 ✅ Cycle 35-39
- **6 (backtest implementation)** → Cycle 41-43 hedef
- **7 (üç paralel methodology factor selection)** → Cycle 42 hedef
- **8 (13 theme cluster + tangency)** → Cycle 42 hedef
- **9 (DSR + walk-forward + bootstrap)** → Cycle 43 hedef
- 10 (v1→v2 opsiyonel) → Cycle 45+ backtest sonrası karar

---

## İlgili Sayfalar

### Parent + Sister Methodology
- [[methodology/backtest_spec]] §1-9 (parent; theoretical infrastructure)
- [[methodology/data_sources]] §1-7 (sister; data infrastructure pointer)

### Strategy Specs
- [[strategies/sp500_v1]] §5 Backtest Implementation Roadmap
- [[strategies/nasdaq100_v1]] §5 Backtest Implementation Roadmap
- [[strategies/known_weaknesses]] §3.13 NDX Intangibles Dörtlü Konsolidasyonu (§7 cross-link)

### Meta
- [[meta/handoff_faz3]] §5 Cycle 41-43 yol haritası
- [[CLAUDE.md]] §7 Faz 3 schema 10/10 sertifika kriter

### Faz 3 Seçici İngest Anchor Papers
- [[papers/hou_xue_zhang_2015_q_factor]] (Cycle 35; q-factor 5. paralel methodology)
- [[papers/fama_french_2008_dissecting_anomalies]] (Cycle 37; size-partition methodology Q14 ANCHOR)
- [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] (Cycle 38; Cop methodology)
- [[papers/stambaugh_yuan_2017_mispricing_factors]] (Cycle 39; Stambaugh-Yuan 20/80 4. methodology choice)

### Concepts
- [[concepts/post_publication_decay]] dört darbe sentez tablosu
- [[concepts/multiple_testing]] 3 paper × üç paralel methodology aile
- [[concepts/anomaly_replication]] HXZ + JKP iki paralel
- [[concepts/q_factor_model]] q-factor model 5. paralel methodology
- [[concepts/intangibles_adjusted_accounting]] F bloğu 4-katmanlı methodology hierarchy
- [[concepts/backtest_overfitting]] DSR + 5-input variable

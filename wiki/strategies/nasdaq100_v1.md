---
type: strategy
version: v1
evren: nasdaq100
status: formal_spec
predecessor: strategies/v1_draft (§2 NDX)
sister_spec: strategies/sp500_v1
backtest_run: false
opened: 2026-05-02
phase: faz_3_cycle_33
basis: 24_papers_2_methodology_v1_draft_synthesis
purpose: "NDX winner identification formal spec; tech-heavy intangibles-aware methodology"
---

# strategies/nasdaq100_v1 — NDX Winner Identification Formal Spec

> 📝 **Cycle 33 Faz 3 ikinci formal spec.** sp500_v1 (Cycle 32 ✓)
> paterninin paralel uygulaması; NDX-spesifik tasarım kararları
> ([[strategies/sp500_v1]] §1-7 paterni; bu doküman F bloğu
> 4-katmanlı intangibles-aware methodology + 5-theme FAANG profile +
> capped VW ZORUNLU mega-cap kontrolü ek katmanları).

> ⚠️ **Backtest çalıştırılmadı.** Tüm performance projeksiyonları
> literatür rakamlarının decay-adjusted türevi; somut backtest çıktısı
> Faz 3 implementation (Cycle 41-43) sonrası eklenecek. **Decay
> multiplier ×0.50 NDX agresif** (limited arbitrage Q29; sp500 ×0.65
> standard'dan farklı; MP [Tablo 8] büyük/likit firmalarda decay
> agresif çift darbe).

---

## §1 Universe & Sample Definition

### §1.1 Universe

| Item | Spec |
|------|------|
| **Index** | Nasdaq 100 (top 100 non-financial Nasdaq-listed) |
| **Wiki amaç evreni map'i** | NDX top 100 ≈ Israel-Moskowitz size Q5 üst yarısı (largest 20% NYSE breakpoint); FAANG profile MP [Tablo 8] limited arbitrage büyük/likit/divid-payer/düşük-idio profilinin ucu ([[papers/mclean_pontiff_2016_post_publication_decay]]) |
| **Index reconstitution** | Annual June rebalans + quarterly review (Nasdaq methodology); reconstitution-aware survivorship correction |
| **Mega-cap concentration** | **Kritik özellik**: Apple/MSFT/Google/Nvidia/Meta/Tesla FAANG-grubu NDX %15-20+ ([[papers/jensen_kelly_pedersen_2023_replication_crisis]] [s.3 fn 3] Nokia Finland %70+ paterni paralel) |
| **Sektör concentration cap** | GICS Level-2 max 40%; **Information Tech max 70%** (NDX zaten tech-tilted; sektör neutralization NDX amacıyla çelişir; sp500'de Level-1 max 25%'ten farklı) |

### §1.2 Sample Definition (NDX-spesifik 2000-2020)

**İki ayrı dönem (sp500 paterni; NDX-spesifik baseline farkı):**

| Dönem | Yıl | Statü | Gerekçe |
|-------|-----|-------|---------|
| **Baseline** | **2000-2020** | In-sample anchor + modern dönem JKP sertleştirme | NDX yapısal genişleme 1985+; pre-2000 NDX top 100 farklı kompozisyon (mega-cap tech öncesi); FAANG era 2000+ modern dönem; JKP sample sonu 2020 ([[papers/jensen_kelly_pedersen_2023_replication_crisis]]) |
| **Out-of-sample test** | **2021-2024** | OOS sensitivity (FAANG/AI era) | Wiki paperlarının dışı (JKP sample sonu 2020); Faz 3 implementation backtest sonrası değerlendirilir; post-2020 modern replikasyon Faz 3 custom requirement |

**sp500 farkı**: sp500 1980-2020 baseline (Compustat coverage standart); NDX 2000-2020 baseline (yapısal genişleme + FAANG era).

### §1.3 Three-Weighting Methodology Alternatives

| Methodology | Spec | Anchor | Faz 3 statü NDX |
|-------------|------|--------|------------------|
| Pure VW | HXZ 2020 baseline (NYSE-VW saf) | [[papers/hou_xue_zhang_2020_replicating_anomalies]] | Sensitivity test; **mega-cap distortion riski** |
| FF half-weight | FF1993 paterni (büyük/küçük 50-50) | [[papers/famafrench1993_three_factor]] | Sensitivity test |
| **Capped VW** ⭐⭐ | NYSE 80th percentile winsorize | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] | **Faz 3 ZORUNLU** (mega-cap %15-20+ concentration kontrolü) |

**Faz 3 baseline tercih: capped VW ZORUNLU** (sp500'de tercih aday; NDX'te zorunlu). Gerekçe: Apple/MSFT/Google/Nvidia/Meta/Tesla FAANG-grubu mega-cap concentration distortion kritik; JKP methodology natural fit ([[methodology/data_sources]] §5); Nokia Finland %70+ paterni JKP [s.3 fn 3] paralel.

---

## §2 Factor Inclusion Specification

### §2.1 Theme Allocation (5 dominant FAANG profile; JKP 13 universal'den)

| # | Theme | Wiki anchor signal | Allocation weight | Direction |
|---|-------|---------------------|---------------------|-----------|
| 1 | **Quality** | [[factors/QMJ]] 4-dimension z-score + Asness QARP composite | Yüksek | Long high |
| 2 | **Profitability** | G & V/P binary intersection + [[factors/Gross_Profitability]] GP/A standalone | Yüksek | Long high (FAANG yüksek GP/A; FGX DS-sig) |
| 3 | **Profit Growth** | [[factors/G_Score]] industry-median 8-component (Mohanram NASDAQ partition paterni) | Yüksek | Long high (NDX growth-tilted natural fit) |
| 4 | **Investment\*** ⭐ | [[factors/Organization_Capital]] OC factor signal + R&D-to-market overlay + adjusted Bm intangibles-aware (F bloğu 4-katmanlı) | Yüksek | Long high (NDX-spesifik kritik) |
| 5 | **Value** | Adjusted HML intangibles-aware Bm rebuild ([[papers/lev_srivastava_2020_value_failure]] anchor; vanilla HML reject) | Orta | Long high (F bloğu 4-katmanlı) |

**8 theme NDX-relevant değil** (universal'den; Q69 paralel):
- Seasonality (FAANG profile için marjinal)
- Leverage (NDX low leverage; theme zaten low)
- Low risk (NDX high beta tech)
- Momentum (NDX overlay opsiyonel; sp500'de path D ama NDX'te 5-theme dışı)
- Size (NDX zaten large-cap; size theme N/A)
- Skewness* (FAANG positive skew; theme tersine)
- Debt Issuance* (NDX low debt; theme zaten low)
- Accruals* (Sloan filter; signal layer F bloğu içinde değil; standalone path değil)

**Reject** (theme allocation dışı; v1_draft §2.B inheritance):
- Vanilla HML standalone ([[papers/lev_srivastava_2020_value_failure]] post-2010 NEGATIVE + [[papers/israel_moskowitz_2013_shorting_size_time]] size-conditional)
- SMB vanilla ([[meta/open_questions]] Q11 fully-answered **ASTERISK üç-paper sertleştirme**: Cycle 19 Asness QMJ controlling for QMJ → SMB α=64bps t=6.39 + Cycle 22 Israel-Moskowitz 86-yıl size-conditional + **Cycle 39 Stambaugh-Yuan modified SMB ~2x premium** middle-group methodology mispricing-immune; Cycle 40 §11.5 propagation asimetri kapatıldı sp500_v1 paterni paralel)
- F-Score standalone large-cap (BM-Q5 only kalibre; NDX growth-tilted uyumsuz)
- RMW Ope (HXZ q-factor INSIG; FGX DS-sig methodology farkı [[factors/RMW]]; QMJ Profitability composite tercih)

### §2.2 Composite Score Formülleri (5 path)

**Path A — Quality (QMJ + QARP)**:
```
QMJ_signal  = top quintile of QMJ 4-dimension z-score composite
QARP_signal = top quintile of (QMJ_z - log(P/B))   # Asness QARP framework
Path_A_long = QMJ_signal AND QARP_signal
```

**Path B — Profitability (G&V/P binary + GP/A standalone)**:
```
G_V_P_signal = [G-Score top quintile binary] AND [V/P top quintile binary]
GP_A_signal  = top quintile of GP/A standalone
Path_B_long  = G_V_P_signal OR GP_A_signal   # union (ya G&V/P ya GP/A)
```

**Path C — Profit Growth (Mohanram NASDAQ partition paterni)**:
```
G_Score = Σ(8 binary components industry-median: profitability + cash flow + accruals + earnings stability + ...)
Path_C_long = top quintile of G-Score (industry-median NDX partition)
```

**Path D — Investment* (R&D-to-market + OC factor; NDX-spesifik kritik)**:
```
Rdm        = R&D / Market_equity   # HXZ 4/4 hayatta kalan q-factor signal
OC_signal  = industry-relative OC quintile (Eisfeldt-Papanikolaou full SG&A δ=15% perpetual inv)
Path_D_long = top quintile of Rdm AND top quintile of OC_signal
```

**Path E — Value (adjusted HML; F bloğu 4-katmanlı)**:
```
adjusted_Bm = (Book_equity + K_knowledge + K_organization + K_external) / Market_equity
              # K_knowledge = Lev-Sougiannis perpetual inventory (industry-spesifik δ pharma 9 + scientific 5 yıl)
              # K_organization = Eisfeldt-Papanikolaou full SG&A δ=15% VEYA Peters-Taylor θ=0.30 (Q60 horse race)
              # K_external = Compustat intan field
total_q     = Market_value / (K_phy + K_int)   # Peters-Taylor Eq.9
Path_E_long = top quintile of adjusted_Bm    # vanilla HML reject sonrası
```

### §2.3 Forensic Filter

**Beneish M-Score** ([[factors/M_Score]]):
- Cutoff: `M-Score > -2.84` → suspect manipulator → REJECT
- Prior `.01` **CONSERVATIVE** (NDX tech firma high SGI + AQI false positive Q47 paralel; sp500 `.025` default'tan farklı)
- Q47 sensitivity test FAZ 3 implementation (cutoff range -2.84 ↔ -2.22)

### §2.4 Long Portfolio Construction

```
eligible_pool   = NDX top 100 ∩ (NOT Beneish flagged at .01 conservative)
candidate_long  = eligible_pool ∩ (Path_A ∪ Path_B ∪ Path_C ∪ Path_D ∪ Path_E)
final_long      = top 20-30 stocks of candidate_long, weighted by:
                  - capped VW (NYSE 80th percentile winsorize) ZORUNLU
                  - 5-theme balanced allocation
                  - GICS Level-2 max 40% concentration cap
                  - Information Tech max 70% (NDX zaten tech-tilted)
```

### §2.5 F Bloğu 4-Katmanlı Intangibles-Aware Methodology (NDX-spesifik CORE)

> 📝 **NDX-spesifik yeni alt-bölüm.** sp500'de Path C tek satır
> (adjusted HML θ=0.30); NDX'te CORE infrastructure F bloğu
> 4-katmanlı methodology hierarchy ([[concepts/intangibles_adjusted_accounting]]
> Cycle 25 sertleştirme).

| Katman | Methodology | Anchor | NDX role |
|--------|-------------|--------|----------|
| **1. Knowledge** | Lev-Sougiannis perpetual inventory R&D capital (industry-spesifik δ) | [[papers/lev_sougiannis_1996_rd_capitalization]] [Tablo 1+5] | F bloğu methodology infrastructure |
| **2. Organization** ⭐ | Eisfeldt-Papanikolaou full SG&A δ=15% **VEYA** Peters-Taylor θ=0.30 partial allocation | [[papers/eisfeldt_papanikolaou_2013_organization_capital]] (factor portfolio direct evidence) + [[papers/peters_taylor_2017_intangible_capital]] | F bloğu factor portfolio anchor; **Q60 horse race** Faz 3 implementation iki alternative sensitivity test |
| **3. Total** | Peters-Taylor q^tot = Market_value / (K^phy + K^int) | [[papers/peters_taylor_2017_intangible_capital]] [Eq.9] | F bloğu total q proxy |
| **4. Application** | Lev-Srivastava adjusted HML methodology (39 yılın 34'ünde conventional'ı geçer) | [[papers/lev_srivastava_2020_value_failure]] [Figure 1] | F bloğu post-2010 application |

**R&D-to-market overlay** (HXZ 2020 4/4 hayatta kalan; NDX-spesifik Cycle 13):
- Rdm = R&D_expense / Market_equity (yıllık)
- q-factor alpha 0.7%/ay sig dört darbenin TAMAMINDA hayatta kalan ([[concepts/post_publication_decay]] dört darbe sentez tablosu)

---

## §3 Methodology Specification

### §3.1 Rebalance Protocol (sp500 paterni)

| Item | Spec | Anchor |
|------|------|--------|
| Frekans | Annual June | [[methodology/backtest_spec]] §2.1 |
| Accounting lag | 4-month (fiscal year-end + 4 ay) | [[papers/famafrench1993_three_factor]] convention |
| Reconstitution | Annual June rebalans + quarterly review | §1.1 (Nasdaq methodology) |

### §3.2 Statistical Filter (Üç Paralel Methodology Aile; sp500 paterni)

Factor inclusion için **en az iki paralel methodology'de sig** zorunlu:

| Layer | Methodology | Cutoff | Anchor |
|-------|-------------|--------|--------|
| 1 | HLZ frequentist Bonferroni/BHY | `\|t\| > 3.0` BHY 1% | [[papers/harvey_liu_zhu_2016_multiple_testing]] |
| 2 | FGX frequentist DS LASSO | DS-sig 150-factor library | [[papers/feng_giglio_xiu_2020_factor_zoo]] |
| 3 | JKP Bayesian Empirical Bayes | hierarchical model sig+ | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] |

### §3.3 Replication-Robust Filter (İki Paralel Methodology; sp500 paterni)

| Lens | Methodology | Anchor |
|------|-------------|--------|
| 1 | HXZ NYSE-VW (q-factor span) | [[papers/hou_xue_zhang_2020_replicating_anomalies]] |
| 2 | JKP capped VW (Bayesian Empirical Bayes hierarchical) | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] |

### §3.4 Multi-Theme Allocation Framework (5 NDX dominant)

[[papers/jensen_kelly_pedersen_2023_replication_crisis]] 13 theme universal'den NDX 5 dominant subset (Q69 NDX-spesifik subsample decomposition):
- Quality + Profitability + Profit Growth + Investment* + Value
- Tangency portfolio analysis NDX subsample re-estimation Faz 3 implementation
- 8 theme NDX-relevant değil (§2.1 dokümante)

### §3.5 Reporting Protocol (Üçlü + İki Metric; sp500 paterni)

| Metric | Spec | Anchor |
|--------|------|--------|
| **DSR** | Deflated Sharpe Ratio | [[papers/bailey_lopezdeprado_2014_deflated_sharpe]] |
| **Alpha t-stat** | vs q5 model + Carhart 4F | [[methodology/backtest_spec]] §3.2 |
| **Decay-adjusted spread** | conservative ×0.50 NDX agresif (limited arbitrage Q29) + JKP %85 sensitivity reference | §4 |
| **Factor mean return** ⭐ | iki ayrı metric (FGX SDF loading vs risk premium ayrımı) | [[papers/feng_giglio_xiu_2020_factor_zoo]] [s.22] |
| **SDF loading** ⭐ | iki ayrı metric (factor pricing contribution) | [[papers/feng_giglio_xiu_2020_factor_zoo]] + [[papers/jensen_kelly_pedersen_2023_replication_crisis]] |

### §3.6 NDX-Spesifik Methodology Nüansları

> 📝 NDX-spesifik yeni alt-bölüm. sp500'de yok.

| Nüans | Spec | Anchor |
|-------|------|--------|
| **Tech firma R&D-arî GP/A numerator** | Q56 paralel; FAANG firmalar yüksek GP/A çünkü R&D giderleştirilmiyor numerator'da; intangibles-aware avantaj | [[meta/open_questions]] Q56 + [[factors/Gross_Profitability]] |
| **Intangibles-adjusted denominator** | F bloğu 4-katmanlı adjusted Bm denominator; total q proxy AT yerine | §2.5 + [[papers/peters_taylor_2017_intangible_capital]] [Eq.9] |
| **Sektör compositional shift quarterly review** | NDX top 100 yıllık değişim; quarterly review reconstitution awareness | §1.1 |
| **R&D capital stock vs flow** | Q39 paralel; Lev-Sougiannis [s.133 fn 22] proper capitalization stock 3-yıl flow toplamı'ndan dramatic farklı | [[meta/open_questions]] Q39 |

---

## §4 Expected Performance & Sensitivity

> ⚠️ **Backtest çalıştırılmadı**; aşağıdaki rakamlar literatür
> rakamlarının NDX-agresif decay-adjusted projeksiyonu; **somut
> backtest çıktısı değil**. Her sayının yanında [paper + tablo]
> explicit atfı (Cycle 36 §11.5 consolidation stale claim riski
> önleme; kullanıcı netleştirme Cycle 33).

### §4.1 Conservative Baseline (×0.50 NDX Agresif Multiplier)

**Anchor**: HXZ + MP + FGX conservative-side + NDX limited arbitrage (Q29 paralel; MP [Tablo 8] büyük/likit firmalarda decay agresif çift darbe).

| Bileşen | In-sample | Source | Conservative ×0.50 |
|---------|-----------|--------|---------------------|
| G & V/P combined | +21.45%/yıl | [[papers/li_mohanram2019_quality_value]] [Tablo 7, s.22] all-firms 1973-2012 | ~10.7% |
| G & NEGPEG growth | +20.07%/yıl | [[papers/li_mohanram2019_quality_value]] [Tablo 6, s.20] low-BM subsample 1973-2012 | ~10.0% |
| QMJ 4-factor alpha | 66 bps/ay × 12 ≈ 7.92%/yıl (t=11.20) | [[papers/asness_frazzini_pedersen_2019_qmj]] [Tablo VI Panel A; Tablo A4 large-cap] US 1956-2012 | ~4.0% |
| Adjusted HML (intangibles-aware) | 39 yılın 34'ünde conventional'ı geçer (vanilla HML reject sonrası ek primum) | [[papers/lev_srivastava_2020_value_failure]] [Figure 1] | conventional decay'i absorb |
| R&D-to-market overlay | 0.7%/ay × 12 ≈ 8.4%/yıl q-factor alpha sig | [[papers/hou_xue_zhang_2020_replicating_anomalies]] [Tablo 5] dört darbe 4/4 hayatta kalan | ~4.2% |
| OC factor signal | Carhart 4F α 3.9%/yıl sig 1% | [[papers/eisfeldt_papanikolaou_2013_organization_capital]] [Tablo 4] 1970-2008 | ~2.0% |
| Mohanram NASDAQ partition | +26.4% spread | [[papers/mohanram2005_g_score]] [Tablo 5 Panel D, s.20] 1979-1999 | (post-2000 OOS caveat §6 madde 2) |
| **TOPLAM baseline range** | — | — | **8-13%/yıl** |

### §4.2 Anti-Conservative Upper Bound (JKP %85 Sensitivity Reference)

**Anchor**: JKP Bayesian Empirical Bayes hierarchical %85 replication anti-conservative-side ([[meta/contradictions]] §3 resolution).

| Bileşen | In-sample | Source | Anti-conservative JKP %85 |
|---------|-----------|--------|----------------------------|
| G & V/P combined | +21.45%/yıl | [[papers/li_mohanram2019_quality_value]] [Tablo 7, s.22] | ~18.2% |
| G & NEGPEG growth | +20.07%/yıl | [[papers/li_mohanram2019_quality_value]] [Tablo 6, s.20] | ~17.1% |
| QMJ 4-factor alpha | 7.92%/yıl | [[papers/asness_frazzini_pedersen_2019_qmj]] [Tablo VI; Tablo A4] | ~6.7% |
| R&D-to-market overlay | 8.4%/yıl | [[papers/hou_xue_zhang_2020_replicating_anomalies]] [Tablo 5] | ~7.1% |
| OC factor signal | Carhart 4F α 3.9%/yıl | [[papers/eisfeldt_papanikolaou_2013_organization_capital]] [Tablo 4] | ~3.3% |
| **TOPLAM upper bound range** | — | — | **16-21%/yıl** |

### §4.3 Sensitivity Range

**Range 2x**: 8-13% conservative ↔ 16-21% anti-conservative — methodology choice'a aşırı duyarlı (Cycle 27 ~50pp gap kanıt; [[meta/contradictions]] §3).

**Methodology choice sensitivity test**: pure VW + FF half-weight + capped VW (üç alternative; §1.3; NDX'te capped VW ZORUNLU mega-cap kontrolü).

---

## §5 Backtest Implementation Roadmap

### §5.1 Data Sources (sp500 paterni + NDX-spesifik)

[[methodology/data_sources]] §1-3 üç paralel kaynak:

| # | Kaynak | Methodology | NDX-spesifik nüans |
|---|--------|-------------|---------------------|
| 1 | Chen-Zimmermann 2022 Open Asset Pricing Database | Pure replication ~100% | NDX subsample re-estimation gerekli (CRSP all-stocks default) |
| 2 | JKP 2023 GlobalFactor code repository | Bayesian Empirical Bayes %85 | GitHub bkelly-lab/GlobalFactor + custom NDX subsample 13 theme NDX-spesifik decomposition (Q69 paralel) |
| 3 | WRDS open-source access | CRSP + Compustat raw feed | **Q72 paralel: NDX-spesifik data feed configuration** (top 100 non-financial Nasdaq sub-universe filtering; index reconstitution annual June + quarterly review) |

### §5.2 Code Repository Strategy

- **JKP bkelly-lab/GlobalFactor**: 153 factor × 93 country implementation; Bayesian Empirical Bayes hierarchical model + 13 theme cluster
- **Custom NDX subsample**: capped VW NYSE 80th percentile winsorize + NDX top 100 non-financial reconstitution + 5-theme allocation + F bloğu 4-katmanlı adjusted Bm rebuild + Q60 horse race
- **Walk-forward 4-fold expanding window**: 2000-2005 / 2005-2010 / 2010-2015 / 2015-2020 (sp500 5-fold'dan farklı; NDX baseline 2000+ kısa)
- **Bootstrap**: 1000-iter CI
- **DSR-corrected Sharpe protocol**: Bailey-LdP 5 input variable

### §5.3 Performance Hedefler vs Faz 3 Sertifika Kriterleri

[[CLAUDE.md]] §7 Faz 3 sonu sertifika 10/10 yapısal kriter; nasdaq100_v1 backtest implementation:

| Kriter | nasdaq100_v1 spesifik |
|--------|------------------------|
| 2 (formal spec) | ✅ BU DOKÜMAN |
| 4 (backtest spec finalize) | [[methodology/backtest_spec]] §1-9 + NDX-spesifik §6 F bloğu 4-katmanlı |
| 5 (backtest implementation) | Cycle 41-43 hedef; üç alternative weighting + Q60 horse race iki sensitivity test |
| 6 (HLZ + FGX + JKP üç paralel methodology) | §3.2 |
| 7 (13 theme cluster + tangency portfolio NDX subsample) | §3.4 (5 NDX dominant) |
| 8 (DSR-corrected + walk-forward + bootstrap) | §3.5 + §5.2 |

### §5.4 Out-of-Sample Test Protocol (2021-2024)

- 2000-2020 baseline parametrelerle 2021-2024 holdout test
- FAANG/AI era performance (post-Bitcoin/AI boom; NDX Apple/MSFT/Google/Nvidia/Meta/Tesla 2021-2024 dramatic moves)
- Post-2020 modern replikasyon Faz 3 custom (JKP sample dışı)
- v1 → v2 evrim aday: backtest sonrası v1 spec güncellemesi gerekirse historic preservation pattern (Cycle 30 origin)

---

> 📝 **Cycle 35 ek**: q-factor model formal origin
> [[papers/hou_xue_zhang_2015_q_factor]] (Cycle 35 ✓) §3.2 statistical
> filter ek katman (5. paralel methodology HXZ q-factor span direct
> test); [[factors/I_A]] + [[factors/ROE]] yeni factor entity cross-link
> (Path D Investment* theme NDX-spesifik kritik OC factor + R&D-to-
> market overlay paralel; Path B Profitability theme G&V/P + GP/A);
> §2.5 F bloğu 4-katmanlı methodology q-factor span kontrolü ek katman
> (intangibles-aware Bm rebuild q-factor traditional accounting'tan
> ortogonal; Q73 yeni q-factor intangibles-aware genişletme aday Faz 3
> implementation custom modification).

> 📝 **Cycle 37 ek**: FF 2008 size-partition methodology origin
> [[papers/fama_french_2008_dissecting_anomalies]] (Cycle 37 ✓) §1.1
> NDX top 100 mega-cap ≈ FF 2008 big-stocks üst yarısı (NYSE >50th
> percentile + mega-cap focus); Q14 fully-answered cross-strategy
> anchor (FF 2008 + Israel-Moskowitz + HXZ 2015 üçlü teyit); §2.1
> Path B Profitability theme G&V/P + GP/A + QMJ composite tercih FF
> 2008 evidence ile sertleştirme (FF 2008 [Tablo II] only small grup
> hedge returns sig + among profitable firms positive relation); Path
> D Investment* theme NDX FAANG profile + R&D-to-market overlay +
> OC factor F bloğu 4-katmanlı methodology FF 2008 traditional
> accounting'tan ortogonal Q73 paralel.

> 📝 **Cycle 38 ek**: Ball-GLN Cop methodology origin
> [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]
> (Cycle 38 ✓) §2.1 Path B Profitability theme Cop standalone +
> [[factors/Cop]] yeni entity; Profitability zinciri 4-paper × 7-yıl
> methodology hierarchy 4. halka NDX implementation; **Q79 yeni
> NDX-spesifik kritik caveat**: Cop = REVT − COGS − SG&A; SG&A R&D
> dahil → FAANG/biotech firmalarda R&D giderleştirme Cop'u **yapay
> düşürür** (Apple/Microsoft/Google/Nvidia/Meta/Tesla R&D-intensive);
> F bloğu paralel intangibles-aware Cop modification Faz 3
> implementation custom (Q56 + Q73 paterni paralel; SG&A R&D purging
> + R&D capital adjusted Cop NDX-tailored); §2.5 F bloğu 4-katmanlı
> methodology Cop intangibles-adjusted entegrasyonu Q79 paralel
> Faz 3 Cycle 41+ implementation karar.

> 📝 **Cycle 39 ek**: Stambaugh-Yuan composite mispricing scoring
> paradigma [[papers/stambaugh_yuan_2017_mispricing_factors]] (Cycle
> 39 ✓) §2.1 multi-theme allocation formal cross-link + [[factors/MGMT]]
> + [[factors/PERF]] yeni factor entity; **Q82 yeni NDX-spesifik
> kritik caveat**: Cluster 1 (MGMT) asset growth + I/A FAANG R&D
> capitalization YOK traditional accounting → R&D-intensive firmalarda
> yapay yüksek I/A + asset growth (Q73 paralel I/A intangibles-aware
> genişletme aday); Cluster 2 (PERF) GP/A + ROA FAANG R&D giderleştirme
> yapay düşük profitability (Q56 + Q79 paralel); F bloğu paralel
> intangibles-aware MGMT/PERF modification Faz 3 implementation
> custom; **Q56+Q73+Q79+Q82 NDX intangibles dörtlü konsolidasyonu**
> Cycle 40 §11.5 ZORUNLU consolidation pass'de nasdaq100_v1 §6 +
> known_weaknesses §3 propagation kontrol (Q75 propagation pattern
> paralel kullanıcı request); §2.5 F bloğu 4-katmanlı methodology
> MGMT/PERF intangibles-adjusted entegrasyonu Q82 paralel Faz 3
> Cycle 41+ implementation karar.

## §6 Known Weaknesses

> 📝 [[strategies/v1_draft]] §2.F formalize 11 madde + numbered formal list.
>
> 📝 **Cycle 34 cross-strategy formal registry**: [[strategies/known_weaknesses]]
> ✓ açıldı; NDX-spesifik weakness'ler §3 (Q3 + Q29 + Q47 + Q56 + Q60
> + Q67 + Q69 + Q72 + Q39 + 100-stock diversification limit + tech
> concentration + pre-2000 NDX kompozisyon) migrate edildi; cross-
> strategy weakness'ler §1 + methodology choice sensitivity §4 +
> acknowledged-but-not-addressed §5 wiki-level registry'de formalize.

1. **Modern data partial → TAM KAPANMA + post-2020 OOS** (§1.2 + §5.4): JKP sample sonu Dec 2020; 2021-2024 wiki paperları dışı, Faz 3 custom modern replikasyon ile değerlendirilir; FAANG/AI era out-of-sample.

2. **Mohanram sample 1979-1999 post-2000 out-of-sample** ([[meta/open_questions]] Q3): G-Score NASDAQ partition +26.4% [[papers/mohanram2005_g_score]] [Tablo 5 Panel D, s.20] 25 yıl out-of-sample (FAANG era 2008-2024 mega-cap tech yükselişi); Li-Mohanram 2019 partial-stronger 2000-2012 ama post-2014 hala OOS.

3. **NDX 100-stock sample küçük; portfolio diversification limit**: top 20-30 stocks zorunlu (sp500 30-50'den farklı); concentration risk yüksek; idiosyncratic volatility yüksek.

4. **Tech concentration extreme (Information Tech 60-70% NDX)**: sektör neutralization NDX amacıyla çelişir; NDX zaten tech-tilted; GICS Level-2 max 40% + Information Tech max 70% spec (§1.1) NDX uniqueness ile uyumlu.

5. **F bloğu 4-katmanlı methodology Q60 horse race direct empirik test eksik** ([[meta/open_questions]] Q60): Eisfeldt-Papanikolaou full SG&A δ=15% vs Peters-Taylor θ=0.30 partial allocation methodology farkı; Faz 3 implementation iki alternative sensitivity test (Cycle 25 + 27 sertleştirme).

6. **Q47 tech firma Beneish false positive** ([[meta/open_questions]] Q47): NDX tech firma high SGI (revenue growth) + AQI (intangibles) M-Score'u şişirir; cutoff `.01` conservative kalibrasyon ama large-cap kalibrasyon direct empirik test eksik.

7. **Q56 intangibles-aware GP/A modern data implementation eksik** ([[meta/open_questions]] Q56): F bloğu + Profitability zinciri entegrasyonu Faz 3 implementation; FAANG firmalar yüksek GP/A çünkü R&D giderleştirilmiyor numerator'da.

8. **Monthly-orijinal annual-uyarlama primum kaybı sensitivity test edilmedi** ([[meta/open_questions]] Q35 + Q51 + Q57 + **Q75 yeni Cycle 35**): QMJ + UMD + GP/A monthly rebalance orijinal; wiki yıllık. NDX için ek caveat: G-Score industry-median rebalance frekansı sektör compositional shift altında etki edebilir. **Cycle 35 HXZ 2015 [Apx E + s.7 fn 5] direct evidence**: annually-sorted versiyonları momentum + PEAD + IVOL + distress anomalies **TÜMÜYLE INSIG**; Q75 direct empirik kanıt. R&D-to-market overlay (HXZ 2020 4/4 hayatta kalan) + OC factor signal (Eisfeldt-Papanikolaou annual June) annual rebalance OK; ama r_ROE monthly resort zorunluluğu wiki annual frequency hedef için hibrit yapı (r_I/A annual + r_ROE monthly) reconciliation NDX FAANG profile için kritik. **Faz 3 backtest implementation'ın ilk sensitivity test'i bu olmalı.**

9. **R&D capital stock vs flow ölçümü** ([[meta/open_questions]] Q39): Lev-Sougiannis [s.133 fn 22] proper capitalization stock 3-yıl flow toplamı'ndan dramatic farklı; F bloğu Knowledge layer implementation karar.

10. **3. contradictions entry resolution acknowledged** ([[meta/contradictions]] §3): HXZ 2020 vs JKP 2023 dramatic methodology disagreement (~50pp gap; capped VW + 1-month + Bayesian framework methodology choice'lara aşırı duyarlı). Wiki **conservative-side baseline** tercih edilir (HXZ + MP + FGX ×0.50 NDX agresif decay multiplier); **anti-conservative-side framework** (JKP %85 Bayesian Empirical Bayes hierarchical) **varlığı acknowledged** (§4.2 + §4.3 sensitivity range 2x).

11. **Lev-Srivastava ↔ JKP Value theme F bloğu integration** ([[meta/open_questions]] Q67): Value theme methodology disagreement scope-dependent; F bloğu adjusted HML methodology Faz 3 implementation.

12. **NDX-spesifik 13 theme subsample decomposition** ([[meta/open_questions]] Q69): JKP 13 theme universal; NDX 5 dominant theme (Quality + Profitability + Profit Growth + Investment* + Value); 8 theme NDX-relevant değil; Faz 3 implementation NDX subsample re-estimation.

13. **Eksik kalanlar listesi (Faz 3 seçici ingest aday)** — Cycle 35-39 büyük ölçüde KAPANDI:
    - ✅ FF 2008 "Dissecting Anomalies" Cycle 37 (Q14 fully-answered ANCHOR)
    - ✅ Ball-GLN 2016 Cycle 38 (Cop methodology origin + factors/Cop)
    - ✅ HXZ 2015 q-factor origin Cycle 35 (q-factor model formal tanımı + factors/I_A + factors/ROE)
    - ✅ Stambaugh-Yuan 2017 Cycle 39 (mispricing factors + factors/MGMT + factors/PERF)
    - LSV 1994 (Tier 1 #7 opsiyonel Cycle 44)
    - Frankel-Lee 1998 V/P (Tier 1 paywall) + ACM 2023 (Tier 2 #43) hala eksik
    - Frazzini-Pedersen 2013 BAB (Tier 3 #51; Low risk theme placeholder)

14. **NDX Intangibles Dörtlü Konsolidasyonu (Cycle 40 §11.5 propagation)** ⭐ — NDX-spesifik tek-kanal yerine **dörtlü konsolidasyon** olarak ele alınır:
    - **Q56**: Intangibles-aware GP/A FAANG (Cycle 23 Novy-Marx + Cycle 26 FGX + Cycle 38 Ball-GLN; F bloğu + Profitability zinciri entegrasyonu)
    - **Q73**: q-factor intangibles-aware genişletme (Cycle 35 HXZ 2015; r_I/A traditional ΔAT/AT vs intangibles-adjusted)
    - **Q79**: Cop methodology NDX-spesifik R&D-intensive kalibrasyonu (Cycle 38 Ball-GLN; Cop = REVT − COGS − SG&A; SG&A R&D dahil → FAANG/biotech firmalarda R&D giderleştirme **yapay düşük Cop**)
    - **Q82**: MGMT+PERF NDX-spesifik R&D-intensive kalibrasyonu (Cycle 39 Stambaugh-Yuan; Cluster 1 asset growth + I/A FAANG R&D capitalization YOK → **yapay yüksek I/A**; Cluster 2 GP/A + ROA FAANG R&D giderleştirme → **yapay düşük profitability**)

    **Faz 3 implementation custom**: F bloğu 4-katmanlı (Knowledge + Organization + Total + Application) paralel intangibles-aware modification — q-factor I/A (Q73) + Cop SG&A R&D purging (Q79) + MGMT/PERF R&D-aware modification (Q82) + GP/A intangibles-adjusted (Q56) **dört paralel methodology** NDX-tailored revize Cycle 41+ hedef. [[methodology/backtest_implementation_plan]] §7 NDX intangibles dörtlü konsolidasyonu implementation. **Q75 propagation paterni paralel** disiplin (Cycle 36 stale claim fix paterni paralel kullanıcı request Cycle 40).

---

## §7 Cross-references

### Predecessor (HISTORIC + SYNTHESIS)
- [[strategies/v0_draft]] — Cycle 24 historic kayıt (superseded_by v1_draft Cycle 30)
- [[strategies/v1_draft]] — Cycle 30 synthesis; "niye" sorularına cevap; cycle evrim notu + 6 revize gerekçesi

### Sister Spec (Cross-Strategy Karşılaştırma)
- [[strategies/sp500_v1]] — **Cycle 32 ✓ kardeş formal spec**; 7 dominant theme + Fortune 500 GP/V + Israel-Moskowitz long-only UMD overlay; sp500 ↔ NDX karşılaştırma:
  - Theme allocation: 7 vs 5 dominant (NDX FAANG profile concentration)
  - Anchor empirik: Fortune 500 vs Mohanram NASDAQ partition + G&V/P
  - Capped VW: tercih aday vs **ZORUNLU** (mega-cap %5-8 vs %15-20+)
  - Beneish cutoff: `.025` vs **`.01` conservative**
  - Decay multiplier: ×0.65 vs **×0.50 NDX agresif**
  - F bloğu: Path C overlay vs **CORE infrastructure 4-katmanlı**
  - Path sayısı: 4 vs **5** (Investment* NDX-spesifik path)
  - Final long: 30-50 vs **20-30** stocks
  - Sektör cap: GICS L1 max 25% vs **GICS L2 max 40% + Info Tech max 70%**
  - Sample baseline: 1980-2020 vs **2000-2020** (NDX yapısal genişleme)
  - Conservative baseline range: 6-10% vs **8-13%/yıl**
  - Anti-conservative range: 14-18% vs **16-21%/yıl**

### Methodology
- [[methodology/backtest_spec]] §1-9 — backtest mekanizması tek kaynak-of-truth
- [[methodology/data_sources]] §1-7 — modern data infrastructure pointer

### Anchor Papers (24 paper; v1_draft inheritance; NDX-spesifik vurgular)

**F bloğu 4-katmanlı (NDX CORE)**:
- [[papers/lev_sougiannis_1996_rd_capitalization]] — Knowledge katmanı
- [[papers/peters_taylor_2017_intangible_capital]] — Total q proxy
- [[papers/lev_srivastava_2020_value_failure]] — Application; Q1 anchor
- [[papers/eisfeldt_papanikolaou_2013_organization_capital]] — Organization katmanı; factor portfolio direct evidence; Q41 anchor

**Profitability zinciri (4 paper × 7 yıl)**:
- [[papers/novy_marx_2013_gross_profitability]] — GP/A origin
- [[papers/famafrench2015_five_factor]] — RMW Ope
- [[papers/asness_frazzini_pedersen_2019_qmj]] — QMJ Profitability GPOA + QARP framework + Q2 anchor
- [[papers/hou_mo_xue_zhang_2020_security_analysis]] — q5 model lens

**NDX-spesifik anchor**:
- [[papers/mohanram2005_g_score]] — NASDAQ partition +26.4% (Cycle 6)
- [[papers/li_mohanram2019_quality_value]] — G&V/P +21.45% + G&NEGPEG +20.07% modern replikasyon

**Replication / decay / multiple testing (D bloğu)**:
- [[papers/mclean_pontiff_2016_post_publication_decay]] — limited arbitrage [Tablo 8] çift darbe NDX
- [[papers/harvey_liu_zhu_2016_multiple_testing]], [[papers/hou_xue_zhang_2020_replicating_anomalies]], [[papers/bailey_lopezdeprado_2014_deflated_sharpe]], [[papers/feng_giglio_xiu_2020_factor_zoo]], [[papers/jensen_kelly_pedersen_2023_replication_crisis]]

**Foundational + B/C bloğu**:
- [[papers/famafrench1993_three_factor]], [[papers/carhart1997_four_factor]], [[papers/cochrane2011_discount_rates]], [[papers/piotroski2000_f_score]], [[papers/sloan1996_accruals_anomaly]], [[papers/cooper_gulen_ion2018_asset_growth_factor_models]], [[papers/beneish_1999_m_score]]

**E bloğu (large-cap reality)**:
- [[papers/israel_moskowitz_2013_shorting_size_time]] — size Q5 large-cap reality

### Factor Entities
- Quality: [[factors/QMJ]] + [[factors/G_Score]]
- Profitability: [[factors/Gross_Profitability]] + [[factors/RMW]]
- Value: [[factors/HML]] (vanilla reject; adjusted methodology)
- Investment* (NDX-spesifik): [[factors/Organization_Capital]] OC factor signal
- Filter: [[factors/M_Score]]

### Concepts
- [[concepts/intangibles_adjusted_accounting]] — F bloğu 4-katmanlı methodology hierarchy hub (NDX CORE)
- [[concepts/post_publication_decay]] — dört darbe çerçevesi sentez tablosu; NDX limited arbitrage çift darbe
- [[concepts/multiple_testing]] — 3 paper × üç paralel methodology aile
- [[concepts/anomaly_replication]] — replication crisis literatür hattı
- [[concepts/winner_loser_identification]] — B bloğu core kavramı
- [[concepts/fundamental_scoring]] — komposit score paradigması
- [[concepts/value_premium]] — adjusted HML methodology
- [[concepts/factor_zoo]] — Cochrane #1-#3 framing
- [[concepts/backtest_overfitting]] — DSR + 5-input variable

### Meta
- [[meta/handoff_faz3]] — Faz 3 başlangıç (4. handoff; TAM sertifika)
- [[meta/open_questions]] — 72 Q (9 fully-answered + Q3/Q29/Q35/Q39/Q47/Q51/Q56/Q57/Q60/Q67/Q69/Q72 §6 reference)
- [[meta/data_gaps]] — Cycle 22-29 + 32 + 33 sonrası bölümler
- [[meta/contradictions]] — 3 entry (HML evrimi + MP↔HXZ + HXZ↔JKP)
- [[meta/source_tier_list]] — Tier 1-2-3 + Faz 3 seçici ingest adayları (§6 madde 13)

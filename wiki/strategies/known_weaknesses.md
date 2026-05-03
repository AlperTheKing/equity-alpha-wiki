---
type: strategy_meta
status: formal_acknowledgment_registry
opened: 2026-05-02
phase: faz_3_cycle_34
sister_specs: [strategies/sp500_v1, strategies/nasdaq100_v1]
v1_draft_inheritance: §4 cross-strategy comparison
purpose: "Wiki-level cross-strategy weakness registry; Faz 3 implementation öncesi transparent acknowledgment"
---

# strategies/known_weaknesses — Wiki-Level Cross-Strategy Weakness Registry

> 📝 **Cycle 34 Faz 3 üçüncü formal spec.** sp500_v1 (Cycle 32 ✓) +
> nasdaq100_v1 (Cycle 33 ✓) §6 weakness numbered list'lerini birleşik
> wiki-level **acknowledgment registry**'sinde formalize eder. Bu
> doküman Faz 3 implementation öncesi **transparent acknowledgment**
> ve Faz 3 sonu v1 → v2 evrim opsiyonel revize input'u.

> ⚠️ **Strategy-spesifik vs cross-strategy ayrımı net.** §1 her iki
> evrene uygulanan ortak weakness; §2-3 evrene-spesifik (sp500 / NDX
> ayrı); §4 methodology choice sensitivity (Faz 3 implementation
> roadmap); §5 acknowledged-but-not-addressed (Faz 3 implementation
> backlog).

---

## §1 Cross-Strategy Weaknesses (Her İki Evrene Uygulanan)

> 📝 sp500_v1 + nasdaq100_v1 §6 ortak weaknesses; v1_draft §4
> cross-strategy comparison inheritance.

### §1.1 Modern Data Partial → TAM KAPANMA + Post-2020 OOS

**Acknowledgment**: [[methodology/data_sources]] §1-3 üç paralel data kaynağı (Chen-Zimmermann 2022 Open Asset Pricing Database pure replication ~100% + JKP 2023 GlobalFactor code repository Bayesian Empirical Bayes %85 + WRDS open-source access CRSP + Compustat raw feed) Cycle 29 TAM KAPANMA partial; **post-2020 hala out-of-sample** (FAANG/AI 2021-2024).

**Faz 3 implication**: Custom modern replikasyon ile tam kapanma; sp500_v1 §5.4 + nasdaq100_v1 §5.4 OOS test protocol (2021-2024 holdout).

### §1.2 3. Contradictions Entry Resolution Acknowledged

**Acknowledgment**: [[meta/contradictions]] §3 HXZ 2020 ↔ JKP 2023 dramatic empirik fark (~50pp gap); methodology disagreement scope-dependent (capped VW + 1-month + Bayesian framework methodology choice'lara aşırı duyarlı).

**Faz 3 implication**: Wiki **conservative-side baseline** tercih (HXZ + MP + FGX ×0.65 sp500 / ×0.50 NDX agresif decay multiplier); **anti-conservative-side framework** (JKP %85 Bayesian Empirical Bayes hierarchical) varlığı acknowledged sensitivity range 2x reporting (sp500_v1 §4.3 + nasdaq100_v1 §4.3).

### §1.3 Monthly-Orijinal Annual-Uyarlama Sensitivity (Q35 + Q51 + Q57 + Q75)

**Acknowledgment**: QMJ ([[papers/asness_frazzini_pedersen_2019_qmj]]) + UMD ([[papers/carhart1997_four_factor]]) + Novy-Marx GP/A ([[papers/novy_marx_2013_gross_profitability]]) **hepsi monthly rebalance orijinal**; wiki yıllık (CLAUDE.md §1 annual frequency hedef).

**Cycle 35 sertleştirme — Q75 direct empirik kanıt**: [[papers/hou_xue_zhang_2015_q_factor]] [Apx E + s.7 fn 5] **annually-sorted versions of momentum + PEAD + IVOL + distress anomalies DON'T EXIST** — none of high-minus-low portfolios produce mean excess returns or CAPM alphas significantly different from zero. Q35+Q51+Q57 indirect concern (monthly-orijinal annual-uyarlama primum kaybı varsayımı) → **Q75 direct evidence** (annually-sorted momentum/PEAD/IVOL/distress hedge alpha INSIG). UMD overlay annual rebalance varsayımı (sp500_v1 Path D + nasdaq100_v1 momentum overlay opsiyonel) Q75 direct evidence ile **explicit caveat**: HXZ 2015 q-factor model bütünü için r_ROE monthly resort zorunlu; wiki annual frequency hedef için hibrit yapı (r_I/A annual + r_ROE monthly) reconciliation karar.

**Faz 3 implication**: **Backtest implementation'ın ilk sensitivity test'i bu olmalı** (sp500_v1 §6 madde 4 + nasdaq100_v1 §6 madde 8 her ikisinde Cycle 36 §11.5 stale claim fix Q75 propagate edildi); annual uyarlama primum kaybı sensitivity range Faz 3 Cycle 41-43; r_I/A annual + r_ROE monthly hibrit reconciliation Faz 3 backtest implementation karar (custom NDX subsample + WRDS data feed configuration Q72 paralel).

### §1.4 Composite Scores McLean-Pontiff Sample Explicit Yok (Proxy)

**Acknowledgment**: [[papers/mclean_pontiff_2016_post_publication_decay]] aggregate %35 multiplier composite scores (F-Score / G-Score / QMJ / Magic Formula) için explicit listed değil; **proxy** ([[meta/data_gaps]] Cycle 11 placeholder).

**Faz 3 implication**: Composite-spesifik decay direct empirik kanıt eksik; aggregate ×0.65 / ×0.50 multiplier kullanılır; Faz 3 backtest implementation custom composite decay tahmin sensitivity test.

### §1.5 Faz 3 Paywall Paperlar Seçici İngest Aday

**Acknowledgment**: [[meta/handoff_faz3]] §3 + [[meta/source_tier_list]] paywall paperlar Faz 3 seçici ingest aday:
- **FF 2008 "Dissecting Anomalies"** (Tier 1; paywall→preprint; Q14 CMA/RMW direct test)
- **Ball-GLN 2016** (Tier 1 #9; Cop methodology origin standalone)
- **HXZ 2015 q-factor origin** (Tier 1 #3; q-factor model formal tanımı; **Cycle 35 hedef yüksek priori**)
- **Stambaugh-Yuan 2017** (Tier 1 #23; mispricing factors)
- **LSV 1994** (Tier 1 #7; value premium contrarian origin)
- **Frankel-Lee 1998** (Tier 1; paywall; V/P origin)
- **Avramov-Cheng-Metzker 2023** (Tier 2 #43; ML vs Economic Restrictions)

**Faz 3 implication**: Cycle 35 + 37-39 + 44 yol haritası ([[meta/handoff_faz3]] §5).

### §1.6 v0 → v1 → Potential v2 Evrim Historic Preservation Pattern

**Acknowledgment**: [[strategies/v0_draft]] (Cycle 24 historic) → [[strategies/v1_draft]] (Cycle 30 historic Cycle 34 itibariyle) → sp500_v1 + nasdaq100_v1 + known_weaknesses (Cycle 32-34 formal spec'ler) historic preservation pattern (Cycle 30 origin).

**Faz 3 implication**: Backtest implementation (Cycle 41-43) sonrası v1 → v2 opsiyonel revize gerekirse aynı pattern (CLAUDE.md §7 Faz 3 schema 10. madde formalize edildi); v1 historic preservation content **DEĞİŞTİRİLMEZ**.

---

## §2 sp500-Spesifik Weaknesses

> 📝 [[strategies/sp500_v1]] §6 inherit; sp500 evrene özgü.

### §2.1 Q14 RMW/CMA Large-Cap-Only Direct Test — FULLY-ANSWERED (Cycle 37)

**Acknowledgment**: [[meta/open_questions]] Q14; [[papers/israel_moskowitz_2013_shorting_size_time]] HML-spesifik fully-answered (Cycle 22); **Cycle 37 FF 2008 ingest ile Q14 fully-answered ANCHOR**: [[papers/fama_french_2008_dissecting_anomalies]] [Tablo II + IV] asset growth size-conditional direct origin (CMA(big) VW spread -0.02% t=-0.10 INSIG + regression slope big -0.17 t=-0.86 INSIG); profitability sorts hedge returns "weakest" only small grup VW+EW >2σ (RMW Ope size-conditional zayıflığın root'u).

**Üçlü teyit**: FF 2008 (Cycle 37) + Israel-Moskowitz 2013 (Cycle 22; HML 86-yıl size-conditional Q5 INSIG + B/M big-stock 0.17 t=1.79 weakest çift teyit) + HXZ 2015 [s.7] (Cycle 35; "investment effect strong in microcaps... largely absent in big stocks" cross-cite + q-factor size-controlled motivation).

**Faz 3 implication**: sp500_v1 §6 madde 5 + sp500_v1 §2.1 Path D Investment* theme + Path B Profitability theme RMW Ope reject + QMJ composite + GP/A standalone tercih FF 2008 evidence ile sertleştirme; FF15 [s.13] CMA(small) sig vs CMA(big) insig finding'inin direct origin paper'ı dokümante.

### §2.2 Q46 Beneish M-Score Small-Cap-Tilted Sample

**Acknowledgment**: [[meta/open_questions]] Q46; [[factors/M_Score]] Beneish 1999 sample küçük-cap-tilted (74 manipulators 2-digit SIC matched); sp500 large-cap kalibrasyon direct empirik test eksik; cutoff `.025` default sensitivity range ±0.5.

**Faz 3 implication**: sp500_v1 §6 madde 6; Faz 3 backtest implementation cutoff sensitivity test.

### §2.3 7 Dominant Theme Allocation Faz 3 Backtest Sensitivity

**Acknowledgment**: sp500_v1 §2.1 7-theme allocation (Quality + Profitability + Profit Growth + Value + Momentum + Accruals* + Low risk) JKP 13 universal'den; theme weight balanced allocation Faz 3 backtest direct empirik kalibrasyon eksik.

**Faz 3 implication**: 13 theme cluster + tangency portfolio sensitivity test ([[papers/jensen_kelly_pedersen_2023_replication_crisis]]); 3 displaced (Profitability + Investment + Size) joint modeling redundancy Faz 3 implementation.

### §2.4 Pre-1980 Compustat Coverage Incomplete

**Acknowledgment**: sp500_v1 §1.2 sample 1980-2020 baseline; pre-1980 Compustat coverage incomplete (Sloan + CGS + F-Score paterni 1980+ standart accounting period gerekçe).

**Faz 3 implication**: 1962-1979 pre-1980 ek out-of-sample test wiki kapsamı dışı; backtest implementation 1980-2020 baseline + 2021-2024 OOS yeterli.

---

## §3 NDX-Spesifik Weaknesses

> 📝 [[strategies/nasdaq100_v1]] §6 inherit; NDX evrene özgü.

### §3.1 Q3 Mohanram Sample 1979-1999 Post-2000 OOS

**Acknowledgment**: [[meta/open_questions]] Q3; [[papers/mohanram2005_g_score]] [Tablo 5 Panel D, s.20] NASDAQ partition +26.4% sample 1979-1999; **25 yıl out-of-sample** (FAANG era 2008-2024 mega-cap tech yükselişi); Li-Mohanram 2019 partial-stronger 2000-2012 ama post-2014 hala OOS.

**Faz 3 implication**: nasdaq100_v1 §6 madde 2; backtest implementation post-2000 NASDAQ partition modern replikasyon kritik.

### §3.2 Q29 Limited Arbitrage NDX İmplikasyon Çift Darbe

**Acknowledgment**: [[meta/open_questions]] Q29; [[papers/mclean_pontiff_2016_post_publication_decay]] [Tablo 8] büyük/likit firmalarda decay agresif; NDX FAANG profile = MP limited arbitrage profilinin ucu; **çift darbe** (in-sample large-cap zayıf + post-pub decay agresif).

**Faz 3 implication**: NDX decay multiplier ×0.50 agresif (sp500 ×0.65 standard'dan farklı); nasdaq100_v1 §4.1 conservative baseline 8-13%/yıl.

### §3.3 Q47 Tech Firma Beneish High SGI/AQI False Positive

**Acknowledgment**: [[meta/open_questions]] Q47; NDX tech firma high SGI (revenue growth) + AQI (intangibles) M-Score'u şişirir; cutoff `.01` conservative kalibrasyon ama large-cap kalibrasyon direct empirik test eksik.

**Faz 3 implication**: nasdaq100_v1 §6 madde 6; backtest implementation cutoff range -2.84 ↔ -2.22 sensitivity test.

### §3.4 Q56 Intangibles-Aware GP/A FAANG Modern Data Eksik

**Acknowledgment**: [[meta/open_questions]] Q56; FAANG firmalar yüksek GP/A çünkü R&D giderleştirilmiyor numerator'da (intangibles-aware avantaj); F bloğu + Profitability zinciri entegrasyonu Faz 3 implementation eksik.

**Faz 3 implication**: nasdaq100_v1 §3.6 NDX-spesifik nüans (tech firma R&D-arî numerator + intangibles-adjusted denominator); Faz 3 implementation custom GP/A intangibles-aware revize.

### §3.5 Q60 F Bloğu 4-Way Horse Race Direct Empirik Test Eksik

**Acknowledgment**: [[meta/open_questions]] Q60; [[papers/eisfeldt_papanikolaou_2013_organization_capital]] full SG&A δ=15% **vs** [[papers/peters_taylor_2017_intangible_capital]] θ=0.30 partial allocation methodology farkı; Faz 3 implementation iki alternative sensitivity test (Cycle 25 + 27 sertleştirme).

**Faz 3 implication**: nasdaq100_v1 §2.5 F bloğu 4-katmanlı methodology hierarchy Q60 horse race; backtest implementation iki alternative + sensitivity report.

### §3.6 Q67 Lev-Srivastava ↔ JKP Value Theme F Bloğu Integration

**Acknowledgment**: [[meta/open_questions]] Q67; Value theme methodology disagreement scope-dependent ([[papers/lev_srivastava_2020_value_failure]] adjusted HML 39 yılın 34'ü conventional ↔ [[papers/jensen_kelly_pedersen_2023_replication_crisis]] Value theme >75% replicate); F bloğu adjusted HML methodology Faz 3 implementation.

**Faz 3 implication**: nasdaq100_v1 §2.5 Application katmanı Lev-Srivastava methodology; backtest implementation methodology choice.

### §3.7 Q69 13 Theme NDX Subsample Decomposition

**Acknowledgment**: [[meta/open_questions]] Q69; JKP 13 theme universal; NDX 5 dominant theme (Quality + Profitability + Profit Growth + Investment* + Value); 8 theme NDX-relevant değil (§2.1 nasdaq100_v1 dokümante).

**Faz 3 implication**: Faz 3 implementation NDX subsample re-estimation (universal 13 theme NDX-spesifik decomposition); tangency portfolio NDX 5 dominant theme.

### §3.8 Q72 WRDS NDX-Spesifik Data Feed Configuration

**Acknowledgment**: [[meta/open_questions]] Q72; [[methodology/data_sources]] §3 WRDS open-source access CRSP + Compustat raw feed; NDX top 100 non-financial sub-universe filtering + index reconstitution annual June + quarterly review configuration eksik.

**Faz 3 implication**: nasdaq100_v1 §5.1 data sources NDX-spesifik nüans; backtest implementation custom NDX subsample configuration.

### §3.13 NDX Intangibles Dörtlü Konsolidasyonu (Q56+Q73+Q79+Q82) ⭐ Cycle 40 §11.5 Propagation

> 📝 **Cycle 40 §11.5 ZORUNLU consolidation pass propagation** (Q75 Cycle 36 paterni paralel kullanıcı request); NDX intangibles tek-kanal yerine **dörtlü konsolidasyon** olarak ele alınır.

**Acknowledgment**: NDX FAANG profile + R&D-intensive firma yapısı + traditional accounting paterni nedeniyle dört paralel kanaldan intangibles-aware modification gerekir:

| Q | Cycle | Methodology | Etki |
|---|-------|-------------|------|
| **Q56** | 23 Novy-Marx + 26 FGX + 38 Ball-GLN | Intangibles-aware GP/A; F bloğu + Profitability zinciri entegrasyonu | FAANG yüksek GP/A (R&D numerator-out avantaj) |
| **Q73** | 35 HXZ 2015 | q-factor intangibles-aware genişletme; r_I/A = ΔAT/AT traditional vs intangibles-adjusted | NDX FAANG profile q-factor traditional accounting'tan ortogonal |
| **Q79** | 38 Ball-GLN | Cop NDX-spesifik R&D-intensive; Cop = REVT − COGS − SG&A; SG&A R&D dahil | FAANG/biotech R&D giderleştirme **yapay düşük Cop** |
| **Q82** | 39 Stambaugh-Yuan | MGMT+PERF NDX-spesifik R&D-intensive; Cluster 1 asset growth + I/A + Cluster 2 GP/A + ROA | FAANG R&D capitalization YOK → Cluster 1 **yapay yüksek**; Cluster 2 R&D giderleştirme **yapay düşük** |

**Faz 3 implication**: F bloğu 4-katmanlı methodology hierarchy (Knowledge + Organization + Total + Application; Cycle 25 sertleştirme) paralel intangibles-aware modification dört paralel kanal:
1. **GP/A intangibles-adjusted** (Q56) — Profitability zinciri 1. halka modification
2. **q-factor I/A intangibles-aware** (Q73) — q-factor model traditional ΔAT'den intangibles-adjusted
3. **Cop SG&A R&D purging** (Q79) — Profitability zinciri 4. halka modification
4. **MGMT/PERF R&D-aware** (Q82) — Composite mispricing scoring 3. halka modification

**Faz 3 Cycle 41+ hedef**: [[methodology/backtest_implementation_plan]] §7 NDX intangibles dörtlü konsolidasyonu implementation; nasdaq100_v1 §6 madde 14 propagation paralel; Q75 propagation paterni (Cycle 36 stale claim fix) Cycle 40 paterni paralel disiplin.

**Cross-references**: [[strategies/nasdaq100_v1]] §6 madde 14 + §2.5 F bloğu 4-katmanlı + §3.6 NDX-spesifik nüans.

### §3.9 Q39 R&D Capital Stock vs Flow Ölçümü

**Acknowledgment**: [[meta/open_questions]] Q39; [[papers/lev_sougiannis_1996_rd_capitalization]] [s.133 fn 22] proper capitalization stock 3-yıl flow toplamı'ndan dramatic farklı; F bloğu Knowledge layer implementation karar.

**Faz 3 implication**: nasdaq100_v1 §2.5 Knowledge katmanı methodology; backtest implementation stock vs flow sensitivity.

### §3.10 NDX 100-Stock Sample Diversification Limit

**Acknowledgment**: NDX top 100 sample küçük (sp500 500'den 5x küçük); top 20-30 long-only stocks portfolio diversification limit; concentration risk yüksek; idiosyncratic volatility yüksek.

**Faz 3 implication**: nasdaq100_v1 §2.4 final long top 20-30 (sp500 30-50'den farklı); backtest implementation portfolio risk reporting.

### §3.11 Tech Concentration Extreme

**Acknowledgment**: NDX Information Tech %60-70; sektör neutralization NDX amacıyla çelişir (NDX zaten tech-tilted); GICS Level-2 max 40% + Information Tech max 70% spec ([[strategies/nasdaq100_v1]] §1.1) NDX uniqueness ile uyumlu.

**Faz 3 implication**: NDX strategy sektör concentration cap kabul edilen yapısal özellik; backtest implementation sektör risk reporting.

### §3.12 Pre-2000 NDX Top 100 Farklı Kompozisyon

**Acknowledgment**: NDX yapısal genişleme 1985+; pre-2000 NDX top 100 kompozisyon farklı (mega-cap tech öncesi); FAANG era 2000+ modern dönem; nasdaq100_v1 §1.2 sample 2000-2020 baseline (sp500 1980-2020'den farklı).

**Faz 3 implication**: 1985-1999 NDX historic out-of-sample wiki kapsamı dışı; backtest implementation 2000-2020 baseline + 2021-2024 OOS yeterli.

---

## §4 Methodology Choice Sensitivity (Faz 3 Implementation Roadmap)

> 📝 [[methodology/backtest_spec]] §3 + sp500_v1 §3 + nasdaq100_v1 §3
> methodology choice'larının sensitivity test mandatory liste.

### §4.1 Üç Alternative Weighting Mandatory Sensitivity Test

| Methodology | Anchor | sp500_v1 | nasdaq100_v1 |
|-------------|--------|----------|--------------|
| Pure VW | [[papers/hou_xue_zhang_2020_replicating_anomalies]] HXZ baseline | Sensitivity test | Sensitivity test (mega-cap distortion riski) |
| FF half-weight | [[papers/famafrench1993_three_factor]] paterni | Sensitivity test | Sensitivity test |
| Capped VW | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] NYSE 80th percentile winsorize | **Tercih aday** | **ZORUNLU** mega-cap %15-20+ FAANG |

**Faz 3 implication**: Üç alternative report sensitivity range; methodology choice ~50pp gap kanıt ([[meta/contradictions]] §3).

### §4.2 Üç Paralel Statistical Filter Sensitivity (HLZ + FGX + JKP)

| Layer | Methodology | Cutoff | Anchor |
|-------|-------------|--------|--------|
| 1 | HLZ frequentist Bonferroni/BHY | `\|t\| > 3.0` BHY 1% | [[papers/harvey_liu_zhu_2016_multiple_testing]] |
| 2 | FGX frequentist DS LASSO | DS-sig 150-factor library | [[papers/feng_giglio_xiu_2020_factor_zoo]] |
| 3 | JKP Bayesian Empirical Bayes | hierarchical model sig+ | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] |

**Faz 3 implication**: Factor inclusion için **en az iki paralel methodology'de sig** zorunlu; sp500_v1 §3.2 + nasdaq100_v1 §3.2.

### §4.3 İki Paralel Replication-Robust Filter (HXZ + JKP)

| Lens | Methodology | Anchor |
|------|-------------|--------|
| 1 | HXZ NYSE-VW (q-factor span) | [[papers/hou_xue_zhang_2020_replicating_anomalies]] |
| 2 | JKP capped VW (Bayesian Empirical Bayes hierarchical) | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] |

**Faz 3 implication**: Factor hayatta kalmak için **her iki methodology lens'inde sig** tercih (en konservatif standard); sp500_v1 §3.3 + nasdaq100_v1 §3.3.

### §4.4 13 Theme Cluster + Tangency Portfolio Joint Modeling Sensitivity

**Acknowledgment**: [[papers/jensen_kelly_pedersen_2023_replication_crisis]] 13 theme cluster + tangency portfolio; 10/13 themes >75% replicate; **3 displaced** (Profitability + Investment + Size) joint modeling redundancy.

**Faz 3 implication**: sp500 7 dominant theme (universal'den) + NDX 5 FAANG dominant theme (Q69 paralel); tangency portfolio NDX subsample re-estimation; sp500_v1 §3.4 + nasdaq100_v1 §3.4.

### §4.5 Sektör Concentration Cap Farkı

| Strategy | Concentration cap | Gerekçe |
|----------|--------------------|---------|
| sp500_v1 | GICS Level-1 max 25% | 11 GICS Level-1 sektör; balanced allocation |
| nasdaq100_v1 | GICS Level-2 max 40% + Information Tech max 70% | NDX zaten tech-tilted; sektör neutralization NDX amacıyla çelişir |

**Faz 3 implication**: sp500_v1 §1.1 + nasdaq100_v1 §1.1; backtest implementation sektör risk reporting.

---

## §5 Acknowledged But Not Addressed (Faz 3 Implementation Backlog)

> 📝 Wiki-level acknowledgment; Faz 3 implementation sonrası v1 → v2
> opsiyonel revize aday.

### §5.1 Post-2020 (FAANG/AI 2021-2024) OOS Custom Replikasyon

**Acknowledgment**: JKP sample sonu Dec 2020; 2021-2024 wiki paperları dışı; Faz 3 custom modern replikasyon Cycle 41+ implementation backlog.

**Faz 3 implication**: sp500_v1 §5.4 + nasdaq100_v1 §5.4 OOS test protocol (2021-2024 holdout); FAANG/AI era performance backtest sonrası reporting.

### §5.2 Anti-Conservative JKP %85 Baseline'a Göre Over-Promise Riski

**Acknowledgment**: [[papers/jensen_kelly_pedersen_2023_replication_crisis]] %85 Bayesian Empirical Bayes hierarchical anti-conservative-side; wiki **conservative-side baseline** tercih (over-promise riski Cycle 24 muhafazakâr revize karar).

**Faz 3 implication**: Sensitivity range 2x reporting (sp500 6-10% ↔ 14-18%; NDX 8-13% ↔ 16-21%); methodology choice transparent reporting.

### §5.3 v1 → v2 Backtest Sonrası Opsiyonel Revize

**Acknowledgment**: [[CLAUDE.md]] §7 Faz 3 schema 10. madde formalize edildi; backtest implementation (Cycle 41-43) sonrası v1 spec güncellemesi gerekirse historic preservation pattern (Cycle 30 origin).

**Faz 3 implication**: v1 historic preservation content **DEĞİŞTİRİLMEZ**; v2 ayrı dosya (sp500_v2.md + nasdaq100_v2.md) açılır gerekirse; YAML predecessor field cycle-by-cycle evrim notu.

---

## §6 Cross-references

### Sister Specs (Faz 3 Formal Spec'ler)
- [[strategies/sp500_v1]] — Cycle 32 ✓ S&P 500 winner identification formal spec; §6 sp500-spesifik weakness numbered list inherit (§2 buraya migrate)
- [[strategies/nasdaq100_v1]] — Cycle 33 ✓ NDX winner identification formal spec; §6 NDX-spesifik weakness numbered list inherit (§3 buraya migrate)

### Predecessor (HISTORIC)
- [[strategies/v0_draft]] — Cycle 24 historic kayıt
- [[strategies/v1_draft]] — Cycle 30 synthesis; **Cycle 34 historic'e geçti** (üç formal spec sonrası synthesis fonksiyonu absorb; v0_draft Cycle 30 paterni paralel; superseded_by sp500_v1 + nasdaq100_v1 + known_weaknesses üçlü sister spec)

### Methodology
- [[methodology/backtest_spec]] §1-9 — backtest mekanizması tek kaynak-of-truth; §10 known_weaknesses inbound
- [[methodology/data_sources]] §1-7 — modern data infrastructure pointer

### Meta
- [[meta/handoff_faz3]] — Faz 3 başlangıç (4. handoff; TAM sertifika); §3 paywall paperlar Faz 3 seçici ingest aday
- [[meta/contradictions]] §3 — HXZ ↔ JKP entry; cross-strategy reference §1.2
- [[meta/open_questions]] — 72 Q (9 fully-answered + cross-strategy + sp500-spesifik + NDX-spesifik weakness reference; konsolide)
- [[meta/data_gaps]] — Cycle 22-29 + 32 + 33 + 34 sonrası bölümler
- [[meta/source_tier_list]] — Tier 1-2-3 + Faz 3 seçici ingest adayları (§1.5)

### 24 Paper Anchor (v1_draft inheritance)

**Cross-strategy referans (D bloğu epistemik omurga + E bloğu)**:
- [[papers/mclean_pontiff_2016_post_publication_decay]], [[papers/harvey_liu_zhu_2016_multiple_testing]], [[papers/hou_xue_zhang_2020_replicating_anomalies]], [[papers/bailey_lopezdeprado_2014_deflated_sharpe]], [[papers/feng_giglio_xiu_2020_factor_zoo]], [[papers/jensen_kelly_pedersen_2023_replication_crisis]], [[papers/israel_moskowitz_2013_shorting_size_time]]

**sp500 anchor**:
- [[papers/famafrench1993_three_factor]], [[papers/famafrench2015_five_factor]], [[papers/novy_marx_2013_gross_profitability]], [[papers/li_mohanram2019_quality_value]], [[papers/sloan1996_accruals_anomaly]], [[papers/cooper_gulen_ion2018_asset_growth_factor_models]], [[papers/beneish_1999_m_score]], [[papers/piotroski2000_f_score]], [[papers/carhart1997_four_factor]], [[papers/cochrane2011_discount_rates]]

**NDX anchor (F bloğu 4-katmanlı + Profitability zinciri + Quality)**:
- [[papers/lev_sougiannis_1996_rd_capitalization]], [[papers/peters_taylor_2017_intangible_capital]], [[papers/lev_srivastava_2020_value_failure]], [[papers/eisfeldt_papanikolaou_2013_organization_capital]], [[papers/asness_frazzini_pedersen_2019_qmj]], [[papers/mohanram2005_g_score]], [[papers/hou_mo_xue_zhang_2020_security_analysis]]

### 9 Fully-Answered Q (Faz 1: 5 + Faz 2: 4)
Q1 (S&P 500 value post-2000) + Q2 (large-cap quality vs value) + Q5 (post-publication decay anchor) + Q11 (SMB never sig under MT) + Q17 (Cochrane #3 factor zoo) + Q7 (FGX redundancy) + Q41 (F bloğu 4-way horse race) + Q55 (Profitability ailesi) + Q63 (post-2017 modern replikasyon)

### 72 Active Q (Cross-Strategy + Strategy-Spesifik Reference)
- Cross-strategy: Q35, Q51, Q57 (monthly-orijinal annual-uyarlama)
- sp500: Q14 (RMW/CMA), Q46 (Beneish small-cap)
- NDX: Q3, Q29, Q39, Q47, Q56, Q60, Q67, Q69, Q72

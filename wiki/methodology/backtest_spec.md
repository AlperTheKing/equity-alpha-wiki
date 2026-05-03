---
type: methodology
name: backtest_spec
status: skeleton
opened: 2026-05-01
phase: faz_2_cycle_21
sources_basis: 19_papers_16_concepts_13_factors
purpose: "Faz 3 strategy spec'lerinin (s&p500_v1, nasdaq100_v1) ön koşulu; backtest mekaniğinin tek kaynak-of-truth"
---

# methodology/backtest_spec — Backtest Specification (Faz 2 skeleton)

> 📝 **Cycle 21 açılış (Faz 2 yapısal başlangıç).** Bu sayfa Faz 1'in
> 19 paper sayfası + 16 concept + 13 factor entity'sinden derlenmiş
> methodology infrastructure'ın tek dokümana toplanmış halidir.
> Faz 3'te `s&p500_v1.md` + `nasdaq100_v1.md` strategy spec'leri bu
> sayfaya atıfla yazılacak.
>
> **Skeleton statüsü**: Faz 2 ingest'leri (Israel-Moskowitz + FF 2008
> + Novy-Marx + Chen-Zimmermann + JKP 2023 + Eisfeldt-Papanikolaou)
> sonunda bölümler genişler. Cycle 24 4-cycle ardışık consolidation
> pass'inde ilk re-review.
>
> 📝 **Cycle 32 inbound cross-link**: [[strategies/sp500_v1]] formal
> spec §3 (Methodology Specification) bu sayfanın §1-9'una atıfla
> yazılmıştır (rebalance protocol + statistical filter HLZ+FGX+JKP +
> replication-robust HXZ+JKP iki lens + multi-theme allocation +
> reporting protocol DSR+alpha+decay-adjusted+factor mean+SDF loading).
>
> 📝 **Cycle 33 inbound cross-link**: [[strategies/nasdaq100_v1]]
> formal spec §3 (Methodology Specification) bu sayfanın §1-9'una
> atıfla yazıldı + NDX-spesifik §3.6 nüansları (tech firma R&D-arî
> GP/A numerator Q56 + intangibles-adjusted denominator + sektör
> compositional shift quarterly review + R&D capital stock vs flow
> Q39); §6 F bloğu 4-katmanlı methodology hierarchy NDX CORE (sp500'de
> overlay; NDX'te CORE infrastructure); §1.3 capped VW ZORUNLU NDX
> (sp500'de tercih aday; NDX'te zorunlu mega-cap %15-20+ FAANG
> concentration kontrolü).
>
> 📝 **Cycle 34 inbound cross-link**: [[strategies/known_weaknesses]]
> formal cross-strategy acknowledgment registry §4 Methodology Choice
> Sensitivity bu sayfanın §1.3 (üç alternative weighting) + §3.2-3.3
> (üç paralel statistical + iki paralel replication-robust) + §3.4
> (13 theme tangency) bölümlerine atıfla yazıldı; methodology choice
> sensitivity test mandatory liste Faz 3 implementation roadmap;
> sektör concentration cap sp500 vs NDX farkı §4.5 dokümante.
>
> 📝 **Cycle 35 ek**: q-factor model **formal origin tanımı**
> [[papers/hou_xue_zhang_2015_q_factor]] (Cycle 35 ✓ Tier 1 #3 yüksek
> priori) §3 statistical filter + §4.4 replication-robust filter
> sertleştirme: (1) HXZ q-factor lens factor inclusion **5. paralel
> methodology** (HLZ + FGX + JKP statistical + HXZ NYSE-VW + JKP
> capped VW replication-robust + **q-factor span direct test**); (2)
> 4-factor formal tanımı MKT + r_ME + r_I/A + r_ROE; r_ROE monthly
> resort zorunluluğu [HXZ 2015 s.7 fn 5] wiki annual frequency hedef
> hibrit (r_I/A annual + r_ROE monthly) Faz 3 backtest implementation
> karar (Q75 yeni); (3) [[concepts/q_factor_model]] yeni concept
> (Cycle 35) hub sayfa; [[factors/I_A]] + [[factors/ROE]] yeni factor
> entity'ler.
>
> 📝 **Cycle 37 ek**: FF 2008 size-partition methodology origin
> [[papers/fama_french_2008_dissecting_anomalies]] (Cycle 37 ✓ Faz 3
> seçici ingest #2 yüksek priori) §1.3 universe methodology
> sertleştirme: (1) NYSE-VW + microcap-arınmış convention FF 2008
> origin (microcaps ~60% stocks ama ~3% market cap; cross-section
> dispersion of anomaly variables largest in microcaps); HXZ 2015/2020
> + JKP 2023 capped VW paterni FF 2008'den methodology continuity;
> (2) **Q14 fully-answered ANCHOR**: CMA(big) FF15 [s.13] insig
> paterni FF 2008 [Tablo II + IV] direct origin (asset growth slope
> big -0.17 t=-0.86 INSIG; spread big -0.02% t=-0.10 INSIG; -2.97σ
> from micro slope sig size-difference); (3) RMW(big) zayıf hedge
> returns ama positive profitability relation tüm size groups → §5
> factor inclusion list RMW Ope reject + QMJ Profitability composite
> + GP/A standalone tercih sertleştirme; üçlü teyit FF 2008 +
> Israel-Moskowitz 2013 + HXZ 2015 [s.7].
>
> 📝 **Cycle 38 ek**: Ball-GLN Cop methodology origin
> [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]
> (Cycle 38 ✓ Faz 3 seçici ingest #3) §5.1 4/4 hayatta kalan tablosu
> sertleştirme: (1) **Cop formal origin paper** + [[factors/Cop]] yeni
> entity (Profitability zinciri 4. halka standalone); HMXZ Tablo 5
> Cop alpha 0.69%/ay sig + HXZ 2020 Replicating dört darbe 4/4
> hayatta kalan empirical validation Ball-GLN origin'inden methodology
> continuity; (2) **Profitability zinciri 4-paper × 7-yıl methodology
> hierarchy** GP/A → RMW Ope → QMJ GPOA → Cop; sp500_v1 + nasdaq100_v1
> §2.1 Path B Profitability theme RMW Ope reject + Cop standalone
> tercih + QMJ composite Ball-GLN evidence ile sertleştirme (Tablo 5
> RMW^CbOp 4.88%/yr t=6.29 vs RMW^Op 3.25%/yr t=3.65; Tablo 8 4F+Cop
> tangency Sharpe 1.67 ⭐); (3) **Sloan accruals exception complementary**
> Cycle 35 q-factor I/A+ROE size-controlled lens vs Cycle 38 Cop
> accrual-cash flow decomposition lens iki ayrı epistemic framework;
> (4) **Annual rebalance compatible** Ball-GLN [s.7] portfolio sorts
> annual June (HXZ 2015 r_ROE monthly resort zorunluluğu Q75'in
> TERSİ; Cop wiki annual frequency hedef için direct uyumlu); (5)
> Q79 yeni NDX-spesifik R&D-intensive firma kalibrasyonu (Cop = REVT
> − COGS − SG&A; SG&A R&D dahil; FAANG/biotech firmalarda yapay
> düşük Cop Faz 3 implementation custom modification).
>
> 📝 **Cycle 40 ek**: Backtest implementation operational sub-document
> [[methodology/backtest_implementation_plan]] (Cycle 40 §11.5 + backtest
> implementation kickoff) açıldı; operational vs theoretical ayrımı:
> backtest_spec parent theoretical infrastructure (factor inclusion
> criteria + dört darbe filter + üç paralel statistical + Faz 3 ön
> koşulları); backtest_implementation_plan child operational roadmap
> (data pipeline + code repository + Cycle 41-43 sertifika kriter
> #6-9 ilerleme planı + NDX intangibles dörtlü konsolidasyonu §7);
> Cycle 21 backtest_spec + Cycle 29 data_sources paterni paralel
> methodology kategorisinde 3. sayfa.

> 📝 **Cycle 39 ek**: Stambaugh-Yuan mispricing factor model
> [[papers/stambaugh_yuan_2017_mispricing_factors]] (Cycle 39 ✓ Faz 3
> seçici ingest #4) §3 statistical filter + §1.3 universe methodology
> sertleştirme: (1) **MGMT (UMO1) + PERF (UMO2) composite mispricing
> factor entity'leri** [[factors/MGMT]] + [[factors/PERF]] yeni;
> Composite scoring paradigm 4-paper × 17-yıl literature continuity
> Piotroski → Mohanram → Stambaugh-Yuan → JKP; (2) **20/80 NYSE+AMEX+
> NASDAQ percentile breakpoints DEPARTURE FF15** §1.3 üç alternative
> weighting + Stambaugh-Yuan 20/80 breakpoint paterni 4. methodology
> choice (sp500_v1 + nasdaq100_v1 sensitivity test); (3) **Modified
> SMB ~2x premium** Q11 fully-answered ASTERISK üç-paper sertleştirme
> (Asness QMJ + Israel-Moskowitz + Stambaugh-Yuan); (4) **Long-only
> methodology kararı sertleştirme** Stambaugh-Yuan short-leg sentiment-
> driven mispricing kanıt CLAUDE.md §1 long-only hedef için kritik
> (sp500_v1 + nasdaq100_v1 long-only top 30-50 stocks); (5) **MGMT/PERF
> composite mispricing 4. paralel framework** §3 statistical filter
> ek katman (FF + HXZ q-factor + Stambaugh-Yuan mispricing üç paralel
> framework wiki taraf tutmaz Cochrane mathematical equivalence); Q82
> yeni NDX-spesifik MGMT+PERF kalibrasyonu Cycle 40 §11.5 ZORUNLU
> consolidation pass'de Q56+Q73+Q79+Q82 NDX intangibles dörtlü
> konsolidasyonu kullanıcı request.

---

## 1. Universe & sample

### 1.1 İki ayrı strateji evreni

Wiki'nin proje amacı (`CLAUDE.md` §1) iki bağımsız strateji tasarımı:

- **S&P 500 evren** — top 500 US stocks (large-cap value/quality
  ekseni); baseline composite [[factors/F_Score]] + V/P combined
  ([[papers/li_mohanram2019_quality_value]] +11.92% spread, modern
  replikasyon all-firms 1973-2012)
- **Nasdaq 100 evren** — top 100 non-financial Nasdaq-listed
  (FAANG-dominant, growth/intangibles-yoğun); baseline composite
  [[factors/G_Score]] + V/P combined (+21.45% spread) veya G &
  NEGPEG (+20.07%) ([[papers/li_mohanram2019_quality_value]] [Tablo 6])

Her iki evren NYSE-breakpoint üst-tarafında doğal yer alır → microcap
influence yapısal olarak yok ([[meta/contradictions]] MP↔HXZ
methodology resolution; HXZ NYSE-VW preference wiki amaç evrenleri
için doğru baseline).

### 1.2 Sample dönemi

**Default**: Modern data infrastructure tam erişilebilir (Cycle 27 +
Cycle 29 sonrası).
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] sample 1967-2014
  (anchor empirik replication baseline; conservative-side)
- [[papers/asness_frazzini_pedersen_2019_qmj]] US long sample
  1956-2012 (anchor large-cap quality)
- [[papers/jensen_kelly_pedersen_2023_replication_crisis]] sample
  US 1926+ Global 1986+ Dec 2020 (anchor modern güncelleme;
  anti-conservative-side)
- **Modern data infrastructure** [[methodology/data_sources]]
  (Cycle 29 ✓): Chen-Zimmermann 2022 Open Asset Pricing Database
  (pure replication ~100% reproducible) + JKP 2023 GlobalFactor
  code repository (Bayesian Empirical Bayes %85 replication) +
  WRDS open-source access (CRSP + Compustat raw data feed) **üç
  paralel data kaynağı**
- **Post-2020 dönem (FAANG/AI 2021-2024)** hala out-of-sample;
  Chen-Zimmermann database update + Faz 3 custom modern replikasyon
  ile tam kapanma

### 1.3 Methodology default tercihleri

- **NYSE breakpoint**: portfolio sort percentile cutoff'ları sadece
  NYSE-listed stocks üzerinden hesaplanır
  ([[papers/hou_xue_zhang_2020_replicating_anomalies]] anchor; wiki
  amaç evrenleri NYSE-breakpoint üst-tarafında)
- **Value-weighted (VW) — üç alternative methodology** (Cycle 27 ek):
  - **Pure VW** ([[papers/hou_xue_zhang_2020_replicating_anomalies]]
    anchor; microcap-arınmış sample). [[papers/israel_moskowitz_2013_shorting_size_time]]
    **erken anchor** (Cycle 22): [Tablo A2] equal-weighted decile
    alpha 8.4% (t=2.81) vs value-weighted INSIG paterni HXZ 2020'nin
    merkezi methodology eleştirisini 7 yıl önceden örnekliyor;
    çift teyit.
  - **FF half-weight** ([[papers/famafrench1993_three_factor]]
    paterni; size sortunda small + large eşit ağırlık)
  - **Capped VW** (NYSE 80th percentile winsorize)
    ([[papers/jensen_kelly_pedersen_2023_replication_crisis]]
    Cycle 27 ek; mega-cap concentration distortion kontrolü;
    Nokia örneği [s.3 fn 3]) — wiki amaç evrenleri large-cap
    concentrated; capped VW natural fit Faz 3 implementation
    tercih
  - **Methodology choice sensitivity test** Faz 3 spec'inde üç
    alternative replication-robust filter; HXZ ↔ JKP **dramatic
    empirik fark methodology choice'a aşırı duyarlı**
    ([[meta/contradictions]] §3): %35 HXZ pure VW vs %56.9 JKP
    capped VW + 8.5pp methodology decomposition
- **Equal-weight all-stocks (EW) "exaggerated upper bound"**:
  [[papers/mclean_pontiff_2016_post_publication_decay]] equal-weight
  CRSP NYSE-Amex-NASDAQ all-stocks methodology spread'leri şişirir
  (microcap %60+ stocks ama %3 market cap); MP %65 hayatta rakamı
  bu artifact'i içerir → wiki için **upper bound** referansı, baseline
  değil ([[meta/contradictions]] resolution 4. madde)
- **Wiki amaç evrenleri size partition (Israel-Moskowitz Q4-Q5)**:
  S&P 500 üst yarısı ≈ Israel-Moskowitz size Q5 (avg 36B 2011); S&P
  500 alt yarısı ≈ Q4 (avg 4.8B Russell Midcap); NDX top 100 ≈ Q5
  üst yarısı. Israel-Moskowitz 86-yıl direct kanıt: **vanilla HML
  Q4-Q5'te α=1.97-3.70 t=1.04-1.90 INSIG** [Tablo 3] → wiki strateji
  spec için standalone BE/ME baseline = sıfır.

---

## 2. Rebalance frequency

### 2.1 Annual default

`CLAUDE.md` §1 proje amacı **yıllık-frekans fundamental scoring**;
backtest spec'in default rebalance Annual.

- **June 30 rebalance convention** — fiscal year end + 4-6 ay reporting
  lag standardı; [[papers/famafrench1993_three_factor]] HML/SMB June
  rebalance; [[papers/sloan1996_accruals_anomaly]] [s.293] 4-month
  lag varsayımı; [[papers/cooper_gulen_ion2018_asset_growth_factor_models]]
  CGS asset growth June rebalance — wiki ingested paper'lardaki
  ortak konvansiyon
- **Look-ahead lag ≥4 ay** — fiscal year end (typically Dec 31) +
  4-6 ay reporting → minimum data_lag June rebalance ile tutarlı

### 2.2 Aylık-orijinal factor'lerin annual uyarlama sensitivity

Bazı factor'ler aylık rebalance ile literatüre girdi; annual uyarlama
primum sensitivity test gerekli ([[meta/open_questions]] Q33 + Q35 + Q51):

- [[factors/UMD]] — [[papers/carhart1997_four_factor]] aylık t-7
  through t-2 momentum; annual rebalance turnover dramatic azalır
  ama momentum decay yıl-içi (Daniel-Moskowitz 2016 momentum crashes
  state-dependent; Tier 3 #60 ingest edilmedi)
- [[factors/QMJ]] — [[papers/asness_frazzini_pedersen_2019_qmj]] monthly
  rebalance orijinal; annual uyarlama primum sensitivity test Faz 3
  spec'inde
- [[papers/sloan1996_accruals_anomaly]] — annual rebalance orijinal
  (fiscal year accrual computation); annual default ile tutarlı
- [[papers/piotroski2000_f_score]], [[papers/mohanram2005_g_score]],
  [[papers/li_mohanram2019_quality_value]] — annual rebalance orijinal

---

## 3. Performance reporting (DSR baseline)

### 3.1 Vanilla Sharpe ratio yasağı

Strateji performansı **Deflated Sharpe Ratio** ([[concepts/backtest_overfitting]]
+ [[papers/bailey_lopezdeprado_2014_deflated_sharpe]]) ile raporlanır.
Vanilla SR raporlamak yasak (backtest overfitting filter olmadan
upward-biased reporting).

**Üçlü reporting** zorunlu:
1. **DSR** (5 input variable: N trial-count, V[{SR}] Sharpe variance
   across trials, T sample length, skewness, kurtosis)
2. **Alpha t-stat** factor model lens'inde (default q5 model
   [[papers/hou_mo_xue_zhang_2020_security_analysis]] + Carhart 4F
   alternative [[papers/asness_frazzini_pedersen_2019_qmj]] paralel)
3. **Decay-adjusted spread** in-sample × 0.65 multiplier
   ([[concepts/post_publication_decay]] aggregate %35 baseline)

### 3.2 DSR formal formülasyonu

[[papers/bailey_lopezdeprado_2014_deflated_sharpe]] DSR formülü 4
düzeltme bacağı sağlar:
- DSR-1 trial-count (N anomaly testleri arasında en iyi seçim bias)
- DSR-2 skewness (negative skew Sharpe inflation)
- DSR-3 kurtosis (fat tails Sharpe inflation)
- DSR-4 sample length (kısa sample noise)

### 3.3 Çift düzeltme prensibi (Q37)

DSR-1 trial-count + HLZ MT-corrected birlikte uygulandığında
double-counting riski ([[papers/harvey_liu_zhu_2016_multiple_testing]]
+ [[papers/bailey_lopezdeprado_2014_deflated_sharpe]] [s.8]
complementary; aynı statistical bias'in iki representation'ı).

**Kural**: Tek-düzeltme tercih.
- **Factor-level evaluation** (single anomaly t-stat) → HLZ `|t| > 3.0`
  BHY 1% ([[concepts/multiple_testing]])
- **Strategy-level evaluation** (Sharpe ratio reporting) → DSR
  ([[concepts/backtest_overfitting]])

> 📝 **Cycle 26 ek (FGX 2020 ingest) — D bloğu statistical bacağı sertleştirme**:
>
> [[papers/feng_giglio_xiu_2020_factor_zoo]] Double-Selection LASSO
> methodology HLZ frequentist Bonferroni/BHY'nin **tamamlayıcı
> statistical layer'ı** — iki ortogonal frequentist concern:
> - **HLZ**: data-snooping bias (multiple-testing FDR control)
> - **FGX**: omitted variable bias (model selection mistakes correction)
>
> **Üç paralel methodology layer Faz 3 backtest spec için**:
> 1. **Factor-level HLZ FDR**: single anomaly t-stat `|t| > 3.0`
>    BHY 1% (data-snooping bias correction)
> 2. **Factor-level FGX DS LASSO**: SDF loading test 150-factor
>    library lens'inde (omitted variable bias correction)
> 3. **Strategy-level DSR**: Sharpe ratio reporting filter (backtest
>    overfitting correction)
>
> **Çift düzeltme prensibi genişlemesi**: HLZ + FGX iki ayrı
> factor-level test paralel uygulanabilir (iki ortogonal concern
> complementary, çift sayım değil); DSR strategy-level ayrı layer.
> Wiki için three-layer factor selection protocol:
> - HLZ MT-corrected sig + FGX DS-sig **iki ayrı kontrol**
> - Strategy-level DSR Sharpe reporting filter
>
> **SDF loading vs risk premium kritik epistemic point** ([[papers/feng_giglio_xiu_2020_factor_zoo]]
> [s.22]): factor mean return (sample-spesifik risk premium) ≠
> SDF loading (pricing contribution); Faz 3 backtest reporting
> **iki ayrı metric** rapor edilir (FGX paterni). HXZ 2017 paterni
> teyit (about half of factors INSIG risk premium FGX sample'da).

> ⚠️ **Faz 3 design decision**: Composite strategy (F&V/P, G&V/P)
> evaluation'ında DSR tercih; bireysel factor inclusion test'inde
> HLZ MT-corrected. Bu ayrım Cycle 24 v0_draft sırasında re-evaluate.

---

## 4. Dört darbe filter pipeline

Factor inclusion için sırayla 4 filter ([[concepts/post_publication_decay]]
çerçeve):

### 4.1 Darbe 1 — In-sample large-cap sig

Paper'ın orijinal sample'ında **large-cap alt-evrende (NYSE breakpoint
VW)** sig mi?

- ✅ **Hayatta kalanlar**: [[factors/UMD]] (Carhart sig + **Israel-Moskowitz
  86-yıl size-invariant + Q5 long-only α=3.92% t=3.83 sig** Cycle 22
  ek), [[factors/RMW]] (FF15 t=2.92 ama Asness QMJ Profitability tarafından
  dominate edilir), [[factors/CMA]] (FF15 sig ama large-cap zayıf
  t=1.03-2.00 [[papers/famafrench2015_five_factor]] [s.13]),
  [[factors/QMJ]] (Asness 4-factor alpha 66 bps/ay t=11.20), Sloan
  operating accruals (q-factor alpha -0.54% sig
  [[papers/hou_xue_zhang_2020_replicating_anomalies]])
- ❌ **REJECT (Cycle 22 sertleştirme)**: [[factors/HML]] standalone
  large-cap — [[papers/israel_moskowitz_2013_shorting_size_time]] **86-yıl
  direct kanıt** [Tablo 3] size Q4-Q5 (largest 40% NYSE) CAPM α=1.97-3.70%
  t=1.04-1.90 INSIG; [[papers/lev_srivastava_2020_value_failure]] Q1
  anchor (vanilla HML 1989'dan beri faltering). Çift anchor → §5.3
  reddedilen liste sertleşti
- ❌ **REJECT (Cycle 22 sertleştirme)**: [[factors/SMB]] vanilla —
  Israel-Moskowitz 86-yıl CAPM α=2.05% t=1.72 INSIG; HLZ MT-corrected
  never sig çift kanıt; Q11 fully-answered ASTERISK
- ⚠️ **Caveat**: [[factors/F_Score]] sadece BM-Q5 evrende test;
  large-cap alt-evrende [Tablo 4] spread zayıflar
- ⚠️ **Caveat**: [[factors/G_Score]] hi-tech subgroup spread +17.8%
  güçlü ama 1979-1999 sample post-2000 out-of-sample
- ⚠️ **Caveat**: [[factors/Accruals]] Sloan size-adj +2.9% marjinal,
  raw +10.4% size-loaded; Israel-Moskowitz size-conditional anomaly
  paterni paralel

### 4.2 Darbe 2 — Post-pub decay-adjusted spread sig

[[papers/mclean_pontiff_2016_post_publication_decay]] aggregate %35
decay multiplier; in-sample × 0.65 baseline.

**Kalibrasyon ölçekleri**:
- **Standard**: ×0.65 (MP aggregate baseline)
- **NDX agresif sensitivity** (Q29 stress-testi): ×0.50 — limited
  arbitrage [Tablo 8] büyük/likit/divid-payer/düşük-idio firmalarda
  decay daha güçlü; NDX FAANG-dominant bu profilin ucu
- **Composite-spesifik empirik kanıt**:
  [[papers/li_mohanram2019_quality_value]] modern continuous all-firms
  Piotroski +23% → +7.44% (~3x düşüş), Mohanram +21.2% → +6.06%
  (~3.5x düşüş); decay + universe + binary→continuous + industry
  revision karışık etkenler

> ⚠️ Composite scores McLean-Pontiff 82-anomaly sample'da explicit
> listed değil; aggregate multiplier wiki composite'lerde **proxy**
> rolünde, doğrudan kanıt değil ([[meta/data_gaps]] Cycle 11 boşluğu).

### 4.3 Darbe 3 — MT-corrected sig

[[papers/harvey_liu_zhu_2016_multiple_testing]] 316 factor census
recommended cutoff:
- **Baseline**: `|t| > 3.0` (BHY 1%)
- **Agresif alternative**: `|t| > 3.78` (Bonferroni 1965-2032
  projection [Şekil 3])
- **Time-aware**: HLZ Şekil 3 1965-2032 cutoff projection statik
  rakamları kullanmaz (örn. 2012 yayım `|t| > 3.39`); wiki için
  static cutoff yeterli

> 📝 **Cycle 26 ek (FGX 2020 ingest) — darbe (3) iki paralel methodology**:
>
> [[papers/feng_giglio_xiu_2020_factor_zoo]] **Double-Selection
> LASSO (DS) methodology** HLZ FDR control'in **tamamlayıcı statistical
> layer'ı**. Wiki Faz 3 backtest spec için darbe (3) MT-corrected sig
> **iki paralel test**:
>
> 1. **HLZ frequentist Bonferroni/BHY** (data-snooping bias):
>    - Single anomaly t-stat `|t| > 3.0` BHY 1% baseline
>    - Bonferroni `|t| > 3.78` agresif alternative
>
> 2. **FGX frequentist DS LASSO** (omitted variable bias):
>    - SDF loading test 150-factor library lens'inde
>    - Cross-validation tuning parameter (10-fold disjoint subsamples)
>    - Two-pass cross-section regression + Belloni vd. 2014b double
>      selection
>
> **Empirik teyit factor zoo decay**:
> - HLZ 316 factor census çoğunluk INSIG (cutoff `|t| > 3.0`)
> - **FGX 150 factor recursive 1994-2016: 17 sig (%11)**
> - HXZ 2020 NYSE-VW 447 anomaly → 46 net sig (%10)
> - MP 2016 aggregate decay %35
>
> **Üç ayrı methodology, çift+üç teyit**: factor zoo decay ~%85-90.
>
> Wiki için **darbe (3) iki paralel test** uygulanır — factor
> hayatta kalmak için **hem HLZ MT-corrected sig hem FGX DS-sig**
> tercih (her iki ortogonal statistical concern paralel). Tek-test
> insufficient (örn. RMW Ope HXZ q-factor INSIG ama FGX DS-sig
> methodology farkı dokümante; iki paralel test transparent).

**SMB never sig under MT** (Q11 fully-answered):
[[factors/SMB]] HLZ Şekil 3'te Bonferroni / Holm / BHY üç düzeltmede
de insig. Quality-controlled SMB resurrection asteriks
([[papers/asness_frazzini_pedersen_2019_qmj]] α=64 bps t=6.39
controlling for QMJ) — Faz 3 quality-aware SMB exposure revisit.

### 4.4 Darbe 4 — Replication-robust

[[papers/hou_xue_zhang_2020_replicating_anomalies]] q-factor lens'inde
NYSE-VW microcap-arınmış sample'da hayatta kalma:
- 447 anomaly → 161 sig at 5% → 46 net sig q-factor sonrası (~%10)
- "Captures by q5" durumu **dolaylı kabul**: factor exposure proxy =
  uygulanabilir, alpha kaybı caveat
- Örn. [[factors/HML]] q5 captures ama factor exposure portföye
  girer; [[factors/RMW]] / [[factors/CMA]] q5'in I/A + Roe component'i

> 📝 **Cycle 27 ek (JKP 2023 ingest) — darbe (4) iki paralel methodology**:
>
> [[papers/jensen_kelly_pedersen_2023_replication_crisis]] modern
> güncelleme **dramatic farklı sonuç** ([[meta/contradictions]] §3):
> HXZ %35 raw replication US-only NYSE-VW pure VW 1967-2014 vs JKP
> %84.9 Bayesian replication US 1926+ + %84.0 Global capped VW
> 1-month — ~50pp gap.
>
> **Wiki için Faz 3 darbe (4) iki paralel methodology** (Cycle 27 ek):
>
> 1. **HXZ pure VW empirik replication** (1967-2014 US-only):
>    - Conservative-side baseline (×0.65 standard / ×0.50 NDX agresif
>      decay multiplier Cycle 24 v0_draft muhafazakâr revize)
>    - Q-factor span direct test (factor exposure proxy)
>
> 2. **JKP Bayesian Empirical Bayes hierarchical** (1926-2020 US +
>    Global):
>    - Anti-conservative-side upper bound sensitivity reference
>    - Capped VW (NYSE 80th percentile winsorize) methodology
>    - 13 theme cluster + tangency portfolio multi-theme allocation
>      framework (10/13 themes sig+ tangency; 3 displaced:
>      profitability + investment + size)
>
> **Methodology choice sensitivity test** (üç alternative replication-
> robust filter):
> - Pure VW (HXZ baseline)
> - FF half-weight (FF1993 paterni)
> - Capped VW (JKP baseline)
>
> **Wiki için baseline tercih**: factor hayatta kalmak için **üç
> methodology tümünde sig** tercih edilebilir (en konservatif standard;
> Cycle 24 muhafazakâr revize ile uyumlu). Alternative: HXZ + JKP
> iki-yolu (pure VW + capped VW; FF half-weight ek opsiyonel).
>
> **13 theme cluster Faz 3 strategy spec anchor**: factor selection
> + theme allocation iki paralel decision; v0_draft §1.B + §2.B
> factor inclusion list **theme diversification yapısı** Faz 3 v1
> revize aday (10/13 themes tangency sig+ multi-theme allocation
> framework).

### 4.5 Çerçeve genişleme disiplini meta-not

[[concepts/post_publication_decay]] çerçeve genişleme disiplini:
**5. darbe açılmadı** (Cycle 14 disiplin meta-not testi geçti).

5. darbe açılması için 3 kriter:
1. Ortogonal mekanizma (mevcut 4 darbe ile overlap olmayan)
2. Aggregate tablo girdi (decay-adjusted spread tablosuna 5. sütun)
3. Faz 3 strategy spec için somut girdi kriteri

Bailey-LdP DSR (Cycle 14) 4. ayağı pekiştirdi ama 5. açmadı; çerçeve
4 darbede sabitlendi. Faz 2/3 yeni paper ingest'lerinde aynı disiplin.

---

## 5. Factor inclusion list (Faz 1 sentez)

### 5.1 4/4 hayatta kalan (Faz 3 strategy spec target)

| Factor | Origin | Q-factor alpha | Filter konumu |
|--------|--------|----------------|---------------|
| Sloan operating accruals (Oa) | [[papers/sloan1996_accruals_anomaly]] | -0.54%/ay sig (t=-3.77) | core signal (S&P 500 + NDX); **Sloan zinciri origin** |
| R&D-to-market (Rdm) | [[papers/lev_sougiannis_1996_rd_capitalization]] methodology | 0.7%/ay sig | NDX-spesifik intangibles signal |
| Earnings announcement Abr | [[concepts/earnings_quality]] | 0.66%/ay sig | event-driven complement |
| Cash-based op profits (Cop) | [[papers/novy_marx_2013_gross_profitability]] (GP/A origin) → Ball-GLN 2016 (cash-aware evrim) | 0.69%/ay sig | profitability core; **Profitability zinciri 4. halka** |

(Q-factor alpha rakamları [[papers/hou_xue_zhang_2020_replicating_anomalies]]
[Tablo 6 Internet Appendix], aggregate teyit; Faz 2 modern data ingest
ile re-evaluate)

### 5.2 3-4/4 baseline composite (anchor)

| Composite | Spread | Origin | Strategy anchor |
|-----------|--------|--------|-----------------|
| F & V/P | +11.92% (modern all-firms) | [[papers/li_mohanram2019_quality_value]] | ⭐ S&P 500 baseline |
| G & V/P | +21.45% | [[papers/li_mohanram2019_quality_value]] | ⭐ NDX baseline |
| G & NEGPEG | +20.07% (low-BM subsample) | [[papers/li_mohanram2019_quality_value]] | NDX growth alternative |
| QMJ | 4-factor α=66bps/ay (t=11.20) | [[papers/asness_frazzini_pedersen_2019_qmj]] | quality anchor (q5 captures asterisk) |
| UMD | classic 0.67% sig | [[papers/carhart1997_four_factor]] | momentum exposure (q5 Roe span) |
| CMA | classic 0.34% sig | [[papers/famafrench2015_five_factor]] | investment exposure (q5 I/A span) |
| HML adjusted | post-2010 vanilla NEGATIVE | [[papers/lev_srivastava_2020_value_failure]] | value adjusted methodology baseline |
| Long-only momentum (top 30%) | 86-yıl size-invariant; Q5 largest α=3.92% t=3.83 sig | [[papers/israel_moskowitz_2013_shorting_size_time]] | **Cycle 22 yeni**; long-only retail-style actionable; UMD long-short alternative; Q52 paralel |
| Gross Profitability GP/A | univariate FF3 α 0.52% t=4.49 + Fortune 500 GP/V Sharpe 0.74 ⭐ | [[papers/novy_marx_2013_gross_profitability]] | **Cycle 23 yeni**; **Profitability zinciri origin** (1. halka); large-cap size-invariant; Fortune 500 GP/V wiki S&P 500 direct anchor; vanilla HML reject sonrası primary value-side alternative |
| GP × V/P combined (Fortune 500 rank-based) | 0.62%/ay; annual Sharpe 0.74; long-side market-hedged 18bps/ay t=3.46 | [[papers/novy_marx_2013_gross_profitability]] [Tablo 7] | **Cycle 23 yeni**; ⭐ S&P 500 strategy spec **birebir empirik altyapı**; Li-Mohanram F&V/P + G&V/P binary intersection paralel **continuous rank product**; QARP framework empirik anchor |
| Organization Capital (OC) factor portfolio | industry-relative spread 4.8%/yıl Sharpe 0.58 + FF3 α 5.5% sig + Carhart α 3.9% sig 1% (1970-2008) | [[papers/eisfeldt_papanikolaou_2013_organization_capital]] | **Cycle 25 yeni**; **F bloğu 4. ayak (factor portfolio direct evidence)** ⭐ NDX strategy spec; SG&A perpetual inventory δ=15%; industry-relative within FF17 + annual June rebalance; high OC firms NDX FAANG profile birebir match (low PP&E/AT + growth-tilted + low leverage); operating leverage rejected (DOL-controlled 3.1% sig 1%) |

### 5.3 0/4 reddedilen (Faz 3 strategy spec'e girmiyor)

- [[factors/F_Score]] **standalone large-cap** — BM-Q5 evrende
  kalibre, large-cap alt-evrende spread zayıf
- [[papers/sloan1996_accruals_anomaly]] **size-adjusted standalone**
  +2.9% marjinal — large-cap evrende yapısal silinme beklenir
  ([[meta/open_questions]] Q5 partial)
- [[factors/SMB]] **vanilla** — never sig under MT (Q11) **+ Israel-Moskowitz
  86-yıl CAPM α=2.05% t=1.72 INSIG çift kanıt** (Cycle 22 sertleştirme)
- [[factors/HML]] **standalone large-cap** ⚠️ **YENİ Cycle 22**:
  [[papers/israel_moskowitz_2013_shorting_size_time]] [Tablo 3] size
  Q4-Q5 CAPM α=1.97-3.70% t=1.04-1.90 INSIG + [[papers/lev_srivastava_2020_value_failure]]
  Q1 anchor (vanilla HML 1989'dan beri faltering) çift anchor → standalone
  vanilla BE/ME large-cap REJECT. **Adjusted HML** (intangibles-aware
  methodology, [[concepts/intangibles_adjusted_accounting]]) ayrı baseline
- [[factors/RMW]] (operating profitability) — Asness QMJ Profitability
  composite tarafından dominate edilir (4 dimension breakdown
  [[papers/asness_frazzini_pedersen_2019_qmj]])
- [[factors/Magic_Formula]] — q5 captures
  ([[papers/hou_mo_xue_zhang_2020_security_analysis]]); standalone
  alpha microcap residual
- **Distress factor cluster** (failure prob., O-Score, Z-Score, credit
  rating) — [[papers/hou_xue_zhang_2020_replicating_anomalies]] [s.2]
  "virtually nonexistent"

### 5.4 Forensic filter

[[factors/M_Score]] ([[papers/beneish_1999_m_score]]) — filter, signal
değil:
- **Default cutoff**: −2.22 (Beneish orijinal `.025` rakamı)
- **NDX conservative**: −2.84 (`.01` cutoff; high SGI tech firma false
  positive riskine karşı)
- **Combined yaklaşım**: F & M / G & M screen-and-rank — F-Score /
  G-Score winner ranking + M-Score filter
- **Caveat**: Beneish sample küçük-cap-tilted (manipulators median
  TA $43M); large-cap kalibrasyon Q46 paralel

### 5.5 QMJ ASTERISK (SMB resurrection)

[[papers/asness_frazzini_pedersen_2019_qmj]] [Tablo X]: vanilla SMB
never sig under MT (Q11) AMA quality-controlled SMB sig α=64bps
t=6.39. Faz 3 strategy spec'inde **quality-aware SMB exposure
revisit** — wiki amaç evrenleri large-cap olduğu için size primum
küçük ama negative-quality firms'da arbitrage opportunity.

### 5.6 QARP framework anchor

[[papers/asness_frazzini_pedersen_2019_qmj]] Section 7 QARP (Quality
At Reasonable Price) framework + [[papers/li_mohanram2019_quality_value]]
F&V/P + G&V/P combined paterni paralel:
- **Operationalization horse race** (Q50): Li-Mohanram binary
  intersection vs Asness continuous z-score; Faz 3 strategy spec'inde
  empirik test
- **NDX-spesifik kalibrasyon**: F bloğu intangibles-aware Bm ile
  QARP kombinasyonu (Q50 paralel)

---

## 6. F bloğu intangibles-aware methodology (NDX-spesifik)

[[concepts/intangibles_adjusted_accounting]] **4-katmanlı methodology
hierarchy** (Cycle 25 sertleştirme; Cycle 17 3-katmanlı + Cycle 25
ek 4. ayak factor portfolio direct evidence):

| Katman | Paper | Component | Tip |
|--------|-------|-----------|-----|
| 1 (Knowledge) | [[papers/lev_sougiannis_1996_rd_capitalization]] | R&D capital perpetual inventory | Methodology infrastructure |
| **2 (Organization)** | **[[papers/eisfeldt_papanikolaou_2013_organization_capital]]** | OC factor portfolio (SG&A perpetual inventory δ=15%) | **Factor portfolio direct evidence** ⭐ |
| 3 (Total) | [[papers/peters_taylor_2017_intangible_capital]] | q^tot proxy (Knowledge + Organization + External) | Methodology infrastructure |
| 4 (Application) | [[papers/lev_srivastava_2020_value_failure]] | Adjusted HML post-2010 value crisis | Methodology infrastructure |

**Methodology infrastructure (1+3+4) + factor portfolio anchor (2)
ayrımı**: Knowledge + Total + Application **methodology paper'ları**
adjusted Bm rebuild altyapısını sağlar; **Eisfeldt-Papanikolaou (2)
factor portfolio anchor** olarak Faz 3 NDX strategy spec'inde direct
overlay layer (R&D-to-market 4/4 hayatta kalan + OC factor 5.5%
FF3 α paralel signal layer).

### 6.1 Vanilla HML reject

[[papers/lev_srivastava_2020_value_failure]] anchor (Q1 fully-answered):
- Vanilla HML 1970s +102% → 1980s +75% → 1990s -10% → 2007-2018
  NEGATIVE
- 1989'dan beri faltering ([Figure 1])
- İki mekanizma: intangibles bias + mean reversion slowdown post-2007

### 6.2 Adjusted Bm rebuild (perpetual inventory)

Book equity adjustment:
- **Knowledge capital** (R&D): [[papers/lev_sougiannis_1996_rd_capitalization]]
  industry-spesifik amortization rates (5-9 yıl useful life)
  - Pharma: 9 yıl
  - Scientific Instruments: 5 yıl
  - 6 sektör tablosu [Tablo 3]
  - Perpetual inventory methodology Eq. (3)
- **Organization capital** (SG&A): iki methodology paralel
  ([[meta/open_questions]] Q60 yeni Cycle 25):
  - [[papers/peters_taylor_2017_intangible_capital]] θ=30% allocation
    (Eq. 9-11) — partial allocation (Knowledge + Organization + External
    decomposition için θ tahmin)
  - [[papers/eisfeldt_papanikolaou_2013_organization_capital]] full
    SG&A perpetual inventory δ=15% — measurement error caveat ile
    full SG&A treatment (Lev-Radhakrishnan 2004 paterni); **factor
    portfolio direct evidence** Carhart 4F α=3.9% sig 1%
- **External intangibles** (Compustat `intan` field):
  [[papers/peters_taylor_2017_intangible_capital]] üçlü component'in
  3.'sü
- **Industry amortization rates** (Q38): BEA / Li 2012 modern data;
  Faz 2 Eisfeldt-Papanikolaou 2013 ingest sonrası refine

### 6.3 Total q proxy

[[papers/peters_taylor_2017_intangible_capital]] Eq. 9:
`q^tot = V / (K^phy + K^int)` standard q'dan üstün (ρ² +21%);
macro-level R² 4% → 61%; high-intangible firms'da q theory daha iyi
fits.

### 6.4 R&D stock methodology (Q39)

[[papers/lev_sougiannis_1996_rd_capitalization]] [s.133 fn 22]
**proper capitalization stock** vs 3-yıl flow toplamı dramatic
farklı:
- Stock methodology: RDC/M coef 0.0114 (t=3.88) sig upper-quartile
- Flow methodology: 0.0078 (t=1.20) insig

**Kural**: Faz 3 strategy spec'inde proper perpetual inventory stock
methodology zorunlu; flow approximation reddi.

### 6.5 R&D-aware Sloan accruals revision (Q26 partial)

Adjusted Sloan accruals = traditional + (RD_t - RA_t) — Lev-Sougiannis
methodology üzerinden tech firma working capital distortion düzeltmesi.
Wiki'de henüz formal formülasyon yok; Faz 2 sentez sırasında Eisfeldt-
Papanikolaou 2013 + modern data ingest sonrası finalize.

### 6.6 GICS sektör mapping (Q38 paralel)

NDX evrende GICS Level-2/3/4 hangi seviyede mapping yapılacak; SIC
1996 amortization rates → modern GICS sektör translation methodology
Faz 3 backtest spec için ön koşul. Mohanram G6 industry-median (Q19
sektör sınıflandırma) ile bağlantılı; Faz 2 finalize.

---

## 7. Composite scoring methodology

### 7.1 F-Score (binary 9-component)

[[factors/F_Score]] ([[papers/piotroski2000_f_score]] origin):
- 9 binary indicator (ROA, ΔROA, CFO, Accrual, ΔLEVER, ΔLIQUID, EQ_OFFER,
  ΔMARGIN, ΔTURN)
- High-BM evrende kalibre; large-cap caveat (§4.1)
- **Continuous variant**: paper [s.16] qualitatively similar ama
  spread 0.230 → 0.092

### 7.2 G-Score (binary 8-component industry-median)

[[factors/G_Score]] ([[papers/mohanram2005_g_score]] origin):
- 8 binary signal (ROA, CFROA, CFO>NI, Earnings variability, Sales
  growth variability, R&D, CapEx, Advertising — son 3'ü conservatism)
- 2-digit SIC industry-median benchmark
- Low-BM evrende kalibre; NDX hi-tech subgroup +17.8% spread
  ([Tablo 5 Panel D])
- G6 (R&D/Assets) **dual origin attribution**: Mohanram conservatism
  + [[papers/lev_sougiannis_1996_rd_capitalization]] literatür hattı
  (Cycle 15 keşif)

### 7.3 M-Score (probit 8-component / 5-sig)

[[factors/M_Score]] ([[papers/beneish_1999_m_score]] origin):
- 8 ratio (DSRI, GMI, AQI, SGI, DEPI, SGAI, TATA, LVGI)
- 5 sig (DSRI, GMI, AQI, SGI, TATA), 3 insig (DEPI, SGAI, LVGI)
- Probit coefficients pseudo-R² 30.6% / 37.1%
- **Filter, signal değil** — earnings manipulation detection;
  combined yaklaşım F&M / G&M screen-and-rank

### 7.4 QMJ (continuous z-score 4-dimension)

[[factors/QMJ]] ([[papers/asness_frazzini_pedersen_2019_qmj]] origin):
- 22 measure → 4 dimension z-score composite
  - **Profitability** (GPOA, ROE, ROA, CFOA, GMAR, ACC) — origin
    attribution dual:
    - **GPOA** kökü [[papers/novy_marx_2013_gross_profitability]]
      (Profitability zinciri 1. halka)
    - **ACC** kökü [[papers/sloan1996_accruals_anomaly]] (Sloan zinciri 1. halka)
    - İki paralel quality zinciri 6 measure içinde birleşiyor
  - Growth (5-year prior changes of profitability measures) — origin
    [[papers/mohanram2005_g_score]]
  - Safety (BAB, IVOL, Z-Score, ROE volatility, leverage, payout) — BAB
    origin Frazzini-Pedersen 2013 (Tier 3 #51, ingest edilmedi)
  - Payout (PAYOUT, NETISS, ΔSHRO)
- Composite QMJ "the strongest of the four" [Tablo VI Panel A]
- 4-dimension hierarchy decompose Q49 paralel (Faz 2 sentez)

### 7.5 Magic Formula

[[factors/Magic_Formula]] (Greenblatt 2006, Tier 3 #57 kitap, ingest
edilmedi):
- 2-component composite (EBIT/EV + ROC)
- [[papers/hou_mo_xue_zhang_2020_security_analysis]] q5 captures
  (academic validator); standalone alpha microcap residual
- **Faz 3'te dahil edilmiyor** — q5 captures + microcap residual

### 7.6 QARP framework (Faz 3 anchor)

[[papers/asness_frazzini_pedersen_2019_qmj]] Section 7:
- Quality At Reasonable Price = high QMJ + low P/B
- [[papers/li_mohanram2019_quality_value]] F&V/P + G&V/P combined
  paterninin Asness paralel'i
- Operationalization horse race (Q50) Faz 3 spec'inde

---

## 8. Origin attribution & literature provenance

[[concepts/intangibles_adjusted_accounting]] + Cycle 9 origin
attribution dual pattern: composite score'un her bileşeni için iki
ayrı origin işareti.

### 8.1 Sloan zinciri (4 paper × 23 yıl mispricing detection)

| Halka | Paper | Component |
|-------|-------|-----------|
| Origin | [[papers/sloan1996_accruals_anomaly]] | Total accruals (TA) |
| 2 | [[papers/piotroski2000_f_score]] | F_ACCRUAL (CFO > NI binary) |
| 3 | [[papers/mohanram2005_g_score]] | G3 (CFO > NI binary; Sloan paralel) |
| 4 | [[papers/asness_frazzini_pedersen_2019_qmj]] | Profitability ACC (negative accruals → high quality) |

### 8.1b Profitability zinciri (4 paper × 7 yıl productive efficiency signal) — Cycle 23 yeni

| Halka | Paper | Component | Methodology evrim |
|-------|-------|-----------|-------------------|
| **Origin** | [[papers/novy_marx_2013_gross_profitability]] | GP/A = (REVT − COGS) / AT | Standalone signal; numerator intangibles-aware (R&D ARÎ); denominator AT |
| 2 | [[papers/famafrench2015_five_factor]] | RMW Ope = (REVT − COGS − SG&A − int) / BE | Factor portfolio; numerator daha düşük (operating); denominator BE |
| 3 | [[papers/asness_frazzini_pedersen_2019_qmj]] | QMJ Profitability dimension GPOA | Composite z-score 6 measure'dan biri |
| 4 | [[papers/hou_xue_zhang_2020_replicating_anomalies]] (HMXZ Tablo 5) | Cop (cash-based op profits-to-assets) | Cash-aware evrim (Ball-GLN 2016 origin); q-factor alpha 0.69%/ay sig (4/4) |

**İki paralel quality zinciri QMJ 4-dimension'da birleşiyor**: QMJ
Profitability dimension 6 measure içinde GPOA (Profitability zinciri 3.
halka) + ACC (Sloan zinciri 4. halka) yan yana — wiki için literature
continuity yapısal kazanım. QMJ Profitability composite **iki bağımsız
mekanizmanın sentezi**: productive efficiency (Novy-Marx) + earnings
management detection (Sloan).

### 8.1c F bloğu intangibles 4-katmanlı methodology hierarchy (Cycle 25 sertleştirme)

| Katman | Paper | Component | Yıl | Tip |
|--------|-------|-----------|-----|-----|
| 1 (Knowledge) | [[papers/lev_sougiannis_1996_rd_capitalization]] | R&D capital perpetual inventory (δ industry-spesifik 5-9 yıl) | 1996 | Methodology infrastructure |
| **2 (Organization)** | **[[papers/eisfeldt_papanikolaou_2013_organization_capital]]** | OC factor portfolio (SG&A perpetual inventory δ=15%) | 2013 | **Factor portfolio direct evidence** ⭐ |
| 3 (Total) | [[papers/peters_taylor_2017_intangible_capital]] | q^tot proxy (Knowledge + Organization + External) | 2017 | Methodology infrastructure |
| 4 (Application) | [[papers/lev_srivastava_2020_value_failure]] | Adjusted HML post-2010 value crisis decomposition | 2020 | Methodology infrastructure |

**Yapısal kazanım**: F bloğu Cycle 17'de **3-katmanlı** kapatılmıştı;
Cycle 25 ek 4. ayak (Organization, factor portfolio direct evidence)
ile **methodology infrastructure (1+3+4) + factor portfolio anchor
(2) ayrımı** dokümante. Wiki için NDX strategy spec'inde:
- Adjusted Bm rebuild (1+3+4 methodology infrastructure)
- **OC factor signal layer (2 direct factor portfolio)** + R&D-to-
  market signal layer (HXZ 2020 4/4 hayatta kalan)

**Q41 fully-answered** (Cycle 25): Lev-Sougiannis vs Peters-Taylor
vs Eisfeldt-Papanikolaou vs Lev-Srivastava 4-way horse race
methodology hierarchy + factor portfolio anchor ayrımı dokümante.

### 8.2 M-Score TATA literature hattı (Healy-Jones, Sloan değil)

[[papers/beneish_1999_m_score]] reference list [s.20-21]:
- Healy 1985 (earnings management / accruals manipulation)
- Jones 1991 (discretionary accruals model)
- **Sloan 1996 explicit listed DEĞİL** — methodology paralel ama
  literatür hattı ayrı (Cycle 18 keşif)
- Wiki implication: Sloan + M-Score TATA complementary use possible
  (mispricing + fraud detection iki epistemik düzlem)

### 8.3 QMJ Safety BAB literatür hattı

[[papers/asness_frazzini_pedersen_2019_qmj]] Safety dimension BAB
component → Frazzini-Pedersen 2013 "Betting Against Beta" (Tier 3 #51,
ingest edilmedi); QMJ Safety dimension origin attribution Faz 2'de
güçlenir (Frazzini-Pedersen ingest aday).

### 8.4 Faz 3 strategy spec disiplini

Composite scores'ın literatür hattı kökleri Faz 3 strategy spec'inde
"wiki'nin neye dayandığını biliyoruz" disiplini — her bileşen **iki
sayfa atfı** (paper-spesifik origin + literatür hattı kökü)
zorunlu (`s&p500_v1.md` + `nasdaq100_v1.md` template requirement).

---

## 9. Faz 3'e geçiş için ön koşullar

### 9.1 E bloğu eksiklikleri (Cycle 22-23 ingest planı)

| # | Paper | Tier | Cycle target | Niye |
|---|-------|------|--------------|------|
| 1 | Israel-Moskowitz 2013 | Tier 1 | Cycle 22 | E bloğu (large-cap reality) Faz 1'de yumuşak; Q4 + Q14 tam cevap |
| 2 | Fama-French 2008 "Dissecting Anomalies" | Tier 1 | Cycle 22-23 | E bloğu paralel; size-conditional sonuçlar |
| 3 | Novy-Marx 2013 GP/A | Tier 1 #5 | Cycle 23 | QMJ Profitability dimension origin; Q49 anchor |

### 9.2 Tier 1 q-factor origin (Cycle 24+)

[[papers/hou_xue_zhang_2020_replicating_anomalies]] q-factor lens
kullanıyor ama origin paper Hou-Xue-Zhang 2015 "Digesting Anomalies"
(Tier 1 #3) ingest edilmedi; Cycle 24+ aday ([[meta/data_gaps]]
Cycle 8 boşluğu).

### 9.3 Modern data ingest (Faz 2 sonu)

| # | Paper | Tier | Niye |
|---|-------|------|------|
| 1 | Chen-Zimmermann 2022 Open Asset Pricing | Tier 2 #41 | Modern data portalı; replikasyon altın standart |
| 2 | Jensen-Kelly-Pedersen 2023 | Tier 2 #44 | ML-aware framework + global data; HXZ 2020 modern güncelleme |
| 3 | Eisfeldt-Papanikolaou 2013 organization capital | Tier 2 #28 | Q41 4-way horse race (Lev-Sougiannis + Peters-Taylor + Eisfeldt-Papanikolaou + Lev-Srivastava); F bloğu factor portfolio direct evidence |

### 9.4 v0_draft strategy taslağı (Cycle 24)

[[meta/handoff_faz2]] Cycle 24 = 4-cycle ardışık consolidation pass +
ilk strategy v0 draft (`wiki/strategies/v0_draft.md`). 3-4 cycle Faz
2 ingest sonrası birikim sentezi.

### 9.5 Q49/Q50/Q51 Faz 2 sentez

- **Q49** — QMJ 4 dimension hierarchy (Profitability vs Growth vs
  Safety vs Payout en güçlü hangisi); paper [Tablo VI Panel A]
  decompose edilmemiş
- **Q50** — NDX-spesifik QARP kalibrasyonu (Li-Mohanram binary vs
  Asness continuous operationalization horse race)
- **Q51** — QMJ post-2012 modern replikasyonu (sample sonu Dec 2012;
  FAANG era + COVID + AI 2013-2024 out-of-sample)

### 9.6 Q40/Q42/Q44/Q45 Faz 2 sentez (F bloğu kalan)

- **Q40** — Modern Peters-Taylor methodology replikasyonu (sample
  sonu 2011)
- **Q42** — R&D-to-market Peters-Taylor total intangibles versiyonu
  test eden paper yok
- **Q44** — Post-2018 (FAANG + AI 2019-2024) replikasyon eksikliği
- **Q45** — Value-trap-avoidance filter design (Lev-Srivastava Logit
  Table 1 escape attributes)

---

## 10. Bilinen zayıflıklar ve caveats (Faz 3 `known_weaknesses.md` öncüsü)

> 📝 Faz 3'te ayrı sayfa açılır (`wiki/strategies/known_weaknesses.md`).
> Backtest spec'in self-aware section'ı — bu liste exhaustive değil,
> Faz 2 ingest'lerle genişler.

1. **Composite scores McLean-Pontiff sample'da explicit listed değil**
   — aggregate %35 multiplier proxy, doğrudan kanıt değil
2. **Annual rebalance sensitivity test** UMD/QMJ/aylık-orijinal
   factorler için tam yapılmadı (Q33+Q35+Q51)
3. **NDX intangibles methodology factor portfolio direct evidence**
   eksik — Eisfeldt-Papanikolaou 2013 ingest beklemede
4. **Sample selection bias** — wiki ingested paperlar pre-2014 sample
   ağırlıklı; FAANG era + COVID + AI 2013-2024 out-of-sample
5. **Mispricing vs risk premium** felsefi çatallanma
   ([[papers/cochrane2011_discount_rates]] mathematical equivalence) —
   wiki taraf tutmaz; portföy aynı, yorum farklı
6. **Buffett-tipi alpha discretionary**
   ([[papers/hou_mo_xue_zhang_2020_security_analysis]] q5 alpha 0.77%
   t=2.69) — wiki strategy hedeflememeli, achievable değil
7. **Memory effects / strong-trend series** (UMD momentum) backtest
   overfit "loss maximization" classic case
   ([[concepts/backtest_overfitting]])
8. **Equal-weight all-stocks rakamları "biased upper bound"** — MP +
   Li-Mohanram modern + Mohanram NASDAQ partition rakamları range-based
   sensitivity için kullanılır

---

## İlgili sayfalar

- **Concepts**: [[concepts/post_publication_decay]] (dört darbe çerçevesi),
  [[concepts/multiple_testing]] (HLZ FDR), [[concepts/anomaly_replication]]
  (HXZ NYSE-VW), [[concepts/backtest_overfitting]] (DSR),
  [[concepts/intangibles_adjusted_accounting]] (F bloğu hub),
  [[concepts/fundamental_scoring]] (composite paradigm)
- **Anchor papers**: [[papers/bailey_lopezdeprado_2014_deflated_sharpe]]
  (DSR), [[papers/mclean_pontiff_2016_post_publication_decay]] (decay),
  [[papers/harvey_liu_zhu_2016_multiple_testing]] (MT), [[papers/hou_xue_zhang_2020_replicating_anomalies]]
  (replication), [[papers/lev_srivastava_2020_value_failure]] (vanilla
  HML reject), [[papers/asness_frazzini_pedersen_2019_qmj]] (QARP)
- **Meta**: [[meta/open_questions]] (51 Q; 5 fully-answered), [[meta/data_gaps]],
  [[meta/contradictions]] (2 entry), [[meta/handoff_faz2]] (Faz 2
  yol haritası)

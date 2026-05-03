---
type: paper
authors: [Jensen, Theis Ingerslev, Kelly, Bryan T., Pedersen, Lasse Heje]
year: 2023
title: "Is There a Replication Crisis in Finance?"
venue: "Journal of Finance"
url: https://www.nber.org/papers/w28432
local_path: raw/papers/jensen_kelly_pedersen_2023_replication_crisis.pdf
ingested: 2026-05-01
tags: [replication_crisis, bayesian_methodology, multiple_testing, factor_taxonomy, modern_data, global_data, d_block_replication_pillar]
status: ingested
cycle: 27
cycle_35_note: "q-factor model formal origin paper [[papers/hou_xue_zhang_2015_q_factor]] Cycle 35 ✓; JKP 2023 13 theme cluster taxonomy q-factor I/A + ROE Investment* + Profitability themes paralel; **Profitability + Investment + Size 3 displaced** (joint modeling redundancy) [[meta/contradictions]] §3 paterni paralel; HXZ 2015 frequentist factor regression vs JKP 2023 Bayesian Empirical Bayes hierarchical methodology farkı + global 1986+ extension; D bloğu replication ayağı 2-paper dramatic methodology disagreement HXZ ↔ JKP scope-dependent (Cycle 13 + 27 paterni paralel; HXZ 2015 origin + 2020 Replicating empirical + JKP 2023 Bayesian üç paralel framework)"
cycle_38_note: "JKP Profitability theme Ball-GLN Cop methodology paralel [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓; JKP 13 theme cluster Profitability theme **displaced** (joint modeling redundancy) Cop standalone Ball-GLN [Tablo 2 col 6] subsumes Acc paterni paralel; Profitability zinciri 4. halka Cop Bayesian framework cross-test"
cycle_39_note: "JKP 13 theme cluster Stambaugh-Yuan 11 anomaly 2-cluster paterni paralel evolution [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; clustering methodology continuity Ahn-Conrad-Dittmar 2009 + Ward 1963 hierarchical (Stambaugh-Yuan) → Bayesian Empirical Bayes hierarchical (JKP); 11 anomaly fixed set (SY) → 153 factor library scope evolution (JKP); composite mispricing scoring 4-paper × 17-yıl literature continuity Piotroski → Mohanram → Stambaugh-Yuan → JKP 4. halka"
block: D_complement
---

# Jensen, Kelly, Pedersen (2023) — Is There a Replication Crisis in Finance?

> 📝 **Faz 2 Cycle 27 ingest** — D bloğu kompleman (replication ayağı
> modern güncelleme); HXZ 2020 (US-only NYSE-VW empirik replication)
> + **JKP 2023 (global Bayesian ML-aware framework)** **iki paralel
> methodology, dramatic farklı sonuç**. **3. contradictions entry
> zorunlu** (plan §11 karar matrisi: dramatic empirik fark).
>
> **Plan revize**: Plan'da "ML-aware framework" demiştim; paper
> aslında **Bayesian Empirical Bayes hierarchical model** (ML değil
> klasik Bayesian methodology). Üç paralel statistical methodology
> dokümante: HLZ frequentist Bonferroni/BHY + FGX frequentist DS
> LASSO + **JKP Bayesian Empirical Bayes** = D bloğu statistical
> bacağı **3 paper × üç paralel methodology aile**.

## TL;DR

JKP 2023 **Bayesian Empirical Bayes hierarchical model + 153 factor
× 93 country global data + 13 theme cluster taxonomy** ile factor
replication crisis iddialarını **çürütüyor**. **Headline replication
rates** [Figure 1]:
- **HXZ 2020 (Hou et al.) raw returns**: %35
- **JKP US sample raw returns**: %56.9 (HXZ ile aynı OLS t-stat
  methodology; +21.9pp metodoloji decomposition: +4.3% longer
  sample + +4.0% 1-month focus + +8.5% capped VW + +2.4% 15 ek
  factor + +2.7% minor)
- **JKP US exclude factors never sig**: %64.7
- **JKP US CAPM alphas**: %77.3
- **JKP US Bayesian Empirical Bayes**: **%84.9** ⭐
- **JKP Global Bayesian Empirical Bayes**: **%84.0** ⭐
- **HLZ 2016 multiple-testing adjustment**: %77.3 (Benjamini-Yekutieli)

**13 theme cluster** (algorithmic taxonomy): Accruals*, Debt
Issuance*, Investment*, Leverage*, Low risk, Momentum, Profit Growth,
Profitability, Quality, Seasonality, Size*, Skewness*, Value (* =
factors short the corresponding characteristic). **10/13 themes
>75% replication rate**; istisnalar: seasonality, leverage, size.
**10/13 themes tangency portfolio'a positive weight ile giriyor**;
3 displaced: **profitability, investment, size** (Q49 paralel —
QMJ Profitability dimension hierarchy farklı epistemik düzlem).
**Out-of-sample combined %88.5 positive**.

**Wiki için yapısal kazanım**:
- **3. contradictions entry** açılır (HXZ 2020 vs JKP 2023 dramatic
  empirik fark): %35 vs %84.9 = ~50pp gap; methodology decomposition
  + Bayesian framework choice + global data extension scope-dependent
- **D bloğu replication ayağı 2 paper** (HXZ origin + JKP modern
  güncelleme; iki paralel methodology, çelişen empirik bulgular)
- **D bloğu statistical bacağı 3 paper × üç paralel methodology
  aile**: HLZ frequentist + FGX frequentist DS LASSO + JKP Bayesian
  Empirical Bayes

## Tek Cümle Tezi

**Asset pricing factor zoo'nun büyük çoğunluğu (%85)** Bayesian
hierarchical model + global data + capped value-weighting altında
**replicate**; "replication crisis" iddiası HXZ 2020 methodology
choice'larına aşırı duyarlı (raw VW + 1/6/12-month + US-only)
ve scope-dependent — **factor research empirik kanıtla destekli
collective body**.

## Sample ve Methodology

- **Universe**:
  - **US**: CRSP (beginning **1926**); common stocks (Compustat
    primary security identification)
  - **Global**: Compustat, **93 countries**, beginning **1986**
    (most developed countries; emerging markets later)
  - **Total**: ex-financials excludes; delisting returns -30% (Shumway
    1997 paterni)
- **Sample sonu**: **paperdan teyit January 2021** (NBER WP February
  2021; data through 2020 muhtemelen) — **post-2020 modern dönem
  out-of-sample (2021-2024) eksik** (Q63 + Q44 partial-stronger,
  fully-answered değil)
- **Frequency**: Monthly factor returns; **1-month holding period**
  default (HXZ 1/6/12-month vs JKP only 1-month methodology farkı)
- **Factor library size**: **153 factors**
  - HXZ 2020 + Chen-Zimmermann database üzerine inşa
  - 15 ek factor previously studied
  - 13 theme cluster taxonomy
- **Construction**:
  - **Capped value-weighting** (NYSE 80th percentile winsorize) —
    "compromise between pure VW and Fama-French method"; HXZ pure
    VW vs FF half-weight-small-stocks vs JKP capped VW
  - Annual + quarterly accounting data (4-month accounting lag);
    quarterly aggregate 4-quarter rolling
  - International standardization: USD denominated; excess returns
    relative to US treasury bill rate; 0.1%/99.9% winsorization
- **Methodology**:
  - **Bayesian Empirical Bayes (EB) hierarchical model** [Section 1]
  - **CAPM benchmark** (FF1993 mechanically explains size+value;
    JKP CAPM-residual factors for replication assessment)
  - **13 theme cluster taxonomy** (Ward 1963 hierarchical clustering;
    CAPM-residual returns within-theme correlation > 0.5 in 10/13)
  - **Tangency portfolio analysis** (which themes simultaneously
    contribute?)
  - **Multiple testing adjustment via Bayesian shrinkage** (HLZ
    Benjamini-Yekutieli paralel ama hierarchical structure dependence
    leverage)
- **Online data + code**: bryankellyacademic.org; GitHub bkelly-lab/
  GlobalFactor; WRDS open-source link — Faz 3 backtest implementation
  modern data infrastructure direct kullanılabilir

## D bloğu epistemik omurga statistical + replication bacağı sertleştirme (Cycle 27)

[[concepts/multiple_testing]] + [[concepts/anomaly_replication]] D
bloğu **3 paper × üç paralel methodology aile**:

| Paper | Yıl | Approach | Methodology aile | Sample |
|-------|-----|----------|------------------|--------|
| [[harvey_liu_zhu_2016_multiple_testing]] | 2016 | Multiple testing FDR control | **Frequentist** Bonferroni/Holm/BHY | 316 factor census |
| [[feng_giglio_xiu_2020_factor_zoo]] | 2020 | Omitted variable bias correction | **Frequentist** DS LASSO + Fama-MacBeth | 150 factor + 750 portfolio US 1976-2017 |
| **[[jensen_kelly_pedersen_2023_replication_crisis]]** | **2023** | Hierarchical Bayesian replication | **Bayesian Empirical Bayes** + 13 theme cluster | **153 factor × 93 country US 1926+ Global 1986+** |

**D bloğu replication ayağı 2 paper** (HXZ origin + JKP modern güncelleme):

| Paper | Yıl | Approach | Sample | Headline replication rate |
|-------|-----|----------|--------|---------------------------|
| [[hou_xue_zhang_2020_replicating_anomalies]] | 2020 | NYSE-VW empirik replication | 447 anomaly US 1967-2014 | %35 raw / %10 net q-factor |
| **[[jensen_kelly_pedersen_2023_replication_crisis]]** | **2023** | **Bayesian + global + capped VW** | **153 factor × 93 country** | **%84.9 Bayesian US / %84.0 Global** ⭐ |

**Wiki için yapısal kazanım**:
- D bloğu epistemik omurga **3 paper × üç paralel methodology aile**
  (frequentist FDR + frequentist ML + Bayesian hierarchical)
- D bloğu replication ayağı **2 paper × dramatic empirik fark**
  → 3. contradictions entry zorunlu

## Empirik Sonuçlar (sayılarla)

### 1. Replication rate decomposition [Figure 1]

| Spec | Replication rate | Methodology |
|------|------------------|-------------|
| HXZ 2020 raw returns | **%35** | NYSE-VW + 1/6/12-month + US-only |
| JKP US raw returns | **%56.9** | +4.3% longer sample +4.0% 1-month focus +8.5% capped VW +2.4% 15 ek factor +2.7% minor |
| JKP US exclude factors never sig | %64.7 | "factors never significant" düşürüldü |
| JKP US CAPM alphas | %77.3 | Bayesian benchmark CAPM (FF1993 değil) |
| HLZ MT-adjustment | %77.3 | Benjamini-Yekutieli FDR control |
| **JKP US Bayesian Empirical Bayes** | **%84.9** | Hierarchical model + theme dependence |
| **JKP Global Bayesian Empirical Bayes** | **%84.0** | 93 country global extension |

**Methodology decomposition kritik**: HXZ 2020 → JKP US raw %35 →
%56.9 (+21.9pp) **methodology choice'a aşırı duyarlı**:
- +8.5% capped VW (NYSE 80th percentile winsorize) vs pure VW —
  Nokia örneği [s.3 fn 3]: %70+ Finland market cap concentration
  pure VW'de mask ediliyor
- +4.3% longer sample
- +4.0% 1-month focus (HXZ üç paralel holding period factor count
  ×3)

### 2. 13 theme cluster taxonomy [Section 2]

**Algorithmic clustering** (Ward 1963 hierarchical clustering;
CAPM-residual returns):

| Theme | Sign convention | >75% replication? | Tangency portfolio? |
|-------|-----------------|---------------------|----------------------|
| Accruals* (low accruals long) | * | ✅ | ✅ |
| Debt Issuance* | * | ✅ | ✅ |
| Investment* | * | ✅ | **❌ displaced** |
| Leverage* | * | ❌ exception | ✅ |
| Low risk | — | ✅ | ✅ |
| Momentum | — | ✅ | ✅ |
| Profit Growth | — | ✅ | ✅ |
| Profitability | — | ✅ | **❌ displaced** |
| Quality | — | ✅ | ✅ |
| Seasonality | — | ❌ exception | ✅ |
| Size* | * | ❌ exception | **❌ displaced** |
| Skewness* | * | ✅ | ✅ |
| Value | — | ✅ | ✅ |

**10/13 themes >75% replication**; istisnalar: **seasonality,
leverage, size**.
**10/13 themes tangency portfolio'a positive weight**; **3 displaced**:
**profitability, investment, size**.

> 📝 **Profitability + Investment displaced (tangency)**: Q49
> partial-stronger + Q55 fully-answered (Cycle 26) ile **paralel
> nüans**. Profitability theme >75% replicate AMA tangency'ye
> displaced (other themes already capture variation). Wiki için:
> profitability factor **standalone replicate** ama joint modeling
> altında **redundant relative to other themes**. v0_draft
> Profitability seçimi (S&P 500 GP×V/P + NDX QMJ + GP/A) standalone
> sig kalır (Cycle 26 FGX validation güçlü) ama tangency portfolio
> joint allocation'da diğer theme'lere kayar.

### 3. Out-of-sample replication [Section 3]

- **In-sample period**: original reference paper sample
- **Out-of-sample (Panel A)**: in-sample öncesi dönem
- **Out-of-sample (Panel B)**: in-sample sonrası dönem
- **Out-of-sample (Panel C, combined)**: hem öncesi hem sonrası

**Sonuç [s.36-37]**:
- Post-original sample: **88.5% positive** (out-of-sample sürdürüyor)
- Combined out-of-sample: **88.5% positive**

**MP 2016 paterni paralel** (Cycle 11): %35 aggregate decay vs JKP
%88.5 positive — **dramatic farklı**; methodology decomposition
benzer (sample/methodology choice'lar).

### 4. Global decomposition

**93 country sample**: most developed countries Compustat 1986+;
emerging markets later. Global Bayesian replication rate **%84.0**
(US %84.9 ile çok benzer) → **factor research US-spesifik değil,
global**. International size-controlled, currency-standardized.

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | ⚠️ N/A → epistemic prerequisite (replication study factor inclusion test framework, decile-spread değil; **Top-N strategy spec için güçlü ön koşul**: 13 theme cluster taxonomy + tangency portfolio analysis Faz 3 strategy spec için multi-theme allocation framework) | N/A doğrudan + ⭐ epistemic prerequisite (tangency portfolio Faz 3 anchor) |
| **Annual rebalance** | ⚠️ partial fit: monthly factor returns + **1-month holding period default** (HXZ 1/6/12-month vs JKP only 1-month methodology farkı; +4.0% replication rate katkı). Wiki annual rebalance ile farklı methodology — sensitivity test gerekli (Q33+Q35+Q57+Q63 paralel) | ⚠️ partial; 1-month default annual uyarlama Q33 paralel |
| **Large-cap evrene transfer** | ⚠️ partial fit + ⭐ **capped value-weighting (NYSE 80th percentile winsorize)** large-cap focused ama mega-cap concentration kontrollü (Nokia örneği [s.3 fn 3]); HXZ pure VW + FF half-weight-small-stocks + JKP capped VW **üç methodology** trade-off; **explicit large-cap-only sub-sample test direct yok** ama capped VW methodology choice large-cap-relevant; size theme tangency'de displaced (Q11 paralel; size factor standalone replication >75% değil) | ⚠️ partial + ⭐ ⭐ capped VW NYSE 80th percentile methodology preference |
| **NDX intangibles / growth firms** | ⚠️ partial fit; **153 factor library 13 theme içinde Quality + Profitability + Profit Growth + Accruals* + Investment* + Value 6 theme intangibles-related characteristics dahil**; F bloğu intangibles factor'leri (Lev-Sougiannis Knowledge + Eisfeldt-Papanikolaou OC + Peters-Taylor q^tot) **explicit listed teyit edilmedi** (153 factor liste paperdan tek-tek kontrol edilmedi); ML-aware framework değil **Bayesian Empirical Bayes** (plan revize); Cycle 25 OC + Cycle 23 GP/A + Cycle 22 Israel-Moskowitz JKP framework'te muhtemelen dahil ama tek-tek teyit edilmedi (Q64 + Q67 paralel) | ⚠️ partial; F bloğu integration paperdan tek-tek teyit edilmedi |

**Strateji tasarımına net implikasyon:**

1. **3. contradictions entry zorunlu** (Cycle 13/19/22/26 paterni
   karar matrisi):
   - HXZ 2020: %35 raw replication (US-only NYSE-VW)
   - JKP 2023: %84.9 Bayesian US (capped VW + global + 1-month)
   - **~50pp gap dramatic empirik fark**
   - Methodology decomposition + Bayesian framework choice + global
     data extension scope-dependent
   - Wiki için: [[meta/contradictions]] **3. entry açılır**
     (HXZ 2020 vs JKP 2023 replication rate disagreement);
     resolution: scope-dependent + methodology disagreement; Cycle
     13 paterni paralel (MP %65 hayatta vs HXZ %10 net sig
     methodology disagreement scope-dependent)

2. **Q33 (post-2014 modern decay) fully-answered aday revize**:
   - JKP sample sonu **2020** (paperdan teyit; NBER WP Feb 2021);
     post-2014 → 2014-2020 6 yıl modern dönem kapsanmış
   - **Post-2020 (FAANG/AI 2021-2024) hala out-of-sample**
   - Q33 **partial-stronger** (fully-answered değil; 6 yıl modern
     dönem kanıt var ama post-2020 yok)
   - Chen-Zimmermann data portal (Cycle 29) ile birlikte tam
     fully-answered

3. **Q44 (post-2018 FAANG/AI) partial-stronger**:
   - JKP sample 2018-2020 dönemi kapsanmış
   - Post-2020 hala out-of-sample
   - Lev-Srivastava 2020 sample sonu 2018 + JKP 2020 → 2018-2020
     2 yıl partial validation

4. **Q63 (post-2017 FGX modern replikasyon) fully-answered**:
   - FGX 2020 sample sonu 2017 + JKP 2020 → 3 yıl modern güncelleme
   - JKP Bayesian hierarchical paralel methodology FGX DS LASSO
     ile complementary
   - **Q63 fully-answered** (Cycle 26 yeni → Cycle 27 fully-answered)

5. **D bloğu statistical bacağı 3 paper × üç paralel methodology
   aile**:
   - HLZ frequentist Bonferroni/BHY (data-snooping bias)
   - FGX frequentist DS LASSO (omitted variable bias)
   - **JKP Bayesian Empirical Bayes hierarchical (replication
     crisis cevap)**
   - Üç farklı epistemik yaklaşım, complementary, Faz 3 backtest
     spec için **üç paralel methodology layer**

6. **13 theme cluster Faz 3 strategy spec anchor**:
   - 10/13 themes tangency portfolio sig+ → **multi-theme allocation
     framework**
   - 3 displaced (profitability, investment, size) **redundant
     relative to other themes** joint modeling altında
   - Wiki için: factor selection + theme allocation iki paralel
     decision; v0_draft §1.B + §2.B factor inclusion list **theme
     diversification** yapısı eklenmeli (Faz 3 v1 revize)

7. **Capped value-weighting methodology** (NYSE 80th percentile
   winsorize):
   - HXZ pure VW + FF half-weight + **JKP capped VW** üç methodology
     trade-off
   - Wiki amaç evrenleri (S&P 500 + NDX top 100) zaten large-cap
     concentrated → capped VW Faz 3 implementation tercih edilebilir
     mega-cap (Apple, Microsoft, vb.) concentration distortion
     kontrolü için
   - [[methodology/backtest_spec]] §1.3 universe methodology yeni
     alt-bölüm: pure VW vs FF half-weight vs **capped VW** üç
     alternative methodology

## Limitler ve Caveats

- **Sample sonu 2020** — post-2020 (FAANG/AI 2021-2024) out-of-sample;
  modern data Chen-Zimmermann data portal (Cycle 29) + custom modern
  replication Faz 3 implementation
- **Bayesian framework choice** — frequentist HLZ + FGX paralel
  methodology lens'inde sonuç farklı (HLZ %77.3 MT-adj vs JKP %84.9
  Bayesian); methodology disagreement
- **Capped value-weighting NYSE 80th percentile**: HXZ pure VW
  paterninden +8.5pp replication rate; methodology choice empirik
  bulgular için kritik
- **1-month holding period default**: HXZ 1/6/12-month paterninden
  +4.0pp; wiki annual rebalance ile uyumsuz (Q33 paralel)
- **153 factor liste paperdan tek-tek kontrol edilmedi**: F bloğu
  intangibles factor'leri (Lev-Sougiannis Knowledge + Eisfeldt-
  Papanikolaou OC + Peters-Taylor q^tot) explicit dahil teyit edilmedi
  (Q64 paralel); 13 theme cluster içinde Quality + Profit Growth +
  Investment* themes intangibles-related ama tek-tek factor listesi
  Tablo C.3 paperdan kontrol edilmedi
- **F bloğu Q1 (Cycle 17 fully-answered) vs JKP value theme**: Lev-
  Srivastava 2020 vanilla HML 2010s NEGATIVE; JKP Bayesian value
  theme >75% replication global → **methodology disagreement**;
  intangibles-aware Bm rebuild (F bloğu 4-katmanlı) JKP framework'te
  yapılmamış
- **Composite scores DAHIL DEĞİL**: F-Score, G-Score, M-Score, F&V/P,
  G&V/P, QARP composite scoring strategies JKP 153 library individual
  factor census (HLZ + HXZ + FGX paterni paralel); composite scores
  Bayesian replication test wiki Faz 3 methodology gap (Q65 Cycle 26
  paralel)
- **HMXZ q5 model + JKP Bayesian framework**: q-factor model çapraz
  test wiki'de eksik

## İlgili Sayfalar

### Bu paperın update ettiği mevcut sayfalar

- [[concepts/anomaly_replication]] — **Cycle 13'ten beri açık
  placeholder DOLDURULU**: HXZ 2020 (US-only NYSE-VW empirik) +
  **JKP 2023 (global Bayesian Empirical Bayes hierarchical)**;
  replication crisis literatür hattı tablosu sertleştirme; iki paper
  × dramatic empirik fark
- [[concepts/multiple_testing]] — **D bloğu statistical bacağı 3
  paper × üç paralel methodology aile** sertleştirme: HLZ frequentist
  + FGX frequentist DS LASSO + **JKP Bayesian Empirical Bayes**
- [[concepts/post_publication_decay]] — dört darbe sentez tablosu
  replication kolonu **JKP 2023 modern data ile sertleştirme**;
  HXZ %10 + FGX %11 + JKP %84.9 dramatic methodology disagreement
- [[concepts/factor_zoo]] — 13 theme cluster taxonomy + tangency
  portfolio analysis; Cochrane #2/#3 Bayesian cevap (FGX frequentist
  DS LASSO paralel methodology)
- [[papers/mclean_pontiff_2016_post_publication_decay]] — MP %35
  aggregate decay (1972-2011) vs JKP %88.5 out-of-sample positive
  (combined) **dramatic empirik fark**; methodology disagreement
  scope-dependent paper sayfasında not (contradictions.md ek not
  yapılmadı, sadece HXZ vs JKP 3. entry)
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] — HXZ %35 raw
  / %10 net q-factor (US-only NYSE-VW 1967-2014) vs JKP %84.9
  Bayesian (US + global Bayesian capped VW 1926+); **3.
  contradictions entry zorunlu**; iki paper × dramatic empirik fark
- [[papers/feng_giglio_xiu_2020_factor_zoo]] — FGX 17/150 sig (%11
  recursive 1994-2016) + JKP 84.9% Bayesian (US 1926+) iki paralel
  ML-aware methodology farkı; D bloğu statistical bacağı 3 paper
  sertleştirme
- [[papers/harvey_liu_zhu_2016_multiple_testing]] — HLZ frequentist
  Bonferroni/BHY (data-snooping bias) + JKP Bayesian Empirical Bayes
  paralel methodology; D bloğu 3 paper sertleştirme; HLZ MT-adjustment
  77.3% paralel JKP CAPM α 77.3% (paper [Figure 1] iki rakam aynı)
- [[papers/asness_frazzini_pedersen_2019_qmj]] — QMJ Quality theme +
  Pedersen co-author overlap; QMJ paper'da QMJ vs replication
  literature explicit cite; JKP Quality theme >75% replicate sig
  + tangency'de sig+
- [[papers/lev_srivastava_2020_value_failure]] — Lev-Srivastava
  vanilla HML 2010s NEGATIVE (Q1 fully-answered Cycle 17) vs JKP
  Value theme >75% replicate global → **methodology disagreement**;
  intangibles-aware Bm rebuild (F bloğu 4-katmanlı) JKP framework
  yapılmamış (Q67 paralel)
- [[methodology/backtest_spec]] §1 universe & sample modern data
  anchor (post-2014 + post-2017 + post-2020 partial); §1.3 universe
  methodology **capped value-weighting** alternative; §4.4 darbe
  (4) replication-robust HXZ + JKP iki paralel methodology; §10
  bilinen zayıflıklar 1. madde "Modern data eksik" partial kapanma
  (JKP paper-form modern güncelleme)
- [[strategies/v0_draft]] §1.A + §2.A sample dönemi modern data
  anchor; §1.F + §2.F bilinen zayıflıklar partial kapanma; §5
  Cycle 27 JKP ✓; **§1.B + §2.B factor inclusion list theme
  diversification yapısı** Faz 3 v1 revize aday (10/13 themes
  tangency sig+ multi-theme allocation framework)
- [[meta/contradictions]] — **3. entry zorunlu** (HXZ 2020 vs JKP
  2023 dramatic empirik fark; ~50pp replication rate gap; methodology
  disagreement scope-dependent)
- [[methodology/data_sources]] — **Cycle 29 yeni**; JKP code repository
  GitHub bkelly-lab/GlobalFactor + WRDS open-source link explicit
  pointer dokümantasyonu; methodology/ klasörünün 2. sayfası;
  Bayesian Empirical Bayes hierarchical implementation Faz 3
  backtest implementation direct kullanılabilir; 153 factor × 93
  country code + data + meticulous documentation [paper s.2]

## Çelişkiler/Tartışmalar

### HXZ 2020 vs JKP 2023 — **3. contradictions entry zorunlu** ⚠️

**Plan §11 karar matrisi**: dramatic empirik fark → contradictions.md
3. entry açılır.

**Empirik durum**:
- HXZ 2020: **%35 raw replication** (US-only NYSE-VW 1967-2014, 447
  anomaly); ~%10 net q-factor sonrası → "factor zoo'nun büyük
  çoğunluğu false discovery"
- JKP 2023: **%84.9 Bayesian replication** (US 1926+, 153 factor) +
  **%84.0 Global** (93 country); → "factor research empirik kanıtla
  destekli collective body"
- **~50pp gap dramatic empirik fark** (raw rakam karşılaştırması:
  35% vs 56.9% JKP US raw +21.9pp; methodology decomposition kontrollü)

**Methodology disagreement scope-dependent** (paper [Figure 1]
explicit decomposition):
- HXZ pure VW vs JKP capped VW (NYSE 80th percentile winsorize):
  **+8.5pp** (Nokia örneği [s.3 fn 3]: %70+ Finland concentration
  pure VW'de mask)
- HXZ 1/6/12-month vs JKP 1-month focus: +4.0pp
- HXZ shorter sample vs JKP longer sample: +4.3pp
- HXZ 447 anomaly vs JKP 153 factor + 15 ek: +2.4pp
- Minor construction: +2.7pp

**Bayesian framework eklendiğinde**: %56.9 raw → %84.9 Bayesian (+28pp)

**Resolution**: **scope-dependent + methodology disagreement**.
Cycle 13 HXZ vs MP paterni paralel (MP equal-weight all-stocks vs
HXZ NYSE-VW microcap-arınmış scope-dependent). Wiki taraf tutmaz;
iki paper × iki paralel methodology empirik bulgular çelişen ama
**her iki sonuç kendi methodology context'inde geçerli**.

**Strateji implikasyonu**:
1. Faz 3 backtest spec için **methodology choice transparent
   reporting**: pure VW + FF half-weight + capped VW üç alternative
   sensitivity test
2. **Decay-adjusted spread baseline (×0.65 standard ×0.50 NDX
   agresif)** Cycle 24 v0_draft muhafazakâr revize **HXZ-paralel
   conservative tarafta**; JKP %85 replication paterni
   anti-conservative; wiki konservatizm korunur (over-promise
   riski)
3. **Theme cluster taxonomy + tangency portfolio analysis** Faz 3
   strategy spec anchor (10/13 themes sig+ multi-theme allocation
   framework)

### MP 2016 vs JKP 2023 (paralel ama dramatic farklı)

MP %35 aggregate decay (1972-2011, 82 anomaly) vs JKP %88.5
out-of-sample positive (combined). **Methodology farkı** (publication-
anchored regression vs Bayesian replication); empirik çelişen
bulgular **resolution scope-dependent**. **Yeni contradictions
entry açılmadı** (sadece HXZ vs JKP 3. entry; MP vs JKP paralel
note paper sayfasında).

### FGX 2020 vs JKP 2023 (üç paralel methodology)

FGX 17/150 sig (%11 recursive) + JKP %84.9 Bayesian aynı sample
window (1976-2017 vs 1926-2020 büyük overlap). **Methodology aile
farkı**: frequentist DS LASSO vs Bayesian Empirical Bayes
hierarchical. Çelişen değil **complementary methodology lens**;
iki paralel statistical concern (omitted variable bias vs hierarchical
dependence). [[concepts/multiple_testing]] D bloğu 3 paper × üç
paralel methodology aile sertleştirme.

### Lev-Srivastava 2020 vs JKP 2023 Value theme (Q67 paralel)

Lev-Srivastava: vanilla HML **2010s NEGATIVE** (Q1 fully-answered
Cycle 17) → "value strategies failed post-2010".
JKP: Value theme **>75% replicate** US + global Bayesian → "value
factor robust".

**Methodology disagreement**:
- Lev-Srivastava: vanilla HML decade-by-decade decomposition (Figure
  1) post-2010 NEGATIVE
- JKP: Bayesian Empirical Bayes hierarchical model + 13 theme cluster
  (Value cluster içinde many ratio'lar; vanilla HML sadece 1/N)
- JKP framework'te **intangibles-aware Bm rebuild yapılmamış** (F
  bloğu 4-katmanlı methodology integration eksik)

**Resolution**: scope-dependent (single-ratio vs theme cluster);
methodology disagreement (decomposition vs Bayesian); F bloğu
intangibles entegrasyon eksikliği. **Yeni contradictions entry
açılmadı**; paper sayfasında not + Q67 yeni.

## Açık Sorular (Open Questions)

- **Q33** (post-2014 modern decay) → **partial-stronger (fully-answered
  aday revize)**: JKP sample sonu 2020; post-2014 → 2014-2020 6 yıl
  modern dönem kapsanmış. Post-2020 (FAANG/AI 2021-2024) hala
  out-of-sample. Chen-Zimmermann data portal (Cycle 29) ile birlikte
  tam fully-answered.

- **Q44** (post-2018 FAANG/AI dönemi) → **partial-stronger**: JKP
  sample 2018-2020 2 yıl partial validation; post-2020 hala
  out-of-sample.

- **Q63** (post-2017 FGX modern replikasyon, Cycle 26 yeni) →
  **FULLY-ANSWERED** (Cycle 27): JKP Bayesian Empirical Bayes
  hierarchical paralel methodology FGX DS LASSO ile complementary;
  3 yıl modern güncelleme (FGX 2017 + JKP 2020 = 2017-2020 modern
  dönem kanıt).

- **Q5** (post-publication decay anchor) → **partial-stronger**:
  MP %35 aggregate decay (1972-2011, 82 anomaly) + JKP %88.5
  out-of-sample positive (combined) **dramatic farklı**; iki paper
  × iki paralel methodology resolution scope-dependent + methodology
  disagreement (publication-anchored regression vs Bayesian
  replication).

- **Q49** (4 quality dimension hangisi en güçlü) → **partial-stronger**:
  JKP Profitability theme >75% replicate AMA tangency'ye **displaced**
  (other themes already capture variation); v0_draft Profitability
  seçim **standalone** geçerli ama joint modeling redundancy
  kanıtı yeni layer.

- **Yeni Q'lar (Cycle 27)**:
  - **Q66 yeni**: ML methodology factor selection vs Bayesian
    methodology comparison: HLZ + FGX frequentist + **JKP Bayesian**
    iki paralel epistemic family wiki için; hangisi Faz 3
    backtest spec için baseline?
  - **Q67 yeni**: Lev-Srivastava vanilla HML 2010s NEGATIVE vs
    JKP Value theme >75% replicate methodology disagreement;
    intangibles-aware Bm rebuild (F bloğu 4-katmanlı) JKP
    framework'te yapılmamış; F bloğu integration JKP Bayesian
    Empirical Bayes hierarchical methodology sensitivity test
    Faz 3 implementation
  - **Q68 yeni**: Capped value-weighting (JKP NYSE 80th percentile
    winsorize) vs pure VW (HXZ) vs FF half-weight (Fama-French)
    üç methodology trade-off; wiki amaç evrenleri S&P 500 + NDX
    için optimal weighting scheme
  - **Q69 yeni**: 13 theme cluster taxonomy NDX-spesifik subsample
    decomposition: NDX top 100 non-financial muhtemelen Quality +
    Profitability + Investment + Profit Growth themes dominantı;
    diğer themes (Seasonality + Size + Skewness*) NDX-relevant değil;
    Faz 3 NDX strategy spec **theme diversification** simplified
  - **Q70 yeni**: Tangency portfolio 10/13 themes sig+ multi-theme
    allocation framework Faz 3 strategy spec anchor; 3 displaced
    (profitability, investment, size) joint modeling redundancy;
    factor selection vs theme allocation iki paralel decision

## Strateji tasarımına spesifik katkı

1. **3. contradictions entry zorunlu** (HXZ 2020 vs JKP 2023):
   methodology disagreement transparent reporting; Faz 3 backtest
   spec **methodology choice sensitivity test** üç alternative
   (pure VW + FF half-weight + capped VW)

2. **D bloğu statistical bacağı 3 paper × üç paralel methodology
   aile sertleştirme** ([[concepts/multiple_testing]] +
   [[concepts/anomaly_replication]]):
   - HLZ frequentist Bonferroni/BHY (data-snooping bias)
   - FGX frequentist DS LASSO (omitted variable bias)
   - **JKP Bayesian Empirical Bayes hierarchical (replication
     crisis cevap)**

3. **13 theme cluster + tangency portfolio Faz 3 strategy spec
   anchor**:
   - 10/13 themes sig+ multi-theme allocation framework
   - 3 displaced (profitability, investment, size) joint modeling
     redundancy
   - v0_draft §1.B + §2.B factor inclusion list **theme diversification
     yapısı** Faz 3 v1 revize aday

4. **Capped value-weighting (NYSE 80th percentile) Faz 3 implementation
   tercih**:
   - Mega-cap (Apple, Microsoft) concentration distortion kontrolü
   - HXZ pure VW + FF half-weight + JKP capped VW üç alternative
     sensitivity test
   - Wiki amaç evrenleri (S&P 500 + NDX top 100) zaten large-cap
     concentrated; capped VW natural fit

5. **Modern data infrastructure**:
   - JKP code repository (GitHub bkelly-lab/GlobalFactor) + WRDS
     open-source link Faz 3 backtest implementation direct
     kullanılabilir
   - **Chen-Zimmermann data portal (Cycle 29)** ile complementary

6. **Q33 + Q44 + Q63 modern dönem kanıt**:
   - 2014-2020 modern dönem 6 yıl kanıt (JKP sample)
   - Post-2020 (FAANG/AI 2021-2024) hala out-of-sample
   - v0_draft "Modern data eksik" weakness **partial kapanma**
     (paper-form modern güncelleme)

7. **Out-of-sample 88.5% positive**:
   - MP %35 aggregate decay vs JKP %88.5 positive **dramatic farklı**
   - Faz 3 backtest spec için decay multiplier ×0.65 standard +
     ×0.50 NDX agresif Cycle 24 muhafazakâr revize **HXZ + MP
     paralel conservative tarafta**; JKP %88.5 anti-conservative;
     **wiki konservatizm korunur** (over-promise riski Cycle 24
     karar)

8. **Theme cluster Q49 paralel insight**:
   - Profitability theme >75% replicate **standalone** sig
   - Tangency portfolio'a **displaced** (other themes already
     capture variation)
   - QMJ 4-dimension hierarchy paralel: composite QMJ DS-sig FGX
     + JKP Profitability theme replicate; ama dimension-spesifik
     hierarchy (Q49 partial-stronger)

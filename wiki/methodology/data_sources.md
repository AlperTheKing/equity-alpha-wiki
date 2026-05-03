---
type: methodology
name: data_sources
status: skeleton
opened: 2026-05-02
phase: faz_2_cycle_29
purpose: "Faz 3 backtest implementation modern data infrastructure pointer dokümantasyonu"
sources: ["Chen-Zimmermann 2022 Open Asset Pricing Database", "JKP 2023 GlobalFactor code repository", "WRDS open-source access"]
---

# methodology/data_sources — Modern Data Infrastructure Pointer

> 📝 **Cycle 29 açılış (Faz 2 yapısal devam).** methodology/ klasörünün
> **2. sayfası** (Cycle 21 [[methodology/backtest_spec]] sonrası).
> Paper sayfası **DEĞİL** — veri portalı/code repository **pointer
> dokümantasyonu**. Faz 3 backtest implementation modern data + 
> replikasyon altyapısı için **tek kaynak-of-truth**.
>
> **Skeleton statüsü**: Cycle 30 v0 → v1 revize draft + Cycle 31 
> Faz 2 sertifika + Faz 3 implementation sonunda bölümler genişler.
> Cycle 32 §11.5 ardışık consolidation pass'inde ilk re-review.
>
> 📝 **Cycle 32 inbound cross-link**: [[strategies/sp500_v1]] formal
> spec §5 (Backtest Implementation Roadmap) bu sayfanın §1-3'üne
> atıfla yazılmıştır (Chen-Zimmermann + JKP code repository + WRDS
> üç paralel kaynak; capped VW NYSE 80th percentile winsorize Faz 3
> tercih §5 referansla; sp500_v1 ilk implementation kullanıcısı).
>
> 📝 **Cycle 33 inbound cross-link**: [[strategies/nasdaq100_v1]]
> formal spec §5 bu sayfanın §1-3'üne atıfla yazıldı; **NDX-spesifik
> data feed configuration Q72 paralel** (top 100 non-financial Nasdaq
> sub-universe filtering + index reconstitution annual June + quarterly
> review + WRDS data feed configuration); F bloğu 4-katmanlı modern
> data implementation (Knowledge perpetual inventory industry-spesifik
> δ + Organization Eisfeldt-Papanikolaou full SG&A δ=15% vs
> Peters-Taylor θ=0.30 Q60 horse race + Total q^tot proxy + Application
> Lev-Srivastava adjusted HML); 13 theme cluster NDX subsample
> re-estimation (5 NDX-specific theme vs 13 universal Q69 paralel).

---

## 1. Chen-Zimmermann 2022 Open Asset Pricing Database

### 1.1 Pointer

- **Resmi URL**: https://www.openassetpricing.com/
- **Tier durumu**: source_tier_list #41 (Tier 2 — modern replication
  database; data portal değil paper)
- **WRDS access**: open-source via WRDS academic platform link
- **GitHub** (kod): https://github.com/OpenSourceAP/CrossSection
- **Sample**: 200+ anomaly modern replikasyon database (1926+ US
  base; international extension limited)

### 1.2 Methodology

- **Pure replication** (Hamermesh "scientific replication" değil) —
  [[papers/jensen_kelly_pedersen_2023_replication_crisis]] [s.1 fn 1]
  explicit: "Chen and Zimmermann (2020) consider pure replication,
  attempting to use the same data and methods as the original papers
  for a large number of factors."
- **Reproducibility infrastructure**: factor return time-series +
  paper-by-paper methodology details + machine-readable codes
- **JKP framing** [s.1 fn 1]: "They are able to reproduce nearly
  100% of factors, but Hou et al. (2020) challenge the **scientific**
  replication and Harvey et al. (2016) challenge validity due to
  multiple testing."
- **Pure ↔ scientific replication ayrımı** kritik: Chen-Zimmermann
  pure replication ~100% (aynı data + aynı method); HXZ 2020
  scientific replication %35 (NYSE-VW + 1/6/12-month methodology
  choice farklı sonuç); JKP %85 Bayesian (capped VW + Bayesian
  framework). Üç paper × üç methodology aile factor zoo decay
  conservative-side; **Chen-Zimmermann pure replication
  anti-conservative-side ucu** (~100% reproducible)

### 1.3 Faz 3 implementation rolü

- **Methodology choice sensitivity test data altyapısı**: pure VW
  (HXZ baseline) + capped VW (JKP baseline) + FF half-weight üç
  alternative weighting scheme empirik validation
- **HXZ 2020 + JKP 2023 paterni paralel**: HXZ NYSE-VW empirik
  replication 447 anomaly (1967-2014) vs JKP Bayesian Empirical
  Bayes 153 factor 93 country (1926-2020) **iki paralel methodology
  → Chen-Zimmermann common pure replication baseline**
- **Composite scores**: F-Score / G-Score / M-Score / F&V/P / G&V/P
  / QARP composite scoring strategies wiki Faz 3 implementation
  Chen-Zimmermann database üzerine custom composite construction
  ([[meta/data_gaps]] Q65 Cycle 26 yeni paralel)

### 1.4 Caveats

- **Pure replication ≠ wiki amaçları için yeterli**: HXZ 2020 +
  JKP 2023 + FGX 2020 dramatic methodology disagreement
  ([[meta/contradictions]] §3) gösteriyor ki **methodology choice'a
  aşırı duyarlı** sonuç; pure replication baseline değil **starting
  point** olarak kullanılır
- **Sample sonu** (Chen-Zimmermann 2022 paper publication):
  Cycle 29 ingest sırasında database update durumu paperdan teyit
  edilmedi (data portal aktif olarak güncellenir; post-2020 modern
  dönem dahil olabilir)
- **International extension limited**: US base 1926+ comprehensive
  ama global data limited (Compustat international ile birleştirme
  Faz 3 implementation sırasında JKP GlobalFactor ile cross-validate)

---

## 2. JKP 2023 GlobalFactor Code Repository

### 2.1 Pointer

- **GitHub**: https://github.com/bkelly-lab/GlobalFactor (paper [s.2]
  explicit)
- **Author website**: bryankellyacademic.org (Bryan Kelly, Yale SOM)
- **WRDS access**: paper [s.2] "made this data set easily accessible
  to researchers via a direct open-source link to WRDS"
- **Code + data + documentation**: paper [s.2] "meticulous
  documentation of the data set and the underlying code base to
  reproduce it"

### 2.2 Methodology

- **153 factor × 93 country** Bayesian Empirical Bayes hierarchical
  implementation
- **Sample**: US 1926+ (CRSP), Global 1986+ (Compustat International)
- **Capped value-weighting** (NYSE 80th percentile winsorize) —
  default weighting scheme; Faz 3 implementation tercih aday
- **1-month holding period** default
- **Annual + quarterly accounting data** + 4-month accounting lag +
  quarterly aggregate 4-quarter rolling
- **13 theme cluster taxonomy** (Ward 1963 hierarchical clustering;
  CAPM-residual returns within-theme correlation > 0.5 in 10/13)
- **Tangency portfolio analysis** (10/13 themes sig+; 3 displaced:
  profitability + investment + size)

### 2.3 Faz 3 implementation rolü

- **Bayesian Empirical Bayes hierarchical model** direct implementation
  (HLZ frequentist Bonferroni/BHY + FGX frequentist DS LASSO + **JKP
  Bayesian** üç paralel methodology aile factor selection)
- **13 theme cluster + tangency portfolio multi-theme allocation
  framework** Faz 3 strategy spec anchor (factor selection + theme
  allocation iki paralel decision)
- **Capped VW methodology** Faz 3 implementation tercih aday (mega-cap
  concentration distortion kontrolü; wiki amaç evrenleri large-cap
  concentrated natural fit)
- **Modern data + global extension** post-2014 + post-2018 + post-2020
  dönemlerinde out-of-sample validation

### 2.4 Caveats

- **Bayesian Empirical Bayes framework**: HLZ frequentist + FGX
  frequentist methodology aile farklı (Cycle 26 + 27 sertleştirme)
- **Sample sonu Dec 2020**: post-2020 (FAANG/AI 2021-2024) hala
  out-of-sample; Chen-Zimmermann database güncellemesi + Faz 3
  custom modern replikasyon ile tam kapanma
- **Anti-conservative-side framework**: %84.9 US / %84.0 Global
  Bayesian replication rate; HXZ %35 raw + FGX %11 recursive +
  MP %35 decay conservative-side baseline ile dramatic methodology
  disagreement ([[meta/contradictions]] §3)

---

## 3. WRDS Open-Source Access

### 3.1 Pointer

- **Wharton Research Data Services**: https://wrds-www.wharton.upenn.edu/
- **Academic data access platform**: institutional subscription gerekli
  (üniversite üyeliği)
- **Data feeds**:
  - **CRSP** (Center for Research in Security Prices): US stock
    return + market cap + share code 10/11 data
  - **Compustat North America**: accounting data US stocks
  - **Compustat Global**: international accounting data
  - **IBES**: analyst forecasts
  - **Chen-Zimmermann + JKP GlobalFactor + Pa̧stor-Stambaugh +
    AQR data sets**: published factor return time-series

### 3.2 Faz 3 implementation rolü

- **Ortak access point**: Chen-Zimmermann + JKP + Compustat + CRSP
  ortak altyapı; tek WRDS subscription ile tüm modern data +
  replikasyon database access
- **Wiki amaç evrenleri data feed'ler**:
  - **S&P 500**: CRSP US + Compustat North America + IBES analyst
    forecasts
  - **NDX top 100 non-financial**: CRSP US Nasdaq-listed subset
    + Compustat North America + tech sektör IBES
- **JKP open-source link**: paper [s.2] explicit "direct open-source
  link to WRDS" — GlobalFactor data WRDS üzerinden academic erişim
- **Q72 paralel**: WRDS NDX-spesifik subsample optimal data feed
  configuration Faz 3 implementation kararı

### 3.3 Caveats

- **Institutional access gerekli**: bireysel araştırmacı için
  paywall; academic affiliation veya commercial subscription şart
- **Data licensing**: Compustat + CRSP licensing terms academic-only;
  commercial production use ek licensing
- **Update frequency**: monthly/quarterly batch update; real-time
  data feed değil (Faz 3 historical backtest implementation için
  yeterli)

---

## 4. Faz 3 backtest implementation ön koşul

### 4.1 Modern data infrastructure (üç paralel kaynak)

| Kaynak | Methodology aile | Faz 3 rolü |
|--------|------------------|------------|
| Chen-Zimmermann 2022 | Pure replication (~100% reproducible) | Methodology choice sensitivity test baseline |
| JKP 2023 GlobalFactor | Bayesian Empirical Bayes hierarchical (capped VW) | 13 theme cluster + tangency portfolio + multi-theme allocation framework |
| WRDS (CRSP + Compustat) | Raw data feed | Custom composite scoring + adjusted Bm rebuild + dynamic implementation |

### 4.2 Replication infrastructure

- **HXZ 2020 NYSE-VW empirik** (1967-2014): conservative-side baseline
  ([[meta/contradictions]] §3 ana entry; ×0.65 / ×0.50 decay multiplier)
- **JKP 2023 capped VW Bayesian** (1926-2020): anti-conservative-side
  upper bound sensitivity reference
- **Chen-Zimmermann pure replication** (1926+ US base): methodology
  choice sensitivity test ortak data altyapısı
- **MP 2016 aggregate %35 decay**: behavioral decay benchmark
- **FGX 2020 17/150 sig (%11) recursive**: omitted variable bias
  correction filter

### 4.3 Üç paralel statistical methodology aile (Cycle 26 + 27 sertleştirme)

- **HLZ frequentist Bonferroni/BHY** (data-snooping bias FDR control;
  cutoff `|t| > 3.0` BHY 1%)
- **FGX frequentist DS LASSO** (omitted variable bias model selection
  correction; SDF loading test)
- **JKP Bayesian Empirical Bayes hierarchical** (replication crisis
  cevap; 13 theme cluster + tangency portfolio)

### 4.4 13 theme cluster + tangency portfolio multi-theme allocation framework

- 10/13 themes tangency portfolio sig+: Accruals* + Debt Issuance* +
  Leverage* + Low risk + Momentum + Profit Growth + Quality +
  Seasonality + Skewness* + Value
- 3 displaced (joint modeling redundancy): Profitability + Investment +
  Size
- Faz 3 strategy spec **multi-theme allocation framework anchor**:
  factor selection + theme allocation iki paralel decision

---

## 5. Methodology choice sensitivity test (üç alternative weighting)

[[methodology/backtest_spec]] §1.3 + §4.4 cross-link:

| Methodology | Source | Faz 3 rolü |
|-------------|--------|------------|
| **Pure VW** | [[papers/hou_xue_zhang_2020_replicating_anomalies]] | Conservative baseline (microcap-arınmış) |
| **FF half-weight** | [[papers/famafrench1993_three_factor]] | Size sortunda small + large eşit ağırlık |
| **Capped VW** (NYSE 80th percentile winsorize) | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] | Mega-cap concentration distortion kontrolü; **Faz 3 implementation tercih aday** |

**3. contradictions entry** ([[meta/contradictions]] §3 HXZ ↔ JKP):
methodology choice'a aşırı duyarlı (~50pp gap; capped VW alone +8.5pp);
**üç alternative replication-robust filter** transparent reporting
zorunlu.

---

## 6. Cross-references

### Methodology
- [[methodology/backtest_spec]] §1 universe & sample modern data
  anchor; §1.3 üç alternative weighting; §4.4 darbe (4) replication-
  robust HXZ + JKP iki paralel methodology

### Strategy
- [[strategies/v0_draft]] §1.A + §2.A modern data anchor; §1.F + §2.F
  "Modern data eksik" weakness **tam kapanma** (Cycle 27 partial →
  Cycle 29 tam)

### Concepts
- [[concepts/anomaly_replication]] — Cycle 13'ten beri "Chen-Zimmermann
  2022 placeholder" replication crisis literatür hattı tablosu
  doldurulu
- [[concepts/multiple_testing]] — D bloğu statistical bacağı 3 paper
  × üç paralel methodology aile data infrastructure cross-link
- [[concepts/post_publication_decay]] — dört darbe sentez tablosu
  modern data anchor

### Anchor papers
- [[papers/jensen_kelly_pedersen_2023_replication_crisis]] — Cycle 27
  ingest; GlobalFactor code repository origin
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] — Cycle 13
  ingest; Chen-Zimmermann 2022 [s.1 fn 1] paralel cross-link
- [[papers/mclean_pontiff_2016_post_publication_decay]] — modern
  güncelleme infrastructure
- [[papers/feng_giglio_xiu_2020_factor_zoo]] — modern data extension

### Meta
- [[meta/source_tier_list]] — Tier 2 #41 Chen-Zimmermann 2022 status
  update (data portal pointer; tam ingest gerekmez)
- [[meta/data_gaps]] — Cycle 29 sonrası bölüm; Modern data eksik
  tam kapanma
- [[meta/handoff_faz2]] — Faz 2 sertifika kriteri Modern replication
  ✓ (JKP 2023 + Chen-Zimmermann 2022 portal)

---

## 7. Bilinen zayıflıklar ve caveats

> 📝 Faz 3'te formalize: implementation sırasında karşılaşılan
> data quality + access + methodology issues `wiki/strategies/known_weaknesses.md`'e
> taşınır.

1. **Chen-Zimmermann pure replication ≠ scientific replication**
   (HXZ 2020 paterni; JKP [s.1 fn 1] explicit ayrım)
2. **Sample sonu post-2020 hala out-of-sample**: FAANG/AI 2021-2024
   modern dönem Faz 3 custom implementation ile kapanma
3. **WRDS institutional access paywall**: bireysel araştırmacı için
   alternative API'ler (Yahoo Finance, Quandl, Stooq) limited
   accounting data
4. **International data limited**: Chen-Zimmermann US base; JKP 93
   country global extension Faz 3 NDX dışı için kullanılabilir ama
   wiki amaç evrenleri (S&P 500 + NDX top 100) US-only
5. **Composite scores wiki Faz 3 implementation**: F-Score / G-Score
   / M-Score / F&V/P / G&V/P / QARP **individual factor census
   dışı** (Q65 Cycle 26 + Cycle 29 paralel); custom composite
   construction Faz 3 backtest implementation
6. **Real-time data feed YOK**: monthly/quarterly batch update;
   live trading implementation Faz 3 dışı (academic backtest
   implementation odaklı)

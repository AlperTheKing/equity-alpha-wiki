---
type: paper
authors: [Harvey, Campbell R., Liu, Yan, Zhu, Heqing]
year: 2016
title: "...and the Cross-Section of Expected Returns"
venue: "Review of Financial Studies 29 (1), 5-68 (NBER WP 20592, October 2014)"
url: https://www.nber.org/papers/w20592
local_path: raw/papers/harvey_liu_zhu_2016_cross_section.pdf
ingested: 2026-04-30
tags: [multiple_testing, FDR, Bonferroni, Holm, BHY, factor_zoo, replication, statistical_filter, epistemic_backbone, D_blok_2]
status: ingested
---

# Harvey, Liu & Zhu (2016) — Multiple Testing Cross-Section

> 📝 **Atıf konvansiyonu:** `[Tablo N]`, `[Şekil N]` ve `[s. X]` NBER WP
> (October 2014) sayfa numarası. Embedded text extract:
> `raw/papers/harvey_liu_zhu_2016_cross_section.txt`. JF 2016 final yayın
> sayfa numaraları farklı, tablo numaraları aynı.

> 📝 **D bloğunun #2'si** — replication / multiple testing / decay.
> Cycle 11'de [[mclean_pontiff_2016_post_publication_decay]] (behavioral
> decay bacağı) ingest edildi; bu paper **statistical FDR bacağını**
> kuruyor. Wiki epistemik omurgası iki bağımsız multiple-testing
> mekanizmasıyla tamamlanıyor: post-publication arbitraj + multiple-
> testing düzeltmesi.

## TL;DR

**313 published + 63 working = 316 factor**, 1967-2014 (paperin yazıldığı
zaman) akademik finans-muhasebe-ekonomi dergilerinde rapor edilmiş
cross-sectional return predictors. Geleneksel `|t| > 2.0` kesim eşiği
multiple-testing context'inde **yetersiz**; üç düzeltme prosedürü
(Bonferroni, Holm, BHY) önerilir [Tablo 3, s.13]. **Recommended cutoffs
2012 itibariyle (M = R, all tests observable varsayımıyla)** [Şekil 3,
s.22]:

- **Bonferroni:** `|t| > 3.78` (FWER %5)
- **Holm:** Bonferroni'ye yakın, hafif altta (sequential FWER, %5)
- **BHY:** `|t| > 3.39` (FDR %1) veya `|t| > 2.78` (FDR %5)

**Hidden tests düzeltmesi (M > R)** ile (paperin tahminine göre %71
factor missing) [s.24-25]:

- Bonferroni 4.01
- Holm 3.96
- BHY 3.68 (FDR %1) veya **3.18 (FDR %5)** — paperin önerdiği **mutlak
  minimum**

**2032 projeksiyon** (factor production rate son yıllar gibi devam
ederse) [Şekil 3]: Bonferroni 4.00.

**Ana mesaj [s.1, s.55]:** "Most claimed research findings in financial
economics are likely false." Tıbbi literatürdeki Ioannidis (2005)
"Why Most Published Research Findings Are False" tezi finans için de
geçerli.

**Yorumu [Şekil 3 mark'leri]:** Geleneksel "flagship" faktörlerin **bir
kısmı** multiple-testing'i geçer (HML, MOM, DCG, SRV, MRT — Bonferroni
+ Holm + BHY her üçünde sig); **bir kısmı bazen geçer** (EP, LIQ, CVOL);
**bir kısmı asla geçmez** (SMB, DEF, IVOL, LRV).

> ⚠️ **Wiki amacı için "üç darbe" çerçevesinin statistical bacağı:**
> [[piotroski2000_f_score]] [Tablo 4] large-cap zayıflık (in-sample
> hurdle) + [[mclean_pontiff_2016_post_publication_decay]] [Tablo 8]
> post-pub decay büyük cap'te agresif (behavioral hurdle) +
> **HLZ multiple-testing-corrected sig hurdle** (statistical hurdle).
> Wiki'nin Faz 3 strateji baseline'ı bir factor'u dahil ederken üç
> hurdle'ı da geçen factorleri arayacak. Detay
> [[concepts/multiple_testing]] aggregate tablosu +
> [[concepts/post_publication_decay]] "Üç darbe çerçevesi" alt-bölümü.

## Tek Cümle Tezi

Akademik literatürde önerilen 316 cross-sectional asset pricing factor'ün
multiple-testing context'inde değerlendirilmesi gerekir; geleneksel
`|t| > 2.0` kesim eşiği hidden-tests + correlated tests ile önemli ölçüde
yetersizdir; modern asset pricing araştırması için **mutlak minimum
`|t| > 3.0`** (BHY-FDR-1% veya M>R adjusted-5%) eşiği gereklidir; finans
literatüründe iddia edilen bulguların **çoğu büyük olasılıkla yanlış**.

## Ortaya Konan Sinyal/Faktör

**Yeni empirik faktör YOK.** Bu paper bir **methodology paper** —
mevcut faktörlerin **statistical filter** kriterini değiştiriyor.
Wiki'de bu paperdan yeni `factors/*` sayfası açılmadı. Yerine **bir
concept sayfası açıldı:**

- [[concepts/multiple_testing]] — concept; 3 düzeltme prosedürü hierarchy
  (Bonferroni / Holm / BHY) + FWER vs FDR farkı + recommended cutoff'lar
  + wiki'deki ingested 11 paper / 11 factor için **aggregate
  multiple-testing-corrected sig durumu tablosu**

> 📝 **Cycle 12 kullanıcı kararı 2:** false_discovery_rate ayrı sayfa
> AÇILMADI; FDR (BHY procedure) multiple_testing.md içinde alt-bölüm.
> Ayrı sayfa Faz 2'de ML asset pricing (Gu-Kelly-Xiu) FDR'ı çok özel
> kullanırsa açılabilir.

## Metodoloji

### 316 factor seçimi [s.1-3, Section 2]

- 313 published papers + 63 selected working papers
- Top journals (finans / accounting / economics)
- Cross-sectional return predictor'lar; sample-period overlapping
- 316 different factors (some highly correlated; e.g., 4 idiosyncratic
  volatility variants)

### Factor classification [Tablo 1, s.4]

| Risk type | Sub-category | # factors |
|---|---|---|
| **Common (113)** | Financial | 46 |
|  | Macro | 40 |
|  | Microstructure | 11 |
|  | Behavioral | 3 |
|  | Accounting | 8 |
|  | Other | 5 |
| **Individual (202)** | Financial | 61 |
|  | Microstructure | 28 |
|  | Behavioral | 3 |
|  | Accounting | 87 |
|  | Other | 24 |

> 📝 "Common" = aggregate factor / mimicking-portfolio (FF tradition);
> "Individual" = stock-level characteristic (cross-sectional regression).
> Wiki'deki paperlar büyük ölçüde "Accounting + Financial" alt-grupların
> kesişimini hedefliyor (Sloan accruals = Accounting Individual; Piotroski
> F-Score = Accounting composite, Individual; Mohanram G-Score = aynı).

### Factor production rate [Şekil 2, s.20]

- 1980-1991: ~1 factor/yıl
- 1991-2003: ~5 factor/yıl
- 2003-2012: ~18 factor/yıl (acceleration)
- 2012'de cumulative 316 factor; 2032 projeksiyon ~600+ factor (linear
  extrapolation)

### Three multiple-testing methods [Tablo 3, s.13]

| Adjustment | Type | Error rate | Stringency |
|---|---|---|---|
| **Bonferroni** | Single step | FWER | Most stringent |
| **Holm** | Sequential step-down | FWER | Bonferroni ≤ Holm |
| **BHY (Benjamini-Hochberg-Yekutieli)** | Sequential | FDR (false discovery rate) | Most lenient |

**FWER vs FDR farkı [s.8-12]:**
- **FWER (Family-Wise Error Rate):** P(en az bir false discovery). Stringent.
- **FDR (False Discovery Rate):** Expected proportion of false discoveries
  arasında discoveries. Daha lenient — total discovery sayısı arttıkça
  Bonferroni/Holm prohibitively stringent olurken FDR scale eder.

### Bonferroni adjustment [s.13]

```
p_i^Bonferroni = min[M × p_i, 1]
```

M = total tests, p_i = original p-value. Single step, dependence
structure'a duyarsız.

### Holm adjustment [s.14-15]

Sequential step-down; ordered p-values üzerinde:
```
Reject H_(k) if p_(k) ≤ α_w / (M + 1 - k)
```

Bonferroni ≤ Holm: Holm her durumda Bonferroni discoveries'i içerir +
ek discoveries ekler.

### BHY adjustment [s.15-17]

Sequential step-up; ordered p-values üzerinde:
```
Reject H_(k) if p_(k) ≤ (k / [M × c(M)]) × α_d
```

`c(M) = Σ(1/j)` for j=1..M; arbitrary dependence structure altında valid.

> 📝 **Pratik fark:** 10-test örneğinde [Tablo 4, s.13] α=5% level'da:
> - Single test: 10/10 sig
> - Bonferroni: 3/10 sig
> - Holm: 4/10 sig
> - BHY: 6/10 sig

### Recommended cutoffs [Şekil 3, s.22]

**M = R (all tests observable, paperdaki ana asumpsiyon):**

| Method | 2012 | 2032 (projection) | Significance |
|---|---|---|---|
| Bonferroni | **3.78** | **4.00** | FWER 5% |
| Holm | ~3.6 | ~3.8 | FWER 5% |
| BHY | **3.39** | **3.40** (stationary) | FDR 1% |
| BHY | **2.78** | **2.81** (stationary) | FDR 5% |

**M > R (hidden tests, paperin %71 missing factor tahmini) [s.24-25]:**

| Method | 2012 |
|---|---|
| Bonferroni | 4.01 |
| Holm | 3.96 |
| BHY (1%) | 3.68 |
| BHY (5%) | **3.18** ← paperin önerdiği MUTLAK MINIMUM |

> 📝 **Wiki için pratik kural:** `|t| > 3.0` baseline (BHY 1%, M=R) +
> NDX agresif sensitivity için `|t| > 3.78` (Bonferroni, M=R) — çift
> hurdle.

## Empirik Sonuçlar (sayılarla)

### Şekil 3 — Selected factors' multiple-testing performance [s.22]

Paperin Şekil 3'ünde işaretli flagship faktörlerin durumu:

| Faktör | Source | Reported |t| | Bonferroni | Holm | BHY | Wiki status |
|---|---|---|---|---|---|---|
| **HML** (book-to-market) | Fama-French (1992) | ~6 | sig | sig | sig | [[HML]] ingested |
| **MOM** (momentum) | Carhart (1997) | 4.46 | sig | sig | sig | [[UMD]] ingested |
| **DCG** (durable cons. goods) | Yogo (2006) | sig | sig | sig | sig | henüz wiki'de yok |
| **SRV** (short-run vol.) | Adrian-Rosenberg (2008) | sig | sig | sig | sig | henüz wiki'de yok |
| **MRT** (market beta) | Fama-MacBeth (1973) | 2.57 | borderline | sig | sig | (CAPM-base) |
| **EP** (earnings-price) | Basu (1983) | varies | sometimes | sometimes | sometimes | henüz wiki'de yok |
| **LIQ** (liquidity) | Pastor-Stambaugh (2003) | varies | sometimes | sometimes | sometimes | henüz wiki'de yok |
| **CVOL** (consumption vol.) | Boguth-Kuehn (2012) | varies | sometimes | sometimes | sometimes | henüz wiki'de yok |
| **SMB** (size) | Fama-French (1992) | 1.73 (FF93)-2.5 (varies) | **never sig** | **never sig** | **never sig** | [[SMB]] ingested ⚠️ |
| **DEF** (default) | Vassalou-Xing (2004) | varies | never | never | never | henüz wiki'de yok |
| **IVOL** (idio vol.) | Ang vd. (2006) | varies | never | never | never | henüz wiki'de yok |
| **LRV** (long-run vol.) | Adrian-Rosenberg (2008) | varies | never | never | never | henüz wiki'de yok |

> ⚠️ **Wiki'de ingested faktörler için kritik bulgu:** **SMB hiçbir
> multiple-testing düzeltmesini geçmiyor**. FF93'te t=1.73 zaten klasik
> standartta marjinal; HLZ-corrected hiçbir adjustment'ta sig değil. Bu,
> wiki'nin SMB exposure'ını "factor-model baseline" olarak kullanma
> kararını **statistical bias yönünden de** sorguluyor. Detay
> [[concepts/multiple_testing]] aggregate tablo.

### Hidden tests adjustment [Section 4.7, s.24-25]

Paperin Appendix A'sında M > R durumunda %71 factor missing tahmini.
Bonferroni cutoff M=R 3.78 → M>R 4.01; BHY (5%) M=R 2.78 → M>R 3.18.
Yani gerçek hurdle paperdaki Şekil 3'ten **biraz daha yüksek**.

### Bayesian framework [Section 4.7.3, s.25]

Frequentist Bonferroni/Holm/BHY'a alternatif Bayesian multiple testing.
Paper Bayesian methodology'i Appendix B'de tartışıyor ama hesap
karmaşıklığı + missing data sorunu nedeniyle **frequentist'i tercih
ediyor** [s.25].

> 📝 Wiki için: Bayesian multiple testing Faz 2'de Avramov-Cheng-Metzker
> 2023 (Tier 2 #43) "ML vs Economic Restrictions" ingest edildiğinde
> tekrar ele alınabilir.

### Correlation among test statistics [Section 5, s.26-]

Paperin Section 5'i correlated tests için **structural model** önerir:
contemporaneous return correlation `ρ` parametresi ile multiple-testing
düzeltmesi yapılabilir. Bu wiki için ileri-detay; aggregate cutoff
rakamları yeterli.

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Paper top-N selection önermiyor; 316 factor'a multiple-testing düzeltmesi ile **filter criterion** sunar. Wiki'nin top-N stratejilerinin (F+V/P, G+NEGPEG) bileşenlerini multiple-testing-corrected sig kanıtla seçmek için **ön koşul**. | N/A → epistemic prerequisite |
| **Annual rebalance** | Paper rebalance frekansı önermiyor; faktör inclusion criterion sunar. Frekansa nötr. Faz 3 yıllık rebalance + binary inclusion karara aynı şekilde uygulanır. | N/A |
| **Large-cap evrene transfer** | Paper universe-spesifik uygulama önermiyor; tüm 316 factor genelde CRSP-default universe (NYSE/AMEX/NASDAQ all-stocks). Wiki'nin large-cap (S&P 500 + NDX) evrenine transferli faktörlerin multiple-testing-corrected sig durumu **paperdan tek-tek çıkmıyor**; aggregate framework uygulanır. | N/A |
| **NDX intangibles / growth firms** | Kapsamda değil. Multiple-testing methodology evren-bağımsız uygulanır. | N/A |

**Strateji tasarımına net implikasyon:**

1. **Wiki'nin t-stat hurdle'ı yükselir.** Geleneksel `|t| > 2.0` yerine
   BHY-corrected `|t| > 3.0` (1% sig) gerekli; M>R hidden tests
   düzeltmesiyle `|t| > 3.18` (5% BHY). Bu, Faz 3 strateji tasarımında
   **baseline factor inclusion** kriteri.

2. **"Üç darbe" çerçevesi tamamlandı:** McLean-Pontiff'in çift darbe
   çerçevesine HLZ statistical bacağı eklenir.
   - **In-sample large-cap sig** ([[piotroski2000_f_score]] [Tablo 4]
     reddi)
   - **Post-pub decay-adjusted spread anlamlı**
     ([[mclean_pontiff_2016_post_publication_decay]] [Tablo 8] limited
     arbitrage reddi)
   - **Multiple-testing-corrected sig** (HLZ reddi)
   Üç hurdle'ın **birinin** reddi → factor strateji baseline'a girmez.
   Detay sentez tablosu: [[concepts/post_publication_decay]] "Üç darbe
   çerçevesi" alt-bölümü.

3. **Faz 3 spread expectation'ları yeniden kalibre.** Decay-adjusted
   spread tablosuna **multiple-testing-adjusted sig durumu** sütunu
   eklenir → [[concepts/post_publication_decay]] tablosu Cycle 12
   ingest sonrası genişletilir.

4. **Wiki'deki SMB exposure'ı sorgulanır.** SMB never-sig under
   multiple-testing → factor-model baseline olarak kullanma kararı
   statistical bias yönünden challenged. FF93 origin paperından beri
   wiki'de SMB neutral; HLZ kanıtı bu pozisyonu pekiştiriyor (Q11
   partial-stronger).

## Bu paper'ın sürprizi

| Hipotez | Beklenti | Paper'da gerçek |
|---|---|---|
| **Geleneksel `\|t\| > 2.0` cutoff'unun yetersizliği** | Yaygın hipotez (multiple-testing eleştirisi) | Doğrulandı; spesifik replacement cutoff sayısal verildi |
| **Bonferroni vs FDR eşitliği** | Bonferroni "doğru cevap" hipotezi | **Bonferroni stringent ama sample size'a duyarlı**; BHY stationary, daha pratik. Modern preference: BHY |
| **Famous factor'lerin durumu** | Hepsinin sig kalması beklenebilir | **HML/MOM her durumda sig; SMB/IVOL never sig**. Klasik 3F modelin SMB bacağı statistical olarak weakest |
| **Hidden tests'in büyüklüğü** | %20-30 missing factor tahmini olabilir | **%71 missing** — paperin tahmininden yüksek; hurdle daha da yüksek |
| **Bayesian alternatif uygulanabilir mi** | Bayesian methodology ideal olabilir | Missing data + hesap karmaşıklığı → frequentist tercih |

**Sürpriz büyüklüğü:** ORTA. Geleneksel cutoff'un yetersizliği yaygın
hipotez ama **rakam büyüklüğü sürprizli**: 1.96 → 3.78 (Bonferroni) +
**SMB never sig** sonucu klasik 3F modelin temel taşlarından birinin
sorgulanması.

**En sürprizli bulgu:** SMB'nin **hiçbir multiple-testing düzeltmesinde**
sig olmaması — wiki [[famafrench1993_three_factor]] paper'ından beri
SMB için "marjinal sig" not'u taşıyor; HLZ bu marjinal'i
**multi-testing'le explicit ortadan kaldırıyor**.

## Limitler ve Caveats

- **Sample sonu 2012-2014:** Modern post-2012 anomaly explosion (FAANG
  era, ML factor mining, COVID macro shocks) paperin kapsamı dışı.
  Update için Hou-Xue-Zhang 2020 (Tier 1 #18) + Jensen-Kelly-Pedersen
  2023 (Tier 2 #44) gerekli → Q30.

- **Frequentist framework, missing data ile sınırlı:** Paper Bayesian
  alternatif sunmuyor (Appendix B tartışma). ML asset pricing
  literature'ında Bayesian variable selection daha güçlü olabilir;
  Avramov-Cheng-Metzker 2023 (Tier 2 #43) bu boşluğu doldurabilir.

- **Top journal selection bias:** "We narrow our search to generally the
  top journals" [s.4]. Tier 2-3 dergilerdeki anomaly paperları kapsam
  dışı; gerçek factor population yine fazla missing.

- **Working paper subset arbitrary:** "We choose a subset of papers that
  we suspect are in review at top journals" [s.4]. 63 working paper
  seçimi yazarın takdirine bağlı.

- **Theoretical vs empirical hierarchy yok (caveat):** [s.5] "A factor
  derived from a theory should have a lower hurdle than a factor
  discovered from a purely empirical exercise. Nevertheless, whether
  suggested by theory or empirical work, a t-ratio of 2.0 is too low."
  Yani teori-supported factor (CAPM, q-theory) için lenient hurdle
  argümanı kabul ediliyor ama specific cutoff verilmiyor.

- **Unconditional tests focus:** [s.5] "It is possible that a particular
  factor is very important in certain economic environments and not
  important in other environments. The unconditional test might
  conclude the factor is marginal." → Q19 (sektör nötrleştirme), Q22
  (post-2014 conditional regimes) ile bağlantılı.

- **CRSP-default universe:** Wiki amaç evrenleri (S&P 500 + NDX)
  için spesifik multiple-testing korreksiyonu paperdan gelmiyor.
  Aggregate cutoff'lar uygulanır.

- **Correlation modeling Section 5 ileri-detay:** Wiki bu paperdan
  aggregate cutoff'lar için yararlanıyor; correlation-aware structural
  model derinlemesine kullanılmıyor (Faz 2'de FGX 2020 ingest'inde
  tekrar ele alınır).

- **No empirical horse race FF5 vs HXZ4 multiple-testing-aware:**
  Paper individual factor t-statistic'leri raporluyor, factor model
  comparison yapmıyor. Q15, Q24 boşlukları ortogonal kalıyor.

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfalar
- [[concepts/multiple_testing]] — concept; 3 düzeltme prosedürü hierarchy
  + FWER vs FDR farkı + recommended cutoff'lar + wiki ingested factors
  aggregate sig durumu tablosu

### Bu paperın update ettiği mevcut sayfalar
- [[concepts/factor_zoo]] — "Multiple testing problemi" alt-bölüm HLZ
  kanıtla genişletildi; Cochrane #1 + #3 statistical procedural cevap
- [[concepts/post_publication_decay]] — "Çift-bacak epistemik omurga"
  yeni alt-bölüm (behavioral McLean-Pontiff + statistical HLZ); "Üç
  darbe çerçevesi" sentez tablosu
- [[concepts/factor_model]] — multiple-testing-corrected hurdle FF3/
  Carhart/FF5/q5 hiyerarşisine eklendi
- [[famafrench1993_three_factor]] — SMB never-sig under multiple
  testing (Q11 partial-stronger)
- [[famafrench2015_five_factor]] — RMW borderline, CMA sig (Q14, Q15
  partial-stronger)
- [[carhart1997_four_factor]] — UMD sig her cutoff'ta
- [[piotroski2000_f_score]] — F-Score BM-Q5 sig her cutoff'ta; large-cap
  insig (üç darbe)
- [[mohanram2005_g_score]] — G-Score sig 1% her cutoff'ta yaklaşık
- [[sloan1996_accruals_anomaly]] — accruals raw sig her cutoff'ta;
  size-adj insig
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — CMA / asset
  growth sig her cutoff'ta
- [[li_mohanram2019_quality_value]] — composite-score-spesifik
  multiple-testing rakamları paperde yok (Q31 yeni)
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 alpha F-Score
  microcap t=2.67 BHY borderline; Magic Formula q5 alpha negatif insig
- [[mclean_pontiff_2016_post_publication_decay]] — paper içinde HLZ
  reference [s.5-6] McLean-Pontiff'i complementary out-of-sample
  yaklaşım olarak gösteriyor

### İlgili paperlar (ingested)
- [[mclean_pontiff_2016_post_publication_decay]] — paper [s.5-6]
  explicit reference: "Our research is related to a recent paper by
  McLean and Pontiff (2014)... Their paper tests the statistical biases".
  HLZ McLean-Pontiff'in post-pub decay'ini "statistical bias kanıtı"
  olarak yorumluyor. **Wiki için iki paperin epistemik komplementaritesi:**
  HLZ statistical filter + MP behavioral decay = factor zoo'dan true
  signal'i ayıklamanın iki bağımsız mekanizması.
- [[cochrane2011_discount_rates]] — Cochrane #3 sorusu ("kaç factor
  really matter") HLZ-statistical procedural cevap. 316 factor → multiple-
  testing-corrected ~9-30 surviving (paperin specific rakamları
  Tablo 5-6'da; aggregate framework yeterli).
- [[famafrench1993_three_factor]] — paper Şekil 3'te HML mark sig her
  cutoff'ta; SMB never sig
- [[carhart1997_four_factor]] — UMD/MOM mark sig her cutoff'ta

### Cycle 13 ek (HXZ 2020 ingested)
- [[hou_xue_zhang_2020_replicating_anomalies]] — HLZ paper [s.4]
  HXZ'ye explicit referans; HXZ 2020 Cycle 13'te ingest edildi.
  HLZ multiple-testing framework + HXZ empirical replication **iki
  ayrı framework, aynı conclusion**: factor zoo'nun büyük çoğunluğu
  false. **Çift-bacak epistemik omurga → üç-bacak epistemik omurga**.

### Cycle 14 ek (Bailey-LdP DSR ingested)
- [[bailey_lopezdeprado_2014_deflated_sharpe]] — Bailey-LdP paper
  [s.8] **explicit** "DSR uses HL's threshold to deflate a particular
  Sharpe ratio estimate... these two methods are complementary".
  HLZ paper-level multiple testing + DSR strategy-level Sharpe
  inflation aynı epistemik düzlem (selection bias correction);
  farklı uygulama. **Hipotez C teyit:** trial-count HLZ overlap;
  skewness/kurtosis (DSR-2/3) ortogonal Sharpe-spesifik filter;
  sample length (DSR-4) statistical correction. **5. darbe AÇILMADI**
  (Cycle 14 disiplin meta-not testi geçti — [[concepts/post_publication_decay]]).
  DSR Faz 3 backtest spec için methodology infrastructure;
  [[concepts/backtest_overfitting]] ayrı concept.

### Cycle 26 ek (FGX 2020 ingested)
- [[feng_giglio_xiu_2020_factor_zoo]] — **HLZ-FGX methodology
  continuity**: HLZ frequentist Bonferroni/BHY (data-snooping bias)
  + FGX **frequentist DS LASSO** (omitted variable bias) **iki
  ortogonal frequentist concern complementary** (paper [s.23-24]
  explicit kabul). 150 factor library + Fama-MacBeth two-pass +
  cross-validation tuning. Recursive 1994-2016: 17/150 sig (%11).
  FGX HLZ frequentist methodology'sinin **paralel ML extension'ı**
  (Bayesian DEĞİL). D bloğu epistemik omurga statistical bacağı
  **2 paper × iki paralel frequentist methodology** sertleştirme.

### Cycle 27 ek (JKP 2023 ingested)
- [[jensen_kelly_pedersen_2023_replication_crisis]] — **D bloğu
  statistical bacağı 3. paper** (üç paralel methodology aile
  sertleştirme): HLZ frequentist FDR + FGX frequentist DS LASSO +
  **JKP Bayesian Empirical Bayes hierarchical**. JKP HLZ Appendix
  B'de tartışılan **Bayesian framework'ün gerçek implementation'ı**
  (Empirical Bayes hierarchical model + 13 theme cluster + tangency
  portfolio). HLZ MT-adjustment %77.3 (Benjamini-Yekutieli) paralel
  JKP CAPM α %77.3 (paper [Figure 1] aynı rakam) — **HLZ frequentist
  + JKP CAPM α convergence**. Bayesian Empirical Bayes ek +7.6pp
  → %84.9 final US, %84.0 Global. **3. contradictions entry**
  ([[meta/contradictions]] §3): HXZ 2020 ↔ JKP 2023 dramatic empirik
  fark ~50pp gap; methodology disagreement scope-dependent.

### Henüz wiki'de olmayan, doğrudan ilgili Tier-1 ve Tier-2 paperlar
- Avramov-Cheng-Metzker (2023) (Tier 2 #43) — "ML vs Economic
  Restrictions"; HLZ-aware ML asset pricing
- Chen-Zimmermann (2022) (Tier 2 #41) — Open Asset Pricing replikasyon
  database; HLZ kriterleri uygulanmış modern data (Cycle 29 ön koşul)

## Çelişkiler / Tartışmalar

> 📝 **Potansiyel tutarlılık (çelişki DEĞİL):** HLZ %71 missing factor
> tahmini ile [[mclean_pontiff_2016_post_publication_decay]] aggregate
> %35 post-pub decay birbiriyle **uyumlu**. Eğer factor zoo'nun büyük
> kısmı (%71) hidden + missing ise, **published anomaly'lerin büyük
> kısmının "elite" survivors olması** beklenebilir → post-pub decay
> %35 (yani %65 hayatta) hipotezi doğal. İki paper aynı epistemik
> resmin iki tarafını sunuyor: HLZ statistical filter (factor zoo
> hidden tail), MP behavioral filter (published tail decay).

> 📝 **Potansiyel çelişki (placeholder, resmî entry yok):** SMB
> wiki'nin [[famafrench1993_three_factor]] foundational factor model
> bileşeni; HLZ Şekil 3'te SMB **never sig under multiple testing**.
> Wiki SMB için "marjinal sig" not'u taşıyor (Q11); HLZ bu marjinal'i
> daha kati çürütüyor. Bu **çelişki değil çürütme**: FF93 sample-spesifik
> SMB t=1.73 marjinal, HLZ tüm 316 factor sample'da SMB never sig.
> Resolution: SMB factor-model baseline'da kalır (model parsimony +
> incremental information argümanları) ama wiki'nin Faz 3 strateji
> tasarımı için "SMB exposure target" değil.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q1 partial-stronger update]** S&P 500 evreninde value (HML, F-Score)
  post-2000 performansı: HLZ-corrected HML primum FF93 örnekleminde
  Şekil 3 mark "sig her cutoff'ta" → klasik HML sig. Ancak post-2010
  FF15 redundancy + Lev-Srivastava 2020 (Tier 2 #30) post-2010 value
  collapse argümanı + HLZ statistical filter birlikte HML için
  **decay-adjusted + multiple-testing-corrected** bileşik durumu
  multidimensional. Tam Q1 cevabı için Lev-Srivastava 2020 ek ingest.

- **[Q11 partial-stronger update]** SMB post-1991 ve large-cap
  relevance: HLZ Şekil 3 mark **SMB never sig under multiple testing**
  (Bonferroni + Holm + BHY). Wiki'nin SMB exposure'ı için
  factor-model baseline olarak kullanma kararı statistical bias
  yönünden challenged. FF93 sample-spesifik t=1.73 marjinal sig'in
  multiple-testing-corrected tam çürütülmesi. → Q11 fully-answered
  (statistical düzeyde); behavioral decay tarafı Hou-Xue-Zhang 2020
  (Replicating Anomalies) ingest'iyle.

- **[Q15 partial-stronger update]** FF5 vs HXZ4 horse race: HLZ
  Şekil 3 doğrudan FF5/HXZ4 comparison yapmıyor; ama SMB never sig +
  RMW (FF15 t=2.92) borderline + CMA (FF15 t=4.07) sig her cutoff'ta
  bilgisi FF5'in **bir kısmı** multiple-testing'i geçer (CMA, MKT-RF)
  bir kısmı borderline (RMW) bir kısmı çürütülür (SMB). Q15 cevabı
  için HXZ 2015 q-factor origin paperı ingest'i hala gerekli; ama
  multiple-testing düzeyinde FF5 redundancy yarısının çürütülmesi
  netleşti.

- **[Q17 fully-answered (statistical bacak); partial (empirical bacak)]**
  Cochrane #3 ("how many factors really matter") cevabı: HLZ multiple-
  testing-corrected statistical procedural cevap → 316 factor'den
  Bonferroni-corrected ~9 sig (Şekil 3 mark'e göre); BHY-corrected
  ~30 sig (FDR 5%). McLean-Pontiff aggregate %65 hayatta + HLZ
  multiple-testing-corrected ~%10-30 sig birlikte → factor zoo'nun
  **gerçek replicable subset'i K=10-30 arası**. Tam empirical bacak
  için Hou-Xue-Zhang 2020 (Replicating Anomalies, Tier 1 #18)
  individual replication rate raporlar.

- **[Q5 partial-stronger update]** Post-publication decay ve
  multiple-testing düzeltmesi epistemik komplementer: McLean-Pontiff
  behavioral arbitrage decay (%35 sig) + HLZ statistical filter
  (`|t| > 3.0` BHY) wiki epistemik omurganın **çift bacağı**. Bir
  factor "decay-adjusted spread sig + multiple-testing-corrected sig"
  iki kontrolü de geçmeli — Faz 3 baseline kararı.

- **[Yeni Q30]** HLZ sample sonu ~2012, post-2012 yeni faktörlerin
  multiple-testing-corrected hayatta kalma oranı: HLZ 2032 projeksiyon
  Bonferroni 4.00; gerçek post-2014 dönem (FAANG, ML mining, COVID)
  rakamları wiki'de yok. Hou-Xue-Zhang 2020 ~447 anomaly + Jensen-
  Kelly-Pedersen 2023 modern güncelleme + Chen-Zimmermann 2022 Open
  Asset Pricing data portalı + Avramov-Cheng-Metzker 2023 ML restrictions
  ortaklaşa cevap.

- **[Yeni Q31]** Composite-score (F-Score, G-Score, F&V/P, G&V/P)
  multiple-testing-corrected sig durumu: HLZ 316 factor census
  individual factors üzerinde; **composite scores explicit dahil
  değil**. Wiki'deki F-Score (Piotroski t=5.59 BM-Q5), G-Score (sig
  1%), F&V/P (Li-Mohanram +17.94%) gibi composite spread'lerin
  multiple-testing düzeltmesi paperin çerçevesinde **retroactive**
  uygulanmamış. Faz 3 baseline kararı için kritik — composite
  scoring strategies için ayrı multiple-testing test çalışması.

---
type: concept
name: multiple_testing
related_papers: [[harvey_liu_zhu_2016_multiple_testing]], [[mclean_pontiff_2016_post_publication_decay]], [[hou_xue_zhang_2020_replicating_anomalies]], [[bailey_lopezdeprado_2014_deflated_sharpe]], [[cochrane2011_discount_rates]], [[stambaugh_yuan_2017_mispricing_factors]]
---

> 📝 **Cycle 39 ek**: Stambaugh-Yuan FGX 150-factor library içinde DS LASSO sig [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; FGX 2020 (Cycle 26) 150-factor library cross-test Stambaugh-Yuan UMO1+UMO2 mispricing factors validation; Q55+Q7 fully-answered Cycle 26 Stambaugh-Yuan composite scoring methodology cross-evidence; D bloğu epistemik omurga statistical bacağı 3 paper × üç paralel methodology aile (HLZ frequentist Bonferroni/BHY + FGX frequentist DS LASSO + JKP Bayesian Empirical Bayes hierarchical) + Stambaugh-Yuan composite mispricing scoring complementary 4. paralel methodology.

# Multiple Testing — Statistical Filter Mekanizması

> 📝 **Wiki epistemik omurganın statistical bacağı.**
> [[concepts/post_publication_decay]] behavioral decay (sophisticated
> trader arbitrage) bacağını kurarken, bu sayfa **statistical filter**
> bacağını kurar. İki bacak Faz 3 strateji tasarımının **çift-kontrol
> mekanizması**.

## Tanım

Hipotez testinde aynı veri seti üzerinde **birden fazla bağımsız test**
yapıldığında, geleneksel `|t| > 1.96` (5% sig) eşiği false positive
discoveries kontrol etmek için **yetersiz** kalır. 100 test 5% level'da
yapılırsa, beklenen yanlış pozitif sayısı 5; 1000 test → 50 yanlış
pozitif. Asset pricing literatüründe **316+ factor** önerilmiş
[[harvey_liu_zhu_2016_multiple_testing]] [Şekil 2, s.20] → multiple-
testing context'inde geleneksel cutoff yetersiz.

Üç temel düzeltme prosedürü ([[harvey_liu_zhu_2016_multiple_testing]]
[Tablo 3, s.13]):

1. **Bonferroni (single-step, FWER):** En stringent. p-value
   inflation: `p_i × M`.
2. **Holm (sequential step-down, FWER):** Bonferroni'den hafif lenient;
   step-down ordered p-values üzerinde.
3. **BHY / Benjamini-Hochberg-Yekutieli (sequential, FDR):** En lenient.
   FDR control: total discovery sayısı arttıkça scale eder.

## FWER vs FDR

[[harvey_liu_zhu_2016_multiple_testing]] [s.8-12]:

| Error rate | Tanım | Stringency | Asset pricing'de tercih |
|---|---|---|---|
| **FWER** (Family-Wise Error Rate) | P(en az bir false discovery) | Stringent | Az sayıda test, "elite" group |
| **FDR** (False Discovery Rate) | E[proportion of false discoveries / total discoveries] | Lenient (test sayısı büyüdükçe scale eder) | Çok sayıda test (medikal, asset pricing 316 factor) |

**Pratik fark:** 10-test örneğinde [[harvey_liu_zhu_2016_multiple_testing]]
[Tablo 4, s.13] α=5% level'da:
- Single test: 10/10 sig
- Bonferroni: 3/10 sig
- Holm: 4/10 sig
- BHY: 6/10 sig

Asset pricing'de modern preference **BHY-FDR** çünkü factor zoo büyüdükçe
Bonferroni prohibitively stringent oluyor.

## Recommended cutoffs (HLZ 2016)

[[harvey_liu_zhu_2016_multiple_testing]] [Şekil 3, s.22]:

### M = R (all tests observable)

| Method | 2012 | 2032 (linear extrapolation) | Significance |
|---|---|---|---|
| Bonferroni | **3.78** | **4.00** | FWER 5% |
| Holm | ~3.6 | ~3.8 | FWER 5% |
| BHY | **3.39** | **3.40** (stationary) | FDR 1% |
| BHY | **2.78** | **2.81** (stationary) | FDR 5% |

### M > R (hidden tests, %71 missing factor estimate)

[[harvey_liu_zhu_2016_multiple_testing]] [s.24-25]:

| Method | 2012 |
|---|---|
| Bonferroni | 4.01 |
| Holm | 3.96 |
| BHY (1%) | 3.68 |
| BHY (5%) | **3.18** ← paperin önerdiği MUTLAK MINIMUM |

**Wiki için pratik kural:**
- **Baseline `\|t\| > 3.0`** (BHY 1%, M=R) — Faz 3 factor inclusion threshold
- **Agresif sensitivity `\|t\| > 3.78`** (Bonferroni, M=R) veya `|t| > 3.18`
  (BHY 5%, M>R) — NDX evren stress-testi

## False Discovery Rate (FDR) — BHY procedure detayı

> 📝 **Cycle 12 kullanıcı kararı 2:** FDR ayrı concept sayfası
> AÇILMADI; multiple_testing içinde bu alt-bölüm yeterli. Faz 2'de ML
> asset pricing literatüründe FDR çok özel kullanılırsa ayrı sayfa
> açılabilir.

**FDR tanımı:**

```
FDR = E[N_falsediscovery / N_totaldiscovery | N_total > 0]
```

BHY procedure ([[harvey_liu_zhu_2016_multiple_testing]] [s.15-17]):

1. Ordered p-values: `p_(1) ≤ p_(2) ≤ ... ≤ p_(M)`
2. Reject `H_(k)` if `p_(k) ≤ (k / [M × c(M)]) × α_d`
3. `c(M) = Σ(1/j)` for `j=1..M` — arbitrary dependence altında valid

**Pratik avantajlar:**
- **Stationary cutoff** test sayısı büyüdükçe (Bonferroni'nin aksine)
- **Test sayısına scale ediyor** — modern factor zoo (316+) için
  pratik
- **Arbitrary correlation** altında valid (BHY-Yekutieli 2001
  generalization)

**Pratik dezavantaj:** Bonferroni'den lenient → FWER vermiyor; bazı
false discoveries kabul ediliyor. Asset pricing context'inde tipik
trade-off: factor zoo çok büyük, Bonferroni hiçbir factor'u
geçirmiyor olabilir → BHY pragmatic.

## Aggregate tablo — Wiki'de ingested factor/paperların durumu

> 📝 **Cycle 12 kullanıcı kararı 3:** Bu aggregate tablo bu sayfada
> tutulur, factor sayfalarında 1-2 cümle status notu + cross-link
> yeterli. Factor sayfalarına HLZ kolonu eklenmedi (tablo proliferation
> kontrol).

**Methodoloji:** Reported in-sample t-statistic'leri vs HLZ-corrected
cutoffs (M=R, 2012):
- `|t| > 1.96` (klasik %5)
- `|t| > 3.0` (BHY 1% wiki baseline)
- `|t| > 3.78` (Bonferroni wiki agresif)

| Factor / Test | Reported \|t\| | Sample | Klasik (1.96) | BHY (3.0) | Bonferroni (3.78) |
|---|---|---|---|---|---|
| **MKT-RF** [[famafrench1993_three_factor]] | varies (~3.0 typical) | 1963-91 | sig | borderline | borderline |
| **SMB** [[famafrench1993_three_factor]] | 1.73 | 1963-91 | borderline | **insig** | **insig** |
| **HML** [[famafrench1993_three_factor]] | 2.91 | 1963-91 | sig | borderline | **insig** |
| **HML** [[famafrench2015_five_factor]] | 3.20 (1963-2013) | 1963-2013 | sig | sig | borderline |
| **HML 5F altında** [[famafrench2015_five_factor]] | a≈0 (redundant) | 1963-2013 | redundant | redundant | redundant |
| **RMW** [[famafrench2015_five_factor]] | 2.92 (2x3) / 4.09 (joint) | 1963-2013 | sig | borderline / sig | **insig** / sig |
| **CMA** [[famafrench2015_five_factor]] | 4.07 (2x3) / 2.71 (joint) | 1963-2013 | sig | sig / borderline | sig / **insig** |
| **UMD/MOM** [[carhart1997_four_factor]] | 4.46 | 1963-93 | sig | sig | sig |
| **F-Score (BM-Q5)** [[piotroski2000_f_score]] | 5.59 | 1976-96 | sig | sig | sig |
| **F-Score (large-cap)** [[piotroski2000_f_score]] | **1.88** | 1976-96 | borderline | **insig** | **insig** |
| **F-Score continuous all-firms** [[li_mohanram2019_quality_value]] | sig 1% (~5+) | 1973-2012 | sig | sig (yaklaşık) | sig (yaklaşık) |
| **F-Score large-cap standalone** [[li_mohanram2019_quality_value]] | sig (~3+) | 1973-2012 | sig | borderline | borderline |
| **F & V/P combined large-cap** [[li_mohanram2019_quality_value]] | sig 1% | 1973-2012 | sig | sig (yaklaşık) | sig (yaklaşık) |
| **G-Score (low-BM)** [[mohanram2005_g_score]] | sig 1% | 1979-99 | sig | sig (yaklaşık) | borderline |
| **G-Score (large-cap)** [[mohanram2005_g_score]] | sig 1% | 1979-99 | sig | sig (yaklaşık) | borderline |
| **G-Score (NASDAQ)** [[mohanram2005_g_score]] | sig 1% (highest) | 1979-99 | sig | sig | sig (yaklaşık) |
| **G-Score continuous all-firms** [[li_mohanram2019_quality_value]] | sig 1% | 1973-2012 | sig | sig (yaklaşık) | borderline |
| **G & V/P combined** [[li_mohanram2019_quality_value]] | sig 1% | 1973-2012 | sig | sig | sig (yaklaşık) |
| **Sloan accruals raw** [[sloan1996_accruals_anomaly]] | 4.71 | 1962-91 | sig | sig | sig |
| **Sloan accruals size-adj** [[sloan1996_accruals_anomaly]] | **1.64** | 1962-91 | **insig** | **insig** | **insig** |
| **CGS asset growth** [[cooper_gulen_ion2018_asset_growth_factor_models]] | sig (1968-2016 alpha analizi) | 1968-2016 | sig | sig | sig (yaklaşık) |
| **F-Score q5 alpha microcap** [[hou_mo_xue_zhang_2020_security_analysis]] | 2.67 | 1972-2018 | sig | borderline | **insig** |
| **F-Score q5 alpha small/big** [[hou_mo_xue_zhang_2020_security_analysis]] | 0.81 / 0.15 | 1972-2018 | **insig** | **insig** | **insig** |
| **Magic Formula q5 alpha** [[hou_mo_xue_zhang_2020_security_analysis]] | -0.76 | 1967-2018 | **insig** | **insig** | **insig** |
| **Buffett's q5 alpha** [[hou_mo_xue_zhang_2020_security_analysis]] | 2.69 | 1965-2018 | sig | borderline | **insig** |
| **QMJ q5 alpha** [[hou_mo_xue_zhang_2020_security_analysis]] | 0.42 | 1957-2016 | **insig** | **insig** | **insig** |
| **QMJ 4-factor alpha (Asness original, US long)** [[asness_frazzini_pedersen_2019_qmj]] | **11.20** | 1956-2012 | sig | sig | sig (~9 sigma) |
| **QMJ 4-factor alpha (global broad)** [[asness_frazzini_pedersen_2019_qmj]] | sig 1% | 1986-2012 | sig | sig | sig |
| **QMJ Profitability dimension** [[asness_frazzini_pedersen_2019_qmj]] | sig 1% (US + global) | 1956-2012 / 1986-2012 | sig | sig | sig (yaklaşık) |
| **QMJ Growth dimension** [[asness_frazzini_pedersen_2019_qmj]] | sig 1% (US) | 1956-2012 | sig | sig | sig (yaklaşık) |
| **QMJ Safety dimension** [[asness_frazzini_pedersen_2019_qmj]] | sig 1% (US) | 1956-2012 | sig | sig | sig (yaklaşık) |
| **QMJ Payout dimension** [[asness_frazzini_pedersen_2019_qmj]] | sig 1% (US) | 1956-2012 | sig | sig | sig (yaklaşık) |

> 📝 **Tablo nasıl okunmalı:**
> - **"sig" / "insig" / "borderline":** Klasik p-value değerleri için
>   geleneksel etiketler. "yaklaşık" ifadesi paperin t-statistic
>   tam vermediği yerlerde "sig 1%" ifadesinden çıkarsama (yaklaşık
>   `|t| > 2.6` minimum, ama paperin spesifik rakamı yok).
> - **HLZ Şekil 3 mark'leri** explicit olarak HML / MOM "sig her cutoff",
>   SMB "never sig" diyor; bu satırlar paperin direkt kanıtı.
> - **Composite scores (F-Score, G-Score, combined)** HLZ 316 factor
>   sample içinde **explicit yok**; aggregate cutoff'lar t-statistic
>   reported değerlerine retroactive uygulandı (Q31 yeni soru).

### Tablo özet bulgular

**Klasik `|t| > 1.96` cutoff'unu geçen 21 satır içinde:**

- **Her cutoff'ta sig (Klasik + BHY 3.0 + Bonferroni 3.78):**
  UMD/MOM, F-Score (BM-Q5 origin), Sloan accruals raw, G & V/P combined,
  HML (FF15 1963-2013 borderline Bonferroni), CMA (2x3), G-Score
  (NASDAQ)
- **BHY 3.0 sig, Bonferroni 3.78 borderline/insig:**
  HML (FF93 origin t=2.91), RMW (joint 4.09), G-Score (low-BM, large-cap,
  continuous), F-Score continuous all-firms, F & V/P combined,
  G & V/P (yaklaşık), F-Score q5 microcap (t=2.67 BHY borderline)
- **Klasik sig ama BHY 3.0 ve Bonferroni 3.78 insig/borderline:**
  HML (FF93 origin Bonferroni), F-Score (large-cap **t=1.88**),
  Sloan accruals **size-adj** (t=1.64), F-Score q5 microcap
  (Bonferroni), Buffett q5 alpha (Bonferroni)
- **Tüm cutoff'larda insig:**
  **SMB (FF93 t=1.73)** ⚠️, Magic Formula q5 alpha, QMJ q5 alpha,
  F-Score q5 small/big

### Wiki için kritik bulgular

1. **SMB never sig under multiple testing.** Wiki'nin
   [[famafrench1993_three_factor]] foundational factor model bileşeni;
   factor model baseline'da bırakılır (model parsimony argümanı) ama
   strateji tasarımında "SMB exposure target" olarak kullanılmaz.

2. **F-Score large-cap çift insig.** Piotroski Tablo 4 in-sample t=1.88
   (klasik borderline) + HLZ multiple-testing'le **kesin insig**.
   "Üç darbe" çerçevesinin **iki bacağı kesinlikli**: in-sample
   large-cap reddi + multiple-testing reddi. Üçüncü bacak
   (post-pub decay) [[mclean_pontiff_2016_post_publication_decay]]
   [Tablo 8] limited arbitrage ile pekişiyor.

3. **Sloan accruals size-adj (t=1.64) tüm hurdle'larda insig.**
   Wiki'nin "anomaly size-loaded" yorumu HLZ-statistical düzeyde
   pekişiyor.

4. **HMXZ q5 alpha'lar büyük ölçüde insig.** Magic Formula q5 (t=-0.76),
   QMJ q5 (t=0.42), F-Score q5 small/big (t=0.81/0.15) hepsi tüm
   cutoff'larda insig. Wiki'nin "fundamental scoring strategies q5
   ile span" yorumu HLZ-statistical düzeyde de doğrulanıyor.

5. **Composite scores (F-Score BM-Q5, F & V/P combined, G & V/P
   combined) klasik cutoff'lar geçer.** Ama paperin 316 factor
   sample'ına explicit dahil değil; retroactive cutoff uygulaması.
   Q31 ek araştırma alanı.

## Sharpe-spesifik düzeltmeler — DSR (Cycle 14 ek)

[[bailey_lopezdeprado_2014_deflated_sharpe]] Cycle 14'te ingest edildi;
**Sharpe-spesifik selection bias düzeltmesi** Deflated Sharpe Ratio
(DSR) formülü ile [Eq. 2, s.8].

**DSR vs HLZ multiple-testing ilişkisi (Hipotez C teyit edildi):**
- **Trial-count bileşeni (DSR-1)** HLZ multiple-testing ile **kavramsal
  olarak örtüşür** (selection bias under multiple testing); ama farklı
  uygulama düzeyi:
  - **HLZ** = paper-level / factor-level (316 factor'den hangisi sig?)
  - **DSR** = strategy-level (kaç backtest denenmiş, hangisi en yüksek Sharpe?)
- **Skewness (DSR-2) + Kurtosis (DSR-3) ortogonal**: mevcut multiple-testing
  framework return distribution shape adreslemiyor — yeni filter
- **Sample length (DSR-4)** statistical (sample noise) — post-pub decay
  (behavioral) ile farklı mekanizma

**Paper [s.8] explicit complementary:**

> "DSR uses HL's threshold to deflate a particular Sharpe ratio
> estimate (see Eq. (2))... these two methods are complementary,
> and we encourage the reader to compute DSR using both thresholds,
> E[max{SR_n}] as well as HL's."

**Wiki için kritik (Q37 — Cycle 14 yeni tasarım kararı):**
DSR + HLZ birlikte uygulandığında **çift düzeltme** riski; Faz 3
backtest spec'inde tek-düzeltme prensibi belirlenmeli. Detay
[[concepts/backtest_overfitting]].

## Üç-bacak epistemik omurga (Cycle 13 ek)

[[hou_xue_zhang_2020_replicating_anomalies]] Cycle 13'te ingest edildi;
çift-bacak (behavioral + statistical) → **üç-bacak (behavioral +
statistical + replication)** olarak genişledi. HXZ paper [s.4] HLZ'ye
explicit referans:

> "Reevaluating 296 significant anomalies in past published studies,
> Harvey et al. report that 80–158 (27%–53%) are false discoveries."

HLZ multiple-testing framework + HXZ empirical replication **iki ayrı
mekanizma** ama aynı conclusion'a varıyor. Detay
[[concepts/post_publication_decay]] üç-bacak epistemik omurga +
[[concepts/anomaly_replication]] paralel sayfa.

**Üç paper ortogonal:**
- HLZ statistical filter (FDR cutoffs)
- MP behavioral decay (post-pub arbitrage)
- HXZ empirik replication (NYSE-VW methodology)

Wiki için: factor zoo'dan true signal ayıklamanın **üç bağımsız ayağı**;
her birinde geçen factorler Faz 3 strateji baseline'a dahil edilir.

## Çift-bacak epistemik omurga

> 📝 [[concepts/post_publication_decay]] sayfasında detaylı sentez +
> "Üç darbe çerçevesi" tablosu. Bu sayfada özet:

Wiki'nin epistemik omurgası **iki bağımsız multiple-testing
mekanizması** üzerine kurulu:

| Mekanizma | Paper anchor | Çerçeve |
|---|---|---|
| **Statistical FDR filter** | [[harvey_liu_zhu_2016_multiple_testing]] | Geleneksel `\|t\| > 2.0` yetersiz; BHY `\|t\| > 3.0` mutlak minimum (1% FDR) |
| **Behavioral decay (post-pub arbitrage)** | [[mclean_pontiff_2016_post_publication_decay]] | 82 anomaly aggregate %35 post-pub decay (sig 1%); large-cap'te daha agresif |

İki paper birbirini **complementary** doğruluyor:
- HLZ %71 missing factor → factor zoo'nun büyük kısmı **gizli ya da
  yayımlanamamış** = sample selection bias kanıtı
- McLean-Pontiff %35 aggregate decay → published anomaly'lerin çoğu
  **publication sonrası zayıflıyor** = arbitrage activity kanıtı
- HLZ paper [s.5-6] McLean-Pontiff'i explicit referansla "out-of-sample
  approach to statistical bias" olarak gösteriyor

**Wiki'nin yorumu:** Factor zoo'dan true signal'i ayıklamanın iki
bağımsız mekanizması var; **her ikisi de geçen** factorler Faz 3
strateji tasarımı için kullanılabilir.

## Cochrane #1 ve #3 sorularına HLZ-statistical cevap

[[cochrane2011_discount_rates]] [s.13]:

**#1 Subsumption:** Hangi factorlar bağımsız bilgi sağlıyor?
- HLZ-statistical cevap: 316 factor → multiple-testing-corrected
  (BHY-FDR-1%) ~30 factor; (Bonferroni) ~9-10 factor. Yani büyük
  çoğunluk subsumed veya spurious.
- Spesifik subsumption ilişkileri için HXZ 2020 (Replicating Anomalies,
  Tier 1 #18) ve FGX 2020 (Taming the Factor Zoo, Tier 1 #21)
  ek ingest gerekli.

**#3 Parsimony (kaç factor really matter):**
- HLZ-statistical cevap: K=10-30 robust factor (BHY) veya K=5-10
  (Bonferroni). Wiki'nin q5 model + momentum + complementer composite
  scoring stratejileri çerçevesi bu parsimony argümanını destekliyor.
- McLean-Pontiff'in **behavioral decay aggregate %65 hayatta** rakamı
  + HLZ'nin **multiple-testing-corrected ~%10-30 sig** rakamı birlikte
  → factor zoo'nun **gerçek replicable subset'i K=10-30 arası**.

## Strateji tasarımına spesifik implikasyon

Faz 3 strateji tasarımında multiple-testing filter **ön koşul**:

1. **Factor inclusion baseline:** Bir factor'u strateji tasarımına dahil
   etmek için reported `|t|` rakamı **BHY 1% sig** (`|t| > 3.0`)
   geçmeli. Klasik `|t| > 2.0` yeterli değil.

2. **NDX agresif sensitivity:** S&P 500 evren için BHY 1% baseline;
   NDX evren için Bonferroni `|t| > 3.78` (M=R) veya BHY 5% M>R
   `|t| > 3.18` ek stress-testi.

3. **Composite scoring strategies için Q31 araştırma:** F-Score, G-Score,
   F&V/P, G&V/P gibi composite scores HLZ 316 factor sample'ına
   explicit dahil değil; retroactive multiple-testing test çalışması
   Faz 3 baseline kararı için kritik.

4. **Factor model exposure kararları:** SMB never sig under
   multiple-testing → wiki'nin SMB factor exposure'ı strateji tasarımı
   için "target" değil; FF93 risk-adjusted regression baseline'da
   kalır (model parsimony argümanı).

5. **Decay-adjusted spread tablosu + multiple-testing kolonu:**
   [[concepts/post_publication_decay]] decay-adjusted spread tablosuna
   "HLZ multiple-testing-corrected sig durumu" sütunu eklendi
   ("Üç darbe çerçevesi" sentez tablosu).

## İlgili paperlar (ingested)

- [[harvey_liu_zhu_2016_multiple_testing]] — anchor paper; 316 factor
  census + 3 düzeltme prosedürü + recommended cutoff'lar + hidden
  tests adjustment
- [[mclean_pontiff_2016_post_publication_decay]] — çift-bacak
  epistemik omurganın behavioral bacağı; HLZ paper'da explicit
  reference [s.5-6]
- [[cochrane2011_discount_rates]] — factor zoo terimi; Cochrane #1
  + #3 sorularına HLZ procedural cevap
- [[famafrench1993_three_factor]] — SMB never sig + HML borderline
  Bonferroni
- [[famafrench2015_five_factor]] — RMW borderline, CMA sig
- [[carhart1997_four_factor]] — UMD sig her cutoff
- [[piotroski2000_f_score]] — F-Score BM-Q5 sig her cutoff; large-cap
  insig (üç darbe)
- [[mohanram2005_g_score]] — G-Score sig 1% her cutoff yaklaşık
- [[sloan1996_accruals_anomaly]] — accruals raw sig her cutoff;
  size-adj insig
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 alpha'ların
  multiple-testing-corrected durumu
- [[hou_xue_zhang_2020_replicating_anomalies]] — 447 anomaly
  empirik replikasyon paralel mekanizma; üç-bacak omurganın replication
  ayağı; HXZ paper [s.4] HLZ'ye explicit complementary reference
- [[bailey_lopezdeprado_2014_deflated_sharpe]] — DSR Sharpe-spesifik
  selection bias düzeltmesi; paper [s.8] HLZ ile **explicit
  complementary** ("DSR uses HL's threshold to deflate"); strategy-
  level multiple testing (HLZ paper-level)

## İlgili paperlar (henüz ingest edilmedi)
- Feng-Giglio-Xiu (2020) "Taming the Factor Zoo" (Tier 1 #21) —
  yeni factor incremental information; HLZ Bayesian extension
- Jensen-Kelly-Pedersen (2023) (Tier 2 #44) — "Replication Crisis in
  Finance" modern güncelleme; HLZ + MP + HXZ 2020 sentezi
- Avramov-Cheng-Metzker (2023) (Tier 2 #43) — "ML vs Economic
  Restrictions"; HLZ-aware ML asset pricing
- Chen-Zimmermann (2022) (Tier 2 #41) — Open Asset Pricing data
  portalı; HLZ kriterleri uygulanmış modern data
- Bailey-Lopez de Prado (2014) "Deflated Sharpe Ratio" (Tier 1 #19) —
  Sharpe ratio multiple-testing düzeltmesi; HLZ analoğu

## İlgili kavramlar

- [[concepts/post_publication_decay]] — çift-bacak epistemik omurganın
  behavioral bacağı; "Üç darbe çerçevesi" sentez tablosu
- [[concepts/factor_zoo]] — multiple_testing factor zoo'nun statistical
  filtreleme mekanizması; Cochrane #1 + #3 prosedürel cevap
- [[concepts/factor_model]] — factor model hiyerarşisi (FF3/Carhart/
  FF5/q5) multiple-testing-corrected hurdle'la sıralanır
- [[concepts/discount_rates]] — Cochrane çerçevesi içinde HLZ "ne
  kadar discount rate spread'i gerçek?" sorusuna cevap

## Faz 3 backtest implementation

> 📝 **Cycle 21 ek (lint_pass).** Bu kavramın methodology'e geçirilmiş
> hali aşağıda; Faz 3 strategy spec'leri için somut kullanım.

**HLZ `|t| > 3.0` BHY 1% hurdle → [[methodology/backtest_spec]] §4
darbe (3) MT-corrected sig**. Factor-level evaluation (single anomaly
t-stat) için baseline; Bonferroni `|t| > 3.78` agresif alternative.
**Çift düzeltme prensibi → [[methodology/backtest_spec]] §3.3**:
DSR-1 trial-count + HLZ MT-corrected double-counting riskine karşı
tek-düzeltme tercih kuralı (factor-level HLZ vs strategy-level DSR).

## D bloğu statistical bacağı sertleştirme — HLZ + FGX iki paralel methodology (Cycle 26)

> 📝 **Cycle 26 ek (FGX 2020 ingest).** D bloğu epistemik omurga
> statistical bacağı **2 paper** (HLZ + FGX) sertleştirme; iki
> paralel frequentist yaklaşım dokümante.

| Paper | Yıl | Approach | Concern | Tools |
|-------|-----|----------|---------|-------|
| [[harvey_liu_zhu_2016_multiple_testing]] | 2016 | Frequentist multiple testing | **Data-snooping bias** | Bonferroni / Holm / BHY (FDR control); recommended `\|t\| > 3.0` |
| [[feng_giglio_xiu_2020_factor_zoo]] | 2020 | Frequentist ML (DS LASSO) | **Omitted variable bias** | Double-Selection LASSO + Fama-MacBeth two-pass; SDF loading test |
| **[[jensen_kelly_pedersen_2023_replication_crisis]]** | **2023** | **Bayesian hierarchical** | **Replication crisis cevap** (hierarchical dependence) | **Bayesian Empirical Bayes** + 13 theme cluster + tangency portfolio |

**Üç paralel statistical methodology aile** (Cycle 26 + 27):
- HLZ: data-snooping/multiple-testing düzeltmesi (yanlış pozitiflere
  karşı stringent cutoff) — **frequentist FDR**
- FGX: omitted variable bias düzeltmesi (gerçek SDF loading kontroller
  sonrası) — **frequentist ML (DS LASSO)**
- **JKP**: hierarchical dependence + theme cluster Bayesian shrinkage
  (replication crisis cevap; 13 theme cluster taxonomy) —
  **Bayesian Empirical Bayes**

**Complementary methodology**, çelişki değil (paper [s.23-24]
explicit FGX-HLZ; JKP Cycle 27 paralel). Faz 3 backtest spec için
**üç-methodology factor selection**: HLZ frequentist FDR + FGX
frequentist DS LASSO + JKP Bayesian hierarchical multi-theme
([[methodology/backtest_spec]] §3.3 + §4.3 sertleştirme).

**Empirik teyit**:
- HLZ 316 factor census + cutoff `|t| > 3.0` BHY: factor zoo'nun
  büyük çoğunluğu yetersiz
- FGX 150 factor library recursive (1994-2016): **17 factor sig** (%11)
- HXZ 2020 NYSE-VW replication (1967-2014): **46/447 net sig** (%10)
- MP 2016 aggregate decay: %35
- **JKP 2023 Bayesian Empirical Bayes (1926-2020)**: **%84.9 US /
  %84.0 Global** ⭐ DRAMATIC FARKLI (Cycle 27)

**Dört ayrı methodology, dramatik methodology disagreement** (Cycle
27 update): conservative-side (HLZ + FGX + HXZ + MP factor zoo decay
~%85-90) vs anti-conservative-side (JKP %85 replication); methodology
choice'lara aşırı duyarlı (capped VW +8.5pp + 1-month +4.0pp +
Bayesian framework +28pp); **3. contradictions entry** (HXZ ↔ JKP,
[[meta/contradictions]] §3) scope-dependent + methodology
disagreement.

> 📝 **Cycle 29 ek (data_sources.md açıldı) — modern data infrastructure
> üç paralel kaynak**: [[methodology/data_sources]] §1-3 dokümantasyon:
> Chen-Zimmermann 2022 Open Asset Pricing Database (pure replication
> ~100%) + JKP 2023 GlobalFactor code repository GitHub bkelly-lab
> (Bayesian Empirical Bayes %85) + WRDS open-source access (CRSP +
> Compustat raw feed). **D bloğu statistical bacağı 3 paper × üç
> paralel methodology aile** + **modern data infrastructure üç
> paralel kaynak** Faz 3 backtest implementation ortak altyapı.
> **Pure replication** (Chen-Zimmermann ~100%) **vs scientific
> replication** (HXZ %35) **vs Bayesian replication** (JKP %85)
> üç paralel methodology framework — JKP [s.1 fn 1] explicit ayrım.

## Forbidden claims

> ⚠️ Wiki bu sayfada yapmaması gereken claim'ler:
> 1. "X factor'u strateji tasarımına alınamaz" — multiple-testing
>    failure tek başına factor'u dışlamak için yeterli **değil**;
>    teori-supported factor'lar için lenient hurdle (HLZ s.5)
>    + post-pub decay-adjusted sig + in-sample evren-spesifik kanıt
>    bileşik karar verir.
> 2. "BHY her durumda Bonferroni'den iyi" — error rate kontrolü
>    farklı (FDR vs FWER); kullanım context'ine göre seçim.
> 3. "316 factor → 9 sig" — bu rakam paperin Şekil 3 mark'lerinden
>    çıkarılan kaba tahmin; paperin specific rakamı 316 → ~30
>    BHY-FDR-1% sig (paperin extract'te detayı yok, framework
>    kanıtla).

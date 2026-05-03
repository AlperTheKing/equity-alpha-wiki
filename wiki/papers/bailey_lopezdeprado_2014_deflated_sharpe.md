---
type: paper
authors: [Bailey, David H., López de Prado, Marcos]
year: 2014
title: "The Deflated Sharpe Ratio: Correcting for Selection Bias, Backtest Overfitting and Non-Normality"
venue: "Journal of Portfolio Management 40 (5), 94-107 (Fall 2014)"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2460551
local_path: raw/papers/bailey_lopezdeprado_2014_deflated_sharpe.pdf
ingested: 2026-05-01
tags: [DSR, deflated_sharpe_ratio, backtest_overfitting, selection_bias, non_normality, methodology_infrastructure, D_blok_4_finali]
status: ingested
---

# Bailey & López de Prado (2014) — Deflated Sharpe Ratio

> 📝 **Atıf konvansiyonu:** `[s. X]` SSRN PDF (July 31, 2014 versiyonu)
> sayfa numarası. Embedded text extract:
> `raw/papers/bailey_lopezdeprado_2014_deflated_sharpe.txt`. JPM Fall 2014
> final yayın sayfa numaraları farklı, formül numaraları (Eq. 1-2) aynı.

> 📝 **D bloğunun #4 ve finali** — replication / multiple testing /
> decay çatı kategorisi tamamlandı. Cycle 11 MP behavioral decay +
> Cycle 12 HLZ statistical FDR + Cycle 13 HXZ empirik replication +
> **Cycle 14 Bailey-LdP DSR** (backtest overfitting Sharpe-spesifik
> filter) ile wiki epistemik omurgası kuruldu.

> ⚠️ **Çerçeve genişleme disiplini meta-not testi (Cycle 14):**
> Cycle 13'te [[concepts/post_publication_decay]] çerçeve genişleme
> disiplini meta-not'unun **ilk gerçek testi**. Plan aşamasında
> Hipotez C (DSR kısmen örtüşür; trial-count HLZ overlap, skewness/
> kurtosis ortogonal) → **5. darbe açılmadı**. Paper okuma sonrası
> teyit edildi: paper [s.8] **explicit** "DSR uses HL's threshold
> to deflate a particular Sharpe ratio estimate... these two methods
> are complementary." Paper kendi konumunu HLZ'ye **complementary
> Sharpe-spesifik düzeltme** olarak tanımlıyor — wiki'nin Hipotez C
> kararıyla tam uyumlu. Çerçeve dört darbede sabitlendi.

## TL;DR

**Deflated Sharpe Ratio (DSR)** = Probabilistic Sharpe Ratio (PSR)
adjusted for **selection bias under multiple testing + non-Normal
returns**. Standart Sharpe ratio sadece mean + std dev kullanır;
DSR **5 ek değişken** ile deflate eder:

1. **N** = number of independent trials (kaç backtest denenmiş)
2. **V[{SR_n}]** = variance of SR estimates across trials
3. **T** = sample length (gözlem sayısı)
4. **γ_3** = skewness of returns distribution
5. **γ_4** = kurtosis of returns distribution

**Ana formül [Eq. 2, s.8]:**

```
DSR = Z[(SR_observed - SR_threshold) × √(T-1) /
       √(1 - γ_3 × SR + ((γ_4 - 1) / 4) × SR²)]
```

Burada:

```
SR_threshold = √V[{SR_n}] × ((1-γ) × Z⁻¹(1 - 1/N) +
                              γ × Z⁻¹(1 - 1/(N×e)))
```

`γ = 0.5772` (Euler-Mascheroni constant); `Z` = standart normal CDF;
`Z⁻¹` = inverse CDF (quantile).

**Numerical example [s.9]:** SR=2.5 daily 5 yıl (T=1250),
V[{SR}]=0.5, γ_3=-3, γ_4=10, N=100 trial → **DSR=0.9** (90%
confidence; 95% eşiğini GEÇEMİYOR). N=46 olsa DSR=0.9505 (95%
geçer). Eğer Normal returns olsaydı (γ_3=0, γ_4=3) N=88'e kadar
toleranslı olurdu.

> 📝 **DSR'ın ana mesajı [s.4]:** Aynı dönem HLZ 2016 ile uyumlu —
> "most claimed research findings in financial economics are likely
> false" (HLZ 2016, s.5; paper bunu explicit alıntılıyor). Bailey-LdP
> bu mesajı **Sharpe ratio reporting** düzeyinde uygular: "a backtest
> where the researcher has not controlled for the extent of the
> search involved in his or her finding is **worthless**, regardless
> of how excellent the reported performance might be" [s.2].

## Tek Cümle Tezi

Geleneksel Sharpe ratio reporting backtest overfitting + selection
bias + non-Normal returns nedeniyle sistemik olarak inflate olur;
Deflated Sharpe Ratio (DSR) bu üç kaynağı **tek formülde** birleştiren
parametrik düzeltme sağlar — N independent trials, V[{SR}], T,
skewness, kurtosis ile.

## Ortaya Konan Sinyal/Faktör

**Yeni empirik faktör YOK.** Bu paper bir **methodology paper** —
mevcut Sharpe ratio reporting'e statistical filter eklemenin
formülasyonu. Wiki'de bu paperdan yeni `factors/*` sayfası açılmadı.
Yerine **bir concept sayfası açıldı:**

- [[concepts/backtest_overfitting]] — concept; DSR formülü detayı +
  p-hacking literatür hattı + multiple_testing'le kavramsal ilişki +
  Faz 3 backtest spec için anchor referans

> 📝 **Cycle 14 kullanıcı kararı 1-2:** Hipotez C onaylandı (DSR kısmen
> örtüşür); 5. darbe açılmadı; **backtest_overfitting ayrı concept**
> açıldı (multiple_testing alt-pencere değil ayrı epistemik düzlem —
> factor selection vs strategy validation farkı).

## Metodoloji

### DSR'ın temel intuition'u

[Eq. 1, s.7] expected maximum Sharpe ratio after N independent trials
under null hypothesis (SR_true = 0):

```
E[max{SR_n}] ≈ V[{SR_n}] × ((1-γ) × Z⁻¹(1 - 1/N) +
                            γ × Z⁻¹(1 - 1/(N×e)))
```

**Yorumu [s.7-8]:** N büyüdükçe E[max{SR_n}] büyür — tamamen rastgele
data'da bile en iyi seçilen trial'ın expected Sharpe'ı pozitif olur.
Bu **selection bias under multiple testing**'in matematiksel
formalizasyonu.

DSR bu threshold'u kullanarak observed SR'yi deflate eder; null
hypothesis'in (SR=0) hangi olasılıkla reddedilebileceğini hesaplar.

### Probabilistic Sharpe Ratio (PSR) altyapısı

Bailey-Lopez de Prado (2012a) PSR: SR'nin gerçek değerinin verilen
threshold üstünde olma olasılığı. PSR sample length + ilk dört
moment (mean, std, skew, kurt) kullanır.

DSR = **PSR + multiple-testing-aware threshold** = iki düzeltme
kaynağını tek formülde birleştirir.

### HLZ ile complementary konumlandırma [s.8]

Paper kendisi explicit söylüyor:

> "In an excellent recent study, Harvey and Liu [2014], henceforth
> denoted HL, compute the threshold that a new strategy's Sharpe ratio
> must overcome in order to evidence greater performance. HL's solution
> is based on Benjamini and Hochberg's framework. The role of HL's
> threshold is analogous to the role played by our E[max{SR_n}] in
> Eq. (1), which we derived through Extreme Value Theory. **DSR uses
> this threshold to deflate a particular Sharpe ratio estimate** (see
> Eq. (2)). In other words, DSR computes how statistically significant
> a particular SR is, considering the set of trials carried out so far.
> In the current paper we apply DSR to the E[max{SR_n}] threshold,
> but DSR could also be computed on HL's threshold. From that
> perspective, **these two methods are complementary**, and we
> encourage the reader to compute DSR using both thresholds,
> E[max{SR_n}] as well as HL's."

> 📝 **Wiki için kritik:** Bailey-LdP DSR + HLZ multiple-testing
> aynı epistemik düzlemi paylaşır (selection bias correction). DSR
> Sharpe ratio reporting için, HLZ factor selection için. **Çift
> düzeltme riski (Q37):** Aynı strateji tasarımında her iki düzeltme
> birlikte uygulanırsa over-correction olur — Faz 3 backtest spec'i
> tek-düzeltme prensibi belirlemeli.

### Backtest overfitting + memory effects [s.5]

Paper kritik bir bulgu: financial series'lerde **memory effects**
varsa, backtest overfitting "loss maximization"a yol açar. Yani
overfitted strateji sadece "out-of-sample sıfır" değil, **negatif**
performans verir. Memory'siz coin'de backtest overfit out-of-sample
sıfır; memory'li (mean-reverting) financial series'te negatif.

> 📝 Wiki için: bu mekanizma post-publication decay (MP 2016) ile
> **paralel ama farklı**. MP arbitrage activity (post-pub trader
> reaction) ile signal degradation; Bailey-LdP memory effects + overfit
> ile loss maximization. İki paper aynı "out-of-sample yetersizlik"
> sonucuna farklı yollardan varıyor.

### Holdout method'un yetersizliği [s.5-6]

Bailey-LdP explicit: k-fold cross-validation + holdout method
**backtest overfitting'i adresleyemez**. Holdout method tek-trial
gibi davranır; çoklu uygulamada false positive beklenir.

> 📝 **Faz 3 wiki için:** Naïve cross-validation Faz 3 backtest spec'i
> için yetersiz; DSR + walk-forward + monte carlo combination gerekli.
> Bailey vd. (2014) "Probability of Backtest Overfitting" (PBO) paralel
> methodology — Bailey-LdP citation [s.6].

## Empirik Sonuçlar (sayılarla)

### Numerical example [s.9-10] — DSR uygulama örneği

**Strateji setup:**
- Sharpe ratio: SR = 2.5 (annualized, daily 5 yıl)
- Sample length: T = 1250 günlük gözlem
- Trial sayısı: N = 100 independent backtest
- SR variance across trials: V[{SR_n}] = 0.5
- Skewness: γ_3 = -3 (left-skewed, riskli)
- Kurtosis: γ_4 = 10 (fat tails)

**Hesaplama:**
- E[max{SR_n}] ≈ √0.5 × ((1-0.5772) × Z⁻¹(0.99) + 0.5772 × Z⁻¹(1-1/271.83))
- = √0.5 × (0.4228 × 2.326 + 0.5772 × 2.762)
- ≈ 1.81 (annualized) → 0.114 (non-annualized daily)
- DSR = Z[(2.5/√250 - 0.114) × √(1250-1) / √(1-(-3)×(2.5/√250) + ((10-1)/4) × (2.5/√250)²)]
- ≈ Z[1.281] ≈ **0.9** (90% confidence)

**Yorumu:** Strateji 95% threshold'unu geçemiyor — backtest selection
bias + non-Normal returns üzerinden Sharpe inflate olmuş.

**Counter-factual senaryolar [s.10]:**
- N = 46 (daha az trial) → DSR ≈ 0.9505 → 95% geçer
- γ_3 = 0, γ_4 = 3 (Normal returns) → N = 88'e kadar toleranslı
- Yani **non-Normality + multiple testing birlikte** stratejiyi
  reddediyor

### When should we stop testing? [s.10]

Paper "secretary problem" / 1/e-law of optimal choice'tan rule of
thumb sunuyor: **Theory-justifiable strateji konfigürasyonlarının
~%37'sini sample, sonra sequential olarak "best so far" arayışı**.
Fazla trial false positive'i artırır.

> 📝 Wiki için: Faz 3 strateji tasarımı için "kaç parametre konfigürasyonu
> test edilebilir" üst sınırı bu prensiple belirlenir; rastgele
> parameter optimization yerine theory-justifiable variant'lara
> sınırlı arama.

### Min Track Record Length / Min Backtest Length

Paper abstract keywords [s.2]: "Minimum Track Record Length, Minimum
Backtest Length" — Bailey & López de Prado (2012a) PSR paper'ında
detay. Wiki paper sayfasında detay yer almıyor (text extract'te
formül detayı eksik), ama Faz 3 backtest spec için methodology
keyword.

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Methodology paper; Sharpe reporting/inflation correction. Top-N selection için **methodology infrastructure** sağlar; doğrudan factor selection değil. Wiki'nin top-N stratejilerinin (F+V/P, G+NEGPEG, UMD) reported Sharpe ratio'larının DSR-corrected raporlanması Faz 3 ön koşulu | N/A → methodology infrastructure |
| **Annual rebalance** | Sample length DSR-4 bileşeni rebalance frekansını dolaylı etkiler — yıllık rebalans yıllık gözlem sayısı düşürür → DSR daha sıkı (T küçükken DSR aşağı). Wiki'nin yıllık-rebalance amacı için DSR daha **muhafazakâr** taraf | N/A → dolaylı methodology girdisi |
| **Large-cap evrene transfer** | Universe-spesifik kalibrasyon yok; Sharpe-corrected reporting evrene-bağımsız. NYSE-VW (HXZ) methodology + DSR ortogonal — birbirini complementary doğrulayabilir | N/A |
| **NDX intangibles / growth firms** | Kapsamda değil. NDX-spesifik distribution shape (skewness/kurtosis) Faz 3'te DSR-2/3 ile raporlanmalı | N/A → Faz 3 spec girdisi |

**Strateji tasarımına net implikasyon:**

1. **Wiki'nin Sharpe ratio claim'leri DSR-corrected raporlanmalı.**
   Faz 3 backtest spec'inde DSR formülü zorunlu — reported Sharpe
   yerine deflated. Faz 3 strategy candidate evaluation'da DSR > 0.95
   minimum kabul edilebilir baseline.

2. **Multiple trial discipline:** Wiki'nin Faz 3'te test edilebilir
   strategy variant sayısı (N) önceden sınırlanmalı (örn. theory-
   justified 5-10 variant); ondan fazla parameter sweep DSR cezasını
   artırır.

3. **Skewness/kurtosis raporlama:** Wiki'deki ingested faktörlerin
   geri dağılımları (Sloan accruals + R&D-to-market + UMD vb.)
   non-Normal — DSR-2/3 düzeltmesi raporlanmalı. Q36 ortogonal soru.

4. **DSR + HLZ çift düzeltme prensibi:** Paper [s.8] DSR + HLZ
   complementary olarak konumlandırıyor; Faz 3 backtest spec'inde
   tek-düzeltme prensibi belirlenmeli (hangi metodolojinin baseline
   alınacağı). Q37 wiki tasarım kararı.

5. **D bloğu finali — wiki epistemik omurgası tamamlandı.** Faz 1
   (Foundation) ön koşulları: D bloğu 4 paper × 4 mekanizma + B+C
   bloğu factor evidence base; Faz 2 (Synthesis) başlangıcı için
   Tier 1 kalan paperlar değerlendirilir (mini consolidation gerekli).

## Bu paper'ın sürprizi

| Hipotez (plan'da) | Beklenti | Paper'da gerçek |
|---|---|---|
| **DSR ↔ HLZ ilişkisi** | Hipotez C: kısmen örtüşür (trial-count HLZ overlap, skew/kurt ortogonal) | **Doğrulandı + güçlendirildi** — paper [s.8] DSR'ı HLZ'ye **explicit complementary** konumlandırıyor; iki yöntem aynı epistemik düzlemde paralel kullanılabilir |
| **5. darbe açılma testi** | Disiplin meta-not kriterleri 1/3 tam + 1/3 kısmen + 1/3 reddedilir → açılmaz | Paper konumlandırması açılmama kararını destekliyor — DSR Sharpe reporting filter, factor selection filter değil |
| **Backtest overfitting → out-of-sample sıfır** | Yaygın hipotez | **Memory effects altında loss maximization** [s.5] — out-of-sample sıfır değil **negatif** olabilir; mean-reverting series'te overfitted parameters systematik kaybeder |
| **Holdout / cross-validation yeterli mi** | Belirsiz hipotez | **Reddedilir** [s.5-6] — k-fold cross-validation backtest overfitting'i adresleyemez; çoklu uygulamada false positive expected |
| **Optimal trial sayısı** | Belirsiz | **Secretary problem / 1/e-law** [s.10] — theory-justifiable variant'ların ~%37'si sample, sequential "best so far" arayışı |

**Sürpriz büyüklüğü:** ORTA-YÜKSEK. **En sürprizli iki bulgu:**

1. **Memory effects altında backtest overfitting → loss maximization**
   (sıfır değil negatif performance). Wiki için Faz 3 backtest spec'i
   için kritik — naive overfitting "kâr ortadan kalkar" varsayımı
   yanlış; gerçekte zararla sonuçlanabilir.

2. **k-fold cross-validation insuffficient.** Wiki Faz 3 spec'inde
   geleneksel cross-validation yetersiz; DSR + walk-forward + monte
   carlo birleşimi gerekli.

## Limitler ve Caveats

- **N (independent trials) tanımı belirsiz olabilir:** Paper "independent
  trials" diyor; gerçek backtest setup'ında trial'lar genelde korele
  (overlapping parameter spaces). Appendix 3 paperde bu durumu
  adresliyor (text extract'te detay yok). Wiki için: Faz 3 spec'inde
  N tahmini (effective number of independent trials) ek prosedür
  gerektirir.

- **DSR parametrik (Normal-based):** PSR foundation Normal distribution
  + ilk dört moment varsayımıyla. Distribution highly non-Normal ise
  parametrik DSR kestirim hatası artar. Bailey-Lopez de Prado (2014a,
  2013) **non-parametric Probability of Backtest Overfitting (PBO)**
  alternatif; ancak ham veri gerektirir.

- **Wiki uygulanabilirliği sınırlı:** Wiki'deki ingested paperların
  çoğunda reported Sharpe ratio yok (spread + t-stat var). DSR formülü
  uygulanabilmesi için ham return time-series + N + V[{SR}] gerekli;
  bunlar Internet Appendix'lerde olabilir ya da Chen-Zimmermann 2022
  data portalı ile retroactive hesaplanabilir. Q35 ortogonal soru.

- **Sample length adjustment short-sample-spesifik:** T = 1250 (5 yıl
  daily) örneğinde DSR önemli düzeltme; T çok büyükse (örn. T = 12,000
  monthly 50+ yıl) etki azalır. Wiki amaç yıllık-rebalance T küçük
  → DSR muhafazakâr taraf.

- **Memory effects assumption:** "Loss maximization" claim'i
  mean-reverting financial series varsayımına dayanır. Strong-trend
  series'lerde (örn. UMD momentum) memory negatif değil pozitif (auto-
  correlated) olabilir; bu durumda backtest overfit "sıfır
  out-of-sample" classic case'e döner. Paper bu nüansı tartışmıyor.

- **Sample period (paperin kendi sample'ı yok):** Methodology paper —
  paper kendi empirik sample'ı yok; numerical example tek illustrative
  case (SR=2.5 hipotetik). Wiki için kanıt-spesifik kalibrasyon yok.

- **HL referansı 2014 Working Paper'dan:** Paper [s.8] "Harvey and Liu
  [2014]" diyor — bu ya Harvey-Liu 2014 working paper (HLZ 2016'nın
  versiyonu) ya da ayrı Harvey-Liu 2014 paper. Wiki için: HLZ 2016
  ile uyumlu çünkü framework aynı (Bonferroni + FDR threshold).

- **JPM-target audience:** Paper Journal of Portfolio Management,
  practitioner-friendly format. Akademik finance/asset pricing paper
  geleneğinden farklı — formal teorik altyapı (Extreme Value Theory)
  Appendix'lerde, ana metin uygulama odaklı.

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfalar
- [[concepts/backtest_overfitting]] — concept; DSR formülü + p-hacking
  literatür hattı + multiple_testing'le kavramsal ilişki + memory
  effects under overfitting + Faz 3 backtest spec için anchor

### Bu paperın update ettiği mevcut sayfalar
- [[concepts/multiple_testing]] — "Sharpe-spesifik düzeltmeler (DSR)"
  yeni alt-bölüm; DSR-1 trial-count HLZ overlap notu; detay
  backtest_overfitting'e atıf
- [[concepts/post_publication_decay]] — **Çerçeve genişleme disiplini
  meta-not'a Bailey-LdP karar referansı**: "Cycle 14 paper okuma
  sonrası: DSR factor selection değil Sharpe reporting filter; 5.
  darbe açılmadı, çerçeve dört darbede sabitlendi (Hipotez C teyit
  edildi)"
- [[concepts/factor_zoo]] — backtest overfitting + DSR ek statistical
  filter mekanizması cross-reference
- [[concepts/factor_model]] — q-factor model Sharpe ratio'larının
  DSR-corrected raporlanması Faz 3 spec'inde
- [[harvey_liu_zhu_2016_multiple_testing]] — HLZ ↔ DSR complementary
  paralel kanıt (paper [s.8] explicit)
- [[hou_xue_zhang_2020_replicating_anomalies]] — replication crisis
  tartışmasının Sharpe-spesifik ek bacağı
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 alpha Sharpe
  ratio'ların DSR-aware raporlanması; HMXZ Sharpe rakamları paperde
  yok ama implicit
- [[mclean_pontiff_2016_post_publication_decay]] — DSR sample length
  düzeltmesi vs MP behavioral decay paralel ama farklı mekanizma
  (statistical vs behavioral)

### İlgili paperlar (ingested)
- [[harvey_liu_zhu_2016_multiple_testing]] — paper [s.8] **explicit
  complementary**; HLZ Bonferroni-style threshold + DSR Sharpe
  deflation aynı epistemik düzlem (selection bias correction); farklı
  uygulama düzeyi (factor selection vs Sharpe reporting)
- [[hou_xue_zhang_2020_replicating_anomalies]] — replication crisis
  literatür hattının methodology bacağı; Bailey-LdP DSR + HXZ NYSE-VW
  Faz 3 backtest spec için iki ortogonal methodology
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 alpha analizi
  Sharpe ratio reporting metodolojisinin DSR-aware revize gereği
- [[mclean_pontiff_2016_post_publication_decay]] — paper [s.4] HLZ
  2016'ya explicit referans; Bailey-LdP HLZ + MP literature kümesinde
  konumlanır

### Henüz wiki'de olmayan, doğrudan ilgili paperlar
- Bailey, Borwein, López de Prado, Zhu (2014) "Pseudo-Mathematics and
  Financial Charlatanism" — backtest overfitting matematiksel formal
  proof; Bailey-LdP DSR'ın foundation paper'ı
- Bailey & López de Prado (2012a) "The Sharpe Ratio Efficient Frontier"
  — PSR origin paper; DSR'ın altyapısı
- Bailey, López de Prado (2014a) "Probability of Backtest Overfitting"
  (PBO) — non-parametric alternatif; Bailey-LdP DSR'ın paralel
  framework'ü
- Lo (2002) "The Statistics of Sharpe Ratios" — non-Normal Sharpe
  düzeltmesi precedent
- Mertens (2002) — Sharpe ratio asymptotic distribution
- Frazzini-Israel-Moskowitz (2018) "Trading Costs" (Tier 3 #52) —
  trading cost-aware Sharpe reporting
- Chen-Zimmermann (2022) "Open Asset Pricing" (Tier 2 #41) — modern
  data ile DSR retroactive hesaplaması Faz 2'de

## Çelişkiler / Tartışmalar

> 📝 **Çelişki YOK** — Bailey-LdP DSR HLZ multiple-testing + MP
> behavioral decay + HXZ replication ile **complementary**; üç-bacak
> epistemik omurgaya Sharpe-spesifik ek filter olarak eklenir,
> rekabet etmez.

> 📝 **Yorum nüansı:** DSR backtest overfitting filter; HLZ multiple
> testing (paper-level); MP post-pub decay (signal degradation); HXZ
> replication (methodology-robust survival). Dört paper aynı genel
> mesajı (factor zoo'nun çoğu false) **dört farklı epistemik
> uygulama** ile destekliyor. Wiki Faz 1 epistemik omurgası bu dört
> paper × dört mekanizma ile tamamlandı.

> 📝 **Çift düzeltme riski (Q37 wiki tasarım kararı):** DSR-1
> trial-count + HLZ MT-corrected birlikte uygulandığında over-
> correction. Faz 3 backtest spec'inde tek-düzeltme prensibi:
> ya DSR ya HLZ-cutoff (`|t| > 3.0` BHY) — ikisi birlikte değil.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q5 partial-stronger]** Post-publication decay anchor: Bailey-LdP
  DSR sample length düzeltmesi ek statistical bacak; MP behavioral
  decay + HLZ statistical FDR + HXZ empirik replication + DSR
  Sharpe-spesifik filter = **dört-paper epistemik omurga**. Q5'in
  cevabı **dolaylı** olarak DSR ile pekişiyor (Sharpe reporting
  inflation kontrolü).

- **[Q17 partial-stronger]** Cochrane #3 (kaç factor really matter):
  DSR backtest overfitting filter Sharpe ratio'da expected maximum
  formülü kullanır; aynı extreme value theory HLZ Bonferroni
  framework'üne paralel. Cochrane #3 cevabı dört-paper omurganın
  Sharpe-spesifik dolaylı 4. ayağı.

- **[Yeni Q35]** Wiki ingested paperlardan reported Sharpe ratio'lar:
  Çoğu paperda spread + t-stat var, Sharpe explicit verilmemiş.
  Carhart UMD t=4.46 → Sharpe ~ √(t²/T) ≈ 0.7-0.8; FF15 RMW t=2.92
  → Sharpe ~ 0.4-0.5 yaklaşık tahmin. **Ham return time-series
  Internet Appendix bağımlı.** Faz 3 backtest spec için DSR retroactive
  hesaplaması Chen-Zimmermann 2022 + JKP 2023 modern data ingest
  sonrası.

- **[Yeni Q36]** Wiki'deki ingested factor strategy'lerin (F&V/P,
  G&V/P, G&NEGPEG, Sloan F_ACCRUAL, R&D-to-market) **return
  distribution shape'i** (skewness, kurtosis): Faz 3 backtest spec'i
  için DSR-2/3 düzeltmesi ham veri gerektirir. Genel literatür: equity
  long-short hedge return'lerde negative skew + fat tails tipiktir
  (especially momentum crashes Daniel-Moskowitz 2016 referans);
  spesifik wiki factorleri için JKP 2023 + Chen-Zimmermann 2022
  data portalı.

- **[Yeni Q37 — wiki tasarım kararı]** Faz 3 backtest spec'inde DSR-1
  trial-count + HLZ MT-corrected birlikte uygulandığında **çift
  düzeltme oluşur mu, oluşursa hangi tek-düzeltme prensibi seçilir?**
  Adaylar:
  1. **DSR primary, HLZ implicit:** DSR-1 zaten selection bias
     adresliyor; HLZ ek olarak uygulanırsa over-correction
  2. **HLZ primary, DSR Sharpe-only:** Factor selection HLZ ile;
     Sharpe reporting DSR ile (her biri kendi epistemik düzleminde)
  3. **Maximum-conservative birleşim:** Her iki düzeltmeyi de uygula,
     daha düşük olanı baseline kabul et
  Faz 3 backtest spec açıldığında karar.

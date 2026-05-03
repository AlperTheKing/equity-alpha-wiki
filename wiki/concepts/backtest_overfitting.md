---
type: concept
name: backtest_overfitting
related_papers: [[bailey_lopezdeprado_2014_deflated_sharpe]], [[harvey_liu_zhu_2016_multiple_testing]], [[hou_xue_zhang_2020_replicating_anomalies]]
---

# Backtest Overfitting — Strategy-Level Selection Bias + Sharpe Inflation

> 📝 **Wiki epistemik omurgasının dört darbe çerçevesi DIŞINDA bir
> filter.** Cycle 14 kullanıcı kararı 1: DSR Hipotez C (kısmen
> örtüşür); 5. darbe AÇILMADI; çerçeve dört darbede sabitlendi.
> Bu sayfa **factor selection değil strategy validation** filter'ı —
> Faz 3 backtest spec'i için anchor.

> 📝 **Cycle 14 kullanıcı kararı 2-3:** backtest_overfitting ayrı
> concept açıldı (multiple_testing alt-pencere değil); sayfa adı
> `backtest_overfitting` (sharpe_inflation'dan daha kapsamlı —
> p-hacking + DSR + walk-forward'ı toparlar).

## Tanım

Bir investment strategy'nin parametre-konfigürasyonlarını backtest
sample'ında performans maksimizasyonu için optimize etme; bu işlem
**rastgele patternleri systematic signal sanılmasına** yol açar.
[[bailey_lopezdeprado_2014_deflated_sharpe]] [s.4]:

> "When a set of parameters are optimized to maximize the performance
> of a backtest, an investment strategy is likely to be fit to such
> flukes. ... Although the historical performance of an optimized
> backtest may seem promising, the random pattern that fuels it is
> unlikely to repeat itself in the future, hence rendering the
> strategy worthless."

## Selection bias kaynakları

[[bailey_lopezdeprado_2014_deflated_sharpe]] [s.3]:

| Kaynak | Mekanizma |
|---|---|
| **File drawer effect** | Negatif sonuçların raporlanmaması |
| **Publication bias** | Dergi sadece "positive" outcome yayınlar |
| **Survivorship bias** | Hedge fund index'leri only-survivor takipçi |
| **Self-selection bias** | Manager sadece kazanan stratejileri pazarlar |
| **Backfilling** | Strateji geçmişi başarılı olduktan sonra rapor edilir |
| **Backtest overfitting** | Parametreleri backtest'i maksimize edecek şekilde seçme |

Hepsi **partial reporting + multiple testing** kombinasyonu →
Type I error rate (false positive) inflate olur.

## Memory effects altında kritik bulgu

[[bailey_lopezdeprado_2014_deflated_sharpe]] [s.5]: Memory'siz
financial series (ideal coin) backtest overfit out-of-sample
**sıfır** performans. Memory'li (mean-reverting) series'lerde
backtest overfit **loss maximization** — yani out-of-sample
**negatif** performans.

> ⚠️ **Wiki için kritik mesaj:** Naive overfitting "kâr ortadan
> kalkar" varsayımı yanlış. Mean-reverting equity returns'de
> overfitted strateji systematic kayıp yaşayabilir. Faz 3 backtest
> spec'i için holdout / cross-validation **yetersiz**; DSR + walk-
> forward + monte carlo birleşimi gerekli.

## Holdout method ve k-fold cross-validation yetersizliği

[[bailey_lopezdeprado_2014_deflated_sharpe]] [s.5-6]:

> "The holdout method... cannot prevent backtest overfitting:
> Holdout assesses the generality of a model as if a single trial
> had taken place, again ignoring the rise in false positives as
> more trials occur. If we apply the holdout method enough times
> (say 20 times for a 95% confidence level), false positives are
> no longer unlikely: They are expected."

**Wiki Faz 3 spec için:**
- Geleneksel k-fold cross-validation tek başına **YETERSİZ**
- DSR + walk-forward analysis birleşimi gerekli
- Bailey vd. (2013) Probability of Backtest Overfitting (PBO)
  paralel non-parametric metodoloji

## Deflated Sharpe Ratio (DSR) — formal düzeltme

[[bailey_lopezdeprado_2014_deflated_sharpe]] [Eq. 2, s.8]:

```
DSR = Z[(SR - SR_threshold) × √(T-1) /
       √(1 - γ_3 × SR + ((γ_4 - 1) / 4) × SR²)]
```

```
SR_threshold = √V[{SR_n}] × ((1-γ) × Z⁻¹(1 - 1/N) +
                              γ × Z⁻¹(1 - 1/(N×e)))
```

**5 input variable** (mean + std dev'in üzerine):

1. **N** — number of independent trials
2. **V[{SR_n}]** — variance of SR estimates across trials
3. **T** — sample length
4. **γ_3** — skewness of returns distribution
5. **γ_4** — kurtosis of returns distribution

`γ = 0.5772` (Euler-Mascheroni); `Z` = standart normal CDF;
`Z⁻¹` = inverse CDF (quantile).

**Numerical example [s.9]:** SR=2.5 daily 5 yıl, N=100, V=0.5,
γ_3=-3, γ_4=10 → DSR=0.9 (95% threshold geçemiyor).

## Multiple testing ile ilişki — Hipotez C uygulanması

> 📝 **Cycle 14 plan'ında Hipotez C tartışıldı; paper okuma sonrası
> teyit edildi:** [[bailey_lopezdeprado_2014_deflated_sharpe]] [s.8]
> explicit: "DSR uses HL's threshold to deflate a particular Sharpe
> ratio estimate... these two methods are complementary."

| DSR bileşeni | Mevcut 4 darbe ile ilişki |
|---|---|
| **(a) Trial-count (multiple trials selection)** | HLZ multiple testing ile **kavramsal olarak örtüşür** (selection bias under multiple testing); farklı uygulama düzeyi (paper-level factor selection vs strategy-level Sharpe inflation) |
| **(b) Skewness düzeltmesi (DSR-2)** | **TAM ORTOGONAL** — mevcut darbelerin hiçbiri return distribution-shape'i adreslemiyor |
| **(c) Kurtosis düzeltmesi (DSR-3)** | **TAM ORTOGONAL** — fat-tail risk Sharpe-için problem |
| **(d) Sample length (DSR-4)** | Post-publication decay (MP) ile **paralel ama farklı mekanizma** — MP arbitrage activity (behavioral), DSR sample noise (statistical) |

**Sonuç:** DSR HLZ + MP'ye paralel **Sharpe-spesifik methodology
infrastructure**; factor selection filter (dört darbe çerçevesi)
DEĞİL strategy validation filter. Wiki için bu sayfa Faz 3 backtest
spec'inin anchor referansı.

## Çerçeve genişleme disiplini meta-not testi (Cycle 14)

> 📝 **İlk gerçek test geçti.** Cycle 13'te
> [[concepts/post_publication_decay]] sayfasına eklenen meta-not
> kriterleri:

| Kriter | DSR durumu | Geçer mi? |
|---|---|---|
| **(a) Ortogonal mekanizma** | Trial-count HLZ overlap; skew/kurt/sample-length ortogonal | **KISMEN** — 4 bileşenden 3'ü ortogonal |
| **(b) Wiki'de aggregate tablo** | Ham backtest verisi gerekli (mean, std, skew, kurt, T, N trials); wiki'deki paperlar bu veriyi vermez | **HAYIR** — modern data (JKP 2023 + Chen-Zimmermann 2022) ingest sonrası |
| **(c) Faz 3 include/exclude doğrudan girdi** | Sharpe reporting metodolojisi; factor decision değil performance reporting | **DOLAYLI EVET** |

**Skor: 1 dolaylı tam + 1 kısmen + 1 reddedilir = çerçeve sabit.**

**Meta-not'un ilk sınavı:** "Yeniden dur ve değerlendir" disiplini
çalıştı; otomatik genişleme yapılmadı, kriterlerle test edildi,
açılmama kararına gerekçeli ulaşıldı. Bailey-LdP paper [s.8]
"complementary methods" konumlandırması wiki'nin pozisyonuyla
örtüştü → karar paper-evidence ile teyit edildi.

> 📝 **Paper okuma sonrası Hipotez B'ye dönüş açık** (Cycle 7
> "kısmi redundancy" hipotez disiplini gibi). Eğer paper DSR'ı
> explicit factor selection filter olarak konumlandırsaydı,
> Hipotez B (5. darbe açma) opsiyonu açılırdı. Paper bunu
> yapmadığı için disiplin korundu.

## When should we stop testing? — Optimal trial sayısı

[[bailey_lopezdeprado_2014_deflated_sharpe]] [s.10] secretary problem
/ 1/e-law of optimal choice:

- Theory-justifiable strategy konfigürasyonlarının **~%37'sini sample**
- Sequential olarak "best so far" arayışı
- Fazla trial false positive'i artırır

**Wiki için Faz 3 implication:**
- Strategy variant sayısı (N) önceden sınırlanmalı
- Theory-driven variants (örn. F&V/P, G&NEGPEG, UMD, Sloan F_ACCRUAL,
  R&D-to-market, Cash-based Cop) — ~5-10 candidate
- Random parameter sweep yasak (multiple testing penalty agresif)

## Wiki Faz 3 backtest spec için methodology checklist

Bu sayfa **methodology/backtest_spec.md** (henüz açılmamış) için
ön-tasarım anchor referansıdır. Cycle 15+ Faz 1 → Faz 2 geçişi
sırasında bu spec açılır. İçeriği:

1. **DSR formula** — ana Sharpe reporting metodolojisi
2. **Walk-forward analysis** — IS/OOS rolling validation
3. **Bootstrap / Monte Carlo** — non-parametric robustness
4. **NYSE breakpoint + value-weight** [[hou_xue_zhang_2020_replicating_anomalies]]
   methodology (Cycle 13 Q32)
5. **Decay-adjusted spread baseline** [[concepts/post_publication_decay]]
   (Cycle 11+13 sentez)
6. **Multi-testing-aware threshold** [[concepts/multiple_testing]]
   (HLZ Cycle 12)
7. **Replication-aware** [[concepts/anomaly_replication]] (Cycle 13)
8. **Trial sayısı sınırlandırması** — secretary problem 1/e-law
   (theory-driven ~%37 sample)
9. **Çift düzeltme prensibi** (Q37) — DSR primary vs HLZ primary
   karar noktası

## Wiki'deki ingested faktörler için DSR uygulanabilirliği

> ⚠️ **Q35 + Q36 ortogonal sorular:** DSR formülü ham backtest
> verisi gerektirir; wiki'deki paperlar reported t-stat + spread
> veriyor (Sharpe explicit yok). Retroactive DSR hesaplaması ham
> return time-series Internet Appendix bağımlı.

| Wiki paper | Reported Sharpe? | DSR uygulanabilir? |
|---|---|---|
| [[famafrench1993_three_factor]] | t-stat var, Sharpe yaklaşık tahmin | Modern data + Internet Appendix |
| [[carhart1997_four_factor]] UMD | t=4.46; Sharpe ~0.7-0.8 yaklaşık | Yes via FF data library |
| [[famafrench2015_five_factor]] | t-stat'lar var | Yes via FF data library |
| [[piotroski2000_f_score]] | spread + t var; Sharpe yok | Internet Appendix |
| [[mohanram2005_g_score]] | sig 1%; Sharpe yok | Internet Appendix |
| [[sloan1996_accruals_anomaly]] | hedge raw 10.4% var | Internet Appendix |
| [[hou_xue_zhang_2020_replicating_anomalies]] | 447 anomaly t-stat'lar var | Yes — paperin kendisi modern HXZ data ile |
| Composite scores (F&V/P, G&V/P) | Li-Mohanram modern rakamları var | Internet Appendix; Q31 ortogonal |

**Wiki için pratik kural:** Reported Sharpe yoksa, t-stat üzerinden
yaklaşık `Sharpe ≈ √(t² / T)` hesaplanır (parametrik); DSR-1 trial-
count ek olarak HLZ multiple-testing ile paralel uygulanabilir.
**Tam DSR formülü** ham return distribution gerekli — Faz 2'de modern
data ingest sonrası.

## İlgili paperlar (ingested)

- [[bailey_lopezdeprado_2014_deflated_sharpe]] — anchor paper; DSR
  formülü + memory effects + holdout yetersizliği + secretary problem
- [[harvey_liu_zhu_2016_multiple_testing]] — paper [s.8] explicit
  complementary; HLZ Bonferroni-style threshold + DSR Sharpe deflation
  aynı epistemik düzlem (selection bias correction); farklı uygulama
  düzeyi
- [[hou_xue_zhang_2020_replicating_anomalies]] — replication crisis
  literatür hattının methodology bacağı; DSR + HXZ NYSE-VW iki
  ortogonal Faz 3 methodology
- [[mclean_pontiff_2016_post_publication_decay]] — DSR sample length
  düzeltmesi vs MP behavioral decay paralel ama farklı mekanizma
  (statistical vs behavioral)
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 alpha Sharpe
  raporlama DSR-aware revize gereği

## İlgili paperlar (henüz ingest edilmedi)

- Bailey, Borwein, López de Prado, Zhu (2014) "Pseudo-Mathematics and
  Financial Charlatanism" — backtest overfitting matematiksel formal
  proof; Bailey-LdP DSR'ın foundation paper'ı
- Bailey & López de Prado (2012a) "The Sharpe Ratio Efficient Frontier" —
  PSR origin paper; DSR'ın altyapısı
- Bailey, López de Prado (2014a) "Probability of Backtest Overfitting"
  (PBO) — non-parametric alternatif
- Lo (2002) "The Statistics of Sharpe Ratios" — non-Normal Sharpe
  düzeltmesi precedent
- Frazzini-Israel-Moskowitz (2018) "Trading Costs" (Tier 3 #52) —
  trading cost-aware Sharpe reporting
- Chen-Zimmermann (2022) "Open Asset Pricing" (Tier 2 #41) — modern
  data ile DSR retroactive hesaplaması Faz 2'de

## İlgili kavramlar

- [[concepts/multiple_testing]] — Sharpe-spesifik düzeltmeler alt-bölüm;
  HLZ ↔ DSR aynı epistemik düzlem (selection bias correction)
- [[concepts/post_publication_decay]] — çerçeve genişleme disiplini
  meta-not; DSR 5. darbe AÇILMADI kararı
- [[concepts/anomaly_replication]] — replication crisis literatür
  hattı; DSR + HXZ NYSE-VW Faz 3 ortogonal methodology
- [[concepts/factor_zoo]] — backtest overfitting factor zoo statistical
  filter mekanizmalarından biri
- [[concepts/factor_model]] — q-factor model Sharpe ratio'larının
  DSR-corrected raporlanması Faz 3 spec'inde

## Forbidden claims

> ⚠️ Wiki bu sayfada yapmaması gereken claim'ler:
> 1. "DSR backtest overfitting'i tamamen çözer" — DSR parametrik
>    (Normal-based); highly non-Normal distribution'larda kestirim
>    hatası artar; PBO non-parametric tamamlayıcı
> 2. "DSR > 0.95 Faz 3 baseline" — paperin önerdiği threshold; wiki
>    Faz 3 spec'inde proje-spesifik kalibrasyon gerekli
> 3. "DSR HLZ'nin Sharpe versiyonu" — Hipotez A reddedildi; DSR
>    skewness/kurtosis ortogonal mekanizmalar içerir
> 4. "5. darbe açılır" — Cycle 14 disiplin meta-not testi geçti;
>    çerçeve dört darbede sabit; Faz 2'de yeniden değerlendirilebilir

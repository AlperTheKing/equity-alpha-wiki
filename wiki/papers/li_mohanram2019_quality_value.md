---
type: paper
authors: [Li, Kevin, Mohanram, Partha S.]
year: 2019
title: "Fundamental Analysis: Combining the Search for Quality with the Search for Value"
venue: "Contemporary Accounting Research / SSRN 3129156"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3129156
local_path: raw/papers/li_mohanram_2019_quality_value.pdf
ingested: 2026-04-28
tags: [composite_score, quality_value_synthesis, F_Score_replication, G_Score_replication, V_P_ratio, PEG_ratio, projenin_kalbi]
status: ingested
---

# Li & Mohanram (2019) — Combining Quality with Value

> 📝 **Atıf konvansiyonu:** `[Tablo N]` ve `[s. X]`. Embedded text extract:
> `raw/papers/li_mohanram_2019_quality_value.txt`.

> 📝 **B bloğu #3 — F+G sentezi.** [[piotroski2000_f_score]] ve
> [[mohanram2005_g_score]]'u tek sample'da head-to-head test eden + value-based
> stratejilerle (V/P, PEG) çapraz birleştirmesini yapan paper. Wiki'nin
> Cycle 5+6 omurgasının doğal extension'ı.

## TL;DR

4 standalone strateji + 4 combined strateji testi. Sample 1973-2012, 98,766
firm-year (tüm CRSP/COMPUSTAT NYSE/AMEX/NASDAQ). **Standalone hedge returns**
[Tablo 2, s.15-16]: F-Score 7.44%, G-Score 6.06%, V/P 6.55%, NEGPEG 5.68% —
hepsi sig 1%. **Combined hedge returns** (long top-quintile-of-both, short
bottom-quintile-of-both) [Tablo 4, s.17-18]: **F-Score & V/P: 17.94%; G-Score
& V/P: 21.45%; F-Score & NEGPEG: 16.76%; G-Score & NEGPEG: 20.67%** — yani
combined yaklaşım standalone'un yaklaşık 3 katı. Risk-adj 3F alpha
(annualized): F&V/P 17.50%, **G&V/P 20.27%**, F&NEGPEG 15.69%, G&NEGPEG 18.26%
[Tablo 9, s.25]. Mekanik açıklama [Tablo 3, s.16]: quality (F, G) ile value
(V/P, NEGPEG) **negatif korelasyon** taşıyor → "quality is not cheap" → iki
ortogonal sinyal kaynağı kombine edilince incremental information büyük.
**Wiki için kritik methodological revision:** Li-Mohanram F-Score ve G-Score'u
**sürekli (rank-based 0-1)** versiyonlarda yeniden inşa eder, all-firms
universe'da; bu binary 0/1 + universe-conditioned orijinalden farklı (post-
publication decay tartışması ile bağı).

## Tek Cümle Tezi

Quality-driven (F-Score, G-Score) ve value-driven (V/P, PEG) fundamental analiz
yaklaşımları **negatif korelasyon** taşır; ikisinin **kesişimi** (long ⋂ top
quintiles, short ⋂ bottom quintiles) standalone'un ~3x hedge return'ünü ve risk-
adjusted alpha'sını üretir; 1973-2012 ABD all-firms örnekleminde.

## Ortaya Konan Yapılar

### 4 standalone strateji

1. **F-Score** ([[F_Score]]) — Piotroski 9-bileşen, **continuous-rank versiyon**
   [s.12]: 9 değişken cross-sectional rank ile [0,1] aralığına normalize, toplam
   0-9 yerine **0-9 continuous** range (her sinyal contemporaneous all-firms
   distribution'a göre). Original binary'den farklı.
2. **G-Score** ([[G_Score]]) — Mohanram 8-bileşen, **continuous-rank versiyon**
   [s.12]: 8 değişken **48-industry FF1997 classification** içinde rank,
   normalize. Orijinal Mohanram 2-digit SIC'den farklı.
3. **V/P ratio** — Frankel-Lee 1998 residual income valuation model'inden
   intrinsic value V; V/P = V/price. **Cross-sectional forecast** (Hou-van Dijk-
   Zhang 2012 + Li-Mohanram 2014 modeli) ile analyst-forecast'sız tüm evrene
   uygulanabilir [s.12-13].
4. **NEGPEG** — `−1 × (forward P/E ÷ implied earnings growth rate)`; PEG
   ratio'nun negatifi → yüksek NEGPEG = ucuz [s.13]. Cross-sectional forecast
   ile hesaplanır.

### 4 combined strateji [s.13]

`F+V/P, G+V/P, F+NEGPEG, G+NEGPEG`

**İnşa:** Her yıl her strateji ayrı quintile sortu. Combined = long top-quintile
of *both* approaches, short bottom-quintile of *both* approaches. **Kavramsal
formülasyon:** "iki yaklaşım da aynı stoğu yüksek/düşük ranklıyor → mispricing
güveni daha yüksek".

> 📝 V/P entity sayfası **wiki'de açılmadı** (Frankel-Lee 1998 paywall sebebiyle
> ingest edilmeyebilir). V/P'nin de facto wiki entity'si bu sayfa + sonradan
> HXZ Security Analysis (Tier listesinde değil) sayfası olacak. PEG için ayrı
> entity sayfası açılmadı (ham bir oran tek başına entity hakkı yok).

## Empirik Sonuçlar (sayılarla)

### Örneklem [s.14-15]

- Evren: NYSE/AMEX/NASDAQ, share code 10/11, $1+ price filter
- Dönem: **1973-2012** (40 yıl)
- 98,766 firm-year, ~2,469/yıl, 12,102 unique firms
- Returns: 12-month buy-and-hold, **fiscal year-end + 3-ay lag, July 1st rebalance**
  (Piotroski 5-ay, Mohanram 4-ay'dan kısa). Size-adjusted (CRSP size decile).
  Delisting Shumway 1997 yöntemi.

### Standalone hedge returns [Tablo 2, s.15-16]

| Strateji | Q1 mean | Q5 mean | Hedge (Q5−Q1) | Anlam |
|---|---|---|---|---|
| F-Score | -2.14% | +5.30% | **+7.44%** | sig 1% |
| G-Score | -1.76% | +4.31% | **+6.06%** | sig 1% |
| V/P | -1.43% | +5.11% | **+6.55%** | sig 1% |
| NEGPEG | -0.72% | +4.96% | **+5.68%** | sig 1% |

> 📝 Tüm 4 strateji standalone significant. F-Score en yüksek hedge ama V/P bu
> sample'da G-Score'dan daha güçlü.

### Korelasyonlar [Tablo 3 Panel A, s.16]

- **F-Score ↔ G-Score: strong positive** (her ikisi de financial statement-based)
- **V/P ↔ NEGPEG: strong positive** (her ikisi value-based)
- **F-Score ↔ V/P: NEGATİF** | **F-Score ↔ NEGPEG: NEGATİF**
- **G-Score ↔ V/P: NEGATİF** | **G-Score ↔ NEGPEG: NEGATİF**

> 📝 Yazar yorumu [s.16]: "**Quality does not usually come cheap**" — yüksek
> kalite firmalar yüksek fiyatlanmış oluyor; düşük fiyatlı firmalar düşük
> kaliteli oluyor. Bu **iki ortogonal sinyal kaynağı** olduğu için kombine
> getiri kaynağı yaratıyor.

### Combined hedge returns [Tablo 4, s.17-18]

| Combined | Q1∩Q1 mean | Q5∩Q5 mean | Hedge | Standalone'a göre artış |
|---|---|---|---|---|
| **F-Score & V/P** | -6.36% | +11.58% | **+17.94%** | F'den +10.50%, V/P'den +11.39% |
| **F-Score & NEGPEG** | -6.32% | +10.44% | +16.76% | benzer |
| **G-Score & V/P** | — | — | **+21.45%** | G'den +15.39%, V/P'den +14.90% |
| **G-Score & NEGPEG** | — | — | +20.67% | benzer |

> 📝 **G-Score & V/P en güçlü combined: 21.45%** — standalone G-Score'un (6.06%)
> 3.5x'i. Combined'in incremental information value'su belirgin.

### Combined sample-size kontrolü [Tablo 5, s.18-19]

Combined portföylerde long/short n daha küçük (43-85 firma/yıl). Sample-size
artışı standalone'da hedge return'ü artırıyor mu kontrol edildi:
- 25-grup partition (long/short ~3,900 obs/grup): F-Score 11.41%, G-Score 9.48%,
  V/P 10.15%, NEGPEG 10.77% (quintile'dan ~50% artış)
- 50-grup partition: F-Score 11.93%, G-Score 9.33% — slightly daha yüksek
- **Combined yine de yüksek:** F&V/P 17.94% > F-50grup 11.93%; sample-size
  artefaktı değil.

### BM partition [Tablo 6, s.20-21]

| Strateji | Growth (low BM) | Medium | Value (high BM) |
|---|---|---|---|
| F-Score | 8.01% | 7.83% | **9.97%** |
| G-Score | **10.92%** | 6.63% | 4.80% |
| V/P | 4.55% | 3.21% | **7.30%** |
| NEGPEG | 1.99% | 2.31% | **8.55%** |
| F & V/P | 13.97% | 12.87% | **19.42%** |
| F & NEGPEG | 14.00% | 11.31% | **19.90%** |
| G & V/P | **18.57%** | 10.99% | 8.99% |
| G & NEGPEG | **20.07%** | 9.57% | 11.26% |

> 📝 **F-Score value'da en güçlü, G-Score growth'da en güçlü** — orijinal
> tasarım kararı doğrulanır. **Combined'da:** F+V/P value'da en güçlü, G+V/P
> growth'da en güçlü → context-aware seçim. **Medium BM (orta-BM) için en güçlü
> combined: F&V/P 12.87%** — yine da growth/value uçlarındaki kadar yüksek
> değil.

### Size partition [Tablo 7, s.21-22]

| Strateji | Small | Medium | **Large** |
|---|---|---|---|
| F-Score | 10.19% | 8.02% | **4.43%** |
| F&V/P | — | — | **11.92%** (improvement +7.49%) |
| F&NEGPEG | — | — | similar improvement |

> 📝 **Large-cap'te F-Score standalone zayıf (4.43%) ama F&V/P combined large-
> cap'te 11.92%'e çıkıyor.** [[piotroski2000_f_score]] [Tablo 4, s.19]'daki
> orijinal F-Score large-cap-zayıflık (spread 0.152, p=0.224) **partially
> compensated by combined approach**. **Q18 partial cevap.**

### Time-series robustness [Tablo 8, s.24]

| Strateji | Mean annual hedge | Sharpe | Negative years (40 yılda) |
|---|---|---|---|
| F-Score | 7.15% | 1.19 | 5 |
| G-Score | 5.47% | 0.56 | 13 |
| V/P | 7.13% | 0.51 | 14 |
| NEGPEG | 6.21% | 0.58 | 9 |
| **F & V/P** | **16.88%** | **1.22** | 4 |
| **G & NEGPEG** | **18.52%** | **1.16** | 5 |

> 📝 Combined stratejilerin Sharpe ratio'ları standalone'a göre belirgin yüksek
> (özellikle V/P-NEGPEG için 0.51 → 1.22). Negative-year frequency düşüyor →
> risk-tabanlı açıklamadan uzaklaşıyor.

### Risk-adjusted alphas (multi-factor) [Tablo 9, s.25]

3-Factor (FF93) annualized alpha:

| Strateji | Annual alpha |
|---|---|
| F-Score | 7.98% |
| G-Score | 6.42% |
| V/P | 6.42% |
| NEGPEG | 5.25% |
| **F & V/P** | **17.50%** |
| **G & V/P** | **20.27%** |
| F & NEGPEG | 15.69% |
| G & NEGPEG | 18.26% |

4-Factor (Carhart) ve 5-Factor (FF15) alfaları benzer büyüklüklerde — combined
stratejiler risk-faktör kontrolünden sonra da hayatta kalıyor.

### Graham-Dodd benchmark [Tablo 10, s.26-27]

Graham-Dodd 10-criteria screen [Lee 2014 implementation] hedge return = 8.75%
(GDS=9-10 vs GDS=0-1). Combined stratejiler aynı subsample'da: F&V/P 14.32%,
G&V/P 20.42%, F&NEGPEG 16.69%, G&NEGPEG 20.87% — Graham-Dodd'un 2x'inden fazla.

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Quintile-quintile combined intersection (top∩top, bottom∩bottom) — explicit "winner vs loser" formülü; finer partition (25/50 grup) kontrolü da yapılmış [Tablo 5, s.18-19] | ✅ doğrudan fit |
| **Annual rebalance** | July 1st rebalance, 12-aylık holding, fiscal year-end + 3-ay lag [s.14] | ✅ doğrudan fit |
| **Large-cap evrene transfer** | [Tablo 7, s.22] **size partition test edildi.** F-Score standalone large-cap'te zayıf (4.43%) ama **F & V/P combined large-cap'te 11.92%, +7.49% improvement.** Yazar [s.22]: "strong performance of combined strategies in subset of large firms is especially important, as it suggests that such a strategy is likely to be implementable" | ✅ doğrudan fit (combined yaklaşımıyla) |
| **NDX intangibles / growth firms** | NASDAQ partition [Tablo 7]: combined'da hem NYSE/AMEX hem NASDAQ subsample'da significant improvement. Growth (low BM) partition [Tablo 6]: G&NEGPEG growth'da 20.07% — en yüksek. Sample 1973-2012 → post-2000 tech bubble + 2008 kriz dahil; ancak post-2014 FAANG dönemi out-of-sample. R&D capitalization yapılmamış (Mohanram orijinal G-Score formülasyonu kullanılmış) | ✅ explicit fit; ⚠️ post-2014 out-of-sample |

**Strateji tasarımına net implikasyon:**

Bu paper, wiki'nin **B bloğu sentez paperı** — F-Score + G-Score'un standalone
kullanımı yerine value-based skorla (V/P, NEGPEG) **kombine** edilmesinin
büyük artı sağladığı kanıtıdır. **Üç dengeli kayıt:**

1. **Sample 1973-2012 → post-2014 out-of-sample.** FAANG-dominant 2014-2024
   dönemi paperda yok; mega-cap tech etkisi belirsiz. Modern data ile
   replikasyon Faz 3'te gerekli.
2. **Combined yaklaşım large-cap'te güçlü:** F-Score'un standalone large-cap
   zayıflığı (Q18) combined ile büyük ölçüde kompanse → **Q18 partial cevap.**
3. **Methodology revision:** Li-Mohanram F-Score ve G-Score'u **continuous
   rank-based** versiyonlarda all-firms universe'da inşa eder. Orijinal binary
   + universe-conditioned tasarımlardan farklı. Bu **post-publication decay
   tartışmasının** bir parçası — orijinal Piotroski +23% spread'in modern
   replikasyonda 7.44%'e inmesi sample uzatma + methodology revision +
   universe değişiklikleri kombinasyonu.

**Pratik tasarım önerileri (Faz 3):**
- **S&P 500 stratejisi:** F-Score-anchor (value-tilted mixed evren) + V/P (intrinsic
  value) kombinasyonu. F&V/P value subgroup'ta 19.42% kanıtlı en güçlü.
- **Nasdaq 100 stratejisi:** G-Score-anchor (growth) + NEGPEG (PEG-tabanlı value)
  kombinasyonu. G&NEGPEG growth subgroup'ta 20.07% kanıtlı en güçlü.
- **Mixed S&P 500 için F&V/P alternatif:** F-Score'un value-side avantajı + V/P
  intrinsic-value-tabanlı korelasyonu → genel kullanımda en sağlam combined.

## Limitler ve Caveats

- **Sample sonu 2012 → post-2014 out-of-sample:** Modern FAANG dönemi yok.
- **Cross-sectional forecast quality:** V/P ve NEGPEG hesaplaması Hou-van Dijk-
  Zhang 2012 + Li-Mohanram 2014 cross-sectional earnings forecast'ine dayanır;
  bu forecast'ler analyst forecast'lerinden daha **noisy** [s.8]. Forecast
  hatası combined performance'ı zayıflatabilir.
- **Combined stratejiler small portfolio sizes:** ~43-85 firma/yıl → trading
  capacity sınırlı. Yazar [Tablo 5] sample-size effect'i kontrol etmiş ama
  ham implementability sorusu açık.
- **Optimal weighting yok:** Yazar açıkça [s.29]: "we focus on simple
  intersection... no effort to determine optimal weight". Factor analysis
  veya cross-validated weighting daha yüksek getiri verebilir.
- **F-Score & G-Score continuous, all-firms revision:** Orijinal
  [[piotroski2000_f_score]] binary, BM-Q5 only. [[mohanram2005_g_score]] binary,
  BM-Q1 only + 2-digit SIC industry. Li-Mohanram her ikisini continuous, all-firms,
  FF1997 48-industry yapar. **Methodology revision farkları orijinal vs.
  replikasyon spread'in farklılığında ana faktördür** — McLean-Pontiff
  post-publication decay tartışmasının somut örneği.
- **No PEG or V/P entity in wiki:** PEG ham bir oran (entity hakkı yok); V/P
  Frankel-Lee 1998'den (paywall, ingest edilmeyebilir). Bu sayfa ve gelecek
  paper sayfaları V/P'nin de facto wiki açıklaması rolü görür.
- **Mispricing yorumu:** Yazar risk-tabanlı açıklamayı dışlamıyor [s.29] —
  "we cannot rule out the possibility that our results may arise from other
  unobserved risk factors". Wiki bu felsefi seçimde taraf tutmaz.

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfa
- [[comparisons/f_score_vs_g_score]] — F-Score ↔ G-Score head-to-head karşılaştırma
  (bu paper'ın replikasyon kanıtları omurga)

### Bu paperın update ettiği mevcut sayfalar
- [[F_Score]] — Reported Performance + continuous-version note + large-cap
  combined improvement
- [[G_Score]] — Reported Performance + continuous-version note + 48-industry
  revision
- [[winner_loser_identification]] — combined paradigm + orta-BM gap status
  ("azaltıyor ama kapatmıyor")
- [[contextual_fundamental_analysis]] — quality × value cross-product methodology
- [[fundamental_scoring]] — combined skor satırı tabloya

### İlgili paperlar (ingested)
- [[piotroski2000_f_score]] — F-Score origin paper; methodology revision farkı
  ile replikasyon
- [[mohanram2005_g_score]] — G-Score origin paper; aynı yazar (Mohanram), aynı
  research line continuation
- [[famafrench1993_three_factor]], [[carhart1997_four_factor]],
  [[famafrench2015_five_factor]] — risk-adjusted alpha kontrolünde kullanılan 3F/4F/5F
  modelleri
- [[hou_mo_xue_zhang_2020_security_analysis]] — Li-Mohanram'ın F-Score
  ve V/P standalone'larını q5 model lens'inde test eder. **Combined F&V/P,
  G&V/P doğrudan HMXZ kapsamında değil** — Li-Mohanram'ın combined paradigm'i
  HMXZ'de teyit edilmiş değil ama bireysel bileşenlerinin q5 alpha'ları sıfıra
  yakın (V/P tam span; F-Score microcap hariç span) → combined alpha muhtemelen
  küçük (doğrudan kanıt yok)
- [[asness_frazzini_pedersen_2019_qmj]] — **Cycle 19 ek**; Asness QARP
  (Quality at a Reasonable Price) framework Li-Mohanram F&V/P + G&V/P
  combined paradigm'ın **yapısal paralel'i**. QARP = quality × n − P/B;
  n yakın 1 highest alpha (US long sample). Li-Mohanram simple quintile
  intersection vs Asness continuous quality × n − P/B operationalization
  farkı; ama aynı concept (combined approach). Faz 3 strategy spec için
  **anchor framework**: Li-Mohanram F&V/P + G&V/P (binary intersection)
  + Asness QARP (continuous score) iki alternatif operationalization;
  Q21 (combined methodology) + Q50 (QARP NDX kalibrasyonu) paralel.
  QMJ paper Frankel-Lee 1998 + Piotroski 2000 explicit cite [s.7] —
  combined approach literatür hattı kökü ortak.
- [[mclean_pontiff_2016_post_publication_decay]] — wiki'de
  **composite-score-spesifik post-publication decay'in tek somut empirik
  örneği** Li-Mohanram modern replikasyondur. Karşılaştırma: orijinal
  Piotroski (1976-1996, BM-Q5, binary) +23.0% → Li-Mohanram (1973-2012,
  all-firms, continuous) +7.44% = ~3x düşüş; orijinal Mohanram (1979-1999,
  low-BM, binary) +21.2% → Li-Mohanram (1973-2012, all-firms, continuous)
  +6.06% = ~3.5x düşüş. McLean-Pontiff aggregate %35 decay'i + universe
  genişlemesi + binary→continuous + industry classification revision
  bileşik etkisi. Saf decay komponenti ayrıştırılmamış; bu paper
  composite-score evrimini gösteren benchmark.

### Cycle 12 ek (HLZ 2016 ingested)
- [[harvey_liu_zhu_2016_multiple_testing]] — Li-Mohanram composite scores
  (F-Score, G-Score continuous all-firms; F&V/P, G&V/P, F&NEGPEG,
  G&NEGPEG combined) HLZ 316 factor census **explicit dahil değil**;
  individual factor list. **Composite-score-spesifik multiple-testing
  test çalışması paperin çerçevesinde retroactive uygulanmamış** →
  yeni Q31. Reported t-statistic'ler "sig 1%" düzeyinde (yaklaşık
  |t| > 2.6) — BHY 1% (3.0) yaklaşık sig, Bonferroni 3.78 borderline.
  G&V/P combined +21.45% spread Faz 3 baseline'da MT-corrected sig
  yaklaşık.

### Cycle 13 ek (HXZ 2020 ingested)
- [[hou_xue_zhang_2020_replicating_anomalies]] — Li-Mohanram composite
  scores (F&V/P, G&V/P, F&NEGPEG, G&NEGPEG) HXZ 2020 447 individual
  anomaly census'da **explicit dahil değil**. F-Score quarterly (Fq)
  individual factor olarak replicate edilir [s.27] ama composite
  cross-product (quality × value) form'u test edilmemiş. **Q31 ortogonal
  kalır** (composite-score-spesifik replication); Faz 3 baseline kararı
  için JKP 2023 (Tier 2 #44) modern güncelleme + Chen-Zimmermann 2022
  (Tier 2 #41) data portalı ek ingest gerekli. Üç darbe çerçevesinde
  Li-Mohanram composite'leri **3/3 sig** ama 4. darbe (replication)
  ortogonal. Detay [[concepts/anomaly_replication]] aggregate tablosu;
  [[concepts/post_publication_decay]] dört darbe çerçevesi tablosu
  (3/4 q-factor span ile risk premium proxy).

### Henüz wiki'de olmayan, doğrudan ilgili paperlar
- Frankel-Lee (1998) — V/P origin paper, **paywall sebebiyle ingest
  edilmeyebilir** (Tier 1 #8 ama paywall risk)
- Hou-van Dijk-Zhang (2012), Li-Mohanram (2014) — cross-sectional earnings
  forecast modelleri (bu paperın V/P ve NEGPEG hesaplamasının altyapısı)
- Piotroski-So (2012) — F-Score out-of-sample 1997-2014 (Tier listesinde değil
  ama önerilen Tier 2)
- Asness-Frazzini-Pedersen (2019) QMJ — quality-cheap kombinasyonunun paralel
  literatürü (Tier 1 #6)
- Lee (2014) — Graham-Dodd implementation

## Çelişkiler / Tartışmalar

> 📝 Bu paper kendi başına yeni çelişki yaratmaz; **methodology revision
> farkları** oluşturduğu rakam farklılığı [[comparisons/f_score_vs_g_score]]
> sayfasında "replikasyon farkı" olarak işaretlenir, çelişki olarak değil
> ([[meta/contradictions]]'a giriş yok). McLean-Pontiff post-publication
> decay tartışmasının somut bir örneği olur.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q3 partial-stronger update]** F-Score / G-Score Nasdaq 100'de test edildi mi?
  → Li-Mohanram 1973-2012 sample post-2000 tech bubble dönemini kapsıyor;
  NASDAQ partition'da combined improvement significant [Tablo 7]. **NDX 100
  endeks-üyesi spesifik test yine yok**, ama out-of-sample kapsam genişledi.
- **[Q18 partial-stronger update]** F-Score large-cap'te zayıf, hangi yapısal
  değişiklik? → **Combined yaklaşım** F-Score large-cap zayıflığını V/P ile
  kompanse: F&V/P large-cap = 11.92% (vs F-Score-only 4.43%). Q18 cevabı:
  "kombinasyon" structural change'lerden biri.
- **[Yeni Q21]** Combined skor methodology belirsizliği: Li-Mohanram simple
  quintile-intersection kullanıyor [s.13]; **factor analysis weighting,
  continuous-rank product, ML-based weighting** alternatifleri test edilmedi.
  Yazar açıkça not [s.29]: "no effort to determine optimal weight".
  Faz 3 strateji tasarımının bir karar noktası.
- **[Yeni Q22]** Post-2014 (özellikle 2015-2024 mega-cap dominant FAANG
  dönemi) F+G+V/P+PEG combined skor replikasyonu. Modern data ile out-of-
  sample test gerekli.

- **[Q5 fully-answered (composite-score için)]** Post-publication decay
  composite-score-spesifik somut empirik kanıtı bu paper sağlıyor:
  F-Score 3x düşüş, G-Score 3.5x düşüş (orijinal vs modern). McLean-Pontiff
  2016 ([[mclean_pontiff_2016_post_publication_decay]]) aggregate %35 decay
  baseline'ı bu spesifik düşüşlerin bir bileşeni; karışık etkenler (sample
  uzatma + universe genişlemesi + binary→continuous + industry classification
  revision) saf decay'i ayrıştırmaz. Wiki için:
  [[post_publication_decay]] decay-adjusted spread tablosu Li-Mohanram
  modern rakamlarını "modern out-of-sample" sütununda gösterir.

- **[Q21 + Q22 partial-stronger update (Cycle 17)]** Combined intangibles-
  aware revize gereği: [[lev_srivastava_2020_value_failure]] vanilla HML
  decay'in büyük kısmı intangibles bias'a bağlı (39 yılın 34'ünde
  adjusted methodology conventional'ı geçer); F&V/P + G&V/P combined
  yaklaşımları **V/P denominator raporlu price'a karşı tek başına yeterli
  değil** — V/P numerator (intrinsic value) reported BV / earnings'a
  dayanıyor; intangibles-aware adjusted metrics ile V/P revize edilmeli.
  Lev-Srivastava methodology Li-Mohanram strategy framework'ünde
  uygulanmalı. **Q21 (combined methodology) + Q22 (post-2014 modern
  replikasyon) partial-stronger ileri**: tam cevap modern data
  (Chen-Zimmermann 2022 + JKP 2023) + adjusted V/P methodology paper
  bekliyor.

- **[Q23 partial-stronger ileri (Cycle 17)]** NDX intangibles q-factor
  span: F bloğu 3 ayak tamamlandı (Lev-Sougiannis + Peters-Taylor +
  Lev-Srivastava); Li-Mohanram NASDAQ partition combined results
  (G&V/P spread 21.45%) intangibles-aware versiyonla daha güçlü
  beklenir; **NDX strategy spec için methodology infrastructure hazır**.

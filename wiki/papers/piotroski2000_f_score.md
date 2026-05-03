---
type: paper
authors: [Piotroski, Joseph D.]
year: 2000
title: "Value Investing: The Use of Historical Financial Statement Information to Separate Winners from Losers"
venue: "Journal of Accounting Research 38 Supplement (2000), 1-41 (also U Chicago GSB Selected Paper 84, 2002)"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=249455
local_path: raw/papers/piotroski_2000_f_score.pdf
ingested: 2026-04-27
tags: [composite_score, fundamental_screen, value, earnings_quality, accrual, profitability, leverage, projenin_kalbi]
status: ingested
cycle_39_note: "Composite scoring paradigm literature continuity 4-paper × 17-yıl [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓: F-Score (BU PAPER; binary 9-component high-BM origin) → G-Score (Mohanram 2005) → Stambaugh-Yuan MGMT/PERF (continuous composite 11-anomaly 2-cluster Cycle 39) → JKP 13 theme cluster (Cycle 27); F-Score Stambaugh-Yuan composite mispricing scoring origin paterni paralel"
---

# Piotroski (2000) — F-Score: 9-Bileşenli Fundamental Skor

> 📝 **Atıf konvansiyonu:** `[Tablo N]` numaralı tablolar; `[s. X]` paper iç sayfa
> numarası (Selected Paper 84, 2002 sayfalandırması). Embedded text extract'ten
> okundu (`raw/papers/piotroski_2000_f_score.txt`).

> 📝 **Projenin kalbi paperı:** Bu wiki'nin amacı (S&P 500 / Nasdaq 100'de yıllık
> fundamental stock selection) için **prototypal** bir sistem. Annual rebalance,
> tablo verisi tabanlı, ad-hoc skor, large-cap evrene transfer ihtiyacı: tüm
> pozisyon kararlarımız için referans.

## TL;DR

9 bileşenli, her biri 0/1 (binary) olan **F-Score** komposit fundamental skor.
9 sinyal üç kategoride: **profitability** (ROA, ΔROA, CFO, accrual), **leverage/
liquidity** (Δleverage, Δcurrent ratio, equity issuance), **operating efficiency**
(Δgross margin, Δasset turnover). F-Score = sum, 0-9 aralığı [s.7-9]. Strateji
**sadece BM-quintile-5 (high-value)** evrende test edilir, 1976-1996, 14,043
firm-year (COMPUSTAT). Headline: **High F (8-9) − Low F (0-1) = +0.230 yıllık
market-adjusted spread (t=5.59)** [Tablo 3, s.16]; long-only High F mean
market-adj return = **+0.134** (vs all high BM = 0.059) [Tablo 3, s.16].
**Wiki için kritik nüans:** Tablo 4 [s.19] büyüklük ayrımı — sonuç **Small**'da
güçlü (High-Low = 0.270, t=4.71), **Medium**'da orta (0.173, t=2.87), **Large'da
istatistiksel olarak anlamlı değil (0.152, p=0.224)**. Bu, S&P 500 / Nasdaq 100
büyük-cap evrene **doğrudan transferin riskli olduğunun** doğrudan kanıtı.

## Tek Cümle Tezi

Yüksek BM (value) hisselerin geniş portföyü içinde, geçmiş finansal tabloya dayalı
9-binary-sinyal toplamı (F-Score) "güçlü" firmaları ayırarak ortalamayı yıllık
~7.5% yukarı kaydırır ve uzun-kısa stratejisi yıllık ~23% getirir; 1976-1996 ABD
örnekleminde.

## F-Score: 9 Bileşen [s.7-9]

### Profitability (4 sinyal)

| Sinyal | Tanım | "1" koşulu |
|---|---|---|
| `F_ROA` | Net income / beginning total assets | ROA > 0 |
| `F_CFO` | Cash flow from operations / beginning total assets | CFO > 0 |
| `F_ΔROA` | ROA(t) − ROA(t-1) | ΔROA > 0 |
| `F_ACCRUAL` | (CFO − ROA) işareti | CFO > ROA (yani accrual ≤ 0; earnings cash-supported) [s.7] |

> 📝 `F_ACCRUAL` Sloan (1996) accruals anomalisini bireysel-firma seviyesine
> taşır: pozitif accrual'ler (NI > CFO) gelecek getiri için kötü işaret.

### Leverage / Liquidity / Source of Funds (3 sinyal) [s.7-8]

| Sinyal | Tanım | "1" koşulu |
|---|---|---|
| `F_ΔLEVER` | Long-term debt / average total assets oranındaki değişim | leverage **azalmış** (negatif Δ) |
| `F_ΔLIQUID` | Current ratio (current assets / current liab) değişimi | liquidity **artmış** |
| `F_EQ_OFFER` | Önceki yıl equity issuance | firma equity ihraç **etmemiş** |

> 📝 İşaretler high-BM (financially distressed) firmalar için yorumlanmış [s.7].
> Sağlıklı firmalar için işaretler farklı yorumlanabilir — **scope uyarısı**.

### Operating Efficiency (2 sinyal) [s.8-9]

| Sinyal | Tanım | "1" koşulu |
|---|---|---|
| `F_ΔMARGIN` | Gross margin (= (sales − COGS) / sales) değişimi | gross margin **artmış** |
| `F_ΔTURN` | Asset turnover (= sales / avg total assets) değişimi | asset turnover **artmış** |

### Toplam

`F_SCORE = F_ROA + F_CFO + F_ΔROA + F_ACCRUAL + F_ΔMARGIN + F_ΔTURN + F_ΔLEVER + F_ΔLIQUID + F_EQ_OFFER`

Range: 0-9. Düşük (0-1) = "Low F", Yüksek (8-9) = "High F".

> 📝 **Equal-weighted binary toplam.** Yazar açıkça "I adopted the binary signal
> approach because it is simple and easy to implement" [s.10] diyor. Sürekli
> versiyonlar veya factor analysis ile optimum kombinasyon "implementation
> cost"undan ötürü tercih edilmedi. **Bu wiki için tasarım kararı:** continuous
> + ranked versiyon test edildi [s.16] ve "qualitatively similar" sonuç verdi
> ama spread daha küçük (0.092 vs. 0.230).

## Empirik Sonuçlar (sayılarla)

### Örneklem [s.11-13, Tablo 1]

- Evren: COMPUSTAT, **sadece highest BM quintile** (yani value tilt'in en uç
  bacağı)
- Dönem: 1976-1996 (21 yıl), portföy formation 1975-1995 fiscal years
- 14,043 firm-year observations
- Ortalama firma: BM = 2.444, market cap = $188.5M (medyan $14.4M) → çoğunluk
  microcap [Tablo 1 Panel A, s.13]
- 41.6% firmaların önceki 2 yılda zarar yaşamış [s.7 fn 3]
- Returns: 12-month buy-and-hold, **fiscal year-end + 5 ay** itibarıyla başlar
  (look-ahead nötr) [s.11]

### Headline: One-year market-adjusted returns [Tablo 3 Panel A, s.16-17]

| Portföy | Mean | Median | %Positive | n |
|---|---|---|---|---|
| All high BM | 0.059 | -0.061 | 0.437 | 14,043 |
| Low F (0-1) | **-0.096** | -0.200 | 0.318 | 396 |
| High F (8-9) | **+0.134** | 0.000 | 0.500 | 1,448 |

| Karşılaştırma | Mean Diff | t-stat | p (bootstrap) |
|---|---|---|---|
| **High − All** | +0.075 | 3.140 | 0.002 |
| **High − Low** | +0.230 | 5.590 | 0.000 |

> 📝 Headline iddia (abstract): "an investment strategy that buys expected
> winners and shorts expected losers generates a **23% annual return** between
> 1976 and 1996" — Tablo 3 panel A High-Low = 0.230 [s.16].

### One-year raw returns [Tablo 3 Panel B, s.17]

- All high BM: 0.239
- Low F: 0.078
- High F: 0.313
- High − Low: 0.235 (t=5.59)

### Two-year market-adjusted [Tablo 3 Panel C, s.17]

- High F: +0.287
- Low F: -0.145
- High − Low: **+0.432** (t=5.75)

> 📝 İki-yıllık spread'in bir-yıllık spread'in *iki katından az* olması: post-formation
> momentum büyük kısmı *ilk yılda* gerçekleşir; ikinci yıl getiri şişişi sınırlı.

### Distribution shift [Tablo 3 Panel A, s.16]

Bootstrap testleri (10/25/median/75/90 yüzdelik):
- High F'ün 10. yüzdelik return'ü -0.462; Low F'ün -0.781 → **left tail %32 yukarı
  kayar** (-0.319 fark, t-significant).
- 90. yüzdelik: High F 0.885; Low F 0.490 → **right tail da yukarı kayar**.

**Yorumu:** F-Score sadece "ortalamayı yukarı taşımıyor", **tüm dağılımı sağa
kaydırıyor** (kötü-firma korumayı + iyi-firma seçimi birlikte yapıyor).

### Size-conditional results [Tablo 4, s.19] — wiki için KRİTİK

Size partition (1976-1996, 75K total obs, 14K high BM):

| Size | n high BM | High − Low return diff | t-stat | Anlam |
|---|---|---|---|---|
| Small (bottom 1/3 ME) | 8,302 (59%) | **+0.270** | 4.71 | sig 1% |
| Medium (mid 1/3) | 3,906 (28%) | +0.173 | 2.87 | sig 1% |
| **Large (top 1/3 ME)** | 1,835 (13%) | **+0.152** | **1.88** | **NOT sig (p=0.224)** |

> ⚠️ **Yazar yorumu [s.19]:** "differentiation is weak among the largest firms,
> where most return differences are either statistically insignificant or only
> marginally significant at the 5% or 10% level."

> ⚠️ **Wiki için ana implication:** **F-Score'un orijinal formülasyonu S&P 500 /
> Nasdaq 100 evrene direkt transferli DEĞİL.** Large-cap evrende spread mevcut
> ama istatistiksel olarak güçsüz. Bu nokta → [[meta/open_questions]] yeni
> Q18, [[meta/data_gaps]] yeni boşluk.

### Share price ve trading volume sonuçları [Tablo 5, s.20]

- Düşük share price + medium share price'da High − Low spread sig 1% (0.246, 0.258)
- High share price'da spread daha düşük (0.132, t-marginal)
- Düşük volume'da en güçlü, ama tüm volume seviyelerinde anlamlı

> 📝 Yazar yorumu [s.20]: "the positive return performance of this fundamental
> analysis strategy is not solely based upon an ability to purchase stocks with
> extremely low share prices."

### Behavioral mekanizma — earnings announcement returns [s.4-5, abstract]

- F-Score winner ile loser arasındaki yıllık 1-year market-adjusted return
  spread'inin **1/6'sı** (yani %16-17'si) **dört quarterly earnings announcement
  3-günlük pencerelerinde** gerçekleşiyor [s.4-5]
- Bu, **market'in F-Score implication'ını ex-ante fiyatlamadığı** ve sonradan
  earnings announcement'larda surprise olarak realize ettiği yorumunu destekler

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | "Winner vs loser" doğrudan formüle edilmiş; F=8-9 (top tier) vs F=0-1 (bottom tier); ayrıca size/share-price/volume alt-bölümleri [Tablo 4-5, s.19-20] | ✅ doğrudan fit |
| **Annual rebalance** | 12-aylık buy-and-hold default; portföy formation fiscal year-end + 5 ay [s.11]; rebalanslar yıllık | ✅ doğrudan fit |
| **Large-cap evrene transfer** | [Tablo 4, s.19] **Large size partition'da High-Low fark istatistiksel olarak anlamlı değil:** spread 0.152 (vs Small 0.270), t=1.88, p=0.224. Yazar açıkça "differentiation is weak among the largest firms" diyor | ⚠️ **UYARI: doğrudan transfer riskli**, formülasyon yeniden gerekli |
| **NDX intangibles / growth firms** | High-BM (BM-quintile-5) filtresi growth firms'i **dışlıyor** [s.5, s.11]; Nasdaq 100'ün ağırlıklı tech/growth profili bu evren dışında. Tech-heavy intangibles (R&D capitalization) bu paperda hiç ele alınmamış | ⚠️ **UYARI: scope dışı evren**, Mohanram 2005 G-Score ile cevaplanacak |

**Strateji tasarımına net implikasyon:**

1. **F-Score olduğu gibi S&P 500 / Nasdaq 100'e uygulanamaz.** Tablo 4 large-cap
   sonucu istatistiksel olarak null hipotezi reddetmiyor.
2. Yapılması gereken yapısal değişiklikler:
   - **Sektör nötrleştirme** (büyük cap evrende sektör bazlı baseline farkı)
   - **Universe-spesifik breakpoint** (CRSP all-stocks değil S&P 500 / NDX içi)
   - **Evren-spesifik bileşen ağırlıkları** (factor analysis veya in-sample
     tuning ile equal-weight binary yerine optimum)
   - **Growth-side için Mohanram G-Score paralel kalibrasyonu** (Nasdaq 100)
3. Bu 4 adım [[meta/open_questions]] Q18 altında konsolide edildi.

## Limitler ve Caveats

- **Universe sınırlı: sadece high-BM (value) [s.5]:** F-Score tüm hisseler için
  formüle edilmedi; yazarın iddiası high-BM'de financial distress sinyallerinin
  diferensiyel değer taşıdığı. **Growth tarafında** (low-BM) muhtemelen
  G-Score [Mohanram 2005] gerekecek (henüz wiki'de yok).
- **Microcap dominant [Tablo 1, s.13]:** Ortalama market cap $188M, medyan $14M.
  Strateji *uygulama olarak* küçük-cap arbitrajına yakın. Trading cost,
  capacity, liquidity sorunları paperda detaylı tartışılmaz.
- **Large-cap'te zayıf [Tablo 4, s.19]:** Yukarıda detayı verildi. **Wiki'nin
  amacı için en kritik kısıtlama.**
- **t-stat'lar parametrik (Newey-West / HAC yok):** Bootstrap ile cross-check
  yapıldı; bootstrap p-değerleri parametrik t-stat'larla uyumlu [Tablo 3].
- **Örneklem dönemi 1976-1996:** Post-publication decay testi paperda yok.
  Out-of-sample 1997-2014 evrimi için [Piotroski-So 2012] gerekli (Tier
  listesinde değil ama önerilen ek).
- **Survivorship bias:** Delisting return = 0 varsayılıyor [s.11] — yazara göre
  sonuçları "kötüleştirir" yani gerçek primum'u underestimate eder. Modern
  replikasyonlar delisting CRSP-method ile düzeltir.
- **Reporting lag varsayımı [s.11]:** 5 ay (fiscal year-end + 5 months). Modern
  PIT data ile bu lag daha kısalabilir; potansiyel performans gain.
- **Equal-weighted, binary signals [s.10]:** Optimal değil. Continuous + factor-
  analysis-weighted versiyon "qualitatively similar but smaller spread" [s.16].
  **Wiki için tasarım kararı:** binary basitlik mi, continuous güç mü? Bu seçim
  Faz 3'te tartışılır.
- **Industry-neutralization yapılmamış [s.7 fn 3]:** Yazar industry-adjusted
  versiyon test ettiğini ve "sonuçlar substantially farklı değil" dediğini
  belirtir ama detay göstermez. Sektör nötrleştirme open question.

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfalar
- [[F_Score]] — faktör/skor entity sayfası
- [[earnings_quality]] — kavram sayfası
- [[fundamental_scoring]] — kavram sayfası

### Bu paperın update ettiği mevcut sayfalar
- [[HML]] — Piotroski'nin "value premium'un kötü-tarafını ele" stratejisi:
  HML'in uzun bacağındaki firmaları F-Score ile filtrele

### İlgili paperlar (ingested)
- [[famafrench1993_three_factor]] — high-BM portföyü Piotroski'nin başlangıç
  evreni; F-Score "saf HML üstü" filtrelemedir
- [[cochrane2011_discount_rates]] — F-Score'un "absence of beta" çerçevesinde
  yeri: discount rate spread'i fundamental sinyallere göre **conditional**
  olabilir

### İlgili ingested paperlar (B bloğu komplemanı)
- [[mohanram2005_g_score]] — G-Score, growth-tarafı (low-BM) muadil paper.
  Mohanram acknowledgments [s.1] Joe Piotroski'yi explicit içerir; G-Score
  F-Score'un growth-side parallel'i olarak doğrudan motive edilmiş.
  **Methodoloji farkı:** F-Score "kendi geçmişine değişim" (Δ-based), G-Score
  "endüstri-medyana göre level" (industry-relative).
- [[li_mohanram2019_quality_value]] — F-Score'un **modern replikasyonu** (1973-2012,
  continuous rank-based, all-firms): hedge return +7.44% (orijinal +23.0%'den
  3x düşük; sebep: sample uzatma + universe genişlemesi + binary→continuous
  revision). Combined F&V/P 17.94% — F-Score'un large-cap zayıflığını
  kompanse eder. Detay: [[comparisons/f_score_vs_g_score]].
- [[hou_mo_xue_zhang_2020_security_analysis]] — F-Score q-factor / q5 model
  lens'inde test (1972-2018): **q5 alpha mikrocap 0.33% (sig); small/big
  0.10%/0.03% (insig)** [Tablo 2]. Yani F-Score'un getirisi large-cap'te
  q5 risk premium exposure'larıyla **büyük ölçüde span ediliyor**; ROE
  factor key driver. F-Score "saf alpha" değil, factor exposure proxy
  olarak çalışıyor.

### F-Score komponentlerinin origin paperları (ingested)
- [[sloan1996_accruals_anomaly]] — **F_ACCRUAL bileşeninin origin paperı**.
  Sloan'un 1962-1991 sample'ında accruals anomaly +10.4%/yıl raw hedge return
  [Tablo 6, s.305]; Piotroski 2000 (1976-1996 sample) F_ACCRUAL'i Sloan
  paterninin binary versiyonu olarak adapte etti. Continuous decile (Sloan)
  → binary CFO>NI (F-Score) simplifikasyonu.

### Bu paperın update ettiği yeni paper sayfası (Cycle 12)
- [[harvey_liu_zhu_2016_multiple_testing]] — F-Score multiple-testing-
  corrected durumu: **BM-Q5 origin sample t=5.59 sig her cutoff'ta**
  (Bonferroni / Holm / BHY hepsi sig). **AMA Tablo 4 large-cap partition
  t=1.88 multiple-testing-corrected kesin insig**. Üç darbe çerçevesinin
  iki bacağı: in-sample large-cap reddi + MT-corrected reddi.
  [[mclean_pontiff_2016_post_publication_decay]] [Tablo 8] limited
  arbitrage üçüncü bacak. F-Score large-cap standalone Faz 3'te
  kullanılmaz; F & V/P combined kompanse eder.

### Cycle 13 ek (HXZ 2020 ingested)
- [[hou_xue_zhang_2020_replicating_anomalies]] — F-Score quarterly (Fq)
  durumu [s.27]: 1m/6m/12m horizon'da klasik high-minus-low
  0.58%/0.53%/0.42% (t=2.47/2.52/2.22) **sig**; **q-factor alpha
  0.13%/0.15%/0.07% (t=0.58/0.86/0.49) INSIG** — q-factor Roe factor
  F-Score'u tam span ediyor. HMXZ Security Analysis (Cycle 8) ile
  uyumlu. Üç darbe çerçevesinde F-Score (BM-Q5 origin) 3/4 (q-factor
  span = Roe factor exposure proxy); F-Score (large-cap, Tablo 4)
  **0/4** (in-sample insig + post-pub agresif + MT insig + replication
  paralel insig). Earnings announcement abnormal returns (Abr) — paper
  [s.27] q-factor alpha sig; Piotroski 2000 [s.4-5] F-Score spread'in
  1/6'sı Abr penceresinde realize → Piotroski'nin behavioral
  mekanizmasının q-factor lens'inde de hayatta kalan bileşeni. Detay
  [[concepts/anomaly_replication]] + [[concepts/post_publication_decay]]
  dört darbe çerçevesi.

### Bu paperın update ettiği yeni paper sayfası (Cycle 11)
- [[mclean_pontiff_2016_post_publication_decay]] — 82 anomaly aggregate
  post-pub decay %35 (sig 1%); F-Score 82 anomaly setinde explicit listed
  **DEĞİL** (paper ref list'te Piotroski 2000 yok — F-Score için decay
  rakamı paperdan tek-başına çıkmıyor). Aggregate decay multiplier
  uygulanır; modern empirik karşılaştırma için Li-Mohanram 2019 modern
  replikasyon ([[li_mohanram2019_quality_value]]) F-Score continuous
  +7.44% (1973-2012, all-firms) → orijinal +23.0%'den ~3x düşüş; bu
  aggregate decay'i içselleştiriyor + universe genişlemesi + binary→
  continuous + industry revision karışık etken.
  > ⚠️ **Çift darbe**: Piotroski Tablo 4 large-cap zaten zayıf (0.152
  > t=1.88, p=0.224 insig); McLean-Pontiff Tablo 8 [[post_publication_decay]]
  > büyük/likit/divid-payer firmalarda post-pub decay daha güçlü. Wiki
  > amaç evrenleri (S&P 500 + NDX) bu profilin tam ortasında → in-sample
  > zayıf + post-pub decay agresif kümülatif yapısal risk.

### Henüz wiki'de olmayan, doğrudan ilgili paperlar
- Beneish (1999) — M-Score forensic filter olarak F-Score ile kombine (Tier 1 #15)
- Lakonishok-Shleifer-Vishny (1994) — value etkisinin kavramsal temeli (Tier 1 #7)

## Çelişkiler / Tartışmalar

> 📝 Henüz çelişki yok — Piotroski risk-vs-mispricing yorumunu açıkça
> *behavioral mispricing* tarafında konumlandırıyor [s.4-5]
> ("market initially underreacts to historical information"). Fama-French (1992)
> yorumu (high-BM = financial distress = rational risk premium) ile bu yorum
> çelişir. Cochrane (2011) çerçevesinde bu **#4 sorusu** (why do prices move) —
> wiki bu felsefi tartışmayı stratejik kararlarda taraf tutmaz.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Yeni Q18]** F-Score'un large-cap (S&P 500 / Nasdaq 100) evrende
  performansı [Tablo 4, s.19] istatistiksel olarak anlamlı değil. **Bu wiki'nin
  amacı için F-Score nasıl yeniden formüle edilmeli?** Sektör-nötrleştirme,
  evren-spesifik breakpoint, alt-bileşenlerin tekrar ağırlıklandırılması — hangisi
  large-cap'te transferli skor üretir? Cevaplar için Mohanram 2005 (G-Score
  growth tarafı) + Li-Mohanram 2019 (combined) ingestleri kritik. Ek olarak
  Piotroski-So 2012 (out-of-sample, Tier listesinde değil) önerilebilir.

- **[Q1 partial-stronger update]** Original sample 1976-1996. **Post-1996 ve özellikle
  post-2000 F-Score performansı?** McLean-Pontiff 2016 ingest edildi
  [[mclean_pontiff_2016_post_publication_decay]]: 82 anomaly aggregate
  %35 post-pub decay; F-Score paperin explicit ref list'inde değil ama
  aggregate decay multiplier (×0.65) uygulanabilir. Spesifik F-Score
  decay için Li-Mohanram 2019 modern replikasyonu (1973-2012, +7.44%)
  ortogonal kanıt. Tam Q1 cevabı için Lev-Srivastava 2020 (Tier 2 #30)
  post-2010 value-spesifik decay kanıtı eksik.

- **[Q5 fully-answered (aggregate); partial (F-Score-spesifik)]**
  Post-publication decay: aggregate %35 cevabı [[mclean_pontiff_2016_post_publication_decay]]
  üzerinden geliyor; F-Score spesifik decay rakamı için Li-Mohanram 2019
  modern replikasyon (~3x düşüş) ortogonal empirik kanıt; saf decay
  komponenti karışık etken nedeniyle ayrıştırılmamış. Detay
  [[post_publication_decay]].

- **F-Score'un BM-quintile-5 evrenine bağımlılığı:** Pure value evren dışında
  (örn. tüm S&P 500) F-Score relevance düşer mi? Mohanram G-Score (low-BM)
  bu sorunun komplemanı.

- **Continuous vs. binary inşa:** Yazar binary kullanıyor "implementation cost"
  argümanıyla [s.10]; modern computation gücü ile continuous F-Score yapılabilir.
  Performansı Faz 3'te test edilmeli.

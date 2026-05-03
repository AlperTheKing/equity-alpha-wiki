---
type: factor
name: Asset_Growth
category: investment
direction: long_low  # uzun düşük asset growth, kısa yüksek asset growth
data_lag_required: "Annual report total assets t ve t-1; standard reporting lag"
rebalance_frequency: annual
universe_tested: ["NYSE+AMEX+NASDAQ ex-financials, 1968-2016 (CGS-Ion modern revisit)"]
cycle_39_note: "Stambaugh-Yuan 11 anomaly Cluster 1 (MGMT) içinde asset growth + I/A dahil [[factors/MGMT]] Cycle 39 ✓ ([[papers/stambaugh_yuan_2017_mispricing_factors]]); composite mispricing P1 6-anomaly avg ranking; Asset_Growth tek-anomaly factor + UMO1 composite mispricing factor complementary methodology"
---

# Asset Growth (Total Asset Growth Anomaly)

## Tanım [[cooper_gulen_ion2018_asset_growth_factor_models]] [s.7]

```
Asset Growth_t = (Total Assets_t − Total Assets_{t-1}) / Total Assets_{t-1}
```

- Total Assets = Compustat AT
- Annual measure, June rebalans
- Filtreler: financials hariç, negative book equity hariç (CGS 2008 + CGS-Ion
  2018 convention)

## Origin

- **Empirical origin:** Cooper-Gulen-Schill (2008) "Asset Growth and the
  Cross-Section of Stock Returns" — **JF orijinal paperı; wiki'de YOK
  (paywall, [[meta/data_gaps]] notu)**
- **Modern revisit (de facto wiki entity referansı):** [[cooper_gulen_ion2018_asset_growth_factor_models]]
- **Theoretical kökenler:**
  - Cochrane (1991) investment-q model — rational yorum (high investment →
    low future return)
  - Lakonishok-Shleifer-Vishny (1994) tarzı mispricing — extrapolation hipotezi
  - Detay: [[asset_growth_anomaly]] concept sayfası

## CMA ile hierarchical relationship

```
[[CMA]] (FF15 mimicking-portföy investment factor)
   = aggregate / sorted version of Asset Growth measure
       │
       ▼
[[Asset_Growth]] (this entity)
   = single-variable decile sort, standalone hedge return testi
```

**Detay:**
- **CMA**: 2x3 NYSE breakpoint mimicking-portföy (low asset growth long,
  high asset growth short, value-weighted) → factor model regresyon değeri
- **Asset_Growth**: single-variable decile (10) sort → hedge return
- **HXZ q-factor I/A factor:** aynı asset growth measure, farklı portfolio
  inşası
- **CGS asset growth ölçüsü** her üç yapının altındaki temel metric

## Reported Performance Across Studies

| Paper | Dönem | Evren | Spread | t-stat | Notlar |
|---|---|---|---|---|---|
| Cooper-Gulen-Schill 2008 (origin) | 1968-2003 | NYSE+AMEX+NASDAQ ex-fin | (paperda yok, paywall) | — | **Wiki'de doğrulanamadı**; original headline literatürde ~13% per year decile spread olarak referans verilir, modern wiki kanıtı [[cooper_gulen_ion2018_asset_growth_factor_models]] üzerinden |
| [[cooper_gulen_ion2018_asset_growth_factor_models]] (extended) | 1968-2016 | aynı | decile 10 − decile 1 negatif sig | (paperdan teyit) | [Tablo II, s.10]; CGS pattern out-of-sample replicates; spesifik rakam paper detayında |
| [[cooper_gulen_ion2018_asset_growth_factor_models]] (q5/FF5 lens) | aynı | aynı | factor model alpha analizi | — | [s.3-4]; HXZ + CGS asset growth = **5/35** anomaly açıklanamıyor; CAPX/PPE/intangibles ile değiştirildiğinde **15-24/35** açıklanamıyor → asset growth ölçüsü unique |
| [[mclean_pontiff_2016_post_publication_decay]] aggregate decay multiplier | (82 anomaly aggregate, 1972-2011) | NYSE+AMEX+NASDAQ all-stocks aggregate | aggregate post-pub decay **%35** (sig 1%); CGS asset growth (2008 origin) paper ref list'inde **explicit listed değil** ama "accounting-related sorts" aggregate'ta dahil | (anomaly-equal-weighted aggregate t-stat values [Tablo 2, s.31]) | [Tablo 3, s.32] aggregate decay; CGS-Ion 2018 sample 1968-2016 zaten post-publication dönem (CGS 2008 yayım sonrası 13 yıl) içerir → modern revisit'in anomaly'i hayatta bulması aggregate decay'in **anomaly-spesifik survival** açısından zayıflamamış örneği; sample-uzatma robustness'ı için relatif güçlü kanıt |

_(Hou-Xue-Zhang 2020 "Replicating Anomalies" Tier 1 #18 ingestiyle 2018+ replication eklenebilir.)_

## Faktör Ailesi İçindeki Yeri

- **[[CMA]]** — aggregate version (FF15 mimicking-portföy)
- **HXZ q-factor I/A** — aynı asset growth measure, farklı portfolio yapısı
- **[[Accruals]]** — Sloan total accruals ile yapısal yakın; working capital
  bileşeni overlap. Fairfield-Whisenant-Yohn 2003 (Tier 2 #37) bu ayrımı
  decompose eder.
- **F_ΔLEVER + F_EQ_OFFER** ([[F_Score]]) — debt/equity-funded asset growth
  proxy'si ama Piotroski'nin literature kökü Myers-Majluf 1984 (asset growth
  literatürü değil).
- **G7 (Capex/Assets)** ([[G_Score]]) — capex direct asset growth driver ama
  Mohanram'ın yorumu **yön açısından ters** (G7 long-high; CGS long-low).
- **Subsumed by?** Wiki'de doğrudan kanıt yok; [[hou_mo_xue_zhang_2020_security_analysis]]
  q5 model'in I/A factor'ü asset growth measure'a kritik bağlı olduğundan
  span ilişkisi tautolojik (q-factor + asset growth = asset growth + asset
  growth).

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

- **Sample NYSE+AMEX+NASDAQ all-stocks**, large-cap-only kalibrasyon yok.
- Sloan accruals paterniyle paralel — anomaly **size-loaded** olabilir; [[meta/open_questions]]
  Q4 (Cooper-Gulen-Schill asset growth large-cap'te?) paperdan teyit
  bekliyor.
- **NDX tech firma asset growth ölçümü:** [[cooper_gulen_ion2018_asset_growth_factor_models]]
  intangibles düzeltmesinin (Peters-Taylor 2017 total capital) anomaly'i
  GÜÇLENDİRMEDİĞİNİ raporluyor [s.5-6]. Yani NDX evrene transfer için "intangibles
  düzelt" naif yaklaşımı yetersiz; Q26 paralel açık soru.

## Decay / Post-Publication Performance

[[cooper_gulen_ion2018_asset_growth_factor_models]] sample 1968-2016, post-CGS
2008 paper (2003 sonu) dönemi out-of-sample dahil; anomaly hayatta — yani
CGS asset growth post-publication decay sample-uzatma testinde **görece güçlü
survival** gösterir.

[[mclean_pontiff_2016_post_publication_decay]] [Tablo 3, s.32] 82 anomaly
aggregate **post-pub decay %35 (sig 1%)**. CGS asset growth 82 anomaly
setinde Cochrane "accounting-related sorts" taksonomisi içinde aggregate'a
dahil edilebilir — ama explicit ref'te yok. Aggregate multiplier (×0.65)
uygulanır; CGS-Ion 2018 sample uzatma sonrası anomaly hayatta, **aggregate-
altı decay rate** (yani anomaly relatif güçlü).

> 📝 **Wiki yorumu:** Asset growth anomaly McLean-Pontiff aggregate
> baseline'ından *daha yavaş* decay yaşıyor görünüyor (sample uzatma
> sonrası anlamlı kalmaya devam). Nedeni paperde explicit yok; iki olası
> açıklama: (a) anomaly mekanizması mispricing değil rational q-theory
> reaction (Q27 cevap arar), (b) limited arbitrage faktörleri (büyük cap
> firmaların asset growth ölçümü görece distorted) decay'i yavaşlatıyor.
> Detay [[post_publication_decay]] decay-adjusted spread tablosu — CGS
> asset growth satırı modern revisit sample post-pub dönem dahil olduğu
> için "modern out-of-sample" sütunu zaten decay'i içselleştiriyor.

### Multiple Testing Status (Cycle 12 ek)

[[harvey_liu_zhu_2016_multiple_testing]] çerçevesinde CGS asset growth
HLZ Şekil 3 mark'inde explicit yok ama Tablo 1 "Accounting Individual"
kategorisi içinde aggregate framework'e dahil. CGS 2008 origin paper
literatürde t-statistic ~10+ konvansiyonu üzerinden multiple-testing-
corrected sig **yaklaşık** her cutoff'ta. CMA factor (FF15 mimicking)
2x3 inşa t=4.07 sig her cutoff'ta. Üç darbe çerçevesinde asset growth
2-3/3 (sample uzatma sonrası görece güçlü survival). Detay
[[concepts/multiple_testing]] aggregate tablosu;
[[concepts/post_publication_decay]] üç darbe çerçevesi tablosu.

### Replication Status (Cycle 13 ek — HXZ 2020 ingested)

[[hou_xue_zhang_2020_replicating_anomalies]] [s.5] Cooper-Gulen-Schill
2008 asset growth **explicit listed** significant (replicate edilen
"smaller in magnitude than originally reported"). Investment kategorisi
38 anomaly içinde 27 sig (%71 — momentum + investment en yüksek
replication rate'leri). CMA factor q-factor lens'inde span ediliyor
(klasik 0.34% sig + q-factor alpha 0.01% insig) — q-factor I/A factor
CGS asset growth measure'a dayandığı için **tautolojik subsumption**
([[cooper_gulen_ion2018_asset_growth_factor_models]] uyumlu). Üç darbe
+ replication = **dört darbede 3-4/4** (görece güçlü survival, q-factor
span = investment factor exposure proxy). Detay
[[concepts/anomaly_replication]] aggregate tablosu;
[[concepts/post_publication_decay]] dört darbe çerçevesi tablosu.

### Intangibles-adjusted asset growth (Cycle 15 ek — Lev-Sougiannis ingested)

[[lev_sougiannis_1996_rd_capitalization]] R&D capitalization
methodology asset growth measure için **intangibles-aware revision**
sağlar:
- Geleneksel: `Asset Growth = (TA_t - TA_{t-1}) / TA_{t-1}`
- R&D-adjusted: TA → TA + RDC (R&D capital cumulative eklenmiş)
- Tech-heavy firms: 22.2% average book equity understatement
  ([[lev_sougiannis_1996_rd_capitalization]] [s.123]) → geleneksel
  asset growth measure yapay sinyal

### Total intangibles-adjusted asset growth (Cycle 16 ek — Peters-Taylor ingested)

[[peters_taylor_2017_intangible_capital]] Lev-Sougiannis R&D-only
methodology'sini total intangible capital'a genişletir:
- Total-adjusted: `((TA + K^int)_t - (TA + K^int)_{t-1}) /
  (TA + K^int)_{t-1}` burada K^int = Knowledge + Organization +
  External (Peters-Taylor Eq. 11)
- **CGS-Ion 2018 [s.5-6] explicit Peters-Taylor methodology kullanmış
  (modern revisit'in iki paralel açıklayıcısı):** HXZ + Peters-Taylor
  total capital → 5/35 → **23/35 unexplained** (intangibles düzeltmesi
  anomaly açıklayıcı gücünü **GÜÇLENDİRMİYOR** ⚠️)
- Yorumu: Peters-Taylor methodology asset growth measure'ı
  intangibles-aware versiyona dönüştürdüğünde anomaly **persist**
  ediyor — CGS asset growth measure'ın mekanizması saf intangibles-
  underrecognition değil; başka kaynak (working capital, acquisitions,
  noncash CA) baskın
- **NDX evrene transfer rec:** Faz 3 spec'inde **iki paralel asset
  growth measure** baseline + sensitivity:
  - Geleneksel CGS: `(TA_t - TA_{t-1}) / TA_{t-1}`
  - Peters-Taylor adjusted: `((TA + K^int)_t - (TA + K^int)_{t-1}) /
    (TA + K^int)_{t-1}`
  Iki ölçü Faz 3 horse race'te değerlendirilir (Q40 SG&A θ=30%
  kalibrasyonu + Q41 Lev-Sougiannis vs Peters-Taylor vs Eisfeldt-
  Papanikolaou)
- Detay [[concepts/intangibles_adjusted_accounting]] F bloğu anchor
  concept.

## Implementation Notes

- **Required data:** Compustat AT (total assets), t ve t-1
- **Sharadar:** trivial computation
- **Annual rebalance:** June (CGS convention)
- **Filtreler:** financials (SIC 6000-6999) ve negatif book equity firmaları
  hariç (CGS standart)
- **Decile sorting:** NYSE breakpoint convention (FF tradition); alternatif
  evren-içi median (Q19 NDX uygulaması) açık soru
- **Working capital + acquisitions decomposition** [[cooper_gulen_ion2018_asset_growth_factor_models]]
  [s.6, Section 4]: asset growth'un alt-bileşenleri (cash, noncash current
  assets, gross PPE, other assets) ayrı ayrı test edilir; "other assets" ve
  noncash CA bileşenleri PPE'den **daha büyük paylar** ve asset growth'un
  açıklayıcı gücünün büyük kısmı bu non-PPE bileşenlerden geliyor

## Bu Faktörün Yumuşak Karnı

- **Mekanizma belirsiz:** Asset growth'un *neden* unique olduğu paper
  tarafından açık değil. Investment-q rational yorumu vs LSV mispricing
  yorumu (Q27 wiki açık sorusu).
- **Intangibles düzeltmesi anomaly'i güçlendirmiyor [[cooper_gulen_ion2018_asset_growth_factor_models]]
  [s.5-6]:** Peters-Taylor 2017 metodu uygulandığında HXZ + total capital
  daha kötü performans (5 → 23 unexplained anomaly). NDX evrene transfer
  için açık soru — Lev-Sougiannis 1996 alternatif metod beklenir.
- **Original CGS 2008 wiki'de yok (paywall):** Rakamlar modern revisit
  üzerinden; orijinal headline 13%/year (literatürde anılır) doğrulanmadı.
- **Working capital + accruals overlap:** Sloan total accruals ile yapısal
  yakın; iki signal'i birlikte kullanmak partial redundant olabilir.
  Fairfield-Whisenant-Yohn 2003 (Tier 2 #37) decompose eder — wiki'de yok.
- **Mispricing vs risk premium yorumu:** [[hou_mo_xue_zhang_2020_security_analysis]]
  q-factor model investment factor (asset growth) "risk premium" yorumu
  sunar; CGS 2008 mispricing yorumu sunar. Mathematical equivalence
  ([[cochrane2011_discount_rates]]).
- **Yön farkı (G_Score G7):** G7 yüksek-capex pozitif sinyal; CGS asset
  growth yüksek negatif. Mohanram'ın growth-firma bağlamı CGS'in literatür
  kökünden farklı yön ⊕/⊖ yorumlamasını üretiyor — strateji tasarımı için
  context-aware.

## İlgili

- [[cooper_gulen_ion2018_asset_growth_factor_models]] — modern revisit paper
- [[asset_growth_anomaly]] — concept sayfası (mekanizma adayları)
- [[CMA]] — aggregate / mimicking-portföy version (FF15)
- [[Accruals]] — Sloan total accruals; working capital bileşeni overlap
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 model I/A factor (aynı
  asset growth measure'ı kullanır)
- [[famafrench2015_five_factor]] — CMA factor formal tanımı
- [[F_Score]] (F_ΔLEVER, F_EQ_OFFER ile dolaylı bağ; origin Myers-Majluf, CGS değil)
- [[G_Score]] (G7 yön farkı notu)
- [[fundamental_scoring]] — investment-side composite skorlamada bileşen
- [[mclean_pontiff_2016_post_publication_decay]] — 82 anomaly aggregate
  decay %35; asset growth ref list'inde explicit yok ama CGS-Ion 2018
  sample uzatma anomaly hayatta = aggregate-altı decay rate
- [[lev_sougiannis_1996_rd_capitalization]] — R&D capitalization
  methodology (intangibles-adjusted asset growth seviyesi 1)
- [[peters_taylor_2017_intangible_capital]] — total intangible capital
  methodology (intangibles-adjusted asset growth seviyesi 2; CGS-Ion
  2018'in kullandığı methodology)
- [[concepts/intangibles_adjusted_accounting]] — F bloğu hub
- (sonra) Cooper-Gulen-Schill 2008 — original paper (paywall risk)
- (sonra) Hou-Xue-Zhang 2015 — q-factor origin paperı (Tier 1 #3)
- (sonra) Fairfield-Whisenant-Yohn 2003 — accrual + asset growth decompose
  (Tier 2 #37)
- (sonra) Eisfeldt-Papanikolaou 2013 — organization capital direct
  factor portfolio (Tier 2 #28)

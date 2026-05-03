---
type: paper
authors: [Cooper, Michael, Gulen, Huseyin, Ion, Mihai]
year: 2018
title: "The Use of Asset Growth in Empirical Asset Pricing Models"
venue: "Working Paper, May 2018 (Utah / Purdue / Arizona)"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1335524
local_path: raw/papers/cooper_gulen_schill_2008_asset_growth.pdf
ingested: 2026-04-28
tags: [asset_growth_anomaly, CMA_origin, q_factor_critique, FF5_critique, intangibles_skepticism, C_blok_2]
status: ingested
cycle_37_note: "CGS asset growth + FF 2008 size-conditional dissection paralel papers (aynı yıl 2008; CGS 2008 asset growth origin univariate decile + FF 2008 [Tablo II + IV] asset growth size-partition methodology test) [[papers/fama_french_2008_dissecting_anomalies]] Cycle 37 ✓; FF 2008 hedge return big VW -0.02% t=-0.10 INSIG + slope big -0.17 t=-0.86 INSIG → CGS asset growth large-cap'te yok ANCHOR; CGS-Ion 2018 size-loaded uyarı FF 2008 origin'inde dokümante"
cycle_39_note: "Stambaugh-Yuan 11 anomaly Cluster 1 (MGMT) içinde asset growth + I/A dahil [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; mispricing composite scoring P1 6 anomaly avg ranking; CGS-Ion CMA factor exposure proxy + Stambaugh-Yuan UMO1 composite mispricing factor complementary methodology"
---

# Cooper, Gulen & Ion (2018) — Asset Growth in Asset Pricing Models

> 📝 **Atıf konvansiyonu:** `[Tablo N]` ve `[s. X]`. Embedded text extract:
> `raw/papers/cooper_gulen_ion_2018_asset_growth.txt`. Local PDF dosya adı
> `cooper_gulen_schill_2008_asset_growth.pdf` (yanlış indirme; **gerçek paper
> Cooper-Gulen-Ion 2018**).

> 📝 **Kimlik düzeltmesi:** Bu paper **orijinal Cooper-Gulen-Schill (2008)
> "Asset Growth and the Cross-Section of Stock Returns" DEĞİL.** Bu, Schill
> yerine Ion eklenmiş, başlığı **"The Use of Asset Growth in Empirical Asset
> Pricing Models"** olan modern revisit (May 2018 draft). Original 2008 paperı
> wiki'de yok (paywall) → [[meta/data_gaps]] notu.

> 📝 **C bloğunun #2'si** — earnings quality / accruals / **investment**.
> [[CMA]] factor'ün (FF15 investment factor) ve HXZ q-factor I/A factor'ünün
> empirical origin'i. Bu paper original 2008 anomaly'i kanıtlamak yerine, **q5
> ve FF5'in investment factor inşasının asset growth ölçüsüne kritik bağlı
> olduğunu** gösteren analiz.

## TL;DR

Sample: 1968-2016 (CGS 2008'in 1968-2003'ünden uzatılmış), NYSE+AMEX+NASDAQ
ex-financials. **35 anomaly spread portfolio** üzerinde HXZ q-factor model +
FF5 model performansı asset growth ölçüsünün yapısına göre test ediliyor.
**Kritik bulgular [s.3-4, abstract]:**

1. **HXZ orijinal (CGS asset growth):** 35 anomaly'den **5'i** açıklanamıyor
   (5/35 alpha sig).
2. **HXZ + CAPX-based investment factor:** **15/35** anomaly açıklanamıyor.
3. **HXZ + PPE-based investment factor:** **14/35** açıklanamıyor.
4. **HXZ + total capital (intangibles dahil):** **23/35** açıklanamıyor — *daha
   da kötü*.
5. **FF5 (CGS asset growth):** **11/35** açıklanamıyor.
6. **FF5 + CAPX:** **23/35** açıklanamıyor.
7. **FF5 + PPE:** **24/35** açıklanamıyor.

**Net iddia:** q-factor / FF5 modelin investment factor'ünün açıklayıcı gücü
**asset growth'un kendisinden geliyor**, traditional yatırım ölçülerinden
(CAPX, PPE) **değil**. Intangibles düzeltmesi de yardım etmiyor.

## Tek Cümle Tezi

q-factor (HXZ 2015) ve FF5 (FF 2015) modellerinin investment factor'ünün
empirik gücü — yani anomaly spread portfolio'larını açıklama kapasitesi —
geleneksel yatırım ölçüleri (CAPX, PPE, intangibles-adjusted) yerine **CGS 2008
asset growth ölçüsünün spesifik yapısına** kritik bağlıdır; bu, "asset growth =
investment proxy" yorumunu sorgular.

## Bu paper'ın sürprizi

> ⚠️ **Wiki'nin önceki sentezini sorgulayan bulgu.** Önceki sentez:
> [[CMA]] ve q-factor I/A faktörü = **investment proxy**, capex/debt
> issuance ile değiştirilebilir.
>
> **Bu paperın kanıtı [s.3-4, Tablo (paperdan teyit)]:** Asset growth measure'ı
> CAPX, PPE veya intangibles-adjusted versiyonla değiştirildiğinde **q-factor
> ve FF5 model performansı dramatik düşüyor** (5/35 → 15-24/35 unexplained).
> Yani asset growth ölçüsü **unique** bir signal — geleneksel investment
> measures ile reproduce edilemiyor.
>
> **Wiki için implication:** "CMA = investment proxy" kavramsal yorumu
> **revisit** edilmeli. CMA'nın getirisi sadece "firma yatırım yapıyor mu?"
> sorusunu yakalamıyor; asset growth'un spesifik yapısı (working capital +
> capex + acquisitions + diğer) **kombine** bir anomaly. Bu, "asset growth
> mekanizması" sorusunu açar — investment-q reaction (rational) mı, mispricing
> mi, yoksa **asset growth'un kendisinin başka bir mekanizmaya bağlı** olduğu
> mu (Sloan accruals + working capital + investor inattention bileşeni)?
>
> **Etkilenen wiki sayfaları (challenged-by işareti uygulandı):**
> - [[CMA]] — "investment proxy" yorumu sorgulandı
> - [[famafrench2015_five_factor]] — CMA factor'ün empirik temeli
> - [[hou_mo_xue_zhang_2020_security_analysis]] — q5 I/A factor'ün empirik temeli

## Ana methodoloji

### Asset Growth measure (CGS 2008)

`Asset Growth_t = (Total Assets_t − Total Assets_{t-1}) / Total Assets_{t-1}`

Yıllık. Annual report'tan, June rebalans (tipik convention).

### Test çerçevesi

35 anomaly spread portfolio (HXZ 2015 paperından temin) → multi-factor model
regresyonu ile alpha test. Her model versiyonu için "açıklanamayan anomaly
sayısı" (alpha sig) raporlanır.

**Models:**
- **HXZ (q-factor):** R - Rf = α + β_MKT·MKT + β_ME·ME + β_I/A·I/A + β_ROE·ROE [Eq. 1, s.X]
- **FF5:** R - Rf = α + β_MKT·MKT + β_SMB·SMB + β_HML·HML + β_RMW·RMW + β_CMA·CMA [Eq. 2, s.X]
- **Carhart 4F (C4F):** baseline comparison
- **Alternative investment factor versiyonları:**
  - CAPX (Compustat capital expenditure)
  - PPE growth (property, plant, equipment)
  - Total capital (CAPX + intangibles, Peters-Taylor 2017 metodu)
  - Diğer balance-sheet alt-bileşenleri (cash, noncash current assets, gross PPE, "other assets")

## Empirik Sonuçlar (sayılarla)

### Sample ve hazırlık [s.7-8]

- Evren: NYSE+AMEX+NASDAQ
- Dönem: **July 1968 - June 2016** (CGS 2008'in 1968-2003'ünden 13 yıl uzatılmış)
- Filtreler: financials hariç, negative book equity hariç [s.7 fn 3]

### Original asset growth anomaly replikasyonu [Tablo II, s.10]

CGS 2008 paterninin 1968-2016 sample'da out-of-sample replikasyonu (paperdan
teyit edilecek detay):
- Decile 10 (yüksek asset growth) − Decile 1 (düşük asset growth) hedge
  return: significantly negatif (consistent with CGS 2008 "high-asset-growth
  underperforms")
- 1968-2016 sample'da anomaly **hayatta** ama büyüklüğü original'a göre
  ölçülecek

### Anomaly spread portfolio test sonuçları [paperdan teyit, kritik tablolar]

35 HXZ anomaly spread portfolio'sunda her model'in açıklayamadığı anomaly
sayısı:

| Model | Investment factor | Unexplained / 35 |
|---|---|---|
| HXZ original | CGS asset growth | **5** |
| HXZ alt | CAPX | **15** |
| HXZ alt | PPE growth | **14** |
| HXZ alt | total capital (intangibles dahil) | **23** |
| FF5 original | CGS asset growth (CMA) | **11** |
| FF5 alt | CAPX | **23** |
| FF5 alt | PPE growth | **24** |
| Carhart 4F | (no investment factor) | comparison baseline |

> 📝 **Tek satır özet:** Investment factor'ün CGS asset growth ölçüsünden
> CAPX/PPE'ye değiştirilmesi **unexplained anomaly sayısını ~3x artırıyor**.

### Intangibles düzeltmesi [s.5-6 + Tablo (paperdan teyit)]

- "Total capital" (Peters-Taylor 2017 metodu) — CAPX + intangibles capitalization
- HXZ + total capital: **23/35** unexplained (CAPX'tan **daha kötü**)
- Yorum: intangibles düzeltmesi tek başına asset growth'un avantajını telafi
  etmiyor

### Asset growth'un yapısal decompose'u [s.6, Section 4]

CGS asset growth = Δ(cash + noncash current assets + gross PPE + other assets)

- "Other assets" ve noncash current assets bileşenleri **PPE'den daha büyük
  paylar**
- HXZ + (asset growth eksi PPE-related component) → performans **düşmüyor**
- Yorum: asset growth'un açıklayıcı gücü PPE-related olmayan bileşenlerden
  geliyor (working capital + acquisitions + diğer)

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Asset growth decile spread (top vs bottom) test edilmiş + 35 anomaly spread portfolio formal asset pricing test çerçevesi | ✅ doğrudan fit |
| **Annual rebalance** | June rebalance, annual asset growth measure'a uygun | ✅ doğrudan fit |
| **Large-cap evrene transfer** | Sample NYSE+AMEX+NASDAQ all-stocks; explicit large-cap-only test paperda yok. Asset growth literatürde Sloan accruals paterniyle paralel — **size-loaded** olabilir (Q4 ile bağlı) | ⚠️ size-loaded olası; large-cap-only kalibrasyon yok |
| **NDX intangibles / growth firms** | **Sürpriz bulgu:** intangibles düzeltmesi (Peters-Taylor 2017 total capital) anomaly'i **GÜÇLENDİRMİYOR** — aksine HXZ unexplained 5 → 23'e çıkıyor. Tech firmalarda asset growth ölçümü yapısal sorun (Q26 ile paralel) | ⚠️ + sürprizli; intangibles düzeltmesi yardımcı olmuyor; NDX evrene transfer için açık soru |

**Strateji tasarımına net implikasyon:**

Bu paper, **CMA / I-A factor'ün Faz 3 strateji tasarımındaki rolü için
revisit ettiren bulgu**. Üç dengeli kayıt:

1. **Asset growth ölçüsü unique:** CAPX, PPE, intangibles-adjusted total
   capital ile değiştirilemez. CMA factor exposure almak istenirse asset
   growth'un kendisi kullanılmalı, "investment proxy" yorumuyla alternatif
   ölçüm seçilmemeli.
2. **Intangibles düzeltmesi paradoksu:** Peters-Taylor 2017 metodunun asset
   growth'a uygulanması performans **düşürüyor** — yani NDX tech-heavy
   evrene transfer için "intangibles düzelt" stratejisi naif olabilir.
   Q26 ile paralel olarak bu wiki'de açık soru.
3. **Asset growth'un mekanizması belirsiz:** CGS 2008 mispricing yorumu;
   HXZ q-theory rational yorumu; bu paper ikisini de doğrudan test etmiyor —
   sadece **CGS measure'ın ampirik üstünlüğünü** raporluyor. Mekanizma
   sorusu açık (Q27).

## Limitler ve Caveats

- **Original CGS 2008 paper paywall'sız wiki'de yok:** Bu paper modern revisit;
  original headline rakamlar (1968-2003 sample) wiki'de doğrulanmamış.
- **Intangibles düzeltmesi sadece Peters-Taylor 2017 metodu test edilmiş:**
  Lev-Sougiannis 1996 ve diğer alternatif intangible capitalization metotları
  bu paperda yok.
- **Mekanizma sorusu:** Paper "asset growth ölçüsü unique" diyor ama **NEDEN**
  unique olduğu cevaplanmamış (working capital? acquisitions? mispricing
  bileşeni?). Bu açık soru → Q27.
- **Sample 1968-2016, post-2016 yok:** FAANG-dominant 2017-2024 dönemi
  out-of-sample.
- **NDX 100 endeks-üyesi spesifik test yok:** Tüm NYSE+AMEX+NASDAQ universe.
- **Paywall'sız draft (May 2018):** Final yayım versiyonu (varsa) farklı tablo
  numaraları taşıyabilir; wiki [s.X] atıfları May 2018 draft'a referansla.

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfalar
- [[Asset_Growth]] — total asset growth factor entity (CGS 2008 origin
  measure, modern revisit referansla)
- [[asset_growth_anomaly]] — concept sayfası (Sloan accruals_anomaly'ye
  paralel; mekanizma adayları: investment-q vs mispricing vs hybrid)

### Bu paperın update ettiği mevcut sayfalar (challenged-by işaretleriyle)
- [[CMA]] — empirical origin işareti CGS 2008 + ⚠️ challenged note
  ("investment proxy" yorumu sorgulandı)
- [[famafrench2015_five_factor]] — CMA empirical temeli + ⚠️ challenged note
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 I/A empirical temeli +
  ⚠️ challenged note
- [[F_Score]], [[G_Score]] — ilgili listesinde Asset_Growth + asset_growth_anomaly
  link (bileşen-seviyesinde origin işareti yok; G7 yön farkı notu)
- [[concepts/factor_zoo]] — investment cluster + Cochrane #2 cevabı
- [[concepts/earnings_quality]] — investment-related accruals boyutu
- [[sloan1996_accruals_anomaly]] — Sloan accruals ↔ asset growth korelasyonu
  (Fairfield-Whisenant-Yohn 2003 placeholder)

### İlgili paperlar (ingested)
- [[famafrench2015_five_factor]] — CMA factor; bu paperın eleştirisinin ana
  hedefi
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 model I/A factor; aynı
  eleştiri
- [[sloan1996_accruals_anomaly]] — accruals literature; asset growth ile
  yapısal yakın
- [[cochrane2011_discount_rates]] — investment-q çerçevesinin felsefi temeli
- [[mclean_pontiff_2016_post_publication_decay]] — 82 anomaly aggregate
  post-pub decay %35; CGS asset growth (2008 origin) reference list'inde
  explicit listed değil ama "accounting-related sorts" olarak Cochrane
  taksonomisi içinde aggregate'a dahil. CGS-Ion 2018 sample 1968-2016
  zaten post-publication dönem (CGS 2008 yayım sonrası 13 yıl) içerir;
  modern revisit'in asset growth anomaly'i hayatta bulması aggregate
  decay'in **anomaly-spesifik survival** açısından **zayıflamamış** bir
  örneğidir → wiki ingested anomaly'leri arasında sample-uzatma
  robustness'ı için relatif güçlü kanıt.

### Cycle 12 ek (HLZ 2016 ingested)
- [[harvey_liu_zhu_2016_multiple_testing]] — CGS asset growth (CGS 2008
  origin) HLZ Şekil 3 mark'inde **explicit listed değil**, ama HLZ
  Tablo 1 "Accounting Individual" kategorisi 87 factor içinde aggregate
  framework'e dahil; 1968-2016 sample alpha analizleri sig — multiple-
  testing-corrected sig yaklaşık (CGS 2008 published t-statistic
  ~10+ literatür konvansiyonu üzerinden). CMA factor model bileşeni
  HLZ Şekil 3 mark'inde yok ama FF15 paper'ında t=4.07 (2x3) sig her
  cutoff. Asset growth anomaly multi-testing düzeyinde sağlam.

### Cycle 15 ek (Lev-Sougiannis 1996 ingested) — intangibles methodology paralelliği
- [[lev_sougiannis_1996_rd_capitalization]] — CGS-Ion 2018 [s.5-6]
  Peters-Taylor 2017 (Cycle 16'da ingest edildi) total intangible
  capital metodu kullanıyor; Lev-Sougiannis **R&D-only basic
  methodology** seviyesi paralel. CGS-Ion'un "intangibles düzeltmesi
  yapılsa bile asset growth unique" bulgusu Lev-Sougiannis seviyesinde
  de uygulanabilir (mantıksal extension): R&D capital eklenmiş
  adjusted asset growth measure'ı ile traditional asset growth factor
  bağımsız sinyal verir mi paperdan tek-tek teyit edilemedi (CGS-Ion
  Peters-Taylor metodu kullanıyor). Detay
  [[concepts/intangibles_adjusted_accounting]] F bloğu anchor concept.

### Cycle 16 ek (Peters-Taylor 2017 ingested) — explicit cross-reference
- [[peters_taylor_2017_intangible_capital]] — CGS-Ion 2018 [s.5-6]
  paperin **dörtlü total capital methodology'sini explicit kullanıyor**:
  Peters-Taylor (2017) total intangible capital (knowledge + organization
  + external) metodu CGS-Ion alternative investment measures'ında dahil.
  - **CGS-Ion findings [s.3-4]**: HXZ + traditional CGS asset growth =
    5/35 unexplained; CAPX/PPE/total-capital ile değiştirildiğinde
    15-24/35 unexplained → asset growth measure unique
  - **Peters-Taylor methodology kontekstinde**: Total intangible capital
    dahil edildiğinde **HXZ 23/35 unexplained** [s.5-6] — intangibles
    düzeltmesi anomaly açıklayıcı gücünü **GÜÇLENDİRMİYOR** (sürpriz
    bulgu)
  - **NDX strateji implikasyonu**: Peters-Taylor methodology naive
    uygulamak yerine **CGS asset growth measure baseline** + horse
    race testleri gerekir; intangibles-aware versiyonun ek alpha
    üretmediği CGS-Ion ile gösterilmiş
  - Peters-Taylor methodology'sinin direct return prediction yapmadığı
    not edilir — Peters-Taylor q theory test eden corporate finance
    paper; CGS-Ion ise Peters-Taylor'ı **methodology aracı** olarak
    asset growth anomaly açıklayıcı gücünde test ediyor

### Cycle 13 ek (HXZ 2020 ingested)
- [[hou_xue_zhang_2020_replicating_anomalies]] — Cooper-Gulen-Schill
  (2008) asset growth paperin abstract'ında **explicit listed**
  significant [s.5] ("Cooper-Gulen-Schill (2008) asset growth"); HXZ
  replicate ediyor (smaller magnitude than originally reported).
  Investment kategorisinde 38 anomaly içinde 27 sig (%71 — momentum
  + investment en yüksek replication rate'leri). CMA factor q-factor
  lens'inde span ediliyor (klasik 0.34% sig + q-factor alpha 0.01%
  insig). Asset growth anomaly **dört darbenin tümünde** hayatta
  (in-sample CGS-Ion 2018 sample uzatma 1968-2016 + post-pub aggregate-
  altı + MT sig + HXZ replicate). Detay
  [[concepts/anomaly_replication]] aggregate tablosu;
  [[concepts/post_publication_decay]] dört darbe çerçevesi tablosu.

### Henüz wiki'de olmayan, doğrudan ilgili paperlar
- Cooper-Gulen-Schill (2008) "Asset Growth and the Cross-Section of Stock
  Returns" (JF) — **original paper, paywall, wiki'de yok**
- Hou-Xue-Zhang (2015) "Digesting Anomalies" (Tier 1 #3) — q-factor model origin
- Lyandres-Sun-Zhang (2008) — q-theory of investment, asset growth rational
  yorum (Tier listesinde değil)
- Fairfield-Whisenant-Yohn (2003) — accrual + growth ayrımı (Tier 2 #37)
- Eisfeldt-Papanikolaou (2013) — organization capital factor portfolio
  direct evidence (Tier 2 #28; Q41 horse race için)

### İngest edildi (cross-reference)
- [[lev_sougiannis_1996_rd_capitalization]] — R&D-only intangibles methodology
- [[peters_taylor_2017_intangible_capital]] — total intangibles methodology
  (CGS-Ion'un explicit kullandığı paper; Cycle 16 ingest)

## Çelişkiler / Tartışmalar

> ⚠️ **CMA "investment proxy" yorumu vs CGS-Ion findings:**
> - **Önceki wiki sentezi (Cycle 5'te FF15 ingestiyle):** CMA = aggregate
>   asset-growth-based investment factor; geleneksel yatırım ölçüleriyle
>   (capex, debt issuance) değiştirilebilir alternatif yorumu mümkün.
> - **Bu paper [Tablo (paperdan teyit), s.3-4]:** CAPX/PPE/total-capital ile
>   değiştirildiğinde HXZ unexplained anomaly 5 → 15-24'e çıkıyor; CMA
>   getirisinin büyük kısmı **asset growth'un yapısal yapısından** geliyor.
> - **Resolution:** open. Asset growth'un *neden* unique olduğu paper
>   tarafından cevaplanmıyor. Wiki taraf tutmaz; CMA factor exposure
>   uygulamasında **CGS 2008 asset growth ölçüsü** kullanılmalı (alternatif
>   measures naif).

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q5 partial-stronger update]** Post-publication decay: CGS-Ion 2018 sample
  1968-2016 (CGS 2008 sample 1968-2003'ün 13 yıl uzatılmışı). Asset growth
  anomaly hayatta — sample uzatma sonrası anlamlı; ama spesifik decay rakamları
  paperdan teyit edilmeli (paperın main odağı decay değil model sensitivity).
  McLean-Pontiff 2016 ([[mclean_pontiff_2016_post_publication_decay]])
  aggregate %35 decay baseline'ına göre asset growth anomaly **görece
  güçlü survival** gösteriyor — sample uzatma sonrası HXZ q-factor
  yapısı asset growth'a kritik bağlı kalmaya devam ediyor. Aggregate-altı
  bir survival rate, anomaly'nin "saf statistical bias" açıklamasını
  empirik olarak zayıflatır (sample-end opportunism reddi
  [[mclean_pontiff_2016_post_publication_decay]] [Tablo 4] ile uyumlu).
  Detay: [[post_publication_decay]] decay-adjusted spread tablosu.
- **[Q26 partial-stronger update]** Tech firma intangibles: CGS-Ion 2018
  intangibles düzeltmesinin (Peters-Taylor 2017) **performans düşürdüğünü**
  raporluyor. Yani NDX tech-heavy evrene transfer için "intangibles düzelt"
  yaklaşımı naif olabilir; tech firma asset growth ölçümü için **yeni
  metodoloji** gerekli — Lev-Sougiannis 1996 alternatif kapitalizasyon
  literatürü açık soru.
- **[Yeni Q27]** Investment-q reaction (Cochrane 1991, Lyandres-Sun-Zhang 2008)
  vs CGS mispricing yorumu: Asset growth anomaly'nin mekanizması rational
  q-theory ile açıklanır mı, yoksa Lakonishok-Shleifer-Vishny tarzı mispricing
  mi? CGS-Ion 2018 q-factor model'in açıklayıcı gücünü sorguluyor — mispricing
  yorumuna ek kanıt sağlıyor olabilir, ama paper explicit mekanizma testi
  yapmıyor. Lyandres-Sun-Zhang 2008 (Tier listesinde değil) ve Hou-Xue-Zhang
  2015 ingestleri ile cevap.

---
type: concept
name: asset_growth_anomaly
related_papers: [[cooper_gulen_ion2018_asset_growth_factor_models]]
---

# Asset Growth Anomaly — Yüksek-Asset-Growth Firmaları'nın Düşük Beklenen Getirisi

> 📝 [[accruals_anomaly]] sayfasına paralel yapı; mekanizma sorusu açık,
> ortodoks rational yorumlar (Cochrane investment-q) ve davranışsal
> mispricing yorumları yan yana.

## Tanım

**Asset growth anomaly:** Yüksek total-asset-growth firmaları gelecekte
sistematik düşük getiri, düşük-growth firmaları sistematik yüksek getiri
üretiyor. **Origin:** Cooper-Gulen-Schill (2008) "Asset Growth and the
Cross-Section of Stock Returns" (paywall, wiki'de yok). **Modern revisit
ve kanonik wiki referansı:** [[cooper_gulen_ion2018_asset_growth_factor_models]].

```
Asset Growth_t = (Total Assets_t − Total Assets_{t-1}) / Total Assets_{t-1}
```

Decile sort + hedge return: long bottom-decile + short top-decile.

## Mekanizma adayları (3)

### 1. Investment-q reaction (rational)

**Cochrane (1991) investment-q model çerçevesi.** Firma değeri = bugünkü
kapitalin getiri × marjinal q. Yüksek asset growth → marjinal q düşüyor →
gelecek beklenen getiri düşüyor. **Rational risk premium yorumu.**

- Lyandres-Sun-Zhang (2008) bu hipotezi q-theory of investment çerçevesinde
  formalize eder (henüz wiki'de yok)
- Hou-Xue-Zhang (2015) q-factor model investment factor'ünü bu çerçeveden
  motive eder

### 2. Capital allocation efficiency (mispricing)

**Lakonishok-Shleifer-Vishny (1994) tarzı extrapolation.** Yüksek-asset-growth
firmaları over-investing; piyasa bunu fark etmiyor; over-investment'in
verim düşürmesi gelecek dönemlerde fiyatlanıyor → underperformance.

- Cooper-Gulen-Schill (2008) original paper bu yorumu öneriyor (paywall
  sebebiyle wiki'de doğrulanmadı)
- Sloan accruals anomalisinin "investor fixation" mekanizmasıyla yapısal
  benzerlik

### 3. Investor inattention / sürdürülemezlik fixation

**Davranışsal:** Yatırımcılar asset büyümesinin sürdürülemez olduğunu fark
etmiyor; Sloan'ın "earnings fixation"ına paralel "growth fixation".

## CGS-Ion 2018'in spesifik bulgusu

> ⚠️ **Önemli mekanizma sorusu:** [[cooper_gulen_ion2018_asset_growth_factor_models]]
> [s.3-4] geleneksel investment measures (CAPX, PPE, intangibles-adjusted
> total capital) ile asset growth'u **reproduce edemediğini** gösteriyor.
> Bu, "asset growth = pure investment proxy" yorumunu sorgular.
>
> **Eğer asset growth saf rational investment-q reaction olsaydı**, CAPX
> veya PPE ile reproduce edilebilmesi beklenirdi. Reproduce edilememesi
> şunlardan birini ima edebilir:
>
> 1. **Asset growth working capital bileşenini içerir** — Sloan accruals'la
>    overlap → mispricing channel
> 2. **Acquisitions / non-organic growth bileşeni** — capital allocation
>    sinyali
> 3. **Off-balance-sheet veya other assets** bileşeni
>
> Mekanizma belirsiz; literature dalları (Lyandres-Sun-Zhang, Lev-Sougiannis,
> Fairfield-Whisenant-Yohn) ileri ingestlerle aydınlanacak. Wiki taraf
> tutmaz; pratik strateji tasarımı her iki yorumda da aynı portföye götürür
> (long düşük-asset-growth + short yüksek-asset-growth).

## Sloan accruals_anomaly ile ilişkisi

```
Total Accruals (Sloan) = Working capital changes + LT operating accruals
Asset Growth (CGS) = Δ(cash + noncash CA + PPE + other assets) / Assets
```

**Overlap:**
- Working capital changes hem Sloan accruals'ın hem CGS asset growth'un
  bileşeni
- İki signal'in korelasyonu yüksek olabilir; iki anomaly'i ayrı ayrı
  kullanmak partial redundancy

**Decompose:** Fairfield-Whisenant-Yohn (2003) (Tier 2 #37, wiki'de yok)
accrual + growth ayrımı; "long-term operating accruals" vs "current accruals
+ working capital growth" ayrımı yapar.

## Modern asset pricing ile ilişkisi

- **[[CMA]]** (FF15 investment factor) = aggregate version of Asset Growth
- **HXZ q-factor I/A factor** = aynı asset growth measure
- **Empirik bulgu [[cooper_gulen_ion2018_asset_growth_factor_models]]:**
  HXZ ve FF5 modellerinin investment factor performansı CGS asset growth
  ölçüsüne kritik bağlı. Alternatif investment ölçüleri (CAPX, PPE,
  intangibles-adjusted) ile değiştirildiğinde 35 anomaly'den **5/35 → 15-24/35**
  açıklanamayan anomaly.

## Bu wiki'nin strateji tasarımına spesifik implikasyon

- **CMA factor exposure** strateji tasarımının doğal bileşeni; Faz 3'te
  asset growth ölçüsü olarak **CGS measure'ı** kullanılmalı (CAPX/PPE
  alternatif naif).
- **Tech firma asset growth ölçümü problemli:** Q26 paralel açık soru;
  intangibles düzeltmesi (Peters-Taylor 2017) anomaly'i **güçlendirmiyor**
  [[cooper_gulen_ion2018_asset_growth_factor_models]] [s.5-6]. NDX evrene
  transfer için yeni metodoloji araştırılmalı (Lev-Sougiannis 1996 alternatif
  capitalization).
- **Sloan accruals'ı korelasyon riski:** Faz 3 strateji tasarımında accruals
  + asset growth ikisini birlikte kullanmak — partial redundancy. F-Score
  F_ACCRUAL ve potansiyel asset-growth screen birlikte kullanılırsa
  Fairfield-Whisenant-Yohn 2003 decomposition önerilir.

## İlgili paperlar (ingested)

- [[cooper_gulen_ion2018_asset_growth_factor_models]] — modern revisit + q-factor/FF5 sensitivity testi
- [[famafrench2015_five_factor]] — CMA factor formal tanımı
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 I/A factor; security analysis stratejilerinde uygulama
- [[sloan1996_accruals_anomaly]] — accruals anomaly yapısal yakın
- [[cochrane2011_discount_rates]] — investment CAPM çerçevesi (epistemik temel)

## İlgili paperlar (henüz ingest edilmedi)

- Cooper-Gulen-Schill (2008) "Asset Growth and the Cross-Section of Stock
  Returns" — **original paper, paywall**
- Hou-Xue-Zhang (2015) "Digesting Anomalies" (Tier 1 #3) — q-factor model origin
- Lyandres-Sun-Zhang (2008) — q-theory of investment, asset growth rational
  yorum (Tier listesinde değil)
- Titman-Wei-Xie (2004) "Capital Investments and Stock Returns" (Tier 2 #38)
- Fairfield-Whisenant-Yohn (2003) — accrual + growth ayrımı (Tier 2 #37)
- Peters-Taylor (2017) — intangible capital + investment-q (Tier 2 #27)

## İlgili kavramlar

- [[accruals_anomaly]] — yapısal paralel anomaly; working capital bileşeni
  overlap
- [[earnings_quality]] — investment-related accruals boyutu
- [[fundamental_scoring]] — investment-side composite skorlamada bileşen
- [[contextual_fundamental_analysis]] — yön farkı (G7 long-high capex vs CGS
  long-low asset growth) bu kavramın somut örneği
- [[factor_zoo]] — investment cluster (CMA / I-A / Asset Growth aynı yapı)
- [[discount_rates]] — investment-q rational yorumun çerçevesi

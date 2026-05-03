---
type: concept
name: discount_rates
related_papers: [[cochrane2011_discount_rates]], [[famafrench1993_three_factor]]
---

# Discount Rates — Beklenen Getirilerin Zaman Serisi ve Kesit Varyasyonu

## Tanım

**Discount rate** ≡ **expected return** ≡ **risk premium** [[cochrane2011_discount_rates]] s.1.
Bir fiyat-cashflow özdeşliğinde fiyatın değişme nedeni iki kaynaktan gelir:

`P_t = E_t[ Σ M_{t,t+j} · D_{t+j} ]`

P_t değişiyor → ya **E_t[D]** (beklenen cashflow) değişiyor, ya **discount rate**
değişiyor, ya ikisi.

> 📝 1970'lerin asset-pricing tezi (Fama 1970) "fiyatlar bekleneni yansıtır" idi;
> yani **E_t[D] varyasyonu fiyat varyasyonunu açıklar**. [[cochrane2011_discount_rates]]
> 2011 itibarıyla bunun tersini söyler: P/D oranı varyasyonunun **neredeyse tamamı**
> discount rate varyasyonu ile açıklanır [Tablo II, s.2].

## Time-series ve cross-section yansımaları

### Time-series

Campbell-Shiller (1988) present-value identity (yaklaşık):

`dp_t ≈ Σ ρ^(j-1) [r_{t+j} − Δd_{t+j}]`

Burada `dp = log(D/P)`, `r = log return`, `Δd = log dividend growth`, `ρ ≈ 0.96`.

Long-run regression coefficient identity [[cochrane2011_discount_rates]] [Tablo II,
s.2]:

`1 ≈ b_r(k) − b_d(k) + b_dp(k)`

Cochrane'in kanıtı (CRSP value-weighted, 1947-2009): `b_d ≈ 0` → P/D varyasyonunun
**tamamı** beklenen-getiri (discount rate) varyasyonuna gider.

### Cross-section

Discount rate cross-section'da **expected return spreads** olarak görünür. Örnek:
[[famafrench1993_three_factor]] HML tek-faktör spread'i ortalamada 0.40%/ay. Bu,
**book-to-market faktörünün discount rate spread'idir.**

[[cochrane2011_discount_rates]] [s.12] yorumu: "**absence of beta is really the
heart of the value puzzle**" — yani discount rate spread'i **var**, ama tek-faktör
beta ile açıklanmıyor (CAPM başarısızlığı).

## Bu wiki'nin strateji tasarımına spesifik implikasyonu

- **Wiki'nin amacı discount rate "alma"sıdır** — yani sistematik faktör exposure'u
  ile pozitif beklenen-getiri kaynağı yakalamak. Bu, "discount rate çerçevesi
  içinde" çalışmak demek.
- Strateji bir faktöre uzun pozisyon aldığında, o faktörün **discount rate
  spread'inin standalone primum'unu** hedefler. Bu primum'un *neden* var olduğu
  (rational risk premium mu, mispricing mi) — bu wiki'nin scope'u **dışı**dır
  (Cochrane #4).
- **Time-series implications:** Eğer discount rate'ler değişiyorsa, **strateji
  performansı zamanla değişir**; "this time is different" değil, expected-return
  varyasyonu bekleniyor. Bu, value premium'un 2010-2020 yıllarındaki çöküşünü
  veya momentum crashes'ı *normal* kılar (Lev-Srivastava 2020,
  Daniel-Moskowitz 2016 ingestleri ile destek bekleniyor).

## İlgili paperlar

- [[cochrane2011_discount_rates]] — kavramın bu wiki için kanonik kaynağı
- [[famafrench1993_three_factor]] — cross-section discount rate spread'inin
  empirik formülasyonu (HML, SMB)
- [[famafrench2015_five_factor]] — discount rate spread'in kaynaklarının
  genişletilmesi (RMW, CMA)

## İlgili kavramlar

- [[expected_returns_vs_cash_flows]] — present-value decomposition
- [[factor_zoo]] — discount rate spread'lerinin potansiyel kaynaklarının çokluğu
- [[factor_model]] — discount rate spread'inin parametrik açıklama yapısı

---
type: paper
authors: [Lev, Baruch, Sougiannis, Theodore]
year: 1996
title: "The Capitalization, Amortization, and Value-Relevance of R&D"
venue: "Journal of Accounting and Economics 21 (1), 107-138 (March 1993 received, April 1995 final)"
url: https://www.sciencedirect.com/science/article/abs/pii/0165410195004106
local_path: raw/papers/lev_sougiannis_1996_rd_capitalization.pdf
ingested: 2026-05-01
tags: [intangibles, R&D_capitalization, amortization, value_relevance, mispricing, NDX_kritik, F_blok_1, Faz_1_finalizasyon]
status: ingested
---

# Lev & Sougiannis (1996) — R&D Capitalization

> 📝 **Atıf konvansiyonu:** `[Tablo N]` numaralı tablolar; `[s. X]`
> JAE 1996 yayın sayfa numarası (pp.107-138). Embedded text extract:
> `raw/papers/lev_sougiannis_1996_rd_capitalization.txt`. Paper-iç sayfa
> numaraları yayın pp.107-138 ile uyumlu.

> 📝 **F bloğu (intangibles) #1** — Faz 1 finalizasyon Cycle 15.
> Wiki'nin Cycle 9-14 boyunca tekrarlanan "intangibles methodology
> eksikliği" data_gaps boşluğunu **kısmen kapatır**; **Cycle 16'da
> Peters-Taylor 2017 ingest'iyle total intangible capital generalization
> tamamlandı** (R&D + organization + external); **Cycle 17'de
> Lev-Srivastava 2020 ingest'iyle F bloğu KAPANDI** (post-2010 value
> crisis application). NDX strateji için **yapısal foundation**
> paper'ı.

> 📝 **Yazar continuity (Cycle 17 ek)**: Baruch Lev (NYU Stern) bu
> paperin co-author + [[lev_srivastava_2020_value_failure]] (F bloğu
> kapanış paper) baş yazarı — **24 yıl arayla aynı R&D capitalization
> methodology**'sini value strategy crisis context'inde uyguluyor.
> Origin attribution literature continuity: Lev'in F bloğu hattı
> 1996 → 2020 (24 yıl) wiki için methodology hub.

> 📝 **Peters-Taylor 2017 [s.10] explicit citation:** "A large R&D
> literature (e.g., Lev and Sougiannis, 1996) shows that R&D
> investments increase firms' future profits." Peters-Taylor methodology
> Lev-Sougiannis'in **strict generalization'ı**: aynı perpetual
> inventory + industry-specific δ paradigm; R&D-only kapsam → R&D +
> organization + external kapsam.

## TL;DR

GAAP **R&D'yi tam giderleştirmeyi zorunlu kılar** (FAS No. 2, 1974);
Lev-Sougiannis bu standart'ın value-relevance açısından sorgulanması
gerektiğini empirik olarak gösteriyor. **Sample: 1975-1991, ~2600
manufacturing firm** (NBER R&D Master File), 6 endüstri (Chemicals/
Pharma 28, Machinery/Computer Hardware 35, Electrical/Electronics 36,
Transportation Vehicles 37, Scientific Instruments 38, Other R&D
Industries).

**Methodology [Eq. 4, s.111]:** Operating income / sales = f(tangible
assets, lagged R&D expenditures, advertising) — instrumental variable
(industry-average R&D, 4-digit SIC) + Almon lag procedure (multicolinearity
düzeltme). Industry-spesifik amortization rates δ_k hesaplanır, firm-level
R&D capital ve adjusted earnings/book values üretilir.

**Üç ana finding:**

1. **R&D capital + amortization rate estimation statistically reliable
   + economically meaningful** [Tablo 3, s.121]:
   - Industry-spesifik R&D useful life: **Chemicals/Pharma 9 yıl**
     (en uzun) → **Scientific Instruments 5 yıl** (en kısa)
   - Annual internal rate of return on $1 R&D investment (operating
     income terms): Pharma **28%**, Electrical 22%, Scientific
     Instruments 20%, Other 20%, Transportation 19%, Machinery 15%
   - FAS No. 2 premise ("a direct relationship between R&D and
     subsequent benefits has not been demonstrated") empirik olarak
     **REDDEDİLDİ**

2. **R&D-adjusted earnings + book values value-relevant** [Tablo 4,
   s.126]:
   - Cross-sectional regression: stock price/return ↔ R&D-adjusted
     financials
   - Earnings misstatement coefficient (X^c - X^a) **2.030 (t=4.14)**
     — reported earnings coefficient 1.114'ün **2x kadar büyük**
   - Price model R&D capital coefficient (BV^c - BV^a) = R&D capital
     **2.368 (t=16.11)** sig
   - R&D-yoğun firmalarda (upper quartile RDC/BV) coefficient'lar
     daha güçlü

3. ⭐ **R&D capital → subsequent stock returns sig** [Tablo 5, s.132,
   intertemporal Fama-French 1992 framework]:
   - Total sample: RDC/M coefficient **0.0015 (t=3.10)** sig 1% level
   - Upper quartile (R&D-intensive firms): RDC/M coefficient
     **0.0114 (t=3.88)** sig — total sample'ın **8x katı**
   - **Annual return implication: 4.57%** (mean RDC/M = 0.327; monthly
     0.0114 × 12 → ≈4.57%)
   - **Yorum açık** [s.134]: "systematic mispricing of R&D-intensive
     firms (underreaction) **OR** extra-market risk factor associated
     with R&D capital"

**Survivorship bias kontrolü** [s.128-129]: Jensen alpha α = -0.0003
(t=-0.25) **insig** — survivorship bias yok.

**Earnings ve book value adjustments büyüklüğü [s.123]:**
- Average earnings understatement (R&D expensing nedeniyle): **20.55%**
  (range Electrical 26.8% en yüksek → Other 9.7% en düşük)
- Average book value understatement (R&D capital eksikliği): **22.2%**
  (range Scientific Instruments + Computer Hardware 24.6% en yüksek →
  Other 12.3% en düşük)

## Tek Cümle Tezi

R&D firm-level capitalize edildiğinde (industry-spesifik amortization
patterns ile), adjusted earnings ve book values stock prices/returns'la
istatistiksel olarak güçlü association gösterir; üstelik R&D capital
**subsequent stock returns'i sig predict eder** (RDC-yoğun firmalarda
~4.57% yıllık), suggesting mispricing OR extra-market risk premium
ilişkili intangible assets.

## Ortaya Konan Sinyal/Faktör

**Yeni empirik faktör YOK** (Cycle 15 plan onayı: factor entity
açılmaz). Paper bir **methodology paper** — R&D capitalization
formülasyonu sunar; factor selection değil, accounting adjustment
methodology.

Wiki'de bu paperdan **bir concept sayfası açıldı:**

- [[concepts/intangibles_adjusted_accounting]] — F bloğu anchor
  concept; Lev-Sougiannis 1996 origin + Peters-Taylor 2017 (Cycle
  16 bekliyor) + Lev-Srivastava 2020 (Cycle 17 bekliyor) ortak
  referans noktası; HML/Bm + Sloan accruals + asset growth factor
  intangibles-aware revision'larının hub'ı

> 📝 **Paper'ın factor-level dolaylı katkıları wiki'de mevcut:**
> - [[G_Score]] G6 (R&D / Assets) — Mohanram 2005 conservatism
>   yorumu + Lev-Sougiannis 1996 literatür hattı kökü (dual origin
>   attribution)
> - [[hou_xue_zhang_2020_replicating_anomalies]] R&D-to-market (Rdm)
>   factor (q-factor alpha sig dört darbe 4/4) — methodology temeli
>   Lev-Sougiannis amortization patterns
> - [[CMA]], [[Asset_Growth]] — intangibles-adjusted book equity
>   ile alternatif inşa cross-link

## Metodoloji

### Estimation framework [Eq. 4, s.111]

```
(OI/S)_it = α_0 + α_1 (TA/S)_{i,t-1} +
             Σ_k α_{2,k} (RD/S)_{i,t-k} +
             α_3 (AD/S)_{i,t-1} + ε_it
```

Burada:
- `OI` = operating income (before depreciation, R&D, advertising)
- `S` = sales
- `TA` = tangible assets (plant+equipment+inventory+investments)
- `RD` = annual R&D expenditures (current dollars)
- `AD` = advertising expenses
- `α_{2,k}` = lag k R&D'nin operating income'a katkısı (amortization
  profile coefficients)

### Instrumental variable: industry R&D [Eq. 4a, s.115]

Endogeneity problemi: shock simultaneous'ı operating income + R&D'yi
korele eder (high return → more R&D investment). Çözüm: 4-digit SIC
industry-average R&D (firm-spesifik shock'a immune) instrumental
variable; two-stage least squares.

### Almon lag procedure

Multicolinearity (yıllık R&D expenditures stable over time) → Almon
polynomial lag procedure ile lag coefficient'leri estimate; fewer
parameters than lags k.

### Industry-spesifik amortization rates [Tablo 3, s.121]

Yearly cross-sectional regressions 1975-1990 (16 yıl), 6 industry için:

| Endüstri (SIC) | δ_0 | δ_1 | δ_2 | δ_3 | δ_4 | δ_5 | δ_6 | δ_7 | δ_8 | Useful life | Σα_{2,k} | Annual IRR |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **Chemicals & Pharmaceutics (28)** | 0.082 | 0.133 | 0.158 | 0.161 | 0.147 | 0.121 | 0.086 | 0.060 | 0.052 | **9 yıl** | 2.628 | **28%** |
| **Machinery & Computer Hardware (35)** | 0.106 | 0.168 | 0.192 | 0.186 | 0.157 | 0.115 | 0.076 | — | — | ~7 yıl | 1.663 | 15% |
| **Electrical & Electronics (36)** | 0.114 | 0.176 | 0.196 | 0.183 | 0.146 | 0.095 | 0.050 | 0.040 | — | ~8 yıl | 1.968 | 22% |
| **Transportation Vehicles (37)** | 0.072 | 0.123 | 0.155 | 0.170 | 0.171 | 0.162 | 0.147 | — | — | ~7 yıl | 2.024 | 19% |
| **Scientific Instruments (38)** | 0.135 | 0.207 | 0.240 | 0.244 | 0.174 | — | — | — | — | **5 yıl** | 1.718 | 20% |
| **Other R&D Industries** | 0.110 | 0.176 | 0.205 | 0.205 | 0.177 | 0.127 | — | — | — | ~7 yıl | 1.832 | 20% |

> 📝 **Wiki için kritik tablo:** Industry-spesifik amortization rates
> Faz 3 NDX strategy spec'inde **methodology baseline** (Q38 wiki
> tasarım kararı için referans). NDX evren GICS sektör sınıflandırma
> 1996 SIC kodlarından farklı; Faz 3'te GICS-Level-2/3 mapping
> gerekecek (örn. NDX tech firmaları → SIC 35/36/38 hibrit).

### R&D capital hesaplama [Eq. 8, s.123]

```
RDC_it = Σ_{k=0}^{N} RD_{i,t-k} × (1 - Σ_{j=0}^{k} δ_j)
```

R&D capital = unamortized portion'ların kümülatif toplamı; useful
life N (industry-spesifik 5-9 yıl).

### R&D-adjusted earnings [Eq. 7, s.122]

```
X^c_it = X^a_it + RD_it - RA_it
```

Adjusted earnings = reported (GAAP) earnings + current R&D outlay −
R&D amortization (industry δ_k uygulanmış).

## Empirik Sonuçlar (sayılarla)

### Adjustments büyüklüğü [s.123]

**Earnings understatement** (X^c - X^a / X^a):
- Electrical & Electronics 26.8% (en yüksek)
- Other Industries 9.7% (en düşük)
- All-firm average: **20.55%**

**Book value understatement** (BV^c - BV^a / BV^a = RDC / BV^a):
- Scientific Instruments + Machinery/Computer Hardware 24.6% (en yüksek)
- Other Industries 12.3% (en düşük)
- All-firm average: **22.2%**

> 📝 Wiki için: bu rakamlar **NDX evren içeren tech-heavy firmalar
> için geleneksel HML/Bm + Sloan accruals'in yapısal bias büyüklüğü**.
> 22.2% book equity yapay düşük → B/M yapay yüksek (growth firma
> "value" gibi gözükebilir).

### Contemporaneous analysis [Tablo 4, s.126]

**Return regression (Eq. 11, all firms):**

| Variable | Coefficient | t-stat |
|---|---|---|
| Reported earnings (X^a) | 1.114 | 11.11 |
| **Earnings misstatement (X^c - X^a)** | **2.030** | **4.14** |
| Adj R² | 0.09 | |

**Return regression upper quartile RDC firms (R&D-yoğun):**
- X^a coefficient 1.197 (t=8.79) — total sample'a benzer
- Earnings misstatement coefficient **2.207 (t=5.68)** — total
  sample'dan büyük

**Price regression all firms:**
- Reported earnings coefficient 6.240 (t=11.28)
- Earnings misstatement coefficient 10.612 (t=14.37)
- Adj R² 0.44

**Price regression with R&D capital:**
- Reported earnings 5.193 (t=8.25)
- **R&D capital (BV^c - BV^a) coefficient 2.368 (t=16.11)** — sig 1%
- Adj R² 0.46

Yorum: R&D-adjusted financials reported financials'tan **daha güçlü
explanatory power** + R&D capital independent value-relevant.

### Intertemporal analysis — KRİTİK [Tablo 5, s.132]

Fama-French 1992 framework + RDC/M:

```
R_{i,t+j} = c_0 + c_1 β_it + c_2 ln(M)_it + c_3 ln(B/M)_it +
            c_4 ln(A/B)_it + c_5 (E^+/M)_it + c_6 (E/M dummy)_it +
            c_7 ln(RDC/M)_it + ε_{i,t+j}
```

180 cross-sectional regressions (15 yıl × 12 monthly) ortalamaları:

| Sample | RDC/M coefficient | t-stat | Implication |
|---|---|---|---|
| **Total sample (without R&D)** | n/a | n/a | FF92 replication; B/M sig (t≈3) |
| **Total sample (with RDC/M)** | **0.0015** | **3.10** | sig 1% |
| **Upper quartile RDC firms (without R&D)** | n/a | n/a | B/M sig coefficient 0.0043 |
| **Upper quartile RDC firms (with RDC/M)** | **0.0114** | **3.88** | sig 1%; total sample'ın 8x |

**Annual return implication:** Upper-quartile RDC firms için RDC/M
coefficient 0.0114 × mean RDC/M (0.327) × 12 (monthly→annual) ≈
**4.57% yıllık subsequent return**.

**Önemli yan bulgu:** Upper-quartile RDC firms'da **B/M coefficient
sig kaybediyor** (RDC/M dahil edilince) — RDC/M B/M'in açıklayıcı
gücünü absorb ediyor. Yani **R&D-yoğun firmalarda B/M yapay sinyal**;
gerçek value-relevance R&D capital'da.

### Survivorship bias kontrolü [Eq. 16, s.128-129]

CAPM-base Jensen alpha test:
```
R_RD,t - R_F,t = α + β(R_M,t - R_F,t) + ε_t
```

192 monthly observations (1976-1991):
- α = -0.0003 (t=-0.25) **insig**
- β = 0.842 (t=33.81)
- Adj R² = 0.86

Survivorship bias **yok** — sample'da bankrupt + merged firms dahil
(R&D Master File COMPUSTAT Research File içerir).

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Paper return prediction'a göre top-N selection değil, **value-relevance test** (Mishkin 1983 framework) + intertemporal anomaly (RDC/M sig coefficient). [Tablo 5] upper-quartile RDC firms 4.57% subsequent return implication — top-decile R&D-intensive long stratejisi indirect kanıt | ⚠️ dolaylı fit (factor selection methodology infrastructure) |
| **Annual rebalance** | Sample yıllık financial statements; intertemporal analysis 12-aylık return windows (6-ay disclosure lag + 12-ay return); annual rebalans natural fit. Industry δ_k yıllık güncellenir | ✅ doğrudan fit |
| **Large-cap evrene transfer** | Sample US R&D-intensive firms with R&D > 0 + R&D/Sales ≥ %2; large-cap-friendly ama explicit large-cap-only test yok. Industry sample size'lar 54-118 firms (Tablo 1) — moderate-to-large; mixed cap ama large-cap weighted (R&D yatırımı large firms'da daha yaygın) | ⚠️ paperdan teyit gerekli; large-cap-friendly beklenir ama kanıt indirect |
| **NDX intangibles / growth firms** | ⭐ **KRİTİK** — paperin ana mesajı NDX strateji için **yapısal temel**. Tech-heavy NDX evrende (FAANG dominant) geleneksel HML/Bm + Sloan accruals + CMA factor'leri yapay sinyal verir; Lev-Sougiannis methodology 22.2% book equity understatement düzeltmesi NDX-FAANG firms için kritik | ✅ explicit fit + KRITIK |

**Strateji tasarımına net implikasyon:**

1. **NDX strateji için yapısal foundation:** 22.2% average book equity
   understatement (R&D capital eksikliği) tech-heavy NDX evrende
   daha agresif. Lev-Sougiannis methodology FAANG-tipi firmaların
   yapay "growth" sınıflandırmasını düzeltir → growth-quality ayrımı
   netleşir. Faz 3 NDX strategy baseline ön koşulu.

2. **HML/Bm intangibles-aware versiyonu:** B/M ratio dispersion
   azalır; tech firmaların yapay düşük B/M'i düzeltilir. Wiki için
   [[HML]] sayfasında "intangibles-adjusted Bm" alternatif inşası
   not edilir.

3. **HXZ R&D-to-market dört darbe 4/4 methodology temeli:** HXZ 2020
   [s.28] R&D-to-market (Rdm) q-factor alpha sig sonucunun **methodology
   altyapısı Lev-Sougiannis amortization patterns**. Wiki'nin Faz 3
   NDX baseline aday'ı için origin paper.

4. **Sloan accruals tech firma bias mekanizması:** R&D giderleştirme
   working capital değişimi azaltır → traditional accruals "düşük
   accrual" gösterir (gerçekte capex-tipi yatırım). Q26 (tech firma
   accrual ölçümü) cevabı.

5. **CMA / Asset Growth intangibles-aware revision:** Adjusted book
   equity → adjusted asset growth. CGS-Ion 2018 Peters-Taylor 2017
   metodu ile "intangibles düzeltmesi yapılsa bile asset growth unique"
   bulgusu Lev-Sougiannis basic methodology seviyesinde de uygulanabilir.

6. **Industry-spesifik amortization Q38 wiki tasarım kararı:** NDX
   evrende GICS sektör mapping + Lev-Sougiannis 6-sektör amortization
   rates Faz 3 spec için ön koşul.

7. **R&D capital'ın subsequent return prediction'ı (4.57% yıllık)
   wiki'nin amaç metriği:** Paper headline R&D-intensive long-strategy
   indirect kanıtıdır; Faz 3 NDX strategy alpha component aday'ı.

## Bu paper'ın sürprizi

| Hipotez | Beklenti | Paper'da gerçek |
|---|---|---|
| **R&D capital value-relevant mi** | Paper iddia ediyor (FAS No. 2 reddi) | **DOĞRULANDI** — Tablo 4 R&D-adjusted financials reported'tan güçlü association |
| **Industry useful life range** | Genel 5-10 yıl beklenir | **5-9 yıl spesifik:** Pharma 9 yıl, Scientific Instruments 5 yıl — dramatic range; Mansfield 1986 + Levin 1987 patent appropriability hierarchy ile uyumlu |
| **R&D capital → subsequent return prediction** | Belirsiz hipotez | **SİG (4.57% yıllık RDC-yoğun firmalarda)** — paperin en sürprizli bulgusu; mispricing veya extra-market risk factor |
| **B/M coefficient RDC dahil edildiğinde** | Belirsiz hipotez | Upper-quartile RDC firms'da **B/M sig kaybediyor** — RDC/M B/M'in explanatory power'ını absorb ediyor; **B/M yapay sinyal R&D-intensive firms'da** |
| **Survivorship bias** | Risk olabilir | **Reddedildi** — Jensen alpha α=-0.0003 insig; R&D Master File bankrupt+merged firms dahil |
| **Earnings + book understatement büyüklüğü** | Anlamlı bekleniyor | **20.55% earnings + 22.2% book** — substantial; Electrical 26.8% en agresif tech-heavy |

**Sürpriz büyüklüğü:** YÜKSEK. **Üç sürprizli bulgu:**

1. **B/M intangibles-yoğun firmalarda yapay sinyal** — Tablo 5
   upper-quartile RDC firms'da B/M coefficient sig kaybı. Wiki için
   yapısal kanıt: NDX (FAANG-dominant) evrende geleneksel HML/Bm
   value premium **muhtemelen R&D capital'ın absorb edilmesinden
   kaynaklanan artifact'tır**.

2. **R&D capital → 4.57% yıllık subsequent return implication.** R&D-
   yoğun firms long-strategy indirect kanıt; Faz 3 NDX alpha
   component aday'ı.

3. **Industry useful life dramatic range (5-9 yıl)** — Pharma 9 yıl
   vs Scientific Instruments 5 yıl. Mansfield-Levin patent
   appropriability hierarchy ile uyumlu; sektör-spesifik kalibrasyon
   Faz 3 spec için kritik (Q38).

## Limitler ve Caveats

- **Sample sonu 1991:** Modern dönem (post-2000 FAANG, 2010-2024
  mega-cap tech) out-of-sample. Lev-Srivastava 2020 (Cycle 17) post-
  2010 value collapse'ı bu methodology üzerinden açıklayacak.

- **Sample manufacturing-only:** R&D Master File manufacturing odaklı
  (NBER convention). Modern hizmet sektörleri (software, financial
  services, biotech) muhtemelen kısmen kapsanmış (Computer Hardware
  35, Scientific Instruments 38) ama post-1996 software/internet
  patlaması paperin kapsamı dışında.

- **R&D-only methodology:** Sadece R&D capitalization; advertising
  + organization capital + brand value adresleyemiyor (advertising
  flow proxy olarak Eq. 4'te). Peters-Taylor 2017 (Cycle 16) total
  intangible capital ile genişletme.

- **Industry classification 4-digit SIC:** Modern GICS sınıflandırma
  ile mapping gerekli — NDX evrende GICS Level-3/4 mapping yapılmalı
  (Q38 Faz 3 tasarım kararı).

- **Mispricing vs extra-market risk yorumu açık [s.134]:** Paper iki
  alternative hipotezi disentangle etmiyor. Wiki taraf tutmaz; HXZ
  2020 R&D-to-market q-factor alpha sig (4/4) bulgusu **risk premium
  exposure** yorumuna eğilimli; ama mispricing tarafı LSV 1994 +
  contrarian literature ile uyumlu olabilir.

- **Jensen alpha CAPM-base, q-factor lens'inde test EDİLMEDİ:** Modern
  factor model lens'i (FF5, q5) ile sample-period spesifik alpha
  raporlanmamış. HXZ 2020 + HMXZ Security Analysis q-factor alpha
  paralel kanıt.

- **R&D growth rate dependency [s.123]:** R&D-adjusted ROE >
  reported ROE only when R&D growth rate sufficiently high. Yavaş-
  büyüyen R&D firms için adjusted ROE düşebilir (Merck 1991 örneği:
  R&D growth ~20% < earnings growth ~35% → adjusted ROE 0.40 vs
  reported 0.55). Faz 3 spec için kalibrasyon nüansı.

- **Linear amortization assumption:** Almon polynomial lag procedure
  parametrik; non-linear amortization patterns (örn. accelerated
  obsolescence yoğun-değişim sektörlerde) underfitting riski.

- **Multicolinearity regression-spesifik:** Industry instrumental
  variable + Almon lag güçlü methodology ama hala parametric
  varsayımlar; non-parametric alternatif (örn. Hall 1993 stock-market-
  based estimation) paper [s.110] kıyaslama olarak kullanılmış,
  benzer sonuçlar.

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfa
- [[concepts/intangibles_adjusted_accounting]] — F bloğu anchor
  concept; Lev-Sougiannis 1996 origin + Peters-Taylor 2017 (Cycle
  16 bekliyor) + Lev-Srivastava 2020 (Cycle 17 bekliyor)

### Bu paperın update ettiği mevcut sayfalar
- [[G_Score]] — G6 dual origin attribution: Mohanram 2005 conservatism
  yorumu (paper-spesifik origin) + **Lev-Sougiannis 1996 literatür
  hattı kökü** (R&D'nin earnings/value relevance teorik dayanak);
  Cycle 9 Sloan F_ACCRUAL/G3 origin pattern'inde
- [[mohanram2005_g_score]] — G6 R&D/Assets bileşeninin literatür
  kökü Lev-Sougiannis cross-link
- [[CMA]] — intangibles-adjusted book equity ile CMA aggregate
  asset growth measure alternatif inşa cross-link
- [[Asset_Growth]] — adjusted book equity ile asset growth measure
  revision; CGS-Ion 2018 + Peters-Taylor 2017 paralel
- [[hou_xue_zhang_2020_replicating_anomalies]] — R&D-to-market (Rdm)
  factor q-factor alpha sig 4/4 sonucunun **methodology temeli
  Lev-Sougiannis amortization patterns**; explicit cross-link
- [[concepts/earnings_quality]] — "intangibles-related accruals"
  boyutu Q26 mekanizma cevabı (Cycle 9-10 placeholder dolar)
- [[concepts/asset_growth_anomaly]] — adjusted asset growth measure
  intangibles-aware revision
- [[sloan1996_accruals_anomaly]] — R&D giderleştirme tech firma
  accrual bias mekanizması (Q26 partial cevap)
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — CGS-Ion 2018
  Peters-Taylor methodology + Lev-Sougiannis basic methodology
  uyum cross-link
- [[famafrench1993_three_factor]] + [[famafrench2015_five_factor]] —
  HML/Bm intangibles-aware versiyonu; B/M coefficient upper-quartile
  RDC firms'da sig kaybediyor (Tablo 5 bulgusu)

### İlgili paperlar (ingested)
- [[famafrench1993_three_factor]] / Fama-French 1992 — paper Section 6
  intertemporal analysis FF92 framework + RDC/M extension; B/M
  coefficient kaybı kritik bulgu
- [[mohanram2005_g_score]] — G6 R&D/Assets bileşeni Lev-Sougiannis
  literatür hattı kökünde; Mohanram conservatism yorumu paralel
- [[peters_taylor_2017_intangible_capital]] — **F bloğu #2 (Cycle 16)**;
  Lev-Sougiannis R&D-only methodology'sini total intangible capital'a
  genişletir (R&D + organization + external); Peters-Taylor [s.10]
  Lev-Sougiannis'i explicit cite ediyor (R&D investment future profits
  empirik kanıtı)
- [[lev_srivastava_2020_value_failure]] — **F bloğu #3 KAPANIŞ
  (Cycle 17)**; aynı yazar Baruch Lev 24 yıl sonraki güncelleme;
  R&D capitalization methodology'sini (1996 origin) post-2010 value
  crisis decomposition'da kullanıyor; adjusted BV methodology 39
  yılın 34'ünde conventional value strategy'i geçiyor; F bloğu 3
  ayak hierarchy tamamlandı
- [[eisfeldt_papanikolaou_2013_organization_capital]] — **Cycle 25
  yeni**; F bloğu **2. ayak / 4. katman (factor portfolio direct
  evidence)**; SG&A perpetual inventory (Lev-Sougiannis R&D perpetual
  inventory paterni paralel; aynı methodology farklı capital türü:
  Knowledge=R&D vs Organization=SG&A); δ=15% depreciation rate
  Lev-Sougiannis industry-spesifik (5-9 yıl) vs Eisfeldt-Papanikolaou
  default tek rate methodology farkı; Q59 yeni (Knowledge ↔
  Organization correlation orthogonality empirik test eksik); F bloğu
  Cycle 17 3-katmanlı kapatıldı, Cycle 25 ek 4. ayak ile 4-katmanlı
  hierarchy + methodology infrastructure (Lev-Sougiannis 1+3+4) +
  factor portfolio anchor (Eisfeldt-Papanikolaou 2) ayrımı
- [[hou_xue_zhang_2020_replicating_anomalies]] — R&D-to-market dört
  darbe 4/4 methodology temeli
- [[hou_mo_xue_zhang_2020_security_analysis]] — q-factor model
  intangibles düzeltmesi yok (Q23 wiki açık sorusu); Lev-Sougiannis
  + Peters-Taylor 2017 ile birlikte tam intangibles-aware q5
  versiyonu Faz 2'de
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — Peters-Taylor
  2017 metodu (Cycle 16) ile asset growth + intangibles relationship
- [[sloan1996_accruals_anomaly]] — R&D bias accrual hesabında

### Henüz wiki'de olmayan, doğrudan ilgili paperlar
- Lev-Srivastava (2020) "Explaining the Recent Failure of Value
  Investing" (Tier 2 #30) — **Cycle 17 ingest**; post-2010 value
  collapse
- Eisfeldt-Papanikolaou (2013) "Organization Capital and the Cross-
  Section of Expected Returns" (Tier 2 #28) — Faz 2'de seçici ingest
- Hirshleifer-Hsu-Li (2018) "Innovative Originality" (Tier 2 #29) —
  Faz 2'de seçici ingest
- Mishkin (1983) "A Rational Expectations Approach to Macroeconometrics"
  — value-relevance test methodology; paper Section 5 framework
- Hall, B. (1993a, 1993b) — R&D stock-market valuation
- Mansfield (1986), Levin et al. (1987) — patent appropriability
  hierarchy paper ile uyumlu

## Çelişkiler / Tartışmalar

> 📝 **Mispricing vs extra-market risk yorumu açık [s.134]:** Paper
> iki alternative hipotezi disentangle etmiyor. Wiki taraf tutmaz;
> mathematical equivalence (Cochrane 2011) çerçevesinde her iki
> yorum da R&D-aware factor inşası için aynı strateji çıktısını
> verir. **Çelişki olarak listelenmedi** — yorumsal çatallanma.

> 📝 **B/M coefficient kaybı (Tablo 5 upper-quartile RDC):** Lev-Sougiannis
> bulgusu HML factor'ünün R&D-yoğun firmalarda **yapay sinyal**
> olduğunu ima ediyor. Bu doğrudan FF92/93 HML factor'üyle çelişmiyor
> ama **modulates HML interpretation**: HML primum'unun bir kısmı
> (R&D-intensive sub-sample'da) intangibles factor'ün proxy'si.
> Wiki için: HML + RDC/M iki ayrı factor; combined kullanım double-
> counting riski.

> 📝 **HXZ R&D-to-market 4/4 hayatta kalan factor + Lev-Sougiannis
> mispricing yorumu:** HXZ 2020 R&D-to-market q-factor alpha sig
> sonucu paper'ın "extra-market risk factor" yorumuna **eğilimli**
> (q-factor risk premium exposure'u). Lev-Sougiannis "mispricing"
> yorumu LSV 1994 contrarian literature ile uyumlu olabilir; ikisi
> arasında empirik horse race wiki'de yok.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q23 partial-stronger update — Cycle 15+16]** NDX intangibles
  q-factor span: Lev-Sougiannis methodology partial cevap — paper
  q-factor model öncesi 1996, ama R&D capitalization methodology
  HXZ 2020 R&D-to-market q-factor alpha sig bulgusunun **altyapısı**.
  **Cycle 16 ek**: Peters-Taylor 2017 [Eq. 9] q^tot proxy total
  intangible capital'ı q ile entegre eder; Q23 partial-stronger ileri,
  tam Q23 cevabı için **modern q-factor + Peters-Taylor methodology
  entegrasyonu** yapan paper gerekli (wiki'de yok — Faz 2 aday).

- **[Q26 partial-stronger update — Cycle 15+16]** Tech firma accrual
  ölçümü R&D distortion: Lev-Sougiannis mekanizma cevabı —
  - R&D giderleştirme → working capital değişimi az → Sloan total
    accruals "düşük" görünür (gerçekte capex-tipi yatırım yapılıyor)
  - Lev-Sougiannis capitalize edilince R&D yatırımı accrual hesabına
    entegre edilir (capex paralel)
  - **Cycle 16 ek**: Peters-Taylor 2017 advertising + organization
    capital adjustment ekler; adjusted Sloan accruals = traditional +
    (RD - RA) + (advertising - RA_adv) + (SG&A_org - RA_org); Q26
    partial-stronger ileri, total intangibles methodology Q26 kapanışına
    yakın.

- **[Q1 partial-stronger update]** S&P 500 value post-2000:
  Lev-Sougiannis methodology adjusted Bm dispersion azaltır →
  traditional value premium R&D-yoğun firms'da yapay olabilir.
  Lev-Srivastava 2020 (Cycle 17) post-2010 value collapse'i bu
  methodology üzerinden açıklayacak.

### Yeni Q'lar (Q38, Q39):

- **[Yeni Q38]** Industry-spesifik R&D amortization patterns NDX evrende
  kalibrasyon: Lev-Sougiannis 6 sektör amortization rates (1975-1990
  data, 4-digit SIC). NDX evrende GICS sektör sınıflandırma + modern
  amortization rate kalibrasyonu Faz 3 spec için kararı:
  - GICS Level-2 / Level-3 / Level-4 mapping seçimi
  - SIC 28 → GICS Pharmaceuticals; SIC 35/36/38 → GICS Tech Hardware /
    Software hibrit
  - Modern data (Chen-Zimmermann 2022) ile rate güncelleme
  - Mohanram 2005 G6 industry-median methodology Lev-Sougiannis-aware
    versiyona genişletilmeli mi (Q19 sektör sınıflandırma ile bağlantılı)
  Faz 3 backtest spec açıldığında karar.

- **[Yeni Q39]** R&D capital stock vs flow ölçümü farkı: Lev-Sougiannis
  adjusted **stock** (kümülatif capitalized R&D, RDC formülü Eq. 8)
  hesaplar. HXZ 2020 R&D-to-market formülasyonu hangi versiyonu
  kullanıyor — current year R&D / market (flow) yoksa cumulative
  capitalized R&D / market (stock)? **Paper [s.133 footnote 22]
  explicit not:**
  > "we replaced [estimated R&D capital] with the sum of R&D outlays
  > in the current and the preceding two years. ... the estimated
  > RDC/M coefficient based on the sum of the recent three years
  > R&D is 0.0078 (t=3.01), while the RDC/M coefficient based on
  > the capitalization procedure is 0.114 (t=3.88). When we focus
  > on the firms in the top decile of the R&D capital-to-total assets
  > ratio, the difference is even more striking. The RDC/M coefficient
  > based on the three-year R&D is statistically insignificant
  > (0.0105, t=1.20), while that based on the capitalization
  > procedure is large and significant (0.0165, t=1.85)."
  Yani **proper capitalization (industry δ_k uygulanmış stock)
  3-yıl-flow-toplamı'ndan dramatic farklı**. NDX strategy spec'inde
  hangisi kullanılacak Q39 — wiki için Lev-Sougiannis methodology
  recommendation: proper capitalization stock.

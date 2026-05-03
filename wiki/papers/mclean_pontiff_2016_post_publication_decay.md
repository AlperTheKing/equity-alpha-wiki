---
type: paper
authors: [McLean, R. David, Pontiff, Jeffrey]
year: 2016
title: "Does Academic Research Destroy Stock Return Predictability?"
venue: "Journal of Finance 71 (1), 5-32 (working paper October 2012)"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2156623
local_path: raw/papers/mclean_pontiff_2016_does_research_destroy.pdf
ingested: 2026-04-28
tags: [post_publication_decay, replication, multiple_testing, limited_arbitrage, informed_trading, epistemic_backbone, Q5_anchor, D_blok_kalbi]
status: ingested
---

# McLean & Pontiff (2016) — Post-Publication Decay

> 📝 **Atıf konvansiyonu:** `[Tablo N]` numaralı tablolar; `[s. X]` working paper
> versiyonunun (Oct 23, 2012) iç sayfa numarası. Embedded text extract:
> `raw/papers/mclean_pontiff_2016_does_research_destroy.txt`. Yayınlanmış
> JF 2016 versiyonunun sayfa numaraları farklı; tablo numaraları aynı.

> 📝 **D bloğunun #1'i** — replication / decay / multiple testing. Wiki'nin
> **epistemik omurgasını** kuran paper. [[meta/open_questions]] (Q5) anchor referansı; A-B-C bloklarında
> ingest edilen tüm fundamental scoring + accruals + asset growth paperlarının
> **post-publication decay rakamı** bu paper üzerinden okunur.

## TL;DR

**82 anomaly, 68 farklı çalışma**, 1972-2011 arası akademik finans-muhasebe
dergilerinde rapor edilmiş cross-sectional return predictors. Random-effects
panel regresyonu (in-sample mean ile normalize edilmiş aylık portfolio
returnleri) iki coefficient tahmin eder: **out-of-sample (post-sample,
pre-publication)** ve **post-publication**. Headline (strongest form) [Tablo 3,
s.32]:

- **Out-of-sample decay (statistical bias proxy):** ≈ **10%** (-0.097, p=0.386)
  → istatistiksel olarak **0'dan farksız** (data-mining hipotezi reddediliyor)
- **Post-publication decay:** ≈ **35%** (-0.369, p<0.001) → istatistiksel olarak
  hem 0'dan hem -100%'den farklı (decay var ama *tam* yok)
- **Lower bound publication effect:** 35% − 10% = **≈25%**, sophisticated
  trader arbitrajına atfedilen kısım

İki yan kanıt mekanizmayı destekler:

1. **Informed trading [Tablo 6-7]:** Anomaly stocks'ta turnover, dollar volume,
   variance, short interest **post-sample VE post-publication artıyor**. Total
   change %9-22 — informed traders'in publication-aware olduğu somut izi.
2. **Limited arbitrage [Tablo 8]:** Post-publication decay **büyük cap, yüksek
   dollar volume, düşük idio risk, dividend-payer** firmalarda **DAHA güçlü**.
   Coefficients (anomaly-month decay regresyonu): Size +1.442, Dollar Vol
   +1.380, Idio Risk -1.420, Divid +1.439, hepsi p<0.001-0.013.

> ⚠️ **Wiki amacı için "çift darbe" implication'ı [Tablo 8]:** Wiki S&P 500 /
> Nasdaq 100 evrenlerine odaklı (large-cap, likit, çoğu dividend-payer, düşük
> idio risk). McLean-Pontiff'in bulgusu: bu tam olarak **post-publication decay
> en agresif olduğu** firma profili. Dolayısıyla wiki gündemi için decay riski
> yapısal olarak **iki kat** yüklü: (1) F-Score gibi paperları large-cap'te
> zaten zayıf [[piotroski2000_f_score]] [Tablo 4]; (2) post-publication
> arbitraj baskısı large-cap'te en yüksek. Faz 3 strateji tasarımı bu çift
> darbeyi base-rate olarak içselleştirmeli.

Sample-end opportunism reddediliyor [Tablo 4]: orijinal sample'ın son 12 ayında
return decay coefficient -0.091 INSIG (p=0.678); first-12-out-of-sample +0.338
INSIG. Yani araştırmacılar "iyi göründüğü yerden kesip alıyor" hipotezi kanıtla
desteklenmiyor.

## Tek Cümle Tezi

Akademik literatürde rapor edilmiş 82 cross-sectional anomaly'nin getirisi
out-of-sample dönemde istatistiksel olarak değişmez (statistical bias ≈%10
insig), ama yayım sonrasında **ortalama %35 azalır** (sig %1) — fark
**publication-induced sophisticated arbitrage**'a atfedilir; decay büyük,
likit, kolay-arbitraj-edilebilir firmalarda en güçlüdür.

## Ortaya Konan Sinyal/Faktör

**Yeni empirik faktör YOK.** Bu paper bir **meta-empirical study** — mevcut
anomalies'in kendisini analiz konusu yapar. Wiki'de bu paperdan yeni
`factors/*` sayfası açılmadı. Yerine **bir concept sayfası açıldı:**

- [[post_publication_decay]] — concept; decay'in mekanizmaları (statistical
  bias / informed trading / limited arbitrage), decay-adjusted spread tablosu
  (wiki'deki ingested factors için), wiki'nin epistemik omurgası

> 📝 **Decay-adjusted spread tablosu** (Cycle 11 kullanıcı kararı 2): wiki'deki
> ingested faktörlerin in-sample headline spread'ine McLean-Pontiff %35
> decay-shrink uygulanmış versiyonu **[[post_publication_decay]] sayfasında**
> tutulur, [[fundamental_scoring]] sayfasında değil. Strateji baseline rakamı
> olarak Faz 3'te kullanılır.

## Metodoloji

### 82 anomaly seçimi [s.6-7]

- Peer-reviewed finance / accounting / economics dergilerinde cross-sectional
  predictability rapor eden 68 çalışma
- Null reddi 5% level
- Compustat + CRSP ile inşa edilebilir public data
- 82 = 68 paperdan derlenen (bazı paper birden fazla anomaly raporlar)
- Compustat field değişimleri sebebiyle 10 anomaly in-sample replicate edilemedi
  (Fama-MacBeth t-stat |t|<1.25); **kalan 72 anomaly ana testlerde** [s.10, fn 8]

### Anomaly-level normalizasyon [s.13-14, eq.(1)]

Aylık Fama-MacBeth slope coefficient $\bar{Y}_{i,t}$ (continuous variable
veya quintile-portfolio dummy üzerinden) → in-sample mean $\mu_i$ ile
**normalize edilir** ($\tilde{Y}_{i,t} = \bar{Y}_{i,t}/\mu_i$).

Random-effects panel regresyonu:

$$
\tilde{Y}_{i,t} = a + H_1 \cdot \text{PostSample}_{i,t} + H_2 \cdot \text{PostPub}_{i,t} + \epsilon
$$

- `PostSample = 1` if month is after end-of-sample but pre-publication
- `PostPub = 1` if month is after publication date
- $H_1$ ≈ "statistical bias" (sophisticated traders publication öncesi unaware
  varsayımı)
- $H_2$ ≈ "statistical bias + publication effect"

Decay yorumu: $H_1 = -0.10$ → out-of-sample return in-sample mean'in %90'ı
(yani %10 decay).

### "Strongest form" specification [s.13]

Her anomaly için iki yöntem (continuous Fama-MacBeth vs. extreme-quintile
long-short portfolio) hesaplanır; **in-sample t-stat'i daha güçlü olan**
seçilir. Bu, "tek-yönlü" replikasyon hipotezini test eder: eğer anomalies
saf gürültüden ibaretse, in-sample-en-güçlü specification post-pub
overshooting decay göstermesi gerekir; pratikte göstermiyor.

## Empirik Sonuçlar (sayılarla)

### Tablo 1 — 82 anomaly profili [s.30]

| Kriter | Sayı | % |
|---|---|---|
| Toplam | 82 | 100% |
| Finance dergileri | 61 | 74% |
| Accounting dergileri | 19 | 24% |
| Economics dergileri | 2 | 2% |
| Continuous (e.g. size, past return) | 67 | 82% |
| Binary (e.g. credit downgrade) | 15 | 18% |
| In-sample replicate edilebildi | 72 | 88% |
| Continuous-stronger (replicated içinden) | 36 | 50% |
| Quintile-portfolio-stronger | 36 | 50% |

> 📝 **Wiki ile kesişen anomaly listesi (paperda explicit ismen geçenler veya
> referans listesinde yer alanlar):** Sloan 1996 (accruals), Banz 1981 (size),
> Jegadeesh-Titman 1993 (momentum), Bali-Cakici-Whitelaw 2011 (MAX), Amihud
> 2002 (illiquidity), Ang-Hodrick-Xing-Zhang 2006 (idio vol), Dichev-Piotroski
> 2001 (credit rating), Michaely-Thaler-Womack 1995 (dividend init/omission),
> Ritter 1991 (IPO), Naranjo-Nimalendran-Ryngaert 1998 (dividend yield),
> Franzoni-Marin 2006 (pension funding). **Piotroski 2000 (F-Score)
> referans listesinde YOK** — F-Score 82 anomaly setinde explicit listed
> değil; F-Score için decay rakamı doğrudan paperdan gelmiyor, [[meta/open_questions]] (Q5)
> cevabı **aggregate %35 ortalaması üzerinden** uygulanır
> (composite-score-spesifik anomaly-level decay literatürü için Li-Mohanram
> 2019 ve Green-Hand-Soliman 2011 separately gerekli).

### Tablo 2 — anomaly-level decay özeti [s.31]

In-sample mean ile normalize edilmiş out-of-sample ve post-publication
return'lerin **anomaly-equal-weighted ortalaması**:

| Specification | Out-of-Sample (pre-pub) | Post-Publication |
|---|---|---|
| **Continuous (Panel A)** | 0.78 (t=-1.40, %63 anomaly <1) | **0.51** (t=-4.91, %82 <1) |
| **Portfolio (Panel B)** | 0.90 (t=-0.58, %57 <1) | **0.47** (t=-3.62, %68 <1) |
| **Strongest (Panel C)** | 0.77 (t=-1.56, %65 <1) | **0.51** (t=-4.02, %78 <1) |

> 📝 Tablo 2 anomaly-level summary, kısa-sample anomalies'e fazla weight
> verir. Tablo 3 random-effects regression daha doğru standart hata yapısı
> verir.

### Tablo 3 — main result, random-effects regression [s.32]

| Coefficient | Continuous | Portfolios | Strongest | Strongest-SSRN |
|---|---|---|---|---|
| **Post Sample** | -0.202 (p=0.090) | -0.015 (p=0.902) | **-0.097 (p=0.386)** | -0.102 (p=0.389) |
| **Post Publication** | -0.422 (p<0.001) | -0.347 (p=0.002) | **-0.369 (p<0.001)** | -0.343 (p<0.001) |
| Constant | 0.986 | 1.040 | 0.982 | 0.961 |
| HO: PP=PS p-value | 0.073 | 0.010 | 0.020 | 0.050 |
| HO: PS=-1 p-value | <0.001 | <0.001 | <0.001 | <0.001 |
| HO: PP=-1 p-value | <0.001 | <0.001 | <0.001 | <0.001 |
| Obs | 37,676 | 37,676 | 37,676 | 37,676 |

> 📝 **Headline rakamların kaynağı:** Abstract "out-of-sample ≈10%, post-pub
> ≈35%" rakamları **Strongest-form (Panel C/Column 3) coefficient'lerine
> denk geliyor**: 1−0.97=0.03 ≈ 0.10 değil aslında — Strongest -0.097 → ≈10%
> decay (paperin abstract dilinde). Post-pub -0.369 → ≈35-37% decay. Continuous
> -0.422 → 42%, Portfolios -0.347 → 35%; yazarlar ortalamayı 35% raporlar.

### Tablo 4 — yıllık decay paterni [s.33]

Sample-end manipulation testi + post-pub decay'in zaman boyutu:

| Variable | Coefficient | SE | p-value |
|---|---|---|---|
| **Last 12 months sample** | -0.091 | 0.218 | **0.678 (insig)** |
| **First 12 months out-of-sample** | +0.338 | 0.209 | 0.107 |
| Post-First-12 (out-of-sample) | -0.292 | 0.119 | 0.014 |
| **P1-12 (post-pub year 1)** | -0.283 | 0.217 | 0.191 |
| **P13-24** | -0.178 | 0.226 | 0.430 |
| **P25-36** | **-0.577** | 0.237 | **0.015** |
| **P37-48** | -0.563 | 0.241 | 0.020 |
| **P49-60** | -0.481 | 0.222 | 0.030 |
| **P>60** | -0.307 | 0.090 | <0.001 |
| Constant | 0.964 | 0.063 | <0.001 |
| N | 37,680 | | |

> 📝 İki kritik bulgu:
> 1. **Sample-end opportunism reddediliyor:** Last-12 INSIG (p=0.678) +
>    First-12-out-of-sample POZİTİF (insig). Eğer araştırmacılar opportunistik
>    sample-end seçseydi tam tersi işaretler beklenirdi.
> 2. **Decay timing pattern:** Yıl 1-2 decay görece zayıf (insig); maximum
>    decay **yıl 3-5'te** (-0.577, -0.563, -0.481, hepsi sig); yıl 5+ partial
>    recovery (-0.307). Bu pattern, sophisticated trader'larin publication
>    sonrası **3-5 yıl boyunca progresif giriş yaptığını** + zamanla
>    crowded-out olunca yeni-anomaly'lere geçtiğini ima eder.

### Tablo 5 — time trends ve post-pub indicator yarışı [s.34]

Post-publication effect bir **discrete change**'i mi temsil ediyor, yoksa
**lineer time trend**'in bir parçası mı?

| Spec | Time | Time Post Pub | Post 1993 | Post Sample | Post Pub |
|---|---|---|---|---|---|
| 1 (Time only) | -0.041%/ay (p=0.021, sig) | | | | |
| 2 (TimePostPub only) | | -0.190%/ay (p<0.001, sig) | | | |
| 3 (Post1993 only) | | | -0.122 (p=0.255, **insig**) | | |
| 4 (Time + indicators) | +0.003%/ay (p=0.900, **insig**) | | | -0.029 (p=0.806) | **-0.365 (p<0.001)** |
| 5 (TimePostPub + indicators) | | -0.070%/ay (p=0.280, insig) | | -0.025 (p=0.845) | **-0.293 (p=0.021)** |
| 6 (Post1993 + indicators) | | | +0.099 (p=0.419) | -0.069 (p=0.588) | **-0.425 (p<0.001)** |

> 📝 **Time trends post-pub indicator ile birlikte INSIG hale gelir;
> post-pub indicator sig kalır.** Anomaly decay bir lineer trend değil,
> **publication zamanına ankrajlı discrete change**. Trading-cost
> reduction veya post-1993 information environment hipotezleri (Chordia
> vd. 2011) tek başına yeterli değil.

### Tablo 6-7 — Informed trading kanıtı [s.35-36]

In-sample mean'e göre normalize edilmiş trading activity rank'leri:

**Tablo 6 anomaly-level summary (Post-Publication panel):**

| Trait | Mean ratio | t-stat | %>1 |
|---|---|---|---|
| Turnover | 1.11 | 5.71 | %83 |
| Dollar Volume | 1.11 | 4.64 | %73 |
| Variance | 1.22 | 11.51 | %89 |
| Short Interest | 1.09 | 8.01 | %92 |

**Tablo 7 random-effects regression (Post Pub coefficients, %):**

| Trait | Post Sample | Post Pub | HO: PP=PS p |
|---|---|---|---|
| Variance | 1.108 (p=0.541) | 1.991 (p<0.001) | 0.099 |
| Turnover | 0.300 (p=0.011) | 0.281 (p=0.059) | 0.850 |
| Dollar Volume | 0.281 (p=0.007) | 0.262 (p=0.046) | 0.830 |
| Short Interest | 0.867 (p<0.001) | 1.893 (p<0.001) | <0.001 |

> 📝 **Yorumu:** Trading activity (turnover, volume, short interest, variance)
> hem post-sample hem post-publication artıyor. Variance ve short interest
> için post-pub artış post-sample'dan **anlamlı şekilde daha güçlü**;
> turnover ve dollar volume için fark insig. Toplam sonuç: informed traders
> pre-publication (working-paper aşamasında) zaten anomaly'leri arbitraj
> ediyor; publication effect ek bir kuvvet katıyor.

### Tablo 8 — Limited arbitrage [s.37] — wiki için KRİTİK

Post-pub-only sample (9,823 obs); dependent variable normalize edilmiş
anomaly return; independent variables **anomaly portfolio'sundaki
in-sample average stock-level traits**:

| Trait | Constant (intercept) | Slope (sig p<0.05 hepsinde) | Yorum |
|---|---|---|---|
| **Size** | -1.490 (p=0.013) | **+1.442 (p<0.001)** | Büyük-cap firmalar daha çok decay |
| Spreads | 0.999 (p=0.092) | 0.176 (p=0.502) | Borderline |
| **Dollar Volume** | -1.671 (p=0.009) | **+1.380 (p<0.001)** | Likit firmalar daha çok decay |
| **Idiosyncratic Risk** | 4.054 (p<0.001) | **-1.420 (p=0.001)** | Yüksek idio risk → decay AZ |
| **Dividends** | -1.381 (p<0.001) | **+1.439 (p<0.001)** | Dividend-payer'lar daha çok decay |

> 📝 **Yorumu:** 5 traits'in 4'ü (size, dollar volume, idio risk, divid)
> p<0.001-0.013'da significant. Pattern tutarlı: **arbitrage daha kolay**
> firmalarda (büyük cap, likit, düşük idio risk, divid-payer ⇒ holding cost
> düşük) post-pub decay **daha güçlü**. Bu, "publication → arbitrage →
> mispricing reduction" mekanizmasının doğrudan empirik kanıtıdır.

> ⚠️ **Wiki için "çift darbe" implication:** S&P 500 + NDX evren tam olarak
> bu 4 trait'e high-end'de (büyük, likit, çoğunlukla dividend-payer,
> görece düşük idio risk). Yani wiki'nin amaç evrenleri için decay
> **agresif** beklenmeli. Bunu Q29 olarak open_questions'a ekledim.

### Tablo 9 — Correlation dynamics [s.38-39]

In-sample anomaly portfolios birbirleriyle korele (β=0.634, p<0.001), post-pub
anomaly portfolios ile korelasyon zayıf (β=0.025, p=0.136). **Publication
sonrası** bu pattern tersine döner: post-pub interaction terim -0.555 (sig),
yeni in-sample anomaly'lerle korelasyon ~0.08'a düşer; post-pub interaction
+0.399 (sig), diğer published anomaly'lerle korelasyon yükselir.

> 📝 Yorumu: Yayım, sophisticated traders'i bir anomaly üzerinde "aynı tarafa"
> çeker; bu, publish edilmiş anomaly'lerin **sınıf-içi** korelasyonunu
> arttırır. Mispricing'in **ortak kaynağı** vardır (Stambaugh-Yuan 2017
> "mispricing factors" hipotezini destekler).

### Tablo 10 — Anomaly persistence [s.40]

Aylık anomaly return otokorelasyonu: 1-ay lag +0.132 (sig); 12-ay sum lag
+0.016 (sig p=0.007). Anomaly returns short-term momentum gösterir.

> 📝 Faz 3 strateji tasarımı için ipucu: Anomaly portfolios kendi-aralarında
> kısa-vadeli persistence taşır. Yıllık rebalans bu otokorelasyonu sömürmez
> ama dilüe eder.

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Paper anomaly-level decay'i analiz eder, kendisi top-N selection önermez. Ama 82 anomaly'nin tümü extreme-quintile long-short formülasyonunda — top-N selection paradigmasının post-pub robustness'ı için **temel epistemik altyapı**. Wiki'nin top-N stratejilerinin (F+V/P, G+NEGPEG) decay-adjusted baseline rakamı bu paper üzerinden okunur. | N/A → epistemic backbone |
| **Annual rebalance** | Paper aylık Fama-MacBeth slope'larıyla çalışır; rebalance frekansı kendisi önermez. Ama Tablo 10 anomaly persistence'i 1-ay > 6-ay > 12-ay → **monthly otokorelasyon yıllık rebalans tarafından dilüe edilir**. Wiki amacı (annual rebalance) için bu nüans nötr-zayıf-negatif. | N/A / ⚠️ aylık rebalans daha fazla persistence yakalar; yıllık kompleman |
| **Large-cap evrene transfer** | [Tablo 8, s.37] **post-pub decay büyük cap firmalarda DAHA güçlü** (Size coef +1.442, p<0.001). Wiki amaç evrenleri (S&P 500 + NDX) tam olarak bu segmentte → **çift darbe** kanıtı. | ⚠️ **kritik bulgu**: large-cap evrende decay agresif; in-sample large-cap zaten zayıf (Piotroski Tablo 4) → kümülatif risk |
| **NDX intangibles / growth firms** | Paper intangibles'i adresleme; 82 anomaly içinde R&D / intangibles factors var ama ayrı decompose edilmez. NDX growth-heavy firmalar için spesifik decay testi paperdan gelmiyor. | N/A — Lev-Sougiannis 1996, Peters-Taylor 2017 ingestleri ile cevap |

**Strateji tasarımına net implikasyon:**

1. **Decay-adjusted spread baseline**: Wiki'deki ingested fundamental
   scoring strategies'in (F-Score, G-Score, Magic Formula, F+V/P, G+NEGPEG,
   Sloan accruals, CGS asset growth) Faz 3 baseline performansı,
   in-sample headline'a **0.65 decay multiplier** uygulanmış versiyondur
   (1 − 0.35 = 0.65). Detay [[post_publication_decay]] sayfasında
   decay-adjusted spread tablosu.

2. **Çift darbe kanıtı [Tablo 8 + Piotroski Tablo 4]**: Wiki amaç evrenleri
   (S&P 500 + NDX) için yapısal decay riski **iki bağımsız kanıt** üzerinden
   güçleniyor: (a) in-sample large-cap'te F-Score zaten zayıf
   ([[piotroski2000_f_score]] [Tablo 4]); (b) post-pub decay large-cap'te
   en agresif (bu paper). Faz 3 strateji tasarımı bu çift darbeyi
   base-rate olarak kabul etmeli — hem **combined yaklaşım** ([F+V/P, G+NEGPEG,
   [[li_mohanram2019_quality_value]]]) hem **q5 baseline kontrolü**
   ([[hou_mo_xue_zhang_2020_security_analysis]]) bu çift darbeye karşı
   defansif bileşen.

3. **Sample-end opportunism reddi [Tablo 4]**: Wiki ingest workflow'unda
   "yazarlar sample'ı opportunistik kesti" şüphesi yapısal olarak
   geçerli değil (Last-12 INSIG, First-12-out-of-sample POSITIVE INSIG).
   Bu, in-sample headline rakamlarına **statistical bias üzerinden**
   güvenebileceğimiz anlamına gelir — decay sebebi başka (informed
   trading + arbitrage).

4. **Annual rebalance + monthly otokorelasyon ipucu [Tablo 10]**: Wiki amacı
   yıllık-frekanslı; aylık otokorelasyon (1-ay lag +0.132 sig) yıllık
   horizon'da dilüe olur. Faz 3'te "yıllık rebalans + 6-aylık intra-year
   re-evaluation" hibridi düşünülebilir, ancak bu wiki amacının dışına
   çıkar.

## Bu paper'ın sürprizi

> 📝 Hipotez tablo: paper okunmadan önce ne bekleniyordu vs. paperin
> empirik bulgusu. Cycle 8'den itibaren §11 governance pattern.

| Hipotez | Beklenti (kullanıcı önceki cycle özetinde) | Paper'da gerçek |
|---|---|---|
| **Out-of-sample decay büyüklüğü** | "Belirgin" beklenebilirdi (statistical bias yaygın) | %10 ortalama, **istatistiksel olarak 0'dan farksız** — bias minimal |
| **Post-publication decay** | "Tam silme" (=%100) hipotezi possible | %35, **0'dan da -100'den de farklı** — kısmi decay; anomaly hayatta ama zayıflıyor |
| **Decay timing** | Lineer trend beklenebilir | **Discrete jump, ankrajlı yayım tarihi**; max decay yıl 3-5 |
| **Limited arbitrage işareti** | Belki small/illiquid firmalarda decay az | Doğrulandı + **büyük/likit/divid-payer/düşük-idio'da decay AGRESİF** |
| **Sample-end opportunism** | "Araştırmacılar iyi yerde kesip alıyor" yaygın eleştiri | **REDDEDİLİYOR**; Last-12 month coefficient INSIG, opposite-sign |

**Sürpriz büyüklüğü:** ORTA. Limited arbitrage ve discrete-change-at-publication
bulgular **kantitatif olarak güçlü** ama yön olarak yaygın hipotezi destekliyor.
**En sürprizli bulgu**: sample-end opportunism reddi — çoğu eleştirmen tarihsel
olarak bu varsayım üzerine bina kuruyor; paper bunu doğrudan testle çürütüyor.

## Limitler ve Caveats

- **82 anomaly'nin tam listesi paperin published versiyonunda Internet
  Appendix'te [s.9, fn 7]:** Wiki text extract'inde tam liste yok; abstract +
  reference list explicit anomaly'leri listeler ama 82'sinin tamamı
  enumerate edilmedi. Wiki için kritik: spesifik factor (F-Score, G-Score,
  Magic Formula) decay rakamı **paperdan tek-tek çıkarılamaz**; aggregate
  %35 ortalaması ve 82-anomaly band üzerinden uygulanır.

- **Continuous Fama-MacBeth + extreme-quintile long-short standartı:**
  Composite scores (F-Score, G-Score) bu specification'a tam fit etmez —
  9-binary toplam single Fama-MacBeth coefficient'ine sığmaz. Composite
  score decay için Li-Mohanram 2019 [[li_mohanram2019_quality_value]]
  modern replikasyon (1973-2012) **somut decay örneği** sağlar (F orijinal
  +23% → +7.44%, ~3x). Bu paperin aggregate %35 ortalaması ile
  Li-Mohanram'in spesifik decay'i uyumlu (sample uzatma + universe genişlemesi
  + binary→continuous + industry classification revision karışık etkiler
  paperin tek decay komponentiyle birebir aynı değil).

- **Sample 1972-2011 (yayım 2016, working paper Oct 2012):** Modern
  post-2012 anomalies (FAANG dönemi, ML feature explosion) bu paper kapsamı
  dışı. Chen-Zimmermann 2022 (Tier 2 #41) modern replikasyon database'i;
  Jensen-Kelly-Pedersen 2023 (Tier 2 #44) "Replication Crisis" paper
  modern eksik halkayı doldurur. Bu, **Q28** olarak open_questions'a eklendi.

- **Aylık portfolio returns + Fama-MacBeth, yıllık değil:** Wiki amacı
  yıllık-frekanslı; bu paperin findings yıllık rebalans için **direct**
  uygulanamaz, ama aggregate decay multiplier (0.65) yıllık-frekans için de
  geçerli kabul edilebilir (decay temelde fundamental information arbitrage
  sürecidir, frekansla orantısız).

- **CRSP all-stock universe:** Paper CRSP'de listed tüm hisseler (NYSE +
  AMEX + NASDAQ); large-cap-only (S&P 500) ya da NDX-only sub-sample testi
  paperda yok. Wiki amaç evrenlerine "çift darbe" implication'ı [Tablo 8]
  üzerinden çıkarılır, doğrudan endüstri-özel test değil.

- **Mispricing vs risk-premium yorumu:** Paper sophisticated trader
  arbitrage hipotezini destekler ([s.4-5, s.18-20]) — yani anomaly'lerin
  **mispricing component'i** olduğu yorumu. HMXZ 2020 q-factor model
  lens'inde anomaly'ler **risk premium exposure**'larıyla span edilebilir
  (mispricing değil) [[hou_mo_xue_zhang_2020_security_analysis]] — bu,
  potansiyel **felsefi çelişki** alanıdır (aşağıda Çelişkiler bölümünde).
  Wiki taraf tutmaz; pratik strateji tasarımı için her iki yorum da
  decay-adjusted spread baseline'ı destekler.

- **Yayımlanmış vs working-paper sayfa numaraları farkı:** Bu wiki working
  paper (Oct 2012) sayfa numaralarını kullanır. JF 2016 final yayında
  tablo numaraları aynı, sayfa numaraları farklı (5-32 aralığı).

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfalar
- [[post_publication_decay]] — concept; decay'in 3 mekanizması, decay-adjusted
  spread tablosu (wiki'deki ingested factors için), wiki'nin epistemik omurgası

### Bu paperın update ettiği mevcut sayfalar
- [[sloan1996_accruals_anomaly]] — Q5 anchor; Sloan accruals decay aggregate
  %35 baseline (paper-spesifik decay rakamı paperdan teyit edilemiyor;
  82-anomaly aggregate ortalaması)
- [[piotroski2000_f_score]] — Q5 anchor + F-Score "çift darbe" (large-cap
  zayıf + post-pub decay agresif)
- [[mohanram2005_g_score]] — Q5 anchor + G-Score decay (paper-spesifik
  rakamı yok; aggregate üzerinden + Li-Mohanram somut karşılaştırma)
- [[li_mohanram2019_quality_value]] — Q5 anchor + combined decay perspective
  (Li-Mohanram modern replikasyonu McLean-Pontiff aggregate'ı somutlaştıran
  composite-score örneği)
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — Q5 anchor + asset
  growth decay
- [[hou_mo_xue_zhang_2020_security_analysis]] — Q5 cross-link (q5 model
  span vs post-pub decay potansiyel çelişki notu)
- [[F_Score]] — Reported Performance McLean-Pontiff aggregate decay multiplier
- [[G_Score]] — Reported Performance benzer
- [[Magic_Formula]] — Reported Performance benzer
- [[Accruals]] — Reported Performance Sloan'a uygulanmış decay
- [[Asset_Growth]] — Reported Performance CGS asset growth decay
- [[factor_zoo]] — "Decay perspective on factor zoo" yeni alt-bölüm; Cochrane
  #1+#3 ile bağ

### İlgili paperlar (ingested)
- [[cochrane2011_discount_rates]] — Cochrane #3 sorusu ("how many factors
  really matter") McLean-Pontiff prosedürel cevabın bir kısmını sağlar:
  82 anomaly aggregate %35 decay → factor zoo'nun bir kısmı **gerçek**
  ama survival rate kısıtlı.
- [[famafrench1993_three_factor]] — paperin reference'unda HML/FF3 explicit
  anomaly olarak yer almaz ama "size and value" Schwert (2003) atfı ile
  index-fund-decay context'inde geçer
- [[famafrench2015_five_factor]] — anomaly-survival çerçevesinde FF5'in
  kendisi de bu literatürün bir parçası
- [[carhart1997_four_factor]] — momentum 82 anomaly'den biri (Jegadeesh-
  Titman 1993 reference list'te); paperda momentum decay individual olarak
  rapor edilmez ama aggregate'a dahil
- [[israel_moskowitz_2013_shorting_size_time]] — **Cycle 22 ek**;
  limited arbitrage [Tablo 8] büyük/likit firmalarda decay agresif → Israel-Moskowitz
  86-yıl sample'da "anomaly small-cap dominant" cross-evidence (HML
  size Q5 α=3.70% t=1.90 INSIG; size Q1 α=11.22% t=3.87 sig). MP
  publication-anchored decay + Israel-Moskowitz pre-MP decade-by-decade
  size decomposition iki farklı time variation paradigması (Q53 yeni);
  çelişki yok, sentez Faz 2'de.
- [[hou_mo_xue_zhang_2020_security_analysis]] — q-factor lens'inde span
  edilen 6 strategy McLean-Pontiff aggregate'ından **bağımsız**
  decay testi; mathematical equivalence (Cochrane) iki yorumu uyumlu kılar

### Cycle 12 ek (HLZ 2016 ingested)
- [[harvey_liu_zhu_2016_multiple_testing]] — paper içinde McLean-Pontiff
  explicit reference [s.5-6]: "Our research is related to a recent
  paper by McLean and Pontiff (2014)... Their paper tests the
  statistical biases". HLZ McLean-Pontiff'in post-pub decay'ini
  "out-of-sample approach to statistical bias" olarak gösteriyor.

### Cycle 13 ek (HXZ 2020 ingested)
- [[hou_xue_zhang_2020_replicating_anomalies]] — paper [s.3] McLean-
  Pontiff'i **explicit methodology eleştirisi** tonuyla ele alıyor:
  "However, McLean and Pontiff use NYSE-Amex-NASDAQ breakpoints and
  equal-weights in their tests." Bu eleştiri **empirik çürütme değil
  methodology disagreement**. Wiki [[meta/contradictions]] sayfasında
  resmî entry açıldı: "MP 2016 ↔ HXZ 2020 methodology farkı"
  (resolution: scope-dependent). **97 anomaly nüansı:** HXZ "97
  anomalies" diyor (yayınlanmış JF 2016 versiyonu); wiki MP paper
  sayfasında 82 anomaly (working paper Oct 2012). MP yayınlanmış
  versiyonunda 82'den 97'ye genişletilmiş.
  **Üç-bacak epistemik omurga (Cycle 13):** HLZ statistical FDR
  filter + MP behavioral decay + **HXZ empirik replication** =
  factor zoo'dan true signal ayıklamanın üç bağımsız mekanizması.
  Detay [[concepts/post_publication_decay]] üç-bacak epistemik
  omurga + dört darbe çerçevesi tablosu;
  [[concepts/anomaly_replication]] aggregate tablosu.

### Cycle 14 ek (Bailey-LdP DSR ingested)
- [[bailey_lopezdeprado_2014_deflated_sharpe]] — DSR sample length
  düzeltmesi (DSR-4) ile MP behavioral decay **paralel ama farklı
  mekanizma**: MP arbitrage activity (post-pub trader reaction) ile
  signal degradation; Bailey-LdP statistical sample noise correction.
  Memory effects altında Bailey-LdP backtest overfitting "loss
  maximization"a yol açar [s.5] — out-of-sample sıfır değil negatif.
  MP'nin %35 aggregate decay'i bu memory mekanizmasıyla **kısmen**
  açıklanabilir (mean-reverting equity returns'de overfitted strateji
  kayıp yaşar). İki paper aynı "out-of-sample yetersizlik" sonucuna
  farklı yollardan varır.

### Henüz wiki'de olmayan, doğrudan ilgili Tier-1 ve Tier-2 paperlar
- Hou-Xue-Zhang (2020) "Replicating Anomalies" (Tier 1 #18) — ~447 anomaly
  replikasyon, McLean-Pontiff'i büyük örneklemde tekrarlar
- Jensen-Kelly-Pedersen (2023) (Tier 2 #44) — "Replication Crisis in Finance"
  modern güncelleme
- Chen-Zimmermann (2022) (Tier 2 #41) — Open Asset Pricing replikasyon
  database
- Green-Hand-Soliman (2011) (Tier listesinde değil, aday) — accruals anomaly
  decay anchor, McLean-Pontiff'le birlikte Sloan-spesifik decay için kanıt
- Schwert (2003) — index-fund-tabanlı size + value decay (paperin
  conceptual ancestor'u)

## Cycle 29 ek (data_sources.md açıldı)

[[methodology/data_sources]] modern data infrastructure pointer
dokümantasyonu: Chen-Zimmermann 2022 Open Asset Pricing Database
(pure replication ~100%) + JKP 2023 GlobalFactor code repository +
WRDS open-source access **üç paralel data kaynağı** Faz 3 backtest
implementation ön koşul. MP 2016 aggregate %35 decay benchmark
modern data infrastructure altında **post-publication coefficient**
modern güncelleme (Chen-Zimmermann database 1926+ + post-2014 ek)
Faz 3 custom replikasyon ile validate edilebilir.

## Cycle 27 ek (JKP 2023 ingest) — MP ↔ JKP dramatic farklı sonuç

[[jensen_kelly_pedersen_2023_replication_crisis]] modern güncelleme
**dramatik farklı sonuç**: MP 2016 aggregate **%35 decay** (1972-
2011, 82 anomaly) vs JKP 2023 **%88.5 out-of-sample positive**
(combined; 1926-2020, 153 factor) — **methodology disagreement**:

| Aspect | MP 2016 | JKP 2023 |
|--------|---------|----------|
| Methodology | Publication-anchored panel regression | Bayesian Empirical Bayes hierarchical |
| Sample | 82 anomaly US 1972-2011 | 153 factor US 1926+ Global 1986+ |
| Out-of-sample | Post-publication coefficient | Pre+post out-of-sample positive |
| Aggregate result | **%35 decay** sig 1% | **%88.5 positive** combined |

**Resolution scope-dependent** (Cycle 13 paterni paralel + Cycle 27
HXZ ↔ JKP **3. contradictions entry**): MP publication-anchored
decade-shift framing vs JKP Bayesian replication framework. **Yeni
contradictions entry açılmadı** (HXZ ↔ JKP §3 entry yeterli; MP
↔ JKP paralel note paper sayfasında). MP konservatif tarafta
(×0.65 / ×0.50 decay multiplier korunur Cycle 24); JKP
anti-conservative upper bound sensitivity reference.

## Çelişkiler / Tartışmalar

> 📝 **Potansiyel çelişki (placeholder DEĞİL — sadece not):** McLean-Pontiff
> aggregate %35 decay vs HMXZ 2020 q5-model-spans-anomalies bulgusu birinci
> bakışta çelişir görünür: McLean-Pontiff "anomaly mispricing component
> arbitraj edilir" der, HMXZ "anomalies risk premium exposure'larıyla
> başından beri açıklanır" der.
>
> Cochrane (2011) [s.20] mathematical equivalence'a göre çelişki **YALNIZ
> felsefi**: aynı portfolyoyu (long high-F-Score, short low-F-Score) iki
> yorumla da kurabilirsin. Strateji performansı aynı; "risk premium" ya da
> "mispricing" yorum seçimi backtest sonucunu değiştirmez.
>
> **Resmî contradictions.md entry açılmadı** (Cycle 11 kullanıcı kararı 4):
> Hou-Xue-Zhang 2015 (q-factor origin paper, henüz wiki'de yok) ingest
> edildiğinde resmî entry değerlendirilecek — q5 ve McLean-Pontiff'in
> aggregate decay'i somut sayısal cross-test edilince.

> ⚠️ **Potansiyel çelişki — Hou-Xue-Zhang 2020 "Replicating Anomalies"
> (henüz ingest edilmedi, Tier 1 #18):** McLean-Pontiff %35 post-pub
> decay → ~%65 spread korunuyor iddiası ile HXZ 2020'nin ~%50 anomaly
> replicate başarısızlığı raporu arasında potansiyel empirik tansiyon.
> Resmî [[meta/contradictions]] entry'si HXZ 2020 ingest'inden sonra
> açılır.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q5 fully answered]** McLean-Pontiff 2016 anchor cevabı sağlandı:
  82 anomaly **aggregate** post-pub decay ≈%35 (sig 1%); büyük/likit/
  divid-payer/düşük-idio firmalarda **daha güçlü** (limited arbitrage).
  Sloan accruals, F-Score, G-Score, Magic Formula gibi spesifik anomaly'ler
  için paper anomaly-level decay rakamı **vermez** (82 anomaly tek-tek
  enumerate edilmedi paper extract'inde); aggregate ortalama her ingested
  factor'a uygulanır → [[post_publication_decay]] decay-adjusted spread
  tablosu. Q5 epistemik omurga sorusu kapanmış sayılır; Q28 ve Q29 yeni
  takip soruları açıyor.

- **[Yeni Q28]** Modern post-2012 anomaly decay replikasyonu: McLean-Pontiff
  sample 2011'de bitiyor. Post-2012 dönem (FAANG yükselişi, ML feature
  explosion, COVID-19 macro shocks) için aggregate decay rakamı henüz
  wiki'de yok. Chen-Zimmermann 2022 (Tier 2 #41) "Open Asset Pricing"
  güncel replikasyon database; Jensen-Kelly-Pedersen 2023 (Tier 2 #44)
  "Replication Crisis in Finance" modern parça; Hou-Xue-Zhang 2020
  "Replicating Anomalies" (Tier 1 #18) ~447 anomaly replikasyonu da
  cevap sağlar. Q28 bu üç paper ingest sonrasında tam cevaplanır.

- **[Yeni Q29]** Limited arbitrage NDX implikasyonu: McLean-Pontiff
  [Tablo 8] post-pub decay büyük/likit/divid-payer/düşük-idio firmalarda
  daha güçlü bulgusu wiki amaç evrenlerine **çift darbe** anlamı taşıyor.
  S&P 500 ve özellikle NDX (FAANG-dominant) bu profili maksimize eder.
  **Spesifik soru:** NDX evreninde post-2012 dönem için F-Score, G-Score,
  Magic Formula gibi composite scoring strategies'in post-pub decay'i
  aggregate %35'ten **daha yüksek** mi? Limited arbitrage hipotezi
  evet öngörür, ama empirik kanıt wiki'de yok. Faz 3 backtest tasarımında
  "decay-adjusted spread" rakamı NDX için **agresif tarafta**
  (örn. %50 decay) sensitivity analizi yapılmalı.

- **[Q1 partial-stronger]** S&P 500 evreninde value (HML, F-Score) post-2000
  performansı: McLean-Pontiff aggregate decay sample'ı 2011'e kadar gider
  (post-publication HML decay aggregate'a dahil); ama HML / F-Score
  spesifik decay rakamı paperdan ayrı ayrı çıkmıyor. Q1 anchor cevabı
  bu paperdan **partial** geliyor (aggregate %35 baseline); spesifik
  large-cap HML decay için Lev-Srivastava 2020 (Tier 2 #30) ek kanıt.

- **[Q17 partial-stronger]** Cochrane #3 ("how many factors really matter")
  cevabı: 82 anomaly **aggregate** %65 hayatta (decay-adjusted) — yani
  factor zoo'nun büyük kısmı **gerçek** ama post-pub zayıflıyor. Tam
  cevap için Hou-Xue-Zhang 2020 (Replicating Anomalies, Tier 1 #18)
  ingest gerekli — paper individual anomaly replication rate raporlar.

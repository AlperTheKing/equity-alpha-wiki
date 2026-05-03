---
type: paper
authors: [Lev, Baruch, Srivastava, Anup]
year: 2020
title: "Explaining the Recent Failure of Value Investing"
venue: "SSRN Working Paper, Oct 2019 / Feb 2020 (peer-reviewed publication: Critical Finance Review forthcoming/published)"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3442539
local_path: raw/papers/lev_srivastava_2020_value_failure.pdf
ingested: 2026-05-01
tags: [value_premium, intangibles, post_2010_crisis, mean_reversion, NDX_kritik, F_blok_3_kapanis, Faz_1_finalizasyon, S&P500_value, adjusted_HML, Q1_fully_answered]
status: ingested
---

# Lev & Srivastava (2020) — Explaining the Recent Failure of Value Investing

> 📝 **Atıf konvansiyonu:** `[Tablo N]` numaralı tablolar; `[s.X]` SSRN
> working paper PDF sayfa numarası (29 sayfa, Oct 2019 / Feb 2020 draft).
> Embedded text extract: `pdftotext -layout` ile lokal okuma.

> 📝 **F bloğu (intangibles) #3 ve KAPANIŞ** — Faz 1 finalizasyon Cycle 17.
> Lev-Sougiannis 1996 (R&D-only methodology origin, Cycle 15) +
> Peters-Taylor 2017 (total intangible capital generalization, Cycle 16) +
> Lev-Srivastava 2020 (post-2010 value-spesifik application, bu cycle) =
> F bloğu **3-katmanlı yapısal hierarchy**. NDX strateji yapısal foundation
> 3. ayağı; Q1 (S&P 500 value post-2000) **fully-answered** kanıt anchor.

> 📝 **Yazar continuity**: Baruch Lev (NYU Stern) Lev-Sougiannis 1996'nın
> ortak yazarı + Lev-Srivastava 2020'nin baş yazarı — 24 yıl sonra aynı
> R&D capitalization methodology'sini value strategy crisis context'inde
> uyguluyor. Origin attribution literature continuity.

## TL;DR

Lev-Srivastava 2020 **value investing strategy'sinin "post-2007 collapse"
yorumunun yetersiz olduğunu** empirik olarak gösterir: aslında value
strategy **1989'dan beri faltering**, sadece 2000-2006 tech bubble
shorting kısa rezerve ile maskelenmişti. **Iki ana sebep**:

1. **Accounting deficiencies** [Section 4-6]: Intangibles expensing
   (R&D + SG&A) book value mismeasurement → **adjusted book value
   methodology** (Lev-Sougiannis + Peters-Taylor paralel) ile 39 yılın
   34'ünde conventional strategy'i geçer; intangibles-yoğun glamour
   firms'da effect dramatic
2. **Mean reversion slowdown** [Section 7-9]: Post-2007 financial crisis
   bank lending contraction + consumer demand fall → value firms
   (banking, retail, insurance, wholesale, utilities = 50-60% large
   value companies) trapped, R&D/IT/acquisitions yapamıyor; glamour
   firms (software, pharma, electronics) scalable intangibles + network
   effects ile 2007-2018 highest profitability since 1970

**Sample**: 1970-2018 (49 yıl); CRSP+Compustat all-stocks (NYSE+AMEX+
NASDAQ ex-financials); Fama-French 1993 HML methodology (size-adjusted
long-short value-weighted, June 30 rebalance).

**KRİTİK NÜANS — sample focus** [s.16 footnote 13]:
> "We focus in the subsequent analyses on the 50% largest value and
> glamour stocks, since our adjusted strategy yielded above-market
> returns for the small value and glamour stocks."

- **Section 1-7** (intangibles methodology + adjusted strategy returns):
  TÜM SAMPLE (CRSP all-stocks)
- **Section 8-11** (mean reversion + macro + glamour experience + escape):
  **50% LARGEST FOCUS**

Bu nüans wiki için kritik: S&P 500 ≈ top 500 ⊂ top 50% of CRSP all-stocks
(~1500 firms) → S&P 500 paper'a **adequate proxy** ama "tam S&P 500
universe" değil; Q1 fully-answered "50% largest subset" caveat ile.

## Tek Cümle Tezi

Value investing strategy'sinin "post-2007 collapse" yorumunun yetersiz
olduğunu, aslında 1989'dan beri faltering olduğunu ve iki ana sebebin
(intangibles accounting deficiencies + post-2007 mean reversion
slowdown) bulunduğunu empirik olarak göstererek, intangibles-aware
adjusted methodology'nin value strategy'i 39 yılın 34'ünde **kurtardığını**
gösterir.

## Ortaya Konan Sinyal/Faktör

**Yeni empirik faktör YOK** (Cycle 17 plan onayı: factor entity
açılmaz). Paper bir **value premium decay decomposition + intangibles-
aware adjusted strategy methodology** paper'ı; Lev-Sougiannis +
Peters-Taylor methodology'sinin direct application'ı.

Wiki'de bu paperdan **mevcut concept sayfaları zenginleştirilir:**

- [[concepts/intangibles_adjusted_accounting]] — F bloğu hub; Cycle 17
  ek olarak methodology hierarchy 3. satır (R&D-only → total → post-2010
  value-spesifik application)
- [[concepts/value_premium]] — Cycle 12'den beri izole concept (9
  inbound); Lev-Srivastava ile **yapısal zenginleşme** (Cycle 16
  audit'te tespit edilen izolasyon erken çözümü)

> 📝 **Paper'ın factor-level dolaylı katkıları wiki'de:**
> - [[HML]] — post-2010 performance crisis explicit kanıt; adjusted HML
>   alternative inşa
> - [[F_Score]] — F&V/P combined intangibles-aware revize gereği
>   (Q21 + Q23 ile bağlantılı)
> - [[G_Score]] — G&V/P combined intangibles-aware revize gereği
>   (Q21 + Q23 ile bağlantılı)
> - Logit Table 1 escape attributes (intangibles + capex + sales growth
>   + debt) Faz 3 strategy spec'inde **value-trap-avoidance filter**
>   baseline (Q45 yeni)

## Metodoloji

### Sample + value strategy methodology [Section 3-4]

- **Universe**: CRSP+Compustat all-stocks (NYSE+AMEX+NASDAQ); financials
  HARİÇ DEĞİL (Section 9-10'da banking sektörü explicit value sektör
  analiz ediliyor); negative book equity HARİÇ
- **Sample period**: 1970-2018 (49 yıl); decade-by-decade analiz
- **Value classification** [s.5 fn 4]: Fama-French 2003 methodology — 6
  equal groups (2 size × 3 MB), highest 30% MB = "glamour", lowest 30%
  MB = "value", **annual June 30 rebalance**
- **Returns**: HML one-half [(large value + small value)/2 long − (large
  glamour + small glamour)/2 short]; **value-weighted by capitalization**
- **Sample focus**:
  - Section 1-7 (intangibles methodology): all stocks
  - Section 8-11 (mean reversion + macro + escape): **50% largest only**
    [s.16 footnote 13]

### Adjusted book value methodology [Section 5-6]

```
Adjusted BV = reported BV + R&D capital stock + SG&A intangibles capital - amortizations
```

Methodology paralelliği:
- **R&D capital stock** = perpetual inventory of R&D — Lev-Sougiannis 1996
  [Eq. 8] paralel
- **SG&A intangibles part** — Enache-Srivastava 2018 (Management Science)
  + Peters-Taylor 2017 [Eq. 11] θ paralel; SG&A allocation organization
  capital olarak

Paper [Section 6] adjusted earnings methodology:
> "adding back to earnings the annual R&D expense and the part of SG&A
> related to intangibles, and subtracting from earnings the annual
> amortization of the R&D and SG&A capitals."

### Mean reversion measures [Section 8]

3 measure:
1. **Rank correlation**: stock'un MB rank'i (relative to all stocks)
   t yıl sonu vs t-1 yıl sonu — yüksek rank corr = düşük mean reversion
2. **Length of stay**: bir stock'un value veya glamour portfolio'da
   kalma süresi (yıl)
3. **Large price upticks/downticks**: 10%+ value stock yıllık upticks /
   glamour stock yıllık downticks frekansı

### Logit regression — Value escape attributes [Section 11, Table 1]

Sample 2008-2017 large value firms; bağımlı değişken = "escape from
value category to medium/high MB" (binary).

Methodology: Logit, 1% winsorize.

## Empirik Sonuçlar (sayılarla)

### Decade-by-decade returns [Section 3, Figure 1]

Long-short value strategy, $1 invested January 1 of each decade,
end-of-decade cumulative return:

| Decade | $1 → end value | Return | Notlar |
|---|---|---|---|
| **1970s** | $2.02 | **+102%** | "swan song of value investing" |
| **1980s** | $1.75 | **+75%** | Hala güçlü ama 1989 sonu faltering başlangıç |
| **1990s** | $0.90 | **-10%** | Tech bubble glamour'u şişirdi → short bacak kaybı |
| **2000-2006** | (small positive) | brief resurgence | Tech bubble shorting boost; "until 2006" |
| **2007-2018 (12 yıl)** | (negative) | "yielded negative returns" | 2007 financial crisis sonrası faltering derinleşmesi |

Paper [s.7]:
> "the value strategy had already lost much of its potency in the late
> 1980s, and yielded negative returns in the 1990s, barring a brief
> resurgence in 2000-2006."

### Adjusted strategy decade-by-decade [Section 5, Figure 3]

| Decade | Conventional | Adjusted | Adjusted advantage |
|---|---|---|---|
| 1970s | $2.02 | benzer (low intangibles) | minimal |
| 1980s | $1.75 | **$2.86** | +68% (1.11/1.75) |
| 1990s | $0.90 | **$2.00+** ("doubled the original") | dramatic |
| 2000-2009 | benzer | "substantially higher" | substantial |
| 2010-2018 | negative | "**reasonably positive gains**" | dramatic |

**Headline**: "All in all, in 34 out of the 39 years examined, 1970-2018,
the returns from the adjusted value strategy were higher than those of
the conventional strategy."

### Mean reversion slowdown [Section 8, Figures 6-8]

Rank correlation (large stocks):
- Value stocks: ~45% (1989-2006) → ~55-60% (2007-2018)
- Glamour stocks: 45-47% (1989-2006) → **~60% (2007-2018)**

Length of stay (large stocks):
- Value: 2.5 yıl (1989-2006) → **3.3 yıl (2007-2018)** = +32%
- Glamour: 3.5 yıl (1989-2006) → **4.5 yıl (2007-2018)** = +28%

Large price upticks/downticks frequency:
- Value 10%+ upticks: **22% (2000-2006) → 10% (2007-2018)** = -55%
- Glamour 10%+ downticks: **18% (2000-2006) → 10% (2007-2018)** = -44%

### Macro mekanizma post-2007 [Section 9-10]

Value firms (50-60% large value companies):
- Banking, retail, insurance, wholesale, utilities (5 lider sektör)
- Bank lending contraction → can't finance R&D/IT/acquisitions
- "**Less than 1% of value firms issued stock annually**" (2007-2018)
- Median ROE + RNOA collapse [Figure 9]: 2007-2018 worst since 1970
- Internal funds (earnings minus dividends) **negative average** [Figure 10]

Glamour firms (5 lider sektör):
- Business services (software), pharmaceuticals (incl biotech), electronics
- Scalable intangible assets + first-mover advantage + network externalities
- 2007-2018 **highest profitability since 1970** [Figure 9]
- "the average large glamour company invests now close to $1 billion a
  year in R&D" [s.21]

### Logit escape regression [Table 1, s.25]

2008-2017 large value firms; escape from value to medium/high MB
category:

| Variable | Coefficient | Sig |
|---|---|---|
| **Intangibles to Assets** | **1.664** | **<.01** |
| **Capex (net of dep) to Assets** | **4.686** | **<.01** |
| Sales growth | (sig) | **<.01** |
| Debt to Assets | (sig) | **<.01** |
| Loss | -0.485 | <.01 |
| Log of Assets | -0.193 | <.05 |
| Acquisitions, industry change, ROE, FCF/Assets, Cash/Assets, Age | — | insig |

**Yorum**: Internal investments (intangibles + capex + sales growth) +
debt-funded financing → escape; corporate acquisitions / industry
change / ROE → ineffective.

### MB ratio gap [Figure 12]

Paper [Section 12]:
> "the current differences between the medians of the market-to-book
> ratios of value and glamour stocks in Figure 12 aren't significantly
> larger than those that prevailed in the late 1990s and early 2000s."

→ **Value rebound argümanı zayıf**; value stocks "much cheaper than
glamour" hipotezi empirik destek bulmuyor.

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Paper return prediction değil — value strategy **explanation paperı**. AMA Logit regression [Table 1, s.25] value escape characteristics test eder: intangibles + capex + sales growth + debt sig pozitif coefficients ile **"value firms which escape low-MB" cross-section identification** sağlar. Doğrudan Top-N decile-spread methodology yok ama "escape predictors" cross-section signal seti olarak Faz 3 strategy spec'inde **value-trap-avoidance filter** baseline (Q45 yeni). | **⚠️** dolaylı |
| **Annual rebalance** | Sample 1970-2018; HML methodology (Fama-French 2003) **annual rebalance June 30**. Paper'ın merkezi reporting frequency yıllık (decade-by-decade returns + adjusted book value annual). Annual frequency natural fit. | **✅** |
| **Large-cap evrene transfer** | ⭐ **KRİTİK** — Paper [s.16 footnote 13]: **"We focus in the subsequent analyses on the 50% largest value and glamour stocks"**. Section 8-11 (mean reversion + macro + escape + glamour experience): **50% LARGEST FOCUS**. Section 1-7 (intangibles methodology + adjusted strategy): all-stocks. **Q1 (S&P 500 value post-2000) fully-answered**: 1989'dan beri faltering + 2007 crisis derinleşmesi + 2010s negative + adjusted methodology dramatic effect + 50% largest stocks focus. **Caveat**: S&P 500 ≈ top 500 ⊂ top 50% of CRSP all-stocks (~1500 firms) — adequate proxy, tam S&P 500 universe değil. | **✅** Q1 fully-answered |
| **NDX intangibles / growth firms** | ⭐ **KRİTİK** — Lev-Sougiannis (R&D-only) + Peters-Taylor (total intangible) methodology'sinin **direct application'ı**. Glamour firms Lev-Srivastava'nın merkezi: business services (software), pharma, electronics — scalable intangible assets + network effects + first-mover advantage; 2007-2018 highest profitability since 1970 [Figure 9]. NDX evren = ağırlıklı glamour firms (FAANG + pharma + biotech). NDX strateji yapısal foundation 3. ayağı (post-2010 crisis context layer); Lev-Sougiannis methodology hub + Peters-Taylor total q proxy + Lev-Srivastava post-2010 application = **3-katmanlı F bloğu hierarchy tamamlandı**. | **✅** NDX strateji yapısal foundation 3. ayağı |

**Strateji tasarımına net implikasyon:**

1. **Top-N ⚠️ ama dengeleyici 4 bulgu:**
   - Paper return prediction değil ama Logit Table 1 escape attributes
     (intangibles + capex + sales growth + debt) cross-section signal
     olarak kullanılabilir; Faz 3 strategy spec'inde **value-trap-
     avoidance filter** baseline (Q45 yeni).
   - **Q21 (combined methodology) + Q23 (NDX intangibles q-factor) ile
     bağlantılı**: Li-Mohanram combined F&V/P + G&V/P + adjusted MB
     methodology integration Faz 2 sentez.
   - Adjusted book value methodology **doğrudan Faz 3 backtest spec'inde**:
     HML factor inşası standard BV yerine adjusted BV (Lev-Sougiannis +
     Peters-Taylor + Lev-Srivastava methodology entegrasyonu) ile.
   - Logit escape attributes Faz 3 spec'i için **iki yorum boyutu**:
     (a) standalone "value escape predictor" screen, (b) F-Score / G-Score
     combined yaklaşımına ek katman.

2. **Q1 fully-answered: S&P 500 value post-2000 TAM CEVAP**:
   - 1989'dan beri faltering + 2007 crisis derinleşmesi + 2010s negatif
     + intangibles methodology adjusted strategy + 50% largest stocks
     focus → wiki'nin priori sorduğu temel sorunun definitive cevabı.
   - **Caveat**: 50% largest of CRSP all-stocks ≈ top 1500 firms; S&P
     500 = top 500 (subset); paper "top 1500" sample S&P 500'ün
     **superset proxy'si**, exact S&P 500 değil.
   - **Faz 3 implikasyon**: S&P 500 strategy spec'inde **vanilla HML
     yetersiz**; intangibles-aware adjusted HML + value-trap-avoidance
     filter + post-2010 macro context.

3. **NDX strateji yapısal foundation 3 ayak tamam**:
   - 1. ayak: Lev-Sougiannis 1996 R&D capitalization methodology (Cycle 15)
   - 2. ayak: Peters-Taylor 2017 total intangible capital generalization
     (Cycle 16)
   - 3. ayak: Lev-Srivastava 2020 post-2010 value crisis application +
     adjusted strategy (Cycle 17)
   - **Tam Faz 3 NDX strategy spec methodology infrastructure hazır**
     (factor portfolio kanıtı için Faz 2'de Eisfeldt-Papanikolaou 2013
     değerlendirmesi).

## Limitler ve Caveats

1. **Paper return prediction yapmıyor — explanation + adjusted strategy
   methodology paperı**. Top-N decile-spread direct yok; Logit
   regression cross-section identification eder ama factor portfolio
   kanıtı sınırlı.

2. **Sample sonu 2018** — Modern dönem (post-2018 FAANG era + COVID +
   AI 2019-2024) Lev-Srivastava methodology replikasyonu yok. Q44 yeni:
   modern data ile out-of-sample test gerekli.

3. **Mean reversion slowdown decomposition** — Paper iki mekanizma
   (intangibles + macro) birlikte sunuyor; ayrı ayrı katkı oranı
   decompose edilmemiş. Q43 yeni: intangibles-only adjusted methodology
   mean reversion slowdown'u ne ölçüde absorb eder?

4. **50% largest focus Section 8-11'de — caveat**: Paper subsequent
   analyses (mean reversion + macro + escape) için top 1500 of CRSP
   all-stocks; S&P 500 (~500) subset. **S&P 500 spesifik test yok**;
   adequate proxy ama tam S&P 500 evren değil.

5. **Adjusted methodology infrastructure dependent**:
   - R&D capital perpetual inventory: Lev-Sougiannis methodology
   - SG&A intangibles allocation: Enache-Srivastava 2018 + Peters-Taylor
     θ=30% paralel
   - Paper kendi dataset'inde uygular ama bu adjustments'ları yapan
     replicable code/data wiki'de yok; Faz 3 backtest spec için
     methodology rebuild gerekli (bu zaten F bloğu kapanış sentezinden
     açık).

6. **Causal vs correlational distinction**: Paper "two reasons" sunar
   (intangibles + macro) ama causal identification testi yok; her iki
   mekanizma post-2007 dönemde **birlikte gözlenir**. Mean reversion
   slowdown intangibles bias'in **mekanizmasının kendisi mi yoksa
   bağımsız bir post-2007 olgu mu** open question.

7. **Bazı sektörler "value sektör" olarak sınıflandırılırken survival
   bias**: Banking, retail, utilities 2007-2018 dönem-spesifik value;
   1970-1989'da bu sektörler value sınıflandırması farklıydı. Cross-
   sectional sektör compositional shift paperda partial discussion
   ediliyor [Section 9].

## Çelişkiler/Tartışmalar

> ⚠️ **Lev-Srivastava 2020 ↔ FF15 HML redundancy bulgusu (potansiyel
> çelişki adayı, scope-dependent):**
> - **FF15 [Tablo 6, s.19]**: HML 5-faktör altında redundant (a≈0,
>   t≈0); FF5 + 4 factor HML'ı span ediyor.
> - **Lev-Srivastava 2020 [Section 5]**: HML adjusted methodology
>   (intangibles-aware) ile 39 yılın 34'ünde conventional HML'i geçer
>   → adjusted HML primum gerçek; vanilla HML decay'i intangibles
>   bias'a bağlı.
>
> **Çelişki değil, scope-dependent**:
> - FF15: vanilla HML measurement (reported BV / market) FF5 redundant
> - Lev-Srivastava: adjusted HML (adjusted BV / market) primum hayatta
> İki paper farklı methodology üzerinde sonuç veriyor; **aynı vanilla
> HML için aynı şeyi söylüyor olabilir** (FF15 vanilla redundant; Lev-
> Srivastava vanilla 1990s-2018 negatif decay). Adjusted versiyonun FF5
> altında redundant olup olmadığı modern test gerekli (Faz 2 aday).
> [[meta/contradictions]]'a eklenmedi (paralel methodology, complementary
> finding).

> ⚠️ **Lev-Srivastava 2020 ↔ Lakonishok-Shleifer-Vishny 1994 (LSV) yorumu
> (extension, çelişki değil):**
> - **LSV 1994**: Value premium = investors' "extrapolation bias" —
>   misinterpreting temporary good/bad sales/earnings streaks as
>   long-term trends → mean reversion gains
> - **Lev-Srivastava 2020 [Section 7-8]**: LSV mean reversion mechanism
>   **post-2007 yavaşlamış**; intangibles bias mispricing source ekleyici;
>   LSV mekanizması korunur ama post-2007 attenuated
> Paper [s.16] LSV'i extension ile builds on, çelişki değil.

> ⚠️ **Lev-Srivastava 2020 ↔ Cochrane 2011 mathematical equivalence
> framing**:
> Paper "intangibles bias" + "mean reversion slowdown" mekanizmalarını
> **mispricing yorumu**'nda sunar (post-2007 macro shocks ⇒ value firms
> trapped ⇒ price reversal yavaşlar). Cochrane 2011 mathematical
> equivalence çerçevesinde aynı bulgu **risk premium** yorumuna eşdeğer
> (post-2007 high risk premia value firms için). Wiki taraf tutmaz —
> mathematical equivalence (Cochrane).

## İlgili Sayfalar

### Concepts
- [[concepts/intangibles_adjusted_accounting]] — F bloğu hub; methodology
  hierarchy 3. satır eklendi; 3-katmanlı sentez (R&D-only → total →
  post-2010 application)
- [[concepts/value_premium]] — Cycle 17 yapısal zenginleşme (izole
  concept çözümü); Lev-Srivastava ana bulguları + risk-vs-mispricing
  3. yorum boyutu (intangibles measurement-error mispricing)
- [[concepts/post_publication_decay]] — HML decay-adjusted spread
  tablosuna Lev-Srivastava intangibles-aware versiyon alternatif
  satır; HML-spesifik decay aggregate'tan daha agresif kanıt
- [[concepts/factor_model]] — adjusted HML factor inşa methodology
  (FF3 / FF5 framework içinde intangibles-aware revision)

### Papers
- [[lev_sougiannis_1996_rd_capitalization]] — F bloğu #1; aynı yazar
  (Baruch Lev) 24 yıl sonraki güncellemesi; R&D capitalization
  methodology origin
- [[peters_taylor_2017_intangible_capital]] — F bloğu #2; total
  intangible capital generalization; Lev-Srivastava SG&A allocation
  methodology paralel (Enache-Srivastava 2018 + Peters-Taylor θ=30%
  paralel)
- [[eisfeldt_papanikolaou_2013_organization_capital]] — **Cycle 25
  yeni**; F bloğu **4. ayak (factor portfolio direct evidence)**;
  Lev-Srivastava methodology infrastructure (adjusted BV) içinde
  organization capital component dahil; Eisfeldt-Papanikolaou OC
  factor Lev-Srivastava adjusted HML methodology'sine entegre
  edilebilir (factor portfolio overlay layer); F bloğu 4-katmanlı
  hierarchy (Lev-Sougiannis Knowledge + Eisfeldt-Papanikolaou
  Organization + Peters-Taylor Total + Lev-Srivastava Application);
  Q41 fully-answered.
- [[famafrench1993_three_factor]] — HML methodology origin; Lev-Srivastava
  Fama-French 2003 paralel inşa methodology kullanır
- [[famafrench2015_five_factor]] — HML redundancy bulgusu; Lev-Srivastava
  adjusted HML alternative (scope-dependent çelişki adayı)
- [[li_mohanram2019_quality_value]] — F&V/P + G&V/P combined intangibles-
  aware revize gereği güçlendirildi; Q21 + Q23 ile bağlantılı
- [[mclean_pontiff_2016_post_publication_decay]] — 82 anomaly aggregate
  decay; HML-spesifik decay Lev-Srivastava ile aggregate'tan daha
  agresif kanıt
- [[asness_frazzini_pedersen_2019_qmj]] — **Cycle 19 ek**; uyumlu
  kanıt zinciri: Lev-Srivastava [Figure 9] glamour firms 2007-2018
  highest profitability since 1970 + QMJ "quality stocks low value
  exposure" (Section 8 QMJ-HML negative correlation). NDX glamour-
  heavy evren yapısal olarak QMJ "long" tarafına denk geliyor; QARP
  framework Lev-Srivastava decay açıklaması + Asness quality-value
  combined paradigm birlikte Faz 3 strategy spec için anchor.

### Factors
- [[HML]] — post-2010 performance crisis explicit kanıt; adjusted HML
  alternative inşa
- [[F_Score]] — F&V/P combined intangibles-aware revize gereği
- [[G_Score]] — G&V/P combined intangibles-aware revize gereği
- [[QMJ]] — **Cycle 19 ek**; QMJ Profitability dimension glamour
  firms 2007-2018 highest profitability paterniyle uyumlu; QARP
  framework Lev-Srivastava decay context + Asness quality combined

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q1 fully-answered (Cycle 17)]** S&P 500 value post-2000:
  Lev-Srivastava 50% largest stocks focus + decade-by-decade returns
  (1970s +102% → 2010s NEGATIVE) + iki mekanizma decomposition +
  adjusted methodology dramatic effect → wiki priori sorusunun definitive
  cevabı. Caveat: 50% largest of CRSP all-stocks ≈ top 1500; S&P 500
  ≈ top 500 (subset); adequate proxy.

- **[Q23 partial-stronger ileri (Cycle 17)]** NDX intangibles q-factor
  span: F bloğu 3 ayak tamamlandı; methodology infrastructure hazır.
  Modern q-factor + Peters-Taylor entegrasyonu yapan paper hala wiki'de
  yok (Faz 2 aday).

- **[Q26 partial-stronger ileri (Cycle 17)]** Tech firma accrual R&D
  distortion: 3-katmanlı methodology (Lev-Sougiannis R&D-only +
  Peters-Taylor total + Lev-Srivastava post-2010 application) tam;
  Q26 kapanışına çok yakın.

- **[Q40 partial-stronger (Cycle 17)]** Peters-Taylor SG&A θ=30% NDX
  kalibrasyon: Lev-Srivastava Enache-Srivastava 2018 referansla SG&A
  allocation kullanıyor; Peters-Taylor θ=30% paralel kalibrasyon. Lev-
  Srivastava paper "intangibles part of SG&A" demiyor θ değeri explicit
  ama Peters-Taylor ile uyumlu methodology.

- **[Q41 partial-stronger (Cycle 17)]** 3-paper horse race: F bloğu 3
  ayak tamamlandı (Lev-Sougiannis + Peters-Taylor + Lev-Srivastava);
  Eisfeldt-Papanikolaou 2013 organization-only direct factor portfolio
  hala eksik (Faz 2 aday) — 4-way horse race tam.

### Yeni Q'lar (Q43, Q44, Q45):

- **[Q43 yeni]** Mean reversion slowdown post-2007 macro-economic vs
  intangibles ayrıştırma: Lev-Srivastava paper iki mekanizma birlikte
  sunuyor; ayrı ayrı katkı oranı decompose edilmemiş. Faz 2 design
  decision: intangibles-only adjusted methodology mean reversion
  slowdown'u ne ölçüde absorb eder? Causal vs correlational separation
  test paperda yok.

- **[Q44 yeni]** Post-2018 (FAANG era + AI dönemi 2019-2024) value
  premium replikasyonu: Lev-Srivastava sample sonu 2018; modern dönem
  (post-2018, 2020 COVID, 2022-2024 AI boom) intangibles-aware value
  strategy out-of-sample. Modern data Chen-Zimmermann 2022 (Tier 2 #41)
  + JKP 2023 (Tier 2 #44) ile replikasyon.

- **[Q45 yeni]** Value-trap-avoidance filter Faz 3 strategy spec için:
  Lev-Srivastava Logit Table 1 escape attributes (intangibles + capex +
  sales growth + debt) signal seti S&P 500 strategy'de **filtre olarak
  nasıl entegre edilir**? Adaylar:
  1. Standalone "value escape predictor" screen
  2. F-Score / G-Score combined yaklaşımına ek katman
  3. F&V/P + escape filter cross-product
  4. Logit coefficient'leri factor portfolio weight olarak
  Faz 3 design decision; literatürde sistematik karşılaştırma yok.

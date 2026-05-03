---
type: paper
authors: [Fama, Eugene F., French, Kenneth R.]
year: 1993
title: "Common risk factors in the returns on stocks and bonds"
venue: "Journal of Financial Economics 33 (1993) 3-56"
url: https://rasmuseconomics.com/Risk_factors.pdf
local_path: raw/papers/fama_french_1993.pdf
ingested: 2026-04-27
tags: [factor_model, value, size, market_factor, foundational, large_cap_relevant]
status: ingested
cycle_37_note: "FF ailesi methodology continuity 1993→2008→2015 üçüncü halka [[papers/fama_french_2008_dissecting_anomalies]] Cycle 37 ✓ size-partition methodology evolution; FF 2008 [Tablo IV] B/M big-stock 0.17 (t=1.79) zayıf relation FF06b post-1962 US-only — FF93 HML 1963-1991 sample-spesifik kontekstinde size-conditional finding"
---

# Fama-French (1993) — Common Risk Factors in Stocks and Bonds

> 📝 **Atıf konvansiyonu:** Bu sayfa boyunca `[Tablo N]` makalenin numaralı tablolarına,
> `[PDF p.N]` ise `raw/papers/ff1993_pages/pNN.png` rendering'lerinin sayfa numarasına
> atıfta bulunur (1-indexed, JFE 33 (1993) 3-56'nın sırasıyla pp.3-56'sına eşler).
> Cross-check için ilgili PNG açılabilir.

## TL;DR

Fama-French üç-faktör hisse modeli (`MKT-RF`, `SMB`, `HML`) ve iki-faktör tahvil modelinin
(`TERM`, `DEF`) ilk açıklaması. 25 size×book-to-market portföyü ile NYSE/AMEX/NASDAQ
1963-07 / 1991-12 örnekleminde (342 ay) test edilir. Üç-faktör hisse modeli 25 portföyün
ortalama getirilerinin kesitini açıklar (R² ekseriyetle 0.83-0.97 [Tablo 4, PDF p.20]),
CAPM'in tek-beta yapısının açıklayamadığı size ve değer (book-to-market) etkilerini
yakalar. **HML aylık ortalama prim 0.40% (t=2.91)** ve **SMB 0.27% (t=1.73)** olarak
raporlanır [Tablo 2, PDF p.13]. Bu sayfa **wiki'nin factor model vocabulary kökü**;
sonraki paper sayfaları HML / SMB tanımları için bu sayfaya değil, ayrı entity sayfalarına
([[HML]], [[SMB]], [[MKT_RF]]) link verir.

## Tek Cümle Tezi

Hisse senedi getirilerindeki ortak değişkenliği `MKT-RF`, `SMB` ve `HML` mimicking
portföyleri yakalar; bu üç faktör 25 size×BE/ME portföyünün ortalama getiri kesitini
açıklar ve dolayısıyla CAPM'in başaramadığı yere bir asset-pricing modeli oturtur.

## Ortaya Konan Sinyaller / Faktörler

Üçü hisse, ikisi tahvil olmak üzere beş faktör tanımlar:

- **`MKT-RF`** — value-weighted CRSP NYSE/AMEX/NASDAQ market portföyü eksi 1-aylık
  T-bill getirisi [PDF p.10]. → [[MKT_RF]]
- **`SMB`** ("Small Minus Big") — 6-portföylü 2×3 size×BE/ME zero-investment
  portföyünden inşa edilen size mimicking faktörü [PDF p.9]. → [[SMB]]
- **`HML`** ("High Minus Low") — aynı 6 portföyden inşa edilen book-to-market
  mimicking faktörü [PDF p.9]. → [[HML]]
- **`TERM`** — uzun-vadeli devlet tahvili getirisi eksi 1-aylık T-bill (term structure
  risk). **Scope dışı** (hisse stratejisi tasarımı için) — bu wiki'de ayrı sayfa
  açılmadı. [PDF p.7]
- **`DEF`** — uzun-vadeli kurumsal tahvil getirisi eksi uzun-vadeli devlet tahvili
  (default risk). **Scope dışı.** [PDF p.7]

### Faktör inşası — HML ve SMB için 6 portföylü 2×3 sıralama [PDF p.8-9]

Haziran sonunda her yıl t için, NYSE breakpoint'leri kullanılarak:

- **Size sıralaması (2 grup):** NYSE median ME (June t-end). NYSE/AMEX/NASDAQ tüm
  hisseleri "Small (S)" veya "Big (B)" olarak işaretle.
- **BE/ME sıralaması (3 grup):** NYSE 30-uncu ve 70-inci yüzdelikleri. Hisseler "Low (L)",
  "Medium (M)", "High (H)" olarak işaretlenir.
  - **BE** = book equity, fiscal year-end of t-1
  - **ME** = market equity, December-end of t-1
- 2×3 = 6 portföy: S/L, S/M, S/H, B/L, B/M, B/H. Value-weighted aylık getiri.
- **SMB** = (S/L + S/M + S/H)/3 − (B/L + B/M + B/H)/3
- **HML** = (S/H + B/H)/2 − (S/L + B/L)/2

Negatif BE'li firmalar dışlanır [PDF p.8]. Finansal firmalar dışlanır (yüksek
leverage finansallarda normaldir, distress sinyali değildir) [PDF p.8].

### Test evreni — 25 size×BE/ME portföyü [PDF p.8-9]

Bağımsız NYSE-quintile sortları size ve BE/ME üzerine, 5×5 = 25 value-weighted aylık
portföy. Bu 25 portföy regresyonların **bağımlı değişkenleri**.

## Empirik Sonuçlar (sayılarla)

### Örneklem [Tablo 2, PDF p.13]

- Evren: NYSE / AMEX / NASDAQ, finansal hisseler hariç
- Dönem: 1963-07 ile 1991-12 (342 aylık gözlem)
- Tahvil verisi: CRSP Government Bond File + Ibbotson Associates corporate bonds

### Faktör portföylerinin özet istatistikleri (% aylık) [Tablo 2, PDF p.13]

| Faktör | Mean | Std | t(mean) |
|---|---|---|---|
| `RM-RF` | 0.43 | 4.54 | 1.76 |
| `SMB` | 0.27 | 2.89 | 1.73 |
| `HML` | 0.40 | 2.54 | 2.91 |
| `TERM` | 0.06 | 3.02 | 0.38 |
| `DEF` | 0.02 | 1.60 | 0.21 |

> 📝 HML 0.40%/aylık (t=2.91) makalede "büyük, hem pratik hem istatistiksel olarak"
> ifadesiyle vurgulanır [PDF p.13]. SMB t-stat'ı 1.73 — 5% iki-yanlı standart eşiği
> aşmaz; faktörün "primium" olduğu iddiası tek başına bu örneklemde marjinaldir.

### Faktör korelasyonları [Tablo 2, PDF p.13]

| | `RM-RF` | `SMB` | `HML` |
|---|---|---|---|
| `RM-RF` | 1.00 | 0.32 | -0.38 |
| `SMB` |  | 1.00 | -0.10 |
| `HML` |  |  | 1.00 |

> 📝 `HML` ile `RM-RF` arasında −0.38'lik korelasyon, value tilt'in piyasaya karşı
> defansif eğilim taşıdığını gösterir [PDF p.13]. `SMB` ve `HML` arasında −0.10
> ile yaklaşık ortogonal; bu factor zoo argümanlarının (bkz. [[meta/data_gaps]]
> "redundant factors") önünü açar.

### Üç-faktör hisse modeli — 25 portföy time-series [Tablo 4, PDF p.20]

`R(t) - RF(t) = a + m·(RM-RF)(t) + s·SMB(t) + h·HML(t) + e(t)`

- **R²**: 25 portföyün geneli **0.83-0.97** [Tablo 4, PDF p.20]
- `m` slope (market loading): tüm 25 portföyde 0.94-1.10 civarı, neredeyse 1
- `s` slope (size loading): "Small" tarafta yüksek (>1.4), "Big" tarafta sıfıra
  yakın veya negatif — monoton azalma
- `h` slope (BE/ME loading): "Low" tarafta negatif (~-0.3), "High" tarafta pozitif
  (~+0.7) — monoton artış [Tablo 4, PDF p.20]
- Intercept'ler (`a`): 25 portföy için çoğu istatistiksel olarak sıfırdan ayırt
  edilemiyor; üç-faktör modeli "average returns'ün cross-section'ını açıklar"
  ifadesinin temeli [PDF p.21, sonuç p.51]

### TERM ve DEF tek başına hisse açıklayamıyor [Tablo 3, PDF p.15]

`R(t) - RF(t) = a + b·TERM(t) + c·DEF(t) + e(t)`

- 25 hisse portföyü için R² düşük (~0.06-0.21)
- Intercept'ler büyük — yani size ve BE/ME etkilerini yakalamayan model

### Beş-faktör birleşik (hisse + tahvil) [Tablo 6, PDF p.22-23]

`R(t)-RF(t) = a + b·TERM + c·DEF + m·(RM-RF) + s·SMB + h·HML + e`

- 25 hisse portföyü için 5-faktör model 3-faktör hisse modeline kıyasla R²'yi
  marjinal yükseltir; `b` ve `c` slopeları küçük → hisse getirilerinin TERM/DEF
  varyasyonu zaten `RM-RF` üzerinden absorbe ediliyor [PDF p.27]
- 7 tahvil portföyü için 5-faktör model R²'yi 0.93+ seviyelerine çeker; hisse ve
  tahvil getirilerinin **ortak** common variation'ı ortaya çıkar [PDF p.30]

### Ortogonal market faktörü regresyonu [Eq. (1), PDF p.27]

`RM-RF = 0.50 + 0.44·SMB − 0.63·HML + 0.81·TERM + 0.79·DEF + e`
        `(2.55) (6.48)   (-8.23)    (9.09)    (4.62)`
R² = 0.38, σ = 1.97% per month [PDF p.27]

> 📝 Bu regresyon `RM-RF` üzerine SMB ve HML'in incremental information taşıdığını
> ve aynı zamanda piyasanın `TERM` ve `DEF`'le güçlü bağlantısını gösterir.

### Cross-section değerlendirmesi [§5, PDF p.31; sonuç p.51]

Üç-faktör hisse modeli (`RM-RF`, `SMB`, `HML`) 25 size×BE/ME portföyünün ortalama
getiri kesitini açıklar; CAPM'in (`RM-RF` tek başına) yapamadığı, size ve BE/ME
patternlerinin yakalanmasını başarır [PDF p.51].

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Paper "factor model" — 25 size×BE/ME portföyünün asset pricing testlerini yapar; "top-N stock selection" formülasyonu yok. Mimicking-portföy yaklaşımı tüm long-leg / short-leg dağılımını kullanır | N/A — vocabulary paperı; stock selection bağlamı sonraki paperlardadır |
| **Annual rebalance** | HML ve SMB **yıllık** rebalance (Haziran sonu, NYSE breakpoint'leriyle) [PDF p.8-9]. Bağımlı değişken portföyleri aylık getirilerle test edilir, ama portföy formation yıllık | ✅ doğrudan fit |
| **Large-cap evrene transfer** | NYSE/AMEX/NASDAQ **all-stocks** evren; large-cap-only kalibrasyon yok. NYSE breakpoint asimetrisi nedeniyle "Big" tarafı NYSE/AMEX/NASDAQ tüm büyük caplerini içerir ama HML/SMB factor zaman serisi büyük ölçüde mikrokap dinamiğini yansıtır | ⚠️ **UYARI: large-cap-only kalibrasyon yapılmamış**; SMB özellikle S&P 500/NDX evrene transferli değil — bkz. [[meta/open_questions]] Q12 |
| **NDX intangibles / growth firms** | Finansal firmalar dışlanmış [PDF p.8]. Tech/growth firmalar evrende mevcut ama BE/ME tanımı **R&D-intangibles için kalibre değil** — book equity tarihi maliyeti yansıtır, R&D giderleştirilir → tech firma BE/ME yapay olarak düşük | ⚠️ **UYARI: intangibles düzeltmesi yok**; Lev-Sougiannis 1996 (Tier 2 #26) ve Peters-Taylor 2017 (Tier 2 #27) ile cevaplanacak |

**Strateji tasarımına net implikasyon:** FF93 wiki'nin **factor model
vocabulary'sinin** ve baseline asset-pricing çerçevesinin kaynağıdır. Strateji
tasarımının kendisi bu paperdan doğrudan çıkmaz — ama benchmark olarak strateji
portföyleri MKT-RF/SMB/HML üzerine regresyonla test edilecek (alpha üretiyor mu?).
Ham HML faktörünün primum'u "saf value tilt" olarak strateji hipotezimiz değil
([[winner_loser_identification]] yaklaşımı tercih edilir).

## Limitler ve Caveats

- **NYSE breakpoint'lerinin asimetrisi:** Size breakpoint'i NYSE median'ı.
  NYSE/AMEX/NASDAQ tüm hisseleri içeren evrende NYSE median'ın altında çok daha
  fazla "small" hisse vardır → SMB ağırlıklı olarak **çok küçük cap**'lerin
  performansını yansıtır [PDF p.8-9]. **Large-cap (S&P 500 / Nasdaq 100) evrenleri için
  SMB'in marjinal etkisi sınırlı olabilir** — bu wiki'nin amacı için kritik bir nüans.
- **Finansal firmalar dışlanmış [PDF p.8]:** Bu, S&P 500 stratejisi tasarımında
  bilinçli bir karar gerektirir (financials sektörü S&P 500'ün ~%13'ü).
- **Look-ahead düzeltmesi [PDF p.8]:** BE/ME'de book equity *fiscal year t-1
  sonu*, market equity *Aralık t-1 sonu*; sıralamalar Haziran t'de uygulanır.
  Bu 6-aylık gap reporting lag varsayımıdır. Modern PIT data ile karşılaştırılmalı
  (bkz. [[meta/data_gaps]] "PIT vs. as-reported").
- **Örneklem dönemi 1963-1991:** Post-1991 out-of-sample performans bu paperda yok.
  Post-publication decay için → [[meta/open_questions]] Q5.
- **Survivorship:** Paperda CRSP+COMPUSTAT delisting'i nasıl ele aldığını detaylı
  tartışmaz; modern replikasyonlar için [[meta/data_gaps]] "survivorship".
- **Asset-pricing yorumu vs. anomaly yorumu:** Yazarlar açıkça notlar [PDF p.53]:
  size ve BE/ME etkilerinin ekonomik temelinin ne olduğu — risk premia mı, mispricing
  mi — bu paperda kapanmaz, açık soru bırakılır.
- **t-stat'lar i.i.d. varsayımı altında:** Newey-West veya başka HAC düzeltmesi
  yapılmıyor (paperda tartışılmadı).

## İlgili Sayfalar

### Bu paperın ürettiği faktör entity sayfaları
- [[HML]] — book-to-market değer faktörü
- [[SMB]] — size faktörü
- [[MKT_RF]] — piyasa fazla getirisi faktörü

### Kavramsal
- [[factor_model]] — multi-factor asset pricing kavramı, time-series regression metodolojisi

### FF93'ün üzerine inşa eden / sorgulayan ingest edilmiş paperlar
- [[famafrench2015_five_factor]] — RMW (profitability) ve CMA (investment) eklendi;
  HML redundant bulundu
- [[carhart1997_four_factor]] — UMD (momentum) eklendi; FF3'ün momentum-sorted
  portföylerdeki açığını kapatır
- [[piotroski2000_f_score]] — value premium high-BM evrende daha rafine ele
  alınabilir: HML uzun bacağında diferensiyel F-Score skoruyla ekstra +0.230
  yıllık spread [Tablo 3, s.16]; FF93'ün ham value tilt'inin "winner-loser
  identification" ile genişletilmesi (bkz. [[winner_loser_identification]])
- [[mohanram2005_g_score]] — growth muadili: HML *kısa bacağında* (low-BM)
  diferensiyel G-Score ile +21.2% yıllık size-adj spread [Tablo 4, s.15-16];
  HML'in "growth firmaların hepsi underperformer" ham yorumunu rafine eder —
  growth firma içinde de winner-loser ayrımı mümkün

### FF93'ü çerçeveleyen survey
- [[cochrane2011_discount_rates]] — FF93'ü "order to chaos" olarak tanımlar
  [s.11-12]; HML'in başarısı "absence of beta is the heart of the value puzzle"
  yorumu [s.12]

### Henüz wiki'de olmayan, FF93'le ilgili paperlar
- Hou-Xue-Zhang (2015, 2020) — q-factor model + replication kanıtları

### Wiki'ye gelecek paper'ların bu sayfaya nasıl link vermesi beklenir

Sonraki ingest'ler için convention:
- Bir paper "FF3 modelini test ediyor / replicate ediyor / extend ediyor" diyorsa
  → bu paper sayfasına link, ayrıca ilgili faktör entity sayfasına ([[HML]] vs.) link.
- Bir paper "value premium" veya "size premium"dan bahsediyorsa → entity sayfasına
  ([[HML]] / [[SMB]]) link, FF93 paper sayfasına direkt link **gerekmiyor** (entity
  sayfası zaten origin olarak buraya işaret ediyor).
- Bir paper FF93'ün spesifik bir tablosuna / iddiasına itiraz ediyorsa → bu paper
  sayfasının "Çelişkiler" bölümüne `> ⚠️ challenged by [[X]]` notu eklenir +
  [[meta/contradictions]]'a giriş.

## Çelişkiler / Tartışmalar

> ⚠️ **HML faktörünün incremental information taşıdığı iddiası FF15 tarafından
> sorgulanır:** FF93 [Eq.(1), PDF p.27] HML'in `RM-RF`, `SMB`, `TERM`, `DEF`
> üzerine spanning'inde HML t-stat = −8.23 (büyük) — yani HML 3-faktör/2-bond
> seti içinde span edilmez. Ancak [[famafrench2015_five_factor]] Tablo 6 [s.19]
> RMW ve CMA eklendiğinde HML intercept'i sıfıra düşer (a=−0.04%, t=−0.47, 2x3
> inşa). Bu **çelişki değil, kanıt seti genişlemesi** — RHS faktör seti farklı.
> Detay [[meta/contradictions]] dosyasında.

### HML post-2010 performance crisis (Cycle 17 ek — Lev-Srivastava ingested)

[[lev_srivastava_2020_value_failure]] FF93 HML methodology'sinin
post-2010 dönemde **çöktüğünü** decade-by-decade decomposition ile
gösterir:

| Decade | Vanilla HML $1 → end value | Return |
|---|---|---|
| 1970s | $2.02 | +102% |
| 1980s | $1.75 | +75% |
| **1990s** | **$0.90** | **-10%** |
| 2000-2006 | brief resurgence | tech bubble shorting |
| **2007-2018** | **negative** | "yielded negative returns" |

**1989'dan beri faltering** — "post-2007 collapse" yorumu yetersiz;
faltering 1989 başlangıç, 2007 financial crisis sonrası **derinleşti**.

**Iki sebep** [Lev-Srivastava ana tezi]:
1. **Accounting deficiencies (intangibles expensing)**: 1980'lerden
   itibaren intangibles proliferation → reported BV mismeasurement →
   adjusted methodology dramatic effect (39 yılın 34'ünde conventional'ı
   geçer)
2. **Mean reversion slowdown post-2007**: 2007 financial crisis bank
   lending contraction + consumer demand fall → value firms (banking,
   retail, insurance, wholesale, utilities) trapped

**Wiki yorumu**: FF93 vanilla HML methodology'i (reported BV / market)
**Lev-Sougiannis 1996 + Peters-Taylor 2017 + Lev-Srivastava 2020 F bloğu
3 ayak methodology infrastructure** ile **adjusted HML** (adjusted BV /
market) versiyonuna geçirilmeli. Faz 3 NDX strategy spec'inde vanilla
HML reject; adjusted HML baseline.

**Caveat (Q1 fully-answered subset framing)**: Lev-Srivastava Section
8-11'de "50% largest stocks focus" [s.16 footnote 13] — top 1500 of
CRSP all-stocks; S&P 500 ≈ top 500 ⊂ subset; **adequate proxy**, exact
S&P 500 değil. Detay [[concepts/value_premium]] post-2010 collapse
bölümü; [[meta/open_questions]] (Q1 fully-answered).

## HXZ 2020 Replication Status (Cycle 13 ek)

[[hou_xue_zhang_2020_replicating_anomalies]] [Tablo 4, s.25; Şekil 3]
FF93 faktörlerinin NYSE-VW replication durumu:
- **HML book-to-market (Bm):** klasik 0.59% (t=2.84) replicate sig;
  q-factor alpha 0.18% (t=1.15) **insig** — investment factor (I/A)
  span ediyor. Wiki için HML factor exposure proxy olarak
  kullanılabilir; standalone alpha kaynağı değil.
- **SMB:** specific HXZ rakamı paperdan teyit; HLZ Şekil 3 mark'i
  "never sig under multiple testing" + HXZ NYSE-VW under likely
  insig → **çift kanıt** SMB strateji için "target" değil.

Detay: [[concepts/anomaly_replication]] aggregate replication tablosu;
[[concepts/post_publication_decay]] dört darbe çerçevesi tablosu.

## HLZ Multiple-Testing Status (Cycle 12 ek)

[[harvey_liu_zhu_2016_multiple_testing]] [Şekil 3, s.22] FF93 faktörlerinin
multiple-testing-corrected durumu:
- **HML:** t=2.91 (1963-91) → BHY 1% (3.0) borderline; Bonferroni (3.78)
  **insig**. Paperin Şekil 3 mark'i HML'i sig her cutoff gösteriyor ama
  bu Fama-French 1992 versiyonu sample sonu güncellenmiş; FF93 origin
  rakamı borderline-MT hurdle'ı.
- **SMB:** t=1.73 (1963-91) → **never sig** under multiple testing
  (Bonferroni / Holm / BHY hepsi insig); HLZ Şekil 3 mark'i explicit
- **MKT-RF:** typical |t| ~3.0; borderline

Detay: [[concepts/multiple_testing]] aggregate tablosu;
[[concepts/post_publication_decay]] üç darbe çerçevesi.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- FF93 örneklemi 1963-1991. Post-1991 ve özellikle post-2000 dönemde HML primi ve
  SMB primi nasıl evrildi? → [[meta/open_questions]] (Q1) ve (Q11)
- SMB inşası NYSE breakpoint asimetrisi taşır → S&P 500 / Nasdaq 100 evrenleri için
  yeniden inşa gerekir mi? → [[meta/open_questions]] (Q12)
- Size ve BE/ME etkilerinin **ekonomik kaynağı** (risk vs. mispricing) FF93 tarafından
  açık bırakılır [PDF p.53] → [[meta/open_questions]] (Q1) ile bağlantılı
- **(Q11) fully-answered (statistical düzeyde):** SMB **never sig under
  multiple testing** ([[harvey_liu_zhu_2016_multiple_testing]] [Şekil 3]).
  FF93 t=1.73 marjinal sig'in MT-corrected kesin çürütülmesi. Wiki SMB
  factor exposure'ı strateji tasarımı için "target" değil; factor-model
  baseline'da kalır.

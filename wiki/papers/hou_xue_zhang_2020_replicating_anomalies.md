---
type: paper
authors: [Hou, Kewei, Xue, Chen, Zhang, Lu]
year: 2020
title: "Replicating Anomalies"
venue: "Review of Financial Studies 33 (5), 2019-2133 (NBER WP 23394, May 2017)"
url: https://www.nber.org/papers/w23394
local_path: raw/papers/hou_xue_zhang_2020_replicating_anomalies.pdf
cycle_35_note: "q-factor model formal origin paper [[papers/hou_xue_zhang_2015_q_factor]] Cycle 35 ✓; 447 anomaly empirical replication HXZ 2015 q-factor lens kullanır; literature continuity hattı 2. → 3. halka"
cycle_37_note: "NYSE-VW + microcap-arınmış convention FF 2008 origin paterni paralel [[papers/fama_french_2008_dissecting_anomalies]] Cycle 37 ✓; HXZ 2020 [s.3] MP eleştirisi 'NYSE-Amex-NASDAQ breakpoints + equal-weights' methodology farkının kökü FF 2008'in microcap-influence dokümantasyonunda (FF 2008 microcaps ~60% stocks ama ~3% market cap; cross-section dispersion of anomaly variables largest in microcaps)"
cycle_38_note: "HXZ 2020 Cop dört darbe 4/4 hayatta kalan empirical validation; Cop methodology standalone origin paper [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓; HMXZ + HXZ 2020 q-factor lens Cop validation Ball-GLN origin'inden methodology continuity Profitability zinciri 4. halka"
cycle_39_note: "HXZ 2020 73 anomaly set Stambaugh-Yuan 4F (MKT+SMB+UMO1+UMO2) outperforms validation [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; Stambaugh-Yuan [Section 3] HXZ 2015a/b 73 anomaly larger set'inde 4F outperforms HXZ4 + FF5; mispricing-based factor model q-factor investment-based methodology paralel"
ingested: 2026-04-30
tags: [replication_crisis, anomaly_replication, NYSE_breakpoint, value_weight, microcap_filter, q_factor_model, p_hacking, epistemic_backbone, D_blok_3]
status: ingested
---

# Hou, Xue & Zhang (2020) — Replicating Anomalies

> 📝 **Atıf konvansiyonu:** `[Tablo N]`, `[Şekil N]` ve `[s. X]` NBER WP
> (May 2017) sayfa numarası. Embedded text extract:
> `raw/papers/hou_xue_zhang_2020_replicating_anomalies.txt`. RFS 2020
> final yayın sayfa numaraları farklı, tablo numaraları aynı.

> 📝 **D bloğunun #3'ü** — replication / multiple testing / decay
> çatı kategorisinin empirik replikasyon ayağı. Cycle 11'de
> [[mclean_pontiff_2016_post_publication_decay]] (behavioral decay
> bacağı) + Cycle 12'de [[harvey_liu_zhu_2016_multiple_testing]]
> (statistical FDR bacağı) ingest edildi; bu paper **üçüncü bacak
> (empirik replikasyon)** kuruyor. Wiki epistemik omurgası **çift-bacak →
> üç-bacak** olarak genişliyor. Wiki amaç evrenleri (S&P 500 + NDX)
> için **NYSE breakpoint + value-weight** methodology default tercih.

## TL;DR

**447 anomaly variable** (57 momentum + 68 value-vs-growth + 38
investment + 79 profitability + 103 intangibles + 102 trading frictions),
1967-2014 sample. **NYSE breakpoint + value-weighted methodology**
microcap influence'ı arındırır (microcaps NYSE 20th percentile altı;
%3 market cap ama %60 stocks).

**Headline rakamlar [Abstract, s.1-2]:**

- **286 anomaly (64%) insig at klasik 5% level** (|t| < 1.96)
- **380 anomaly (85%) insig at HLZ-cutoff t > 3.0**
- 161 sig anomaly içinde **q-factor model 115 alpha'yı insig bırakır**;
  **46 q-factor alpha sig** (11 with t > 3) [Tablo 4, s.25-29]
- Trading frictions/liquidity **biggest casualty: 95/102 (93%) insig**
- **Distress anomaly virtually nonexistent** (failure probability,
  O-Score, Z-Score, credit rating insig)

**Specific wiki-relevant findings:**
- **FF15 RMW (operating profits-to-book equity, Ope) insig** [s.10] —
  q-factor model'de RMW klasik 0.27% (t=2.58) ama q-factor alpha
  0.04% (t=0.42) **insig** [Tablo 4 ?, s.24] — ⚠️ wiki için kritik
  düzeltme (HLZ Cycle 12'de RMW 2x3 borderline / joint 4.09 sig idi;
  HXZ q-factor lens'inde RMW span ediliyor)
- **CMA klasik 0.34% (t=3.63)** ama **q-factor alpha 0.01% (t=0.32) insig**
  — q-factor I/A factor CMA'yı span ediyor ([[cooper_gulen_ion2018_asset_growth_factor_models]]
  uyumlu)
- **UMD klasik 0.67% (t=3.66)** ama **q-factor alpha 0.11% (t=0.43) insig**
  — momentum q-factor lens'inde span ediliyor
- **Sloan operating accruals q-factor alpha -0.54% (t=-3.77) sig kalır**
  [s.27] — accruals anomaly üç darbenin (MP + HLZ + HXZ) **HEPSİNDE**
  hayatta kalan nadir bulgu
- **Piotroski F-Score (Fq quarterly) q-factor alpha 0.13% (t=0.58) insig**
  [s.27] — Piotroski klasik sig ama q-factor span; HMXZ Security
  Analysis (Cycle 8) ile uyumlu
- **CGS asset growth replicates** (smaller magnitude than original
  Cooper-Gulen-Schill 2008) [s.5]
- **Richardson-Sloan-Soliman-Tuna 2005 total accruals (Ta) insig** [s.5]
  — ⚠️ Sloan 1996 accruals'ın **modern revisit'i (RSST 2005)** wiki'de
  ingest edilmemiş ama burada explicit çürütülüyor; Sloan 1996 hayatta,
  RSST 2005 değil
- **R&D-to-market (Rdm) q-factor alpha sig** [s.28] — intangibles
  category Q23 cevabı; NDX evrene transferli kritik kanıt
- **Earnings announcement abnormal returns (Abr)** q-factor alpha sig
  [s.27] — Piotroski 2000 [s.4-5] explicit referans; F-Score
  spread'in 1/6'sı earnings announcement penceresinde realize ediyor

> ⚠️ **Wiki için ana mesaj [s.31]:** "Capital markets are more efficient
> than previously reported." Anomaly literatürünün **çoğu (64-85%)**
> microcap-arınmış large-cap-aware methodology'de hayatta kalmıyor.
> Wiki amaç evrenleri (S&P 500 + NDX) için bu **muhafazakâr taraf**
> baseline.

## Tek Cümle Tezi

Akademik anomaly literatürü mikrocap'leri NYSE-Amex-NASDAQ breakpoints
+ equal-weight ile aşırı-temsil ederek p-hacking ile dolu; NYSE
breakpoints + value-weighted methodology ile 447 anomaly'nin %64-85'i
istatistiksel olarak anlamlı değil; **kapital piyasaları önceden
bildirilenden daha verimli**.

## Ortaya Konan Sinyal/Faktör

**Yeni empirik faktör YOK.** Bu paper bir **replication study** —
mevcut 447 anomaly'nin methodology-robust tekrar testi. Wiki'de bu
paperdan yeni `factors/*` sayfası açılmadı. Yerine **bir concept
sayfası açıldı:**

- [[concepts/anomaly_replication]] — concept; replication crisis
  literatür hattı (HXZ 2020 + JKP 2023 + Chen-Zimmermann 2022) +
  methodology farkları (NYSE breakpoint VW vs equal-weight all-stocks)
  + 447 anomaly replication rate by category + wiki ingested factors
  için aggregate replication tablosu + üç-bacak omurganın empirik
  replication ayağı

> 📝 **Cycle 13 kullanıcı kararı 1-2:** anomaly_replication ayrı concept
> sayfası açıldı (sayfa adı `replication_crisis` yerine
> `anomaly_replication` neutral terminoloji). Üç-bacak omurga sentezi
> [[concepts/post_publication_decay]] içinde tutulur (kullanıcı kararı 3,
> wiki'nin synthesis hub'u).

## Metodoloji

### 447 anomaly seçimi [s.2-3, Section 3.1]

6 kategoride 447 anomaly variable [Tablo 1, s.36+ Internet Appendix]:

| Kategori | # anomaly | Significance rate (5%) | Sig with t > 3 |
|---|---|---|---|
| **Momentum** | 57 | 37 sig (65%) | (paperdan teyit) |
| **Value-versus-growth** | 68 | 31 sig (46%) | |
| **Investment** | 38 | 27 sig (71%) | |
| **Profitability** | 79 | 33 sig (42%) | |
| **Intangibles** | 103 | 26 sig (25%) | |
| **Trading frictions** | 102 | 7 sig (7%) | |
| **Toplam** | **447** | **161 sig (36%)** | **67 with t > 3** |

> 📝 Toplam sig sayısı 161 = 447 − 286 (insig at 5%); t > 3 cutoff'ta
> 67 sig = 447 − 380.

### Methodology farkları

**HXZ 2020 standartı [s.2]:**
- **NYSE breakpoint** (NYSE-only ME percentile 20% altı microcap)
- **Value-weighted returns** (VW)
- High-minus-low decile = top decile − bottom decile (NYSE breakpoint)
- Microcap influence arındırılmış (microcaps %3 market cap ama %60
  stocks)

**Önceki literatür standartı [paper'ın eleştirisi]:**
- **NYSE-Amex-NASDAQ breakpoint** (microcap inclusive)
- **Equal-weighted returns** (EW)
- Fama-MacBeth regressions (microcap'lere lineer ağırlık)
- Yan-Zheng 2017, McLean-Pontiff 2016 EW standartı kullanır

**Sonuç farkı [s.2]:** Microcaps "have the highest equal-weighted average
returns and the largest cross-sectional standard deviations" → equal-
weighted methodologies anomaly profits'i şişiriyor.

### McLean-Pontiff 2016'ya explicit eleştiri [s.3]

> "McLean and Pontiff (2016) study the out-of-sample performance of 97
> anomalies, and find that their average high-minus-low returns decline
> out of sample and post publication. **However, McLean and Pontiff use
> NYSE-Amex-NASDAQ breakpoints and equal-weights in their tests.**"

> 📝 **Önemli wiki nüansı:** HXZ paper'ı MP 2016'nın yayınlanmış
> versiyonunda **97 anomaly** olduğunu söylüyor; wiki'deki MP paper
> sayfasında 82 anomaly (working paper Oct 2012) yazıyor. Yayınlanmış
> JF 2016 versiyonunda 97'ye genişletilmiş. Wiki paper sayfasına bu
> nüans eklenir.

### Harvey-Liu-Zhu 2016 ile complementary

[s.4]: "Reevaluating 296 significant anomalies in past published studies,
Harvey et al. report that 80–158 (27%–53%) are false discoveries."

HLZ multiple-testing framework + HXZ empirical replication **iki ayrı
mekanizma** ama aynı conclusion'a varıyor: "anomaly literatürünün büyük
kısmı false."

### Q-factor model performance [Section 4]

161 sig anomaly üzerinde q-factor model regression:
- 115 alpha insig at 5% level
- 150 alpha insig at t > 3
- **46 alpha sig** (11 with t > 3)
- GRS test 107 reject at 5% level, 72 at 1%

q-factor model bileşenleri:
- **Investment factor (I/A) klasik 0.45% (t=5.6) sig** [s.24]
- **ROE factor klasik 0.5%+ (t > 3) sig**
- Together with MKT and ME

## Empirik Sonuçlar (sayılarla)

### Tablo 2 — Microcap dominance [s.16, follows Fama-French 2008 Table I]

Microcaps:
- %60.x stocks count
- %3.3 market cap
- En yüksek equal-weighted return
- En geniş cross-sectional std dev

> 📝 Wiki için: Wiki amaç evrenleri (S&P 500 + NDX) **microcap içermez**;
> HXZ 2020 NYSE-VW methodology'i wiki amacı için **doğru baseline**.

### Wiki paperlarının 447 listesindeki durumu

| Wiki paper | 447'de? | HXZ replicate? | q-factor alpha | Yorum |
|---|---|---|---|---|
| **Sloan (1996) operating accruals (Oa)** | ✓ KESİN | ✓ replicate (smaller mag.) | -0.54% (t=-3.77) **sig** [s.27] | Üç darbenin HEPSİNDE hayatta kalan nadir anomaly |
| **CGS (2008) asset growth** | ✓ KESİN | ✓ replicate | (paperdan teyit) | Investment kategorisi q-factor explained |
| **Jegadeesh-Titman (1993) UMD price momentum** | ✓ KESİN | ✓ replicate | (smaller mag.) | Momentum kategorisinde 37/57 sig; UMD klasik 0.67% sig ama q-alpha 0.11% insig |
| **LSV (1994) cash flow-to-price** | ✓ KESİN | ✓ replicate (smaller) | 0.5% / 0.38% / 0.22% (1m/6m/12m) sig with negative Roe loadings | Value kategorisi |
| **FF (1992) HML book-to-market (Bm)** | ✓ KESİN | ✓ replicate | 0.18% (t=1.15) insig [s.25] | Investment factor dominant; Bm explained |
| **FF (2015) RMW operating profits-to-book equity (Ope)** | ✓ KESİN | ✗ **INSIG** [s.10] | (klasik insig) | ⚠️ ⚠️ kritik düzeltme — paperin abstract'ında explicit listed insig |
| **FF (2015) CMA aggregate** | ✓ (factor model komponent) | klasik 0.34% sig | 0.01% (t=0.32) **insig** [s.24] | q-factor I/A factor CMA'yı span; CGS-Ion 2018 ile uyumlu |
| **Carhart (1997) UMD momentum** | ✓ (factor model) | klasik 0.67% (t=3.66) sig | 0.11% (t=0.43) **insig** [s.24] | q-factor lens'inde UMD span ediliyor |
| **Piotroski (2000) F-Score (Fq quarterly)** | ✓ KESİN (ref list) | ✓ replicate (klasik sig) | 0.13% (t=0.58) **insig** [s.27] | Q-factor span; HMXZ Security Analysis ile uyumlu |
| **Mohanram (2005) G-Score** | ✓ ref list (line 1567) | (paperdan teyit; specific result yok) | (paperdan teyit) | Likely q-factor explained (HMXZ kapsamı dışı) |
| **Frankel-Lee (1998) V/P** | ✓ ref list | (HMXZ Security Analysis q5 ile span) | (paralel HMXZ kanıtı) | Reference list'te ama specific HXZ result extract'te yok |
| **Magic Formula (Greenblatt)** | ✗ (kitap, peer-review değil) | n/a | n/a | HXZ academic literature sample dışı |
| **Li-Mohanram (2019) F&V/P combined** | ✗ (composite, individual factor census dışı) | n/a | n/a | Q31 ortogonal soru |
| **Richardson-Sloan-Soliman-Tuna (2005) total accruals (Ta)** | ✓ KESİN (ref list) | ✗ **INSIG** [s.5, s.13] | (klasik insig) | ⚠️ Sloan 1996 hayatta, RSST 2005 modern revisit ÇÜRÜTÜLDÜ |

### Q-factor alpha sig kalan 46 anomaly içinde wiki-relevant olanlar [Section 4.3]

**Earnings announcement abnormal returns (Abr) [s.27]:**
- 1m/6m/12m: 0.74% / 0.3% / 0.22% klasik sig
- q-factor alpha: 0.66% / 0.27% / 0.23% (t=4.49 / 2.41 / 2.65) **sig**
- Roe-factor loading zayıf (0.16-0.26)
- Wiki için: Piotroski 2000 [s.4-5]'te F-Score spread'in 1/6'sı earnings
  announcement penceresinde realize ediyor → Abr Piotroski'nin
  behavioral mekanizmasının q-factor lens'inde de hayatta kalan
  bileşeni

**Operating accruals (Oa) [s.27]:**
- Klasik -0.27% (t=-2.13)
- q-factor alpha -0.54% (t=-3.77) **sig**
- Investment-factor loading tiny (-0.02 t=-0.23)
- Roe-factor loading 0.26 (t=4.13) yanlış yönde
- Wiki için: **Sloan 1996 anomaly üç darbenin tümünde (MP + HLZ + HXZ)
  hayatta kalan nadir kanıt**; Q5 fully-answered güçlendirici

**Discretionary accruals (Dac) [s.27]:**
- Klasik -0.36% (t=-2.73)
- q-factor alpha -0.64% (t=-4.37) **sig**
- Hem investment hem Roe loadings yanlış yönde

**Cash-based operating profits-to-assets (Cop) [s.28]:**
- Klasik 0.63% (t=3.44)
- q-factor alpha 0.69% (t=4.77) **sig**
- Wiki için: Ball-Gerakos-Linnainmaa-Nikolaev 2016 (Tier 1 #9 henüz
  ingest edilmedi) cash-based profitability paper'ının paralel kanıtı

**R&D-to-market (Rdm) [s.28]:**
- Annual sorts klasik 0.68% (t=2.58)
- q-factor alpha 0.7% (t=2.89) **sig**
- Monthly sorts (1m/6m/12m): klasik 1.19% / 0.83% / 0.83%; q-factor
  alpha 1.47% / 0.97% / 0.8% (t=2.97 / 2.73 / 2.8) **sig**
- Wiki için: **Q23 (NDX intangibles için R&D-aware factor) intangibles
  category q-factor alpha sig** — NDX evrene transferli kritik kanıt;
  Lev-Sougiannis 1996 (Tier 2 #26), Peters-Taylor 2017 (Tier 2 #27)
  ingest tamamlar

### Composite q-anomaly performance [s.30]

46 sig q-factor anomaly'yi kategori bazında composite skorla
birleştirme [Stambaugh-Yuan 2016 yaklaşımı]:

| Composite | Klasik HML decile | q-factor alpha | t-stat |
|---|---|---|---|
| Momentum | 1.1% | 0.86% | 3.67 |
| Value-vs-growth | 0.6% | 0.41% | 2.09 |
| Investment | 0.6% | 0.69% | 4.28 |
| Profitability | 0.71% | 0.58% | 4.11 |
| Intangibles | 1.08% | 0.85% | 5.08 |
| Frictions | 0.14% | 0.16% | 1.52 |
| **All 46 q-anomalies** | **1.66%** | **1.4% (t=7.48)** | sig |

> 📝 Wiki için: q-factor model 6 kategoride **explanatory power asimetrik**
> — investment + intangibles en zayıf yakalanır; trading frictions
> already insig.

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Paper top-N selection önermiyor; 447 anomaly extreme decile sortları üzerinde **methodology-robust** replikasyon test ediyor. Wiki'nin top-N stratejilerinin bileşenlerini replication-validated factorlere dayandırma için **ön koşul kanıt seti**. | N/A → epistemic prerequisite |
| **Annual rebalance** | Paper monthly Fama-MacBeth-tipi rebalance kullanır; rebalance frekansı kendisi önermiyor. Frekansa nötr. | N/A |
| **Large-cap evrene transfer** | ⚠️ **KRITIK BULGU** — NYSE breakpoint + VW + microcap-arınmış sample wiki amaç evrenlerine **en uygun methodology**. **HXZ replication rate wiki için "doğru" baseline** (MP equal-weight all-stocks rakamından farklı). Microcap influence wiki için yapısal olarak yok (S&P 500 + NDX large-cap-only). | ⚠️ kritik bulgu — methodology tercihi belirleyici |
| **NDX intangibles / growth firms** | Intangibles kategorisi **103 anomaly, 26 sig (25%)** [Tablo 3]. Q-factor alpha sig 11 intangible anomaly (4 with t > 3) [s.28]: R&D-to-market (Rdm), Heston-Sadka seasonality, vb. **R&D-to-market q-factor span EDİLEMEZ** → NDX evrene transferli intangibles-aware factor için kritik kanıt. | ⚠️ NDX-relevant — Q23 partial cevap; intangibles category survival rate düşük ama R&D-to-market hayatta |

**Strateji tasarımına net implikasyon:**

1. **Wiki amaç evrenleri için "doğru" replication rate HXZ NYSE-VW
   ile ölçülür.** MP %65 hayatta yerine **HXZ %36 sig (161/447)** veya
   **q-factor sonrası %10 sig (46/447)** wiki için baseline. Faz 3
   strateji tasarımı için **muhafazakâr range**.

2. **NYSE breakpoint methodology Faz 3 default tercih (Q12 ile bağlantılı).**
   Wiki'de SMB/HML için "NYSE breakpoint asimetrisi" eleştirisi vardı
   (Q12); HXZ'nin NYSE-VW preference bu sorunun **methodology
   resolution**'u. Wiki amaç evrenleri (S&P 500 + NDX) NYSE-breakpoint
   üst-tarafında zaten — methodology natural fit.

3. **"Üç darbe çerçevesi" → "Dört darbe çerçevesi"**: methodology-robust
   replikasyon dördüncü darbe (kullanıcı kararı 4 + meta-not disiplini).
   Wiki'deki ingested factor/strateji'ler için 19-satır sentez tablosuna
   yeni 4. kolon ([[concepts/post_publication_decay]]).

4. **Intangibles kategorisi NDX-relevant kritik bulgu:** R&D-to-market
   q-factor span EDİLEMİYOR; NDX evrene transferli factor için
   intangibles-aware methodology Faz 3 baseline'a dahil edilmeli.
   Q23 partial cevap.

5. **Sloan accruals üç darbenin tümünde hayatta kalan nadir anomaly:**
   F_ACCRUAL / G3 binary versiyonları komposit içinde **complementary**
   sağlam; Sloan continuous decile standalone large-cap evrene
   transferli değil ama composite içinde **dört darbe geçen factor
   bileşeni**.

## Bu paper'ın sürprizi

| Hipotez | Beklenti | Paper'da gerçek |
|---|---|---|
| **MP %35 decay vs HXZ replication rate çelişkisi** | Plan'da hipotez "scope-dependent" (methodology farkı) | **Paper MP'yi explicit olarak methodology eleştirisi tonuyla ele alıyor** [s.3]: "However, McLean and Pontiff use NYSE-Amex-NASDAQ breakpoints and equal-weights" — ama empirik çürütme değil, methodology disagreement → **scope-dependent teyit edildi** (kullanıcı kararı 6) |
| **Trading frictions/liquidity replication rate** | Belirsiz hipotez | **93% insig** — biggest casualty; Amihud, IVOL, MAX hepsi insig. Wiki'de bu kategori zaten yok ama gelecek factor candidates için kritik |
| **FF15 RMW (Ope) durumu** | Cycle 12'de 2x3 borderline / joint sig idi | **HXZ q-factor lens'inde RMW (Ope) explicit insig** — wiki'nin RMW exposure kararı **çift düzeltme**: HLZ multiple-testing borderline + HXZ q-factor span |
| **Sloan accruals üç darbe** | MP aggregate proxy; HLZ raw sig; HXZ replicate beklenir | **Sloan operating accruals q-factor alpha sig kalır** (-0.54%, t=-3.77) — **MP + HLZ + HXZ üç darbenin TAMAMINDA hayatta kalan nadir anomaly** |
| **Distress anomaly** | Belirsiz | **Virtually nonexistent** — failure probability, O-Score, Z-Score, credit rating hepsi insig. Wiki Tier 2 Campbell-Hilscher-Szilagyi ingest planı için kritik (paper Tier 2 #33; ingest beklenir mi sorgulanır) |
| **97 vs 82 anomaly MP'de** | Wiki MP paper sayfasında 82 anomaly | HXZ "97 anomalies" diyor — yayınlanmış JF 2016 versiyonu 97'ye genişletilmiş; wiki working paper Oct 2012 (82) version okumuş. **MP paper sayfasına nüans eklenir.** |

**Sürpriz büyüklüğü:** YÜKSEK. **Üç sürprizli bulgu:**
1. **FF15 RMW (Ope) explicit insig** — wiki'nin factor model baseline'ında
   RMW yapısal olarak sorgulanır (HLZ + HXZ çift düzeltme)
2. **Trading frictions/liquidity 93% insig** — wiki'de zaten yok ama
   factor zoo'nun bu kolonu büyük çoğunlukla data-mining
3. **Sloan operating accruals üç darbede hayatta** — wiki'de C bloğu
   omurgasının statistical güçlenmesi

## Limitler ve Caveats

- **Sample sonu 2014:** Modern post-2014 dönem (FAANG yükselişi
  2015-2024, COVID-19, ML factor mining) paperin kapsamı dışı.
  Update için JKP 2023 (Tier 2 #44) "Replication Crisis in Finance"
  modern güncelleme; Chen-Zimmermann 2022 (Tier 2 #41) Open Asset
  Pricing data portalı ek kanıt → Q33.

- **U.S.-only sample:** Karolyi (2016) global data eleştirisi paperin
  kendi caveatı [s.32-33]. Non-U.S. anomaly literatürü kapsamı dışı;
  Faz 3 wiki amaç evrenleri (S&P 500 + NDX) zaten U.S. odaklı.

- **NYSE breakpoint VW preference subjektif (paperin tercihi):** Paper
  [s.32] "We recommend NYSE breakpoints and value-weights in sorts
  as the benchmark method" diyor; bu paper-level methodology choice.
  Equal-weight all-stocks rakamları "exaggerated" olarak nitelendirilir
  ama "yanlış" denilmiyor → Q32 wiki için methodology tercih sorusu.

- **Composite scoring strategies (F-Score, G-Score, F&V/P) explicit
  sample dışı:** Q31 ortogonal — composite scores 447 individual
  factor census'da yok; ama F-Score quarterly (Fq) replicate edilir
  (q-factor span). Composite-spesifik replication rate retroactive
  test çalışması için JKP 2023 ek ingest.

- **Q-factor model'in kendisi statistical filter olarak değil
  benchmarking olarak kullanılır:** HXZ q-factor model 161 sig
  anomaly'nin **explanatory framework**'üdür; **filter** değildir.
  Wiki için bu önemli: q-factor span EDİLEN anomaly'ler "false
  positive" değil, **risk-premium-explained** olarak yorumlanır
  (Cochrane mathematical equivalence).

- **q-factor model intangibles düzeltmesi yok:** I/A factor ham total
  asset growth; R&D capitalization yapılmamış (CGS-Ion 2018 challenged
  ile uyumlu). Q23 ortogonal kalır.

- **Working paper May 2017 vs RFS 2020 yayın sayfa numaraları farklı**:
  Wiki bu sayfada NBER WP May 2017 sayfa numaralarını kullanır.

- **Internet Appendix tam 447 anomaly listesi wiki'de yok:** Paper
  Tablo 1 [s.36+] ham listesi var; wiki için aggregate framework
  yeterli, individual anomaly t-statistic'leri için Appendix tam metin
  ek ingest gerekirse.

- **HLZ ile karşılaştırma asymetric:** HLZ 296 sig anomaly üzerinde
  multiple-testing ile %27-53 false discovery; HXZ 447 anomaly
  empirical replication ile %64-85 insig. **İki framework farklı
  test ediyor**: HLZ multiple-testing-aware significance, HXZ
  methodology-robust replication. Birbirini complementary doğruluyorlar
  (her ikisi de "büyük çoğunluk false" diyor).

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfalar
- [[concepts/anomaly_replication]] — concept; replication crisis
  literatür hattı + 447 anomaly category breakdown + methodology
  farkları + wiki ingested factors aggregate replication tablosu

### Bu paperın update ettiği mevcut sayfalar
- [[concepts/post_publication_decay]] — **"Çift-bacak epistemik
  omurga" → "Üç-bacak epistemik omurga"** (behavioral + statistical +
  replication); **"Üç darbe çerçevesi" → "Dört darbe çerçevesi"**
  (methodology-robust replikasyon 4. darbe); 19-satır sentez tablosu
  yeni kolon; **çerçeve genişleme disiplini meta-not** (5 darbe
  noktasında "yeniden dur")
- [[concepts/factor_zoo]] — "Replication crisis perspective" yeni
  alt-bölüm; HXZ + HLZ + MP üçlü omurga
- [[concepts/multiple_testing]] — HXZ 2020 cross-reference;
  empirical replication paralel mekanizma
- [[concepts/factor_model]] — q-factor model'in 447 anomaly'de
  performansı (RMW Ope insig, CMA span, UMD span; investment + Roe
  factor'ler robust)
- [[meta/contradictions]] — **GERÇEK entry** açıldı (wiki'nin 2.
  contradiction): MP 2016 ↔ HXZ 2020 methodology farkı (resolution:
  scope-dependent)
- [[famafrench1993_three_factor]] — HML book-to-market (Bm) klasik
  sig + q-factor alpha 0.18% (t=1.15) insig — investment factor
  dominantı
- [[famafrench2015_five_factor]] — RMW (Ope) **explicit INSIG**;
  CMA klasik sig + q-factor alpha 0.01% insig
- [[carhart1997_four_factor]] — UMD klasik 0.67% sig + q-factor alpha
  0.11% insig
- [[piotroski2000_f_score]] — F-Score quarterly (Fq) replicate sig
  + q-factor alpha 0.13% (t=0.58) insig; HMXZ Security Analysis
  Cycle 8 ile uyumlu
- [[mohanram2005_g_score]] — Mohanram ref list'te (line 1567);
  specific result paperdan teyit gerekir
- [[sloan1996_accruals_anomaly]] — Sloan operating accruals
  q-factor alpha **sig kalır** (-0.54%, t=-3.77) — üç darbenin
  TAMAMINDA hayatta kalan nadir anomaly
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — CGS asset
  growth replicate (smaller magnitude); CMA q-factor span ile uyumlu
- [[li_mohanram2019_quality_value]] — composite F&V/P explicit sample
  dışı; Q31 ortogonal
- [[hou_mo_xue_zhang_2020_security_analysis]] — paralel HXZ paper'ı;
  Security Analysis 6 fundamental scoring strategy q-factor span;
  Replicating Anomalies 447 anomaly geniş kapsam — **HXZ canonical
  reference** complementary çift
- [[mclean_pontiff_2016_post_publication_decay]] — paper [s.3]
  explicit eleştiri "MP NYSE-Amex-NASDAQ + EW"; **MP 97 anomaly
  yayınlanmış vs working paper 82 nüansı** wiki MP sayfasına eklenir
- [[harvey_liu_zhu_2016_multiple_testing]] — paper [s.4] explicit
  reference; HLZ 296 sig %27-53 false vs HXZ 447 anomaly %64-85 insig
  **complementary frameworks**

### İlgili paperlar (ingested)
- [[mclean_pontiff_2016_post_publication_decay]] — behavioral decay
  bacağı; paper'da explicit critique [s.3]; üç-bacak omurganın
  birinci ayağı
- [[harvey_liu_zhu_2016_multiple_testing]] — statistical FDR bacağı;
  paper'da explicit reference [s.4]; üç-bacak omurganın ikinci ayağı
- [[hou_mo_xue_zhang_2020_security_analysis]] — paralel HXZ paper;
  Security Analysis daha dar kapsam (6 fundamental scoring) +
  Replicating Anomalies geniş kapsam (447); HXZ canonical pair
- [[cochrane2011_discount_rates]] — factor zoo terimi; HXZ 2020
  empirik replikasyon ile factor zoo'nun gerçek subset'i ölçülür
- [[bailey_lopezdeprado_2014_deflated_sharpe]] — Cycle 14 ingest;
  DSR Sharpe-spesifik backtest overfitting filter; HXZ NYSE-VW
  methodology + DSR Faz 3 backtest spec için ortogonal iki
  methodology (replication + Sharpe deflation)
- [[israel_moskowitz_2013_shorting_size_time]] — **Cycle 22 ek**;
  HXZ 2020 NYSE-VW + microcap-arınmış paradigmasının **erken anchor'ı**
  (2013); Israel-Moskowitz [Tablo A2] equal-weighted decile alpha 8.4%
  (t=2.81) vs value-weighted INSIG paterni HXZ 2020'nin equal-weight
  all-stocks methodology eleştirisi ile **çift teyit**; çelişki yok,
  methodology continuity. Wiki amaç evrenleri (S&P 500 + NDX top 100-500)
  Israel-Moskowitz Q4-Q5 spektrumunda, HXZ NYSE-VW tercih edilen
  methodology — wiki strateji baseline aynı sonucu üretiyor.
- [[lev_sougiannis_1996_rd_capitalization]] — **Cycle 15 ek; R&D-to-
  market (Rdm) factor'ün methodology temeli** [s.28]: Rdm denominator
  R&D capitalized stock = Lev-Sougiannis Eq. 8 industry-spesifik δ_k
  amortization rates uygulanmış. Lev-Sougiannis [s.133 fn 22] proper
  capitalization stock 3-yıl flow toplamı'ndan dramatic farklı
  (RDC/M coef 0.0114 vs 0.0078; top decile insig vs sig). Wiki için
  Q39 (R&D stock vs flow): HXZ R&D-to-market'in formal tanımı
  paperdan tek-tek teyit edilemedi (text extract'te detay yok); Faz
  3 spec'inde Lev-Sougiannis proper capitalization stock methodology
  recommendation. R&D-to-market dört darbe 4/4 hayatta kalan factor
  Lev-Sougiannis methodology temeline dayanıyor.

- [[eisfeldt_papanikolaou_2013_organization_capital]] — **Cycle 25
  yeni**; HXZ 2020 [s.2] organization capital factor 447 anomaly
  içinde test ediliyor — replication status text extract'te net
  teyit edilmedi; Eisfeldt-Papanikolaou unconditional sort ex-
  financials spread 3.86% Carhart α 5.4% sig → **HXZ paralel
  methodology**; industry-relative spec spread 4.8% FF3 α 5.5% sig.
  Çelişki YOK (scope-dependent: industry-relative vs unconditional);
  HXZ NYSE-VW unconditional methodology Eisfeldt-Papanikolaou ex-fin
  spec ile **çift teyit**. F bloğu 4. ayak (factor portfolio direct
  evidence) replication-robust filter perspektifi.

- [[feng_giglio_xiu_2020_factor_zoo]] — **Cycle 26 yeni**; HXZ 2020
  **replication (NYSE-VW empirik methodology robustness)** + FGX
  2020 **redundancy (DS LASSO model selection bias)** **iki ayrı
  epistemik düzlem** complementary methodology. HXZ 447 anomaly →
  ~46 net sig q-factor sonrası (~%10 hayatta kalan); FGX 150
  factor recursive 1994-2016 → 17 sig (%11). **Iki paper × iki
  methodology paralel decay rate** (sample farkı + methodology
  farkı) **çift teyit factor zoo'nun ~%85-90'ı yetersiz**. Çelişki
  YOK (Cycle 13 paterni paralel; iki ayrı epistemik düzlem
  scope-dependent paper sayfasında not). MP 2016 aggregate %35
  decay + HXZ NYSE-VW + FGX DS LASSO + JKP Bayesian Empirical Bayes
  **dört paper × dört methodology aile** factor zoo decay dört ayrı
  yönden çift+üç+dört teyit (Cycle 27 sertleştirme; conservative-side
  HXZ + FGX + MP vs anti-conservative-side JKP %85 replication
  [[meta/contradictions]] §3 dramatic methodology disagreement).

- [[methodology/data_sources]] — **Cycle 29 yeni**; modern data
  infrastructure pointer dokümantasyonu; Chen-Zimmermann 2022 Open
  Asset Pricing Database (pure replication ~100%) HXZ scientific
  replication (%35 raw / %10 net) ile **paralel methodology**: pure
  vs scientific replication ayrımı (JKP [s.1 fn 1] explicit). HXZ
  pure VW + JKP capped VW + FF half-weight üç alternative methodology
  sensitivity test data altyapısı.

- [[jensen_kelly_pedersen_2023_replication_crisis]] — **Cycle 27
  yeni**; **3. CONTRADICTIONS ENTRY ZORUNLU** ([[meta/contradictions]]
  §3): HXZ 2020 **%35 raw replication** (US-only NYSE-VW pure VW
  1967-2014) vs JKP 2023 **%84.9 Bayesian replication** (US 1926+
  capped VW 1-month) + **%84.0 Global** (93 country) **DRAMATIC
  EMPIRİK FARK ~50pp gap**. Methodology decomposition (paper
  [Figure 1]): capped VW +8.5pp + 1-month +4.0pp + longer sample
  +4.3pp + 15 ek factor +2.4pp + minor +2.7pp = +21.9pp methodology;
  Bayesian framework eklendiğinde +28pp = ~50pp toplam. **Resolution
  scope-dependent + methodology disagreement** (Cycle 13 HXZ ↔ MP
  paterni paralel); empirik ham veri farkı değil **methodology +
  framework evrim**. JKP paper [s.1-3] HXZ 2020'yi explicit
  eleştirir ("pure value weighting sometimes leads to excessively
  concentrated portfolios that mask the behavior of factors")
  ama empirik çürütme değil methodology choice farkı. **Wiki için
  Faz 3 implication**: HXZ + MP paralel conservative tarafta (×0.65
  / ×0.50 decay multiplier); JKP %85 anti-conservative upper bound
  sensitivity reference. **Methodology choice sensitivity test**
  Faz 3 spec'inde üç alternative (pure VW + FF half-weight + capped
  VW). 13 theme cluster + tangency portfolio JKP framework Faz 3
  multi-theme allocation anchor.

- [[peters_taylor_2017_intangible_capital]] — **Cycle 16 ek; R&D-to-
  market potansiyel total-intangibles genişletmesi**: HXZ 2020 Rdm
  factor sadece R&D-only (Lev-Sougiannis methodology). Peters-Taylor
  2017 [Eq. 11] total intangible capital methodology'si (Knowledge
  + Organization + External) kullanılırsa **(R&D + Organization +
  External)/Market** versiyonu **dört darbe 4/4 hayatta kalmaya
  devam eder mi?** Modern data + Peters-Taylor methodology ile direct
  test wiki'de yok — **Q42 yeni soru**. Faz 3 NDX strategy spec'i için
  açık tasarım kararı: Lev-Sougiannis R&D-only baseline vs Peters-
  Taylor total intangibles horse race. CGS-Ion 2018 [s.5-6] paralel
  bulgu (Peters-Taylor methodology asset growth anomaly açıklayıcı
  gücünü güçlendirmiyor) → R&D-to-market'te de "total intangibles
  düzeltmesi yardım etmeyebilir" hipotezi cevap arar.

### Henüz wiki'de olmayan, doğrudan ilgili paperlar
- Hou-Xue-Zhang (2015) "Digesting Anomalies" (Tier 1 #3) — q-factor
  model origin paperı; HXZ 2020 q-factor framework'ünü kullanır,
  origin formal tanımı eksik
- Jensen-Kelly-Pedersen (2023) "Replication Crisis in Finance"
  (Tier 2 #44) — HXZ 2020'ye paralel modern güncelleme; ML-aware
  framework; Q33 cevabı
- Chen-Zimmermann (2022) "Open Asset Pricing" (Tier 2 #41) —
  HXZ methodology'i Chen-Zimmermann modern data ile replikasyon
- Yan-Zheng (2017) — 18,000 fundamental signals bootstrapping;
  paper [s.4] explicit referans
- Linnainmaa-Roberts (2016) — pre-Compustat sample RMW reddi;
  paper [s.33] referans; FF15 RMW data mining argümanı
- Stambaugh-Yuan (2017) "Mispricing Factors" (Tier 1 #23) —
  composite q-anomaly aggregation methodology HXZ paper'da kullanılıyor
- Karolyi (2016) global data eleştirisi
- Ball-Gerakos-Linnainmaa-Nikolaev 2016 (Tier 1 #9) — cash-based
  operating profitability paralel kanıtı (Cop q-factor sig)
- Lev-Sougiannis 1996 (Tier 2 #26), Peters-Taylor 2017 (Tier 2 #27) —
  R&D-to-market intangibles methodology

## Çelişkiler / Tartışmalar

> ⚠️ **GERÇEK contradictions entry açıldı:** Cycle 11 kullanıcı kararı 4
> ile placeholder bırakılmıştı; HXZ 2020 ingest sonrası wiki'nin **2.
> contradictions entry'si** açıldı (ilki HML evrimi FF93↔FF15).
> Detay: [[meta/contradictions]] "Aggregate anomaly survival rate —
> McLean-Pontiff 2016 ↔ HXZ 2020 methodology farkı".
> **Resolution: scope-dependent** (paper MP'yi methodology eleştirisi
> tonuyla ele alıyor ama empirik çürütme değil; iki paper farklı
> methodology tercihleri kullanıyor — empirik çelişen bulgular değil).

> 📝 **HXZ vs HLZ aynı conclusion farklı framework:** İki paper paralel
> çalışıyor (HLZ multiple-testing %27-53 false; HXZ replication %64-85
> insig); birbirini complementary doğruluyor. **Çelişki değil**
> — wiki için iki paralel filter ayrı bacaklar.

> 📝 **HXZ q-factor lens'i risk premium yorumu:** HMXZ Security Analysis
> (Cycle 8) ile uyumlu — anomaly span EDİLEN durumlar "false positive"
> değil **risk-premium-explained**. Wiki taraf tutmaz; mathematical
> equivalence (Cochrane).

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q5 fully-answered (epistemik omurga tüm bacaklarda)]**
  Post-publication decay anchor cevabı:
  - **Behavioral bacak (MP 2016):** 82-97 anomaly aggregate %35
    decay (sig 1%), %65 hayatta
  - **Statistical bacak (HLZ 2016):** 316 factor BHY-FDR-1% sig
    cutoff `|t| > 3.0`; %27-53 false discovery rate
  - **Empirik replication bacak (HXZ 2020):** 447 anomaly NYSE-VW
    methodology'de %64-85 insig; q-factor model sonrası 161 sig
    içinde 115 alpha insig; net %10 sig (46/447)
  Üç bacak independent mekanizmalar, aynı conclusion'a varıyor:
  factor zoo'nun büyük çoğunluğu hayatta kalmıyor. **Q5 epistemik
  omurga tamamlandı**; anomaly-spesifik decay rakamları için
  Internet Appendix'leri Faz 2'de.

- **[Q15 partial-stronger update]** FF5 vs HXZ4/q5 horse race:
  HXZ 2020 [s.24] explicit kanıt:
  - **CMA klasik 0.34% (t=3.63) sig + q-factor alpha 0.01% (t=0.32)
    insig** → q-factor I/A factor CMA'yı tam span eder
  - **RMW (Ope) klasik 0.27% (t=2.58) + q-factor alpha 0.04%
    (t=0.42) insig** → q-factor Roe factor RMW'yi span eder
  - **UMD klasik 0.67% (t=3.66) + q-factor alpha 0.11% (t=0.43)
    insig** → q-factor Roe factor UMD'yi span eder
  q-factor model FF5 + Carhart faktörlerini **büyük ölçüde span ediyor**.
  Tam horse race için HXZ 2015 q-factor origin paper hala gerekli ama
  kanıt çok güçlü. Q15 fully-answered'a yaklaştı.

- **[Q17 fully-answered (üç-bacak epistemik düzey)]** Cochrane #3
  "kaç factor really matter":
  - Behavioral (MP %65 hayatta) + Statistical (HLZ ~%10-30 sig) +
    Empirical (HXZ %10 net sig 46/447)
  - **Üç bacaktan: factor zoo'nun gerçek replicable subset'i K=10-30
    arası** (q-factor model ile span sonra 46 sig anomaly; bunlar da
    Roe + investment factor exposure proxy)
  - Wiki'nin q5 + UMD + composite scoring çerçevesi parsimonious K=5-10
    yeterli olabilir
  - **Q17 fully-answered**.

- **[Q23 partial-stronger update — Cycle 15+16]** NDX intangibles
  için R&D-aware factor: HXZ 2020 [s.28] **R&D-to-market (Rdm)
  q-factor alpha sig** (annual 0.7%, t=2.89; monthly daha güçlü).
  Intangibles category 103 anomaly'nin 26'sı sig (25%); 11'i q-factor
  explained değil. R&D-to-market anomaly hem in-sample hem post-pub
  hem MT-corrected hem q-factor lens'inde sig — wiki'nin Q23 cevabı
  için kritik kanıt. **Lev-Sougiannis 1996** (Cycle 15 ingest) R&D-
  only methodology temeli + **Peters-Taylor 2017** (Cycle 16 ingest)
  total intangibles generalization birlikte NDX-spesifik R&D
  capitalization methodology infrastructure'ı tamamladı. **Q42 yeni**:
  R&D-to-market'in Peters-Taylor total intangibles versiyonu (Knowledge
  + Organization + External / Market) dört darbe 4/4 hayatta kalır
  mı modern data ile direct test gerekli (wiki'de yok).

- **[Q24 partial-stronger update]** q5 vs FF5 horse race:
  HXZ 2020 [s.24] explicit FF15 RMW + CMA q-factor lens'inde span
  ediliyor. q-factor model FF5'i tam alpha-explanation'da geçiyor.

- **[Q28 fully-answered yaklaşık (post-2012 modern decay)]** HXZ 2020
  sample 1967-2014; post-2014 dönem (FAANG, ML mining, COVID) hala
  out-of-sample. JKP 2023 (Tier 2 #44) modern güncelleme tamamlar.

- **[Q30 fully-answered yaklaşık (post-2014 MT-corrected hayatta kalma)]**
  HXZ 2020 1967-2014 sample + HLZ multiple-testing framework birleşimi
  Q30'a büyük ölçüde cevap veriyor. JKP 2023 ile tam kapanma.

- **[Q31 partial-stronger update (composite-score MT)]** HXZ 2020 447
  anomaly **individual factor census** — composite scores (F-Score,
  G-Score, F&V/P, G&V/P) explicit dahil değil. F-Score quarterly (Fq)
  replicate edilir (q-factor span). Composite-spesifik replication
  rate retroactive test JKP 2023 ek ingest.

- **[Q11 partial-stronger]** SMB never sig under MT (HLZ); HXZ 2020'de
  spesifik SMB rakamı paperdan teyit (likely insig under VW
  methodology); paper Tablo 4 ve Section 4.1'de SMB factor'ün q-factor
  reference'da ME factor olarak yer aldığı belirtiliyor.

- **[Yeni Q32]** NYSE breakpoint VW vs equal-weight all-stocks tercih
  sorusu (Q12 ile bağlantılı):
  - HXZ 2020 explicit [s.32]: "We recommend NYSE breakpoints and
    value-weights in sorts as the benchmark method"
  - MP 2016 + Yan-Zheng 2017 + LSV 1994 + Sloan 1996 EW + all-stocks
    methodology kullanır
  - **Wiki amaç evrenleri (S&P 500 + NDX) NYSE-VW methodology'i için
    natural fit** (microcap zaten yok). Faz 3 default tercih: NYSE
    breakpoint + VW. Equal-weight rakamları "exaggerated upper bound"
    referansı.

- **[Yeni Q33]** 447 anomaly'nin post-2014 (FAANG era + COVID) replication
  rate: HXZ 2020 sample sonu 2014; modern dönem JKP 2023 (Tier 2 #44)
  + Chen-Zimmermann 2022 (Tier 2 #41) ile cevap. Q28+Q33 paralel
  (Q28 modern decay, Q33 modern replication rate).

- **[Yeni Q34]** HXZ q-factor model + 447 anomaly çapraz subsumption:
  Paper Section 4'te 161 sig anomaly üzerinde q-factor regression →
  46 alpha sig kalır. Çapraz subsumption (hangi anomaly q5 ile span
  ediliyor?) detay tablo paperdan teyit. HMXZ Security Analysis 6
  fundamental scoring + HXZ Replicating Anomalies 447 individual
  birleşimi factor zoo'nun q-factor lens'inde subsumption haritası
  sağlar.

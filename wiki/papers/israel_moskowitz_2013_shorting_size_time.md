---
type: paper
authors: [Israel, Ronen; Moskowitz, Tobias J.]
year: 2013
title: "The role of shorting, firm size, and time on market anomalies"
venue: "Journal of Financial Economics 108 (2013) 275-301"
url: https://doi.org/10.1016/j.jfineco.2012.11.005
local_path: raw/papers/israel_moskowitz_2013_shorting_size_time.pdf
ingested: 2026-05-01
tags: [size, value, momentum, large_cap, long_only, shorting, time_variation, e_block, fama_french]
status: ingested
cycle: 22
block: E
cycle_37_note: "E bloğu (large-cap reality) FF 2008 ile çift teyit sertleştirme [[papers/fama_french_2008_dissecting_anomalies]] Cycle 37 ✓; HML 86-yıl size-conditional Q5 INSIG (Israel-Moskowitz [Tablo 4]) + B/M big-stock 0.17 (t=1.79) zayıf (FF 2008 [Tablo IV]) çift teyit; UMD size-invariant (Israel-Moskowitz) + momentum tüm size gruplarında pervasive (FF 2008 slopes 0.41+0.82+0.78 all sig) paralel; Q14 fully-answered üçlü teyit FF 2008 + Israel-Moskowitz + HXZ 2015 [s.7] cross-cite"
---

# Israel-Moskowitz (2013) — The Role of Shorting, Firm Size, and Time on Market Anomalies

> 📝 **Faz 2 ilk gerçek paper ingest'i (Cycle 22).** E bloğu (large-cap
> reality) #1; Faz 1 sertifikası YUMUŞAK gerekçesinin ana eksikliklerinden.
> Paper Q4 (CGS-Ion large-cap) ve Q14 (FF5 large-cap-only başarısızlık
> portföyü) tam cevap aday; Q11 (SMB never sig under MT) cross-evidence
> 86-yıl confirmation. backtest_spec §1.3 universe methodology + §4.1
> darbe (1) in-sample large-cap rationale güçlendirilir.

## TL;DR

Israel-Moskowitz US 1926-2011 86 yıl + 4 international + 5 asset class
sample'ında size, value, momentum üç klasik anomaly'i shorting / firm
size / time eksenlerinde decompose ediyor. Üç ana bulgu: (1) **value
premium büyük cap'lerde nonexistent** — HML CAPM α(largest quintile)
= 3.70%/yıl t=1.90 vs α(smallest) = 11.22%/yıl t=3.87 ([Tablo 3]);
(2) **momentum büyük/küçük cap'te eşit** — UMD reliable size-conditional
fark yok 86-yıl sample; (3) **shorting raw return için marjinal** —
SMB ~all, HML ~60%, UMD ~half long side'tan; long-only versions'a yönelirsen
HML ve UMD anlamlı positive alpha. **Time variation insig** (institutional
ownership + hedge fund AUM + trading costs çoğu spec'te momentum dışında
insig).

## Tek Cümle Tezi

Klasik anomaly'lerin (size, value, momentum) **profitability'si firma
büyüklüğüne kritik bağlı** — value büyük-cap'te yapısal olarak silinir,
momentum size-invariant kalır, size premium 86-yıl sample'da CAPM
tarafından zaten kapsanır.

## Sample ve Methodology

- **US universe**: NYSE+Amex+Nasdaq tüm publicly traded stocks
  ([s.276]); NYSE breakpoints decile portfolio formation
- **US sample**: July 1926 - December 2011 (size, value); January 1927
  - December 2011 (momentum); 86 yıl
- **International**: UK, Europe ex-UK, Japan + 5 asset class (country
  equity, government bonds, currencies, commodities); 1972-2011
- **Value measure**: standard BE/ME (Fama-French 1992); robustness
  E/P, C/P, D/P, -Ret(1,60), composite index
- **Momentum measure**: Ret(2,12) past 12-month skip-month
- **Portfolio construction**: VW (default) + EW (robustness); 5×5
  size×value + size×momentum sequential dependent sorts; long-only
  S/H/U portfolios = top 30% size/BE-ME/momentum
- **Size grouping (2011 averages)**: Q5 $36B (>Russell 1000 avg),
  Q4 $4.8B (~Russell Midcap), Q3 $2B (>Russell 2000 avg), Q2 $855M,
  Q1 $156M (microcap) [s.277]

## Ortaya Konan Sinyal/Faktör

Bu paper **methodology paper'ı** — yeni factor önermez, klasik 3
factor'ün (SMB, HML, UMD) size×shorting×time decomposition'unu yapar.
Mevcut wiki entity'lere atıf:

- [[factors/SMB]] — paper SMB CAPM α(86-yıl)=2.05% t=1.72 INSIG
- [[factors/HML]] — paper HML CAPM α(86-yıl)=3.45% t=2.80 sig ama
  size-conditional
- [[factors/UMD]] — paper UMD CAPM α(86-yıl)=10.48% t=6.13 sig + size-invariant

**Yeni factor entity AÇILMADI**: shorting "dimension" methodology
kontrol değişkeni; concept proliferation kontrolü disiplini (Cycle
13/16/17/18/19 paterni).

## Empirik Sonuçlar (sayılarla)

### 1. Long-short SMB / HML / UMD CAPM α (86-yıl sample, [Tablo 1])

| Factor | CAPM α (yıllık %) | t-stat | Yorum |
|--------|-------------------|--------|-------|
| SMB (size) | 2.05 | 1.72 | INSIG; CAPM 86-yıl içinde size'i kapsar |
| HML (value) | 3.45 | 2.80 | sig ama yanılgı: 1963-2011 sub-sample'da α=4.72% t=4.21; 1926-1962'de α=0.71% t=0.37 INSIG |
| UMD (momentum) | 10.48 | 6.13 | sig + tüm subperiyotlarda sig (1926-49: 12.23%; 1990-2011: 8.87%) |

### 2. Long-only S, H, U CAPM α (86-yıl, [Fig.1 Panel D + s.281])

| Long-only | α | t-stat | Information Ratio |
|-----------|---|--------|-------------------|
| S (size, smallest half) | 2.05% | 1.72 | 0.19 |
| H (high BE/ME, top 30%) | 2.93% | 2.40 | 0.26 |
| U (top winners 30%) | 5.55% | 6.74 | 0.73 |

Long-only momentum information ratio (0.73) **size + value'nun ~3x'i**.

### 3. Size-Value interaction ([Tablo 3] CAPM α, %)

| | Size 1 (smallest) | Size 2 | Size 3 | Size 4 | Size 5 (largest) | Size 1−Size 5 |
|--|-------------------|--------|--------|--------|------------------|---------------|
| **Value 5-1 spread α** | 11.22 (t=3.87) | 7.28 (t=3.88) | 5.42 (t=2.96) | 4.24 (t=1.93) | 3.70 (t=1.90) | 7.13 (t=2.10) |
| Long side (Q5) α | 6.15 (t=2.78) | 4.15 (t=2.38) | 3.26 (t=2.05) | 1.73 (t=1.04) | 1.97 (t=1.21) | 4.31 (t=1.97) |
| % long contribution | 47.4% | 65.1% | 70.4% | 112.9% | 89.9% | — |

**Kritik bulgu** [s.277, s.283]: HML 5-1 alpha sadece 1970-1989 subperiod'unda
büyük cap'lerde sig; diğer 3 subperiod (1926-49, 1950-69, 1990-2011)
INSIG large cap. **Largest 40% NYSE stocks'ta value premium yapısal
olarak yok**.

### 4. Size-Momentum interaction ([Tablo 3])

| | Size 1 (smallest) | Size 2 | Size 3 | Size 4 | Size 5 (largest) | Size 1−Size 5 |
|--|-------------------|--------|--------|--------|------------------|---------------|
| **Momentum 5-1 spread α** | 13.12 (t=5.59) | 15.30 (t=7.66) | 14.48 (t=6.32) | 14.19 (t=5.72) | 10.24 (t=4.23) | 2.88 (t=1.31) |
| Long side (Q5) α | 9.30 (t=4.47) | 7.89 (t=5.13) | 7.26 (t=5.71) | 7.17 (t=6.24) | 3.92 (t=3.83) | 5.37 (t=2.40) |

**Momentum size-invariant** [s.284]: 5-1 spread fark Size 1 vs Size
5 = 2.88 t=1.31 INSIG. Ancak long-only Q5 fark 5.37 t=2.40 sig (small
caps long-only momentum daha güçlü).

### 5. Time variation (Tablo 4 Panel A)

[Tablo 4 Panel A]: 20-yıl dummy variables (1950-69, 1970-89, 1990-2011)
+ linear time trend, **hiçbiri sig** SMB/HML/UMD/small cap HML/large
cap HML/large cap UMD için. **Tek sig**: small cap UMD (paperin
açıklaması: 1926-49 anomalous düşük small cap momentum).

### 6. Trading cost + institutional ownership (Tablo 4 Panel B-C)

- **Trading costs**: post-1950 sample'da çoğu spec insig; momentum
  (özellikle small cap momentum) trading cost level/changes ile sig
  positive (limited arbitrage interpretation)
- **Institutional ownership**: SMB negative relation (Gompers-Metrick
  2001 ile uyumlu); HML/UMD/size-conditional çoğu insig
- **Hedge fund AUM/IO**: marjinal sig small cap momentum negative;
  diğerleri insig

### 7. International + asset class

[Tablo 5 + Fig.5]: Value ve momentum 4 international equity market
+ 5 asset class'ta robust. Long ve short side **eşit dağılım** (US
86-yıl bulgusu international ile uyumlu — long-only sub-portfolio'lar
sig positive alpha çoğu pazarda).

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Decile portfolio long-short methodology + long-only sub-portfolio explicit (S/H/U Q10 veya top 30%); 5×5 dependent sort 25 portföy [s.276-277]; long-only versions paperin **merkezi yapısal kontrolü** [s.277-282] | ✅ doğrudan + dengeleyici (long-only sub-portfolio explicit raporlama) |
| **Annual rebalance** | Size portfolio formation **annual** June rebalance (Fama-French konvansiyonu); momentum aylık rebalance Ret(2,12) past 12-month; HML annual rebalance June. Wiki amaç evrenleri (S&P 500 + NDX yıllık) için annual size + value uyumlu, UMD aylık → annual uyarlama Q33 + [[methodology/backtest_spec]] §2.2 sensitivity | ✅ size/value annual + ⚠️ UMD aylık-orijinal |
| **Large-cap evrene transfer** | ⭐ **PAPERİN MERKEZ KONUSU** — Size×Value + Size×Momentum interaction tüm 5 size quintile için ayrı raporlama; Q5 largest quintile (avg 36B 2011 ≈ S&P 500 üst yarısı) explicit; "value premium nonexistent among largest 40% NYSE stocks" [s.276] | ✅ ⭐ KRİTİK doğrudan fit; Q4/Q14 fully-answered aday anchor |
| **NDX intangibles / growth firms** | Paper geleneksel BE/ME value methodology — intangibles-aware değil; ham size partition. NDX growth/intangibles-yoğun firmalar için methodology revision yok; [[concepts/intangibles_adjusted_accounting]] anchor (Lev-Sougiannis + Peters-Taylor + Lev-Srivastava) bu boşluğu doldurur | N/A (paper kapsamı dışı; geleneksel BE/ME) |

**Strateji tasarımına net implikasyon:**

1. **Wiki amaç evrenleri (S&P 500 + NDX top 500/100) Israel-Moskowitz
   Q4-Q5'e karşılık geliyor**. Q5 avg 36B (2011) S&P 500 üst yarısı;
   Q4 avg 4.8B Russell Midcap. Wiki S&P 500 / NDX largest 100-500
   stocks tam Q4-Q5 spektrumunda. **Bu evrende vanilla HML α=1.97-3.70
   t=1.04-1.90 INSIG** [Tablo 3].

2. **Vanilla HML reject teyit edildi** ([[papers/lev_srivastava_2020_value_failure]]
   Q1 fully-answered anchor + Israel-Moskowitz 86-yıl sample stronger
   teyit). Adjusted HML methodology ([[concepts/intangibles_adjusted_accounting]])
   Faz 3 spec'inde zorunlu.

3. **Long-only momentum** (top 30% winners) Q5 largest stocks α=3.92%
   t=3.83 sig — **wiki amaç evrenleri için actionable**. UMD long-short
   gerekli değil; long-only momentum Faz 3 spec için somut girdi.

4. **F&V/P + G&V/P combined** ([[papers/li_mohanram2019_quality_value]])
   Israel-Moskowitz BE/ME-only paterninden farklı; quality × value
   cross-product F-Score / G-Score winner-loser identification ile
   composite. Israel-Moskowitz **standalone BE/ME** large-cap
   başarısızlığı bu combined yaklaşımın motivasyonunu güçlendiriyor.

## Limitler ve Caveats

- **Composite scores (F-Score/G-Score/QMJ) test edilmemiş** — paper
  yalnız 3 klasik factor (SMB/HML/UMD); fundamental composite
  scoring methodology paper kapsamı dışı
- **Intangibles-aware methodology yok** — vanilla BE/ME; tech firma
  R&D distortion ([[concepts/intangibles_adjusted_accounting]])
  paper kapsamı dışı; NDX FAANG-yoğun evrene transfer için
  Lev-Sougiannis + Peters-Taylor + Lev-Srivastava methodology gerekli
- **Sample sonu Dec 2011** — post-2011 (FAANG era 2012-2024 + COVID
  + AI) out-of-sample; modern data Chen-Zimmermann 2022 + JKP 2023
  ingest gerekli (Faz 2 sonu)
- **Momentum aylık rebalance orijinal** — Ret(2,12) past 12-month;
  annual rebalance uyarlama primum sensitivity Q33 + [[methodology/backtest_spec]]
  §2.2
- **Trading cost analysis aggregate** — Frazzini-Israel-Moskowitz
  2018 (Tier 3 #52, paywall) firm-level cost analysis tamamlayıcı;
  AQR practical implementation
- **NYSE+Amex+Nasdaq universe** — wiki amaç evrenleri (S&P 500 + NDX
  index members) explicit subset değil; size partition adequate proxy
  ama index-spesifik test eksik (Q3/Q11 paralel)

## İlgili Sayfalar

- [[papers/famafrench1993_three_factor]] — SMB/HML factor portföyü
  origin; Israel-Moskowitz aynı portföyleri 1926-2011 extended sample'da
  re-test
- [[papers/famafrench2015_five_factor]] — CMA(small) t=4.64-5.49 vs
  CMA(big) t=1.03-2.00 [s.13] paterni Israel-Moskowitz HML size-conditional
  paterni paralel; size-loaded factors ekosistemi
- [[papers/carhart1997_four_factor]] — UMD origin; Israel-Moskowitz
  86-yıl sample size-invariance teyit (Carhart sample 1963-93 daha
  kısa)
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] — HXZ NYSE-VW
  + microcap-arınmış paradigmasının **erken anchor'ı**; 2013→2020
  methodology continuity
- [[papers/mclean_pontiff_2016_post_publication_decay]] — limited
  arbitrage [Tablo 8] büyük/likit firmalarda decay agresif → Israel-
  Moskowitz "anomaly small-cap dominant" cross-evidence; Q5 paralel
- [[papers/cooper_gulen_ion2018_asset_growth_factor_models]] — CGS
  asset growth size-loaded uyarısı [Tablo I] Israel-Moskowitz HML
  size-loaded paterni paralel; Q4 fully-answered aday
- [[papers/asness_frazzini_pedersen_2019_qmj]] — QMJ Tablo A4 + Fig
  A1 large-cap-only kanıtı; Israel-Moskowitz vanilla HML reject
  large-cap'te → QARP framework motivasyon güçleniyor
- [[papers/lev_srivastava_2020_value_failure]] — Q1 anchor + Israel-
  Moskowitz 86-yıl sample stronger teyit; vanilla HML reject **çift
  anchor** (E bloğu + F bloğu)
- [[concepts/anomaly_replication]] — HXZ NYSE-VW paradigmasının
  Israel-Moskowitz 2013 erken anchor'u; size matters empirik kanıt
- [[concepts/post_publication_decay]] — dört darbe sentez tablosu
  in-sample large-cap kolonu Israel-Moskowitz ile sertleştirilir
- [[concepts/winner_loser_identification]] — "large-cap'te hangi
  anomaliler hayatta?" anchor
- [[concepts/factor_zoo]] — size-conditional factor zoo decomposition
- [[methodology/backtest_spec]] — §1.3 NYSE-VW + universe methodology;
  §4.1 darbe (1) in-sample large-cap kalibrasyonu; §5.3 0/4 reddedilen
  (vanilla HML standalone large-cap)

## Çelişkiler/Tartışmalar

### Hong-Lim-Stein 2000 + Grinblatt-Moskowitz 2004 (paper içi tartışma)

Israel-Moskowitz [s.284-286] HLS 2000 ve GM 2004'ün "momentum
small-cap dominant + shorting drives 2/3 of profits" iddialarını
**sample-spesifik** olarak işaretliyor: 1980-1996 (HLS) ve 1963-1999
(GM) sample'larında bulgular replicate ediyor; out-of-sample
(1926-1979 + 2000-2011) bulgular kayboluyor. Wiki için: HLS ve GM
ayrı ingest edilmedi (Tier listesi dışı); paper içinde explicit
methodological eleştiri olarak not edilir, ayrı contradictions
entry açılmaz.

### Avramov-Chordia-Jostova-Philipov 2007/2012 (paper içi tartışma)

Israel-Moskowitz [s.286-287] ACJP'nin "momentum profits stronger
among low credit-rated firms" iddiasını sample-spesifik olarak
işaretliyor (1985-2003 / 1985-2008 sample'ları). Paper credit rating
data 1985 öncesi yok — Israel-Moskowitz 86-yıl sample'da test
edilemiyor; methodology disagreement, çelişki olarak listelenmedi.

### HXZ 2020 vs Israel-Moskowitz 2013 — çelişki potansiyeli **YOK** (çift teyit)

Plan'da hipotez "potansiyel çelişki"; paper okuma sonrası: **çelişki
yok, çift teyit**. Israel-Moskowitz NYSE breakpoints + value-weighted
default methodology HXZ 2020'nin tercih ettiği methodology'dir.
Bulgular paralel:
- HXZ 2020 [s.2-3]: equal-weight all-stocks methodology spread'leri
  şişiriyor
- Israel-Moskowitz [Tablo A2]: equal-weighted decile portfolios
  alpha = 8.4% (t=2.81) vs value-weighted alpha INSIG → aynı
  methodology farkı paterni 7 yıl önce

**[[meta/contradictions]] yeni entry açılmaz**; Israel-Moskowitz HXZ
2020'nin **erken methodology anchor'ı** olarak [[concepts/anomaly_replication]]
sayfasında konumlandırılır.

## Açık Sorular (Open Questions)

- **Q4** (CGS-Ion large-cap) → Israel-Moskowitz **fully-answered aday**:
  86-yıl sample size-conditional anomaly test direct kanıt; CGS asset
  growth ile paralel mekanizma (size-loaded anomaly)
- **Q14** (FF5 large-cap-only başarısızlık portföyü) → Israel-Moskowitz
  **partial-stronger**: HML size-conditional explicit direct test
  (Q4-Q5 quintile'da insig); CMA/RMW direct test paperde yok
  ([[papers/famafrench2015_five_factor]] [s.13] CMA size-conditional
  ek anchor)
- **Q11** (SMB never sig under MT) → Israel-Moskowitz **86-yıl
  cross-evidence**: SMB CAPM α=2.05% t=1.72 INSIG; HLZ MT-corrected
  cutoff'un altında; **Q11 fully-answered ASTERISK genişler** (HLZ
  statistical + Israel-Moskowitz 86-yıl confirmation; QMJ resurrection
  asterisk korunur)
- **Q33** (post-2014 modern decay) → Israel-Moskowitz **partial-stronger**:
  paper sample sonu Dec 2011; 1990-2011 subperiod testi var (HML α=2.98%
  t=1.66 INSIG large-cap; UMD α=8.87% t=2.38 sig); post-2011 out-of-sample
- **Q52 yeni**: Long-only vs long-short anomaly performansı (wiki
  amaç evrenleri long-only retail-style; Israel-Moskowitz long-only
  S/H/U sub-portfolio explicit sig kanıt — Faz 3 spec için kritik
  decomposition)
- **Q53 yeni**: Time-conditional anomaly decay decomposition
  (Israel-Moskowitz 20-yıl dummy + linear time trend insig vs
  McLean-Pontiff publication-anchored discrete change — iki paper
  farklı time variation paterni; sentez Faz 2)
- **Q54 yeni**: Anomaly performansının size × shorting interaction
  (Israel-Moskowitz Tablo 3 long-only/short-only decomposition
  size-conditional; wiki amaç evrenleri large-cap + long-only hangi
  anomaliler birlikte hayatta)

## Strateji tasarımına spesifik katkı

1. **HML standalone large-cap reject** çift anchor: Israel-Moskowitz
   86-yıl sample size-conditional + Lev-Srivastava 2020 post-2010
   collapse. [[methodology/backtest_spec]] §5.3 0/4 reddedilen
   listesinde "vanilla HML standalone large-cap" sertleştirilir.

2. **Long-only momentum** (top 30% winners) wiki amaç evrenleri için
   actionable + Q5 largest α=3.92% t=3.83 sig. Faz 3 strategy spec'inde
   long-only momentum exposure UMD long-short'a alternatif somut girdi.

3. **Adjusted HML methodology** ([[concepts/intangibles_adjusted_accounting]])
   Faz 3 spec'inde zorunlu — vanilla BE/ME her durumda largest 40%
   stocks'ta yetersiz; intangibles-aware Bm rebuild.

4. **F & V/P + G & V/P combined** ([[papers/li_mohanram2019_quality_value]])
   Israel-Moskowitz BE/ME-only paterninden farklı yapısal yaklaşım;
   quality × value cross-product fundamental scoring vanilla HML'in
   yapısal başarısızlığını ((Israel-Moskowitz teyit) bypass eder.
   QARP framework anchor güçleniyor.

5. **Size partition Q5 (largest 20%) ≈ wiki S&P 500 üst yarısı**;
   Q4 (next 20%) ≈ Russell Midcap. Wiki amaç evrenleri Israel-
   Moskowitz Q4-Q5 spektrumunda direct kanıt: vanilla HML α=1.97-3.70
   t=1.04-1.90 INSIG → wiki strategy spec için **standalone BE/ME
   value factor exposure baseline = sıfır**.

---
type: factor
name: RMW
category: profitability
direction: long_high  # uzun robust profitability, kısa weak
data_lag_required: "Haziran t-end için fiscal year-end t-1 muhasebe verisi (≥6-aylık reporting gap)"
rebalance_frequency: annual
universe_tested: ["NYSE/AMEX/NASDAQ ex-financials, 1963-07/2013-12"]
---

> 📝 **Cycle 35 ek**: HXZ 2015 q-factor model r_ROE return on equity factor [[factors/ROE]] yeni entity açıldı (Cycle 35); methodology farkı dokümante (FF15 RMW = operating profitability annual; HXZ ROE = quarterly IBQ/BE_lagged monthly resort earnings announcement-anchored). Profitability zinciri 4 paper × 7 yıl literature continuity Cycle 35'te 4. halka aday HXZ ROE methodology paralel (Novy-Marx GP/A → FF15 RMW Ope → QMJ GPOA → HXZ ROE/Cop). HXZ 2020 q-factor lens vs FGX 2020 DS LASSO methodology farkı RMW iki paralel bulgu (q-factor INSIG α=0.04% t=0.42 vs DS-sig 150-factor library) Cycle 26 dokümante.

> 📝 **Cycle 37 ek**: RMW size-conditional zayıflık direct origin [[papers/fama_french_2008_dissecting_anomalies]] (Cycle 37 ✓); FF 2008 [Tablo II + IV] profitability sorts hedge returns "weakest"; only **small group** EW + VW abnormal hedge returns >2σ; regression slope positive Y/B small 2.36 (t=4.04) + big 0.94 (t=1.81 weakest); among profitable firms positive relation tüm size groups ama **negative profitability'de kanıt YOK** big group içinde. Q14 partial-stronger update: RMW Ope FF15 size-conditional zayıflığın root'u FF 2008'de; QMJ Profitability composite [Tablo A4] large-cap-only 4-factor alpha 66 bps/ay sig (Asness 2019 Cycle 19) FF 2008 traditional Y/B'den methodology evolution. sp500_v1 + nasdaq100_v1 §2.1 Path B Profitability theme RMW Ope reject + QMJ composite + GP/A standalone tercih FF 2008 evidence ile sertleştirme.

> 📝 **Cycle 38 ek**: FF15 RMW Ope vs Ball-GLN Cop methodology farkı direct empirik dokümantasyon [[factors/Cop]] yeni entity Cycle 38 ✓ ([[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]); Ball-GLN [Tablo 2 col 7] horse race **Cop t=5.27 + Ope t=1.56 INSIG Cop wins**; [Tablo 5] RMW^CbOp 4.88%/yr t=6.29 substantially higher than RMW^Op 3.25%/yr t=3.65; [Tablo 8] tangency Sharpe **4F+Cop=1.67 > 4F+Ope=1.40**; [Tablo 7 Panel A] 3F+Cop subsumes RMW^Op (alpha t=-1.15 INSIG) ama 3F+Ope does NOT subsume RMW^CbOp (alpha 27 bps t=7.08 SIG); Profitability zinciri 2. halka (RMW Ope) → 4. halka (Cop) methodology evrim cash-based superior; sp500_v1 + nasdaq100_v1 §2.1 Path B RMW Ope reject + Cop standalone tercih + QMJ composite Ball-GLN evidence ile sertleştirme.

# RMW — Robust Minus Weak (Operating Profitability Faktörü)

## Tanım (Fama-French 2015 inşası)

`RMW` = (S/R + B/R) / 2 − (S/W + B/W) / 2 (2×3 sort versiyonu)

- `S` ve `B`: NYSE median ME breakpoint
- `R` (Robust), `N` (Neutral), `W` (Weak): NYSE 30/70 OP percentile breakpoint'leri
- 6 portföy value-weighted aylık [[famafrench2015_five_factor]] s.10

**OP (Operating Profitability) ölçüsü** [s.7]:

`OP = (revenues − COGS − SGA − interest expense) / book equity (fiscal year-end t-1)`

> 📝 Yazarlar OP'yi "operating profitability minus interest expense" olarak adlandırır
> [s.7] — yani interest expense de çıkarılıyor. Net Income veya EBITDA değil.

## Origin

- İlk paper (mimicking-portföy formuyla): [[famafrench2015_five_factor]] (Fama-French 2015)
- Profitability premium kanıtının akademik kökü: Novy-Marx (2013) Gross Profitability —
  bu wiki'de henüz ingest edilmedi (Tier 1 Source #5; bekliyor)
- Yazarlar [[famafrench2015_five_factor]] s.4-5'te valuation equation (Eq. 3) ile RMW'yi
  teorik olarak motive eder.

## Reported Performance Across Studies

| Paper | Dönem | Evren | Mean (ay) | t-stat | Notlar |
|---|---|---|---|---|---|
| [[famafrench2015_five_factor]] (2x3) | 1963-07 / 2013-12 | NYSE/AMEX/NASDAQ ex-fin | 0.25% | 2.92 | [Tablo 4 Panel A, s.37] |
| [[famafrench2015_five_factor]] (2x2) | aynı | aynı | 0.17% | 2.79 | [Tablo 4 Panel A, s.37] |
| [[famafrench2015_five_factor]] (2x2x2x2) | aynı | aynı | 0.25% | 4.09 | [Tablo 4 Panel A, s.37] |
| [[novy_marx_2013_gross_profitability]] **GP/A origin** | 1963-07 / 2010-12 | NYSE+Amex+Nasdaq ex-fin VW | univariate Q5−Q1 raw 0.31% / FF3 α 0.52% | 2.49 raw / 4.49 α | [Tablo 2]; **RMW Ope methodology kökü** (FF15 [s.4] Novy-Marx 2013 explicit cite); GP/A (REVT−COGS / AT) vs RMW Ope (REVT−COGS−SG&A−int / BE) — numerator+denominator iki seviye fark |
| [[novy_marx_2013_gross_profitability]] PMU\|BM | 1963-2010 | aynı | 0.48% conditional | 5.35 | [Tablo 8]; B/M kontrollü profitability factor Carhart UMD'den daha yüksek IR (PMU\|BM 5.54 vs UMD 5.11) |
| [[novy_marx_2013_gross_profitability]] **Fortune 500 GP/V** | 1963-2010 | top 500 non-fin | 0.62%/ay combined | (sig) | [Tablo 7]; **Sharpe 0.74** large-cap; RMW exposure target değil ama GP/V combined wiki S&P 500 anchor |
| [[feng_giglio_xiu_2020_factor_zoo]] **DS LASSO 150-factor library** | 1976-07 / 2017-12 | NYSE+AMEX+NASDAQ ex-fin | SDF loading sig (since-2012 DS column) | sig | [Tablo 1]; **DS-sig** Profitability factor; FGX 150 library + omitted variable bias correction lens; HXZ q-factor INSIG **methodology farkı**: q-factor model lens (HXZ INSIG 1/4) vs DS LASSO 150-factor library lens (FGX sig) **iki paralel bulgu, çelişki değil** |

_(yeni paperlar ingest edildikçe satır eklenecek)_

> 📝 **Cycle 26 ek (FGX 2020 ingest) — methodology farkı dokümante**:
> RMW Ope **iki paralel bulgu** (çelişki değil):
> - **HXZ 2020 q-factor model lens** ([[hou_xue_zhang_2020_replicating_anomalies]]
>   [Tablo 6]): alpha 0.04% t=0.42 INSIG (1/4 dört darbe; q-factor
>   model'in 4 factor'ünden biri olarak alternatif)
> - **FGX 2020 DS LASSO 150-factor library lens** ([[feng_giglio_xiu_2020_factor_zoo]]
>   [Tablo 1]): SDF loading sig (since-2012 DS-sig)
>
> İki ayrı epistemic question:
> - HXZ: "RMW q-factor model dışında bağımsız bilgi sağlıyor mu?"
>   (q5'in 4 component'i alternatif → INSIG)
> - FGX: "RMW 150-factor library'deki diğer factor'lerden bağımsız
>   pricing contribution sağlıyor mu?" (DS LASSO model selection +
>   omitted variable bias correction → sig)
>
> Faz 3 spec için: RMW factor exposure proxy (q-factor lens'inde) +
> standalone DS-sig signal (FGX lens'inde) **iki kullanım modu** option.

> 📝 **Cycle 23 ek (Novy-Marx 2013) — Profitability zinciri kökü**:
> RMW factor inşası **Novy-Marx GP/A literatür hattı kökü**
> ([[famafrench2015_five_factor]] [s.4] explicit cite). Profitability
> zinciri 4 halka ([[factors/Gross_Profitability]] origin attribution
> tablosu): GP/A → **RMW Ope** → QMJ GPOA → Cop. RMW Ope methodology
> Novy-Marx GP/A'dan farklı (numerator SG&A+interest çıkarılmış;
> denominator BE leverage-sensitive); HXZ 2020 q-factor alpha
> RMW Ope **0.04% t=0.42 INSIG** (1/4 dört darbe). Faz 3 spec için
> RMW factor **exposure proxy** değil; QMJ Profitability composite
> + GP/A standalone tercih.

## Faktör Ailesi İçindeki Yeri

- **Korelasyonlar (FF5 2x3, [Tablo 4 Panel C, s.38]):**
  - RMW ↔ MKT-RF : −0.21
  - RMW ↔ SMB : −0.36 (negatif: küçük caplerde ortalama profitability düşük)
  - RMW ↔ HML : 0.08 (yaklaşık ortogonal)
  - RMW ↔ CMA : −0.11
- **2×2×2×2 (joint kontrol) inşasında HML ile korelasyonu 0.63'e fırlıyor**
  [Tablo 4 Panel C, s.38]; yazarlar "somewhat artificial" olarak yorumluyor [s.14].

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar — Cycle 19 update

[[famafrench2015_five_factor]] NYSE/AMEX/NASDAQ ex-financials evrenini
test eder; large-cap-only / index-spesifik kanıt yok. Ancak FF15'in büyük cap içinde
(megacap quintile) RMW slope'larının da pozitif olduğu Tablo 9'da görülür [s.23] —
bu, large-cap evrende profitability spread'inin var olmaya devam ettiğine dair pozitif
işaret.

**Cycle 19 ek — [[asness_frazzini_pedersen_2019_qmj]] QMJ Profitability
dimension large-cap kanıtı** (Tablo A4 + Figure A1):
- 23/24 country pozitif alpha (large-cap-only ayrı raporlama)
- 17/24 country 4-factor alpha sig
- US long sample composite QMJ alpha 66 bps/ay (t=11.20); Profitability
  dimension ayrı raporlama (Table VI Panel A) sig 1/3/4-factor alpha
- **Q2 fully-answered** anchor (Cycle 19): large-cap quality vs value
  yapı 13 cycle partial sonrası fully-answered

## QMJ alternatifi — RMW vs QMJ Profitability dimension (Cycle 19 ek)

**Yapısal karşılaştırma**:

| Boyut | RMW (FF15) | QMJ Profitability dimension |
|---|---|---|
| Measure sayısı | **1** (operating profitability) | **6** (GPOA + ROE + ROA + CFOA + GMAR + ACC) |
| Formül | (REVT − COGS − XSGA − XINT) / BV | Average of 6 z-scores |
| Sample | NYSE/AMEX/NASDAQ ex-fin 1963-2013 | US 1956-2012 + 24 country broad 1986-2012 |
| Origin paper | [[famafrench2015_five_factor]] | [[asness_frazzini_pedersen_2019_qmj]] |
| Methodology | 2x3 size×OP sort, value-weighted | Conditional 6-portfolio size×quality (FF93 paterni) |
| HLZ MT-corrected | 2x3 t=2.92 BHY borderline / Bonferroni insig; joint t=4.09 sig | t=11.20 ham 4-factor alpha → recommended cutoffs çok rahat geçer |
| HMXZ q5 lens | Klasik 0.27% sig + q-factor alpha 0.04% insig (q-Roe span) | composite QMJ q5 captures (alpha 0.06% t=0.42 GRS p=0.12) |
| Wiki konum | FF5 origin paper'ın bileşeni | Yeni composite (Cycle 19); RMW'nin **kapsamlı alternative**'i |

**Sloan zinciri 4. halka (Cycle 19 keşif)**: QMJ Profitability ACC
component **Sloan 1996 explicit cite [s.7]** — F_ACCRUAL/G3 origin
paterni paralel (M-Score TATA Healy-Jones'tan farklı). Wiki için:
factors/Accruals.md QMJ ACC cross-link; Sloan zinciri 4 paper × 23 yıl.

**Wiki implication Faz 3 strategy spec için**:
- RMW factor exposure dört darbeden 1/4 (HLZ borderline + HXZ q-Roe
  span) → "saf alpha kaynağı" değil
- QMJ Profitability dimension daha kapsamlı (6 measure); 4-factor alpha
  ham sig çok güçlü ama HMXZ q5 captures
- Faz 3 spec: **RMW factor exposure proxy**; QMJ Profitability
  composite scoring **complementary** (winner-loser identification
  içinde quality-tarafı anchor)

## Decay / Post-Publication Performance + Multiple Testing Status

[[mclean_pontiff_2016_post_publication_decay]] aggregate %35 post-pub
decay multiplier RMW'a uygulanır.

[[harvey_liu_zhu_2016_multiple_testing]] çerçevesinde RMW'nin durumu inşa
metodolojisine duyarlı:
- **2x3 inşa t=2.92 (1963-2013):** BHY (3.0) **borderline**;
  Bonferroni (3.78) **insig**
- **Joint 2x2x2x2 t=4.09:** sig her cutoff'ta (Bonferroni / Holm / BHY
  hepsi sig)

Yani RMW'nin multiple-testing-corrected sig durumu **inşa şekline
duyarlı** — joint kontrolde sağlam, 2x3 standalone marjinal. Detay:
[[concepts/multiple_testing]] aggregate tablosu.

> ⚠️ **Cycle 13 ek (HXZ 2020 ingested) — DÖRT DARBE 1/4:**
> [[hou_xue_zhang_2020_replicating_anomalies]] [s.10, s.24] **RMW
> (operating profits-to-book equity, Ope) explicit insig** —
> paperin abstract'ında listed. **Klasik 0.27% (t=2.58) sig + q-factor
> alpha 0.04% (t=0.42) INSIG** [s.24]. q-factor Roe factor RMW'yi tam
> span ediyor. Wiki için: **HLZ multiple-testing borderline + HXZ
> q-factor span = çift düzeltme**. RMW exposure target değil — Faz 3
> strateji tasarımında ROE factor (q-factor model bileşeni) yerini
> alır. Detay [[concepts/anomaly_replication]] aggregate tablosu;
> [[concepts/post_publication_decay]] dört darbe çerçevesi tablosu.

## Implementation Notes

- **Required data:** Compustat veya Sharadar üzerinden revenues, COGS, SGA,
  interest expense, book equity (fiscal year-end t-1)
- **Calculation note:** "operating profitability minus interest expense" formülü
  [s.7]. Bu detay implementation'da kritik — interest expense'i çıkarmamak farklı
  bir faktör verir (örn. Novy-Marx GP/A interest expense'i çıkarmaz).
- **Annual rebalance:** Haziran sonu, NYSE 30/70 OP breakpoint'leriyle.
- **NYSE breakpoint asimetrisi:** Faktörün uzun bacağı (R, robust) ve kısa bacağı
  (W, weak) NYSE 30/70 percentile'larına göre belirlenir, ama tüm üniversi
  içerir. Bu, S&P 500-only için yeniden inşa gerektirir.

## Bu Faktörün Yumuşak Karnı

- **Faktörün kendisinin redundancy testi yapılmadı [s.19]:** Tablo 6 sadece HML'i
  test ediyor; "RMW redundant mı?" sorusu paperda doğrudan cevaplanmıyor — RMW'nin
  intercept'i ve diğer faktör spanning'inin t-stat'ı 3'ün üstünde [s.19], yani RMW
  *bu örneklemde* bağımsız information taşıyor.
- **Joint vs. ayrı sortlar [s.13]:** 2×3 ile 2×2×2×2 inşaları arasında RMW
  korelasyonu 0.80; yani inşa şekli bir miktar farklı sonuç üretir. Replikasyon
  hassasiyeti.
- **Yorum belirsizliği [s.27, s.21]:** RMW slope'ları her zaman univariate OP
  karakteristiğiyle line-up etmez. "Returns behave like firms that invest a lot
  despite low profitability" gibi multivariate slope yorumu paperın temel
  exegetic noktası.

## İlgili

- [[famafrench2015_five_factor]] — origin paper (mimicking-portföy çerçevesi)
- [[CMA]] — kardeş investment faktörü (ikisi birlikte FF5'e eklendi)
- [[HML]] — RMW eklendiğinde HML'in redundant olduğu bulgusu
- [[MKT_RF]], [[SMB]] — FF5'in diğer iki faktörü
- [[factor_model]] — 5-faktör asset pricing kavramı
- [[QMJ]] — **Cycle 19 ek**; QMJ Profitability dimension (6 measure)
  RMW'nin kapsamlı alternative'i (1 measure); winner-loser
  identification quality boyutu; Q2 fully-answered ANCHOR
- [[asness_frazzini_pedersen_2019_qmj]] — QMJ origin paper

---
type: paper
authors: [Fama, Eugene F., French, Kenneth R.]
year: 2015
title: "A Five-Factor Asset Pricing Model"
venue: "Journal of Financial Economics 116 (2015) 1-22"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2287202
local_path: raw/papers/fama_french_2015.pdf
cycle_35_note: "FF5 vs HXZ q-factor horse race [[papers/hou_xue_zhang_2015_q_factor]] Cycle 35 ✓; FF5 RMW Ope ↔ HXZ ROE + FF5 CMA ↔ HXZ I/A methodology farkı dokümante; Q15 fully-answered (HXZ 2015 [Section 3] FF5/Carhart vs q-factor PEAD/IVOL/distress/net issues subsumption test; q-factor outperforms 5/6 anomalies; Sloan accruals exception q-factor WORSE)"
cycle_37_note: "FF15 [s.13] CMA(small) sig vs CMA(big) insig finding'inin direct origin paper'ı [[papers/fama_french_2008_dissecting_anomalies]] Cycle 37 ✓ (FF 2008 [Tablo II + IV] asset growth size-conditional VW spread big -0.02% t=-0.10 INSIG + slope big -0.17 t=-0.86 INSIG); FF15 RMW Ope size-conditional zayıflığının root'u FF 2008'de (only small grup VW+EW >2σ hedge returns); FF ailesi methodology continuity 3-paper × 22+ yıl"
cycle_38_note: "FF15 RMW Ope vs Ball-GLN Cop methodology farkı dokümante [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓; Cop = Ope − ΔWC (working capital accruals çıkarılmış); Ball-GLN [Tablo 2 col 7] horse race Cop t=5.27 vs Ope t=1.56 INSIG Cop wins; Ball-GLN [Tablo 5] RMW^CbOp 4.88%/yr t=6.29 vs RMW^Op 3.25%/yr t=3.65; FF15 RMW Ope methodology Profitability zinciri 2. halka, Ball-GLN Cop 4. halka cash-based evolution; Q55 Cycle 26 fully-answered + Cycle 38 ek nüans"
ingested: 2026-04-27
tags: [factor_model, profitability, investment, value_redundancy, foundational, large_cap_relevant]
status: ingested
---

# Fama-French (2015) — A Five-Factor Asset Pricing Model

> 📝 **Atıf konvansiyonu:** `[Tablo N]` makalenin numaralı tablolarına; `[s. X]`
> JFE basılı sayfa numarasına; `[Eq. N]` makaledeki numaralı denkleme atıfta
> bulunur. Embedded text extract'ten okundu (`raw/papers/fama_french_2015.txt`).

## TL;DR

[[famafrench1993_three_factor]] üç-faktör modeline iki yeni faktör eklenir:
**RMW** (profitability: Robust Minus Weak operating profitability) ve **CMA**
(investment: Conservative Minus Aggressive asset growth). 1963-07 / 2013-12 örnekleminde
(606 ay) beş-faktör model üç-faktör modelden tüm LHS portföy setlerinde daha iyi
çalışır [Tablo 5, s.16-17]. **Kritik bulgu:** beş-faktör çerçevesinde **HML faktörü
redundant olur** — HML'in büyük ortalama getirisi MKT-RF, SMB, RMW ve CMA'ya
exposure'larıyla tamamen absorbe edilir. HML beş-faktör regresyonunda intercept'i
**-0.04% (t=-0.47, 2x3 inşası)**, 0.00% (t=0.01, 2x2), 0.02% (t=0.23, 2x2x2x2)
[Tablo 6, s.19]. Yazarlar parsimony durumunda HML'i drop eden 4-faktör (MKT-RF, SMB,
RMW, CMA) öneriyor; portföy tilt yorumu için ise HML yerine `HMLO` (orthogonal HML)
substitute öneriyor [s.27, Eq.(6)]. Modelin **başarısız olduğu yer**: yüksek yatırım
yapan ama düşük profitability'li küçük hisseler (örn. microcap × low-OP × high-Inv);
GRS testi tüm sortlarda 5-faktör modelini reddeder ama dispersion-of-intercepts
metriklerinde 5-faktör 3-faktöre net üstün [s.18, s.27].

## Tek Cümle Tezi

[[famafrench1993_three_factor]] üç-faktör modeline operating profitability (RMW) ve
investment (CMA) faktörleri eklendiğinde 25 size×profitability ve 25 size×investment
gibi yeni LHS sortlarında performans iyileşir; aynı zamanda **HML, kendisinin RMW ve
CMA'ya pozitif exposure'una indirgenerek redundant hale gelir** — 1963-2013 ABD
örnekleminde.

## Ortaya Konan Sinyaller / Faktörler

Üç-faktör modele eklenen iki yeni faktör (`SMB` revize edilmiş 2x3 yapısıyla
yeniden inşa):

- **`RMW`** ("Robust Minus Weak") — operating profitability mimicking faktörü.
  → [[RMW]]
- **`CMA`** ("Conservative Minus Aggressive") — asset-growth investment mimicking
  faktörü. → [[CMA]]
  > ⚠️ challenged by [[cooper_gulen_ion2018_asset_growth_factor_models]]:
  > CMA "investment proxy" yorumu sorgulandı. CGS-Ion 2018 [s.3-4] FF5
  > performansının CGS asset growth measure'a kritik bağlı olduğunu, CAPX/PPE
  > veya intangibles-adjusted total capital ile değiştirildiğinde **35
  > anomaly'den 23-24'ünü açıklayamadığını** (asset-growth-base 11/35 → 23-24/35)
  > gösterir. Yani CMA "asset growth proxy" demek **doğru**, ama "investment
  > proxy" yorumu (capex/debt ile reproduce edilebilir) **yanıltıcı**. Detay:
  > [[asset_growth_anomaly]].
- **`HMLO`** (orthogonal HML) — HML'in MKT-RF, SMB, RMW, CMA üzerine regresyonundan
  intercept + residual; ortalaması ~0, varyansı orijinal HML'in yaklaşık yarısı
  [s.20, Eq.(6)]. Bu wiki'de ayrı entity sayfası açılmadı; teknik bir varyant olarak
  [[HML]] sayfasına not eklendi.
- Mevcut faktörler ([[MKT_RF]], [[SMB]], [[HML]]) FF93'teki gibi tanımlanır ama
  paperda üç alternatif inşa kıyaslanır: 2×3, 2×2, 2×2×2×2 sortları [s.10-11].

### OP (Operating Profitability) tanımı [s.7]

Haziran t sıralaması için, fiscal year t-1 sonu muhasebe verisiyle:

`OP = (revenues − COGS − SGA − interest expense) / book equity (fiscal year-end t-1)`

NYSE breakpoint'leri (median Size + 30/70 OP percentile'ları için 2×3 sort).

### Inv (Investment) tanımı [s.8]

`Inv = (total assets fiscal year t-1 − total assets fiscal year t-2) / total assets t-1`

> 📝 Yazarlar değerleme denkleminden (Eq.(3), s.2-3) book equity büyümesinin teorik
> olarak doğru olduğunu, ancak total asset growth'un benzer / biraz daha geniş
> spread ürettiğini not eder [s.8]. **Wiki tarafında uygulama:** Sharadar'da
> hem book equity büyümesi hem total asset büyümesi mevcuttur; ikisini paralel
> hesaplamak iyi pratik olabilir.

### RMW ve CMA inşası — 2×3 sort (FF1993 yapısının paralel'i) [s.10]

`SMB`, `HML`, `RMW`, `CMA` inşası için **ayrı 2×3 sortlar**:

- **Size×B/M sortu** → `SMB(B/M)`, `HML`
- **Size×OP sortu** → `SMB(OP)`, `RMW`
- **Size×Inv sortu** → `SMB(Inv)`, `CMA`
- `SMB = (SMB(B/M) + SMB(OP) + SMB(Inv)) / 3` [s.10-11]
- Size breakpoint: NYSE median ME (June t-end). B/M, OP, Inv breakpoint'leri:
  NYSE 30/70 percentile'ları.
- Negatif BE ve finansallar dışlanmış (FF93 ile aynı kural) [s.6].

`RMW = (S/R + B/R)/2 − (S/W + B/W)/2`, ortak Size kontrolü ile.
`CMA = (S/C + B/C)/2 − (S/A + B/A)/2`, ortak Size kontrolü ile.

Paperda alternatif olarak 2×2 (B/M ve OP/Inv için NYSE median breakpoint) ve
2×2×2×2 (joint Size×B/M×OP×Inv kontrolü ile 16 portföy) inşaları da test edilir;
GRS sonuçları üç inşa için "neredeyse aynı" [s.18, s.27].

### Test evrenleri (LHS portföyleri) [s.6-9]

- 25 Size × B/M (5×5 NYSE quintile sortları) — FF93 ile aynı
- 25 Size × OP (5×5)
- 25 Size × Inv (5×5)
- 32 Size × B/M × OP (2×4×4)
- 32 Size × B/M × Inv (2×4×4)
- 32 Size × OP × Inv (2×4×4)

## Empirik Sonuçlar (sayılarla)

### Örneklem [s.6]

- Evren: NYSE/AMEX/NASDAQ, finansal hisseler hariç (CRSP+Compustat share codes 10/11)
- Dönem: 1963-07 / 2013-12 (606 aylık gözlem)

### Faktör portföylerinin özet istatistikleri (% aylık) [Tablo 4 Panel A, s.37]

**2×3 sort (FF93 yapısı, ana versiyon):**

| Faktör | Mean | Std | t(mean) |
|---|---|---|---|
| `RM-RF` | 0.50 | 4.49 | 2.74 |
| `SMB` | 0.29 | 3.07 | 2.31 |
| `HML` | 0.37 | 2.88 | 3.20 |
| `RMW` | 0.25 | 2.14 | 2.92 |
| `CMA` | 0.33 | 2.01 | 4.07 |

**2×2 sort:**

| Faktör | Mean | Std | t(mean) |
|---|---|---|---|
| `RM-RF` | 0.50 | 4.49 | 2.74 |
| `SMB` | 0.30 | 3.13 | 2.33 |
| `HML` | 0.28 | 2.16 | 3.22 |
| `RMW` | 0.17 | 1.52 | 2.79 |
| `CMA` | 0.22 | 1.48 | 3.72 |

**2×2×2×2 sort (joint kontrol):**

| Faktör | Mean | Std | t(mean) |
|---|---|---|---|
| `RM-RF` | 0.50 | 4.49 | 2.74 |
| `SMB` | 0.30 | 2.87 | 2.60 |
| `HML` | 0.30 | 2.13 | 3.43 |
| `RMW` | 0.25 | 1.49 | 4.09 |
| `CMA` | 0.14 | 1.29 | 2.71 |

> 📝 Joint kontrol (2×2×2×2) inşasında CMA primum'u 0.33%'dan 0.14%'e düşer, RMW
> primum'u korunur. Yazarlar bu sonucu "investment premium büyük ölçüde value
> premium ile çakışıyor" şeklinde yorumlar [s.13].

### Faktör korelasyonları (2×3, 1963-2013, 606 ay) [Tablo 4 Panel C, s.38]

| | `RM-RF` | `SMB` | `HML` | `RMW` | `CMA` |
|---|---|---|---|---|---|
| `RM-RF` | 1.00 | 0.28 | -0.30 | -0.21 | -0.39 |
| `SMB` |  | 1.00 | -0.11 | -0.36 | -0.11 |
| `HML` |  |  | 1.00 | 0.08 | 0.70 |
| `RMW` |  |  |  | 1.00 | -0.11 |
| `CMA` |  |  |  |  | 1.00 |

> 📝 **HML ↔ CMA korelasyonu = 0.70** [Tablo 4 Panel C, s.38]. "High B/M value
> firms tend to do little investment" [s.19]. Bu, HML redundancy bulgusunun
> mekanik temelidir: HML'in zaman serisi varyansının önemli kısmı CMA üzerinden
> taşınıyor.

### HML redundancy — Tablo 6 spanning regresyonları [s.19]

`HML(t) = a + b·(RM-RF)(t) + s·SMB(t) + r·RMW(t) + c·CMA(t) + e(t)`

**HML intercept'leri (1963-07 / 2013-12):**

| İnşa | a (HML intercept) | t(a) |
|---|---|---|
| 2×3 | -0.04% | -0.47 |
| 2×2 | 0.00% | 0.01 |
| 2×2×2×2 | 0.02% | 0.23 |

> ⚠️ **Bu, [[HML]] sayfasının "Subsumed by?" satırını dolduran kanıttır.** Üç farklı
> faktör inşasında da HML'in intercept'i istatistiksel olarak sıfırdan ayırt
> edilemez. Diğer 4 faktörün spanning regresyonlarında intercept'ler t-stat>3
> [Tablo 6, s.19].

**Mekanizma:** "the large average HML return is mostly absorbed by the slopes for
RMW and CMA. The CMA slopes are strongly positive ... the RMW slopes are also
strongly positive" [s.19]. Yani HML zaman serisi pozitif olarak hem CMA'ya hem
RMW'a yüklenir. Yorum: high-B/M (value) firmalarının `RMW(t)` ve `CMA(t)`
varyasyonuyla aynı yöne hareket etmesi.

### GRS testleri ve dispersion-of-intercepts [Tablo 5, s.16-18]

- GRS testi tüm 6 LHS portföy setinde tüm modelleri (3F, 4F, 5F) reddeder [s.16].
- 5-faktör modelin ortalama mutlak intercept'leri (`A|aᵢ|`) tüm setlerde 3-faktör
  modelden düşük [s.16].
- **Cross-section variance left unexplained (sampling-error düzeltmeli, β/α-tipi
  metrik):**
  - 25 Size×B/M: 5F = ~24%, 3F = ~37% [s.18]
  - 25 Size×OP: 5F = 6-12%, 3F = >50% [s.18]
  - 25 Size×Inv: 5F = ~28%, 3F = >50% [s.18]
  - 32 Size×OP×Inv: 5F = ~20%, 3F = 61-69% [s.18]
- **Anlamı:** model intercept'lerinin tutarlı sıfır olmaması istatistiksel olarak
  reddediliyor (GRS), ama nokta tahminlerinde 5F modelin "explanatory ratio"su
  3F modele göre net üstün.

### 5F modelin başarısızlığı: küçük + low-OP + high-Inv portföyleri [s.21-26]

- 25 Size×B/M sortunda microcap × extreme growth portföyü 3F intercept = -0.49%
  (t=-5.18); 5F intercept iyileşir ama hâlâ negatif: -0.29% (t=-3.31) [s.21].
- 32 Size×OP×Inv sortunda small × low-OP × high-Inv portföyü: 5F intercept = -0.47%
  (t=-5.89) [Tablo 11, s.26].
- Yazarlar yorumu: "small stocks of firms that invest a lot despite low profitability
  fare much worse than predicted" [s.27].
- **Önemli simetrisizlik:** Aynı karakteristikteki büyük hisseler için 5F intercept
  pozitif veya sıfır → davranışsal "mispricing" hipotezi tek başına açıklamaz
  [s.27-28].

### HMLO — orthogonal HML [s.20, Eq.(6)]

`HMLO = intercept + residual` from regression of HML on `(RM-RF, SMB, RMW, CMA)`.

5-faktör regresyonda HML yerine HMLO kullanmak intercept ve diğer faktör slope'larını
aynı bırakırken HMLO'nun ortalamasını ~0'a çeker. Bu, **value-tilt yorumu yapmak
istenirken redundancy nötrleştirmek için** önerilen substitute [s.20, s.27].

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | "Factor model" çerçevesi; 25 ve 32 portföy testleri. Stock-level top-N seçim formülasyonu yok. RMW ve CMA mimicking-portföyler tüm uzun-kısa dağılımı kullanır | N/A — vocabulary/asset-pricing test paperı |
| **Annual rebalance** | Tüm faktörler (HML, SMB, RMW, CMA) **yıllık** Haziran-end rebalance, NYSE breakpoint'leriyle [s.10-11]. Aylık return data ile test edilir | ✅ doğrudan fit |
| **Large-cap evrene transfer** | NYSE/AMEX/NASDAQ **all-stocks** evren, finansallar hariç. Large-cap-only kalibrasyon yok. **5F modelin başarısız olduğu portföy: küçük-cap × low-OP × high-Inv [Tablo 11, s.26]** — yani başarısızlık küçük-cap'te yığılı; büyük-cap'te 5F daha iyi performans gösterebilir (open question Q14) | ⚠️ **UYARI: doğrudan large-cap test yok**; ancak küçük-cap başarısızlığı large-cap için pozitif sinyal olabilir — Q14 ile yanıtlanacak |
| **NDX intangibles / growth firms** | RMW (operating profitability) growth firmalarda doğrudan ölçülebilir ama **R&D capitalization yapılmamış** — yüksek R&D'li tech firmalarda book equity yapay düşük → BE/ME ve dolayısıyla HML loadings çarpık. CMA (asset growth) tech firmalarda yüksek olabilir → CMA negatif yükleme = beklenen-getiri düşüşü | ⚠️ **UYARI: intangibles düzeltmesi yok**; Lev-Sougiannis 1996, Peters-Taylor 2017 ingestleri ile R&D-adjusted versiyon araştırılacak |

**Strateji tasarımına net implikasyon:** FF15 strateji benchmarking için
güncel (2013'e kadar) baseline'ı sağlar. **HML redundancy bulgusu strateji
tasarımı için kritik:** "saf value tilt" yerine RMW + CMA exposure'u almak,
1963-2013 ABD verisinde span eden bir alternatiftir [Tablo 6, s.19].
Ancak bu redundancy "may be specific to this sample" uyarısıyla geliyor [s.4]
— large-cap evrende ve post-2013'te tekrarlanırlığı açık.

## Limitler ve Caveats

- **HML redundancy iddiası örneklem-spesifik [s.4, s.19]:** Yazarlar açıkça
  uyarır: "we caution the reader that it may be specific to this sample".
  Pre-1963 ABD ve uluslararası örneklemler için test "interesting" olarak
  bırakılır → [[meta/open_questions]] yeni Q13.
- **Momentum dahil değil [s.14, s.28]:** Carhart 1997'nin UMD faktörü 5F'a
  eklenmiyor; yazarlar "for the LHS portfolios examined here, momentum slopes
  close to zero". Ancak FF (2014) anomaly testlerinde momentum LHS'i için
  UMD faktörü kritik [s.14].
- **GRS reddi [s.16]:** "all our models are incomplete descriptions of expected
  returns" — bu wiki'nin amacı için iyi bir uyarı: 5F bir baseline benchmark,
  exhaustive bir model değil.
- **Microcap problem'i [s.21-22, s.26]:** 5F'in en büyük başarısızlığı
  microcap segmentinde. **S&P 500 / Nasdaq 100 evrenleri large-cap-only**
  olduğundan **bu wiki için bu zayıflık marjinal olabilir** — bu kritik bir
  pozitif çıkarım. (Doğrulamak için S&P 500 evreninde test eden başka paper
  ingest'i gerekir → Q14.)
- **Joint vs. ayrı sortlar [s.13-14, s.27]:** 2×2×2×2 RMW/CMA korelasyonu HML ile
  artıyor (0.04→0.63 RMW; 0.70→0.37 CMA); yazarlar bu artışı "somewhat
  artificial" olarak nitelendiriyor.
- **OP tanımı interest expense'i çıkarır [s.7]:** "operating profitability minus
  interest expense" yazarlar tarafından kabul ediliyor. Net Income veya EBITDA
  kullanılmıyor. Sharadar/Compustat replikasyonunda calculation kontrolü gerek.
- **Annual rebalance:** Haziran sonu, FF93 ile aynı.

## İlgili Sayfalar

### Bu paperın ürettiği yeni faktör entity sayfaları
- [[RMW]] — Robust Minus Weak operating profitability faktörü
- [[CMA]] — Conservative Minus Aggressive investment faktörü

### Bu paperın update ettiği mevcut faktör sayfaları
- [[HML]] — "Subsumed by?" satırı bu paper'la dolduruldu (intercept ~0 in 5F)
- [[SMB]] — yeni inşa (3 sort'un ortalaması) FF2015 ile geldi; sayfa update edildi
- [[MKT_RF]] — kapsam genişletildi (1963-2013 örneklem)

### Kavramsal
- [[factor_model]] — 5-faktör extension burada belgelenir

### İlgili paperlar
- [[famafrench1993_three_factor]] — 3-faktör baseline
- [[carhart1997_four_factor]] — paralel post-FF3 extension (UMD/momentum); FF15
  ile aynı core üzerine farklı ek
- [[cochrane2011_discount_rates]] — FF15'in HML redundancy bulgusu Cochrane'in
  1. sorusunun ("which characteristics are subsumed by others?") tipik örneği
- (sonra) Hou-Xue-Zhang 2015 — q-factor model, 4-faktör (MKT, SMB, ROE, IA)
  paralel literatür; FF15 sonuçlarına yakın ama HML'siz
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 (q-factor + expected growth)
  model security analysis stratejilerini test eder; FF5'in HML+RMW yapısına
  alternatif HML-siz q-factor 5F formülasyonu; QMJ q-factor ile span edilmiyor
- [[novy_marx_2013_gross_profitability]] — **Cycle 23**; FF15 RMW
  factor inşası **Novy-Marx GP/A literatür hattı kökü** (paper [s.4]
  explicit cite); RMW Ope methodology farkı (numerator REVT−COGS−SG&A−interest;
  denominator BE) Novy-Marx GP/A (REVT−COGS / AT) ile iki seviye fark.
  Profitability zinciri 2. halka; Q14 CMA/RMW partial-stronger (RMW Ope
  large-cap kanıt aday).
- [[feng_giglio_xiu_2020_factor_zoo]] — **Cycle 26**; FF15 RMW
  (profitability) + CMA (investment) **DS LASSO 150-factor library
  lens'inde DS-sig** (Tablo 1, since-2012 factors); FF5 factor
  independence FGX cross-test çift teyit. RMW Ope için **iki paralel
  bulgu**: HXZ q-factor lens INSIG (1/4) + FGX DS LASSO sig
  (methodology farkı: q-factor model lens vs 150-factor library lens
  iki ayrı epistemic question; çelişki değil — [[factors/RMW]]
  detay). Q15 + Q24 partial-stronger (FF5 vs HXZ q-factor cross-
  subsumption).
  ama q5 capture ediyor [Tablo 4] — Q15 (FF5 vs HXZ horse race) için partial
  cevap
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — CMA factor empirical
  performansının CGS asset growth measure'a kritik bağlı olduğu kanıt
  [s.3-4]; FF5'in investment factor inşasının (CGS measure'ı kullandığı için)
  FF15 paperında dolaylı varsayım olan "investment proxy" yorumunu sorgular.
  Q15 (FF5 vs HXZ) için her iki modelin investment factor'ünün ortak
  kırılganlığı kanıtı.
- (sonra) Asness-Frazzini-Pedersen 2019 — QMJ (Quality Minus Junk), profitability
  faktörü ile yapısal benzerlik
- [[harvey_liu_zhu_2016_multiple_testing]] — FF5 faktörlerinin
  multiple-testing-corrected sig durumu: HML (1963-2013) t=3.20 BHY sig
  / Bonferroni borderline; **RMW 2x3 t=2.92 BHY borderline / Bonferroni
  insig**; RMW joint 2x2x2x2 t=4.09 sig her cutoff; CMA 2x3 t=4.07 sig
  her cutoff; CMA joint t=2.71 BHY borderline / Bonferroni insig.
  **Modelin yarısı multiple-testing-corrected zayıf** ama joint kontrol
  + incremental information argümanları modeli ayakta tutuyor. Detay
  [[concepts/multiple_testing]] aggregate tablosu.
- [[hou_xue_zhang_2020_replicating_anomalies]] — FF15 faktörlerinin
  **NYSE-VW replication + q-factor lens'inde durumu** [s.10, s.24]:
  **RMW (Ope) klasik 0.27% (t=2.58) sig + q-factor alpha 0.04%
  (t=0.42) INSIG**; paper abstract'ında **RMW (Ope) explicit listed
  insig** [s.10] (operating profits-to-book equity wiki için kritik
  düzeltme — HLZ + HXZ çift düzeltme: RMW exposure target değil).
  **CMA klasik 0.34% (t=3.63) sig + q-factor alpha 0.01% (t=0.32)
  INSIG** — q-factor I/A factor CMA'yı tam span ediyor
  ([[cooper_gulen_ion2018_asset_growth_factor_models]] uyumlu).
  HML (Bm) klasik 0.59% sig + q-factor alpha 0.18% insig — q-factor
  I/A span. Detay [[concepts/anomaly_replication]] aggregate tablosu.

## Çelişkiler / Tartışmalar

> ⚠️ **HML redundancy ↔ HML'in pozitif primum'u:** [Tablo 4, s.37]'de HML 2x3
> mean'i 0.37%/ay, t=3.20 — yani **standalone HML hâlâ pozitif premium üretir**.
> Redundancy iddiası "5F modelinde span edilebilir" anlamındadır, "HML primum
> yoktur" anlamına gelmez. Bu nüans → [[meta/contradictions]] dosyasında
> açıklandı.

> 📝 Hou-Xue-Zhang (2012/2015) q-factor modeli paralel olarak HML olmadan 4
> faktör (MKT, ME, ROE, IA) öneriyor [bu paperda s.4 ve s.29 referansla].
> Bu paper HXZ4 ile FF5'i doğrudan karşılaştırmıyor — sadece "interesting that
> HXZ also drops HML" notu var. → [[meta/open_questions]] Q15.

> ⚠️ **Cycle 19 ek — RMW vs QMJ Profitability dimension paralel:**
> [[asness_frazzini_pedersen_2019_qmj]] QMJ Profitability dimension =
> 6 measure (GPOA + ROE + ROA + CFOA + GMAR + ACC) z-score average.
> FF15 RMW = 1 measure (operating profitability). QMJ Profitability
> US long sample 1956-2012 + 24 country broad sig 1/3/4-factor alpha;
> RMW (Cycle 4) 2x3 t=2.92 BHY borderline / Bonferroni insig + joint
> 2x2x2x2 t=4.09 sig + HXZ q-Roe span (dört darbe 1/4). **Wiki için
> Q14 partial-stronger (Cycle 19)**: FF5 başarısızlık portföyü direct
> test değil ama QMJ large-cap-only kanıt FF5 başarısızlığının large-
> cap evrene transfer olmadığına dair yapısal kanıt; AQR data setleri
> (Tier 3 #55) tam Q14 cevabı için ek ingest. RMW factor exposure dört
> darbe 1/4 → Faz 3 strategy spec'inde **target değil**, factor model
> baseline; QMJ Profitability composite scoring tarafı complementary.

> ⚠️ **FF15 HML redundancy ↔ Lev-Srivastava 2020 adjusted HML primum
> (Cycle 17 ek, scope-dependent):**
> - **FF15 [Tablo 6, s.19]**: Vanilla HML 5-faktör altında redundant
>   (a≈-0.04%, t≈-0.47); FF5 + 4 factor HML'ı span ediyor.
> - **[[lev_srivastava_2020_value_failure]] [Section 5]**: Adjusted HML
>   methodology (intangibles-aware adjusted BV) ile **39 yılın 34'ünde**
>   conventional HML'ı geçer; vanilla HML decay'in büyük kısmı intangibles
>   bias'a bağlı.
>
> **Çelişki değil, scope-dependent**:
> - FF15: vanilla HML measurement (reported BV / market) FF5 redundant
> - Lev-Srivastava: adjusted HML (adjusted BV / market) primum hayatta
> İki paper farklı methodology üzerinde sonuç veriyor; **aynı vanilla
> HML için aynı şeyi söylüyor olabilir** (FF15 vanilla redundant; Lev-
> Srivastava vanilla 1990s-2018 negatif decay). Adjusted versiyonun FF5
> altında redundant olup olmadığı modern test gerekli; methodology hazır
> [[concepts/intangibles_adjusted_accounting]] F bloğu 3 ayak.
> [[meta/contradictions]]'a eklenmedi (paralel methodology, complementary
> finding).

## Açık Sorular (bu paperın açtığı / dokunduğu)

- HML redundancy'sinin örneklem-bağımlılığı (pre-1963, uluslararası, post-2013) →
  yeni Q13.
- 5F modelin küçük cap × low-OP × high-Inv başarısızlığı S&P 500 / Nasdaq 100
  evrenlerinde ne ölçüde hayatta kalır? Eğer microcap-spesifikse, large-cap
  stratejisi için 5F **daha iyi** çalışıyor olabilir → yeni Q14.
- HXZ q-factor modeliyle 5F arasında doğrudan horse race wiki'de yok →
  Hou-Xue-Zhang 2015 ingest'iyle Q15 olarak eklenecek.
- 5F'in equal-weighted versiyonu ve Sharadar-tabanlı replikasyon (S&P 500 /
  Nasdaq 100 evrenleri için): tasarım fazında ele alınacak.

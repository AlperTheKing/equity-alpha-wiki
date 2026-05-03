---
type: factor
name: F_Score
category: composite_quality
direction: long_high  # uzun yüksek F (8-9), kısa düşük F (0-1) — sadece high-BM evrende
data_lag_required: "Fiscal year-end + 5 ay (Piotroski 2000 konvansiyonu); 10-K filing lag pratik olarak 60-90 gün"
rebalance_frequency: annual
universe_tested: ["COMPUSTAT highest BM quintile, 1976-1996"]
---

# F-Score (Piotroski 9-Score)

## Tanım [[piotroski2000_f_score]] [s.7-9]

`F_SCORE = F_ROA + F_CFO + F_ΔROA + F_ACCRUAL + F_ΔMARGIN + F_ΔTURN + F_ΔLEVER + F_ΔLIQUID + F_EQ_OFFER`

9 binary (0/1) sinyalin toplamı. Range: 0-9.

### Bileşenler

**Profitability (4):**
- `F_ROA = 1` if net income / beg. total assets > 0
- `F_CFO = 1` if cash flow from operations / beg. total assets > 0
- `F_ΔROA = 1` if ROA(t) > ROA(t-1)
- `F_ACCRUAL = 1` if CFO > ROA (accrual ≤ 0; earnings cash-supported) (origin: [[sloan1996_accruals_anomaly]])

**Leverage / Liquidity (3):**
- `F_ΔLEVER = 1` if long-term debt / avg total assets oranı **azaldıysa**
- `F_ΔLIQUID = 1` if current ratio **arttıysa**
- `F_EQ_OFFER = 1` if firma önceki yıl equity ihraç etmediyse

**Operating Efficiency (2):**
- `F_ΔMARGIN = 1` if gross margin (= (sales-COGS)/sales) **arttıysa**
- `F_ΔTURN = 1` if asset turnover (= sales / avg total assets) **arttıysa**

> 📝 Sadece **high-BM (value)** firmalarda anlamlandırılan işaretler. Sağlıklı /
> growth firmalarda işaretler farklı yorumlanmalı [[piotroski2000_f_score]] [s.7].

## Origin

- İlk paper: [[piotroski2000_f_score]] (Piotroski 2000)
- Yazar: Joseph D. Piotroski (U Chicago GSB)

## Reported Performance Across Studies

| Paper | Dönem | Evren | Spread (1y market-adj) | t-stat | Notlar |
|---|---|---|---|---|---|
| [[piotroski2000_f_score]] | 1976-1996 | COMPUSTAT BM-Q5 | +0.230 (High − Low) | 5.59 | [Tablo 3 Panel A, s.16]; n=14,043; binary 0/1 |
| [[piotroski2000_f_score]] long-only | aynı | aynı | +0.075 (High − All) | 3.14 | [Tablo 3 Panel A, s.16] |
| [[li_mohanram2019_quality_value]] (continuous, all-firms) | 1973-2012 | NYSE/AMEX/NASDAQ all | +7.44% (Q5−Q1) | sig 1% | [Tablo 2, s.15-16]; n=98,766; **continuous rank-based 0-1**, all-firms — orijinalden 3x düşük spread (post-publication decay + universe genişlemesi + methodology revision) |
| [[li_mohanram2019_quality_value]] (large-cap only) | aynı | aynı, large size tercile | +4.43% standalone | — | [Tablo 7, s.22]; standalone'da zayıf |
| [[li_mohanram2019_quality_value]] (F & V/P combined, large-cap) | aynı | aynı, large size tercile | **+11.92%** | sig 1% | [Tablo 7, s.22]; combined approach Q18 partial cevap |
| [[li_mohanram2019_quality_value]] (3F alpha) | aynı | all-firms | +7.98% annualized | sig 1% | [Tablo 9 Panel A, s.25]; Fama-French 3F kontrolü |
| [[hou_mo_xue_zhang_2020_security_analysis]] (q-factor alpha) | 1972-2018 | NYSE/AMEX/NASDAQ all | 0.23%/0.10%/0.12% (micro/small/big quintile) | t=1.56/0.85/0.84 (insig) | [Tablo 2, s.18-19]; q-factor model F-Score'u tam açıklamaz, GRS reject (p=0.01) |
| [[hou_mo_xue_zhang_2020_security_analysis]] (**q5 alpha**) | aynı | aynı | **0.33%/0.10%/0.03%** (micro/small/big) | t=2.67/0.81/0.15 | [Tablo 2, s.18-19]; **microcap'te anlamlı, small/big insignificant**; q5 GRS cannot reject (p=0.09); ROE factor key driver |
| [[mclean_pontiff_2016_post_publication_decay]] aggregate decay multiplier | (82 anomaly aggregate, 1972-2011) | NYSE+AMEX+NASDAQ all-stocks aggregate | aggregate post-pub decay **%35** (sig 1%); F-Score paper ref list'inde explicit listed değil | (anomaly-equal-weighted aggregate t-stat values [Tablo 2, s.31]) | [Tablo 3, s.32] aggregate decay; F-Score-spesifik decay rakamı paperdan tek-tek çıkmıyor; aggregate uygulanır → decay-adjusted +23.0%×0.65 = **+14.95%** baseline; modern empirik karşılaştırma için Li-Mohanram +7.44% satırı (yukarıda) |

## Faktör Ailesi İçindeki Yeri

- **Korelasyon literatürde:** F-Score ↔ HML korelasyonu yüksek olması beklenir
  (her ikisi de high-BM firmalara pozitif yüklenir) ama F-Score *high-BM
  içinde diferensiyel* — yani saf HML üstüne ek skor. Wiki'de doğrudan
  korelasyon kanıtı henüz yok.
- **Subsumed by?** **KISMI subsume — q5 model (HMXZ 2020) F-Score'u microcap
  hariç span ediyor** [[hou_mo_xue_zhang_2020_security_analysis]] [Tablo 2, s.18-19]:
  q5 alpha small/big = 0.10% / 0.03% (insig); microcap = 0.33% (t=2.67, sig).
  ROE factor ana açıklayıcı. q-factor model (q4) F-Score'u açıklamaz (GRS
  p=0.01) ama q5 (q4 + expected growth) yeterli (GRS p=0.09). FF 6-factor
  model (FF5+UMD) da F-Score'u yakalıyor [HMXZ s.19 fn 10]. Yani F-Score
  large-cap segmentinde **risk premium aracılığı** olarak çalışıyor; standalone
  alpha kaynağı microcap'e sınırlı.

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

> ⚠️ **F-Score large-cap evrende istatistiksel olarak anlamlı değil
> [[piotroski2000_f_score]] [Tablo 4, s.19]:**
> - Small (bottom 1/3 ME): High − Low = +0.270 (t=4.71) ✓
> - Medium: +0.173 (t=2.87) ✓
> - **Large (top 1/3 ME): +0.152 (t=1.88, p=0.224)** ✗

Bu, **wiki'nin amacı (S&P 500 / Nasdaq 100) için F-Score'un orijinal formuyla
doğrudan kullanılamayacağının kanıtıdır.** Mohanram 2005 (G-Score, growth-tarafı)
ve Li-Mohanram 2019 (combined) ingest edildiğinde large-cap-friendly versiyon
araştırılacak. Bu nokta → [[meta/open_questions]] Q18.

## Decay / Post-Publication Performance

[[mclean_pontiff_2016_post_publication_decay]] [Tablo 3, s.32] 82 anomaly
aggregate **post-pub decay %35 (sig 1%)**, %10 statistical bias (insig).
Paper ref list'inde Piotroski 2000 explicit listed **değil** — F-Score
paper-spesifik anomaly-level decay rakamı tek-tek çıkmıyor; aggregate
multiplier (×0.65) uygulanır.

**Modern empirik karşılaştırma** (composite-score-spesifik somut tek
örnek): [[li_mohanram2019_quality_value]] [Tablo 2, s.15-16] —
orijinal Piotroski +23.0% (1976-1996, BM-Q5, binary) → modern continuous
all-firms (1973-2012) **+7.44%** = ~3x düşüş. McLean-Pontiff aggregate
%35 + universe genişlemesi + binary→continuous + industry classification
revision karışık etkenler.

> ⚠️ **Çift darbe (Cycle 11 kullanıcı kararı 6 vurgusu):**
> [[mclean_pontiff_2016_post_publication_decay]] [Tablo 8, s.37] post-pub
> decay büyük/likit/divid-payer/düşük-idio firmalarda **DAHA güçlü**
> (Size +1.442 sig, Dollar Vol +1.380 sig, Idio Risk -1.420 sig, Divid
> +1.439 sig). F-Score zaten in-sample large-cap'te zayıf
> ([[piotroski2000_f_score]] [Tablo 4, s.19] +0.152 t=1.88 p=0.224 insig);
> wiki amaç evrenleri (S&P 500 + NDX) tam olarak bu profilde → kümülatif
> yapısal risk. Detay [[post_publication_decay]] decay-adjusted spread
> tablosu — F-Score satırı NDX agresif sensitivity ×0.50 = +11.50%
> (vs aggregate ×0.65 = +14.95%).

### Multiple Testing Status (Cycle 12 ek)

[[harvey_liu_zhu_2016_multiple_testing]] çerçevesinde:
- **F-Score (BM-Q5 origin, t=5.59):** sig her cutoff'ta (Bonferroni /
  Holm / BHY hepsi sig)
- **F-Score (large-cap partition, Tablo 4 t=1.88):** **kesin insig**
  tüm cutoff'larda (klasik 1.96 borderline + multiple-testing kesin
  çürütme)

> ⚠️ **Dört darbe çerçevesi (Cycle 12 + Cycle 13 sentez):** F-Score
> large-cap standalone dört hurdle'ın **HİÇBİRİNDEN** geçemiyor
> (in-sample insig + post-pub decay agresif + MT-corrected insig +
> replication paralel insig = 0/4). Wiki Faz 3 strateji baseline'da
> **standalone kullanılmaz**; F & V/P combined kompanse eder
> (Li-Mohanram +11.92% large-cap, üç darbe 3/3 + replication ortogonal
> Q31 = 3/4). Detay [[concepts/post_publication_decay]] dört darbe
> çerçevesi tablosu; [[concepts/anomaly_replication]] aggregate tablosu.

**Cycle 13 ek (HXZ 2020 ingested):**
[[hou_xue_zhang_2020_replicating_anomalies]] [s.27] F-Score quarterly
(Fq) durumu: 1m/6m/12m horizon'da klasik 0.58%/0.53%/0.42%
(t=2.47/2.52/2.22) **sig**; **q-factor alpha 0.13%/0.15%/0.07%
(t=0.58/0.86/0.49) INSIG** — q-factor Roe factor F-Score'u tam span
ediyor. HMXZ Security Analysis (Cycle 8) ile uyumlu. F-Score (BM-Q5
origin) **3/4** (q-factor span = Roe factor exposure proxy); large-cap
**0/4** (üstte detay). **Earnings announcement abnormal returns (Abr)**
[s.27] q-factor alpha 0.66% (t=4.49) **sig** — Piotroski 2000 [s.4-5]
F-Score spread'in 1/6'sı Abr penceresinde realize → behavioral
mekanizmanın q-factor lens'inde de hayatta kalan bileşeni.

## Implementation Notes

- **Required data:**
  - Income statement: net income, sales, COGS, interest expense
  - Cash flow statement: CFO
  - Balance sheet: total assets (t ve t-1), current assets, current liabilities,
    long-term debt
  - Equity issuance flag (CFS financing activities veya share count delta)
- **Compustat fields (rough):** NI, OANCF (CFO), AT, LCT, ACT, DLTT, SALE, COGS,
  CSHO (delta için)
- **Sharadar mapping:** Sharadar Core US Fundamentals'da bu 8 kalem mevcut. F-Score
  hesaplaması için **9 sinyalin tümü trivial computation** ile yapılabilir.
- **Annual rebalance:** [[piotroski2000_f_score]] [s.11] fiscal year-end + 5 ay
  itibarıyla portföy formation. Modern PIT data ile lag 60-90 güne kısalabilir.
- **Binary vs. continuous:** [[piotroski2000_f_score]] [s.16] continuous (rank
  toplamı) versiyon test etti, "qualitatively similar" sonuç verdi ama spread
  daha küçük (0.092 vs. 0.230). Modern uygulamada continuous tercih edilebilir.
- **NOT EQUAL-WEIGHTED:** F-Score 9 bileşenin **eşit ağırlıklı** toplamı. Optimum
  ağırlıklandırma factor analysis ile yapılabilir (yazar açıkça "not optimal"
  demiş [s.7 fn 2]).

## Bu Faktörün Yumuşak Karnı

- **Large-cap'te zayıf [[piotroski2000_f_score]] [Tablo 4, s.19]:** Yukarıda
  detaylandırıldı. Wiki'nin amacı için ana kısıtlama.
- **Universe high-BM ile sınırlı:** Tüm evrene (sektör-nötr, all S&P 500)
  uygulandığında F-Score'un anlamı bozulur — sinyaller financially distressed
  firmalar için kalibre edildi.
  - F-Score growth evrende test edilmedi, ancak **Mohanram (2005) paralel
    yaklaşımı low-BM evrende test etti → [[G_Score]]**. İki skor birlikte
    value+growth tüm evreni kaplar; orta-BM (BM-Q3) için Li-Mohanram 2019
    birleşik yaklaşımı (henüz wiki'de yok).
- **Equal-weighted binary [s.7 fn 2 + s.10]:** Optimum değil; continuous +
  evren-spesifik breakpoint daha iyi performans verebilir.
- **Sektör nötrleştirme yok:** Yazar industry-adjusted versiyon test ettiğini
  belirtir [s.7 fn 3] ama detay vermez. Sektörler arası baseline farklılığı
  için (örn. yüksek leverage tech vs. utility) ayrı kalibrasyon gerekir.
- **Microcap-driven:** Tablo 4 kanıtı mikrokap segmentinde primum'un yığıldığını
  gösteriyor. **Trading cost / capacity** sorunları paperda detaylı tartışılmıyor.
- **Forensic filter eksikliği — KAPANDI Cycle 18:** F-Score 9 bileşeni
  fundamental winner-loser ayrımı yapar ama **manipulation detection
  yapmaz** (false positive: high-BM evren içinde GAAP-violation
  manipulator firma F-Score'da yüksek skor alabilir). Cycle 18'de
  [[beneish_1999_m_score]] M-Score forensic filter olarak entegre
  edildi: F & M screen-and-rank combined yaklaşım Faz 3 design
  (Q9 partial cevap; Q45 value-trap-avoidance filter ile birlikte).

## İlgili

- [[piotroski2000_f_score]] — origin paper
- [[earnings_quality]] — F_ACCRUAL bileşeninin kavramsal temeli
- [[fundamental_scoring]] — F-Score'un ait olduğu skorlama paradigması
- [[winner_loser_identification]] — F-Score'un ait olduğu metodolojik paradigma
- [[contextual_fundamental_analysis]] — F-Score sinyallerinin sadece high-BM'de
  kalibre olması bu kavramın örneği
- [[value_premium]] — F-Score'un anchor'lı olduğu style premium
- [[HML]] — F-Score "saf HML üstü" diferensiyel filtre
- [[factor_model]] — F-Score'un asset-pricing model içindeki konumu
- [[G_Score]] — Mohanram 2005 growth muadili (komplemanı)
- [[li_mohanram2019_quality_value]] — F-Score continuous-rank revision + V/P/PEG ile combined; large-cap zayıflığını V/P ile compansation
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 model lens'inde F-Score microcap hariç span; risk premium yorumu
- [[comparisons/f_score_vs_g_score]] — head-to-head karşılaştırma sayfası
- [[Magic_Formula]] — alternatif composite (q5 ile tam span; F-Score microcap'te alpha korur)
- [[M_Score]] — **Cycle 18 ingest tamam (Beneish 1999)**; 8-bileşenli
  forensic composite; F & M screen-and-rank combined yaklaşım: M-Score
  yüksek olanlar elenir filter olarak, sonra F-Score Q5 long. Concept
  seviyesinde bağ; akademik combined backtest yok (Quantitative Value
  Gray-Carlisle 2012 Tier 3 kitap pratik literatür). Q9 partial cevap
  (Cycle 18); Faz 2 sentez aşamasında modern data ile combined
  empirical test
- [[beneish_1999_m_score]] — M-Score origin paper
- [[QMJ]] — **Cycle 19 ingest tamam (Asness 2019)**; 22 measure → 4
  dimension z-score composite; epistemik düzlem aynı (winner-loser
  identification, signal); evren farkı: F-Score high-BM (BM-Q5) vs QMJ
  all-cap (large/small ayrı). Combined yaklaşım: F-Score (binary 9-
  component value-side anchor) + QMJ (continuous 4-dimension all-cap
  quality) Faz 3 design adayı; F-Score F_ACCRUAL ↔ QMJ Profitability
  ACC Sloan zinciri paralel
- [[asness_frazzini_pedersen_2019_qmj]] — QMJ origin paper
- [[accruals_anomaly]] — Sloan 1996 anomalisi (F_ACCRUAL bileşeninin
  kavramsal omurgası); spesifik mekanizma: investor fixation + persistence farkı
- [[Accruals]] — total accrual standalone factor entity (Sloan continuous decile)
- [[sloan1996_accruals_anomaly]] — F_ACCRUAL'in **origin paper'ı**
- [[Asset_Growth]] — F_ΔLEVER ve F_EQ_OFFER ile dolaylı bağ (debt/equity-funded
  asset growth proxy); ama F-Score literature kökü Myers-Majluf 1984
  (bu wiki'de yok, bkz. [[meta/data_gaps]]), CGS asset growth değil
- [[asset_growth_anomaly]] — yapısal yakın anomaly (working capital +
  growth bileşenleri F_ACCRUAL ile partial overlap)

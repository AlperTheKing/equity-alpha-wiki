---
type: factor
name: G_Score
category: composite_growth_quality
direction: long_high  # uzun yüksek G (6-8), kısa düşük G (0-1) — sadece low-BM evrende
data_lag_required: "Fiscal year-end + 4 ay (Mohanram 2005); R&D/capex/advertising 10-K'da raporlu, lag 60-90 gün"
rebalance_frequency: annual
universe_tested: ["COMPUSTAT lowest BM quintile, 1979-1999"]
---

# G-Score (Mohanram 8-Score)

## Tanım [[mohanram2005_g_score]] [s.7-11]

`G_SCORE = G1 + G2 + G3 + G4 + G5 + G6 + G7 + G8`

8 binary (0/1) sinyalin toplamı. Range: 0-8.

> 📝 **Methodoloji:** [[piotroski2000_f_score]]'dan kritik fark: **G-Score'un 6
> sinyali (G1, G2, G4-G8) "industry median (2-digit SIC, contemporaneous low-BM
> peers)"a göre level karşılaştırma**. F-Score 5 sinyal "kendi geçmişine göre
> değişim" (Δ-based). Mohanram bu seçimi [s.8] Soliman 2003 (industry-adjusted
> DuPont) ve Beneish-Lee-Tarpley 2001 (contextual FSA) atıflarıyla gerekçelendirir.

### Bileşenler

**Profitability (3) — industry-median:**
- `G1 = 1` if ROA = (NI before extra. / beg. total assets) > industry median
- `G2 = 1` if cash flow ROA = (CFO / beg. total assets) > industry median
- `G3 = 1` if CFO > NI (firm-level, accrual ≤ 0; Sloan paterni — *non-industry*) (origin: [[sloan1996_accruals_anomaly]])

**Naive Extrapolation / Stability (2) — industry-median:**
- `G4 = 1` if 5-yıllık ROA varyansı **<** industry median (earnings stability)
- `G5 = 1` if sales growth varyansı **<** industry median (growth stability)
  - Min 3 yıl geçmiş veri; eksikse 0.

**Conservatism / Future Growth (3) — industry-median:**
- `G6 = 1` if R&D / beg. assets > industry median
- `G7 = 1` if capex / beg. assets > industry median
- `G8 = 1` if advertising / beg. assets > industry median

> 📝 G6/G7/G8 bilinçli olarak "yüksek = iyi" yönünde. Yazar tezi [s.10-11]:
> "yüksek R&D/capex/advertising → conservatism nedeniyle muhasebede gizli
> intangible → book equity yapay düşük → firma BM-Q5'de *muhasebe nedeniyle*,
> *over-valuation* nedeniyle değil → gelecekte upside."

## Origin

- İlk paper: [[mohanram2005_g_score]] (Mohanram 2005)
- Yazar: Partha S. Mohanram (Columbia Business School)
- Mohanram acknowledgments [s.1] Joe Piotroski'yi içerir; G-Score F-Score'un
  growth-tarafı paralel'i olarak doğrudan motive edilmiş

### G6 dual origin attribution (Cycle 15 ek)

[[lev_sougiannis_1996_rd_capitalization]] ingest sonrası G6
(R&D / Assets) bileşeni için **dual origin** belirgin:

- **Paper-spesifik origin** (Mohanram 2005 [s.10-11]): R&D'nin
  "conservatism signal" yorumu — yüksek R&D = muhasebede gizli
  intangible = book equity yapay düşük = high BM-Q5'te muhasebe
  nedeniyle (over-valuation değil) = gelecekte upside. Mohanram'ın
  signal interpretation'ı kendi paper'ında özgün.

- **Literatür hattı kökü** (Lev-Sougiannis 1996): R&D capitalization
  + adjusted earnings + adjusted book equity + R&D capital'ın
  subsequent return prediction (RDC/M coefficient sig, RDC-yoğun
  firmalarda 4.57% yıllık implication) — G6'nın **teorik dayanağı**.
  Mohanram 2005 conservatism yorumu Lev-Sougiannis'in "R&D as
  intangible asset" empirik kanıtı üzerine inşa edilebilir.

> 📝 Cycle 9'da Sloan F_ACCRUAL/G3 origin attribution pattern'ı
> kullanılmıştı (paper-spesifik + literatür hattı kökü ayrımı);
> Cycle 15'te G6 için paralel pattern uygulandı. Detay
> [[concepts/intangibles_adjusted_accounting]].

### G6/G7/G8 Peters-Taylor 2017 framework'ünde sınıflandırma (Cycle 16 ek)

[[peters_taylor_2017_intangible_capital]] Lev-Sougiannis R&D-only
methodology'sini total intangible capital'a genişletir. G-Score'un
intangibles-related üç bileşeni Peters-Taylor framework'ünde explicit
sınıflandırılır:

| G-bileşen | Mohanram conservatism yorumu | Peters-Taylor capital category | İlgili capital flow |
|---|---|---|---|
| **G6 (R&D / Assets)** | Conservatism signal: yüksek R&D = muhasebede gizli intangible asset | **Knowledge Capital** | R&D perpetual inventory (`xrd`); BEA industry-specific δ |
| **G7 (Capex / Assets)** | Growth firma fundamental signal: yüksek capex = expansion | **Physical Capital** (intangibles dışı) | Yıllık CAPX (`capx`); PP&E expansion |
| **G8 (Advertising / Assets)** | Conservatism signal: yüksek advertising = brand/customer relationship building | **Organization Capital** alt-bileşeni | SG&A 30%'inin advertising kısmı; Hulten-Hao 2008 paralel |

**Methodology hierarchy:**
- Mohanram 2005 industry-median yaklaşımı (2-digit SIC) **firm-level
  intra-industry RELATIVE intensity** ölçer (G6/G7/G8 binary 1/0)
- Peters-Taylor 2017 **firm-level absolute capital stocks** ölçer
  (perpetual inventory; CONTINUOUS measure)
- İki yaklaşım **complementary**:
  - G-Score: industry-relative composite signal (cross-section
    fundamental scoring)
  - Peters-Taylor: cross-time firm-level capital stock measurement
    (corporate finance methodology)

**Q19 + Q40 implications:** NDX evrende G-Score industry-median
hesaplama Mohanram 2-digit SIC sınıflandırmadan GICS sektörlerine
geçişte (Q19) Peters-Taylor methodology paralel kalibrasyon
(SG&A θ=30% NDX-spesifik adjustment, Q40) gerekebilir. Faz 3 design
decision.

> 📝 **Yön farkı (G7 ⊕ vs CGS Asset Growth ⊖):** G7 yüksek-capex
> long, CGS asset growth yüksek long-low. Bu paradoks Peters-Taylor
> framework'ünde **resolve** ediliyor: G7 sadece **physical capital**
> ölçer, asset growth measure (TA bazlı) ise **physical + intangibles
> + working capital** karışık. Mohanram'ın hi-tech firmalarda yüksek-
> capex yönü pozitif yorumlaması Peters-Taylor methodology kapsamında
> "physical capital growth" ölçümüne karşılık gelir, total asset
> growth'a karşılık gelmez. CGS-Ion 2018 [s.5-6] working capital ve
> noncash CA bileşenlerinin asset growth açıklayıcı gücünün büyük
> kısmını üstlendiğini gösterir → G7 yön farkının teorik dayanağı.

## Reported Performance Across Studies

| Paper | Dönem | Evren | Spread (1y size-adj) | t-stat (or sig %) | Notlar |
|---|---|---|---|---|---|
| [[mohanram2005_g_score]] | 1979-1999 | COMPUSTAT BM-Q1 (lowest) | **+21.2%** (High − Low) | sig 1% | [Tablo 4, s.15-16]; n=20,866 |
| [[mohanram2005_g_score]] (large-cap) | aynı | aynı, top size tercile | **+19.8%** | sig 1% | [Tablo 5 Panel A, s.17]; F-Score'un large-cap zayıflığının tersine |
| [[mohanram2005_g_score]] (NASDAQ) | aynı | aynı, NASDAQ-only | **+26.4%** | sig 1% | [Tablo 5 Panel C, s.18]; NYSE/AMEX 12.7%'in 2x |
| [[mohanram2005_g_score]] (hi-tech) | aynı | aynı, Field-Hanka SIC | **+17.8%** | sig 1% | [Tablo 5 Panel D, s.20]; hi-tech high group +5.2% |
| [[mohanram2005_g_score]] (yıl 2) | aynı | aynı | +15.8% | sig 1% | [Tablo 4, s.16] |
| [[mohanram2005_g_score]] (risk-adj regr) | aynı | aynı | coef +0.039 per 1pt G-Score (≈ +3.9% size-adj) | sig 1% | [Tablo 7 Panel A pooled, s.22]; SIZE/LBM/MOM/ACCR/EQ_OFF kontrol |
| [[mohanram2005_g_score]] (annual regr) | aynı | aynı | coef +0.037 per 1pt G-Score | sig 1% | [Tablo 7 Panel B, s.22]; 21 yıllık annual regressions ortalaması, Bernard 1995 autocorrelation düzeltmeli |
| [[li_mohanram2019_quality_value]] (continuous, all-firms) | 1973-2012 | NYSE/AMEX/NASDAQ all | +6.06% (Q5−Q1) | sig 1% | [Tablo 2, s.15-16]; n=98,766; **continuous rank-based 0-1**, all-firms, **FF1997 48-industry** (Mohanram orijinal 2-digit SIC'den farklı) — orijinal +21.2%'den 3x düşük spread (post-publication decay + universe + industry classification revision) |
| [[li_mohanram2019_quality_value]] (G & V/P combined) | aynı | all-firms | **+21.45%** (Q5∩Q5 − Q1∩Q1) | sig 1% | [Tablo 4 Panel B, s.18]; combined approach **en güçlü standalone+combined kombinasyonu** |
| [[li_mohanram2019_quality_value]] (G & NEGPEG combined) | aynı | all-firms | +20.67% | sig 1% | [Tablo 4 Panel B, s.18] |
| [[li_mohanram2019_quality_value]] (3F alpha standalone) | aynı | all-firms | +6.42% annualized | sig 1% | [Tablo 9 Panel A, s.25]; Fama-French 3F kontrolü |
| [[li_mohanram2019_quality_value]] (3F alpha G&V/P) | aynı | all-firms | **+20.27% annualized** | sig 1% | [Tablo 9 Panel B, s.25]; combined alpha en yüksek |
| [[mclean_pontiff_2016_post_publication_decay]] aggregate decay multiplier | (82 anomaly aggregate, 1972-2011) | NYSE+AMEX+NASDAQ all-stocks aggregate | aggregate post-pub decay **%35** (sig 1%); G-Score paper ref list'inde explicit listed değil | (anomaly-equal-weighted aggregate t-stat values [Tablo 2, s.31]) | [Tablo 3, s.32] aggregate decay; G-Score-spesifik decay rakamı paperdan tek-tek çıkmıyor; aggregate uygulanır → decay-adjusted +21.2%×0.65 = **+13.78%** baseline; modern empirik karşılaştırma için Li-Mohanram +6.06% satırı (yukarıda); Tablo 8 limited arbitrage büyük/likit firmalarda decay daha güçlü → G-Score'un Mohanram Tablo 5 large-cap +19.8% sig 1% sonucu post-pub'da kısmen erozyona uğrar |

## Faktör Ailesi İçindeki Yeri

- **F-Score komplemanı** ([[F_Score]]): F-Score high-BM, G-Score low-BM. Birlikte
  value+growth tüm evreni kapsar; orta-BM (BM-Q3) için Li-Mohanram 2019 birleşik
  yaklaşımına dayanır.
- **Risk-factor controls [[mohanram2005_g_score]] [Tablo 7, s.22]:** G_SCORE,
  size, BM, momentum, accrual, equity issuance kontrolünden bağımsız incremental
  information taşır (1 puan G-Score = +3.9% size-adj return; sig 1%).
- **Subsumed by?** Wiki'de doğrudan kanıt yok. FF5 (RMW + CMA) G-Score'un
  profitability + investment alt-bileşenlerini kısmen yakalayabilir ama G-Score
  spesifik R&D/advertising sinyalleri RMW'a dahil değil. Hou-Xue-Zhang 2020
  ingest'iyle replication test edilmeli.

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

> 📝 **Wiki'de mevcut en güçlü NDX-relevant kanıt kaynağı.** Üç dolaylı kanıt:

1. **Large-cap'te güçlü** [[mohanram2005_g_score]] [Tablo 5 Panel A, s.17]: spread
   19.8%, sig 1%. F-Score'un large-cap zayıflığından (t=1.88, p=0.224) farklı.
2. **NASDAQ partition'da güçlü** [Tablo 5 Panel C, s.18]: spread 26.4% (NYSE/AMEX
   12.7%'in 2x).
3. **Hi-tech firmalarda güçlü** [Tablo 5 Panel D, s.20]: spread 17.8%, hi-tech
   high group +5.2% (overall low-BM mean +3.3%'in üstünde) → torpedo identification
   *ve* winner identification her ikisi de hi-tech'te çalışıyor.

**Ancak wiki'de mevcut kanıt 1979-1999 ile sınırlı.** Post-2000 (özellikle FAANG
dönemi 2010-2024) **out-of-sample**. Li-Mohanram 2019 (Tier 1 #12) ingest'iyle
kısmi cevap.

## Decay / Post-Publication Performance

[[mclean_pontiff_2016_post_publication_decay]] [Tablo 3, s.32] 82 anomaly
aggregate **post-pub decay %35 (sig 1%)**, %10 statistical bias (insig).
Paper ref list'inde Mohanram 2005 explicit listed **değil** — G-Score
paper-spesifik decay rakamı paperdan tek-tek çıkmıyor; aggregate
multiplier (×0.65) uygulanır.

**Modern empirik karşılaştırma**: [[li_mohanram2019_quality_value]]
[Tablo 2, s.15-16] — orijinal Mohanram +21.2% (1979-1999, low-BM, binary)
→ modern continuous all-firms (1973-2012) **+6.06%** = ~3.5x düşüş.
McLean-Pontiff aggregate %35 decay + universe genişlemesi + binary→
continuous + industry classification revision (FF1997 48-industry)
karışık etkenler.

> ⚠️ **Asimetrik çift darbe (Cycle 11 kullanıcı kararı 6 vurgusu):**
> Mohanram in-sample large-cap'te **güçlü** ([Tablo 5 Panel A, s.17]
> +19.8% sig 1%) — F-Score'dan farklı. Ancak
> [[mclean_pontiff_2016_post_publication_decay]] [Tablo 8, s.37] post-pub
> decay büyük/likit firmalarda **DAHA güçlü** (Size +1.442, Dollar Vol
> +1.380, Idio Risk -1.420, Divid +1.439, sig 1%). G-Score'un large-cap
> in-sample avantajı post-pub'da kısmi erozyon yaşar — Li-Mohanram modern
> ~3.5x düşüş bunun somut empirik kanıtı. Detay
> [[post_publication_decay]] decay-adjusted spread tablosu — G-Score
> satırı NDX agresif sensitivity ×0.50 = +10.60% (vs aggregate ×0.65 =
> +13.78%).

### Multiple Testing Status (Cycle 12 ek)

[[harvey_liu_zhu_2016_multiple_testing]] çerçevesinde G-Score reported
"sig 1%" (yaklaşık |t| > 2.6):
- **G-Score (low-BM origin, large-cap, NASDAQ partitions):** BHY (3.0)
  yaklaşık sig; Bonferroni (3.78) borderline
- **G-Score continuous all-firms (Li-Mohanram, +6.06%):** sig 1%
  yaklaşık → BHY sig yaklaşık, Bonferroni borderline
- **G & V/P combined (+21.45%, sig 1%):** sig her cutoff yaklaşık → Faz
  3 NDX baseline aday (üç darbe 3/3 yaklaşık)

> 📝 **Dört darbe çerçevesi (Cycle 12 + Cycle 13 sentez):** G-Score'un
> dört darbe sonucu **asimetrik 2-3/4** — in-sample large-cap güçlü,
> post-pub decay agresif, MT borderline, replication paperdan teyit
> (Mohanram ref list'te ama specific HXZ rakamı Internet Appendix'te).
> Combined yaklaşımla (G & V/P, G & NEGPEG) kompanse edilirse 3/4
> mümkün (replication ortogonal Q31). Detay
> [[concepts/post_publication_decay]] dört darbe çerçevesi tablosu;
> [[concepts/anomaly_replication]] aggregate tablosu.

**Cycle 13 ek (HXZ 2020 ingested):**
[[hou_xue_zhang_2020_replicating_anomalies]] reference list'te (line
1567); G-Score için **specific HXZ replication rakamı paper extract'te
yok**. G-Score'un industry-median methodology'si HXZ 2020 NYSE-VW
konvansiyonundan farklı; replication adapte edilmiş olarak
değerlendirilmesi gerekir. Q33 (post-2014 modern replication) ile
JKP 2023 ek ingest G-Score-spesifik kanıtı sağlar.

## Implementation Notes

- **Required data:**
  - Income statement: NI, sales, R&D, advertising, depreciation
  - Cash flow statement: CFO, capex (CAPX)
  - Balance sheet: total assets (t ve t-1)
  - Last 5 years: ROA + sales growth (G4/G5 için varyans)
- **Compustat fields:** NI, OANCF (CFO), AT, XRD (R&D), XAD (advertising), CAPX
  (capex), SALE (sales)
- **Sharadar mapping:** Sharadar Core US Fundamentals'da tüm 8 kalem mevcut.
  R&D/advertising bazı sektörlerde missing → endüstri medyanı problemi (örn.
  finans firmaları R&D = 0). Mohanram pratik çözümü: missing/zero olarak ele
  al (G6/G7/G8 = 0).
- **Annual rebalance:** [[mohanram2005_g_score]] [s.12] fiscal year-end + 4 ay
  (Piotroski'nin 5 ay'ından bir ay daha agresif).
- **Industry-median calculation:**
  - 2-digit SIC code, contemporaneous (aynı yıl)
  - Sadece low-BM evren içinde (yani peer = aynı yıl aynı sektördeki low-BM
    firmalar)
  - **NDX uygulamasında problem:** 100-stock evrende sektör çeşitliliği zayıf,
    median noise'lu — bkz. yumuşak karın altı.

## Bu Faktörün Yumuşak Karnı

- **Sadece low-BM evrende kalibre [s.7]:** F-Score gibi G-Score da universe-
  spesifik. Mid-BM evrene transfer edilemez. Tüm-evren uygulama Li-Mohanram 2019
  combined yaklaşımıyla yapılır (henüz wiki'de yok).
- **Industry-median 2-digit SIC noise riski:** NDX gibi 100-stock evrende
  sektör çeşitliliği zayıf (örn. >%30 firma SIC 73x software'de) → endüstri
  medyanı az gözlemden hesaplanır, noise yüksek. **NDX-uygulaması için sektör
  sınıflandırma yeniden seçilmeli** (bkz. [[meta/open_questions]] Q19).
- **R&D/advertising 0 olabilen firmalar:** retail, utility, finans, real estate
  sektörlerinde R&D ve advertising explicit raporlanmaz veya 0. G6/G7/G8 sinyali
  bu firmalarda meaningful değil → industry-median düzeltmesi *kısmi* çözüm
  (sektör içinde herkes 0 ise median 0, kimse signal vermez).
- **Capex (G7) zayıf sinyal [s.13]:** Yıl 1 anlamlı değil; yıl 2'de anlamlı.
  Yazar [s.14 fn 8]: G7'yi look-ahead bias'tan kaçınmak için saklıyor (kötü
  performans olduğunu post-hoc öğrendik).
- **Advertising (G8) yıl 2'de anlamsız [s.13]:** Sadece kısa-vadeli etki;
  Mohanram açıkça not ediyor.
- **Test dönemi 1979-1999, post-2000 yok:** Modern NDX (FAANG-dominant) için
  out-of-sample.
- **Mispricing yorumu:** Yazar [s.28] explicit olarak risk-tabanlı açıklamayı
  reddediyor; ama Cochrane çerçevesi içinde bu felsefi seçim. Wiki strateji
  tasarımında taraf tutmaz.
- **Equal-weighted binary [s.14 fn 9]:** Optimum değil; continuous + factor-
  weighted alternatif look-ahead bias riski yaratır → modern cross-validation
  önerilir.
- **HMXZ 2020 q5 lens'inde test EDİLMEDİ:**
  [[hou_mo_xue_zhang_2020_security_analysis]] paperı G-Score'u kapsamına
  almamış (F-Score, V/P, Magic Formula, QMJ vb. var ama Mohanram G-Score yok).
  Bu, **G-Score'un q-factor model lens'inde durumu wiki'de hala bilinmiyor**
  anlamına gelir — F-Score'un microcap hariç span edildiği patternin
  G-Score için tekrarlanırlığı doğrulanmış değil. → [[meta/open_questions]] Q25.
- **Forensic katman ihtiyacı + tech firma false positive riski (Cycle 18 ek):**
  G-Score growth firmalar evrendir (low-BM = sales growth high) →
  Beneish M-Score'un **SGI bileşeni yapısal olarak yüksek** çıkar →
  G-Score Q5 long bacak içinde manipulators yanlış sınıflandırma
  riski. Kombine yaklaşım iki sorun yaratır:
  1. **G & M screen-and-rank**: M-Score yüksek olanlar elenirse,
     G-Score Q5'in büyük kısmı evren dışı kalır (tech firma SGI
     yapısal yüksek)
  2. **Q47 yeni**: M-Score 8 bileşeni intangibles-aware değil; tech
     firma false positive yapısal — F bloğu 3 ayak methodology
     (Lev-Sougiannis + Peters-Taylor + Lev-Srivastava) M-Score'a
     entegre edilmesi NDX evren için ön koşul
  - Concept seviyesinde G-Score + forensic filter kombinasyonu
    [[concepts/earnings_quality]] forensic boyut sub-section + Q9
    partial cevap (Cycle 18); akademik combined backtest yok

## İlgili

- [[mohanram2005_g_score]] — origin paper
- [[F_Score]] — value-tarafı muadili (komplemanı)
- [[winner_loser_identification]] — G-Score'un ait olduğu paradigma
- [[contextual_fundamental_analysis]] — industry-median tasarım kararı bu kavramı
  doğrudan örnekler
- [[fundamental_scoring]] — "industry-median level" alt-paradigma
- [[earnings_quality]] — G3 (accruals) bileşeninin kavramsal temeli
- [[HML]] — G-Score HML kısa bacağında (low-BM = growth) winner-loser ayrımı
- [[factor_model]] — G-Score'un asset-pricing model içindeki konumu
- [[li_mohanram2019_quality_value]] — birleşik F+G yaklaşımı + V/P ve PEG ile combined; G-Score continuous-rank revision + FF1997 48-industry sınıflandırma
- [[hou_mo_xue_zhang_2020_security_analysis]] — **G-Score test edilmedi** (kapsam dışı); F-Score, V/P, Magic Formula vb. q5 lens'inde test ediliyor ama G-Score yok → Q25 wiki açık sorusu
- [[comparisons/f_score_vs_g_score]] — head-to-head karşılaştırma sayfası
- [[Magic_Formula]] — alternatif composite (q5 ile tam span)
- [[accruals_anomaly]] — Sloan 1996 anomalisi (G3'ün kavramsal omurgası); F_ACCRUAL ile ortak Sloan paterni
- [[Accruals]] — total accrual standalone factor entity
- [[sloan1996_accruals_anomaly]] — G3'ün **origin paper'ı**
- [[lev_sougiannis_1996_rd_capitalization]] — **G6 (R&D / Assets)
  literatür hattı kökü** (Cycle 15); R&D'nin earnings/value relevance
  empirik kanıtı + R&D capital subsequent return prediction (4.57%
  yıllık RDC-yoğun firmalarda); Mohanram conservatism yorumunun teorik
  dayanağı
- [[peters_taylor_2017_intangible_capital]] — **G6/G7/G8 capital
  category sınıflandırma temeli** (Cycle 16); G6 → Knowledge Capital,
  G7 → Physical Capital, G8 → Organization Capital alt-bileşeni;
  Mohanram industry-median + Peters-Taylor methodology hierarchy
  complementary
- [[concepts/intangibles_adjusted_accounting]] — F bloğu anchor concept;
  G6 + advertising (G8) + capex (G7) intangibles-aware framework
- [[Asset_Growth]] — G7 (Capex/Assets) capex'in asset growth driver'ı olarak
  yapısal bağ; **AMA yön farkı**: G7 long-high-capex pozitif sinyal
  (Mohanram growth-firma yorumu); CGS asset growth long-low (yüksek-growth
  negatif sinyal). [[contextual_fundamental_analysis]] sayfasında somut
  örnek; CGS literature kökü G7'yi motive etmiyor
- [[asset_growth_anomaly]] — yapısal yakın anomaly
- [[M_Score]] — **Cycle 18 ingest tamam (Beneish 1999)**; G-Score
  growth firmalar evrendir → SGI yapısal yüksek → M-Score yapay
  yüksek; G & M combined ek katman (forensic filter) — tech firma
  false positive Q47 yeni
- [[beneish_1999_m_score]] — M-Score origin paper
- [[QMJ]] — **Cycle 19 ingest tamam (Asness 2019)**; QMJ Growth
  dimension Mohanram 2005 explicit cite [s.7] → literatür hattı
  kökü; G-Score growth-tarafı + QMJ Growth dimension paralel ama
  farklı operationalization: G-Score industry-median level binary
  vs QMJ 5-year prior growth in profitability measures z-score; QMJ
  Profitability ACC ↔ G-Score G3 (CFO > NI) Sloan zinciri paralel;
  G & QMJ kombine yaklaşım low-BM evren NDX strategy spec adayı
- [[asness_frazzini_pedersen_2019_qmj]] — QMJ origin paper; Mohanram
  2005 + Sloan 1996 explicit cite [s.7]

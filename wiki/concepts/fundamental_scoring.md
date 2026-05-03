---
type: concept
name: fundamental_scoring
related_papers: [[piotroski2000_f_score]], [[ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]
---

> 📝 **Cycle 38 ek**: Profitability factor ailesi methodology hierarchy genişletme [[factors/Cop]] yeni entity ([[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓); Profitability zinciri 4-paper × 7-yıl methodology hierarchy GP/A (origin Novy-Marx 2013) → RMW Ope (FF15) → QMJ GPOA (Asness 2019 composite) → Cop (Ball-GLN 2016 cash-based standalone); Sloan fixation hypothesis çürütme + Cop subsumes accruals + Profitability zinciri en güçlü modern halka.

> 📝 **Cycle 39 ek**: F-Score/G-Score binary → Stambaugh-Yuan continuous composite evolution [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; **Composite scoring paradigm literature continuity 4-paper × 17-yıl**: F-Score (Piotroski 2000 binary 9-component high-BM) → G-Score (Mohanram 2005 binary industry-median low-BM) → Stambaugh-Yuan MGMT/PERF (continuous composite 11-anomaly 2-cluster) → JKP 13 theme cluster (Bayesian Empirical Bayes); methodology evolution binary → continuous + single-evren → multi-anomaly aggregation + sentiment-aware factor model integration.

# Fundamental Scoring — Mali Tablo Verisinden Komposit Skor Üretimi

## Tanım

Birden fazla finansal tablo değişkenini (ROA, ΔROA, accruals, leverage, growth,
…) tek bir **komposit skor**'da birleştirme yaklaşımı. Skor genellikle:
- **Binary:** her sinyal 0/1 (Piotroski F-Score, Mohanram G-Score)
- **Z-score:** her sinyal standartlaştırılır, toplanır (Beneish M-Score, Altman
  Z-Score)
- **Ranked:** her sinyal yıllık quintile rank'a dönüştürülür, toplanır (örn.
  AQR multi-signal composites)
- **Continuous-weighted:** factor analysis veya regresyon ağırlığıyla weighted
  combination

## Bu wiki için neden temel

**Wiki'nin nihai amacı bir fundamental scoring sistemi tasarlamaktır:**
S&P 500 / Nasdaq 100 evrenlerinde, 10-K/10-Q verileriyle yıllık-frekansta hisse
seçimi. Strateji tasarımı **bilinçli olarak fundamental scoring çerçevesi içinde**
kalır:
- Macro / behavioral / friction theorisini değil empirical FF tradition'unu takip
  eder ([[cochrane2011_discount_rates]] "division of labor")
- Tek-faktör değil komposit skor üzerine kurulur (parsimony + robustness için)

## Tasarım eksenleri

### 1. Sinyal seçimi
- **Profitability:** ROA, ROE, OP, gross margin, accruals
- **Growth:** ΔROA, sales growth, asset growth (Cooper-Gulen-Schill 2008
  perspective: yüksek asset growth = kötü işaret)
- **Efficiency:** asset turnover, inventory turnover, capex/sales
- **Leverage / safety:** debt/assets, current ratio, interest coverage,
  Altman/Ohlson Z-O scores
- **Earnings quality:** [[earnings_quality]] — accrual screen, CFO/NI ratio,
  Beneish M-Score forensic flag
- **Intangibles / R&D:** R&D/sales, R&D/assets (Lev-Sougiannis 1996, Tier 2
  #26 — Nasdaq 100 için kritik)

### 2. Universe konditioning
- **High-BM only:** [[piotroski2000_f_score]] yaklaşımı — F-Score sadece
  value tarafında çalışır
- **Low-BM only:** Mohanram G-Score yaklaşımı (henüz wiki'de yok) — growth
  tarafında ayrı kalibrasyon
- **All-universe:** Beneish M-Score, Altman Z-Score yaklaşımı — sektör/style
  bağımsız
- **Sector-neutral:** her sektör içinde ayrı sıralama; özellikle finansallar /
  utilities / real estate için kritik

### 3. Ağırlık şeması
- **Equal-weighted binary, firm-level threshold:** F-Score
  [[piotroski2000_f_score]] [s.7 fn 2 + s.10] — yazar açıkça optimum olmadığını
  söyler ama "implementation cost" argümanıyla tercih eder. Eşik firm-level
  (örn. "ROA > 0").
- **Equal-weighted binary, industry-median threshold:** G-Score
  [[mohanram2005_g_score]] [s.8] — eşik industry-median (2-digit SIC,
  contemporaneous peer'lar). Sektörel baseline farkını nötrler. **Az-firma'lı
  evrenlerde (NDX gibi) median noise riski.**
- **Equal-weighted ranked:** sürekli ranklara dönüştür, eşit ağırlıkla topla.
  Li-Mohanram 2019 [[li_mohanram2019_quality_value]] [s.12] F-Score ve G-Score'u
  bu yöntemle yeniden inşa eder (cross-sectional rank → [0,1] normalize → toplam).
- **Cross-product (intersection) of two rankings:** İki ayrı sıralamanın **kesişim**
  bölgesini long, **kesişim** bölgesini short. Li-Mohanram quality × value
  yaklaşımı [s.13]. Avantaj: ortogonal sinyal kaynaklarını birleştirir; dezavantaj:
  portföy boyutu küçülür.
- **Factor-weighted:** factor analysis veya OLS ile her sinyale optimum ağırlık
- **Cross-validated weighted:** out-of-sample over-fit'e karşı koruyan
  cross-validation ağırlık tahmini

### 4. Frequency
- **Annual:** F-Score, G-Score (annual fundamentals)
- **Quarterly:** modern uygulamalar (10-Q ile sinyal güncelleme)
- **Yıllık-rebalans bu wiki'nin amacıdır** — F-Score / G-Score doğal seçim

### 5. Reporting lag
- 5 ay (Piotroski 2000 konvansiyonu)
- 60-90 gün (modern PIT data ile mümkün)

## Wiki'de mevcut komposit skorlar

| Skor | Kategori | Origin | Wiki sayfası |
|---|---|---|---|
| F-Score | value (high-BM) | Piotroski 2000 | [[F_Score]] |
| G-Score | growth (low-BM) | Mohanram 2005 | [[G_Score]] |
| F+V/P, F+NEGPEG, G+V/P, G+NEGPEG (combined) | quality × value cross-product | Li-Mohanram 2019 | (entity sayfası açılmadı; bkz. [[li_mohanram2019_quality_value]] + [[comparisons/f_score_vs_g_score]]) |
| **M-Score** | **forensic detection (filter, signal değil)** | [[beneish_1999_m_score]] **(Cycle 18)** | [[M_Score]] |
| **QMJ** | **all-cap quality (signal; 4 dimension z-score composite)** | [[asness_frazzini_pedersen_2019_qmj]] **(Cycle 19)** | [[QMJ]] |
| **QARP** | **combined quality + value (continuous quality × n − P/B)** | [[asness_frazzini_pedersen_2019_qmj]] Section 7 **(Cycle 19)** | (entity yok; bkz. [[concepts/value_premium]] 4. yorum boyutu) |
| (sonra) Z-Score | distress | Altman 1968 | _(boş)_ (Tier 2) |
| (sonra) O-Score | distress | Ohlson 1980 | _(boş)_ (Tier 2) |
| (sonra) Magic Formula | EBIT/EV + ROIC | Greenblatt 2006 | _(boş)_ (Tier 3 kitap) |

## Strateji tasarımına spesifik implikasyon

Faz 3 strateji tasarımı **fundamental scoring sistem inşa edecektir**. Tasarım
sorularının çoğu yukarıdaki 5 eksendeki seçimlere indirgenir:

1. **Hangi sinyaller?** — Wiki Tier 1 ingest'leri sonunda evidence-based seçim
2. **Hangi evrene uygulanacak?** — S&P 500 ile Nasdaq 100'ün **ayrı** komposit
   skoru olabilir (value-tilt S&P; growth-tilt Nasdaq)
3. **Hangi ağırlık şeması?** — Bu wiki'nin "factor analysis ile evren-özel
   ağırlık" yaklaşımı **ön planda olacak** ama overfitting riski karşı tedbir
   gerek
4. **Frequency:** **annual** — bu wiki'nin temel kabulü
5. **Reporting lag:** 60-90 gün PIT data önerilir; 5-ay konservatif

## İlgili paperlar (ingested)

- [[piotroski2000_f_score]] — fundamental scoring paradigmasının prototypal
  örneği; binary equal-weighted yaklaşımının güçlü ve zayıf yanları
- [[mohanram2005_g_score]] — paralel growth-tarafı; **industry-median level**
  alt-paradigmasının kanıt kaynağı; large-cap'te güçlü (S&P 500 / NDX için
  pozitif sinyal)
- [[li_mohanram2019_quality_value]] — **continuous rank-based** revision +
  **quality × value cross-product** alt-paradigma; F+G+V/P+PEG sentezi
- [[comparisons/f_score_vs_g_score]] — F ve G arasında head-to-head karşılaştırma
  (replikasyon farkları + context-aware kullanım)
- [[novy_marx_2013_gross_profitability]] — **Cycle 23**; standalone
  GP/A signal (single-variable; F-Score 9-component / G-Score 8-component
  binary composite paradigmasından farklı); Profitability zinciri
  origin (4 halka: GP/A → RMW Ope → QMJ GPOA → Cop); Fortune 500 GP/V
  rank-based combined paterni Li-Mohanram F&V/P + G&V/P binary
  intersection paterninin **continuous rank product paraleli** —
  QARP framework empirik altyapı; Sloan zinciri (mispricing/accruals)
  paralel **iki paralel quality zinciri** dokümante.

## İlgili paperlar (henüz ingest edilmedi)

- Li-Mohanram (2019) — F-Score + G-Score combined (Tier 1 #12)
- Beneish (1999) "M-Score" — forensic-side composite (Tier 1 #15)
- Ou-Penman (1989), Holthausen-Larcker (1992) — earlier fundamental scoring
  research (Piotroski tarafından atfen [[piotroski2000_f_score]] [s.5-6])
- AQR / Greenblatt / Gray-Vogel — practitioner composite implementations (Tier 3)

## İlgili kavramlar

- [[earnings_quality]] — komposit skorun en kritik alt-boyutu
- [[factor_zoo]] — komposit skor "tek faktör"e indirgemenin bir yolu, factor
  zoo problemine cevap
- [[factor_model]] — komposit skor'un asset-pricing model içindeki konumu
- [[discount_rates]] — komposit skorun yakaladığı şey: cross-sectional
  discount rate spread

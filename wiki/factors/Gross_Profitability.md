---
type: factor
name: Gross_Profitability
alias: GP/A
category: profitability
direction: long_high
data_lag_required: "≥6 months after fiscal year end (FF June rebalance konvansiyonu)"
rebalance_frequency: annual
universe_tested: ["NYSE+Amex+Nasdaq ex-financials 1963-2010", "19 international markets 1990-2009", "Fortune 500 1963-2010"]
cycle_38_note: "Profitability zinciri methodology hierarchy 4. halka [[factors/Cop]] yeni entity Cycle 38 ✓ ([[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]); 4-paper × 7-yıl hierarchy: GP/A (origin Novy-Marx 2013 BU FACTOR) → RMW Ope (FF15) → QMJ GPOA (Asness 2019 composite) → Cop (Ball-GLN 2016 cash-based standalone); Ball-GLN [s.10] explicit 'Sharpe ratio for cash-based operating profitability is also higher than the Sharpe ratios for gross profitability and net income' GP/A → Cop methodology evrim"
cycle_39_note: "Stambaugh-Yuan 11 anomaly Cluster 2 (PERF) içinde gross profitability dahil [[factors/PERF]] Cycle 39 ✓ ([[papers/stambaugh_yuan_2017_mispricing_factors]]); composite mispricing P2 5-anomaly avg ranking GP/A bileşeni; GP/A tek-anomaly Profitability zinciri 1. halka + UMO2 composite mispricing Cluster 2 üyesi complementary methodology aile (Profitability zinciri 4-paper × 7-yıl + Composite mispricing scoring 4-paper × 17-yıl iki paralel)"
---

# Gross Profitability — GP/A (Novy-Marx 2013)

## Tanım (matematiksel)

**Gross Profits-to-Assets (GP/A)**:

```
GP/A = (REVT − COGS) / AT
```

- **REVT** (Compustat): total revenue
- **COGS** (Compustat): cost of goods sold (direct labor + materials
  + production-related expenses; details [[papers/novy_marx_2013_gross_profitability]] [s.6 fn 2])
- **AT** (Compustat): total assets

**Methodology işareti**: absolute level (industry-adjusted variant Tablo
1 Panel B daha güçlü; Fama-French 49-industry demean)

**Kritik tasarım kararı** ([[papers/novy_marx_2013_gross_profitability]]
[s.5-7]): "Cleanest accounting measure of true economic profitability";
gross profits R&D, advertising, organizational capital, SG&A, capex,
interest **çıkarılmamış** — bu kalemler tech firmalarda "expense olarak
işlenmiş gelecek productive expenditures" → earnings deflated, gross
profits ARÎ. Numerator **intangibles-aware avantajı** (denominator
total assets traditional).

## Origin

- **İlk paper**: [[papers/novy_marx_2013_gross_profitability]]
- **Yazar**: Robert Novy-Marx (Simon Graduate School of Business,
  University of Rochester)
- **Sample**: 1963-07 / 2010-12 (47 yıl, ex-financials)
- **Methodology**: NYSE breakpoints + value-weighted + annual June
  rebalance

## Profitability zinciri (origin attribution)

Wiki için yapısal kazanım: **iki paralel quality zinciri** dokümante
(Sloan zinciri paralel):

| Halka | Paper | Component | Yıl | Methodology evrim |
|-------|-------|-----------|-----|-------------------|
| **1 (origin)** | [[papers/novy_marx_2013_gross_profitability]] | GP/A = (REVT − COGS) / AT | 2013 | Standalone signal; numerator intangibles-aware (R&D/SG&A/interest çıkarılmamış); denominator AT |
| 2 | [[papers/famafrench2015_five_factor]] | RMW Ope = (REVT − COGS − SG&A − interest) / BE | 2015 | Factor portfolio; numerator daha düşük (operating); denominator BE |
| 3 | [[papers/asness_frazzini_pedersen_2019_qmj]] | QMJ Profitability dimension GPOA | 2019 | Composite z-score 6 measure'dan biri (GPOA + ROE + ROA + CFOA + GMAR + ACC) |
| 4 | [[papers/hou_xue_zhang_2020_replicating_anomalies]] (HMXZ Tablo 5) | Cop = (gross profits − SG&A + R&D − ΔWC − capex...) / AT | 2020 | Cash-aware evrim; Ball-GLN 2016 origin; q-factor alpha 0.69%/ay sig (4/4 hayatta kalan) |

**Sloan zinciri paralel** (mispricing/accruals):
- Sloan 1996 → Piotroski 2000 F_ACCRUAL → Mohanram 2005 G3 → QMJ
  Profitability ACC component

**Iki zincir QMJ 4-dimension'da birleşiyor**: QMJ Profitability
dimension 6 measure içinde GPOA (Profitability zinciri) + ACC (Sloan
zinciri) yan yana — wiki için **literature continuity** dokümante.

## Reported Performance Across Studies

| Paper | Dönem | Evren | Mean (ay) | t-stat | Notlar |
|---|---|---|---|---|---|
| [[novy_marx_2013_gross_profitability]] univariate Q5−Q1 | 1963-07 / 2010-12 | NYSE+Amex+Nasdaq ex-fin VW | 0.31% | 2.49 | [Tablo 2]; modest raw spread |
| [[novy_marx_2013_gross_profitability]] univariate FF3 alpha | aynı | aynı | 0.52% | 4.49 | [Tablo 2]; HML loading büyük negatif (growth strategy) |
| [[novy_marx_2013_gross_profitability]] **size Q5 (largest)** | 1963-2010 | aynı, large-cap | 0.26% | 1.88 | [Tablo 4]; FF3 alpha small-cap kadar güçlü; **profitability premium size-invariant** |
| [[novy_marx_2013_gross_profitability]] **Fortune 500 combined GP/V** | 1963-2010 | top 500 non-fin | **0.62%** | (sig) | [Tablo 7]; **annual Sharpe 0.74** ⭐ wiki S&P 500 direct anchor; rank-based long 150 + short 150 |
| [[novy_marx_2013_gross_profitability]] PMU\|BM (controlling B/M) | 1963-2010 | NYSE+Amex+Nasdaq ex-fin | 0.48% | 5.35 | [Tablo 8]; conditional factor B/M kontrollü |
| [[novy_marx_2013_gross_profitability]] international | 1990-2009 | 19 developed markets ex-fin | (sig + value spread'den büyük) | — | [Tablo 5]; profitability premium global |

## Faktör Ailesi İçindeki Yeri

### Korelasyon ve subsumption

- **GP/A ↔ B/M**: Spearman correlation **−0.18** (sig)
  ([[novy_marx_2013_gross_profitability]] [s.10]); GP/A "the other
  side of value" — growth strategy ama value premium ile tamamlayıcı
- **GP/A long-short ↔ HML long-short return correlation**: **−0.57**
  (sample 1963-2010); 50/50 mix Sharpe 0.85
- **HML standalone HML|GP + PMU|BM tarafından span ediliyor**
  ([[novy_marx_2013_gross_profitability]] [Tablo 8 spec 7-8]); HML
  loading 1.04 on HML|GP + −0.18 on PMU|BM; alpha insig
- **GP/A subsumes** earnings-to-book, free cash flow-to-book, EBITDA-
  to-assets, SG&A-to-assets, asset turnover, gross margins (paper
  [Tablo 1] + Appendix A.2)
- **GP/A ↔ accruals/R&D paralel**: paper Appendix A.3 GP/A predictive
  power persists controlling for accruals (Sloan 1996) ve R&D (Chan-
  Lakonishok-Sougiannis 2001) — bağımsız mekanizma

### Profitability zinciri içindeki konum

| Measure | Numerator | Denominator | Avantaj | Dezavantaj |
|---------|-----------|-------------|---------|------------|
| **GP/A** (Novy-Marx) | REVT − COGS | AT | Numerator intangibles-aware (R&D ARÎ); denominator stabil | Denominator total assets intangibles düzeltilmemiş |
| RMW Ope (FF15) | REVT − COGS − SG&A − interest | BE | Factor portfolio standart | SG&A çıkarılmış (R&D content); leverage-sensitive (BE denominator) |
| QMJ GPOA (Asness) | gross profits | assets | Composite z-score; 22 measure entegre | Standalone vs composite; size-controlled inşa |
| Cop (HMXZ/Ball-GLN) | gross profits − SG&A + R&D − ΔWC − capex | AT | Cash-aware (working capital + capex çıkarılmış); 4/4 hayatta kalan | Methodology karmaşık; Ball-GLN 2016 wiki'de yok |

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

⭐ **Direct kanıt** ([[novy_marx_2013_gross_profitability]] Section 3.2 +
Tablo 7): **Fortune 500 strategy** (top 500 largest non-financial
stocks):
- Combined GP/V rank-based long-short: 0.62%/ay (~7.4%/yıl)
- **Annual Sharpe 0.74** (market 0.34'ün 2x'ı)
- Long-side alone market-hedged: 18bps/ay (t=3.46) sig
- Turnover 1/3 her bacakta her yıl (low cost, annual rebalance)

**Wiki S&P 500 strategy spec için birebir empirik altyapı.**
[[papers/li_mohanram2019_quality_value]] F&V/P + G&V/P combined
paterninin **Novy-Marx GP/V Fortune 500 paraleli** — QARP framework
empirik anchor.

NDX kanıtı paper kapsamı dışı (size partition var ama tech-spesifik
yok); NDX-spesifik kalibrasyon Faz 2 modern data ([[meta/data_gaps]]
Q56 intangibles-aware GP/A).

## Decay / Post-Publication Performance + Multiple Testing Status

[[mclean_pontiff_2016_post_publication_decay]] aggregate %35 post-pub
decay multiplier proxy uygulanır → GP/A FF3 alpha 0.52%/ay × 0.65 ≈
0.34%/ay decay-adjusted.

[[harvey_liu_zhu_2016_multiple_testing]] HLZ recommended cutoff
`|t| > 3.0` BHY: GP/A FF3 alpha t=4.49 ✅ comfortable sig (Bonferroni
3.78 cutoff'unu da geçer).

[[hou_xue_zhang_2020_replicating_anomalies]] HXZ NYSE-VW replication
methodology paralel (Novy-Marx zaten NYSE-VW kullanıyor); GP/A
HXZ 2020 sample'da explicit listed; Cop superior (cash-aware evrim) →
GP/A standalone 3-4/4 hayatta kalan, Cop 4/4.

[[concepts/post_publication_decay]] dört darbe çerçevesi sentez tablosu
**Profitability zinciri 4 satır**:
- GP/A (Novy-Marx 2013): 3-4/4
- RMW Ope (FF15): 1/4 (HXZ 2020 q-factor alpha 0.04% t=0.42 INSIG)
- QMJ Profitability (Asness 2019): 3-4/4 (q5 captures asterisk)
- Cop (HMXZ Tablo 5): **4/4** ⭐

## Implementation Notes

- **Required Compustat data**: REVT, COGS, AT (3 fields, basic)
- **Annual reporting frequency adequate**; quarterly variant
  (REVTQ, COGSQ, ATQ) Appendix A.4 daha güçlü monthly returns ama
  turnover yüksek
- **Universe**: ex-financials (1-digit SIC 6 hariç) standart
- **Rebalance**: NYSE breakpoints + VW + annual June rebalance
- **Industry adjustment**: Fama-French 49-industry portfolios
  ([[novy_marx_2013_gross_profitability]] [Tablo 1 Panel B]); modern
  GICS mapping Q38 paralel

## Bu Faktörün Yumuşak Karnı

- **Denominator total assets intangibles düzeltmesi yapmıyor** —
  numerator gross profits R&D'den ARÎ ama denominator total assets
  intangibles capital'i içermiyor; F bloğu
  ([[concepts/intangibles_adjusted_accounting]]) Peters-Taylor total
  intangible capital + Lev-Sougiannis perpetual inventory ile
  güçlendirilebilir (Q56)
- **Sample sonu Dec 2010** — post-2010 (FAANG era + COVID + AI)
  out-of-sample; modern data Chen-Zimmermann + JKP 2023 ek ingest
- **Cop (cash-based evrim) superior**: HXZ 2020 q-factor lens'inde
  Cop 4/4 hayatta kalan + GP/A 3-4/4; Cop methodology Faz 3 spec için
  preferred ama Ball-GLN 2016 (Tier 1 #9) wiki'de paper sayfası yok
- **Annual vs quarterly trade-off**: Novy-Marx Appendix A.4 quarterly
  daha güçlü ama turnover yüksek; wiki annual default ile uyumlu
  ama sensitivity Q57

## İlgili

### Profitability zinciri (origin attribution dual pattern)
- [[papers/novy_marx_2013_gross_profitability]] — origin (1. halka)
- [[factors/RMW]] — Profitability zinciri 2. halka (FF15 Ope methodology)
- [[factors/QMJ]] — Profitability zinciri 3. halka (4-dimension composite
  GPOA bileşeni)
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] — Cop (cash-aware
  evrim, 4. halka)

### Sloan zinciri paralel (iki paralel quality zinciri)
- [[factors/Accruals]] — Sloan zinciri origin
- [[factors/F_Score]] — F_ACCRUAL bileşeni
- [[factors/G_Score]] — G3 bileşeni

### Combined yaklaşımlar
- [[papers/li_mohanram2019_quality_value]] — F&V/P + G&V/P combined
  binary intersection paterni; Novy-Marx GP/V Fortune 500 rank-based
  combined paraleli (QARP framework)
- [[concepts/fundamental_scoring]] — composite scoring paradigm
- [[concepts/winner_loser_identification]] — value premium uzun bacağı
  içinde profitability refinement

### Concept'ler
- [[concepts/post_publication_decay]] — dört darbe sentez Profitability
  zinciri 4 satır
- [[concepts/factor_zoo]] — RMW + GP/A + GPOA + Cop ailesi factor
  proliferation/redundancy
- [[concepts/intangibles_adjusted_accounting]] — F bloğu hub; Q56
  intangibles-aware GP/A revize

### Cycle 25 cross-link (Eisfeldt-Papanikolaou)
- [[papers/eisfeldt_papanikolaou_2013_organization_capital]] — Novy-Marx
  [Section 4] organizational capital based strategy (Eisfeldt-Papanikolaou
  2011 cite) Novy-Marx 3-factor "açıklıyor" iddiası; Eisfeldt-Papanikolaou
  direct factor portfolio Carhart 4F α=3.9% sig 1% → **Novy-Marx claim
  partial reject** (Q58 partial-stronger). High OC firms gross
  profitability profile yapısal paralel.
- [[factors/Organization_Capital]] — Profitability ailesi yakın komşu
  (yapısal paralel, methodology farkı: GP/A flow-based vs OC stock-based
  perpetual inventory)

### Cycle 26 cross-link (FGX 2020 — Q55 fully-answered)
- [[papers/feng_giglio_xiu_2020_factor_zoo]] — **Q55 fully-answered**
  (Cycle 26): Profitability ailesi DS LASSO 150-factor library lens
  validation. **RMW + ROE + QMJ DS-sig** (Tablo 1, since-2012 factors);
  **GP/A 150 library içinde explicit listed teyit edilemedi** (Tablo
  4 ham liste paperdan tek-tek kontrol edilmedi) ama Profitability
  ailesi genel sig dolaylı validation; Cop FGX library'de explicit
  yok ama HXZ q-factor 4/4 paralel kanıt. **v0_draft Profitability
  seçimi DOĞRULANDI** (revize gerekmez); RMW Ope iki paralel bulgu
  (HXZ q-factor INSIG + FGX DS-sig methodology farkı dokümante;
  factors/RMW sayfasında detay). Q64 yeni: F bloğu intangibles
  factor'lerin FGX framework'üne entegrasyonu eksik.

### Methodology
- [[methodology/backtest_spec]] §5.1 4/4 + §5.2 baseline composite
  + §7 Composite scoring + §8 Origin attribution Profitability zinciri

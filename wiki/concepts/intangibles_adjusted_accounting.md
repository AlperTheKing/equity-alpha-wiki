---
type: concept
name: intangibles_adjusted_accounting
related_papers: [[lev_sougiannis_1996_rd_capitalization]], [[peters_taylor_2017_intangible_capital]], [[lev_srivastava_2020_value_failure]], [[hou_xue_zhang_2020_replicating_anomalies]], [[mohanram2005_g_score]], [[cooper_gulen_ion2018_asset_growth_factor_models]]
---

# Intangibles-Adjusted Accounting — F bloğu Anchor Concept

> 📝 **F bloğu (intangibles) anchor concept — KAPANDI Cycle 17**.
> Cycle 15'te [[lev_sougiannis_1996_rd_capitalization]] ingest'iyle
> açıldı; **Cycle 16 Peters-Taylor 2017 total intangible capital
> generalization** (R&D + organization + external);
> **Cycle 17 Lev-Srivastava 2020 post-2010 value-spesifik application
> (KAPANIŞ)**: F bloğu **3-katmanlı yapısal hierarchy tamamlandı**.
> NDX strateji yapısal foundation **3 ayak hazır**; Q1 fully-answered
> kanıt anchor.

## Tanım

Geleneksel GAAP, R&D + advertising + organization capital + brand
value gibi intangibles'i **financial statement'ta expense** eder
(FAS No. 2, 1974); ekonomik gerçekte bunlar **ileride benefit
yaratan asset'ler** (capex paralel). Intangibles-adjusted accounting,
bu intangibles'i **capitalize** ederek adjusted earnings + adjusted
book equity üretir.

### Methodology hierarchy — F bloğu 3-katmanlı omurga (KAPANDI Cycle 17)

| Katman | Capital scope | Methodology focus | Origin paper | Ingest cycle |
|---|---|---|---|---|
| **1. R&D-only capitalization** | Knowledge capital (R&D perpetual inv) | Industry-spesifik amortization (6 sektör SIC; Pharma 9 yıl → Sci Inst 5 yıl); R&D capital → 4.57% subseq return implication | [[lev_sougiannis_1996_rd_capitalization]] | Cycle 15 |
| **2. Total intangible capital** | Knowledge + Organization (SG&A 30%) + External (`intan`) | q^tot proxy V/(K^phy + K^int); BEA δ rates; perpetual inventory; ρ² +21% | [[peters_taylor_2017_intangible_capital]] | Cycle 16 |
| **3. Post-2010 value-spesifik application** | Adjusted BV = reported BV + R&D capital + SG&A intangibles | 1989'dan beri value faltering decomposition; intangibles bias + mean reversion slowdown; 50% largest stocks focus | [[lev_srivastava_2020_value_failure]] | **Cycle 17 (KAPANIŞ)** |

**Yazar continuity**: Baruch Lev katman 1 (Lev-Sougiannis 1996) +
katman 3 (Lev-Srivastava 2020) — 24 yıl sonraki güncelleme; aynı
methodology hub origin author.

**Lev-Sougiannis 1996 [Eq. 7-8, s.122-123]:**

```
X^c_it = X^a_it + RD_it - RA_it       # Adjusted earnings
RDC_it = Σ_{k=0}^{N} RD_{i,t-k} × (1 - Σ_{j=0}^{k} δ_j)   # R&D capital
BV^c_it = BV^a_it + RDC_it           # Adjusted book equity
```

Burada `δ_k` = industry-spesifik R&D amortization rates (Lev-Sougiannis
[Tablo 3, s.121] 6 sektör için, 1975-1990 sample).

**Peters-Taylor 2017 generalization [Eq. 9, 11, s.12, 14-16]:**

```
q^tot_it = V_it / (K^phy_it + K^int_it)
K^int_it = G_it (knowledge) + O_it (organization) + intan_it (external)

G_it = (1 - δ_R&D) × G_{i,t-1} + R&D_it       # Knowledge cap (perp inv)
O_it = (1 - δ_SG&A) × O_{i,t-1} + θ × SG&A_it  # Organization cap (perp inv)
```

Burada:
- **δ_R&D = BEA industry-specific** (Li 2012; pharma 10% → computers 40%; default %15)
- **δ_SG&A = 20%** (industry-bağımsız default)
- **θ = 30%** (SG&A allocation, Hulten-Hao 2008 + Eisfeldt-Papanikolaou 2014)
- **`intan`** = Compustat balance sheet (Goodwill + Other Intangibles)

Lev-Sougiannis methodology'sinin **strict generalization**: R&D
perpetual inventory aynı yapıda + 2 yeni component (organization +
external).

## Empirik kanıt — Lev-Sougiannis 1996 [s.123, 126, 132]

### Adjustments büyüklüğü

| Metric | All firms average | Range |
|---|---|---|
| Earnings understatement (R&D expensing) | **20.55%** | 9.7% (Other) — 26.8% (Electrical) |
| Book value understatement (R&D capital missing) | **22.2%** | 12.3% (Other) — 24.6% (Computer Hardware + Scientific Instruments) |

> 📝 Wiki için: Bu rakamlar **NDX evren içeren tech-heavy firmalarda
> geleneksel HML/Bm + Sloan accruals'in yapısal bias büyüklüğü**.
> 22.2% book equity yapay düşük → B/M yapay yüksek → growth firma
> "value" gibi gözükebilir.

### Industry-spesifik R&D useful life

[[lev_sougiannis_1996_rd_capitalization]] [Tablo 3, s.121]:

| Endüstri (SIC) | Useful life | δ_0 | Annual IRR |
|---|---|---|---|
| **Chemicals & Pharmaceutics (28)** | 9 yıl (en uzun) | 0.082 | 28% |
| Machinery & Computer Hardware (35) | ~7 yıl | 0.106 | 15% |
| Electrical & Electronics (36) | ~8 yıl | 0.114 | 22% |
| Transportation Vehicles (37) | ~7 yıl | 0.072 | 19% |
| **Scientific Instruments (38)** | 5 yıl (en kısa) | 0.135 | 20% |
| Other R&D Industries | ~7 yıl | 0.110 | 20% |

**Mansfield-Levin patent appropriability hierarchy ile uyumlu:**
patents pharma+drugs'da en effektif → R&D life uzun; instruments+motor
vehicles'da düşük → R&D life kısa.

### R&D capital → subsequent return prediction (KRİTİK)

[[lev_sougiannis_1996_rd_capitalization]] [Tablo 5, s.132] Fama-French
1992 framework + RDC/M:

- **Total sample:** RDC/M coefficient 0.0015 (t=3.10) sig 1%
- **Upper quartile RDC firms:** RDC/M coefficient **0.0114 (t=3.88)**
  sig 1% — total sample'ın **8x katı**
- **Annual return implication: 4.57%** (RDC-yoğun firmalarda)

**Önemli yan bulgu:** Upper-quartile RDC firms'da **B/M coefficient
sig kaybı** — RDC/M B/M'in açıklayıcı gücünü absorb ediyor; **R&D-
intensive firms'da B/M yapay sinyal**.

### Mispricing vs extra-market risk yorumu açık

Paper [s.134] iki alternative hipotezi disentangle etmiyor:
- **Hipotez A:** Systematic mispricing of R&D-intensive firms
  (underreaction)
- **Hipotez B:** Extra-market risk factor associated with R&D capital
  (equilibrium returns)

HXZ 2020 [s.28] R&D-to-market (Rdm) q-factor alpha sig 4/4 hayatta
sonucu **Hipotez B'ye eğilimli** (risk premium exposure). Wiki taraf
tutmaz — Cochrane mathematical equivalence.

## Peters-Taylor 2017 generalization — total intangible capital

> 📝 **Cycle 16 ingest sonrası bu bölüm açıldı.** Lev-Sougiannis
> R&D-only methodology'sini total intangible capital'a genişletir;
> NDX yapısal foundation 2. ayağı.

### Total q proxy [Peters-Taylor Eq. 9, s.12]

```
q^tot_it = V_it / (K^phy_it + K^int_it)
```

Standard q (V/PP&E) **misspecified** (Peters-Taylor [Prediction 4]:
downward-biased q-slope, lower R²); total q **all 5 investment measure'da
üstün** [Tablo 2, s.18-19].

### Empirik bulgular [Peters-Taylor Tablo 2-3, Section 4]

| Metric | Standard regression | Total q regression | Δ |
|---|---|---|---|
| R² i^phy ~ q | 23.3% (CAPX/PPE ~ V/PPE) | 20.9% (i^phy ~ q^tot) | -2.4 pp |
| R² i^int ~ q^tot | — | **27.9%** | yeni |
| R² i^tot ~ q^tot | — | **32.7%** | yeni |
| τ² (theory R²) | 0.372 | 0.423 | +14% |
| ρ² (q proxy quality) | 0.492 | 0.597 | **+21%** |

**Macro-level dramatik fark:** Standard regression R² = 4%; intangibles
dahil R² = **61%** [Section 6].

**Adjustment costs:** φ_int ≈ 2 × φ_phy (intangibles slow-adjusting).

**Sürpriz bulgu** [Section 5, Tablo 4]: Q theory **daha iyi fits**
intangibles-yoğun firms/years/industries — intangible quartile 1→4'te
i^tot R² **23% → 47%** monotonic artar.

### Lev-Sougiannis ↔ Peters-Taylor karşılaştırma

| Boyut | Lev-Sougiannis 1996 | Peters-Taylor 2017 |
|---|---|---|
| Capital scope | R&D-only (knowledge) | R&D + organization + external |
| R&D δ rate methodology | Industry-spesifik (6 sektör SIC, 4-stage Almon) | BEA industry-specific (Li 2012) |
| Pre-1996 vs post-1996 | Pre-1996 (sample 1975-91) | Post-1996 (sample 1975-2011) |
| Organization capital | Yok | SG&A × 30% perpetual inv |
| External intangibles (Goodwill, Other) | Yok | `intan` balance sheet |
| Cross-section returns test | ✅ [Tablo 5] RDC/M sig | ❌ Q theory test (return prediction yok) |
| Methodology hub for | F bloğu #1 origin | F bloğu #2 generalization |

**Wiki recommendation Faz 3 NDX strategy spec için:**
- **Knowledge capital** Peters-Taylor methodology (BEA modern rates) +
  Lev-Sougiannis cross-validation (1975-1990 industry mapping)
- **Organization capital** Peters-Taylor θ=30% baseline; %20-50
  sensitivity (Q40)
- **External intangibles** Peters-Taylor `intan` (Goodwill dahil; Goodwill
  hariç secondary spec)
- **q proxy default**: q^tot (V / (K^phy + K^int)); standard V/PP&E reject

## Lev-Srivastava 2020 generalization — post-2010 value-spesifik application

> 📝 **Cycle 17 ingest sonrası bu bölüm açıldı.** Lev-Sougiannis +
> Peters-Taylor methodology'sinin direct application'ı value strategy
> post-2010 collapse açıklamasında; F bloğu **kapanış paper**.

### Adjusted book value methodology [Lev-Srivastava Section 5-6]

```
Adjusted BV = reported BV + R&D capital stock + SG&A intangibles capital - amortizations
```

- **R&D capital stock** = perpetual inventory of R&D — Lev-Sougiannis
  1996 [Eq. 8] paralel
- **SG&A intangibles part** — Enache-Srivastava 2018 + Peters-Taylor
  2017 θ paralel (organization capital allocation)
- **Adjusted earnings** [Section 6]: "adding back to earnings the annual
  R&D expense and the part of SG&A related to intangibles, and
  subtracting from earnings the annual amortization of the R&D and
  SG&A capitals"

### Ana bulgular — value strategy decomposition [Lev-Srivastava]

**Decade-by-decade returns** [Section 3, Figure 1]:

| Decade | Conventional | Adjusted | Adjusted advantage |
|---|---|---|---|
| 1970s | $2.02 (+102%) | benzer | minimal (low intangibles) |
| 1980s | $1.75 (+75%) | **$2.86** | +68% |
| 1990s | $0.90 (-10%) | **~$2.00** ("doubled") | dramatic |
| 2000-2006 | brief resurgence | "substantially higher" | substantial |
| **2007-2018** | **negative** | "**reasonably positive**" | dramatic |

**Headline**: 39 yılın **34'ünde** adjusted strategy conventional'ı
geçer; 1989'dan beri vanilla HML faltering, 2007 financial crisis
sonrası derinleşmesi.

### Iki mekanizma post-2007 [Lev-Srivastava Section 4-9]

1. **Accounting deficiencies (intangibles expensing)**: 1980'lerden
   itibaren intangibles proliferation; book value mismeasurement;
   adjusted methodology dramatic effect (39/34)

2. **Mean reversion slowdown post-2007** [Section 8, 3 measure]:
   - Rank correlation glamour 45-47% → 60% (large stocks)
   - Length of stay value 2.5 → 3.3 yıl, glamour 3.5 → 4.5 yıl
   - 10%+ upticks/downticks 22%/18% → 10%/10%

### Macro mekanizma post-2007 [Section 9-10]

- **Value firms** (banking, retail, insurance, wholesale, utilities =
  50-60% large value):
  - Bank lending contraction → can't finance R&D/IT/acquisitions
  - **<1% issued stock annually** (2007-2018)
  - Median ROE + RNOA collapse (worst since 1970)
  - Internal funds **negative average**
- **Glamour firms** (software, pharma, electronics):
  - Scalable intangibles + first-mover + network effects
  - **2007-2018 highest profitability since 1970**
  - "Average large glamour company invests close to $1B/year in R&D"

### Logit escape regression [Lev-Srivastava Table 1, s.25]

Sample 2008-2017 large value firms; escape from low-MB:

| Variable | Coefficient | Sig |
|---|---|---|
| Intangibles to Assets | **1.664** | <.01 |
| Capex (net of dep) to Assets | **4.686** | <.01 |
| Sales growth | sig | <.01 |
| Debt to Assets | sig | <.01 |
| Loss | -0.485 | <.01 |
| Acquisitions, industry change, ROE | — | insig |

**Yorum**: Internal investments + debt-funded financing → escape;
acquisitions + industry change → ineffective.

### Q1 fully-answered (S&P 500 value post-2000) — Lev-Srivastava anchor

**Wiki priori soru**: S&P 500 evreninde value (P/B, P/E) faktörünün
post-2000 performansı nedir?

**Lev-Srivastava cevabı** [s.16 footnote 13 + Section 1-12]:
- 50% largest stocks focus (top 1500 of CRSP all-stocks; S&P 500 ≈ top
  500 ⊂ subset; **adequate proxy**)
- Decade-by-decade vanilla HML returns 1970s +102% → 2010s NEGATIVE
- **1989'dan beri faltering** (post-2007 collapse "swan song" değil,
  derinleşme)
- Iki mekanizma decomposition (intangibles + macro)
- Adjusted methodology dramatic effect (39/34 yıl)

**Caveat**: 50% largest of CRSP all-stocks ≈ top 1500; S&P 500 = top
500 (subset); paper "top 1500" sample S&P 500'ün **superset proxy'si**,
exact S&P 500 değil. Q1 fully-answered "subset caveat" ile.

## HXZ 2020 R&D-to-market dört darbe 4/4 — methodology temeli

[[hou_xue_zhang_2020_replicating_anomalies]] [s.28] R&D-to-market
(Rdm) factor:
- Annual sorts: klasik 0.68% (t=2.58); q-factor alpha 0.7% (t=2.89) sig
- Monthly sorts (1m/6m/12m): klasik 1.19%/0.83%/0.83%; q-factor alpha
  1.47%/0.97%/0.8% (t=2.97/2.73/2.8) **sig**
- **Dört darbeden 4/4 hayatta** ([[concepts/post_publication_decay]]
  sentez tablosu) — wiki için NDX-relevant kritik kanıt

**Methodology temeli Lev-Sougiannis amortization patterns** —
HXZ 2020 R&D-to-market'in ratio:
- Numerator: market cap
- Denominator: R&D capitalized stock (Lev-Sougiannis Eq. 8 ile
  industry-spesifik δ_k uygulanmış)

> 📝 Q39 ortogonal: HXZ 2020'nin formal R&D-to-market tanımı
> "capitalization stock" mu "3-yıl flow toplamı" mı paperdan tek-tek
> teyit edilemedi (wiki extract'te detay yok). Lev-Sougiannis [s.133
> footnote 22] **proper capitalization stock 3-yıl-flow-toplamı'ndan
> dramatic farklı** (Pharma RDC/M coef 0.0114 vs 0.0078) — wiki
> recommendation: Faz 3 spec'inde proper capitalization stock.

## Wiki ingested factor/paperları için intangibles-aware revision

> 📝 **F bloğu KAPANDI Cycle 17.** 3-katmanlı methodology hierarchy
> tamamlandı:

| Wiki factor / paper | Geleneksel methodology | Lev-Sougiannis (R&D-only) revision | Peters-Taylor (total) revision | Etkilenen wiki sayfası |
|---|---|---|---|---|
| **HML / Book-to-Market** | Reported BV / Market | BV^c = BV + RDC | BV^c = BV + RDC + Organization + External | [[HML]], [[famafrench1993_three_factor]] |
| **Sloan accruals** | (NI - CFO) / Total Assets | + (RD - RA) adjustment | + (RD - RA) + (advertising - RA_adv) + (SG&A_org - RA_org) | [[Accruals]], [[sloan1996_accruals_anomaly]], [[concepts/earnings_quality]] |
| **CMA / Asset Growth** | (TA_t - TA_{t-1}) / TA_{t-1} | TA^adj = TA + RDC | TA^adj = TA + RDC + O + intan; CGS-Ion 2018 paralel; **HXZ + total capital → 23/35 unexplained** [s.5-6] | [[CMA]], [[Asset_Growth]], [[cooper_gulen_ion2018_asset_growth_factor_models]] |
| **G-Score G6 (R&D / Assets)** | Mohanram industry-median R&D intensity | Lev-Sougiannis literatür hattı kökü | Knowledge capital alt-bileşeni; G7 (Capex) physical capital, G8 (Advertising) organization capital alt-bileşeni | [[G_Score]], [[mohanram2005_g_score]] |
| **HXZ R&D-to-market (Rdm)** | (varies: stock vs flow) | Lev-Sougiannis amortization patterns methodology temeli | **Peters-Taylor total intangibles paradigm'ında genişletilebilir** (Q42 yeni) | [[hou_xue_zhang_2020_replicating_anomalies]] |
| **F-Score** | F_ACCRUAL (CFO > NI) | R&D-adjusted F_ACCRUAL | + advertising + organization adjusted F_ACCRUAL | [[F_Score]] |
| **Earnings quality concept** | CFO + accrual persistence | R&D giderleştirme accrual signal'i distort eder | + organization capital + external intangibles boyutu (Q26 partial-stronger) | [[concepts/earnings_quality]] |
| **q-factor model I/A** | Asset growth (TA bazlı) | R&D-adjusted TA bazlı I/A | **q^tot proxy** (Peters-Taylor Eq. 9): V/(K^phy + K^int); **Q23 partial-stronger** | [[concepts/factor_model]], [[hou_mo_xue_zhang_2020_security_analysis]] |
| **Tobin's q** (general) | V / Book Assets | V / (Assets + RDC) | **V / (K^phy + K^int)** (Peters-Taylor Eq. 9); standard V/PP&E reject; +21% ρ² iyileşme | [[concepts/factor_model]] |

## NDX strateji için yapısal foundation — 3 ayak hazır (KAPANDI Cycle 17)

Wiki'nin amacı (S&P 500 + NDX) için intangibles-aware accounting
**NDX tarafının yapısal temeli — 3 ayak**:

| Ayak | Cycle | Paper | Sağladığı methodology |
|---|---|---|---|
| 1. ayak (Methodology hub) | 15 | [[lev_sougiannis_1996_rd_capitalization]] | R&D-only perpetual inv + industry-spesifik amortization |
| 2. ayak (Total intangibles + q proxy) | 16 | [[peters_taylor_2017_intangible_capital]] | K^int = Knowledge + Organization + External; q^tot proxy |
| 3. ayak (Post-2010 application + adjusted strategy) | 17 | [[lev_srivastava_2020_value_failure]] | Adjusted HML (39/34 yıl); value-trap-avoidance Logit escape |

**Faz 3 NDX strategy spec için methodology infrastructure tam hazır**;
Faz 2'de Eisfeldt-Papanikolaou 2013 organization-only direct factor
portfolio değerlendirmesi (Q41 4-way horse race tamamlamak için).

1. **NDX (FAANG-dominant) tech-heavy evren:** Geleneksel HML/Bm + Sloan
   accruals + CMA + RMW factor'leri yapay sinyal verir; R&D
   capitalization adjusted versiyonlar gerekli.

2. **Q23 (NDX intangibles q-factor span)** anchor: Cycle 13'te HXZ 2020
   R&D-to-market q-factor alpha sig dört darbe 4/4 bulgusu Lev-Sougiannis
   methodology temeline dayanıyor; Q23 partial cevap.

3. **Q26 (tech firma accrual ölçümü R&D distortion)** mekanizma cevabı:
   R&D giderleştirme working capital değişimi azaltır → traditional
   Sloan accruals "düşük accrual" gösterir; Lev-Sougiannis capitalize
   edince signal düzeltilir.

4. **Q1 (S&P 500 value post-2000)** kavramsal hazırlık: Adjusted Bm
   dispersion azalır → traditional value premium R&D-yoğun firms'da
   yapay olabilir; Lev-Srivastava 2020 (Cycle 17) post-2010 value
   collapse'ı bu methodology üzerinden açıklayacak.

5. **Q38 (industry amortization rates) yeni tasarım kararı:** NDX
   evrende GICS sektör sınıflandırma + Lev-Sougiannis 6-sektör
   amortization rates kalibrasyonu Faz 3 spec için ön koşul.

6. **Q39 (R&D stock vs flow) yeni tasarım kararı:** Faz 3 spec'inde
   HXZ 2020 R&D-to-market'in formal tanımı + Lev-Sougiannis proper
   capitalization stock methodology'i tercih edilmesi gerek.

## Dört darbe çerçevesi içinde intangibles-aware factor adayları

[[concepts/post_publication_decay]] dört darbe çerçevesi sentez
tablosu:

- **R&D-to-market (Rdm)** — 4/4 hayatta kalan factor; Lev-Sougiannis
  methodology temeli
- **R&D capital subsequent return implication 4.57% yıllık** —
  Lev-Sougiannis [Tablo 5] direct kanıt; Faz 3 NDX strategy alpha
  component aday'ı
- **Earnings announcement abnormal returns (Abr)** — 4/4 hayatta;
  Piotroski 2000 mekanizmasının q-factor lens'inde hayatta kalan
  bileşeni; intangibles-spesifik mi (paper okumaya değer)?

## İlgili paperlar (ingested)

- [[lev_sougiannis_1996_rd_capitalization]] — F bloğu #1; R&D
  capitalization origin paper (Cycle 15); methodology hub
- [[peters_taylor_2017_intangible_capital]] — F bloğu #2; total
  intangible capital generalization (Cycle 16); q theory + total q
  proxy methodology
- [[eisfeldt_papanikolaou_2013_organization_capital]] — **Cycle 25
  yeni**; F bloğu **4. ayak (factor portfolio direct evidence)** ⭐;
  organization capital factor portfolio long-short 4.8%/yıl Sharpe
  0.58, FF3 α 5.5%, Carhart α 3.9% (1970-2008); SG&A perpetual
  inventory δ=15% (Lev-Radhakrishnan 2004 paterni); industry-relative
  within FF17 + annual June rebalance; **methodology infrastructure
  (1+3+4) + factor portfolio anchor (2) ayrımı dokümante**;
  F bloğu Cycle 17'de 3-katmanlı kapatıldı, Cycle 25 ek 4. ayak ile
  4-katmanlı hierarchy
- [[mohanram2005_g_score]] — G6 R&D/Assets bileşeni Lev-Sougiannis
  literatür hattı kökü; G7/G8 Peters-Taylor framework'ünde knowledge/
  physical/organization capital sınıflandırması
- [[hou_xue_zhang_2020_replicating_anomalies]] — R&D-to-market dört
  darbe 4/4 methodology temeli Lev-Sougiannis; Peters-Taylor total
  paradigm'ında genişletilebilir mi (Q42 yeni)
- [[hou_mo_xue_zhang_2020_security_analysis]] — q-factor model
  intangibles düzeltmesi yok; Lev-Sougiannis + Peters-Taylor
  intangibles-aware q5 versiyonu Faz 2'de (Q23 partial-stronger)
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — Peters-Taylor
  2017 metodu **explicit kullanmış** [s.5-6]: HXZ + total capital →
  5/35 → 23/35 unexplained (sürpriz: intangibles düzeltmesi q-factor
  açıklayıcı gücünü **GÜÇLENDİRMİYOR**)
- [[sloan1996_accruals_anomaly]] — R&D bias accrual hesabında
  (Q26 mekanizma); Peters-Taylor advertising + organization
  ekstensiyon

## İlgili paperlar (henüz ingest edilmedi)

- Eisfeldt-Papanikolaou 2013 "Organization Capital" (Tier 2 #28) —
  Faz 2 seçici ingest adayı; organization capital factor portfolio
  direct evidence (Q41 4-way horse race tamamlamak için kritik)
- Hirshleifer-Hsu-Li 2018 "Innovative Originality" (Tier 2 #29) —
  Faz 2 seçici ingest adayı
- Hall, B. (1993a, 1993b) — R&D stock-market valuation
- Li-Liu-Xue 2014 — q-theory model + intangibles cross-section returns
  (Peters-Taylor [s.6] referans veriyor; organization capital hariç)
- Enache-Srivastava 2018 (Management Science) — Lev-Srivastava 2020
  SG&A intangibles allocation methodology referansı (Q40 ile bağlantılı)

## İlgili kavramlar

- [[concepts/earnings_quality]] — intangibles-related accruals boyutu
  (Q26 mekanizma)
- [[concepts/asset_growth_anomaly]] — adjusted asset growth measure
  intangibles-aware revision; CGS-Ion 2018 + Peters-Taylor 2017
  paralel methodology
- [[concepts/post_publication_decay]] — dört darbe çerçevesinde R&D-
  to-market 4/4 hayatta; Lev-Sougiannis methodology temeli
- [[concepts/contextual_fundamental_analysis]] — sektör-spesifik
  amortization patterns context-dependent; Mohanram industry-median
  + Lev-Sougiannis sektör mapping
- [[concepts/factor_model]] — q-factor model intangibles-aware
  revision (Q23 partial cevap)

## Forbidden claims

> ⚠️ Wiki bu sayfada yapmaması gereken claim'ler:
>
> 1. **"R&D capitalization mispricing kanıtıdır"** — paper [s.134]
>    explicit "mispricing OR extra-market risk factor" iki alternative
>    yorumu açık bırakıyor; wiki taraf tutmaz.
>
> 2. **"Intangibles-aware methodology Faz 3'te otomatik kullanılır"** —
>    Q38 (industry amortization kalibrasyonu) + Q39 (R&D stock vs
>    flow) tasarım kararları beklenir; otomatik uygulama değil
>    kalibrasyonlu seçim.
>
> 3. **"Lev-Sougiannis methodology total intangible capital'ı kapsar"** —
>    Lev-Sougiannis sadece R&D; advertising flow proxy olarak; organization
>    capital + brand value Peters-Taylor 2017 (Cycle 16'da kapsandı:
>    R&D + organization + external) + Eisfeldt-Papanikolaou 2013 ile
>    genişler. **Cycle 16 ingest sonrası bu claim doğrulandı**:
>    Peters-Taylor methodology Lev-Sougiannis'in **strict generalization'ı**;
>    "Lev-Sougiannis methodology yeterli" iddiası R&D-only bağlamında
>    geçerli, total intangible için **Peters-Taylor zorunlu**.
>
> 4. **"R&D capital her zaman positive value-relevant"** — paper
>    [s.123] R&D-adjusted ROE > reported ROE only when R&D growth
>    rate sufficiently high; yavaş-büyüyen R&D firms için adjusted
>    ROE düşebilir.

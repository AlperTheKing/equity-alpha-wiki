---
type: paper
authors: [Peters, Ryan H., Taylor, Lucian A.]
year: 2017
title: "Intangible Capital and the Investment-q Relation"
venue: "Journal of Financial Economics 123 (2), 251-272 (Feb 2016 working draft, JFE 2017 published)"
url: https://www.sciencedirect.com/science/article/pii/S0304405X16301969
ssrn: https://ssrn.com/abstract=2405231
local_path: raw/papers/peters_taylor_2017_intangible_capital.pdf
ingested: 2026-05-01
tags: [intangibles, total_q, organization_capital, knowledge_capital, investment_q_theory, NDX_kritik, F_blok_2, Faz_1_finalizasyon]
status: ingested
---

# Peters & Taylor (2017) — Intangible Capital and the Investment-q Relation

> 📝 **Atıf konvansiyonu:** `[Tablo N]` numaralı tablolar; `[s. X]`
> SSRN working paper PDF sayfa numarası (Feb 2016 draft, 57 sayfa).
> Embedded text extract: `pdftotext -layout` ile lokal okuma. JFE 2017
> yayın versiyon sayfa numaraları farklı olabilir.

> 📝 **F bloğu (intangibles) #2** — Lev-Sougiannis 1996 (Cycle 15)'in
> R&D-only methodology'sini **total intangible capital'a genişletir**:
> R&D + organization (SG&A 30%) + external (intan balance sheet).
> NDX strateji yapısal foundation 2. ayağı; Lev-Sougiannis ile aynı
> konsept (capitalize-instead-of-expense) ama daha kapsamlı.

## TL;DR

Peters-Taylor 2017, **klasik q theory'nin intangible capital ile
test edilmesi gerektiğini** argümanlar; "total q" diye yeni bir
Tobin's q proxy'si önerir: `q^tot = V / (K^phy + K^int)` burada
K^int = knowledge capital (R&D perpetual inventory) + organization
capital (30% × SG&A perpetual inventory) + external intangibles
(Compustat `intan`).

**Sample: Compustat 1975-2011** (regulated utility 4900-4999 hariç,
financial 6000-6999 hariç, non-operating 9000+ hariç, min $5M physical
capital). Within-firm OLS panel regressions (firm + year fixed effects).

**Headline R²** [Tablo 2 + Section 4.1, s.18-19]:
- Physical investment ~ q^tot: R² = **20.9%**
- Intangible investment ~ q^tot: R² = **27.9%**
- **Total investment** ~ q^tot: R² = **32.7%**
- Standard regression CAPX/PPE ~ V/PPE: R² = 23.3%

Total q (intangibles dahil) standard q'dan **5 investment ölçüsünün
hepsinde** üstün R² üretir; iyileştirme 1-8 percentage points (5-50%
relative); t-stat'lar 3.4-25.

**Macro-level fark dramatik** [Section 6]: Standard investment-q
regression R² = 4%; intangibles dahil R² = **61%**.

**Adjustment cost finding** [Section 4.2, Tablo 3]: Cumulant estimator
ile bias-corrected; intangible capital convex adjustment cost (φ_int)
≈ **2 × physical (φ_phy)** — intangibles slow-adjusting.

**Sürpriz bulgu** [Section 5]: Klasik q theory **daha iyi fits**
intangibles-yoğun firms / industries / years'de — intangibles
quartile 1→4'te R² monotonic artar (23%→47%).

**Cash flow finding** [Section 4.2, Panel B]: Theory cash-flow
slope = 0 öngörür; physical investment'ta sig pozitif; **R&D
component cash flow'a insensitive** (theory consistent); SG&A
component highly sensitive (theory inconsistent ama measurement
error caveat).

## Tek Cümle Tezi

Klasik neoklasik investment-q theory, intangible capital dahil
edildiğinde (total q proxy ile) **eski standart q'dan üstün** ve
intangibles-yoğun firms/industries/years'de **daha iyi fits**;
yeni "total q" proxy intangible-aware corporate finance regression
için simple-yet-powerful methodology baseline.

## Ortaya Konan Sinyal/Faktör

**Yeni empirik faktör YOK** (cycle 16 plan onayı: factor entity
açılmaz). Paper bir **methodology paper** — intangible-adjusted
corporate finance regression için "total q" proxy methodology'i;
return prediction değil, q theory test eden corporate finance
paper.

Wiki'de bu paperdan **mevcut concept sayfası genişletilir:**

- [[concepts/intangibles_adjusted_accounting]] — F bloğu anchor
  concept; Cycle 15 Lev-Sougiannis 1996 origin + Cycle 16
  Peters-Taylor 2017 generalization (total intangible capital) +
  **Cycle 17 Lev-Srivastava 2020 post-2010 application (KAPANDI)**

> 📝 **Paper'ın factor-level dolaylı katkıları wiki'de:**
> - [[CMA]], [[Asset_Growth]] — Peters-Taylor intangibles-adjusted
>   I/A formülasyonu (CGS-Ion 2018 [s.5-6] paralel)
> - [[hou_xue_zhang_2020_replicating_anomalies]] R&D-to-market
>   (Rdm) factor — Peters-Taylor total intangibles paradigm'ında
>   genişletilebilir mi (Q42 yeni)
> - [[G_Score]] G6 (R&D) → knowledge capital, G7 (Capex) →
>   physical capital, G8 (Advertising) → organization capital
>   (SG&A alt-bileşeni); Mohanram 2005 + Peters-Taylor methodology
>   hierarchy

## Metodoloji

### Theory framework [Section 2]

**Setup**: Infinitely-lived perfectly competitive firm, 2 capital
goods (physical + intangible), CES production, quadratic adjustment
costs (Hayashi 1982 + Abel-Eberly 1994 paralel).

**Bellman equation [Eq. 1]**: Firm value V_it firm seçtiği physical
+ intangible investment rates'in expected discounted profit minus
adjustment cost integrali.

**4 Predictions [Section 2.1]:**
- **P1 [Eq. 5]**: Marginal q = average q (constant returns to
  scale, perfect competition assumption); `∂V/∂K^phy = ∂V/∂K^int =
  V/K^tot = q^tot`
- **P2 [Eq. 6-7]**: Optimal investment rates linear in q^tot:
  `i^m = (1/φ^m)(q^tot - α^m - p^m)`, m = phy, int
- **P3**: OLS regressions of i^phy / i^int / i^tot on q^tot with
  firm + time FE → q-slope = 1/φ^m; cash flow shouldn't enter
  significantly
- **P4**: Standard regression CAPX/PPE ~ V/PPE produces
  **downward-biased q-slope** ve **lower R²** (misspecified — ratio
  K^tot/K^phy regression disturbance'ında)

### Total q proxy [Eq. 9, s.12]

```
q^tot_it = V_it / (K^phy_it + K^int_it)
```

Burada:
- **V_it** = market equity (Compustat `prcc_f` × `csho`) + book
  debt (`dltt` + `dlc`) − current assets (`act`, cash + inventory
  + marketable securities)
- **K^phy_it** = `ppegt` (gross PP&E book value)
- **K^int_it** = Knowledge Capital (G_it) + Organization Capital
  (O_it) + External Intangibles (`intan`, balance sheet)

### Knowledge capital — perpetual inventory of R&D [Eq. 11]

```
G_it = (1 - δ_R&D) × G_{i,t-1} + R&D_it
```

- **δ_R&D = BEA industry-specific** (Li 2012):
  - Pharma: **10%**
  - Computer hardware/peripherals: **40%**
  - Other industries: **15%** (default)
- Compustat `xrd` annual R&D
- Initial stock G_i0 estimated using founding-year + average pre-IPO
  R&D growth rate (avg log change R&D 0.348 pre-IPO) [Appendix B]

### Organization capital — perpetual inventory of 30% SG&A [Eq. 11 paralel]

```
O_it = (1 - δ_SG&A) × O_{i,t-1} + θ × SG&A_it
```

- **θ = 30%** (default; Hulten-Hao 2008 + Eisfeldt-Papanikolaou
  2014 + Zhang 2014 paralel; %20-50 robustness testleri Section
  7.2 sonuç değişmiyor)
- **δ_SG&A = 20%** (industry-bağımsız default; Section 7.3
  alternatif spesifikasyonlar)
- Compustat `xsga` SG&A (Appendix B'de R&D allocation correction:
  xsga - xrd - rdip; Compustat çoğu durumda xrd'yi xsga'ya dahil
  ediyor)

### External intangibles

Compustat `intan` = Goodwill (`gdwl`) + Other Intangibles (`intano`).
Ana analizde Goodwill dahil; Section 7.3 Goodwill hariç ile sonuç
benzer.

### Cumulant estimator [Section 4.2]

Erickson-Jiang-Whited (2014) higher-order cumulant estimator —
measurement error-adjusted slope estimates. İki ek istatistik üretir:
- **τ²** = hipotetik R² from `i = α + β q + ε` (true q'nun
  investment'ı ne kadar açıkladığı)
- **ρ²** = hipotetik R² from `p = γ + δ q + ν` (q proxy'nin true q
  ile association'ı)

### Empirical sample

- **Sample period**: 1975-2011 (FASB 1975 R&D reporting requirement)
- **Universe**: Compustat firms; regulated utility (4900-4999),
  financial (6000-6999), non-operating (9000+) hariç; min $5M
  physical capital
- **Panel structure**: Firm × year, OLS firm + year FE
- **Winsorization**: 1% level all regression variables
- **Coverage**: 1975-2011 yıllık panel; 47% firm/year missing R&D
  (set to zero starting 1977 per Lev-Radhakrishnan 2005)

## Empirik Sonuçlar (sayılarla)

### Sample statistics [Tablo 1, s.16-17]

- Total q exceeds 10 in **only 1%** of obs (vs 7% for standard q)
  → total q daha **stabil** measure
- Total q standard deviation **74% lower** than standard q
- Average **physical** investment rate ≈ average **intangible**
  investment rate
- Physical investment **more volatile + right-skewed**
- **Manufacturing firms** average intangible intensity ≈ 30-34%
  (sürprizli yüksek)
- High-tech + health firms: **çok daha intangible-heavy**

### Full-sample OLS results [Tablo 2, s.18-19]

| Specification | Investment measure | q measure | R² |
|---|---|---|---|
| Panel A col 1 | i^phy = I^phy/K^tot | q^tot | **20.9%** |
| Panel A col 2 | i^int = I^int/K^tot | q^tot | **27.9%** |
| Panel A col 3 | i^tot = (I^phy+I^int)/K^tot | q^tot | **32.7%** |
| Panel A col 4 | R&D/K^tot (alt int measure) | q^tot | 27.0% |
| Panel B col 5 | CAPX/PPE (standard) | V/PPE (standard) | 23.3% |

Total q delivers larger R² than standard q **all 5 investment
measures** [Panel C]; iyileştirme 1-8 pp (5-50% relative);
t-stats 3.4-25.

### Comovement of physical + intangible investment [Section 4.1]

- Within-firm correlation i^phy ↔ i^int: **31%** (firm + year FE
  removed)
- Q^tot residual'larından sonra: **17%** (q^tot explains 14 pp of
  comovement, theory consistent)

### Bias-corrected cumulant estimator [Tablo 3, s.21-22]

| Specification | Inv measure | q-slope | τ² | ρ² |
|---|---|---|---|---|
| Panel A col 1 | i^phy | q^tot | 0.070 | 0.273 | 0.629 |
| Panel A col 2 | i^int | q^tot | 0.037 | 0.290 | 0.629 |
| Panel A col 3 | i^tot | q^tot | 0.107 | 0.423 | 0.597 |
| Panel A col 5 | CAPX/PPE | V/PPE | 0.036 | 0.372 | 0.492 |

**Adjustment costs**: φ_int ≈ 2 × φ_phy (q-slope intangible 0.037
≈ ½ q-slope physical 0.070 → inverse ⟹ φ_int 2× φ_phy)

**Total q vs standard regression**: τ² **14% higher** (0.423 vs
0.372) + ρ² **21% higher** (0.597 vs 0.492); intangibles dahil
**hem investment-q ilişkisi hem q proxy quality** belirgin iyileşir.

**Cash flow** [Panel B]:
- Physical investment cash-flow slope **0.024** sig pozitif (theory
  inconsistent; standard reg 0.015 → intangibles dahil **60% daha
  yüksek**)
- R&D component cash-flow slope **0.000** (theory consistent)
- Intangible investment cash-flow slope 0.012-0.050 (range —
  SG&A measurement error caveat)

### Subsample analysis — sürpriz bulgu [Tablo 4, Section 5]

Firmler intangible quartile 1 (low) → 4 (high) sırala:

| Intangible quartile | i^tot R² | i^tot R² (standard reg) |
|---|---|---|
| Q1 (low) | 23% | 18% |
| Q2 | 30% | 22% |
| Q3 | 38% | 26% |
| Q4 (high) | **47%** | **30%** |

Klasik q theory **daha iyi fits** intangibles-yoğun firms'de —
hem total q regression hem standard regression dahil. **Tüm 4
investment measure** + **3 subsample partition** (intangible
quartile, FF5-industry, early/late period) **monotonic patterns**.

### Macro-level results [Section 6]

- Standard investment-q regression (CAPX_aggregate ~ V_aggregate /
  PPE_aggregate): R² = **4%**
- Intangibles-aware total q: R² = **61%** — **15× iyileşme**

### Robustness [Section 7]

- **θ (SG&A allocation)** %0-100 range: ana sonuçlar dayanıklı; θ=30%
  best fit
- **δ_SG&A organization depreciation**: ana sonuçlar dayanıklı
- **Goodwill exclusion**: sonuç değişmiyor
- **Initial stock = 0** (alt initial condition): sonuç değişmiyor
  (hatta daha güçlü Section 3 footnote)
- **First 5 years dropped**: sonuç değişmiyor
- **R&D-missing firms dropped** (47% sample): sonuç değişmiyor
- **IV estimators (Biorn 2000, Arellano-Bond 1991)**: cumulant ile
  paralel sonuçlar

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Paper return prediction değil — q theory test eden corporate finance regression. Decile-spread methodology yok. Cross-section returns için Li-Liu-Xue 2014 [s.6] referansı ("they focus on the cross-section of stock returns... Unlike us, they exclude organization capital"). | **❌** |
| **Annual rebalance** | Sample 1975-2011 yıllık Compustat panel; firm × year observations; investment regressions yıllık frekans. **Annual frequency natural fit**. | **✅** |
| **Large-cap evrene transfer** | Sample tüm Compustat (regulated utility/financial/non-operating hariç, min $5M physical capital → small-cap dahil ama not micro). Manufacturing vs non-manufacturing breakdown var [Section 5, Tablo 5]: standard q proxy manufacturing'de daha az measurement error (ρ² Q1 = 68% vs Q4 = 44%); intangibles-aware q **non-manufacturing'de** (high-tech, services) **daha güçlü iyileştirme**. Large-cap-only explicit test paperda yok ama small-cap-tilted **DEĞİL** (intangibles ölçümü çok yıllı public coverage gerekli — natural large-cap bias). | **⚠️** |
| **NDX intangibles / growth firms** | ⭐ **KRİTİK** — Lev-Sougiannis 1996'i tamamlayan total methodology (R&D + organization + external intangibles). NDX evrende FAANG/tech-heavy firmlarda intangibles capital büyük kısmı **SG&A flow** (organization capital) + **`intan` balance sheet stock** (acquired Goodwill + Other) kalemlerinden geliyor — Lev-Sougiannis sadece R&D-only kısmı yakalıyordu. **Section 5 sürpriz bulgu**: q theory **daha iyi fits** intangibles-yoğun firms/industries/years'de — NDX (high-tech + health-care + tech services dominant) yapısal olarak Peters-Taylor methodology'sinin **doğal evren**i. | **✅** NDX strateji yapısal foundation 2. ayağı |

**Strateji tasarımına net implikasyon:**

1. **Top-N ❌ ama dengeleyici 3 bulgu:**
   - Paper return prediction değil, ama **NDX strateji yapısal
     foundation 2. ayağı** (1. ayak: Lev-Sougiannis 1996 R&D
     capitalization basic methodology). Faz 3 NDX strategy spec
     için methodology baseline.
   - Faz 3 NDX strategy spec'inde **total q (V/(K^phy + K^int))**
     kullanım rec; standard q (V/PP&E) reject. CGS-Ion 2018 [s.5-6]
     paralel: HXZ + total capital → 5/35 → 23/35 unexplained
     anomaly (intangibles dahil edilince **factor zoo'nun çoğu
     hala unexplained**) — ama bu bulgu **HXZ q-factor I/A'nın
     intangibles-aware versiyonu kullanılırsa** asset growth
     anomaly'yi çözeceğini implicite ediyor.
   - Manufacturing vs non-manufacturing finding [Section 5] NDX-
     relevant: NDX = ağırlıklı non-manufacturing → intangibles-
     aware q methodology zorunlu.

2. **Faz 3 backtest spec'i için methodology rec'leri:**
   - Q23 Faz 3 spec: q^tot proxy default (Peters-Taylor methodology)
   - Q40 Faz 3 spec: SG&A organization capital allocation θ=30%
     baseline; %20-50 sensitivity testleri
   - Q38 Faz 3 spec: BEA industry-specific R&D depreciation rates
     (Li 2012 modern güncelleme; Lev-Sougiannis 1975-1990 6-sektör
     SIC mapping ile cross-validation)
   - Q39 Faz 3 spec: perpetual inventory **stock** methodology (Eq.
     11) — Lev-Sougiannis ile tutarlı

3. **NDX intangibles ⭐ KRİTİK netliği:** Wiki'nin amacı (S&P 500 +
   NDX) için **NDX strateji = intangibles-aware accounting tabanı
   olmadan tasarlanamaz**. Lev-Sougiannis (R&D-only) + Peters-Taylor
   (total intangibles) kombinasyonu Faz 3 NDX spec için **iki ayaklı
   methodology infrastructure**.

## Limitler ve Caveats

1. **Paper return prediction yapmıyor** — Top-N (✅ aday yok); Faz 3
   spec için methodology infrastructure ama factor portfolio kanıtı
   ayrı ingest gerekir (Eisfeldt-Papanikolaou 2013 organization
   capital factor portfolio direct evidence; Tier 2 #28).

2. **Sample sonu 2011** — Modern dönem (2012-2024 FAANG era,
   COVID-19, ML feature explosion) Peters-Taylor methodology
   replikasyonu yok. Q40 modern data ile organization capital θ
   kalibrasyonu açık.

3. **SG&A allocation θ=30% pre-publication consensus** — paper
   robustness %20-50 testleri yapıyor ama tek bir "doğru" değer
   teorik olarak identifiable değil; theory-data identifying
   assumption ile MLE estimate (consumer 0.38, high-tech 0.51,
   health 0.24) — paper [Section 7.2] "we do not push these θ
   estimates strongly" notu dengeleyici.

4. **Cumulant estimator measurement-error correction** ihtiyaç
   şartları:
   - q proxy non-zero skewness varsayımı
   - Measurement error u, ν independent of true q
   - Bu varsayımlar ihlal edildiğinde slope estimates'lar yanıl
     bulgular verir; standard regression'ın q'sını kullanmak yanıl
     (intangibles measurement error'ı serially correlated) — paper
     bu sebeple total q proxy'sini önerir, ama mutlak measurement
     error sıfır iddiası yok.

5. **Cash-flow finding partial inconsistency** — physical investment
   cash-flow slope sig pozitif (theory predicts 0); paper [Section
   4.2] "decreasing returns to scale veya financing constraints"
   alternatif yorumlar açık bırakır.

6. **Theory simplifies neoclassical assumptions** — constant returns
   to scale, perfect competition, perfect substitutes assumption'ları
   gerçek dünyaya tam fit etmez; sürpriz bulgu (intangibles-yoğun
   firms theory better fits) bu assumption'ların ihlal patternleri
   ile ilgili açık soru — Section 5 + Online Appendix 6 partial
   tartışıyor.

## Çelişkiler/Tartışmalar

> ⚠️ **CGS-Ion 2018 ↔ Peters-Taylor 2017 paralel methodology
> (çelişki değil, complementary):** CGS-Ion 2018
> [[cooper_gulen_ion2018_asset_growth_factor_models]] [s.5-6]
> Peters-Taylor methodology'sini explicit kullanıyor — HXZ + total
> capital intangibles dahil edildiğinde **5/35 unexplained → 23/35
> unexplained** (anomaly explanation power **azalır**). Bu sürprizli
> bulgu Peters-Taylor methodology'sinin q-factor model'in CGS asset
> growth ölçüsüne **kritik bağlı** olduğunu gösteriyor — saf
> intangibles düzeltmesi q-factor'ı asset growth anomaly'yi
> açıklamada **GÜÇLENDİRMİYOR**. Wiki için: NDX strategy spec'inde
> Peters-Taylor methodology'i naive uygulamak yerine **CGS-Ion
> methodology kombinasyonu** + horse race testleri gerekir.

> ⚠️ **Peters-Taylor 2017 ↔ HXZ 2020 q-factor I/A (potansiyel
> definition farkı, çelişki adayı):** HXZ 2020 q-factor model I/A
> = total asset growth (TA bazlı) — Peters-Taylor methodology
> kullanmıyor (intangibles dahil değil). Peters-Taylor [s.5]
> "Li, Liu, and Xue (2014) structurally estimate a q-theory model
> that includes intangible capital ... Unlike us, they focus on the
> cross-section of stock returns, and they exclude organization
> capital" — yani factor portfolio implementation'larda intangibles
> integration parçalı. **NDX strategy için açık tasarım sorusu**:
> q-factor model + Peters-Taylor total intangibles entegrasyonu yapan
> modern paper wiki'de yok. Q42 yeni soru.

> ⚠️ **Peters-Taylor 2017 ↔ wiki Lev-Sougiannis-only methodology
> claim'leri (stale claim adayı, Cycle 16 consolidation pass'te
> kontrol):** Cycle 15 [[concepts/intangibles_adjusted_accounting]]
> sayfası "Lev-Sougiannis methodology total intangible capital'ı
> kapsamaz" forbidden claim olarak işaretlemişti — Peters-Taylor
> ingest sonrası bu claim doğrulanır (Lev-Sougiannis sadece R&D;
> Peters-Taylor R&D + organization + external). Wiki diğer
> sayfalarda (sloan1996_accruals_anomaly, Accruals factor entity)
> "intangibles düzeltmesi = R&D capitalization yeterli" implicit
> assumption olabilir — consolidation pass'te tarama gerekir.

## İlgili Sayfalar

### Concepts
- [[concepts/intangibles_adjusted_accounting]] — F bloğu hub
  (Lev-Sougiannis origin + Peters-Taylor total generalization)
- [[concepts/factor_model]] — q-factor model intangibles-aware
  revision (Q23 partial-stronger via Peters-Taylor)
- [[concepts/asset_growth_anomaly]] — CGS-Ion 2018 + Peters-Taylor
  paralel methodology
- [[concepts/earnings_quality]] — intangibles-related accruals
  boyutu (Q26 partial-stronger via Peters-Taylor advertising +
  organization adjustment)

### Papers
- [[lev_sougiannis_1996_rd_capitalization]] — F bloğu #1; R&D-only
  origin paper; Peters-Taylor [s.10] explicit citation
  ("A large R&D literature (e.g., Lev and Sougiannis, 1996) shows
  that R&D investments increase firms' future profits")
- [[lev_srivastava_2020_value_failure]] — **F bloğu #3 KAPANIŞ
  (Cycle 17)**; Lev-Srivastava SG&A intangibles allocation
  methodology Peters-Taylor θ=30% paralel (Enache-Srivastava 2018
  referans); R&D capital perpetual inventory Lev-Sougiannis paralel;
  3-katmanlı F bloğu hierarchy tamamlandı
- [[eisfeldt_papanikolaou_2013_organization_capital]] — **Cycle 25
  yeni**; F bloğu **4. ayak (factor portfolio direct evidence)**;
  Peters-Taylor [s.5, 10] Eisfeldt-Papanikolaou explicit cite —
  Peters-Taylor **θ=30% SG&A allocation methodology paterninden
  derive**; **methodology farkı (Q60 yeni)**: Eisfeldt-Papanikolaou
  full SG&A perpetual inventory (δ=15%) vs Peters-Taylor θ=30%
  partial allocation; iki methodology aynı SG&A flow'unu farklı
  treatment; çelişki değil — Peters-Taylor knowledge + organization
  + external 3 component ayrım için θ tahmin ediyor, Eisfeldt-
  Papanikolaou measurement error caveat ile full SG&A. Q41 4-way
  horse race fully-answered: methodology infrastructure (Lev-
  Sougiannis + Peters-Taylor + Lev-Srivastava) + **factor portfolio
  anchor (Eisfeldt-Papanikolaou)** ayrımı.
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — Peters-Taylor
  methodology'sini explicit kullanıyor (CGS-Ion [s.5-6]); paralel
  intangibles-aware investment factor analysis
- [[hou_xue_zhang_2020_replicating_anomalies]] — R&D-to-market
  factor (q-factor alpha sig dört darbe 4/4); Peters-Taylor total
  intangibles paradigm'ında genişletilebilir mi (Q42 yeni)
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 model intangibles
  düzeltmesi yok; q-factor + Peters-Taylor entegrasyonu yapan paper
  yok (Q23 partial)
- [[famafrench2015_five_factor]] — CMA factor (asset growth bazlı);
  Peters-Taylor intangibles-adjusted I/A alternative; HML redundancy
  ↔ Lev-Srivastava adjusted HML scope-dependent çelişki adayı

### Factors
- [[CMA]] — Peters-Taylor intangibles-adjusted I/A formülü
- [[Asset_Growth]] — CGS-Ion 2018 + Peters-Taylor methodology
  paralel
- [[G_Score]] — G6 (R&D) → knowledge capital, G7 (Capex) → physical
  capital, G8 (Advertising) → organization capital (SG&A 30%
  alt-bileşeni)

## Açık Sorular (Open Questions)

- **[Q23]** NDX intangibles q-factor span — Peters-Taylor methodology
  q theory intangibles-aware versiyonu test ediyor; q^tot proxy HXZ
  q-factor I/A yerine intangibles-adjusted I/A önerir; **partial-
  stronger ileri**, tam Q23 cevabı için modern q-factor implementation
  Peters-Taylor methodology'i kullanan paper gerekli (wiki'de yok)

- **[Q26]** Tech firma accrual ölçümü R&D distortion — Peters-Taylor
  advertising + organization capital adjustment ekler; adjusted
  Sloan accruals = traditional + (RD - RA) + (advertising - RA_adv)
  + (SG&A_org - RA_org); **partial-stronger ileri**, tam total
  intangibles methodology Q26 kapanışına yakın

- **[Q38]** Industry-spesifik R&D amortization patterns — Peters-Taylor
  BEA industry-specific R&D depreciation rates (Li 2012; pharma 10%
  → computers 40%); Lev-Sougiannis 6-sektör SIC 1975-1990 ile
  modern BEA rates **complementary** (paper [s.13] explicit Li
  2012 reference); **partial-stronger** Faz 3 spec için BEA rates
  modern baseline

- **[Q39]** R&D capital stock vs flow — Peters-Taylor [Eq. 11]
  perpetual inventory **stock** methodology; Lev-Sougiannis ile aynı
  yaklaşım; **partial-stronger ileri**, wiki Faz 3 rec **proper
  capitalization stock** pekiştirilir

- **[Q40 yeni]** Peters-Taylor SG&A organization capital allocation
  θ=30% NDX evrende kalibrasyon: Robustness %20-50 sonuç değişmiyor
  ama NDX-spesifik (tech SG&A büyük kısmı sales force / customer
  acquisition) kalibrasyonu gerekli mi? **Faz 3 design decision**

- **[Q41 yeni]** Peters-Taylor (all-in-one total q) vs Lev-Sougiannis
  1996 (R&D-only) + Eisfeldt-Papanikolaou 2013 (organization-only)
  horse race wiki'de yok. Eisfeldt-Papanikolaou 2013 (Tier 2 #28)
  ingest edildiğinde direct comparison

- **[Q42 yeni]** HXZ R&D-to-market formal tanımı R&D-only
  (Lev-Sougiannis methodology temeli); Peters-Taylor total intangibles
  paradigm'ında genişletilirse (R&D + organization + external)/market
  versiyonu **dört darbe 4/4 hayatta** kalmaya devam eder mi?
  Modern data ile direct test gerekli (wiki'de yok)

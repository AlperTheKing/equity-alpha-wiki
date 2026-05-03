---
type: strategy_draft
version: v0
opened: 2026-05-01
phase: faz_2_cycle_24
status: historic
superseded_by: strategies/v1_draft (Cycle 30)
strategies: [s&p500_v0, nasdaq100_v0]
basis: 21_papers_16_concepts_14_factors_1_methodology
backtest_run: false
purpose: "Faz 2'nin ilk somut strategy çıktı; iki strategy aday'ın taslağı; Faz 3 spec'lerinin (s&p500_v1 + nasdaq100_v1) ön formu"
---

# strategies/v0_draft — İki Strategy Aday Taslağı (HISTORIC)

> 📝 **HISTORIC KAYIT (Cycle 30 itibariyle).** Bu sayfa Cycle 24
> v0_draft açılışı; Cycle 25-29 ek note'larla zenginleşti. **Güncel
> v1 için bkz. [[strategies/v1_draft]]** (Cycle 30 revize). İçerik
> korundu (Cycle 25-29 ek note'lar + Cycle 28 7 stale fix sonrası
> dondurulu) — wiki tasarım kararlarının evrim izlenebilirliği için
> historic preservation. v0 → v1 evrim notu için bkz.
> [[strategies/v1_draft]] §0.

> 📝 **Cycle 24 ilk strategy çıktı.** Wiki Faz 2'nin ilk somut output;
> strategies/ klasörü daha önce boştu. Bu sayfa **iki bağımsız strategy
> aday'ın taslağı** (S&P 500 + NDX); backtest henüz çalıştırılmadı,
> aday faktör seçimleri + methodology + expected performance + bilinen
> zayıflıklar dokümante. Faz 3 v1 spec'lerinin (`s&p500_v1.md` +
> `nasdaq100_v1.md`) ön formu.

> ⚠️ **Bu taslak [[methodology/backtest_spec]] §1-10 + Faz 1 sentez
> backbone (5 priori Q + 5 blok kapanış sentezi + 4/4 hayatta kalan +
> 3-4/4 baseline composite + Sloan zinciri + Profitability zinciri)
> üzerine inşa edilir. Her tasarım kararı **wikilink atıflı** (CLAUDE.md
> §6.1).

---

## 1. STRATEGY 1 — S&P 500 v0

### 1.A Universe & Sample

- **Universe**: S&P 500 üyesi top 500 US stocks (NYSE-VW NYSE-breakpoint
  konvansiyonuna doğal yakın); ex-financials caveat (SIC 1-digit 6
  hariç, [[papers/novy_marx_2013_gross_profitability]] [s.10] paterni)
- **Wiki amaç evrenleri map'i**: S&P 500 ≈ Israel-Moskowitz size Q4-Q5
  spektrumu ([[papers/israel_moskowitz_2013_shorting_size_time]] Q5
  avg 36B 2011 + Q4 avg 4.8B Russell Midcap; Fortune 500 = top 500
  non-fin ≈ S&P 500 üst yarısı — [[papers/novy_marx_2013_gross_profitability]]
  [Tablo 7] direct empirik anchor)
- **Sample dönemi**: backtest henüz çalıştırılmıyor (modern data
  ingest beklenir — Chen-Zimmermann 2022 + JKP 2023 Faz 2 sonu).
  Hedef sample window: 1980-2024 (post-1980 modern accounting period;
  pre/post-publication test dahil). 1963-2010 in-sample
  ([[papers/novy_marx_2013_gross_profitability]] sample) +
  2011-2024 out-of-sample sensitivity test

> 📝 **Cycle 29 ek (data_sources.md açıldı) — Modern data eksik weakness TAM KAPANMA**:
>
> [[methodology/data_sources]] §1-3 tam dokümante: Chen-Zimmermann
> 2022 Open Asset Pricing Database + JKP 2023 GlobalFactor code
> repository GitHub bkelly-lab + WRDS open-source access **üç
> paralel data kaynağı** Faz 3 backtest implementation ön koşul.
> **§1.F + §2.F bilinen zayıflıklar 1. madde "Modern data eksik"
> Cycle 27 partial → Cycle 29 TAM KAPANMA**; v1 revize draft (Cycle
> 30) madde reformulate (post-2020 hala out-of-sample caveat
> korunur ama infrastructure erişilebilir).
>
> **Methodology choice sensitivity test üç alternative weighting**:
> [[methodology/backtest_spec]] §1.3 sertleştirme (pure VW HXZ +
> FF half-weight + capped VW JKP NYSE 80th percentile winsorize);
> Chen-Zimmermann pure replication baseline ortak data altyapısı.

> 📝 **Cycle 27 ek (JKP 2023 ingest) — modern data partial kapanma + multi-theme allocation**:
>
> [[papers/jensen_kelly_pedersen_2023_replication_crisis]] modern
> güncelleme (US 1926+ Global 1986+ 153 factor 93 country Bayesian)
> "Modern data eksik" weakness §1.F + §2.F **partial kapanma**:
> - JKP sample sonu **2020** (NBER WP Feb 2021); post-2014 → 2014-
>   2020 **6 yıl modern dönem kanıt**
> - Post-2020 (FAANG/AI 2021-2024) hala out-of-sample (Chen-Zimmermann
>   data portal Cycle 29 ile tam fully-answered)
>
> **Q33 (post-2014 modern decay) partial-stronger (fully-answered
> aday revize)**; **Q63 (post-2017 FGX modern replikasyon)
> fully-answered**; **Q44 (post-2018 FAANG/AI) partial-stronger**.
>
> **DRAMATIC METODOLOJI DISAGREEMENT** ([[meta/contradictions]] §3):
> HXZ %35 raw + FGX %11 + MP %35 conservative-side vs JKP %84.9 Bayesian
> + %88.5 out-of-sample positive anti-conservative-side ~50pp gap.
> **Wiki için**: HXZ + MP **conservative-side baseline korunur**
> (×0.65 / ×0.50 decay multiplier Cycle 24 muhafazakâr revize); JKP
> %85 anti-conservative upper bound sensitivity reference.
>
> **13 theme cluster + tangency portfolio Faz 3 v1 revize aday**:
> 10/13 themes tangency portfolio sig+ multi-theme allocation
> framework; 3 displaced (profitability, investment, size) joint
> modeling redundancy. v0_draft §1.B + §2.B factor inclusion list
> **theme diversification yapısı** Faz 3 v1 revize sırasında dahil
> edilmeli (Cycle 30 hedef).
>
> **Capped VW (JKP NYSE 80th percentile winsorize) Faz 3 implementation
> tercih aday**: pure VW (HXZ) + FF half-weight + capped VW üç
> alternative ([[methodology/backtest_spec]] §1.3 + §4.4 sertleştirme).

> 📝 **Cycle 26 ek (FGX 2020 ingest) — Profitability seçim DOĞRULANDI**:
> [[papers/feng_giglio_xiu_2020_factor_zoo]] DS LASSO 150-factor
> library lens'inde **RMW + ROE + QMJ DS-sig** (Tablo 1, since-2012
> factors); GP/A 150 library içinde explicit listed teyit edilemedi
> ama Profitability ailesi genel sig dolaylı validation. **v0_draft
> §1.B + §2.B Profitability factor seçim revize gerekmez**;
> RMW Ope iki paralel bulgu (HXZ q-factor INSIG + FGX DS-sig
> methodology farkı dokümante; [[factors/RMW]] detay).

### 1.B Factor Inclusion (dört darbe filter sonrası)

[[methodology/backtest_spec]] §4 dört darbe pipeline + §5 factor
inclusion list referansla:

**S&P 500 CORE composite**:
- **F & V/P combined** ([[papers/li_mohanram2019_quality_value]] modern
  all-firms +11.92% spread; binary intersection) **+** **GP × V/P
  Fortune 500 rank-based** ([[papers/novy_marx_2013_gross_profitability]]
  [Tablo 7] 0.62%/ay Sharpe 0.74; continuous rank product)
- **İki operationalization paralel** (QARP framework Q50 paralel):
  binary intersection vs continuous rank product; horse race Faz 3 v1

**Filter katmanı**:
- **Beneish M-Score forensic** ([[factors/M_Score]]; cutoff −2.22
  default `.025`); large-cap kalibrasyon Q46 paralel

**Overlay**:
- **Long-only momentum top 30%** ([[papers/israel_moskowitz_2013_shorting_size_time]]
  [Fig.1 Panel D]; 86-yıl size-invariant; Q5 largest long-only α=3.92%
  t=3.83 sig; [[factors/UMD]] aylık-orijinal annual uyarlama Q33
  sensitivity test)

**4/4 hayatta kalan factor signal'ları** ([[methodology/backtest_spec]] §5.1):
- **Sloan operating accruals (Oa)** core signal (q-factor alpha
  -0.54%/ay sig; Sloan zinciri origin)
- **Cash-based op profits (Cop)** profitability core (q-factor alpha
  0.69%/ay sig; Profitability zinciri 4. halka)
- **Earnings announcement Abr** event-driven complement (q-factor
  alpha 0.66%/ay sig)

**REJECT**:
- Vanilla HML standalone ([[methodology/backtest_spec]] §5.3; Israel-
  Moskowitz size Q4-Q5 INSIG + Lev-Srivastava post-2010 collapse çift
  anchor)
- SMB vanilla (Q11 fully-answered ASTERISK; HLZ MT + 86-yıl confirmation
  çift kanıt)
- F-Score standalone large-cap (BM-Q5 only kalibre)
- Magic Formula (q5 captures + microcap residual)
- RMW Ope (HXZ q-factor alpha 0.04% t=0.42 INSIG; QMJ Profitability
  composite tercih)

### 1.C Methodology

[[methodology/backtest_spec]] §1-9 referansla:

| Methodology kararı | Spec | Anchor |
|---------------------|------|--------|
| Universe | NYSE-breakpoint VW; S&P 500 top 500 | [[papers/hou_xue_zhang_2020_replicating_anomalies]] + [[papers/israel_moskowitz_2013_shorting_size_time]] [Tablo A2] çift teyit (§1.3) |
| Rebalance | Annual June (CLAUDE.md §1 proje amacı) | [[papers/famafrench1993_three_factor]] + [[papers/sloan1996_accruals_anomaly]] + [[papers/novy_marx_2013_gross_profitability]] convention (§2.1) |
| Performance reporting | DSR + alpha t-stat + decay-adjusted spread üçlü | [[papers/bailey_lopezdeprado_2014_deflated_sharpe]] (§3.1) |
| MT cutoff | HLZ `\|t\| > 3.0` BHY 1% | [[papers/harvey_liu_zhu_2016_multiple_testing]] (§4.3) |
| Decay multiplier | ×0.65 standard ([[papers/mclean_pontiff_2016_post_publication_decay]] aggregate %35) | (§4.2) |
| Çift düzeltme prensibi | Tek-düzeltme: factor-level HLZ vs strategy-level DSR | (§3.3 Q37) |

### 1.D Strategy Architecture

```
S&P 500 strategy v0:
  Step 1 (Universe): top 500 US stocks ex-financials
  Step 2 (Forensic filter): Beneish M-Score > −2.22 → eligible pool
  Step 3 (Composite ranking):
    Path A: F-Score binary 9-component + V/P ranking → quintile
            intersection (top quintile both)
    Path B: GP/A continuous rank + V/P continuous rank → top-150
            combined rank product (Fortune 500 paterni)
  Step 4 (Long portfolio): eligible ∩ (Path A ∪ Path B) top 50-100
  Step 5 (Overlay): long-only UMD top 30% momentum tilt
  Step 6 (Risk constraints): equal-weight veya market-cap-weight;
                              sektör concentration cap (max 25% any
                              GICS Level-1)
  Step 7 (Rebalance): annual June; 4-month accounting lag
  Step 8 (Reporting): DSR + alpha vs q5 model + decay-adjusted spread
                      üçlü
```

**Anchor empirik kanıt**:
- [[papers/li_mohanram2019_quality_value]] F&V/P modern all-firms
  +11.92% spread (1973-2012)
- [[papers/novy_marx_2013_gross_profitability]] Fortune 500 GP/V
  combined 0.62%/ay Sharpe 0.74 (1963-2010)
- [[papers/israel_moskowitz_2013_shorting_size_time]] long-only U
  α=5.55% t=6.74 IR 0.73 (1927-2011)

### 1.E Expected Performance (decay-adjusted)

> ⚠️ **Backtest çalıştırılmadı**; aşağıdaki rakamlar literatür rakamlarının
> decay-adjusted projeksiyonu, **somut backtest çıktısı değil**.

| Bileşen | In-sample | Decay-adjusted (×0.65) | Caveat |
|---------|-----------|--------------------------|--------|
| F & V/P combined | +11.92%/yıl ([[papers/li_mohanram2019_quality_value]]) | ~7.7%/yıl | post-2012 modern data eksik |
| GP × V/P Fortune 500 | +7.4%/yıl Sharpe 0.74 ([[papers/novy_marx_2013_gross_profitability]]) | ~4.8%/yıl | post-2010 out-of-sample |
| Long-only UMD overlay | +5.55% IR 0.73 ([[papers/israel_moskowitz_2013_shorting_size_time]]) | ~3.6%/yıl | aylık-orijinal annual uyarlama Q33 |
| Sloan Oa filter (q-factor alpha) | -0.54%/ay sig short | (negatif accrual screen-out) | 4/4 hayatta kalan |
| **TOPLAM baseline range** | — | **~6-10%/yıl** (muhafazakâr; alt sınır limited arbitrage Tablo 8 worst-case + üst sınır Fortune 500 GP/V optimist) | DSR-corrected daha düşük; modern data eksik |

> 📝 **Cycle 24 lint_pass revize**: range %8-12 → **%6-10** indirildi.
> Gerekçe: McLean-Pontiff aggregate %35 decay multiplier yetmez —
> [[papers/mclean_pontiff_2016_post_publication_decay]] [Tablo 8]
> limited arbitrage büyük/likit firmalarda decay agresif (size +1.442
> sig 1%; dollar volume +1.380 sig 1%); S&P 500 Q5 NYSE-breakpoint
> üst yarısı bu profil. **Çift darbe**: aggregate %35 + large-cap
> additional decay → ×0.50 NDX agresif sensitivity'ye yakın. Faz 3
> backtest sonuçları over-promise riski; muhafazakâr alt sınır.

### 1.F Known Weaknesses (S&P 500 v0)

1. Modern data eksik (Chen-Zimmermann 2022 + JKP 2023 Faz 2 sonu
   ingest); post-2010 sample out-of-sample
2. Composite scores McLean-Pontiff sample'da explicit listed değil
   ([[meta/data_gaps]] Cycle 11); aggregate %35 multiplier proxy
3. Fortune 500 strategy 1963-2010 sample sonu; FAANG era (2011-2024)
   out-of-sample
4. **Monthly-orijinal annual-uyarlama primum kaybı sensitivity test
   edilmedi (Q35 + Q51 + Q57)** — QMJ + UMD + Novy-Marx GP/A hepsi
   monthly rebalance orijinal; wiki yıllık. **Faz 3 backtest
   implementation'ın ilk sensitivity test'i bu olmalı.** Annual
   uyarlama: turnover dramatik düşer ama momentum decay yıl-içi (UMD
   crashes) + QMJ z-score güncelleme frekansı + GP/A persistence
   trade-off'ları empirik test edilmemiş; literatürde sistematik
   karşılaştırma sadece Novy-Marx [Appendix A.4] (annual vs quarterly
   GP/A; daha güçlü monthly returns ama turnover yüksek).
5. Q14 RMW/CMA large-cap-only direct test eksik (Israel-Moskowitz
   HML-spesifik fully-answered)
6. Beneish M-Score sample küçük-cap-tilted (Q46); large-cap
   kalibrasyon gerekli

---

## 2. STRATEGY 2 — Nasdaq 100 v0

### 2.A Universe & Sample

- **Universe**: Nasdaq 100 üyesi top 100 non-financial Nasdaq-listed
  stocks (FAANG-dominant, growth/intangibles-yoğun); index reconstitution
  rules quarterly
- **Wiki amaç evrenleri map'i**: NDX top 100 ≈ Israel-Moskowitz size
  Q5 üst yarısı (largest 20% NYSE breakpoint); FAANG profile
  ([[papers/mclean_pontiff_2016_post_publication_decay]] [Tablo 8]
  limited arbitrage büyük/likit/divid-payer/düşük-idio profilinin
  ucu)
- **Sample dönemi**: NDX yapısal genişleme 1985'ten itibaren; modern
  data 2000-2024 hedef; post-2014 FAANG era out-of-sample sensitivity

### 2.B Factor Inclusion (dört darbe filter sonrası, NDX-spesifik)

**NDX CORE composite**:
- **G & V/P combined** ([[papers/li_mohanram2019_quality_value]]
  +21.45% spread; en yüksek combined hedge; binary intersection)
  veya **G & NEGPEG growth** (+20.07%; low-BM subsample)
- **G-Score industry-median** ([[factors/G_Score]]; tech-heavy
  evrende kalibre [[papers/mohanram2005_g_score]] [Tablo 5 Panel D]
  hi-tech subgroup +17.8% + NASDAQ partition +26.4%)
- **QMJ continuous z-score** ([[factors/QMJ]]; large-cap quality
  ANCHOR Q2 fully-answered; QARP framework Section 7 paralel
  [[papers/asness_frazzini_pedersen_2019_qmj]])
- **GP/A standalone** ([[factors/Gross_Profitability]] Cycle 23 yeni;
  NDX FAANG firmalar yüksek GP/A; numerator intangibles-aware
  R&D ARÎ avantaj)

**Filter katmanı**:
- **Beneish M-Score conservative** ([[factors/M_Score]]; cutoff −2.84
  `.01` NDX agresif; tech firma high SGI false positive Q47 paralel)

**Overlay**:
- **R&D-to-market (Rdm)** ([[concepts/intangibles_adjusted_accounting]];
  q-factor alpha 0.7%/ay sig; 4/4 hayatta kalan; NDX-spesifik kritik
  signal)
- **Organization Capital (OC) factor signal** ⭐ **Cycle 25 yeni**:
  [[factors/Organization_Capital]] industry-relative within FF17
  spread 4.8%/yıl Sharpe 0.58 + FF3 α 5.5% sig + Carhart α 3.9% sig
  1% (1970-2008); high OC firms NDX FAANG profile birebir match
  (low PP&E/AT + growth-tilted + low leverage); F bloğu **4. ayak
  factor portfolio direct evidence** ([[papers/eisfeldt_papanikolaou_2013_organization_capital]])
- **F bloğu intangibles-aware Bm rebuild** (4-katmanlı methodology
  hierarchy, Cycle 25 sertleştirme): Lev-Sougiannis perpetual
  inventory R&D capital + Peters-Taylor θ=30% organization capital
  veya Eisfeldt-Papanikolaou full SG&A (Q60 horse race) + Compustat
  external intangibles; vanilla HML reject + adjusted HML baseline
  ([[papers/lev_srivastava_2020_value_failure]] anchor)

**REJECT** (S&P 500 ile aynı + NDX-spesifik):
- Vanilla HML (Lev-Srivastava 2010s NEGATIVE; Israel-Moskowitz size-conditional)
- SMB vanilla (Q11 fully-answered)
- F-Score standalone large-cap (BM-Q5 kalibre; NDX growth-tilted)
- RMW Ope (HXZ q-factor INSIG)

### 2.C Methodology (NDX-spesifik)

S&P 500 ile aynı core ([[methodology/backtest_spec]] §1-9) + NDX
spesifik ek:

| Methodology ek | Spec | Anchor |
|----------------|------|--------|
| Decay multiplier | ×0.50 NDX agresif sensitivity (limited arbitrage) | [[papers/mclean_pontiff_2016_post_publication_decay]] [Tablo 8] (§4.2 Q29) |
| Adjusted Bm rebuild | R&D capital + organization capital + external intangibles | [[concepts/intangibles_adjusted_accounting]] 4 ayak hierarchy (§6) |
| Industry classification | GICS Level-2/3 mapping (NDX 11 GICS sektör; tech subset 70%+) | (§6.6 Q38) |
| Forensic filter | M-Score `.01` conservative | (§5.4 Q47) |

### 2.D Strategy Architecture

```
NDX strategy v0:
  Step 1 (Universe): NDX top 100 non-financial
  Step 2 (Adjusted Bm rebuild): R&D + org capital + external intangibles
                                  → adjusted V/P ratio per stock
  Step 3 (Forensic filter): Beneish M-Score > −2.84 (conservative
                            tech) → eligible pool
  Step 4 (Composite ranking):
    Path A: G-Score binary 8-component industry-median + adjusted V/P
            ranking → quintile intersection (top quintile both)
    Path B: G & NEGPEG (low-BM subsample alternative)
    Path C: QMJ 4-dimension z-score + QARP (Asness continuous)
  Step 5 (Long portfolio): eligible ∩ (Path A ∪ Path C) top 25-40
  Step 6 (Overlay): R&D-to-market top 30% tilt (intangibles-aware
                    NDX-spesifik signal)
  Step 7 (Risk constraints): equal-weight; sektör concentration cap
                              max 40% any GICS Level-2 (NDX'in tech
                              concentration izin verilmeli ama
                              Information Tech 70% cap)
  Step 8 (Rebalance): annual June; 4-month accounting lag
  Step 9 (Reporting): DSR + alpha vs q5 + decay-adjusted ×0.50 NDX
                      agresif
```

**Anchor empirik kanıt**:
- [[papers/li_mohanram2019_quality_value]] G & V/P combined +21.45%
  spread (en yüksek wiki ingested; 1973-2012)
- [[papers/li_mohanram2019_quality_value]] G & NEGPEG +20.07% (low-BM
  subsample)
- [[papers/mohanram2005_g_score]] NASDAQ partition +26.4% (1979-1999;
  post-2000 FAANG out-of-sample)
- [[papers/asness_frazzini_pedersen_2019_qmj]] [Tablo A4 + Fig A1]
  large-cap-only QMJ 4-factor alpha 66 bps/ay t=11.20
- [[papers/lev_srivastava_2020_value_failure]] adjusted HML 39 yılın
  34'ünde conventional'ı geçer
- [[papers/lev_sougiannis_1996_rd_capitalization]] R&D capital 4.57%
  yıllık subsequent return (RDC-yoğun firmalar)
- [[papers/peters_taylor_2017_intangible_capital]] q^tot proxy
  ρ² +21% standard q'dan üstün

### 2.E Expected Performance (decay-adjusted, NDX-agresif)

> ⚠️ **Backtest çalıştırılmadı**; aşağıdaki rakamlar literatür
> rakamlarının NDX-agresif decay-adjusted (×0.50) projeksiyonu.

| Bileşen | In-sample | Decay-adjusted (×0.50 NDX) | Caveat |
|---------|-----------|------------------------------|--------|
| G & V/P combined | +21.45%/yıl | ~10.7%/yıl | post-2012 modern data + NDX limited arbitrage |
| G & NEGPEG growth | +20.07%/yıl | ~10.0%/yıl | low-BM subsample-spesifik |
| QMJ 4-factor alpha | 0.66%/ay × 12 = ~7.9%/yıl | ~4.0%/yıl | annual uyarlama Q35 |
| Adjusted HML (intangibles-aware) | conventional + ek | conventional decay'i absorb | F bloğu modern replikasyon eksik |
| R&D-to-market overlay | 0.7%/ay × 12 = ~8.4%/yıl | ~4.2%/yıl | 4/4 hayatta kalan |
| **TOPLAM baseline range** | — | **~8-13%/yıl** (muhafazakâr; alt sınır Mohanram 1979-1999 sample post-2000 out-of-sample + intangibles-aware revize Q56 açık caveat + üst sınır G&V/P ×0.50 NDX agresif) | DSR-corrected daha düşük |

> 📝 **Cycle 24 lint_pass revize**: range %10-15 → **%8-13** indirildi.
> Gerekçe: (a) [[papers/mohanram2005_g_score]] sample 1979-1999;
> post-2000 FAANG era 25 yıl out-of-sample (Q3 partial-stronger ama
> tam cevap modern data ile); (b) intangibles-aware Bm rebuild Q56
> formal implementation eksik — adjusted HML methodology Faz 3
> finalize edilene kadar literatür baseline'ı **proxy**; (c)
> [[papers/mclean_pontiff_2016_post_publication_decay]] [Tablo 8]
> NDX FAANG profil limited arbitrage uç ucu → ×0.50 multiplier
> agresif ama composite proxy (Q5 partial). Faz 3 backtest sonuçları
> over-promise riski; muhafazakâr alt sınır.

### 2.F Known Weaknesses (NDX v0)

1. NDX 100-stock sample küçük; portfolio diversification limit (top
   25-40 stocks zorunlu)
2. Tech concentration extreme (Information Tech 60-70% NDX); sektör
   neutralization NDX amacıyla çelişir (NDX zaten tech-tilted)
3. Mohanram G-Score sample 1979-1999; FAANG era (2008-2024) post-2000
   out-of-sample (Q3 partial; modern data eksik)
4. **Monthly-orijinal annual-uyarlama primum kaybı sensitivity test
   edilmedi (Q35 + Q51 + Q57)** — QMJ + UMD + Novy-Marx GP/A hepsi
   monthly rebalance orijinal; wiki yıllık. **Faz 3 backtest
   implementation'ın ilk sensitivity test'i bu olmalı.** NDX için
   ek caveat: monthly G-Score (Mohanram orijinal annual; uyarlama
   yok ama industry-median rebalance frekansı sektör compositional
   shift altında etki edebilir).
5. Intangibles-aware Bm rebuild methodology Faz 3 implementation eksik
   (Q56 yeni Cycle 23)
6. R&D-to-market formal tanımı stock vs flow methodology farkı
   ([[papers/lev_sougiannis_1996_rd_capitalization]] [s.133 fn 22] Q39)
7. NDX 100-spesifik direct fundamental composite scoring test wiki'de
   YOK ([[meta/data_gaps]] Cycle 5 priori boşluğu); Mohanram Tablo 5
   "hi-tech subgroup" + "NASDAQ partition" proxy
8. QMJ post-2012 modern replikasyonu eksik (Q51)
9. Beneish M-Score tech firma false positive (high SGI/AQI; Q47)

---

## 3. EXPECTED PERFORMANCE — İki Strategy Karşılaştırma Özeti

| Metrik | S&P 500 v0 | NDX v0 |
|--------|-----------|--------|
| Anchor compositesi | F&V/P + GP/V Fortune 500 | G&V/P + QMJ + R&D-to-market |
| In-sample literatür baseline | ~12-22% | ~20-26% |
| Decay-adjusted (standard ×0.65) | ~7.7%/yıl (F&V/P) + GP/V ek | n/a (NDX ×0.50) |
| Decay-adjusted (NDX ×0.50 stress) | n/a | ~10-15% |
| **Baseline range hedef (Cycle 24 muhafazakâr revize)** | **~6-10%/yıl** | **~8-13%/yıl** |
| Forensic filter | Beneish .025 | Beneish .01 conservative |
| Overlay | Long-only UMD | R&D-to-market + adjusted Bm |
| Implementation karmaşıklığı | Standart fundamental + screen | F bloğu 4 ayak intangibles-aware (yüksek) |
| Modern data ihtiyacı | Orta (post-2010) | Yüksek (post-2012 FAANG era + intangibles) |

**Wiki için pratik sıralama**: S&P 500 strategy v0 daha **tahmini hazır**
(literatür baseline güçlü + methodology standart); NDX strategy v0
**implementation infrastructure beklemede** (F bloğu 4 ayak intangibles-aware
methodology Faz 3'te formalize edilmeli).

---

## 4. KNOWN WEAKNESSES (cross-strategy genel)

> 📝 [[methodology/backtest_spec]] §10 mevcut + bu sayfada genişletildi.
> Faz 3'te ayrı `wiki/strategies/known_weaknesses.md` açılır.

1. **Modern data eksik** (Chen-Zimmermann 2022 + JKP 2023 Faz 2 sonu
   ingest); post-2014 dönem out-of-sample tüm strategy'ler için
2. **E bloğu (large-cap reality)** Cycle 22 sertleştirme; **Fama-French
   2008 "Dissecting Anomalies"** hala eksik (Tier 1 paywall →
   preprint), Q14 CMA/RMW direct test partial
3. **Profitability zinciri 4. halka Ball-GLN 2016 paper sayfası eksik**
   (Tier 1 #9 ingest edilmedi); Cop methodology origin standalone
   paper sayfası açılmadı
4. **Intangibles-aware GP/A** (Q56) — F bloğu + Profitability zinciri
   entegrasyonu Faz 3 implementation eksik
5. **Lakonishok-Shleifer-Vishny 1994** (Tier 1 #7) value premium
   contrarian hipotezinin ana kaynağı — wiki'de paper sayfası yok
6. **Faktor-spesifik decay literatür eksik**: McLean-Pontiff aggregate
   %35 multiplier composite scores (F-Score, G-Score, QMJ, GP/A)
   için **proxy**, doğrudan kanıt değil
7. **Annual uyarlama UMD/QMJ aylık-orijinal sensitivity** (Q33+Q35+Q57)
   — backtest implementation sensitivity test gerekli
8. **Frazzini-Israel-Moskowitz 2018** firm-level trading cost analysis
   (Tier 3 #52, paywall) — annual rebalance turnover/cost trade-off
   modern empirik kanıt eksik
9. **HXZ 2015 q-factor origin paper** (Tier 1 #3) — q-factor methodology
   formal tanımı paper sayfası yok; HMXZ 2020 Security Analysis +
   HXZ 2020 Replicating Anomalies kullanılan q5 model'in **origin
   formal tanımı eksik**
10. **Buffett-tipi alpha discretionary** ([[papers/hou_mo_xue_zhang_2020_security_analysis]]
    q5 alpha 0.77% t=2.69) — wiki strategy hedeflememeli, achievable
    değil; bu skill-based residual sistematik strategy beyond

---

## 5. NEXT STEPS (Faz 2-3 yol haritası)

> 📝 **Cycle 24 lint_pass revize**: yol haritası FGX 2020 öncelik
> yükseltildi (Cycle 28 → Cycle 26); GKX 2020 + KNS 2020 atlanmış.
> Gerekçe: FGX Q55 (GP/A vs RMW Ope vs QMJ GPOA vs Cop horse race)
> tam cevap için **acil**; v0_draft Profitability seçimini doğrulama
> için kritik. GKX ve KNS wiki proje amacı (sistematik fundamental
> factor strategy) için marjinal — atlama kararı [[meta/handoff_faz3]]
> Faz 2 sonu açılışında not düşülecek.

### Cycle 25 — Eisfeldt-Papanikolaou 2013 ingest (Q41 4-way horse race)

- F bloğu kompleman: organization capital factor portfolio direct
  evidence (Lev-Sougiannis + Peters-Taylor + Lev-Srivastava + Eisfeldt-
  Papanikolaou 4-way comparison)
- NDX strategy v0 §2.B intangibles-aware overlay sertleştirme
  ([[concepts/intangibles_adjusted_accounting]] Faz 3 design decision
  Q41)

### Cycle 26 — Feng-Giglio-Xiu 2020 ingest ⭐ ÖNCELIK YÜKSELTILDİ

- Tier 1 #21 ingest; **Q55 (GP/A vs RMW Ope vs QMJ GPOA vs Cop horse
  race) tam cevap için zorunlu**
- Redundancy testing methodology origin; v0_draft §1.B + §2.B
  Profitability factor seçimini empirik validation
- "Taming the Factor Zoo" — factor zoo redundancy formal framework;
  [[concepts/factor_zoo]] sertleştirme

### Cycle 27 — JKP 2023 ingest (modern replication paper-form)

- Tier 2 #44 ingest; ML-aware framework + global data + 153 anomaly
  modern test
- HXZ 2020 Replicating Anomalies modern güncelleme; post-2014 dönem
  kanıt
- v0_draft modern replication ön koşul (S&P 500 + NDX baseline range
  modern data ile sertleştirme)

### Cycle 28 — §11.5 ZORUNLU 4-cycle ardışık consolidation pass + v0 → v1 revize hazırlık

- Cycle pattern: 4/8/12/16/20/24/**28** ardışık zorunlu (Cycle 25-27
  ingest sonrası)
- 5 derin denetim adımı + v0_draft → v1 revize hazırlık (FGX + JKP +
  Eisfeldt-Papanikolaou birikim sentezi)
- Faz 2 sertifika kriteri ön değerlendirme

### Cycle 29 — methodology/data_sources.md açma

- Chen-Zimmermann 2022 Open Asset Pricing data portalı pointer
  (paper değil, **veri portalı**)
- JKP 2023 code repository pointer
- Faz 3 backtest implementation ön koşul: replikasyon database +
  ML-aware framework infrastructure
- methodology/ klasörünün ikinci sayfası (backtest_spec sonrası)

### Cycle 30 — v1 revize draft

- v0_draft → v1 (FGX + JKP + Eisfeldt-Papanikolaou ingest birikimi
  sonrası empirik validation)
- Cycle 24'te muhafazakâr range (S&P 500 ~6-10% + NDX ~8-13%) modern
  data ile re-evaluate
- Profitability seçimi (GP/A vs Cop) FGX redundancy test sonrası
  finalize

### Cycle 31+ — Faz 2 sertifika değerlendirmesi + Faz 3 geçiş hazırlık

- v1 revize sonrası **Faz 2 sertifika önerisi** (TAM/YUMUŞAK)
- [[meta/handoff_faz3]] açma (Faz 2 sonu, Faz 3 başlangıcı)
- Faz 3: `s&p500_v1.md` + `nasdaq100_v1.md` formal spec'ler

### ATLANAN PAPERLAR (Cycle 24 lint_pass kararı)

- **Gu-Kelly-Xiu 2020** (Tier 1 #20) — wiki proje amacı için marjinal;
  ML feature explosion caveat ([[concepts/factor_zoo]] decay perspective);
  Q6 (top importance feature'lar) FGX redundancy test ile dolaylı kapanır
- **Kozak-Nagel-Santosh 2020** (Tier 1 #22) — SDF estimation methodology;
  sistematik strategy için dolaylı

Bu iki atlama kararı **handoff_faz3.md** açıldığında not düşülecek
(Cycle 31+; Faz 2 sertifika sonrası).

### Faz 2 sertifika kriteri ([[meta/handoff_faz2]] §3 referansla)

- methodology/backtest_spec.md açıldı ✓ (Cycle 21)
- Aday strategy draft (v0_draft.md) açıldı ✓ (Cycle 24)
- E bloğu Israel-Moskowitz ingest ✓ (Cycle 22); **FF 2008 hala eksik**
  (Faz 2 sonu paywall→preprint)
- Tier 2/3 seçici ingest (Novy-Marx ✓ Cycle 23; Eisfeldt-Papanikolaou
  Cycle 25; FGX Cycle 26; **Frankel-Lee 1998 paywall hala**)
- Modern replication (JKP 2023 Cycle 27; Chen-Zimmermann 2022 portal
  Cycle 29)

---

## İlgili Sayfalar

### Methodology
- [[methodology/backtest_spec]] — bu strategy taslağının ön koşulu;
  tüm methodology kararları §1-9 referansla

### Faz 1 sentez backbone
- [[meta/handoff_faz2]] — Faz 1 → Faz 2 geçiş; YUMUŞAK sertifika
- [[concepts/post_publication_decay]] — dört darbe çerçevesi sentez
  tablosu (Profitability zinciri 4 satır + Sloan zinciri paralel)
- [[concepts/multiple_testing]] — HLZ MT cutoff
- [[concepts/anomaly_replication]] — HXZ NYSE-VW + Israel-Moskowitz
  erken anchor
- [[concepts/intangibles_adjusted_accounting]] — F bloğu 4-katmanlı
  methodology hierarchy

### Anchor papers (Faz 3 v1 spec'leri için)
- [[papers/li_mohanram2019_quality_value]] — F&V/P + G&V/P combined
  modern replikasyon
- [[papers/novy_marx_2013_gross_profitability]] — Fortune 500 GP/V
  S&P 500 birebir empirik anchor
- [[papers/israel_moskowitz_2013_shorting_size_time]] — long-only
  retail-style 86-yıl decomposition
- [[papers/asness_frazzini_pedersen_2019_qmj]] — QMJ + QARP NDX large-cap
- [[papers/lev_srivastava_2020_value_failure]] — adjusted HML methodology
- [[papers/mohanram2005_g_score]] — NDX hi-tech + NASDAQ partition
- [[papers/beneish_1999_m_score]] — forensic filter

### Meta
- [[meta/open_questions]] — 58 Q (5 fully-answered + Q49 partial-stronger
  + Q52-Q58 Cycle 22-23 yeni)
- [[meta/data_gaps]] — Cycle 22 + Cycle 23 sonrası bölümler; v0_draft
  Faz 2-3 ön koşulları konsolide

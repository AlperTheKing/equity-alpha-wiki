---
type: strategy_draft
version: v1
opened: 2026-05-02
phase: faz_2_cycle_30
status: historic
historic_since: 2026-05-02
historic_cycle: 34
superseded_by: [strategies/sp500_v1, strategies/nasdaq100_v1, strategies/known_weaknesses]
strategies: [s&p500_v1, nasdaq100_v1]
basis: 24_papers_16_concepts_15_factors_2_methodology
backtest_run: false
purpose: "Faz 2 v0_draft → v1_draft evrim revize (Cycle 25-29 ingest birikim entegrasyonu); Faz 3 v1 formal spec'lerinin (s&p500_v1.md + nasdaq100_v1.md) ön formu"
predecessor: strategies/v0_draft (Cycle 24 historic)
revisions:
  - cycle_25: F bloğu 4-katmanlı + Q41 fully-answered (Eisfeldt-Papanikolaou OC factor portfolio)
  - cycle_26: Q55 + Q7 fully-answered + Profitability seçim doğrulandı (FGX 2020 DS LASSO)
  - cycle_27: Q63 fully-answered + 3. contradictions entry + conservative vs anti-conservative iki kutup (JKP 2023 Bayesian)
  - cycle_28_consolidation: 7 stale claim fix + §11.5 ardışık + v1 hazırlık raporu
  - cycle_29: methodology/data_sources.md + Modern data eksik tam kapanma
  - cycle_34_historic_transition: Faz 3 üç formal spec sonrası historic'e geçiş (sp500_v1 + nasdaq100_v1 + known_weaknesses synthesis fonksiyonunu absorb; v0_draft Cycle 30 paterni paralel)
---

# strategies/v1_draft — İki Strategy Aday v1 Revize (HISTORIC)

> ⚠️ **HISTORIC KAYIT (Cycle 34 itibariyle).** Bu doküman Cycle 30
> Faz 2 ikinci dönüm noktası strategy revize operasyonunun historic
> kaydı. Cycle 32 sp500_v1 + Cycle 33 nasdaq100_v1 + Cycle 34
> known_weaknesses üç formal spec sonrası v1_draft synthesis
> fonksiyonu absorb edildi; v0_draft Cycle 30 paterni paralel
> historic preservation. **Superseded by**: [[strategies/sp500_v1]] +
> [[strategies/nasdaq100_v1]] + [[strategies/known_weaknesses]] üçlü
> sister spec. Content **DEĞİŞTİRİLMEZ** (historic preservation kuralı
> CLAUDE.md §7 + §9; cycle evrim notu + 6 revize gerekçesi + 24 paper
> anchor synthesis referans değer korunur).

> 📝 **Cycle 30 ilk strategy revize.** v0_draft (Cycle 24 ✓) →
> v1_draft (Cycle 30 ✓) evrim Faz 2 yapısal devam. Wiki için ikinci
> dönüm noktası operasyonu (Cycle 24 v0 açma birincisi). v0 historic
> preservation korundu ([[strategies/v0_draft]]); v1 active draft
> (Cycle 34 itibariyle historic'e geçti — yukarıdaki uyarı bloğu).
>
> 📝 **§1 (S&P 500 v1) için formal spec extension** (Cycle 32 ✓):
> [[strategies/sp500_v1]] — OPERASYONEL spec (input/output/methodology/
> factor weights/rebalance protocol/reporting). v1_draft synthesis
> ("niye" sorularına cevap: cycle evrim notu + 6 revize gerekçesi +
> 24 paper anchor) + sp500_v1 formal spec ("ne yapılacak").
>
> 📝 **§2 (NDX v1) için formal spec extension** (Cycle 33 ✓):
> [[strategies/nasdaq100_v1]] — NDX-spesifik OPERASYONEL spec
> (5-theme FAANG profile + F bloğu 4-katmanlı CORE infrastructure +
> capped VW ZORUNLU mega-cap kontrolü + Beneish `.01` conservative +
> ×0.50 NDX agresif decay + Q60 horse race iki sensitivity test).
> v1_draft synthesis status değerlendirme: **artık her iki strategy
> için formal spec extension var** (sp500_v1 + nasdaq100_v1); Cycle
> 34 known_weaknesses cross-strategy formalize sonrası v1_draft
> historic'e geçer mi karar (Cycle 30 v0_draft → historic preservation
> paterni paralel; v1_draft synthesis predecessor olarak korunur).

> ⚠️ **Bu taslak [[methodology/backtest_spec]] §1-10 + [[methodology/data_sources]]
> §1-7 + Faz 1 sentez backbone (5 priori Q + 5 blok kapanış sentezi
> + 4/4 hayatta kalan + 3-4/4 baseline composite + Sloan zinciri +
> Profitability zinciri + F bloğu 4-katmanlı + 3 paralel statistical
> methodology aile + 3. contradictions entry resolution) üzerine
> inşa edilir. Her tasarım kararı **wikilink atıflı** (CLAUDE.md §6.1).

---

## 0. v0_draft → v1_draft Evrim Notu

**Predecessor**: [[strategies/v0_draft]] historic kayıt (Cycle 24
açıldı; Cycle 25-29 ek note'larla zenginleşti; Cycle 30 itibariyle
HISTORIC).

**v1_draft revize cycle'ları** (Cycle 28 hazırlık raporu uyarınca):

| Cycle | Operasyon | v1 etki |
|-------|-----------|---------|
| 25 | Eisfeldt-Papanikolaou 2013 ingest | F bloğu 4-katmanlı + OC factor portfolio direct evidence (NDX §2.B overlay anchor) + Q41 fully-answered |
| 26 | FGX 2020 ingest | Q55 + Q7 fully-answered; Profitability seçim FGX DS-sig validation; D bloğu statistical bacağı 2 paper sertleştirme; methodology §1.C + §2.C üç paralel statistical methodology aile |
| 27 | JKP 2023 ingest | Q63 fully-answered; **3. contradictions entry** (HXZ ↔ JKP); conservative vs anti-conservative iki kutup; 13 theme cluster + tangency portfolio multi-theme allocation; capped VW methodology |
| 28 | §11.5 consolidation + 7 stale fix + v1 hazırlık | F bloğu 3→4 katmanlı + factor zoo 3→4 paper homojen; v1 hazırlık raporu (6 ana revize) |
| 29 | methodology/data_sources.md | Modern data eksik weakness Cycle 27 partial → Cycle 29 TAM KAPANMA; üç paralel data kaynağı (Chen-Zimmermann + JKP code repository + WRDS) |

**v1 ana yenilikler** (v0'dan 6 ana fark):
- **§1.A + §2.A**: Modern data anchor + capped VW methodology + [[methodology/data_sources]] pointer
- **§1.B + §2.B**: Theme diversification yapısı (10/13 themes JKP tangency portfolio sig+ multi-theme allocation framework); F bloğu 4-katmanlı OC factor portfolio
- **§1.C + §2.C**: Üç paralel statistical methodology (HLZ + FGX + JKP) + üç alternative weighting (pure VW + FF half-weight + capped VW) + reporting iki ayrı metric
- **§1.E + §2.E**: Conservative baseline KORUNUR + JKP %85 anti-conservative upper bound sensitivity reference EKLENDI
- **§1.F + §2.F**: Modern data eksik weakness TAM KAPANDI; eksik kalanlar listesi güncel; **3. contradictions entry resolution YENİ madde**
- **§5**: Cycle 25-29 ✓; Cycle 30 ✓ (bu cycle); Cycle 31 Faz 2 sertifika + handoff_faz3; Cycle 32+ Faz 3 başlangıç

---

## 1. STRATEGY 1 — S&P 500 v1

### 1.A Universe & Sample (REVİZE Cycle 30)

- **Universe**: S&P 500 üyesi top 500 US stocks (NYSE-VW NYSE-breakpoint
  konvansiyonuna doğal yakın); ex-financials caveat (SIC 1-digit 6
  hariç, [[papers/novy_marx_2013_gross_profitability]] [s.10] paterni)
- **Wiki amaç evrenleri map'i**: S&P 500 ≈ Israel-Moskowitz size Q4-Q5
  spektrumu ([[papers/israel_moskowitz_2013_shorting_size_time]] Q5
  avg 36B 2011 + Q4 avg 4.8B Russell Midcap; Fortune 500 = top 500
  non-fin ≈ S&P 500 üst yarısı — [[papers/novy_marx_2013_gross_profitability]]
  [Tablo 7] direct empirik anchor)
- **Sample dönemi (Cycle 27 + 29 modern data anchor)**:
  - **Modern data infrastructure tam erişilebilir** ([[methodology/data_sources]]
    §1-3): Chen-Zimmermann 2022 Open Asset Pricing Database (pure
    replication ~100%) + JKP 2023 GlobalFactor code repository
    (Bayesian Empirical Bayes %85) + WRDS open-source access (CRSP +
    Compustat raw feed) **üç paralel data kaynağı**
  - **JKP 2023 anchor sample**: US 1926+ Global 1986+ Dec 2020;
    post-2014 → 2014-2020 **6 yıl modern dönem kanıt**
  - **Post-2020 (FAANG/AI 2021-2024) hala out-of-sample**;
    Chen-Zimmermann database update + Faz 3 custom modern replikasyon
    ile tam kapanma
  - Hedef sample window: **1980-2024** (post-1980 modern accounting
    period; 1980-2014 in-sample anchor + 2014-2020 modern dönem JKP
    sertleştirme + 2021-2024 post-2020 OOS sensitivity)
- **Capped value-weighting (NYSE 80th percentile winsorize)**
  ([[methodology/backtest_spec]] §1.3 + [[methodology/data_sources]]
  §5; Cycle 27 ek): mega-cap (Apple/Microsoft S&P 500 ~%7-8)
  concentration distortion kontrolü; Faz 3 implementation tercih aday

### 1.B Factor Inclusion (REVİZE Cycle 30 — theme diversification)

[[methodology/backtest_spec]] §4 dört darbe pipeline + §5 factor
inclusion list referansla:

**S&P 500 CORE composite** (v0'dan korunur, FGX validation):
- **F & V/P combined** ([[papers/li_mohanram2019_quality_value]] modern
  all-firms +11.92% spread; binary intersection) **+** **GP × V/P
  Fortune 500 rank-based** ([[papers/novy_marx_2013_gross_profitability]]
  [Tablo 7] 0.62%/ay Sharpe 0.74; continuous rank product)
- **İki operationalization paralel** (QARP framework Q50 paralel):
  binary intersection vs continuous rank product
- **FGX DS LASSO validation güçlü** (Cycle 26): RMW + ROE + QMJ DS-sig

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
  0.69%/ay sig; Profitability zinciri 4. halka; [[factors/Gross_Profitability]]
  cross-link)
- **Earnings announcement Abr** event-driven complement (q-factor
  alpha 0.66%/ay sig)

**REJECT** (v0'dan korunur):
- Vanilla HML standalone (Israel-Moskowitz size Q4-Q5 INSIG +
  Lev-Srivastava post-2010 collapse çift anchor)
- SMB vanilla (Q11 fully-answered ASTERISK)
- F-Score standalone large-cap (BM-Q5 only kalibre)
- Magic Formula (q5 captures + microcap residual)
- RMW Ope (HXZ q-factor alpha 0.04% t=0.42 INSIG; Cycle 26 FGX
  DS-sig methodology farkı dokümante [[factors/RMW]]; QMJ Profitability
  composite tercih)

#### 1.B.1 Theme Diversification Yapısı (YENİ Cycle 30 — JKP tangency portfolio multi-theme allocation)

[[papers/jensen_kelly_pedersen_2023_replication_crisis]] (Cycle 27)
13 theme cluster + tangency portfolio multi-theme allocation framework:
10/13 themes tangency portfolio sig+; 3 displaced (profitability +
investment + size) joint modeling redundancy.

**S&P 500 v1 theme allocation** (10/13 universal'den **7 dominant**):

| Theme | Wiki anchor | S&P 500 v1 weight |
|-------|-------------|--------------------|
| **Quality** | [[factors/QMJ]] (Cycle 19 Q2 fully-answered) | Yüksek (composite + 4 dimension) |
| **Profitability** | [[factors/Gross_Profitability]] GP×V/P Fortune 500 (Cycle 23 Q55 fully-answered) | Yüksek (FGX DS-sig + standalone replicate; tangency'de displaced ama factor selection sig) |
| **Profit Growth** | Mohanram G-Score paterni ([[factors/G_Score]]) | Orta (composite içinde) |
| **Value** | Adjusted HML ([[papers/lev_srivastava_2020_value_failure]] Cycle 17 Q1 fully-answered) | Orta (vanilla HML reject sonrası adjusted methodology) |
| **Momentum** | UMD long-only Q5 ([[papers/israel_moskowitz_2013_shorting_size_time]] Cycle 22) | Orta (overlay) |
| **Accruals\*** | Sloan zinciri ([[factors/Accruals]] Cycle 9) | Orta (forensic + signal) |
| **Low risk** | BAB literatür (Frazzini-Pedersen 2013, Tier 3 #51 ingest edilmedi) | Düşük opsiyonel (Faz 3 Tier 3 ingest sonrası) |

**3 displaced theme** (joint modeling redundancy; standalone sig ama
tangency'de düşük katkı):
- Profitability theme **standalone replicate sig** ama tangency
  diğer themes already capture variation
- Investment* theme: CMA + I/A factor exposure paralel; v1'de
  CMA passive exposure
- Size theme: vanilla SMB never sig under MT (Q11); QMJ ASTERISK
  resurrection quality-controlled

### 1.C Methodology (REVİZE Cycle 30 — büyük; 4 yeni satır)

[[methodology/backtest_spec]] §1-9 + [[methodology/data_sources]]
§1-7 referansla:

| Methodology kararı | Spec | Anchor |
|---------------------|------|--------|
| **Universe (REVİZE)** | **Üç alternative weighting**: pure VW (HXZ baseline) + FF half-weight + **capped VW (JKP NYSE 80th percentile winsorize) Faz 3 implementation tercih aday** | [[methodology/backtest_spec]] §1.3 (Cycle 27 sertleştirme); [[meta/contradictions]] §3 |
| Rebalance | Annual June (CLAUDE.md §1) | [[papers/famafrench1993_three_factor]] + [[papers/sloan1996_accruals_anomaly]] + [[papers/novy_marx_2013_gross_profitability]] convention (§2.1) |
| **Performance reporting (YENİ satır)** | DSR + alpha t-stat + decay-adjusted spread üçlü + **YENİ: factor mean return + SDF loading iki ayrı metric** ([[papers/feng_giglio_xiu_2020_factor_zoo]] [s.22] + [[papers/jensen_kelly_pedersen_2023_replication_crisis]]) | [[papers/bailey_lopezdeprado_2014_deflated_sharpe]] (§3.1) |
| **MT cutoff (REVİZE)** | **Üç paralel statistical methodology aile**: HLZ frequentist Bonferroni/BHY (`\|t\| > 3.0` BHY 1%) + FGX frequentist DS LASSO + **JKP Bayesian Empirical Bayes hierarchical** | [[concepts/multiple_testing]] D bloğu 3 paper × üç paralel methodology aile (Cycle 26 + 27 sertleştirme) |
| **Decay multiplier (REVİZE)** | ×0.65 standard (HXZ + MP conservative-side) + **JKP %85 anti-conservative upper bound sensitivity reference** | [[papers/mclean_pontiff_2016_post_publication_decay]] aggregate %35 + [[papers/jensen_kelly_pedersen_2023_replication_crisis]] (§4.2 Cycle 27) |
| Çift düzeltme prensibi | Tek-düzeltme tercih + üç paralel methodology layer factor-level (HLZ + FGX) + strategy-level (DSR) + multi-theme (JKP tangency) | (§3.3 Q37 + Cycle 26 + 27 sertleştirme) |
| **Replication-robust (YENİ satır)** | **HXZ NYSE-VW + JKP Bayesian iki paralel methodology** + 3. contradictions entry resolution dokümante; HXZ + JKP iki-yolu replication-robust filter (factor hayatta kalmak için her iki methodology lens'inde sig tercih edilebilir) | [[meta/contradictions]] §3 (Cycle 27) + [[methodology/backtest_spec]] §4.4 |
| **YENİ: 13 theme cluster + tangency portfolio multi-theme allocation framework** | 10/13 themes sig+ tangency; 3 displaced (profitability, investment, size) joint modeling redundancy; factor selection + theme allocation iki paralel decision | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] (Cycle 27) |

### 1.D Strategy Architecture

```
S&P 500 strategy v1 (theme diversification + capped VW):
  Step 1 (Universe): top 500 US stocks ex-financials; capped VW
                    (NYSE 80th percentile winsorize) Faz 3 baseline
  Step 2 (Forensic filter): Beneish M-Score > −2.22 → eligible pool
  Step 3 (Composite ranking — multi-theme allocation):
    Path A (Quality theme): F-Score binary 9-component +
            QMJ Profitability composite → top quintile both
    Path B (Profitability theme): GP/A continuous rank +
            V/P continuous rank → top-150 combined rank product
            (Fortune 500 paterni)
    Path C (Value theme): Adjusted HML methodology (Lev-Srivastava
            anchor; vanilla HML reject sonrası)
    Path D (Momentum theme): UMD long-only top 30% (Israel-Moskowitz
            Q5 largest)
  Step 4 (Long portfolio): eligible ∩ (Path A ∪ Path B ∪ Path C ∪
                           Path D) top 50-100; 7 theme dominantı
                           weighted allocation
  Step 5 (Replication-robust filter — HXZ + JKP iki-yolu):
    - HXZ NYSE-VW lens'inde sig (q-factor span direct)
    - JKP Bayesian Empirical Bayes lens'inde sig (theme cluster
      tangency portfolio sig+)
  Step 6 (Risk constraints): capped VW + sektör concentration cap
                              max 25% any GICS Level-1
  Step 7 (Rebalance): annual June; 4-month accounting lag
  Step 8 (Reporting — üçlü + iki metric):
    - DSR (Bailey-LdP)
    - Alpha vs q5 model + Carhart 4F
    - Decay-adjusted spread (×0.65 standard + JKP %85 sensitivity)
    - **Factor mean return + SDF loading iki ayrı metric** (FGX +
      JKP framework)
```

**Anchor empirik kanıt (v0'dan korunur)**:
- [[papers/li_mohanram2019_quality_value]] F&V/P modern all-firms
  +11.92% spread (1973-2012)
- [[papers/novy_marx_2013_gross_profitability]] Fortune 500 GP/V
  combined 0.62%/ay Sharpe 0.74 (1963-2010)
- [[papers/israel_moskowitz_2013_shorting_size_time]] long-only U
  α=5.55% t=6.74 IR 0.73 (1927-2011)

**v1 yeni anchor empirik kanıt**:
- [[papers/asness_frazzini_pedersen_2019_qmj]] QMJ Quality theme
  >75% replicate JKP framework (Cycle 27)
- [[papers/jensen_kelly_pedersen_2023_replication_crisis]] 13 theme
  cluster tangency portfolio multi-theme allocation framework
- [[papers/feng_giglio_xiu_2020_factor_zoo]] Profitability ailesi
  DS-sig (RMW + ROE + QMJ; v0 Profitability seçim DOĞRULANDI)

### 1.E Expected Performance (REVİZE Cycle 30 — KORUNUR + EKLENMELI)

> ⚠️ **Backtest çalıştırılmadı**; aşağıdaki rakamlar literatür
> rakamlarının decay-adjusted projeksiyonu, **somut backtest çıktısı
> değil**. v0 conservative baseline KORUNUR (Cycle 24 muhafazakâr
> revize); v1 anti-conservative sensitivity reference EKLENDI.

| Bileşen | In-sample | Conservative ×0.65 (HXZ + MP + FGX) | Anti-conservative JKP %85 (sensitivity) |
|---------|-----------|---------------------------------------|------------------------------------------|
| F & V/P combined | +11.92%/yıl | ~7.7% | ~10.1% |
| GP × V/P Fortune 500 | +7.4%/yıl Sharpe 0.74 | ~4.8% | ~6.3% |
| Long-only UMD overlay | +5.55% IR 0.73 | ~3.6% | ~4.7% |
| Sloan Oa filter | -0.54%/ay sig short | (negatif accrual screen-out) | aynı |
| **TOPLAM baseline range** | — | **~6-10%/yıl** (Cycle 24 muhafazakâr KORUNUR) | **~14-18%/yıl** (anti-conservative upper bound) |

**v1 sensitivity range**: **6-10% conservative ↔ 14-18% anti-conservative
(2x range)** — methodology choice'a aşırı duyarlı (Cycle 27 ~50pp
gap kanıt).

> 📝 **Wiki konservatizm korunur**: baseline range Cycle 24 muhafazakâr
> revize (over-promise riski Cycle 24 karar; HXZ + MP + FGX
> conservative-side); **JKP %85 anti-conservative upper bound
> sensitivity reference olarak EKLENDI** (3. contradictions entry
> resolution; methodology disagreement transparent reporting). Faz 3
> backtest implementation iki kutup arasında **methodology choice
> sensitivity test** (pure VW + FF half-weight + capped VW; HLZ +
> FGX + JKP üç paralel methodology aile).

### 1.F Known Weaknesses (REVİZE Cycle 30 — güncel + 3. contradictions YENİ madde)

1. **Modern data partial → TAM KAPANMA** (Cycle 27 + 29):
   [[methodology/data_sources]] §1-3 üç paralel data kaynağı
   (Chen-Zimmermann 2022 Open Asset Pricing Database pure replication
   ~100% + JKP 2023 GlobalFactor code repository Bayesian Empirical
   Bayes %85 + WRDS open-source access CRSP + Compustat raw feed);
   JKP sample 1926-2020 6 yıl modern dönem 2014-2020 kanıt;
   **post-2020 hala out-of-sample (FAANG/AI 2021-2024)** Faz 3
   custom modern replikasyon ile tam kapanma.

2. Composite scores McLean-Pontiff sample'da explicit listed değil
   ([[meta/data_gaps]] Cycle 11); aggregate %35 multiplier proxy.

3. Fortune 500 strategy 1963-2010 sample sonu; FAANG era (2011-2024)
   out-of-sample.

4. **Monthly-orijinal annual-uyarlama primum kaybı sensitivity test
   edilmedi (Q35 + Q51 + Q57)** — QMJ + UMD + Novy-Marx GP/A hepsi
   monthly rebalance orijinal; wiki yıllık. **Faz 3 backtest
   implementation'ın ilk sensitivity test'i bu olmalı.**

5. Q14 RMW/CMA large-cap-only direct test eksik (Israel-Moskowitz
   HML-spesifik fully-answered).

6. Beneish M-Score sample küçük-cap-tilted (Q46); large-cap
   kalibrasyon gerekli.

7. **YENİ Cycle 30 — 3. contradictions entry resolution acknowledged**:
   HXZ 2020 vs JKP 2023 dramatic methodology disagreement
   ([[meta/contradictions]] §3; ~50pp gap; capped VW + 1-month +
   Bayesian framework methodology choice'lara aşırı duyarlı). Wiki
   **conservative-side baseline** tercih edilir (HXZ + MP + FGX
   ×0.65 / ×0.50 decay multiplier); **anti-conservative-side
   framework** (JKP %85 Bayesian Empirical Bayes hierarchical)
   **varlığı acknowledged**. Faz 3 implementation **methodology
   choice sensitivity test üç alternative** (pure VW + FF half-weight
   + capped VW); factor hayatta kalmak için **HXZ + JKP iki-yolu
   replication-robust filter** (her iki methodology lens'inde sig
   tercih edilebilir, en konservatif standard).

8. **Eksik kalanlar listesi (Faz 3 seçici ingest)**:
   - FF 2008 "Dissecting Anomalies" (paywall→preprint)
   - Ball-GLN 2016 (Tier 1 #9; Cop methodology origin)
   - HXZ 2015 q-factor origin (Tier 1 #3)
   - Stambaugh-Yuan 2017 mispricing factors (Tier 1 #23)
   - LSV 1994 contrarian (Tier 1 #7)
   - Frankel-Lee 1998 V/P (paywall)

---

## 2. STRATEGY 2 — Nasdaq 100 v1

### 2.A Universe & Sample (REVİZE Cycle 30)

- **Universe**: Nasdaq 100 üyesi top 100 non-financial Nasdaq-listed
  stocks (FAANG-dominant, growth/intangibles-yoğun); index reconstitution
  rules quarterly
- **Wiki amaç evrenleri map'i**: NDX top 100 ≈ Israel-Moskowitz size
  Q5 üst yarısı (largest 20% NYSE breakpoint); FAANG profile
  ([[papers/mclean_pontiff_2016_post_publication_decay]] [Tablo 8]
  limited arbitrage büyük/likit/divid-payer/düşük-idio profilinin
  ucu)
- **Sample dönemi (Cycle 27 + 29 modern data anchor)**:
  - Modern data infrastructure tam erişilebilir
    ([[methodology/data_sources]] §1-3); JKP 2023 anchor 1926-2020
    + post-2020 OOS sensitivity
  - NDX yapısal genişleme 1985'ten itibaren; modern data 2000-2024
    hedef; post-2014 FAANG era 2014-2020 6 yıl JKP sertleştirme;
    post-2020 (2021-2024) hala out-of-sample
- **Capped VW (NYSE 80th percentile winsorize)** ⭐: NDX **mega-cap
  concentration distortion kontrolü kritik** (Apple/Microsoft/Nvidia
  NDX %15-20+); JKP methodology Faz 3 implementation tercih natural
  fit (mega-cap mask kontrolü Nokia örneği [[papers/jensen_kelly_pedersen_2023_replication_crisis]]
  [s.3 fn 3] paralel)

### 2.B Factor Inclusion (REVİZE Cycle 30 — F bloğu 4-katmanlı + theme diversification)

**NDX CORE composite** (v0'dan korunur, FGX validation):
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

**Overlay (REVİZE Cycle 30 — F bloğu 4-katmanlı sertleştirme)**:
- **R&D-to-market (Rdm)** ([[concepts/intangibles_adjusted_accounting]];
  q-factor alpha 0.7%/ay sig; 4/4 hayatta kalan; NDX-spesifik kritik
  signal)
- **Organization Capital (OC) factor signal** ⭐ (Cycle 25):
  [[factors/Organization_Capital]] industry-relative within FF17
  spread 4.8%/yıl Sharpe 0.58 + FF3 α 5.5% sig + Carhart α 3.9% sig
  1% (1970-2008); high OC firms NDX FAANG profile birebir match
  (low PP&E/AT + growth-tilted + low leverage); F bloğu **4. ayak
  factor portfolio direct evidence** ([[papers/eisfeldt_papanikolaou_2013_organization_capital]])
- **F bloğu intangibles-aware Bm rebuild** (4-katmanlı methodology
  hierarchy, Cycle 25 sertleştirme):
  - **Knowledge** (Lev-Sougiannis perpetual inventory R&D capital)
  - **Organization** (Eisfeldt-Papanikolaou full SG&A perpetual
    inventory δ=15% **veya** Peters-Taylor θ=30% allocation; Q60
    horse race)
  - **Total** (Peters-Taylor q^tot proxy)
  - **Application** (Lev-Srivastava adjusted HML methodology
    [[papers/lev_srivastava_2020_value_failure]] anchor; vanilla
    HML reject)

**REJECT** (S&P 500 ile aynı + NDX-spesifik):
- Vanilla HML (Lev-Srivastava 2010s NEGATIVE; Israel-Moskowitz
  size-conditional)
- SMB vanilla (Q11 fully-answered)
- F-Score standalone large-cap (BM-Q5 kalibre; NDX growth-tilted)
- RMW Ope (HXZ q-factor INSIG; FGX DS-sig methodology farkı dokümante)

#### 2.B.1 Theme Diversification Yapısı (YENİ Cycle 30 — NDX FAANG profile)

**NDX v1 theme allocation** (10/13 universal'den **5 dominant FAANG
profile**):

| Theme | Wiki anchor | NDX v1 weight |
|-------|-------------|---------------|
| **Quality** | [[factors/QMJ]] + Asness QARP framework (Cycle 19 Q2 anchor) | Yüksek (composite + 4 dimension) |
| **Profitability** | [[factors/Gross_Profitability]] G&V/P + GP/A standalone (Cycle 23 Q55 fully-answered) | Yüksek (FAANG yüksek GP/A; FGX DS-sig) |
| **Profit Growth** | [[factors/G_Score]] Mohanram NASDAQ partition +26.4% (Cycle 6) | Yüksek (NDX growth-tilted natural fit) |
| **Investment\*** | [[factors/Organization_Capital]] OC factor + R&D-to-market overlay + adjusted Bm intangibles-aware (Cycle 25 F bloğu 4-katmanlı) | Yüksek ⭐ (NDX-spesifik kritik) |
| **Value** | Adjusted HML intangibles-aware (Lev-Srivastava + F bloğu 4-katmanlı) | Orta (vanilla HML reject sonrası adjusted methodology) |

**8 theme NDX-relevant değil** (universal'den):
- Seasonality (NDX FAANG profile için marjinal)
- Leverage (NDX low leverage; theme zaten low)
- Low risk (NDX high beta tech)
- Momentum (NDX overlay opsiyonel)
- Size (NDX zaten large-cap; size theme N/A)
- Skewness* (FAANG positive skew; theme tersine)
- Debt Issuance* (NDX low debt; theme zaten low)
- Accruals* (Sloan filter; signal layer F bloğu içinde)

**Q69 paralel** (Cycle 27 yeni): NDX-spesifik 13 theme subsample
decomposition; Faz 3 implementation theme diversification simplified
(5 NDX-specific vs 13 universal).

### 2.C Methodology (NDX-spesifik; REVİZE Cycle 30)

S&P 500 v1 §1.C ile aynı core + NDX spesifik ek:

| Methodology ek | Spec | Anchor |
|----------------|------|--------|
| **Decay multiplier** | ×0.50 NDX agresif sensitivity (limited arbitrage) + **JKP %85 anti-conservative upper bound NDX 16-21% sensitivity** | [[papers/mclean_pontiff_2016_post_publication_decay]] [Tablo 8] (§4.2 Q29) + [[papers/jensen_kelly_pedersen_2023_replication_crisis]] (Cycle 27) |
| Adjusted Bm rebuild | R&D capital + organization capital + external intangibles | [[concepts/intangibles_adjusted_accounting]] **4 ayak hierarchy** (§6) |
| Industry classification | GICS Level-2/3 mapping (NDX 11 GICS sektör; tech subset 70%+) | (§6.6 Q38) |
| Forensic filter | M-Score `.01` conservative | (§5.4 Q47) |
| **YENİ: Theme allocation simplified** | NDX FAANG profile 5 theme dominant (Quality + Profitability + Profit Growth + Investment* + Value) | Q69 (Cycle 27) + [[papers/jensen_kelly_pedersen_2023_replication_crisis]] |
| **YENİ: Capped VW Faz 3 tercih** | NDX mega-cap (Apple/Microsoft/Nvidia %15-20+) concentration distortion kontrolü kritik | [[methodology/backtest_spec]] §1.3 + [[methodology/data_sources]] §5 |

### 2.D Strategy Architecture

```
NDX strategy v1 (F bloğu 4-katmanlı + 5-theme + capped VW):
  Step 1 (Universe): NDX top 100 non-financial; capped VW (NYSE
                    80th percentile winsorize) Faz 3 baseline ⭐
  Step 2 (Adjusted Bm rebuild — F bloğu 4-katmanlı):
    - Knowledge (Lev-Sougiannis R&D capital perpetual inv)
    - Organization (Eisfeldt-Papanikolaou full SG&A δ=15% VEYA
                    Peters-Taylor θ=30%; Q60 horse race)
    - Total (Peters-Taylor q^tot proxy)
    - Application (Lev-Srivastava adjusted HML methodology)
    → adjusted V/P ratio per stock
  Step 3 (Forensic filter): Beneish M-Score > −2.84 (conservative
                            tech) → eligible pool
  Step 4 (Composite ranking — 5 theme allocation):
    Path A (Quality): QMJ 4-dimension z-score + QARP (Asness continuous)
    Path B (Profitability): G & V/P combined + GP/A standalone
    Path C (Profit Growth): G-Score binary 8-component industry-median
    Path D (Investment*): OC factor signal + R&D-to-market overlay
    Path E (Value): Adjusted HML methodology (intangibles-aware Bm)
  Step 5 (Long portfolio): eligible ∩ (Path A ∪ B ∪ C ∪ D ∪ E)
                           top 25-40; 5-theme weighted allocation
  Step 6 (Replication-robust filter — HXZ + JKP iki-yolu):
    - HXZ NYSE-VW lens'inde sig
    - JKP Bayesian Empirical Bayes lens'inde sig (theme cluster
      tangency portfolio sig+)
  Step 7 (Risk constraints): capped VW; sektör concentration cap
                              max 40% any GICS Level-2 (Information
                              Tech 70% cap)
  Step 8 (Rebalance): annual June; 4-month accounting lag
  Step 9 (Reporting — üçlü + iki metric):
    - DSR (Bailey-LdP)
    - Alpha vs q5 + Carhart 4F
    - Decay-adjusted ×0.50 NDX agresif + JKP %85 sensitivity
    - Factor mean return + SDF loading iki metric
```

**Anchor empirik kanıt (v0'dan korunur + v1 yeni)**:
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
- **YENİ Cycle 25**: [[papers/eisfeldt_papanikolaou_2013_organization_capital]]
  OC factor portfolio Carhart 4F α 3.9% sig 1% (1970-2008); high OC
  NDX FAANG profile birebir match
- **YENİ Cycle 27**: [[papers/jensen_kelly_pedersen_2023_replication_crisis]]
  Quality + Profitability + Profit Growth themes >75% replicate
  global Bayesian framework

### 2.E Expected Performance (REVİZE Cycle 30 — KORUNUR + EKLENMELI)

> ⚠️ **Backtest çalıştırılmadı**; aşağıdaki rakamlar literatür
> rakamlarının NDX-agresif decay-adjusted projeksiyonu.

| Bileşen | In-sample | Conservative ×0.50 NDX (HXZ + MP + FGX) | Anti-conservative JKP %85 (sensitivity) |
|---------|-----------|------------------------------------------|------------------------------------------|
| G & V/P combined | +21.45%/yıl | ~10.7% | ~18.2% |
| G & NEGPEG growth | +20.07%/yıl | ~10.0% | ~17.1% |
| QMJ 4-factor alpha | 0.66%/ay × 12 ≈ 7.9%/yıl | ~4.0% | ~6.7% |
| Adjusted HML (intangibles-aware) | conventional + ek | conventional decay'i absorb | aynı |
| R&D-to-market overlay | 0.7%/ay × 12 ≈ 8.4%/yıl | ~4.2% | ~7.1% |
| OC factor signal | Carhart α 3.9%/yıl | ~2.0% (×0.50) | ~3.3% |
| **TOPLAM baseline range** | — | **~8-13%/yıl** (Cycle 24 muhafazakâr KORUNUR) | **~16-21%/yıl** (anti-conservative upper bound) |

**v1 NDX sensitivity range**: **8-13% conservative ↔ 16-21%
anti-conservative (2x range)** — methodology choice ~50pp gap kanıt.

> 📝 **Wiki konservatizm korunur**: NDX baseline range Cycle 24
> muhafazakâr revize ×0.50 multiplier (limited arbitrage NDX FAANG
> profil); JKP %85 anti-conservative upper bound sensitivity reference
> **acknowledged** ama wiki conservative tercih edilir
> ([[meta/contradictions]] §3 resolution).

### 2.F Known Weaknesses (REVİZE Cycle 30)

1. NDX 100-stock sample küçük; portfolio diversification limit (top
   25-40 stocks zorunlu).

2. Tech concentration extreme (Information Tech 60-70% NDX); sektör
   neutralization NDX amacıyla çelişir (NDX zaten tech-tilted).

3. Mohanram G-Score sample 1979-1999; FAANG era (2008-2024) post-2000
   out-of-sample (Q3 partial; **Cycle 27 + 29 modern data partial→tam
   kapanma** ama post-2020 hala OOS).

4. **Monthly-orijinal annual-uyarlama primum kaybı sensitivity test
   edilmedi (Q35 + Q51 + Q57)** — QMJ + UMD + Novy-Marx GP/A hepsi
   monthly rebalance orijinal; wiki yıllık. **Faz 3 backtest
   implementation'ın ilk sensitivity test'i bu olmalı.** NDX için
   ek caveat: monthly G-Score (Mohanram orijinal annual; uyarlama
   yok ama industry-median rebalance frekansı sektör compositional
   shift altında etki edebilir).

5. Intangibles-aware Bm rebuild methodology **F bloğu 4-katmanlı**
   (Cycle 25 sertleştirme); Faz 3 implementation Eisfeldt-Papanikolaou
   full SG&A vs Peters-Taylor θ=30% horse race (Q60).

6. R&D-to-market formal tanımı stock vs flow methodology farkı
   ([[papers/lev_sougiannis_1996_rd_capitalization]] [s.133 fn 22] Q39).

7. NDX 100-spesifik direct fundamental composite scoring test wiki'de
   YOK ([[meta/data_gaps]] Cycle 5 priori boşluğu); Mohanram Tablo 5
   "hi-tech subgroup" + "NASDAQ partition" proxy.

8. QMJ post-2012 modern replikasyonu **Cycle 27 + 29 partial→tam
   kapanma** (Q51 partial-stronger; JKP Quality theme >75% replicate).

9. Beneish M-Score tech firma false positive (high SGI/AQI; Q47).

10. **YENİ Cycle 30 — 3. contradictions entry resolution acknowledged**
    (NDX-spesifik): NDX FAANG profile + capped VW methodology JKP
    framework natural fit; HXZ pure VW conservative-side baseline
    korunur. **Q69** (NDX 13 theme subsample decomposition; 5
    NDX-specific vs 13 universal).

11. **YENİ Cycle 30 — Q60 horse race**: Eisfeldt-Papanikolaou full
    SG&A vs Peters-Taylor θ=30% allocation methodology farkı; Faz 3
    NDX implementation iki alternative sensitivity test (Cycle 25 +
    27 sertleştirme).

---

## 3. EXPECTED PERFORMANCE — İki Strategy Karşılaştırma Özeti (REVİZE Cycle 30)

| Metrik | S&P 500 v1 | NDX v1 |
|--------|-----------|--------|
| Anchor compositesi | F&V/P + GP/V Fortune 500 + 7 theme | G&V/P + QMJ + GP/A + 5 theme NDX FAANG |
| In-sample literatür baseline | ~12-22% | ~20-26% |
| **Conservative baseline (Cycle 24 muhafazakâr KORUNUR)** | **~6-10%/yıl** | **~8-13%/yıl** |
| **Anti-conservative JKP sensitivity (YENİ Cycle 30)** | **~14-18%/yıl** | **~16-21%/yıl** |
| **Sensitivity range (2x)** | 6-10% ↔ 14-18% | 8-13% ↔ 16-21% |
| Forensic filter | Beneish .025 | Beneish .01 conservative |
| Overlay | Long-only UMD | R&D-to-market + OC factor + adjusted Bm 4-katmanlı |
| Theme diversification | 7 dominant (Quality + Profitability + Profit Growth + Value + Momentum + Accruals* + Low risk) | 5 NDX FAANG (Quality + Profitability + Profit Growth + Investment* + Value) |
| Implementation karmaşıklığı | Standart fundamental + screen + 7-theme allocation | F bloğu 4 ayak intangibles-aware (yüksek) + 5-theme NDX-specific |
| Modern data ihtiyacı | Cycle 29 TAM KAPANMA partial (post-2020 OOS) | Cycle 29 TAM KAPANMA partial (post-2020 OOS + intangibles modern) |
| Methodology choice | Capped VW Faz 3 tercih aday | Capped VW ⭐ NDX kritik (mega-cap concentration) |

**Wiki için pratik sıralama**: S&P 500 strategy v1 daha **tahmini
hazır** (literatür baseline güçlü + methodology standart + 7-theme
allocation universal); NDX strategy v1 **F bloğu 4-katmanlı
implementation infrastructure** Faz 3'te formalize edilmeli (Q60 +
Q67 + Q69 paralel).

---

## 4. KNOWN WEAKNESSES (cross-strategy genel; REVİZE Cycle 30)

> 📝 [[methodology/backtest_spec]] §10 mevcut + bu sayfada genişletildi.
> Faz 3'te ayrı `wiki/strategies/known_weaknesses.md` açılır.

1. **Modern data Cycle 29 TAM KAPANMA**: [[methodology/data_sources]]
   üç paralel kaynak (Chen-Zimmermann + JKP + WRDS); post-2020
   FAANG/AI 2021-2024 hala out-of-sample (Faz 3 custom replikasyon).

2. **E bloğu (large-cap reality)** Cycle 22 sertleştirme; **FF 2008
   "Dissecting Anomalies"** hala eksik (Tier 1 paywall→preprint),
   Q14 CMA/RMW direct test partial.

3. **Profitability zinciri 4. halka Ball-GLN 2016 paper sayfası eksik**
   (Tier 1 #9 ingest edilmedi); Cop methodology origin standalone
   paper sayfası açılmadı.

4. **Intangibles-aware GP/A** (Q56) — F bloğu + Profitability zinciri
   entegrasyonu Faz 3 implementation eksik.

5. **Lakonishok-Shleifer-Vishny 1994** (Tier 1 #7) value premium
   contrarian hipotezinin ana kaynağı — wiki'de paper sayfası yok.

6. **Faktor-spesifik decay literatür eksik**: McLean-Pontiff aggregate
   %35 multiplier composite scores için **proxy**, doğrudan kanıt
   değil.

7. **Annual uyarlama UMD/QMJ aylık-orijinal sensitivity** (Q33+Q35+Q57)
   — backtest implementation sensitivity test gerekli.

8. **Frazzini-Israel-Moskowitz 2018** firm-level trading cost analysis
   (Tier 3 #52, paywall) — annual rebalance turnover/cost trade-off
   modern empirik kanıt eksik.

9. **HXZ 2015 q-factor origin paper** (Tier 1 #3) — q-factor methodology
   formal tanımı paper sayfası yok; q5 model'in **origin formal tanımı
   eksik**.

10. **Buffett-tipi alpha discretionary** ([[papers/hou_mo_xue_zhang_2020_security_analysis]]
    q5 alpha 0.77% t=2.69) — wiki strategy hedeflememeli, achievable
    değil; bu skill-based residual sistematik strategy beyond.

11. **YENİ Cycle 30 — 3. contradictions entry resolution acknowledged**:
    HXZ 2020 vs JKP 2023 dramatic methodology disagreement
    ([[meta/contradictions]] §3; ~50pp gap; capped VW + 1-month +
    Bayesian framework methodology choice'lara aşırı duyarlı). Wiki
    conservative-side baseline tercih edilir; anti-conservative-side
    framework varlığı acknowledged. Faz 3 implementation methodology
    choice sensitivity test üç alternative (pure VW + FF half-weight
    + capped VW); HXZ + JKP iki-yolu replication-robust filter.

12. **YENİ Cycle 30 — Stambaugh-Yuan 2017 mispricing factors** (Tier 1
    #23) hala eksik; FGX explicit cite muhtemelen; Faz 3 seçici
    ingest aday.

13. **YENİ Cycle 30 — Avramov-Cheng-Metzker 2023** (Tier 2 #43) ML
    vs Economic Restrictions; Bayesian framework JKP paralel; Faz 3
    seçici ingest aday.

---

## 5. NEXT STEPS (Faz 2-3 yol haritası; REVİZE Cycle 30)

### Cycle 25-29 — Faz 2 ingest birikim ✅

- Cycle 25: Eisfeldt-Papanikolaou 2013 (F bloğu 4. ayak; Q41
  fully-answered)
- Cycle 26: FGX 2020 (D bloğu statistical bacağı 2. paper;
  Q55 + Q7 fully-answered; Profitability seçim doğrulandı)
- Cycle 27: JKP 2023 (D bloğu replication ayağı 2. paper; Q63
  fully-answered; **3. contradictions entry**; conservative vs
  anti-conservative iki kutup; 13 theme cluster + tangency
  portfolio)
- Cycle 28: §11.5 zorunlu consolidation + 7 stale fix
- Cycle 29: methodology/data_sources.md (Modern data eksik weakness
  TAM KAPANMA; üç paralel data kaynağı)

### Cycle 30 — v0_draft → v1_draft revize ✅ (BU CYCLE)

- 6 ana revize uygulandı (universe + factor + methodology + expected
  performance + known weaknesses + next steps)
- v0 historic preservation (Cycle 30 itibariyle; superseded_by v1)
- v1 active draft (Faz 3 v1 formal spec'lerinin ön formu)

### Cycle 31 — Faz 2 sertifika değerlendirmesi + handoff_faz3 + CLAUDE.md §7 ratify

- **Faz 2 sertifika TAM/YUMUŞAK karar** ([[meta/handoff_faz2]] §3
  kriterleri):
  - methodology/backtest_spec.md ✅ Cycle 21
  - Aday strategy draft (v0_draft → v1_draft) ✅ Cycle 24 + 30
  - E bloğu Israel-Moskowitz ✅ Cycle 22
  - Tier 2/3 seçici ingest (Novy-Marx + Eisfeldt-Papanikolaou) ✅
  - Modern replication (JKP 2023 paper-form + Chen-Zimmermann data
    portal) ✅ Cycle 27 + 29
  - FGX 2020 redundancy testing ✅ Cycle 26
  - 3. contradictions entry resolution ✅ Cycle 27
  - §11.5 ZORUNLU consolidation pass ✅ Cycle 28
  - methodology/data_sources.md ✅ Cycle 29
  - **v0 → v1 evrim historic preservation** ✅ Cycle 30 (TAM eşik
    kanıtı)
- **handoff_faz3.md açma** (4. handoff dokümanı; Cycle 24 GKX/KNS
  atlama kararı + Faz 3 yol haritası net)
- **CLAUDE.md §7 schema ratify** (Faz 2 schema → Faz 3 schema geçiş)

### Cycle 32+ — Faz 3 başlangıç

- `wiki/strategies/sp500_v1.md` formal spec
- `wiki/strategies/nasdaq100_v1.md` formal spec
- `wiki/strategies/known_weaknesses.md` formal sayfa (v1_draft §1.F +
  §2.F + §4 cross-strategy formalize)
- **Backtest implementation**: Chen-Zimmermann + JKP code repository
  + WRDS data ile; pure VW + FF half-weight + capped VW üç alternative
  methodology sensitivity test; HLZ + FGX + JKP üç paralel methodology
  factor selection; 13 theme cluster + tangency portfolio multi-theme
  allocation framework
- **Faz 3 seçici ingest aday paperlar** (paywall durumuna göre):
  - FF 2008 + Ball-GLN 2016 + HXZ 2015 + Stambaugh-Yuan 2017 +
    LSV 1994 + Frankel-Lee 1998 + Avramov-Cheng-Metzker 2023

### ATLANAN PAPERLAR (Cycle 24 lint_pass kararı; handoff_faz3'te dokümante)

- **Gu-Kelly-Xiu 2020** (Tier 1 #20) — wiki proje amacı için marjinal;
  ML feature explosion caveat ([[concepts/factor_zoo]] decay perspective);
  Q6 (top importance feature'lar) FGX redundancy test ile dolaylı kapanır
- **Kozak-Nagel-Santosh 2020** (Tier 1 #22) — SDF estimation methodology;
  sistematik strategy için dolaylı

---

## İlgili Sayfalar

### Predecessor (HISTORIC)
- [[strategies/v0_draft]] — Cycle 24 v0 historic kayıt; Cycle 25-29
  ek note'lar + Cycle 28 7 stale fix sonrası dondurulu

### Methodology
- [[methodology/backtest_spec]] — bu strategy taslağının ön koşulu;
  tüm methodology kararları §1-9 referansla; Cycle 22-27 sertleştirildi
- [[methodology/data_sources]] — **Cycle 29 yeni**; modern data
  infrastructure pointer (Chen-Zimmermann + JKP + WRDS); Faz 3
  backtest implementation altyapısı

### Faz 1 + Faz 2 sentez backbone
- [[meta/handoff_faz2]] — Faz 1 → Faz 2 geçiş; YUMUŞAK sertifika
- [[concepts/post_publication_decay]] — dört darbe çerçevesi sentez
  tablosu
- [[concepts/multiple_testing]] — D bloğu statistical bacağı 3 paper
  × üç paralel methodology aile (HLZ + FGX + JKP)
- [[concepts/anomaly_replication]] — replication crisis literatür hattı
  (HXZ + JKP + Chen-Zimmermann data portal)
- [[concepts/intangibles_adjusted_accounting]] — F bloğu **4-katmanlı**
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
- [[papers/eisfeldt_papanikolaou_2013_organization_capital]] — F bloğu
  4. ayak OC factor portfolio
- [[papers/feng_giglio_xiu_2020_factor_zoo]] — Profitability seçim
  DS-sig validation + üç paralel statistical methodology
- [[papers/jensen_kelly_pedersen_2023_replication_crisis]] — modern
  data + 13 theme cluster + tangency portfolio + 3. contradictions
  entry

### Meta
- [[meta/open_questions]] — 72 Q (9 fully-answered + Q1+Q2+Q5+Q7+Q11+
  Q17+Q41+Q55+Q63 + Q49 partial-stronger + Q66-Q72 Cycle 27-29 yeni)
- [[meta/data_gaps]] — Cycle 22 + 23 + 25 + 26 + 27 + 29 sonrası
  bölümler; v1 Faz 2-3 ön koşulları konsolide
- [[meta/contradictions]] — **3 entry** (HML evrimi + MP↔HXZ + **HXZ↔JKP
  Cycle 27**)
- [[meta/handoff_faz2]] — Faz 1 → Faz 2 geçiş yol haritası

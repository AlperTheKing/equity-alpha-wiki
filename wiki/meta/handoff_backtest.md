---
type: handoff
phase: faz_3_sonu_backtest_kickoff
opened: 2026-05-02
predecessor: meta/handoff_faz3.md (Faz 2 → Faz 3; Cycle 41 update Faz 3 YUMUŞAK sertifika)
faz_3_sertifika: YUMUŞAK
faz_3_sertifika_tarih: 2026-05-02
faz_3_sertifika_cycle: 41
backtest_repo: equity-alpha-backtest (yeni, ayrı)
backtest_platform: Portfolio123 Ultimate
wiki_status: yaşayan-proje (canlı bilgi tabanı; yeni paper ingest + backtest geri rapor; cycle numarası post-Faz 3 update kategorisinde devam)
---

# Handoff — Backtest Projesi Kickoff (5. Handoff Dokümanı)

> 📝 **Bu beşinci handoff dokümanı**. handoff.md (1. — Cycle 11
> öncesi, A-B-C bloğu state) + handoff_cycle15.md (2. — Cycle 16
> öncesi, F bloğu başlangıcı) + handoff_faz2.md (3. — Faz 1 → Faz 2;
> YUMUŞAK) + handoff_faz3.md (4. — Faz 2 → Faz 3; TAM + Cycle 41
> YUMUŞAK Faz 3 sertifika anchor) + **handoff_backtest.md (5. — wiki
> ↔ backtest projesi geçiş; Cycle 41 wiki yaşayan-proje statüsüne
> geçiş)**.

---

## 1. Backtest Projesi Kapsamı

| Item | Spec |
|------|------|
| **Repo** | `equity-alpha-backtest` (yeni, ayrı; wiki repo'dan bağımsız) |
| **Platform** | **Portfolio123 Ultimate** ($389/ay); 20-yıl backtest + Position Sizing + Optimizer + Regression + AI Factor + Hedging/Long-Short |
| **Veri** | P123 point-in-time data (CRSP + Compustat lifelong-included) + opsiyonel FMP / SEC EDGAR override (özel field için; örn. F bloğu R&D capital perpetual inventory) |
| **Sample** | **2010-2024** backtest (~14 yıl backtest period; modern era FAANG-dominant) + **2025+** canlı uygulama |
| **Capital** | $1M; sp500_v1 + nasdaq100_v1 birlikte (~%50/%50 split) |
| **Drawdown tolerance** | %50 (kullanıcı risk profili; 2008 + COVID + 2022 senaryoları acknowledge) |
| **Rebalance** | **Annual June** (CLAUDE.md §1 hedef + sp500_v1 §3.1 + nasdaq100_v1 §3.1) + **Quarterly drift check güvenlik valfı** (mega-cap concentration kontrolü; capped VW NYSE 80th percentile winsorize ihlal alarm) |

---

## 2. Wiki ↔ Backtest Projesi İlişkisi (Döngüsel Öğrenme)

```
                  Wiki teori (yaşayan-proje)
                          │
                          │ (Wiki strategy spec → P123 implementation)
                          ▼
                  Backtest projesi (P123 Ultimate)
                          │
                          │ (Backtest sonuç → wiki paper-form rapor)
                          ▼
                  Wiki sentez güçlenir (v1 → v2 evrim aday)
                          │
                          │ (yeni paper ingest + cycle devam)
                          ▼
                  Wiki teori (güncellenmiş)
```

**Yön**:
- **Wiki = canlı bilgi tabanı** (yaşayan proje)
- **Backtest projesi = uygulama katmanı** (P123 implementation)
- **Cycle 30 v0_draft → v1_draft historic preservation paterni paralel**: v1 → v2 evrim **backtest sonuçlarıyla** gerçekleşir; backtest geri rapor wiki'de paper sayfası olarak ingest edilir; v2 spec yazılırsa historic preservation pattern Cycle 30 origin uygulanır

**Wiki maintainer rolü aktif kalır**: cycle numarası post-Faz 3 update kategorisinde devam (Cycle 42+); yeni paper ingest + backtest geri rapor + lint/consolidation pass'ler.

---

## 3. Wiki Spec'lerinin P123'e Mapping

### 3.1 Strategy Spec'leri → P123 Ranking Systems

- **sp500_v1.md §2.1 7 dominant theme** → **7 P123 ranking system** (Quality + Profitability + Profit Growth + Value + Momentum + Accruals* + Low risk); her theme için P123 ranking + theme weight Position Sizing'de balanced allocation
- **nasdaq100_v1.md §2.1 5 FAANG theme** → **5 P123 ranking system** (Quality + Profitability + Profit Growth + Investment* + Value); NDX FAANG profile capped VW ZORUNLU mega-cap concentration kontrolü

### 3.2 Methodology → P123 Simulation Config

- **methodology/backtest_spec §1-9** → P123 simulation config (universe filter + rebalance schedule + accounting lag + transaction cost model)
- **methodology/data_sources §1-3** → P123 native data + opsiyonel FMP / SEC EDGAR override (custom field için)
- **methodology/backtest_implementation_plan §1-8** (Cycle 40 SKELETON) → P123 implementation roadmap çevirisi (§5 alternative weighting + §7 NDX intangibles dörtlü konsolidasyonu P123 custom DSL formula gerektirir)

### 3.3 Known Weaknesses → P123 Implementation Caveats

- **known_weaknesses §1-5** → P123 implementation caveats acknowledge:
  - §1.1 Modern data partial → P123 point-in-time avantaj (FAANG era 2010-2024 native coverage)
  - §1.3 Monthly-orijinal annual-uyarlama Q35+Q51+Q57+Q75 → P123 sensitivity test (annual vs monthly rebalance comparison)
  - §3.13 NDX Intangibles Dörtlü Konsolidasyonu Q56+Q73+Q79+Q82 → P123 custom DSL formula kritik (§4 P123-spesifik notes)

### 3.4 4 Zincir → P123 Formula DSL

| Zincir | Cycle | Wiki Anchor | P123 Implementation |
|--------|-------|-------------|---------------------|
| **Sloan zinciri** (mispricing/accruals 4-paper × 23-yıl) | 9 + 18 + 19 + 38 + 39 | F_ACCRUAL → G3 → QMJ ACC → Cop subsumes accruals | P123 accruals formula + Sloan filter (Oa screen-out) + Cop signal (factor-level) + Stambaugh-Yuan UMO1 composite (üç paralel epistemic framework complementary; sp500_v1 §2.1 madde 6 Cycle 40 sertleştirme) |
| **Profitability zinciri** (4-paper × 7-yıl) | 23 + 4 + 19 + 38 | GP/A → RMW Ope → QMJ GPOA → Cop | P123 ranking system Profitability theme; Cop standalone tercih + QMJ composite + GP/A; RMW Ope reject (HXZ q-factor INSIG + FF 2008 size-conditional zayıf) |
| **F bloğu intangibles 4-katmanlı** (Knowledge + Organization + Total + Application) | 15 + 25 + 16 + 17 | Lev-Sougiannis + Eisfeldt-Papanikolaou + Peters-Taylor + Lev-Srivastava | P123 **custom DSL formula** zorunlu (P123 native R&D capital perpetual inventory YOK; SG&A %30 allocation Peters-Taylor methodology custom); §4 implementation notes |
| **Composite mispricing scoring** (4-paper × 17-yıl) | 5 + 6 + 39 + 27 | F-Score → G-Score → Stambaugh-Yuan MGMT/PERF → JKP 13 theme | P123 ranking system (binary F/G + continuous MGMT/PERF composite); 11 anomaly clustering hierarchical (Stambaugh-Yuan paterni) P123 Optimizer çıkışı |

---

## 4. P123-Spesifik Implementation Notes

### 4.1 F Bloğu 4-Katmanlı Intangibles-Aware Bm Rebuild — Custom Formula

**P123 native EKSİK**: R&D capital perpetual inventory + SG&A allocation methodology
**Custom DSL formula gerekir** (kullanıcı yazacak):
- Knowledge: Lev-Sougiannis perpetual inventory (industry-spesifik δ pharma 9 + scientific 5 yıl); 5-yıl rolling sum R&D + δ amortization
- Organization: Eisfeldt-Papanikolaou full SG&A δ=15% **VEYA** Peters-Taylor θ=0.30 partial allocation (Q60 horse race; iki alternative sensitivity test)
- Total: Peters-Taylor q^tot proxy = MV / (K_phy + K_int)
- Application: Lev-Srivastava adjusted HML methodology

### 4.2 Üç Paralel Statistical Methodology — P123 Approximations

**HLZ + FGX + JKP üç paralel methodology** P123'te **tam implementation YOK**; approximations:
- **HLZ** (`|t|>3.0` BHY): P123 Regression module multiple-testing correction approximation
- **FGX** (DS LASSO 150-factor library): P123 Optimizer module DS-sig approximation (P123 lasso option varsa)
- **JKP** (Bayesian Empirical Bayes): P123 AI Factor module hierarchical model approximation

> ⚠️ **Caveat**: P123 native her üç methodology'i tam implement etmez; approximations + sensitivity test ile yaklaşır; wiki dışı tam implementation Python (statsmodels + scikit-learn + PyMC) gerektirir.

### 4.3 13 Theme Cluster + Tangency Portfolio — P123 Position Sizing

**P123 Position Sizing custom weighting**:
- sp500: 7-theme dominant tangency optimal weights (JKP 2023 paterni paralel)
- nasdaq100: 5-FAANG dominant tangency optimal weights (Q69 paralel)
- 3 displaced theme acknowledgment (Profitability + Investment + Size joint redundancy; JKP 2023)

### 4.4 Capped VW NYSE 80th Percentile Winsorize

**P123 Position Sizing**:
- Mega-cap concentration kontrolü
- sp500: tercih (Apple/MSFT %5-8); nasdaq100: **ZORUNLU** (FAANG %15-20+)
- Stambaugh-Yuan 20/80 NYSE+AMEX+NASDAQ 4. methodology choice **mispricing-aware overlay** (Cycle 39 + 40); P123'te custom breakpoint sensitivity test

### 4.5 Sektör Concentration Cap

| Strategy | Cap | P123 Implementation |
|----------|-----|----------------------|
| sp500_v1 | GICS Level-1 max 25% | P123 Position Sizing sector constraint |
| nasdaq100_v1 | GICS Level-2 max 40% + Information Tech max 70% | P123 sector constraint NDX FAANG profile acknowledge |

---

## 5. Backtest Projesi Roadmap (4-6 Hafta)

| Hafta | İş | Deliverable |
|-------|-----|-------------|
| **1-2** | P123 öğrenme + sp500_v1 ranking systems | 7 ranking system (Quality + Profitability + Profit Growth + Value + Momentum + Accruals* + Low risk) live + simulation 2010-2024 baseline |
| **3** | nasdaq100_v1 ranking systems + intangibles-aware Bm rebuild | 5 NDX ranking system + F bloğu 4-katmanlı custom DSL formula (Knowledge + Organization + Total + Application) |
| **4** | Backtest 2010-2024 (sp500_v1 + nasdaq100_v1 ayrı + birleşik portfolio) | Sample backtest report (sp500 standalone + nasdaq100 standalone + birleşik %50/%50) |
| **5-6** | Sensitivity test + canlı portfolio | Üç (+1) alternative weighting sensitivity (pure VW + FF half-weight + capped VW + Stambaugh-Yuan 20/80) + Mayıs 2026 canlı portfolio top 60-80 stock + $1M allocation |

---

## 6. Geri Rapor Protokolü (Backtest → Wiki)

### 6.1 Backtest Sonuçları — Ayrı Klasör (akademik paper'larla karıştırılmaz)

> 📝 **Cycle 42 schema_update ([[CLAUDE.md]] §12.2)**: Path
> konvansiyonu güncellendi — backtest raporları **`wiki/backtests/`**
> altında saklanır (`wiki/papers/` rezerve akademik literatür için).
> Aşağıdaki orijinal path örneği historic; aktif konvansiyon §12.2.

Backtest sonuçları **wiki yaşayan-proje paterninde** ingest edilir:
- **Aktif konvansiyon ([[CLAUDE.md]] §12.2)**: `wiki/backtests/p123_{strategy}_{YYYY-MM-DD}.md`
  (örn. `wiki/backtests/p123_sp500_v1_2026-06-15.md` +
  `wiki/backtests/p123_nasdaq100_v1_2026-07-01.md`)
- ~~Historic örnek (Cycle 41 yazımı): `papers/p123_backtest_{YYYY}_{strategy}.md`~~ — superseded by §12.2
- YAML frontmatter: `type: backtest_report` zorunlu (tam şablon CLAUDE.md §12.2)
- İçerik: Sample stats + factor inclusion list + theme allocation + DSR + walk-forward sub-period + bootstrap CI + alternative weighting sensitivity matrix

### 6.2 Anchor Sayfa

**[[methodology/backtest_implementation_plan]] §8** — Faz 3 sertifika kriter #6-9 mapping bölümü güncel; backtest_results sub-document oluşturulabilir veya ayrı `methodology/backtest_results.md` 4. sayfa açılır (Cycle 41+ post-Faz 3 update kararı).

### 6.3 v1 → v2 Evrim Trigger

**Trigger kriterleri** (backtest sonucu wiki conservative baseline'dan dramatik sapma):
- sp500_v1 conservative baseline 6-10%/yıl ↔ backtest <3% veya >20% (range dışı)
- nasdaq100_v1 conservative baseline 8-13%/yıl ↔ backtest <4% veya >25% (range dışı)
- Üç (+1) alternative weighting sensitivity dramatic divergence (>5pp methodology choice farkı)
- F bloğu 4-katmanlı intangibles-aware Bm rebuild Q60 horse race winner (Eisfeldt-Papanikolaou full SG&A δ=15% vs Peters-Taylor θ=0.30) açık tercih

**v2 spec açma**: `strategies/sp500_v2.md` + `strategies/nasdaq100_v2.md`; Cycle 30 historic preservation pattern paralel (v1 historic; v2 active). **v1 OVERWRITE EDİLMEZ** ([[CLAUDE.md]] §12.3 Cycle 42 schema_update; YAML `status: historic` + `superseded_by` satırları eklenir, content değiştirilmez).

---

## 7. Wiki Yaşayan-Proje Protokolü

### 7.1 Cycle Numarası Devam

Cycle 41 sertifika YUMUŞAK; **Cycle 42+ post-Faz 3 update kategorisinde** devam:
- Yeni paper ingest (LSV 1994 + Frankel-Lee 1998 + ACM 2023 + diğer kitap/paper)
- Backtest sonuç geri rapor (P123 backtest çıktıları paper-form ingest)
- Lint/consolidation pass'ler (4-cycle ardışık disiplin korunur; Cycle 44/48/...)
- v1 → v2 evrim revize (backtest sonrası historic preservation pattern)

### 7.2 Wiki Maintainer Rolü Aktif

CLAUDE.md §1-11 disiplin korunur:
- Yeni paper ingest workflow (§5.1)
- §11.2 6-spot audit her ingest sonrası
- §11.5 4-cycle ardışık consolidation pass
- Origin attribution dual pattern + concept proliferation kontrol + dört darbe çerçevesi disiplin meta-not + v0/v1/v2 historic preservation pattern

### 7.3 Yeni Paper Önceliği (Yaşayan-Proje Aday Listesi)

[[meta/source_tier_list]] kalan adaylar:
- **Tier 1**: LSV 1994 (Cycle 44+ opsiyonel) + Frankel-Lee 1998 (paywall)
- **Tier 2**: ACM 2023 (#43 ML vs Economic Restrictions)
- **Tier 3**: Frazzini-Pedersen 2013 BAB (#51 Low risk theme); diğer Tier 3 #46-61

### 7.4 Backtest Geri Rapor Trigger

Kullanıcı backtest sonuçlarını ulaştırdığında:
- Yeni session'da `papers/p123_backtest_{YYYY}_{strategy}.md` oluştur
- Anchor sayfaları update (sp500_v1 §5 + nasdaq100_v1 §5 + known_weaknesses §5)
- v1 → v2 evrim trigger değerlendir (§6.3 kriterleri)
- §11.2 audit otomatik

---

## 8. İlgili Sayfalar

### Predecessor Handoff'lar (5 doküman handoff hattı)
- [[meta/handoff]] (1. — Cycle 11 öncesi A-B-C bloğu state)
- [[meta/handoff_cycle15]] (2. — Cycle 16 öncesi F bloğu başlangıcı)
- [[meta/handoff_faz2]] (3. — Faz 1 → Faz 2; YUMUŞAK)
- [[meta/handoff_faz3]] (4. — Faz 2 → Faz 3; TAM + **Cycle 41 YUMUŞAK Faz 3 sertifika anchor**)
- **[[meta/handoff_backtest]] (5. — BU DOKÜMAN; wiki ↔ backtest projesi geçiş; Cycle 41 wiki yaşayan-proje statüsüne geçiş)**

### Strategy Specs (P123 Implementation Inputs)
- [[strategies/sp500_v1]] §2.1 7-theme + §3 methodology + §5 backtest implementation roadmap + §6 known weaknesses
- [[strategies/nasdaq100_v1]] §2.1 5-theme + §2.5 F bloğu 4-katmanlı + §3.6 NDX-spesifik nüans + §6 madde 14 NDX Intangibles Dörtlü Konsolidasyonu
- [[strategies/known_weaknesses]] §3.13 NDX Intangibles Dörtlü Konsolidasyonu Q56+Q73+Q79+Q82

### Methodology
- [[methodology/backtest_spec]] §1-9 (parent theoretical infrastructure)
- [[methodology/data_sources]] §1-7 (data infrastructure pointer; P123 native + FMP/SEC override)
- [[methodology/backtest_implementation_plan]] §1-8 SKELETON (Cycle 40; P123 implementation roadmap çevirisi için input)

### Faz 3 Seçici Ingest Anchor Papers (4 paper, Cycle 35-39)
- [[papers/hou_xue_zhang_2015_q_factor]] (q-factor formal origin; r_I/A + r_ROE)
- [[papers/fama_french_2008_dissecting_anomalies]] (size-partition methodology Q14 ANCHOR)
- [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] (Cop methodology origin; factors/Cop)
- [[papers/stambaugh_yuan_2017_mispricing_factors]] (Composite mispricing 3. halka; factors/MGMT + factors/PERF; 4. methodology choice 20/80)

### Yaşayan-Proje Aday Listesi
- [[meta/source_tier_list]] — Tier 1-2-3 + Faz 3 sonu kalan adaylar
- [[meta/open_questions]] — 82 Q (9 fully-answered + Q15+Q24+Q34 fully-answered/partial-stronger Cycle 35+39)
- [[meta/data_gaps]] — Cycle 22-40 sonrası bölümler (post-Faz 3 update kategorisinde devam)
- [[meta/contradictions]] — 3 entry korunur

---

**Dosya yazıldı: 2026-05-02. Cycle 41 Faz 3 YUMUŞAK sertifika +
backtest projesi kickoff + wiki yaşayan-proje statüsüne geçiş.**

**Bu wiki'nin 5. handoff'u.** Wiki gelişim hikayesi 5 handoff
üzerinden okunabilir:
1. handoff.md (10 cycle, A-B-C bloğu state)
2. handoff_cycle15.md (15 cycle, F bloğu başlangıcı)
3. handoff_faz2.md (20 cycle, Faz 1 → Faz 2 YUMUŞAK)
4. handoff_faz3.md (31 cycle, Faz 2 → Faz 3 TAM + Cycle 41 YUMUŞAK Faz 3 sertifika anchor)
5. **handoff_backtest.md** (41 cycle, wiki ↔ backtest projesi geçiş; **wiki yaşayan-proje statüsüne geçiş**)

---
type: meta_summary
opened: 2026-05-03
phase: post_faz_3_yasayan_proje
purpose: "Wiki yöneticisel özet — proje amacı + ana tez + sinyal aileleri + S&P 500/NDX strateji + çelişkiler + bakım protokolü; 41-cycle birikim hızlı giriş katmanı"
audience: "yeni okuyucu + future Claude session + projeye geri dönen kullanıcı"
---

# Equity Alpha Wiki — Yönetici Özeti

> 📝 **Hızlı giriş katmanı**. 41-cycle birikim (28 paper + 20 factor +
> 17 concept + 5 strategy + 3 methodology + 10 meta) tek sayfa özeti.
> Ayrıntı için `wiki/index.md` + `wiki/log.md` + `wiki/meta/handoff_backtest.md`.

---

## 1. Projenin Amacı

> S&P 500 ve Nasdaq 100 evrenlerinde, finansal tablo (10-K/10-Q) verilerini kullanarak yıllık-frekansta en yüksek getiriyi sağlayacak hisseleri seçen sistematik bir strateji tasarlamak.

Karpathy `llm-wiki` paterni: kullanıcı `raw/` altına kaynak ekler; Claude wiki'yi yazar/bakım yapar; CLAUDE.md schema disipline eder. Memory/training kullanımı yasak — wiki sadece `raw/`'daki kaynaklara dayanır.

---

## 2. Literatürden Çıkan Ana Tez

**Üç-bacak epistemik omurga** (Cycle 11-13 D bloğu):

1. **Behavioral decay**: McLean-Pontiff 2016 — 82 anomaly aggregate post-publication decay %35 (sig 1%); büyük/likit firmalarda decay agresif (limited arbitrage çift darbe).
2. **Statistical FDR**: Harvey-Liu-Zhu 2016 — 316 factor census; multiple-testing correction `|t| > 3.0` (BHY 1%); SMB never sig under MT.
3. **Empirical replication**: Hou-Xue-Zhang 2020 — 447 anomaly NYSE-VW + microcap-arınmış; %64 insig at 5%; q-factor lens sonra **net %10 sig**.

**Dört darbe çerçevesi** (Cycle 13-14 sentez tablosu): in-sample large-cap + post-pub decay + MT-corrected sig + replication-robust. 5. darbe AÇILMADI (Cycle 14 disiplin meta-not testi geçti). Cycle 27 JKP 2023 Bayesian Empirical Bayes hierarchical anti-conservative-side ek bacak (3. contradictions entry HXZ↔JKP scope-dependent ~50pp gap).

---

## 3. En Güçlü Sinyal Aileleri (Wiki Birikimi)

### 3.1 Dört Methodology Zinciri

| Zincir | Paper × yıl | Origin → Modern Halka |
|--------|-------------|------------------------|
| **Sloan zinciri** (mispricing/accruals) | 4 paper × 23 yıl | Sloan 1996 → Piotroski 2000 F_ACCRUAL → Mohanram 2005 G3 → Asness 2019 QMJ ACC |
| **Profitability zinciri** | 4 paper × 7 yıl | Novy-Marx 2013 GP/A → FF15 RMW Ope → Asness QMJ GPOA → Ball-GLN 2016 Cop |
| **F bloğu intangibles 4-katmanlı** | 4 paper × 24 yıl | Lev-Sougiannis 1996 (Knowledge) + Eisfeldt-Papanikolaou 2013 (Organization) + Peters-Taylor 2017 (Total) + Lev-Srivastava 2020 (Application) |
| **Composite mispricing scoring** | 4 paper × 17 yıl | Piotroski F-Score → Mohanram G-Score → Stambaugh-Yuan 2017 MGMT/PERF → JKP 2023 13 theme cluster |

### 3.2 4/4 Hayatta Kalan Faktör Adayları (Faz 3 Strategy Spec Anchor)

(HXZ 2020 dört darbe çerçevesi 4/4: in-sample large-cap + post-pub decay + MT-corrected + replication-robust)

| Factor | Methodology | Cycle |
|--------|-------------|-------|
| **Sloan operating accruals (Oa)** | Sloan zinciri origin; q-factor alpha -0.54%/ay sig | 9 |
| **R&D-to-market (Rdm)** | NDX-relevant; q-factor alpha 0.7%/ay sig | 13 |
| **Earnings announcement Abr** | PEAD; q-factor alpha 0.66%/ay sig | 13 |
| **Cash-based op profits (Cop)** | Profitability zinciri 4. halka; q-factor alpha 0.69%/ay sig; tangency Sharpe 4F+Cop=1.67 ⭐ | 38 |

### 3.3 Cycle 35-39 Faz 3 Seçici Ingest Kazanımları

- **q-factor model formal origin** (HXZ 2015 Cycle 35): 4 faktör (MKT + ME + I/A + ROE) + investment-q theory Cochrane 1991; concepts/q_factor_model + factors/I_A + factors/ROE
- **Size-partition methodology origin Q14 ANCHOR** (FF 2008 Cycle 37): asset growth size-conditional CMA(big) INSIG; üçlü teyit (FF 2008 + Israel-Moskowitz + HXZ 2015 [s.7])
- **Cop methodology standalone** (Ball-GLN 2016 Cycle 38): Profitability zinciri 4. halka; **Cop subsumes accruals** factor-level; Sloan fixation hypothesis çürütme
- **Composite mispricing factors** (Stambaugh-Yuan 2017 Cycle 39): MGMT (6 anomaly) + PERF (5 anomaly); modified SMB ~2x premium (Q11 ASTERISK üç-paper sertleştirme)

---

## 4. Wiki Yapısal Pozisyonlar

| Pozisyon | Karar | Anchor |
|----------|-------|--------|
| **Vanilla HML** | REJECT large-cap evrene transferi (post-2010 collapse + size-conditional + B/M big-stock weakness üçlü teyit) | Lev-Srivastava 2020 + Israel-Moskowitz 2013 + FF 2008 |
| **SMB vanilla** | REJECT (Q11 fully-answered ASTERISK üç-paper sertleştirme: QMJ resurrection + IM 86-yıl + Stambaugh-Yuan modified SMB ~2x premium) | Cycle 19 + 22 + 39 |
| **F-Score standalone large-cap** | REJECT (BM-Q5 only kalibre); F&V/P combined tercih | Li-Mohanram 2019 |
| **Magic Formula** | REJECT (q5 captures + microcap residual) | HMXZ 2020 |
| **RMW Ope standalone** | REJECT (HXZ q-factor INSIG + FF 2008 size-conditional zayıf); QMJ Profitability composite + Cop standalone tercih | Cycle 4 + 19 + 37 + 38 |
| **Capped VW NYSE 80th percentile winsorize** | sp500 Faz 3 tercih; **NDX ZORUNLU** (FAANG mega-cap %15-20+) | JKP 2023 + Cycle 27 |

---

## 5. S&P 500 Strateji Özeti (sp500_v1.md formal spec)

- **Universe**: S&P 500 top 500 ex-financials (NYSE-VW yakın); 1980-2020 baseline + 2021-2024 OOS
- **Capped VW** Faz 3 tercih
- **7 dominant theme allocation** (JKP 13 universal'den): Quality + Profitability + Profit Growth + Value + Momentum + Accruals* + Low risk
- **4 path composite**: F&V/P binary intersection (Path A) + GP×V/P Fortune 500 continuous rank (Path B; Novy-Marx [Tablo 7] paterni) + adjusted HML intangibles-aware (Path C) + UMD long-only top 30% (Path D; Israel-Moskowitz Q5)
- **Forensic filter**: Beneish M-Score `.025`
- **Statistical filter**: HLZ + FGX + JKP üç paralel methodology + q-factor 5. paralel layer
- **Replication-robust**: HXZ NYSE-VW + JKP capped VW iki lens
- **Conservative baseline**: 6-10%/yıl (×0.65 multiplier); anti-conservative upper bound 14-18% (JKP %85 sensitivity); **range 2x methodology choice'a duyarlı**

---

## 6. Nasdaq 100 Strateji Özeti (nasdaq100_v1.md formal spec)

- **Universe**: NDX top 100 non-financial Nasdaq; 2000-2020 baseline + 2021-2024 OOS
- **Capped VW ZORUNLU** (mega-cap %15-20+ FAANG concentration kontrolü)
- **5 FAANG dominant theme allocation** (Q69 NDX-spesifik subset): Quality + Profitability + Profit Growth + Investment* + Value
- **5 path composite**: QMJ + QARP (Path A) + G&V/P + GP/A (Path B) + Mohanram NASDAQ partition (Path C) + R&D-to-market + OC factor (Path D Investment* NDX-spesifik kritik) + adjusted HML 4-katmanlı (Path E)
- **F bloğu 4-katmanlı CORE**: Knowledge + Organization + Total + Application (Q60 horse race Eisfeldt-Papanikolaou full SG&A vs Peters-Taylor θ=0.30)
- **Forensic filter**: Beneish M-Score `.01` conservative (Q47 tech firma high SGI/AQI false positive)
- **Conservative baseline**: 8-13%/yıl (×0.50 NDX agresif multiplier; limited arbitrage Q29 çift darbe); anti-conservative 16-21%; range 2x

---

## 7. Ana Çelişkiler (3 Entry)

1. **HML evrimi FF93 ↔ FF15** (Cycle 1; resolution: scope-dependent + sample-dependent; Cochrane #1 normal evrim)
2. **MP 2016 ↔ HXZ 2020** aggregate anomaly survival rate (Cycle 13; resolution: scope-dependent methodology disagreement; equal-weight all-stocks vs NYSE-VW microcap-arınmış)
3. **HXZ 2020 ↔ JKP 2023** dramatic empirik fark (~50pp gap; Cycle 27; resolution: scope-dependent + methodology disagreement; pure VW + 1-month + frequentist OLS vs capped VW + 1-month + Bayesian Empirical Bayes hierarchical + global)

**Wiki taraf tutmaz** Cochrane mathematical equivalence (mispricing vs risk premium iki polar yorum + investment-based intermediate; Lin-Zhang 2012 "two sides of same coin").

---

## 8. Açık Sorular Özet (82 Q; 9 Fully-Answered)

### Fully-Answered (9)
- Q1 (S&P 500 value post-2000) — Lev-Srivastava 2020 anchor
- Q2 (large-cap quality vs value) — Asness QMJ 2019 anchor
- Q5 (post-publication decay) — MP + HLZ + HXZ üç-bacak omurga
- Q7 (FGX redundancy) — FGX 2020 anchor
- Q11 (SMB never sig under MT) — HLZ + ASTERISK üç-paper
- Q14 (RMW/CMA large-cap-only direct test) — FF 2008 ANCHOR + üçlü teyit (Cycle 37)
- Q15 (FF5 vs HXZ q-factor horse race) — HXZ 2015 anchor (Cycle 35)
- Q17 (Cochrane #3 factor zoo) — üç-bacak omurga sentezi
- Q41 (F bloğu 4-way horse race) — Eisfeldt-Papanikolaou Cycle 25
- Q55 (Profitability ailesi DS-sig) — FGX + Ball-GLN sertleştirme
- Q63 (post-2017 modern replikasyon) — JKP 2023 anchor

### NDX Intangibles Dörtlü Konsolidasyonu (Cycle 40)
**Q56+Q73+Q79+Q82** — F bloğu 4-katmanlı paralel intangibles-aware modification dört kanal (GP/A intangibles-adjusted + q-factor I/A + Cop SG&A R&D purging + MGMT/PERF R&D-aware); Faz 3 implementation custom (P123 backtest projesi).

### Annual-Uyarlama Sensitivity (Cycle 35-39)
**Q35+Q51+Q57+Q75+Q81** — monthly-orijinal (QMJ + UMD + GP/A + r_ROE + Stambaugh-Yuan UMO1/UMO2) annual-uyarlama primum kaybı sensitivity; HXZ 2015 [Apx E] direct empirik kanıt annual-sorted momentum/PEAD/IVOL/distress INSIG.

---

## 9. Wiki Yaşayan-Proje Bakım Protokolü

### 9.1 Faz Durumu (post-Cycle 41)

- ✅ Faz 0 scaffold; ✅ Faz 1 YUMUŞAK (Cycle 20); ✅ Faz 2 TAM (Cycle 31); ✅ Faz 3 YUMUŞAK (Cycle 41)
- 🟢 **Yaşayan-proje statüsü**: wiki dondurulmaz; Cycle 42+ post-Faz 3 update kategorisinde devam

### 9.2 Backtest Projesi Wiki Dışı (Faz 3 Sertifika Kriter #6-9 Delegated)

- **Repo**: `equity-alpha-backtest` (yeni, ayrı)
- **Platform**: Portfolio123 Ultimate
- **Detay**: [[handoff_backtest]] (5. handoff)
- **Geri rapor protokolü**: backtest sonuçları `wiki/backtests/p123_{strategy}_{YYYY-MM-DD}.md` (Cycle 42 schema_update; [[CLAUDE.md]] §12.2; akademik paper'larla karıştırılmaz); v1→v2 evrim trigger değerlendirilir (Cycle 30 historic preservation pattern; [[CLAUDE.md]] §12.3)

### 9.3 Yeni Paper Aday Listesi

[[source_tier_list]] kalan adaylar:
- **Tier 1**: LSV 1994 (opsiyonel) + Frankel-Lee 1998 (paywall)
- **Tier 2**: ACM 2023 (#43 ML vs Economic Restrictions)
- **Tier 3**: Frazzini-Pedersen 2013 BAB (#51 Low risk theme)

### 9.4 CLAUDE.md §1-11 Disiplin Korunur

- §5.1 ingest workflow (scope check + paper okuma + paper sayfa + factor/concept update + index/log/audit/open_questions)
- §11.2 6-spot audit her ingest sonrası (A factor entity + B Goal Alignment 4 eksen + C concept zenginleşmesi + D inbound link + E meta + F open_questions/data_gaps)
- §11.5 4-cycle ardışık consolidation pass (Cycle 4/8/12/16/20/24/28/32/36/40/...)
- Origin attribution dual pattern + concept proliferation kontrol (3-kriter testi) + dört darbe çerçevesi disiplin meta-not + v0/v1/v2 historic preservation pattern
- Memory/training kullanımı YASAK (§6.4 + §9 NON-NEGOTIABLE)

### 9.5 Wiki Maintainer Davranışı (Yaşayan-Proje)

- Yeni paper geldiğinde: scope check + ingest + cross-reference maintenance + audit
- Backtest sonucu geldiğinde: paper-form rapor + anchor sayfa update + v1→v2 trigger değerlendirme
- Stale claim tespit edildiğinde: KÜÇÜK/YAPISAL fix kullanıcı onayıyla
- Wikilink syntax `[[page_name]]` Obsidian-uyumlu; `> ⚠️` uyarılar/çelişkiler için; `> 📝` editör notları için

---

## 10. Maintenance Cadence (Cycle 42 schema_update; CLAUDE.md §12)

Post-Faz 3 yaşayan-proje bakım disiplini üç kural ile formalize edildi
([[CLAUDE.md]] §12 yeni bölüm; bu yönetici özet sayfasının kendisi de
kural #1 kapsamındadır).

| # | Tetikleyici | Aksiyon | Anchor |
|---|-------------|---------|--------|
| **1** | Her 4 cycle (Cycle 44/48/52/...) **veya** büyük paper/backtest ingest sonrası | `meta/executive_summary.md` güncellenir (paper sayım + fully-answered Q sayım + yeni zincir/contradictions/sertifika refleksiyonu) | [[CLAUDE.md]] §12.1 |
| **2** | Backtest motorundan (P123 vb.) sonuç geliyor | `wiki/backtests/p123_{strategy}_{YYYY-MM-DD}.md`; YAML `type: backtest_report` zorunlu; **akademik paper sayfalarıyla karıştırılmaz** (wiki/papers/ rezerve) | [[CLAUDE.md]] §12.2 + [[handoff_backtest]] §6.1 |
| **3** | Backtest sonucu strategy spec değişikliği gerektirir (range dışı sapma; methodology choice >5pp divergence; Q60 horse race) | `sp500_v2.md` / `nasdaq100_v2.md` açılır; **v1 OVERWRITE EDİLMEZ** (status=historic + superseded_by) | [[CLAUDE.md]] §12.3 + Cycle 30 v0→v1 paterni paralel |

**4-cycle ardışık disiplin**: Cycle 44/48/52/... §11.5 derin
consolidation pass + executive_summary güncelleme aynı ritimde
tetiklenir. Her 4 cycle'da iki operasyon paralel: (a) consolidation
denetim + (b) executive_summary refleksiyon.

**Anında güncelle (4-cycle bekleme yok)**: yeni paper bir methodology
zincirine 5. halka ekledi / fully-answered Q sayımı değişti / yeni
contradictions entry açıldı / faz/sertifika durumu değişti.

---

## İlgili Sayfalar (Hızlı Referans)

### Navigasyon
- [[index]] — 87 sayfa katalog
- [[log]] — 61 cycle entry kronoloji
- [[handoff_backtest]] — 5. handoff (wiki ↔ backtest projesi)

### Map of Content
- [[MoC_papers]] (28 paper) + [[MoC_factors]] (20 factor)

### Strategy Specs
- [[strategies/sp500_v1]] (Cycle 32) + [[strategies/nasdaq100_v1]] (Cycle 33) + [[strategies/known_weaknesses]] (Cycle 34)

### Methodology
- [[methodology/backtest_spec]] (Cycle 21) + [[methodology/data_sources]] (Cycle 29) + [[methodology/backtest_implementation_plan]] (Cycle 40 SKELETON)

### Sertifika Anchor'lar
- [[handoff_faz2]] (Faz 1 → Faz 2 YUMUŞAK)
- [[handoff_faz3]] (Faz 2 → Faz 3 TAM + §1.5 Cycle 41 Faz 3 YUMUŞAK)
- [[handoff_backtest]] (Cycle 41 yaşayan-proje statüsüne geçiş)

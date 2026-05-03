# equity-alpha-wiki

LLM-maintained empirical asset pricing wiki for designing a systematic equity strategy on S&P 500 + Nasdaq 100 using fundamental data (10-K/10-Q, annual rebalance). Karpathy [`llm-wiki`](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) pattern: `raw/` academic sources → `wiki/` cross-referenced synthesis → `wiki/strategies/` formal specs.

> **Project goal (one sentence)**: S&P 500 ve Nasdaq 100 evrenlerinde, finansal tablo verilerini kullanarak yıllık-frekansta en yüksek getiriyi sağlayacak hisseleri seçen sistematik bir strateji tasarlamak.

> **State (post-Cycle 42)**: 28 paper + 20 factor + 17 concept + 5 strategy spec + 3 methodology + 10 meta sayfa = ~88 .md page across 41-cycle accumulation. Faz 3 YUMUŞAK sertifika imzalandı (2026-05-02); wiki yaşayan-proje (living-project) statüsünde — yeni paper ingest + backtest geri rapor + cycle numarası post-Faz 3 update kategorisinde devam.

---

## Quick Start

**Yeni okuyucu için**: [`wiki/meta/executive_summary.md`](wiki/meta/executive_summary.md) — 41-cycle birikim tek sayfa yöneticisel özet (proje amacı + ana tez + 4 methodology zinciri + 4/4 hayatta kalan factor + S&P 500/NDX strateji özeti + ana çelişkiler + bakım protokolü).

**Detaylı navigasyon**:
- [`wiki/index.md`](wiki/index.md) — tüm sayfa kataloğu (kategori bazlı)
- [`wiki/meta/MoC_papers.md`](wiki/meta/MoC_papers.md) — 28 paper kronolojik + tematik
- [`wiki/meta/MoC_factors.md`](wiki/meta/MoC_factors.md) — 20 factor entity
- [`wiki/log.md`](wiki/log.md) — append-only operation log (61+ cycle entry)

**Tasarım kararları**:
- [`wiki/strategies/sp500_v1.md`](wiki/strategies/sp500_v1.md) — S&P 500 formal spec
- [`wiki/strategies/nasdaq100_v1.md`](wiki/strategies/nasdaq100_v1.md) — Nasdaq 100 formal spec
- [`wiki/strategies/known_weaknesses.md`](wiki/strategies/known_weaknesses.md) — cross-strategy weakness registry
- [`wiki/methodology/backtest_spec.md`](wiki/methodology/backtest_spec.md) — backtest mekaniğinin tek kaynak-of-truth'u

---

## Kullanım

Bu repo Claude Code ile kullanılmak üzere tasarlandı (LLM operatör + kullanıcı denetçi paterni).

```bash
git clone https://github.com/AlperTheKing/equity-alpha-wiki.git
cd equity-alpha-wiki
claude
```

Claude'un ilk yapacağı şey [`CLAUDE.md`](CLAUDE.md) okumaktır — orada operasyon kuralları (§1-12), sayfa şablonları, audit protokolü ve post-Faz 3 yaşayan-proje bakım disiplini var.

**Tipik yaşayan-proje workflow**:

```
> raw/papers/ klasörüne yeni paper koydum, ingest et
> F bloğu intangibles 4-katmanlı methodology'i özetler misin?
> P123 backtest sonuçlarını paper-form raporla (geri rapor)
> consolidation pass yap (4-cycle ardışık disiplin)
> Q60 horse race durumu — Eisfeldt-Papanikolaou full SG&A vs Peters-Taylor θ=0.30
```

**Tetikleyici cümleler** ([CLAUDE.md §11.6](CLAUDE.md)):
- `TEMIZ devam` → audit sonrası bir sonraki cycle plan
- `KÜÇÜK fix devam` → düzeltme + sonraki cycle
- `consolidation` → §11.5 derin denetim pass
- `freeze ingest` → ingest workflow durdur (sadece query/audit)

---

## Yapı (Üç Katman)

```
equity-alpha-wiki/
├── CLAUDE.md              ← Schema. Operasyon kuralları (§1-12). Sayfa şablonları. Audit protokolü.
├── raw/                   ← Immutable kaynak PDF/TXT. LLM yazmaz; kullanıcı ekler.
│   ├── papers/            ← Akademik makaleler
│   ├── books/             ← Kitap bölümleri
│   └── industry/          ← AQR/RA/MSCI whitepaper'ları
├── wiki/                  ← LLM-yazılı, LLM-bakımlı markdown. ~88 sayfa.
│   ├── index.md           ← Tüm sayfaların kataloğu
│   ├── log.md             ← Append-only kronolojik log
│   ├── papers/      (28)  ← Her ingested kaynağın özet sayfası (Goal Alignment 4 eksen tablosu zorunlu)
│   ├── factors/     (20)  ← Her sinyal/factor için entity sayfası
│   ├── concepts/    (17)  ← Kavram hub'ları (post_publication_decay, factor_zoo, q_factor_model, …)
│   ├── comparisons/  (1)  ← f_score_vs_g_score
│   ├── strategies/   (5)  ← v0_draft historic + v1_draft historic + sp500_v1 + nasdaq100_v1 + known_weaknesses
│   ├── methodology/  (3)  ← backtest_spec + data_sources + backtest_implementation_plan
│   ├── backtests/         ← P123 backtest geri raporları (CLAUDE.md §12.2; ilk rapor henüz yok)
│   └── meta/        (10)  ← index, MoC, open_questions, contradictions, data_gaps, source_tier_list, 6 handoff, executive_summary
└── README.md              ← Bu dosya
```

**Üç katmanın sözleşmesi**:
- `raw/` **immutable** — Claude oradan okur, asla yazmaz; kullanıcı ekler/çıkarır.
- `wiki/` **Claude'un alanı** — tüm yazma/güncelleme/silme işlemleri Claude'un sorumluluğunda; kullanıcı izler/yönlendirir.
- `CLAUDE.md` **co-evolved** — workflow'lar netleştikçe kullanıcıyla birlikte güncellenir.

---

## Literatür Sentezi (Mevcut Birikim)

### Üç-bacak epistemik omurga (D bloğu, Cycle 11-13)

1. **Behavioral decay** — McLean-Pontiff 2016: 82 anomaly aggregate post-publication decay %35 (sig 1%)
2. **Statistical FDR** — Harvey-Liu-Zhu 2016: 316 factor census, multiple-testing correction `|t| > 3.0` (BHY 1%)
3. **Empirical replication** — Hou-Xue-Zhang 2020: 447 anomaly NYSE-VW, ~%64 insig at 5%; q-factor lens net %10 sig

**Dört darbe çerçevesi** (Cycle 13-14): in-sample large-cap + post-pub decay + MT-corrected sig + replication-robust. 5. darbe açılmadı (Cycle 14 disiplin meta-not testi geçti). Cycle 27 JKP 2023 Bayesian Empirical Bayes hierarchical anti-conservative-side ek bacak (3. contradictions entry HXZ↔JKP scope-dependent ~50pp gap).

### Dört methodology zinciri

| Zincir | Paper × yıl | Origin → Modern halka |
|--------|-------------|------------------------|
| **Sloan zinciri** (mispricing/accruals) | 4 paper × 23 yıl | Sloan 1996 → Piotroski 2000 F_ACCRUAL → Mohanram 2005 G3 → Asness 2019 QMJ ACC |
| **Profitability zinciri** | 4 paper × 7 yıl | Novy-Marx 2013 GP/A → FF15 RMW Ope → Asness QMJ GPOA → Ball-GLN 2016 Cop |
| **F bloğu intangibles 4-katmanlı** | 4 paper × 24 yıl | Lev-Sougiannis 1996 (Knowledge) + Eisfeldt-Papanikolaou 2013 (Organization) + Peters-Taylor 2017 (Total) + Lev-Srivastava 2020 (Application) |
| **Composite mispricing scoring** | 4 paper × 17 yıl | Piotroski F-Score → Mohanram G-Score → Stambaugh-Yuan 2017 MGMT/PERF → JKP 2023 13 theme cluster |

### 4/4 hayatta kalan factor adayları (HXZ 2020 dört darbe çerçevesi)

| Factor | Methodology | Cycle |
|--------|-------------|-------|
| Sloan operating accruals (Oa) | Sloan zinciri origin; q-factor alpha −0.54%/ay sig | 9 |
| R&D-to-market (Rdm) | NDX-relevant; q-factor alpha 0.7%/ay sig | 13 |
| Earnings announcement Abr | PEAD; q-factor alpha 0.66%/ay sig | 13 |
| Cash-based op profits (Cop) | Profitability zinciri 4. halka; q-factor alpha 0.69%/ay sig; tangency Sharpe 4F+Cop=1.67 ⭐ | 38 |

### Wiki yapısal pozisyonlar (REJECT listesi)

- **Vanilla HML** — REJECT large-cap evrene transferi (post-2010 collapse + size-conditional + B/M big-stock weakness üçlü teyit)
- **SMB vanilla** — REJECT (Q11 fully-answered ASTERISK üç-paper sertleştirme)
- **F-Score standalone large-cap** — REJECT (BM-Q5 only kalibre; F&V/P combined tercih)
- **Magic Formula** — REJECT (q5 captures + microcap residual)
- **RMW Ope standalone** — REJECT (q-factor INSIG + size-conditional zayıf); QMJ Profitability composite + Cop standalone tercih

Detay: [`wiki/meta/executive_summary.md`](wiki/meta/executive_summary.md) §4.

---

## Faz Durumu (post-Cycle 41)

| Faz | Durum | Tarih | Sertifika |
|-----|-------|-------|-----------|
| **Faz 0** — scaffold | ✅ | 2026-04-27 | — |
| **Faz 1** — Tier 1 ingest (Cycle 1-20) | ✅ | 2026-05-01 | **YUMUŞAK** (epistemik tamlık + sayısal 76%) |
| **Faz 2** — synthesis + strategy aday + methodology infrastructure (Cycle 21-31) | ✅ | 2026-05-02 | **TAM** (11/11 yapısal kriter) |
| **Faz 3** — strategy formal spec + Faz 3 seçici ingest + §11.5 consolidation (Cycle 32-41) | ✅ | 2026-05-02 | **YUMUŞAK** (kriter #1-5 ✅ wiki içi; #6-9 wiki dışı P123 delegated; #10 N/A yaşayan-proje çerçevesinde) |
| 🟢 **Yaşayan-proje** (Cycle 42+) | aktif | 2026-05-03 | — (cycle numarası post-Faz 3 update kategorisinde devam) |

Sertifika anchor sayfaları:
- [`wiki/meta/handoff_faz2.md`](wiki/meta/handoff_faz2.md) — Faz 1 → Faz 2 YUMUŞAK
- [`wiki/meta/handoff_faz3.md`](wiki/meta/handoff_faz3.md) — Faz 2 → Faz 3 TAM + Cycle 41 Faz 3 YUMUŞAK
- [`wiki/meta/handoff_backtest.md`](wiki/meta/handoff_backtest.md) — Cycle 41 wiki yaşayan-proje statüsüne geçiş
- [`wiki/meta/handoff_post_faz3_001.md`](wiki/meta/handoff_post_faz3_001.md) — post-Faz 3 ilk context handoff'u (en güncel)

---

## Backtest Projesi (Wiki Dışı)

Faz 3 sertifika kriter #6-9 (backtest implementation + factor selection + tangency portfolio + DSR/walk-forward/bootstrap) **wiki dışı ayrı projede** yürütülür:

| Item | Spec |
|------|------|
| **Repo** | `equity-alpha-backtest` (yeni, ayrı; henüz açılmadı) |
| **Platform** | [Portfolio123 Ultimate](https://www.portfolio123.com/) ($389/ay; 20-yıl backtest + Position Sizing + Optimizer + Regression + AI Factor) |
| **Veri** | P123 point-in-time (CRSP + Compustat lifelong-included) + opsiyonel FMP / SEC EDGAR override |
| **Sample** | 2010-2024 backtest + 2025+ canlı uygulama |
| **Capital** | $1M; sp500_v1 + nasdaq100_v1 ~%50/%50 split |
| **Drawdown tolerance** | %50 |
| **Rebalance** | Annual June + Quarterly drift check güvenlik valfı |

Detay: [`wiki/meta/handoff_backtest.md`](wiki/meta/handoff_backtest.md) (5. handoff dokümanı; 8 bölüm — kapsam + döngüsel öğrenme + P123 mapping + implementation notes + 4-6 hafta roadmap + geri rapor protokolü + yaşayan-proje protokolü).

### Wiki ↔ Backtest döngüsel öğrenme

```
   Wiki teori (yaşayan-proje, ~88 sayfa)
              │
              │ (strategy spec → P123 implementation)
              ▼
   Backtest projesi (P123 Ultimate)
              │
              │ (backtest sonuç → wiki/backtests/p123_*.md paper-form rapor)
              ▼
   Wiki sentez güçlenir (v1 → v2 evrim aday; CLAUDE.md §12.3)
              │
              │ (yeni paper ingest + cycle devam)
              ▼
   Wiki teori (güncellenmiş)
```

---

## Yazma Disiplini (NON-NEGOTIABLE)

[`CLAUDE.md`](CLAUDE.md) §6 + §9'da tam liste. Özet:

1. **Sayısal iddia kaynaksız geçemez** — her sayı paper sayfa atfı (`[Paper Year, Tablo N]`) veya `[[wikilink]]` ile gerekçelendirilir
2. **Memory/training'den ekleme YASAK** — wiki sadece `raw/`'daki kaynaklara dayanır; "genel olarak literatürde bilinir ki..." yasak
3. **Hedge'ler yasak** ("muhtemelen", "genelde", "etkili olabilir") — ya sayı ya kaynak
4. **Çelişen kanıtlar gizlenmez** — `wiki/meta/contradictions.md`'de cross-reference (3 entry kayıtlı)
5. **YAML frontmatter zorunlu** — paper + factor + concept + strategy + methodology + backtest_report şablonlarında
6. **Wikilink syntax**: `[[page_name]]` (Obsidian-uyumlu)
7. **Türkçe wiki, paper isimleri/dergi isimleri İngilizce kalır** (CLAUDE.md kural 6.6)

## Self-Audit Cycles (CLAUDE.md §11)

Wiki büyüdükçe kullanıcının elle kontrol yapması sürdürülemez. Claude her ingest sonu **kendi kendini denetler**:

- **§11.2 6-spot audit** her ingest sonrası otomatik (A factor entity + B Goal Alignment 4 eksen + C concept zenginleşmesi + D inbound link + E meta + F open_questions/data_gaps)
- **§11.5 4-cycle ardışık consolidation pass** zorunlu (Cycle 4/8/12/16/20/24/28/32/36/40/44/...)
- **§12 post-Faz 3 yaşayan-proje bakım protokolü** (Cycle 42 schema_update): executive_summary güncelleme kadansı + backtest geri rapor `wiki/backtests/` ingest yolu + v1 → v2 evrim historic preservation

Kullanıcı bu sistemde **denetçi** rolünde, **operatör** değil. Operatör Claude.

---

## İlgili

- Karpathy `llm-wiki` pattern: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
- Claude Code: https://claude.com/claude-code
- Portfolio123: https://www.portfolio123.com/

## Lisans

Kişisel araştırma projesi; kaynak paperlar (`raw/`) kendi yazarlarının/dergilerinin telif hakkında. Wiki sentezi (`wiki/`) MIT veya muadili — kullanıcı kararı (henüz lisans dosyası eklenmedi).

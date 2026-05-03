# equity-alpha-wiki

Karpathy [`llm-wiki`](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
pattern'ini empirical asset pricing literatürüne uygulayan kişisel araştırma wiki'si.

**Hedef:** S&P 500 ve Nasdaq 100 evrenlerinde, finansal tablo verilerini kullanarak
yıllık-frekansta en yüksek getiriyi sağlayacak hisseleri seçen sistematik bir
strateji tasarlamak.

## Hızlı giriş

Hızlı bir özet için: **[`wiki/meta/executive_summary.md`](wiki/meta/executive_summary.md)**.

Detaylı katalog: `wiki/index.md` + `wiki/meta/MoC_papers.md` + `wiki/meta/MoC_factors.md`.

## Kullanım

Bu repo Claude Code ile kullanılmak üzere tasarlandı.

```bash
git clone <this-repo>
cd equity-alpha-wiki
claude
```

Claude'un ilk yapacağı şey `CLAUDE.md`'yi okumaktır — orada operasyon kuralları var.

Tipik workflow (yaşayan-proje statüsünde):

```
> raw/papers/ klasörüne yeni paper koydum, ingest et
> F bloğu intangibles 4-katmanlı methodology'i özetler misin?
> P123 backtest sonuçlarını paper-form raporla (geri rapor)
> consolidation pass yap (4-cycle ardışık disiplin)
```

## Yapı

- `CLAUDE.md` — schema, kurallar, workflow'lar (Claude için; §1-11 disiplin protokolü)
- `raw/` — kaynak dosyalar (immutable; PDF/TXT)
- `wiki/` — sentez (LLM-yazılı, LLM-bakımlı; ~87 sayfa)
  - `papers/` (28) — her ingested kaynak için özet sayfası
  - `factors/` (20) — her sinyal/faktör için entity sayfası
  - `concepts/` (17) — kavram hub'ları
  - `comparisons/` (1) — karşılaştırma sayfaları
  - `strategies/` (5) — v0_draft historic + v1_draft historic + sp500_v1 + nasdaq100_v1 + known_weaknesses
  - `methodology/` (3) — backtest_spec + data_sources + backtest_implementation_plan
  - `meta/` (10) — index, MoC, open_questions, contradictions, data_gaps, source_tier_list, 5 handoff doküman, executive_summary

## Faz Durumu (post-Cycle 41)

- [x] **Faz 0** — scaffold
- [x] **Faz 1** — Tier 1 sources ingest (Cycle 1-20; YUMUŞAK sertifika 2026-05-01)
- [x] **Faz 2** — synthesis + Tier 2 sources + strategy aday + methodology infrastructure (Cycle 21-31; **TAM** sertifika 2026-05-02)
- [x] **Faz 3** — strategy formal spec + Faz 3 seçici ingest 4 paper + §11.5 consolidation pass'ler (Cycle 32-41; **YUMUŞAK** sertifika 2026-05-02)
- 🟢 **Wiki yaşayan-proje statüsünde**: yeni paper ingest + backtest sonuç geri rapor + cycle numarası post-Faz 3 update kategorisinde devam

## Backtest Projesi (Wiki Dışı)

Faz 3 sertifika kriter #6-9 (backtest implementation + factor selection + tangency portfolio + DSR/walk-forward/bootstrap) **wiki dışı ayrı projede** yürütülür:

- **Repo**: `equity-alpha-backtest` (yeni, ayrı)
- **Platform**: Portfolio123 Ultimate
- **Detay**: [`wiki/meta/handoff_backtest.md`](wiki/meta/handoff_backtest.md) (5. handoff dokümanı)

Wiki ↔ Backtest projesi **döngüsel öğrenme**: wiki teori → P123 implementation → backtest sonucu wiki'ye paper-form geri rapor → wiki sentez güçlenir → v1→v2 evrim aday.

# Equity Alpha Wiki

> Sistematik fundamental stock-selection literatürünün kümülatif, çapraz-referanslı
> bir bilgi tabanı. **Hedef:** S&P 500 ve Nasdaq 100 evrenlerinde yıllık-frekansta
> en yüksek getiriyi sağlayacak hisseleri seçen bir strateji tasarlamak.

## Hızlı navigasyon

- **[[meta/executive_summary]]** ⭐ — yöneticisel özet (proje amacı + ana tez + sinyal aileleri + S&P 500 / NDX strateji + çelişkiler + bakım protokolü)
- **[[index]]** — tüm sayfaların kataloğu (87 sayfa, kategorize)
- **[[log]]** — operasyon kronolojisi (61 entry, Cycle 0-41)
- **[[meta/MoC_papers]]** — paper'lar (kronolojik + tematik; 28 paper)
- **[[meta/MoC_factors]]** — faktörler (kategori bazında; 20 factor entity)
- **[[meta/open_questions]]** — wiki'de henüz cevaplanmamış sorular (82 Q; 9 fully-answered)
- **[[meta/contradictions]]** — kaynaklar arası çelişkiler (3 entry)
- **[[meta/data_gaps]]** — eksik konular, aranması gereken kaynaklar
- **[[meta/source_tier_list]]** — okunması gereken kaynak listesi (tier'lı)
- **[[meta/handoff_backtest]]** — wiki ↔ backtest projesi geçiş (5. handoff; Cycle 41 yaşayan-proje)

## Çalışma şekli (yaşayan-proje statüsünde)

Bu wiki'yi sen yazmıyorsun, Claude (LLM) yazıyor. Workflow:

1. `raw/` altına kaynak (PDF, makale) ekliyorsun.
2. Claude'a `ingest <slug>` diyorsun → paper sayfası + ilgili factor/concept güncellemesi + index + log + §11.2 6-spot audit.
3. Soru sorduğunda, Claude wiki'den `[[link]]`'lerle cevap veriyor (memory/training kullanımı yasak; CLAUDE.md §6.4 + §9).
4. Her 4 cycle'da bir §11.5 ZORUNLU consolidation pass (orphan + çelişki + stale claim + MoC + broken wikilink).
5. Strategy formal spec'leri (`strategies/sp500_v1.md` + `nasdaq100_v1.md` + `known_weaknesses.md`) Cycle 32-34'te yazıldı; backtest implementation **P123 platformunda** yürütülüyor (bkz. `wiki/meta/handoff_backtest.md`).
6. Backtest sonuçları geldiğinde paper-form ingest (`papers/p123_backtest_*.md`) → wiki sentez güçlenir → v1→v2 evrim trigger değerlendirilir (Cycle 30 historic preservation pattern).

Detaylı kurallar: `CLAUDE.md` §1-11.

## Üç katman

```
raw/   ← immutable kaynak dosyalar (PDF, vb.)
wiki/  ← LLM-yazılı, LLM-bakımlı sentez (markdown)
CLAUDE.md ← schema (operasyon kuralları)
```

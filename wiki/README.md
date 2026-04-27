# Equity Alpha Wiki

> Sistematik fundamental stock-selection literatürünün kümülatif, çapraz-referanslı
> bir bilgi tabanı. **Hedef:** S&P 500 ve Nasdaq 100 evrenlerinde yıllık-frekansta
> en yüksek getiriyi sağlayacak hisseleri seçen bir strateji tasarlamak.

## Hızlı navigasyon

- **[[index]]** — tüm sayfaların kataloğu
- **[[log]]** — operasyon kronolojisi
- **[[meta/MoC_papers]]** — paper'lar (kronolojik + tematik)
- **[[meta/MoC_factors]]** — faktörler (kategori bazında)
- **[[meta/open_questions]]** — wiki'de henüz cevaplanmamış sorular
- **[[meta/contradictions]]** — kaynaklar arası çelişkiler
- **[[meta/data_gaps]]** — eksik konular, aranması gereken kaynaklar
- **[[meta/source_tier_list]]** — okunması gereken kaynak listesi (tier'lı)

## Çalışma şekli

Bu wiki'yi sen yazmıyorsun, Claude (LLM) yazıyor. Sen:

1. `raw/` altına kaynak (PDF, makale) ekliyorsun.
2. Claude'a `ingest <slug>` diyorsun.
3. Claude paper sayfası yazıyor, ilgili faktör/kavram sayfalarını güncelliyor,
   index ve log'u güncelliyor.
4. Soru sorduğunda, Claude wiki'den cevap veriyor — `[[link]]`'lerle.
5. Yeterince kaynak biriktiğinde `build strategy` diyorsun, Claude
   `/wiki/strategies/`'de aday strateji yazıyor.

Detaylı kurallar: `CLAUDE.md`.

## Üç katman

```
raw/   ← immutable kaynak dosyalar (PDF, vb.)
wiki/  ← LLM-yazılı, LLM-bakımlı sentez (markdown)
CLAUDE.md ← schema (operasyon kuralları)
```

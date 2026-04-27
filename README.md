# equity-alpha-wiki

Karpathy [`llm-wiki`](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
pattern'ini empirical asset pricing literatürüne uygulayan kişisel araştırma wiki'si.

**Hedef:** S&P 500 ve Nasdaq 100 evrenlerinde, finansal tablo verilerini kullanarak
yıllık-frekansta en yüksek getiriyi sağlayacak hisseleri seçen sistematik bir
strateji tasarlamak.

## Kullanım

Bu repo Claude Code ile kullanılmak üzere tasarlandı.

```bash
git clone <this-repo>
cd equity-alpha-wiki
claude
```

Claude'a ilk yapacağı şey `CLAUDE.md`'yi okumaktır — orada operasyon kuralları var.

Ardından tipik workflow:

```
> raw/papers/ klasörüne piotroski2000.pdf koydum, ingest et
> F-Score'un Nasdaq 100'de test edildiği kanıt var mı?
> lint pass yap
> build strategy v0
```

## Yapı

- `CLAUDE.md` — schema, kurallar, workflow'lar (Claude için)
- `raw/` — kaynak dosyalar (immutable)
- `wiki/` — sentez (LLM-yazılı, LLM-bakımlı)

## Faz

- [x] Faz 0 — scaffold
- [ ] Faz 1 — Tier 1 sources ingest (~25 paper)
- [ ] Faz 2 — synthesis + Tier 2 sources
- [ ] Faz 3 — strategy design (S&P 500 + Nasdaq 100 ayrı ayrı)

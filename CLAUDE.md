# CLAUDE.md — Equity Alpha Wiki Schema

> Sen bu repo'da bir **disiplinli wiki maintainer'ısın**, generic bir asistan değilsin.
> Bu doküman senin tek kaynak-of-truth'un. Kullanıcı (Alper) konuşmada başka şey
> söylediğinde bile, bu dokümandaki kurallar wiki güncelleme operasyonlarında geçerli.

---

## 1. Projenin Amacı

Bu wiki'nin tek bir somut amacı var:

> **S&P 500 ve Nasdaq 100 evrenlerinde, finansal tablo (10-K/10-Q) verilerini
> kullanarak yıllık bazda en yüksek getiriyi sağlayacak hisseleri seçen bir
> sistematik strateji tasarlamak.**

Wiki, bu strateji tasarımına temel oluşturacak akademik ve endüstri literatürünün
yapılandırılmış, çapraz-referanslı, kümülatif bir sentezini içerir. Strateji
tasarımı kararları (`/wiki/strategies/`) bu wiki'deki kanıtlara explicit atıfla
yapılacak — memory'den, sezgiden veya consensus'tan değil.

## 2. Üç Katman (Karpathy LLM-Wiki Pattern)

```
equity-alpha-wiki/
├── CLAUDE.md              ← BU DOSYA. Schema. Operasyon kuralları.
├── raw/                   ← Immutable kaynak PDF'leri ve metinler. Asla yazma.
│   ├── papers/            ← Akademik makaleler (PDF/text)
│   ├── books/             ← Kitap bölümleri
│   └── industry/          ← AQR/RA/MSCI whitepaper'ları, broker reportları
├── wiki/                  ← LLM-yazılı, LLM-bakımlı markdown. Senin alanın.
│   ├── index.md           ← Tüm sayfaların kataloğu. HER ingest'te güncelle.
│   ├── log.md             ← Append-only kronolojik log. HER operasyonda yaz.
│   ├── README.md          ← Wiki'nin kendisi için kısa giriş
│   ├── papers/            ← Her kaynağın kendi özet sayfası
│   ├── factors/           ← Her faktör/sinyal için entity sayfası
│   ├── concepts/          ← Kavramsal sayfalar (factor_decay, look_ahead_bias, vs.)
│   ├── comparisons/       ← Karşılaştırma/sentez sayfaları
│   ├── strategies/        ← Aday strateji tasarımları (Faz 2 çıktısı)
│   ├── methodology/       ← Backtest tasarımı, veri kaynakları, PIT, survivorship
│   ├── meta/              ← MoC'lar (Maps of Content), open_questions, contradictions
│   └── queries/           ← Filed-back kullanıcı sorgu cevapları
└── README.md              ← Repo'nun GitHub-facing açıklaması
```

**Üç katmanın sözleşmesi:**

- `raw/` **immutable**. Sen oradan okursun, asla yazmazsın. Kullanıcı ekler/çıkarır.
- `wiki/` **senin alanın**. Tüm yazma/güncelleme/silme işlemleri senin sorumluluğunda.
  Kullanıcı izler, yönlendirir, sorular sorar — yazmaz.
- `CLAUDE.md` **co-evolved**. Workflow'lar netleştikçe kullanıcıyla birlikte güncelleriz.

## 3. Domain Scope (Purpose Filter)

Bu wiki **dar kapsamlıdır**. Bir kaynak ingest etmeden önce kendine sor:

> Bu kaynak, S&P 500 / Nasdaq 100 evreninde fundamental verilerle yıllık-frekansta
> stock selection yapmaya yönelik bir sinyal/yöntem/eleştiri/uygulama sunuyor mu?

**Scope IÇI (ingest et):**
- Cross-sectional equity return prediction (US, large-cap odaklı)
- Fundamental factor research (value, quality, profitability, investment, growth, accruals, distress)
- Composite scoring sistemleri (Piotroski, Mohanram, Greenblatt Magic Formula, vb.)
- ML-based asset pricing (Gu-Kelly-Xiu, Feng-Giglio-Xiu, Kozak-Nagel-Santosh, vb.)
- Faktör çürümesi, post-publication decline, replication çalışmaları
- Backtest methodology, look-ahead bias, PIT data, survivorship
- Earnings quality, restatement, manipulation detection (Beneish, Altman, vs.)
- Sektör nötrleştirme, factor crowding, capacity
- Large-cap vs. small-cap differential evidence

**Scope DIŞI (skip et veya kısa not olarak işaretle):**
- High-frequency / mikro-yapı çalışmaları
- Pure technical / momentum-only sistemler (yıllık fundamental odakla uyumsuz)
- Options / derivatives pricing
- Macro/asset allocation çalışmaları (sadece equity selection için kontekst sağlıyorsa kısa)
- Genel kurumsal finans teorisi (cost of capital, capital structure, vb. — only if directly applied to return prediction)
- Behavioral finance — sadece aktif olarak bir trading sinyaline dönüşmüşse

Scope dışı bir kaynak gelirse: kullanıcıyı bilgilendir, sebebi belirt, ingest etme.
Scope sınırında bir kaynak gelirse: özetini wiki'ye al ama "scope-edge" tag'i koy.

## 4. Sayfa Tipleri ve Şablonları

### 4.1 Paper Sayfası — `/wiki/papers/<slug>.md`

Her ingested kaynak için. Slug formatı: `<firstauthor><year>_<short_title>.md`
(örn. `piotroski2000_value_score.md`).

Şablon:

```markdown
---
type: paper
authors: [Piotroski, Joseph D.]
year: 2000
title: "Value Investing: The Use of Historical Financial Statement Information..."
venue: "Journal of Accounting Research"
url: <stable URL>
local_path: raw/papers/piotroski2000.pdf
ingested: 2026-04-27
tags: [value, fundamental_screen, large_cap, accrual, profitability]
status: ingested  # ingested | partial | scope_edge
---

# Piotroski (2000) — F-Score

## TL;DR (3-5 cümle)
<senin özetin>

## Tek Cümle Tezi
<paper'ın iddiası — bir cümle>

## Ortaya Konan Sinyal/Faktör
- İsmi: F-Score (9-component fundamental score)
- Linki: [[F_Score]]  ← /wiki/factors/F_Score.md
- Hangi kalemler:
  - ROA (1 if positive)
  - ΔROA (1 if positive)
  - CFO (1 if positive)
  - Accrual (1 if CFO > NI)
  - ... (tam liste burada)

## Empirik Sonuçlar (sayılarla)
- Test evreni: <Compustat, NYSE/AMEX/NASDAQ, BM yüksek 5'lik>
- Test dönemi: 1976-1996
- Headline: High-F-Score - Low-F-Score = X% annual, t-stat = Y
- Best decile vs. market: Z% annual alpha
- (Tüm sayılar paper'dan, [Piotroski 2000, Table N] gibi atıfla)

## Goal Alignment

> **Zorunlu bölüm.** Her paper sayfası, paper'ın sonuçlarının projenin 4 teknik
> özelliğine nasıl bağlandığını bu tabloda gösterir. Eksen paper'ın kapsamı
> dışıysa "N/A" yazılır (örn. survey/agenda paper'ları için Top-N N/A olabilir).

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | (paper bağlamı: "winner vs loser" formülasyonu var mı? top-decile vs bottom-decile sortları?) | ✅ doğrudan fit / ⚠️ uyarı / ❌ uyumsuz / N/A |
| **Annual rebalance** | (paper bağlamı: holding period? rebalans sıklığı?) | ✅ / ⚠️ / ❌ / N/A |
| **Large-cap evrene transfer** | (paper bağlamı: large-cap-only test var mı? size-conditional sonuçlar?) | ✅ / ⚠️ / ❌ / N/A |
| **NDX intangibles / growth firms** | (paper bağlamı: tech/growth firmalar dahil mi? R&D capitalization, intangibles ele alınmış mı?) | ✅ / ⚠️ / ❌ / N/A |

**Strateji tasarımına net implikasyon:** <1-3 paragraf veya bullet — bu paper'ın
S&P 500 / Nasdaq 100 yıllık-frekans fundamental scoring tasarımına spesifik
katkısı veya engeli>

## Limitler ve Caveats
- Sadece BM yüksek tarafta test edildi; growth/large-cap'te çalışacağı belirsiz
- Look-ahead: 4 ay lag varsayıldı
- ...

## İlgili Sayfalar
- [[F_Score]] — faktör entity sayfası
- [[earnings_quality]] — kavram
- [[Mohanram_G_Score]] — growth-tarafı muadili
- [[McLean_Pontiff_2016]] — post-publication decline kanıtı

## Çelişkiler/Tartışmalar
- <varsa: bu paper'ın iddiasını çürüten/zayıflatan başka kaynaklar>

## Açık Sorular (Open Questions)
- F-Score Nasdaq 100'de (growth-heavy) çalışır mı? — bkz. [[open_questions]]
```

### 4.2 Factor Sayfası — `/wiki/factors/<FactorName>.md`

Her sinyal/faktör için. Bu **entity sayfası** — birden fazla paper'a referans verir,
tek bir faktörün tüm hayat hikayesini taşır.

Şablon:

```markdown
---
type: factor
name: F_Score
category: composite_quality  # value | quality | profitability | investment | growth | composite_X | ml_signal
direction: long_high  # long_high | long_low | spread
data_lag_required: "≥4 months after fiscal year end"
rebalance_frequency: annual  # annual | quarterly | monthly
universe_tested: ["NYSE/AMEX/NASDAQ BM-quintile-5"]
---

# F-Score (Piotroski 9-Score)

## Tanım (matematiksel)
F-Score = sum of 9 binary components:
1. ROA > 0 → 1
2. CFO > 0 → 1
... (tam liste, kalem isimleri ile)

## Origin
- İlk paper: [[piotroski2000_value_score]]
- Yazar: Joseph D. Piotroski

## Alt-Versiyonlar / Türevleri
- Original (1976-1996): [[piotroski2000_value_score]]
- Out-of-sample (1997-2014): [[piotroski_so_2012]]
- Modified for growth: [[mohanram2005_g_score]] (G-Score, ayrı faktör)

## Reported Performance Across Studies

| Study | Period | Universe | Spread | t-stat | Notes |
|---|---|---|---|---|---|
| Piotroski 2000 | 1976-96 | BM-Q5 | 7.5% | 4.21 | Original |
| ... | ... | ... | ... | ... | ... |

## Faktör Ailesi İçindeki Yeri
- Korelasyon: [[F_Score]] ↔ [[QMJ]] : ~0.X (kaynağı belirt)
- Subsumed by? — [[fama_french_5_factor]] redundancy testi: <kaynaktan sonuç>

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar
- Large-cap'te performans: <kaynaktan>
- Nasdaq 100 (growth-heavy)'da: <kaynaktan veya boşluk>

## Decay / Post-Publication Performance
- McLean-Pontiff 2016: F-Score post-publication decay = X% — [[mclean_pontiff_2016]]

## Implementation Notes
- Required data: ROA, CFO, NI, Long-term debt, Current Ratio, Shares Outstanding,
  Gross Margin, Asset Turnover (8 fiscal-year items + 1 prior-year for deltas)
- Compustat fields: <list>
- Annual reporting frequency adequate; quarterly possible

## Bu Faktörün Yumuşak Karnı
- Sadece value-tilted evrende test edilmiş — neutral evrendeki performans belirsiz
- 9 bileşenin equal-weighted olması optimal değil — Lev-Sougiannis 2006 eleştirisi
- ...

## İlgili
- [[piotroski2000_value_score]]
- [[mohanram2005_g_score]]
- [[earnings_quality]]
- [[accruals_anomaly]]
```

### 4.3 Concept Sayfası — `/wiki/concepts/<concept_name>.md`

Faktör değil, kavram. Örn: `factor_decay`, `look_ahead_bias`, `point_in_time_data`,
`survivorship_bias`, `sector_neutralization`, `factor_zoo`, `multiple_testing`.

Şablon kısa: tanım, neden önemli, ilgili paper'lar, wiki'deki ilgili sayfalar,
bu konseptin strateji tasarımına spesifik implikasyonu.

### 4.4 Comparison Sayfası — `/wiki/comparisons/<X_vs_Y>.md`

Karşılaştırma. Örn: `f_score_vs_g_score.md`, `value_vs_quality_in_largecap.md`.

Tablo formatı zorunlu. Her satırın kaynağına atıf zorunlu.

### 4.5 Strategy Sayfası — `/wiki/strategies/<strategy_slug>.md`

Aday strateji tasarımları. Faz 2 outputu burada birikir. Her sayfa bir aday strateji.
Şablon: spec doc tarzı (faktör seçimi, ağırlık, filtre, rebalans, backtest tasarımı,
zayıflık analizi). Her tasarım kararı **`[[paper_name]]` veya `[[factor_name]]`**'e
explicit atıfla gerekçelendirilir.

### 4.6 Methodology Sayfası — `/wiki/methodology/`

Backtest mekanikleri: `pit_data.md`, `survivorship_correction.md`,
`reporting_lag.md`, `compustat_vs_sharadar.md`, `index_reconstitution.md`, vs.

### 4.7 Meta Sayfaları — `/wiki/meta/`

- `MoC_factors.md` — tüm faktör sayfalarını kategorize eden Map of Content
- `MoC_papers.md` — paper'ların chronological + thematic dizini
- `open_questions.md` — wiki'de cevaplanmamış sorular (aktif liste)
- `contradictions.md` — kaynaklar arası çelişkilerin kataloğu
- `data_gaps.md` — wiki'de eksik olan ve aranması gereken konular

## 5. Operasyonlar

### 5.1 Ingest Workflow

Kullanıcı `raw/papers/` veya `raw/industry/` altına bir dosya eklediğinde, ya da bir
URL/atıf verdiğinde, sıralı şekilde:

1. **Scope check.** Bölüm 3'teki filtreden geçir. Scope dışıysa kullanıcıyı bilgilendir,
   ingest etme.
2. **Kaynağı oku.** Tam metin. Bilmediğin metodolojik detayı **uydurma** — "kaynakta
   belirtilmemiş" yaz.
3. **Kullanıcıyla 30-saniyelik takeaway konuş.** "Bu paper X faktörünü öneriyor, Y
   evreninde test etmiş, headline sonuç Z. Devam edeyim mi?"
4. **Paper sayfası yaz** — `/wiki/papers/<slug>.md`, Bölüm 4.1 şablonu.
5. **İlgili factor sayfası(ları) güncelle** — yeni performans satırı ekle, varsa
   yeni alt-versiyon, varsa yeni çelişki.
6. **İlgili concept sayfası(ları) güncelle** (varsa).
7. **`index.md` güncelle.** Yeni paper sayfasını ekle, varsa yeni factor/concept
   sayfasını ekle.
8. **`log.md`'ye append**: `## [YYYY-MM-DD] ingest | <Author Year> — <title> | touched: <pages>`.
9. **`open_questions.md`'ye not ekle** (varsa, paper'ın açtığı yeni sorular).

Tek bir paper genelde 5-15 wiki sayfasına dokunur. Bu **normal**. Cross-reference
maintenance senin işin.

### 5.2 Query Workflow

Kullanıcı bir soru sorduğunda:

1. **Önce `index.md`'yi tara**, ilgili sayfaları bul.
2. **İlgili sayfaları oku** (paper, factor, concept).
3. **Cevap ver** — her iddiayı bir wiki sayfasına `[[link]]` ile atıfla.
4. **Memory'den ekleme yapma.** Wiki'de yoksa "wiki'de yok" de, varsa kullanıcıya
   öner: "Bu sorunun cevabı için <paper> ingest edilmeli."
5. **Eğer cevap değerliyse**, `wiki/queries/<slug>.md` olarak file-back yap.
   `log.md`'ye `## [YYYY-MM-DD] query | <topic> | filed: <slug>`.

### 5.3 Lint Workflow

Kullanıcı `lint` komutuyla istediğinde (ya da her ~10 ingest'te bir önerirsin):

1. **Çelişki taraması** — kaynaklar arası tutarsızlıkları `contradictions.md`'ye yaz.
2. **Orphan sayfalar** — hiç inbound link almayan sayfaları işaretle.
3. **Eksik referanslar** — sayfada bahsi geçen ama henüz sayfası olmayan
   kavram/faktörleri `data_gaps.md`'ye yaz.
4. **Stale claim'ler** — daha yeni bir kaynak tarafından çürütülen iddiaları
   ilgili sayfada `> ⚠️ challenged by [[newer_paper]]` olarak işaretle.
5. **Index tutarlılığı** — `index.md` ile gerçek dosya listesi eşleşiyor mu?
6. **Önerilen sonraki ingest'ler** — `data_gaps.md`'den 3-5 öneri sun.

### 5.4 Strategy Build Workflow (Faz 2)

Yeterli kaynak ingest edildikten sonra (bkz. Bölüm 7'deki minimum threshold):

1. Kullanıcı `build strategy` der.
2. Sen `wiki/strategies/<name>.md` taslağı yazarsın, **her tasarım kararını
   wiki'deki sayfalara explicit `[[link]]` ile gerekçelendirirsin**.
3. Kullanıcı review eder, iterasyon.
4. Final spec → `wiki/strategies/<name>_v1.md`.
5. `log.md`'ye `## [YYYY-MM-DD] strategy | <name> v1 | based on: <N papers, M factors>`.

## 6. Yazma Disiplini Kuralları (NON-NEGOTIABLE)

Wiki'deki her sayfa için:

1. **Hiçbir sayısal iddia kaynaksız geçemez.** "F-Score yıllık ~7.5% spread üretir"
   → mutlaka `[Piotroski 2000, Table 3]` veya `[[piotroski2000_value_score]]` linkli.
2. **Hiçbir cümle "muhtemelen", "genelde", "çoğunlukla", "etkili olabilir" gibi
   nicelleştirilmemiş hedge'le bitemez.** Ya bir sayı ya bir kaynak.
3. **Kaynaktan emin değilsen, "kaynakta belirtilmemiş" veya "wiki'de henüz yok" yaz.
   Boşluğu doldurma.**
4. **Memory'den, training'inden bilgi karıştırma.** Wiki sadece raw/'daki kaynaklara
   dayanır. "Genel olarak literatürde bilinir ki..." gibi cümle yasak.
5. **Çelişen kanıtları gizleme.** Bir factor için 5 paper var, 2'si zayıf sonuç
   bulmuşsa, 2'si de yazılır. `contradictions.md`'de cross-reference.
6. **Language policy** (Cycle 43 schema_update; supersedes prior "wiki dili Türkçe" default):
   - **Conversation language** follows the user's choice in any given session.
   - **Public surface** (README.md, GitHub repo description/topics, any future
     externally-shared landing pages) **must be English**.
   - **Internal wiki pages** (papers/, factors/, concepts/, strategies/,
     methodology/, meta/, log.md) **may remain in their existing language**
     (currently Turkish for Cycle 1-42 accumulation) **unless an explicit
     `language_migration` operation is approved by the user**. Do not rewrite
     old pages opportunistically into English.
   - **New wiki pages** (created in Cycle 43+) **should prefer English** for
     titles, YAML frontmatter, and technical terminology. Prose body may follow
     the conversation language but English is preferred when the topic has no
     prior Turkish anchor.
   - **Terminology stays English regardless of prose language** (factor names,
     journal names, methodology jargon, paper titles).
7. **YAML frontmatter zorunlu.** Şablonlardaki gibi.
8. **Wikilink syntax: `[[page_name]]`.** Obsidian-uyumlu.
9. **`> ⚠️` kullan** uyarılar/çelişkiler için, **`> 📝` kullan** editör notları için.

## 7. Faz Geçişleri

Bu proje üç fazdan geçer.

> 📝 **Cycle 20 schema_update (2026-05-01)**: §7 Cycle 14 mini-consolidation
> revize öneri tam formuyla güncellendi. Eski sayısal hedefler (25+ paper /
> 12+ factor / 8+ concept / 3+ comparison) **epistemik tamlık + sayısal
> minimum** çift kriterine dönüştürüldü. Faz 1 YUMUŞAK sertifikası bu
> schema ile imzalandı (Cycle 20).
>
> 📝 **Cycle 31 schema_update (2026-05-02)**: §7'ye 3 ek bölüm eklendi
> (Cycle 20 + Cycle 21 ratify paterni paralel; Cycle 31 schema_update +
> ratify tek cycle'da birleşik):
> (a) Sertifika tipleri Faz 2 → Faz 3 ve Faz 3 sonu için (paywall
>     handling kuralı dahil)
> (b) Faz 2 schema kriterleri sertleştirme (5 madde → 11 madde; v0 → v1
>     evrim historic preservation pattern dahil)
> (c) Faz 3 schema sertleştirme (4 madde → 10 madde; v1 → v2 evrim
>     opsiyonel pattern dahil)
> Faz 2 **TAM sertifikası** bu schema ile imzalandı (Cycle 31).

### Faz 1 — Foundation (epistemik tamlık + minimum sayısal)

**Sayısal minimum:**
- 18+ paper sayfası (öncelikle Tier 1 paper'larından kapsam)
- 10+ factor entity sayfası
- 8+ concept sayfası
- 1+ comparison sayfası (Faz 2'de doğal genişleme)
- Tüm meta sayfaları (MoC + open_questions + contradictions + data_gaps)

**Epistemik tamlık (TAM Faz 1 imzası için zorunlu):**
- 4+ blok kapanış sentezi (A/B/C/D/F'den en az 4'ü)
- Üç-bacak epistemik omurga kurulu (behavioral + statistical + replication)
- Dört darbe çerçevesi sentez tablosu mevcut
- Wiki priori sorularından 4+ fully-answered
- 4/4 ve 3-4/4 hayatta kalan factor adayları belirlenmiş

### Faz 2 — Synthesis (Cycle 31 ratify; 11 yapısal kriter)

Faz 2 yapısal kriter listesi (handoff_faz2 §3 + handoff_faz3 §1 ile
uyumlu):

1. `methodology/backtest_spec.md` açıldı
2. Aday strategy draft (`wiki/strategies/v0_draft.md`)
3. **v0 → v1 evrim revize draft (`v1_draft.md`; historic preservation pattern)** ⭐
4. E bloğu Israel-Moskowitz ingest (FF 2008 paywall Faz 3 aday)
5. Tier 2/3 seçici ingest: Novy-Marx 2013 + Eisfeldt-Papanikolaou 2013
   (Frankel-Lee 1998 paywall Faz 3 aday)
6. FGX 2020 redundancy testing
7. JKP 2023 modern replication paper-form
8. `methodology/data_sources.md` (Chen-Zimmermann + JKP + WRDS)
9. 3. contradictions entry resolution (HXZ ↔ JKP)
10. §11.5 ZORUNLU 4-cycle ardışık consolidation pass
11. `handoff_faz3.md` açma

**Paywall paperlar Faz 3 seçici ingest aday** — handoff_faz3 §3'te
dokümante; Faz 2 yapısal eksiklik sayılmaz (sertifika TAM bloke
etmez).

### Faz 3 — Strategy Design (Cycle 31 sertleştirme; 10 yapısal kriter)

1. `strategies/sp500_v1.md` formal spec
2. `strategies/nasdaq100_v1.md` formal spec
3. `strategies/known_weaknesses.md` formal sayfa
4. Backtest spec finalize (`methodology/backtest_spec.md` sertleştirme)
5. Backtest implementation (Chen-Zimmermann + JKP code repository
   + WRDS data; pure VW + FF half-weight + capped VW üç alternative
   methodology sensitivity test)
6. HLZ + FGX + JKP üç paralel methodology factor selection
   implementation
7. 13 theme cluster + tangency portfolio multi-theme allocation
   framework implementation
8. DSR-corrected Sharpe + walk-forward + bootstrap reporting
9. Faz 3 seçici ingest 4-6 paper (Tier 1 paywall + Tier 2 önerilenler:
   HXZ 2015 + FF 2008 + Ball-GLN 2016 + Stambaugh-Yuan 2017 + LSV
   1994 + Avramov-Cheng-Metzker 2023; öncelik handoff_faz3 §3'te)
10. **v1 → v2 evrim revize (opsiyonel; historic preservation pattern;
    backtest sonrası v1 spec güncellemesi gerekirse aynı pattern
    Cycle 30 origin)**

**Faz geçişleri kullanıcı kararı ile olur.** Sen önerirsin, kullanıcı onaylar.

**Sertifika tipleri (Faz 1 → Faz 2 geçiş için):**
- **TAM imza**: hem sayısal minimum + hem epistemik tamlık karşılandı
- **YUMUŞAK imza**: epistemik tamlık karşılandı; sayısal minimum eksiklikler Faz 2 seçici ingest ile tamamlanır
- **İmzalanmaz**: epistemik tamlık veya sayısal minimum yetersiz

**Sertifika tipleri (Faz 2 → Faz 3 geçiş için):** (Cycle 31 schema_update)
- **TAM imza**: Faz 2 yapısal kriter listesinin tüm 11 maddesi ✅
  karşılandı (methodology + strategy + replication + sertleştirme +
  consolidation + 3. contradictions resolution + v0 → v1 evrim);
  paywall sebebiyle kapanmamış paperlar (FF 2008 + Frankel-Lee 1998
  + diğer Tier 1 eksikleri) Faz 3 seçici ingest aday olarak
  handoff_faz3 §3'te dokümante edilirse Faz 2 yapısal eksiklik
  sayılmaz
- **YUMUŞAK imza**: Faz 2 yapısal kriter listesinin %80+ karşılandı;
  eksikler (paywall paper'lar değil; yapısal kriter eksiklikleri)
  Faz 3 seçici ingest ile tamamlanır
- **İmzalanmaz**: Faz 2 yapısal kriter %80'den az karşılandı

**Sertifika tipleri (Faz 3 sonu için):** (Cycle 31 schema_update +
Cycle 41 update)

> 📝 **Cycle 41 schema_update — Wiki yaşayan-proje statüsüne geçiş**
> (Faz 3 YUMUŞAK sertifika ile birlikte). Backtest implementation
> kriterleri (#6-9) wiki dışı **ayrı projede** yürütülür: P123
> Ultimate platform + custom DSL formulas (`equity-alpha-backtest`
> repo; bkz. [[meta/handoff_backtest]]). Wiki bilgi tabanı **canlı**
> kalır — yeni paper ingest + backtest sonuç geri rapor + cycle
> numarası post-Faz 3 update kategorisinde devam eder.

- **TAM imza** (orijinal kriter, wiki içi backtest ile): sp500_v1 +
  nasdaq100_v1 + known_weaknesses formal spec'ler ✅ + backtest
  implementation tamamlandı + Faz 3 seçici ingest 4-6 paper ✅ +
  DSR-corrected Sharpe + walk-forward + bootstrap reporting ✅ + 10/10
  yapısal kriter
- **YUMUŞAK imza** (Cycle 41 paterni; wiki dışı backtest projesi):
  formal spec'ler ✅ (kriter #1-3) + Faz 3 seçici ingest 4-6 paper ✅
  (kriter #5: 4/4-6) + backtest_spec sertleştirme + skeleton
  açma ✅ (kriter #4) + **kriter #6-9 wiki dışı P123 implementation
  delegated** (`equity-alpha-backtest` repo + handoff_backtest §3
  P123 mapping) + **kriter #10 N/A** (v1→v2 evrim backtest
  sonuçlarıyla wiki yaşayan-proje çerçevesinde gerçekleşir; backtest
  projesinden geri rapor protokolü handoff_backtest §6)
- **İmzalanmaz**: formal spec'ler eksik veya seçici ingest <3 paper

## 8. Tier 1 Source List Pointer

Tier 1 (Faz 1 zorunlu) kaynak listesi `/wiki/meta/source_tier_list.md`'de.
Bu liste ayrı bir mesajda kullanıcıya sunulur, sen oradan ingest etmeye başlarsın.

## 9. Forbidden Operations

**Asla yapma:**
- `raw/` içindeki dosyaları düzenleme veya silme
- `CLAUDE.md`'yi kullanıcı onayı olmadan düzenleme
- Kullanıcı izni olmadan paper indirme veya web scrape
- Wiki'ye, raw/'da olmayan bir kaynaktan iddia yazma (training data dahil!)
- Bir factor/strategy hakkında "memory'den biliyorum" yazma
- Sayfa silme (yerine `> ⚠️ DEPRECATED, see [[new_page]]` koy)
- 100+ satırlık bir sayfayı tek seferde overhaul etme — incremental edit yap

## 10. Index ve Log Disiplini

`wiki/index.md`:
- Her ingest'te güncellenir.
- Kategori bazlı gruplama: Papers (chronological), Factors (alphabetical),
  Concepts, Comparisons, Strategies, Methodology, Meta.
- Her satır: `- [[page_name]] — <one-line summary>`.

`wiki/log.md`:
- Append-only.
- Format: `## [YYYY-MM-DD] <op> | <subject> | <details>`.
- `<op>` ∈ {ingest, query, lint, strategy, strategy_formal_spec, schema_update, source_added}.
- `grep "^## \[" log.md | tail -10` ile son 10 operasyon görülebilir.

### 11. Self-Audit Cycles

Wiki büyüdükçe her cycle sonunda kullanıcının elle kontrol yapması 
sürdürülemez. Bu bölüm, ingest sonrası **Claude'un kendi kendini 
denetlemesi** için zorunlu protokolü tanımlar.

#### 11.1 Ne zaman tetiklenir

Her `ingest` operasyonu tamamlandığında — yani §5.1 ingest workflow'unun 
adım 9'u (open_questions update) bittikten sonra. **İstisnasız.**

#### 11.2 Standart 6-spot audit

Her ingest sonunda Claude aşağıdaki 6 kontrolü kendi kendine yapar 
ve sonucu PASS / PARTIAL / FAIL olarak raporlar.

**A — Yeni factor entity sayfası integrity (varsa)**
- Bileşen sayım tam mı? (paper'daki gerçek sayıya karşı)
- Her bileşen yanında methodology işareti var mı? (industry-relative / 
  absolute / delta-based / vs)
- "Reported Performance Across Studies" tablosu, mevcut diğer factor 
  sayfalarındaki şablonla aynı kolon yapısında mı? (Inconsistency = PARTIAL)

**B — Goal Alignment 4 eksen kontrolü**
- 4 eksen ayrı ayrı işaretli mi? (Top-N, Annual, Large-cap, NDX)
- N/A olan eksenler "N/A" olarak açıkça yazılmış mı (boş bırakılmamış)?
- ⚠️ uyarı bayrakları olan eksenlerde sayfa atıflı kanıt var mı?
- "En güçlü kanıt kaynağı" tipi vurgu cümleleri varsa, dengeleyici 
  iki kayıt aynı paragrafta mı? (Yoksa FAIL)

**C — Concept sayfa(ları) zenginleşmesi**
- Yeni paper hangi mevcut concept sayfalarını genişletti?
- Genişletme methodoloji düzeyinde mi (yapısal katkı), yoksa sadece 
  referans listesi seviyesinde mi (zayıf)?
- Yeni concept sayfası açıldıysa, sayfanın "İlgili" listesinde henüz 
  ingest edilmemiş paper'lar placeholder olarak işaretli mi?

**D — Mevcut paper sayfalarına inbound link**
- Yeni paper en az 2 mevcut paper sayfasına inbound link ekledi mi? 
  (Cumulative maintenance testi)
- Eklenen link satırları sadece "isim atfı" değil bağlamlı mı?

**E — meta dosyaları update**
- [index.md](http://index.md) güncel mi? (Yeni paper + factor + concept eklendi mi)
- MoC_papers ve MoC_factors uygun kategorilere konuldu mu?
- [log.md](http://log.md) entry'si §10'daki formata uyuyor mu?

**F — open_questions ve data_gaps**
- Bu paper hangi mevcut Q'ları partial cevapladı? (Q-numarası + sayfa atıflı kanıt)
- Hangi yeni Q'lar açıldı? Format diğer Q'larla tutarlı mı? 
  (`**[QN]**` formatı, "yeni" suffix'i YOK)
- data_gaps'a yeni boşluklar eklendi mi?
- Q'lara wikilink referansı `[[meta/open_questions]] (QN)` formatında mı? 
  (`[[QN]]` typo niteliğinde; broken link tarama subset'i, Cycle 12 lint pattern)

#### 11.3 Audit raporu formatı

Audit raporu **ingest mesajının sonunda** otomatik gelir, ayrı bir mesaj 
olarak değil. Format:

Bütünsel durum ölçütü:
- **TEMIZ**: tüm spot'lar PASS → kullanıcı "TEMIZ devam" der, Cycle N+1 başlar
- **KÜÇÜK FIX**: 1-2 PARTIAL, FAIL yok → "KÜÇÜK fix devam" → düzeltme + Cycle N+1
- **YAPISAL FIX**: 1+ FAIL veya 3+ PARTIAL → kullanıcı sayfa-spesifik karar verir
- **ABORT**: yapısal hata → ingest'i geri sar

#### 11.4 Düzeltme onayı

**Asla** otomatik düzeltme yapma. Audit raporu hazırla, kullanıcıdan onay 
bekle. Kullanıcı şunlardan birini söyler:
- "TEMIZ devam" → Cycle N+1 ingest planı sun
- "KÜÇÜK fix devam" → düzeltme yap, log entry'sine `lint_pass` kategorisinde 
  not düş, sonra Cycle N+1 ingest planı sun
- "YAPISAL fix" + spesifik talimat → düzeltme yap, kullanıcı tekrar review eder
- "ABORT" → ingest'i geri sar

#### 11.5 4-cycle consolidation pass

Her **4 cycle'da bir** (cycle 4, 8, 12, 16, 20...) standart audit yerine 
daha derin bir consolidation pass yapılır:

- Orphan sayfa taraması — hiç inbound link almayan sayfa var mı?
- Çelişki taraması — son 4 cycle'da [contradictions.md](http://contradictions.md)'ye eklenmesi gereken 
  çelişki kaçırıldı mı?
- Stale claim taraması — yeni paper tarafından çürütülen iddialar hala 
  "sertçe" duruyor mu?
- MoC tutarlılığı — gerçek dosya listesi ile MoC_papers/MoC_factors eşleşiyor mu?
- Önerilen sonraki ingest — kalan Tier 1 paper'larından, mevcut data_gaps'i 
  en çok kapatan 1-2'sini öner, gerekçesini sun.

Consolidation pass raporu ayrı bir log entry alır:
`## [tarih] consolidation_pass | Cycle N | <bulgular özeti>`.

#### 11.6 Tetikleyici cümleler

Kullanıcı şu cümleleri kullandığında ilgili davranış:

- **"TEMIZ devam"** → audit'ten sonra Cycle N+1 ingest planı
- **"KÜÇÜK fix devam"** → düzeltme + Cycle N+1
- **"YAPISAL fix"** → kullanıcı talimatını bekle
- **"ABORT"** → son ingest'i geri sar
- **"audit"** → mevcut sayfa(lar)a tekrar 6-spot audit çalıştır
- **"consolidation"** → §11.5 derin denetim pass'i (cycle sayısından 
  bağımsız, talep üzerine)
- **"freeze ingest"** → bir sonraki kullanıcı talimatına kadar ingest 
  workflow'u durdur (sadece query/audit yapar)

#### 11.7 Niye bu protokol var

Wiki'nin kümülatif kalitesi ingest hızıyla orantılı **DEĞİL** — denetim 
sıkılığıyla orantılı. 25 paper'lık Tier 1'in son 5 paper'ında dönüp ilk 
5'in hatasını fark etmek pahalı. Self-audit her cycle'da hatayı anında 
yakalamayı mümkün kılar.

Kullanıcı bu sistemde **denetçi** rolünde, **operatör** değil. Operatör 
Claude. Kullanıcı sadece şüpheli durumlarda devreye girer veya 4-cycle 
consolidation noktalarında stratejik karar verir.

---

## 12. Post-Faz 3 Yaşayan-Proje Bakım Protokolü

> 📝 **Cycle 42 schema_update (2026-05-03)**. Faz 3 YUMUŞAK sertifika
> (Cycle 41) sonrası wiki yaşayan-proje statüsünde bakım disiplinini
> netleştirir. Üç kural: executive_summary güncelleme kadansı +
> backtest geri rapor ingest yolu/frontmatter + v1 → v2 evrim historic
> preservation. §11 her ingest audit disiplini bu §12 üstünde aynen
> geçerli kalır.

### 12.1 executive_summary.md güncelleme kadansı

`wiki/meta/executive_summary.md` (Cycle 42'de oluşturulmuş hızlı giriş
katmanı; 41-cycle birikim tek sayfa) **iki tetikleyiciden biri** ile
güncellenir:

- **Her 4 cycle'da bir** — §11.5 ardışık consolidation pass ile aynı
  ritim (Cycle 44/48/52/...). Paper sayım, fully-answered Q sayım,
  yeni zincir/contradictions/sertifika durumu refleksiyonu.
- **Büyük ingest sonrası** — yüksek priori paper (Tier 1 veya kritik
  Tier 2) **veya** backtest geri raporu (strategy-level baseline rapor)
  ingest sonrasında, 4-cycle'ı beklemeden.

Küçük zenginleşmeler (partial-stronger Q güncellemeleri, 1 satır
factor entity ekleme) biriksin, 4-cycle'da konsolide edilir. Aşağıdaki
şartlardan biri karşılanırsa **bekleme yok, anında güncelle**:
- Yeni paper methodology zincirine yeni halka ekledi
- Fully-answered Q sayımı değişti
- Yeni contradictions entry açıldı
- Faz/sertifika durumu değişti

### 12.2 Backtest geri rapor ingest yolu ve frontmatter

P123 platformundan veya başka backtest motorundan gelen sonuçlar
**akademik paper sayfalarıyla karıştırılmaz** (wiki/papers/ rezerve
edilir akademik literatür için).

- **Klasör**: `wiki/backtests/` (yeni; `wiki/papers/` DEĞİL)
- **Slug**: `wiki/backtests/p123_{strategy}_{YYYY-MM-DD}.md`
  (örn. `p123_sp500_v1_2026-06-15.md`,
  `p123_nasdaq100_v1_2026-07-01.md`)
- **YAML frontmatter zorunlu**:
  ```yaml
  type: backtest_report
  strategy: sp500_v1   # veya nasdaq100_v1, sp500_v2 vs.
  platform: portfolio123_ultimate
  sample_period: "1980-2020 baseline + 2021-2024 OOS"
  weighting: "capped VW NYSE 80th percentile"   # methodology choice
  rebalance: "annual June + quarterly drift"
  reporting_methodology: "DSR-corrected Sharpe + walk-forward + bootstrap"
  ingested: YYYY-MM-DD
  status: ingested
  ```
- **İçerik şablonu** (handoff_backtest.md §6.1 paterni):
  TL;DR + Sample stats + Factor inclusion + Theme allocation +
  Headline metrics (DSR + walk-forward sub-period + bootstrap CI +
  alternative weighting sensitivity) + Strategy implikasyonu (v1→v2
  trigger değerlendirmesi).

Akademik paper'lar `wiki/papers/` altında ve [[meta/MoC_papers]]'de
kalır. Backtest raporları `wiki/backtests/` altında ve [[index]]
"Backtests" bölümünde toplanır; gerekirse yaşayan-proje çerçevesinde
`meta/MoC_backtests.md` ayrı registry açılır (ilk 2-3 rapor sonrası).

### 12.3 v1 → v2 evrim historic preservation

Backtest sonucu strateji spec'i değiştirmeyi gerektiriyorsa
(trigger kriterleri [[meta/handoff_backtest]] §6.3: conservative
baseline range dışı sapma; methodology choice >5pp divergence; Q60
horse race açık tercih; F bloğu 4-katmanlı dörtlü konsolidasyon
empirik karar), **v1 dosyaları OVERWRITE EDİLMEZ**:

- `wiki/strategies/sp500_v1.md` ve `wiki/strategies/nasdaq100_v1.md`
  **olduğu gibi kalır** — content değiştirilmez. YAML frontmatter'a
  `status: historic` + `superseded_by: strategies/sp500_v2` satırları
  eklenir; sayfanın §0 üst-not'una "📝 Cycle N v1 → v2 evrim
  trigger'ı: ..." kaydı düşülür.
- Yeni dosyalar: `wiki/strategies/sp500_v2.md` ve/veya
  `wiki/strategies/nasdaq100_v2.md` (active; YAML predecessor=sp500_v1).
- v0 → v1 evrim historic preservation paterni (Cycle 30 origin; §7
  Faz 2 kriter 3 + Faz 3 kriter 10) post-Faz 3 yaşayan-proje
  çerçevesinde **aynen** uygulanır.

`known_weaknesses.md` v2 opsiyoneldir (sp500_v2 + nasdaq100_v2
çıkmadıkça gerekmez); çıkarsa `known_weaknesses_v2.md` aynı pattern.

> ⚠️ **Asla v1 spec'i overwrite etme.** Backtest sonucu conservative
> baseline range içinde kalıyorsa v1 yeterli; v2 tetiklenmez. v1
> içeriğini "güncellemek" historic'i yok eder ve strateji tasarım
> kararlarının evrimini izleme imkanını kapatır. v1'e ek note bile
> şüpheliyse §11.4 paterni — kullanıcıdan "KÜÇÜK fix devam" onayı al.

---

**Bu doküman canlıdır.** Kullanıcıyla birlikte evolve eder. Bir kural çelişki
yaratıyorsa veya pratikte çalışmıyorsa, kullanıcıya bildir, birlikte güncelleyelim.

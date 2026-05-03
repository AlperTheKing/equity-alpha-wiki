---
type: comparison
subjects: [[F_Score]], [[G_Score]]
related_papers: [[piotroski2000_f_score]], [[mohanram2005_g_score]], [[li_mohanram2019_quality_value]]
---

# F-Score vs. G-Score — Head-to-Head Karşılaştırma

> 📝 Bu sayfanın empirik omurgası [[li_mohanram2019_quality_value]] — F ve G'yi
> aynı sample/aynı methodoloji içinde test eden tek paperdır.

## Yapısal karşılaştırma

| Eksen | F-Score [[piotroski2000_f_score]] | G-Score [[mohanram2005_g_score]] |
|---|---|---|
| **Anchor evren** | High-BM (BM-Q5, value) | Low-BM (BM-Q1, growth) |
| **Bileşen sayısı** | 9 | 8 |
| **Eşik metodolojisi** | Firm-level (örn. ROA > 0) | Industry-median (2-digit SIC, contemporaneous low-BM peers) |
| **Sinyal odak** | Profitability (4) + Leverage/liquidity (3) + Operating efficiency (2) — *distressed firma sinyalleri* | Profitability (3) + Stability (2) + Conservatism/R&D-capex-advertising (3) — *growth firma sinyalleri* |
| **Δ-based bileşenler** | 5 (ΔROA, ΔLEVER, ΔLIQUID, ΔMARGIN, ΔTURN) | 0 (tümü level-based) |
| **Ortak çekirdek (Sloan paterni)** | F_ACCRUAL: CFO > NI (firm-level) — origin: [[sloan1996_accruals_anomaly]] | G3: CFO > NI (firm-level, *non-industry*) — origin: [[sloan1996_accruals_anomaly]] — **F_ACCRUAL ile aynı binary signal** |
| **Range** | 0-9 | 0-8 |
| **Distribution** | Çoğu firma 3-7 (binomial-tipi); extreme (0-1, 8-9) az | Left-skewed; G4/G5 min 3-yıl gerektirir; G6/G7/G8 birçok firmada 0 |
| **Origin sample** | 1976-1996, COMPUSTAT BM-Q5, 14,043 firm-year | 1979-1999, COMPUSTAT BM-Q1, 20,866 firm-year |
| **Reporting lag** | Fiscal year-end + 5 ay | Fiscal year-end + 4 ay |

## Methodoloji yeniden-test farkları

[[li_mohanram2019_quality_value]] her iki skoru aynı sample/methodoloji'de
yeniden inşa eder. Bu **çelişki değil**, sample/methodology yeniden-test
farkıdır — McLean-Pontiff (2016) post-publication decay'in somut örneği
([[meta/open_questions]] Q5 ile bağlı).

| Skor | Orijinal headline | Li-Mohanram 2019 replikasyon | Fark gerekçesi |
|---|---|---|---|
| **F-Score** | High − Low = **+23.0%** yıllık market-adj (binary, BM-Q5 only, 1976-1996) [[piotroski2000_f_score]] [Tablo 3, s.16] | Q5 − Q1 = **+7.44%** yıllık size-adj (continuous-rank, **all-firms**, 1973-2012) [[li_mohanram2019_quality_value]] [Tablo 2, s.15] | (1) **Sample uzatması:** 1996-2012 dönemi dahil → post-publication decay etkisi (McLean-Pontiff 2016 ile uyumlu); (2) **Universe genişlemesi:** BM-Q5-only → all-firms (F-Score signaller distressed firma için kalibre, all-firms'de zayıflar); (3) **Methodology revision:** binary 0/1 → continuous rank-based 0-1; (4) Q5-Q1 quintile vs. {0,1}-{8,9} extreme group farkı |
| **G-Score** | High − Low = **+21.2%** yıllık size-adj (binary, BM-Q1 only, 2-digit SIC industry, 1979-1999) [[mohanram2005_g_score]] [Tablo 4, s.15-16] | Q5 − Q1 = **+6.06%** yıllık size-adj (continuous-rank, **all-firms**, **FF1997 48-industry**, 1973-2012) [[li_mohanram2019_quality_value]] [Tablo 2, s.15] | (1) Sample uzatması post-2000 dahil; (2) Universe genişlemesi (BM-Q1-only → all-firms); (3) Continuous vs binary; (4) **Industry classification revision:** 2-digit SIC (~80 sektör) → FF 1997 48-industry (24% daha az kategori, daha agrege) |
| **F-Score q5 lens** | (yukarıdaki ilk satır) | (yukarıdaki ikinci satır) | **3. test:** [[hou_mo_xue_zhang_2020_security_analysis]] [Tablo 2, s.18-19] q-factor / q5 model alpha replikasyonu (1972-2018, NYSE/AMEX/NASDAQ all): **q5 alpha micro 0.33% (sig), small/big 0.10%/0.03% (insig)**. q5 GRS cannot reject (p=0.09). **Yorum:** q5 lens F-Score'u microcap hariç span ediyor — large-cap segmentinde standalone alpha kaynağı yok, fundamental score = factor exposure proxy. Methodology fark sebebi: yeni RHS (q-factor model) eklenmesi, monthly portfolio rebalans frekansı, NYSE breakpoint |
| **G-Score q5 lens** | (yukarıdaki ilk satır) | (yukarıdaki ikinci satır) | **3. test EDİLMEDİ:** [[hou_mo_xue_zhang_2020_security_analysis]] paperı G-Score'u kapsamına almamış. Wiki'de G-Score'un q-factor lens'inde durumu **bilinmiyor** → Q25 açık sorusu. F-Score patterninin (microcap hariç span) G-Score için tekrarlanırlığı doğrulanmamış |

> ⚠️ **Strateji tasarımı için hangi rakamı kullanacağız:** **Li-Mohanram
> replikasyon rakamları — daha modern sample (1973-2012), daha geniş universe,
> continuous methodology**. Orijinal Piotroski 2000 +23% ve Mohanram 2005 +21.2%
> rakamları **dönem-spesifik (universe-spesifik) headline** olarak referans
> kalır ama **strateji baseline benchmark olarak Li-Mohanram 7.44% / 6.06%
> kullanılır**. Daha gerçekçi, post-publication decay-aware rakamlar.

> ⚠️ **HMXZ q5 lens'i ek bir uyarı sağlar:** Li-Mohanram'ın 7.44% F-Score
> hedge return'ünün q5 model alpha'sı large-cap segmentinde sıfıra yakın
> ([[hou_mo_xue_zhang_2020_security_analysis]] [Tablo 2, s.18-19]). Yani
> **strateji tasarımı için baseline 7.44% **factor exposure** üzerinden geliyor**;
> "saf alpha" değil. Faz 3 strateji backtest'inde q5 model'e karşı alpha
> raporlamak gerek; standalone hedge return realistic estimate ama büyük kısmı
> risk premium.

## Aynı sample'da empirik karşılaştırma [[li_mohanram2019_quality_value]] (1973-2012, 98,766 obs)

### Standalone hedge returns [Tablo 2, s.15-16]

| Metrik | F-Score | G-Score |
|---|---|---|
| Hedge return (Q5-Q1) | **+7.44%** | +6.06% |
| Q5 mean RET1 | +5.30% | +4.31% |
| Q1 mean RET1 | -2.14% | -1.76% |
| Negative-year frequency (40 yıl) | 5/40 | 13/40 |
| Sharpe ratio | 1.19 | 0.56 |

> 📝 Aynı sample/methodoloji altında **F-Score G-Score'dan daha güçlü**:
> hem hedge magnitude (+1.38 puan) hem Sharpe ratio (1.19 vs 0.56) hem
> negative-year frequency (5 vs 13). Bu, Mohanram 2005'in growth-side avantajının
> all-firms universe'a transferli olmadığını **gösterir** — G-Score'un
> orijinal +21.2% gücü low-BM-only kalibrasyonundan geliyordu.

### BM context partition [Tablo 6, s.20]

| BM tercile | F-Score hedge | G-Score hedge | F-Score "appropriate"? | G-Score "appropriate"? |
|---|---|---|---|---|
| **Growth (low BM)** | 8.01% | **10.92%** | ❌ context dışı | ✅ origin |
| Medium BM | 7.83% | 6.63% | — | — |
| **Value (high BM)** | **9.97%** | 4.80% | ✅ origin | ❌ context dışı |

> 📝 **Context-aware seçim:** F-Score value'da, G-Score growth'da en güçlü.
> Bu, [[contextual_fundamental_analysis]] kavramının doğrudan empirik kanıtı.
> Wiki için **iki paralel skor** stratejisinin (S&P 500 ↔ F-Score, Nasdaq 100 ↔
> G-Score) pratik temeli.

### Korelasyon [Tablo 3 Panel A, s.16]

- F-Score ↔ G-Score: **strong positive** (her ikisi financial statement-based)
- Bu, "hangisini kullanmalı" sorusu yerine **"hangi context'te hangisini"**
  sorusunun anlamını öne çıkarır.

### Combined ile etkileşim [Tablo 4, s.17-18]

| Combined | Hedge | Anchor avantajı |
|---|---|---|
| F-Score & V/P | 17.94% | F-Score value-side |
| **G-Score & V/P** | **21.45%** | G-Score growth-side, V/P ile genel |
| F-Score & NEGPEG | 16.76% | F-Score value-side |
| G-Score & NEGPEG | 20.67% | G-Score growth-side |

> 📝 **G-Score combined daha güçlü** (21.45% > 17.94%) ama bu (1) growth
> stocks'un V/P'den daha çok yararlanması, (2) G-Score'un standalone'dan
> kombine avantajının daha büyük olması (G: 6.06 → 21.45 = 3.5x; F: 7.44 →
> 17.94 = 2.4x) ile açıklanır.

## Strateji tasarımına net implikasyon

1. **F ve G rakip değil komplementer:** Her biri kendi anchor evrende baskın,
   evren dışına transfer riskli. S&P 500 (mixed/value-tilted) için F-anchor
   öncelikli, Nasdaq 100 (growth) için G-anchor öncelikli.
2. **Standalone yerine combined:** Li-Mohanram kanıtı ile combined yaklaşımları
   strateji tasarımının default'u olmalı (F&V/P veya G&V/P).
3. **Post-publication decay farkındalığı:** Orijinal +23%, +21.2% spread'lerin
   modern sample'da 7.44%, 6.06%'ya inmesi normal beklenti — Faz 3 backtest
   spec'inde bu decay-adjusted hedef tespiti zorunlu.
4. **Methodology seçimi:** Continuous rank-based (Li-Mohanram inşası) >
   binary 0/1 (orijinal). Modern uygulamada continuous tercih edilmeli ama
   look-ahead bias riski ile (her sinyal cross-sectional rank → in-sample
   tüm firmaları biliyor olma).

## Ortak limitler

- **Universe-spesifik kalibrasyon:** Her ikisi anchor evrene bağlı. Orta-BM
  hibrit firmalar her iki skor için suboptimal — bkz.
  [[winner_loser_identification]] "Bu paradigmanın boşlukları".
- **Equal-weighted binary (orijinal) optimum değil.** Continuous (Li-Mohanram
  revision) daha iyi ama **factor-analysis ağırlıklandırma test edilmedi**.
- **Industry definition seçimi sonucu etkiler:** G-Score için 2-digit SIC
  (Mohanram) vs FF1997 48-industry (Li-Mohanram) farklı sonuç verir.
  Wiki için **NDX 100-stock evrende industry granularite seçimi açık soru**
  → [[meta/open_questions]] Q19.
- **Post-2014 out-of-sample (Li-Mohanram):** FAANG-dominant 2015-2024 dönemi
  her iki skor için tekrarlanırlık bilinmiyor.

## İlgili sayfalar

- [[F_Score]] — origin entity
- [[G_Score]] — origin entity
- [[piotroski2000_f_score]] — F-Score origin paper
- [[mohanram2005_g_score]] — G-Score origin paper
- [[li_mohanram2019_quality_value]] — head-to-head test paperı
- [[winner_loser_identification]] — paradigma çatısı
- [[contextual_fundamental_analysis]] — universe-conditioned signal yorumu
- [[meta/open_questions]] Q5 (post-publication decay), Q18 (large-cap), Q19 (NDX
  industry classification)

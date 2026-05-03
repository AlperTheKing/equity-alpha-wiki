---
type: paper
authors: [Eisfeldt, Andrea L., Papanikolaou, Dimitris]
year: 2013
title: "Organization Capital and the Cross-Section of Expected Returns"
venue: "Journal of Finance"
url: https://www.nber.org/papers/w17904
local_path: raw/papers/eisfeldt_papanikolaou_2013_organization_capital.pdf
ingested: 2026-05-01
tags: [intangibles, organization_capital, sga, factor_portfolio, f_block_4th_pillar, ndx_relevant, large_cap_partial]
status: ingested
cycle: 25
block: F_complement
---

# Eisfeldt-Papanikolaou (2013) — Organization Capital and the Cross-Section of Expected Returns

> 📝 **Faz 2 Cycle 25 ingest** — F bloğu kompleman; Faz 1 sertifikası
> YUMUŞAK üçüncü eksiklik kapanışı (Cycle 22 E bloğu + Cycle 23 B
> kompleman sonrası). Paper F bloğu intangibles methodology
> infrastructure'ında **factor portfolio direct evidence eksik**
> boşluğunu kapatır (Cycle 16 sonrası işaretli; Lev-Sougiannis +
> Peters-Taylor + Lev-Srivastava üçü methodology paper, **factor
> portfolio değil**). Eisfeldt-Papanikolaou OC factor portfolio
> direct return prediction kanıtı sağlar — F bloğu **4. ayak**.

## TL;DR

Eisfeldt-Papanikolaou organization capital'ı **SG&A expenditures'ın
perpetual inventory accumulation'ı** ile ölçüyor (Lev-Radhakrishnan
2004 paterni). Industry-relative (FF17 industry classification)
within-industry quintile sort: **high-low spread 4.8%/yıl, Sharpe
0.58** (1970-2008 sample, 38 yıl). CAPM/FF3/Carhart **explain etmiyor**:
CAPM α=5.6%, FF3 α=5.5%, Carhart α=3.9% (1% sig). Yapısal mekanizma:
high OC firms **partial worker-embodied** (rents shareholder ve
labor arasında split); economic restructuring riskine **differential
sensitivity** (frontier technology improvement → workers' outside
option artar → shareholders' rents düşer). Robustness güçlü:
depreciation rate 0.10-0.50 arası 4.2-5.3% spread; DOL-controlled
sort 3.1% spread (still sig). High OC firms **growth-tilted** (low
PP&E/AT, low leverage, high Tobin's Q) **AMA** SMB+HML factor
loadings essentially uncorrelated.

## Tek Cümle Tezi

**Organization capital** (SG&A perpetual inventory accumulation)
**factor portfolio direct return prediction** sağlayan intangibles
ayağıdır; Lev-Sougiannis 1996 (Knowledge capital R&D) +
Peters-Taylor 2017 (Total intangible q proxy) + Lev-Srivastava 2020
(adjusted HML application) **methodology paper'larının factor
portfolio karşılığı** — F bloğu 4. ayak.

## Sample ve Methodology

- **Universe**: NYSE+Amex+Nasdaq Compustat firms (financials sektör
  industry-relative sort'ta dahil; unconditional sort'ta hariç)
- **Sample**: January 1970 - December 2008 (38 yıl) [Tablo 3]
- **Sort**: Industry-relative (Fama-French 1997 17-industry
  classification) within-industry quintile sort
- **Rebalance**: **Annual June rebalance** [s.8] ⭐
- **Organization capital measure** [Eq.(1), s.6]:
  ```
  O_{i,t} = (1 − δ) × O_{i,t-1} + SG&A_{i,t}
  ```
  - Perpetual inventory (BEA R&D capital methodology paralel)
  - Initial stock: O_0 = SG&A_1 / (g − δ); g matched to steady-state
    average investment rate ≈ 0.25
  - Default depreciation rate **δ = 15%/yıl** (recent expenditures
    daha ağır)
  - SG&A consumer price index ile deflate
  - Missing values zero treatment
- **Sort metric**: O/A ratio (organization capital stock / total
  assets) within industry

## Ortaya Konan Sinyal/Faktör

**Organization Capital factor (OC)** — yeni factor entity wiki'de
açıldı: [[factors/Organization_Capital]]

**F bloğu 4. ayak** (Cycle 25 dokümante):
1. **Knowledge capital** ([[papers/lev_sougiannis_1996_rd_capitalization]])
   — R&D perpetual inventory; methodology infrastructure
2. **Organization capital** ([[papers/eisfeldt_papanikolaou_2013_organization_capital]])
   — SG&A perpetual inventory; **factor portfolio direct evidence** ⭐
3. **Total intangible** ([[papers/peters_taylor_2017_intangible_capital]])
   — q^tot proxy (Knowledge + Organization + External); q theory test
4. **Application** ([[papers/lev_srivastava_2020_value_failure]]) —
   adjusted HML post-2010 value crisis decomposition

**Yapısal kazanım**: F bloğu Cycle 17'de **3-katmanlı** kapatılmıştı;
Cycle 25 ek **4. katman (factor portfolio direct evidence)** ile
methodology infrastructure (Lev-Sougiannis + Peters-Taylor +
Lev-Srivastava) + **factor portfolio anchor (Eisfeldt-Papanikolaou)**
ayrımı dokümante.

## Empirik Sonuçlar (sayılarla)

### 1. Headline industry-relative sort [Tablo 3, s.9]

| Spec | Quintile 5 - Quintile 1 | t-stat |
|------|--------------------------|--------|
| Raw mean (annual) | **4.8%** | (sig) |
| **Sharpe ratio (long-short)** | **0.58** | — |
| **CAPM α** | **5.6%** | sig |
| **FF3 α** | **5.5%** | sig |
| **Carhart α** | **3.9%** | sig 1% |
| Long-short std deviation | 8.2% | (low) |

### 2. Faktör loadings [Tablo 4, s.9]

- High OC portfolio CAPM β market beta **lower** than low OC
  portfolio (counterintuitive — risk premia "betas with respect to
  long-short OC portfolio monotonically increasing -0.37 to 0.63"
  [s.9]; OC kendisi pricing factor)
- High OC tech-tilted growth firms (low PP&E/AT, low leverage, high
  Tobin's Q) **AMA** SMB ve HML loadings essentially uncorrelated

### 3. Robustness Checks [s.10]

- **Initial stock sensitivity**: 5+ önceki SG&A obs filter → spread
  4.2%, CAPM α 5.1%, FF3 α 4.9%, Carhart α 3.3% (still sig)
- **Depreciation rate sensitivity**: δ ∈ {0.10, 0.50} → spread 4.2-
  5.3%, CAPM α 4.4-6.2%, FF3 α 5.3-6.2%, Carhart α 3.8-4.6%
- **Unconditional sort** (industry-relative değil; financials hariç):
  spread 3.86%, CAPM α 4.6%, FF3 α 5.3%, Carhart α 5.4%
- **DOL-controlled** (degree of operating leverage tercile within
  industry → 3-OC sort): spread 3.1%, CAPM α 3.7%, FF3 α 4.2%,
  Carhart α 3.3% (still sig 1%) — **operating leverage explanation
  reddedilir**

### 4. Conditional market beta (NBER recession) [s.10-11]

High-low OC portfolio market beta'sı NBER recession dummy üzerine
regression: coefficient **-0.14 (t=-1.47)**; **countercyclical risk
kanıtı YOK** (high OC firms bad times'ta daha riskli değil).

### 5. Persistence [Tablo 2]

Quintile transition: yıllık ~%80 same-quintile (transition prob ~%20)
→ classification fairly persistent; düşük turnover.

### 6. Firm characteristics [Tablo 1]

| Karakteristik | Low OC (Q1) | High OC (Q5) |
|---------------|-------------|--------------|
| Asset tangibility (PPE/AT) | Yüksek | **Düşük** |
| Leverage | Yüksek | **Düşük** |
| Tobin's Q | Düşük | **Yüksek** |
| Capital-labor ratio | Yüksek | **Düşük** (labor-intensive) |
| Operating leverage | Düşük | **Yüksek** |
| Market cap | Benzer | Slightly higher (sig farkı yok) |
| BE/ME median | Benzer | Benzer (sürpriz; portfolio-level VW low BE/ME) |

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Industry-relative within-industry quintile sort + within-DOL tercile sort + unconditional sort; standard cross-sectional anomaly methodology | ✅ doğrudan fit |
| **Annual rebalance** | ⭐ **Annual June rebalance default** [s.8] explicit; wiki proje amacı ile direct uyum (Novy-Marx + FF + Sloan paterni) | ✅ doğrudan + güçlü fit |
| **Large-cap evrene transfer** | ⚠️ Sample NYSE+Amex+Nasdaq all-stocks; **size partition direct test paperde sadece "market cap not vary substantially across portfolios" [s.8]** — explicit large-cap-only test yok; portfolio-level VW BE/ME düşüş gösteriyor (high OC value-tilted değil growth-tilted); ama industry-relative methodology size-neutral değil. **Q4 paterni**: large-cap kanıt seviyesi muhtemelen orta (size-loaded değil ama large-cap-only direct test eksik) | ⚠️ partial fit + ⭐ industry-relative methodology size-neutralizing |
| **NDX intangibles / growth firms** | ⭐ ⭐ KRITIK doğrudan fit; **organization capital tech firma SG&A ağırlıklı** (sales force + customer acquisition + IT outlays + employee training); High OC firms **growth-tilted** (low PP&E/AT, low leverage, high Tobin's Q) → NDX FAANG profile birebir match; intangibles-aware methodology paper'ın MERKEZ konusu | ✅ ⭐ ⭐ KRITIK direct fit (NDX strategy spec için **birebir match**) |

**Strateji tasarımına net implikasyon:**

1. **F bloğu 4. ayak (factor portfolio direct evidence) tamamlandı**.
   Cycle 17'de [[concepts/intangibles_adjusted_accounting]] 3-katmanlı
   methodology hierarchy kapatılmıştı (Lev-Sougiannis methodology +
   Peters-Taylor q theory + Lev-Srivastava application); Cycle 25 ek
   **factor portfolio anchor** — methodology infrastructure ile
   tradable factor portfolio ayrımı dokümante. NDX strategy v0 §2.B
   intangibles-aware overlay anchor güçlenmesi (R&D-to-market 4/4
   hayatta kalan + **OC factor 5.5% FF3 α direct evidence**).

2. **NDX strategy spec için birebir match**. High OC firms NDX FAANG
   profile (low PP&E/AT, growth-tilted, intangibles-yoğun); industry-
   relative sort tech-heavy NDX evren amacıyla uyumlu (FF17 sektör
   içi rank). Q41 4-way horse race (Lev-Sougiannis + Peters-Taylor +
   Lev-Srivastava + Eisfeldt-Papanikolaou) **fully-answered aday**.

3. **Operating leverage rejected explanation**. Eisfeldt-Papanikolaou
   [s.10] DOL-controlled sort 3.1% spread (still sig 1%) → OC factor
   premium operating leverage'a indirgenemez; firm-specific worker-
   embodied risk yapısal.

4. **High OC ↔ Novy-Marx GP/A ↔ QMJ Profitability potansiyel paralel**.
   Novy-Marx [Section 4] organizational capital based strategy
   industry-adjusted GP/A + value + momentum 3-factor model ile
   "açıklanıyor"; Eisfeldt-Papanikolaou direct factor portfolio
   kanıtı bu açıklamanın empirik test'i. Q58 (Industry-adjusted
   GP/A anomaly explanation power) Cycle 23 partial-stronger.

5. **Annual June rebalance default** wiki proje amacıyla direct
   uyum; UMD/QMJ aylık-orijinal annual uyarlama sensitivity
   endişelerinin TERSİ — OC factor wiki için zaten annual baseline
   (Novy-Marx GP/A + Lev-Sougiannis methodology paterni).

## Limitler ve Caveats

- **Sample sonu Dec 2008** — post-2008 (FAANG era 2009-2024 + COVID
  + AI) out-of-sample; modern data Chen-Zimmermann + JKP 2023 ek
  ingest gerekli (Cycle 27)
- **SG&A measurement noise**: paper [s.6-7] "to the extent that
  some SG&A expenditures do not constitute investment in
  organization capital we will be measuring this capital with error";
  Peters-Taylor θ=30% allocation alternative (Q60 yeni)
- **Industry classification FF17 17-industry**; modern GICS Level-2/3
  mapping NDX strategy spec için kalibrasyon gerekli (Q38 + Q61
  paralel)
- **Initial stock sensitivity** robust ama 5+ obs filter spread'i
  4.2%'ye düşürüyor (orig 4.8%) — kısa-zaman-serisi firms için
  initialization choice kritik
- **Size partition direct test eksik**: large-cap-only sub-portfolio
  yok; "market cap not vary substantially across portfolios" general
  statement [s.8] ama Q4 spectrumu (size Q1-Q5) decomposition yok
- **HXZ 2020 organization capital factor potansiyel çelişki**:
  HXZ 2020 [s.2] organization capital (Eisfeldt-Papanikolaou) 447
  anomaly içinde test ediyor; replication status text extract'inde
  net teyit edilmedi — methodology disagreement çıkarsa scope-dependent
- **Modern Peters-Taylor θ=30% vs Eisfeldt-Papanikolaou full SG&A
  perpetual inventory** methodology farkı (Q60 yeni) — adjustment
  factor allocation methodology comparison eksik

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfalar
- [[factors/Organization_Capital]] — yeni factor entity (Cycle 25);
  OC factor portfolio direct evidence; F bloğu 4. ayak

### Bu paperın update ettiği mevcut sayfalar (F bloğu hierarchy)
- [[papers/lev_sougiannis_1996_rd_capitalization]] — F bloğu 1. ayak
  (Knowledge capital R&D); Eisfeldt-Papanikolaou paralel methodology
  (perpetual inventory) ama farklı capital türü (R&D vs SG&A)
- [[papers/peters_taylor_2017_intangible_capital]] — F bloğu 3. ayak
  (Total intangible q proxy); Peters-Taylor [s.5, 10] Eisfeldt-
  Papanikolaou explicit cite — θ=30% SG&A allocation methodology
  paterninden; Q41 4-way horse race tam dolar
- [[papers/lev_srivastava_2020_value_failure]] — F bloğu 4. ayak
  uygulaması (post-2010 value crisis); Eisfeldt-Papanikolaou OC factor
  Lev-Srivastava adjusted HML methodology'sine entegre edilebilir
- [[papers/novy_marx_2013_gross_profitability]] — Novy-Marx [Section
  4] organizational capital based strategy explicit cite Eisfeldt-
  Papanikolaou; industry-adjusted GP/A + value + momentum 3-factor
  açıklama (Q58 partial-stronger)
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] — organization
  capital factor 447 anomaly içinde test (HXZ 2020 [s.2]); replication
  status modern dönem empirik validation
- [[concepts/intangibles_adjusted_accounting]] — F bloğu **4. ayak**
  yeni katman (Knowledge + Organization + Total + Application 4-katmanlı
  hierarchy); methodology infrastructure + factor portfolio anchor
  ayrımı dokümante
- [[concepts/factor_zoo]] — organization capital factor proliferation
  perspektifi; F bloğu intangibles aile içinde 4 measure
- [[concepts/post_publication_decay]] — dört darbe sentez tablosu OC
  factor satır eklenir (raw 4.8% + Carhart α 3.9% + DOL-controlled
  3.1% multiple specs)
- [[methodology/backtest_spec]] §6 F bloğu intangibles-aware
  methodology — 4-katmanlı hierarchy sertleştirme; §5.2 baseline
  composite NDX overlay tablosu OC factor satır; §8 Origin attribution
  F bloğu ayak hierarchy

### Strategy
- [[strategies/v0_draft]] — §2.B NDX intangibles-aware overlay anchor
  güçlenmesi; §5 Cycle 25 Eisfeldt-Papanikolaou Q41 4-way horse race
  resolution

### Cycle 26 cross-link (FGX 2020)
- [[feng_giglio_xiu_2020_factor_zoo]] — Cycle 26 ingest; FGX 150
  factor library içinde **organization capital factor explicit teyit
  edilemedi** (Tablo 4 ham liste paperdan kontrol edilmedi);
  intermediary investment factor (He-Kelly-Manela 2016) DS-sig
  (Tablo 1) ama bu OC factor değil intermediary capital. **Q64 yeni**
  (Cycle 26): F bloğu intangibles factor'lerin (Lev-Sougiannis
  Knowledge + Eisfeldt-Papanikolaou OC + Peters-Taylor q^tot) FGX
  framework'üne entegrasyonu eksik; F bloğu 4-katmanlı methodology
  DS LASSO redundancy test'i Faz 3 implementation gap.

## Çelişkiler/Tartışmalar

### HXZ 2020 vs Eisfeldt-Papanikolaou (potansiyel)

HXZ 2020 [s.2] organization capital factor 447 anomaly içinde test
ediyor; replication status text extract'inde net teyit edilmedi.
**Hipotez**: Eisfeldt-Papanikolaou industry-relative within-industry
sort + 4.8% spread + Carhart α 3.9% (sig 1%) → muhtemelen HXZ 2020
NYSE-VW unconditional methodology'sinde **kısmen replicate** (5%
cutoff sig olabilir; 3.0 t-cutoff borderline). Eisfeldt-Papanikolaou
unconditional sort spread 3.86% (Carhart α 5.4% sig) → **HXZ
methodology paralel**.

**Resolution**: scope-dependent; methodology farkı (industry-relative
vs unconditional). Wiki için contradictions.md yeni entry açılmadı —
çift teyit (Eisfeldt-Papanikolaou unconditional spec HXZ paralel
methodology).

### Eisfeldt-Papanikolaou vs Peters-Taylor 2017 SG&A allocation farkı (Q60)

- Eisfeldt-Papanikolaou: **full SG&A** perpetual inventory (δ=15%)
- Peters-Taylor: **θ=30% allocation** (sadece SG&A'nın %30'u
  organization capital olarak)

**Çelişki değil, methodology farkı**: Peters-Taylor knowledge +
organization + external 3 component'i ayrı tutmak için θ tahmin
ediyor (modern data); Eisfeldt-Papanikolaou full SG&A measurement
error caveat'ı [s.6] ile kabul ediyor. Modern kalibrasyon (Cycle
27 JKP 2023 + Cycle 29 Chen-Zimmermann data sources) iki
methodology empirik comparison sağlayabilir.

## Açık Sorular (Open Questions)

- **Q41** (Lev-Sougiannis vs Peters-Taylor vs Eisfeldt-Papanikolaou
  vs Lev-Srivastava 4-way horse race) → **fully-answered**: 4 paper
  birlikte F bloğu 4-katmanlı methodology hierarchy + factor portfolio
  anchor ayrımı dokümante; Eisfeldt-Papanikolaou OC factor portfolio
  direct evidence (4.8% spread, FF3 α 5.5%, Carhart α 3.9% sig 1%);
  Lev-Sougiannis (Knowledge) + Peters-Taylor (Total q proxy) +
  Lev-Srivastava (Application) methodology infrastructure üçüsü +
  Eisfeldt-Papanikolaou factor portfolio dördüncü ayak. **Wiki F
  bloğu fully-answered**.
- **Q23** (NDX intangibles q-factor span) → **partial-stronger**:
  OC factor Carhart 4-factor altında α=3.9% sig (1%); HXZ 2020
  q-factor span direct text extract'te yok ama yapısal olarak
  industry-relative methodology q-factor I/A vs Roe component
  altında muhtemelen sig kalır (HXZ 2020 ek ingest tam cevap için)
- **Q40** (Modern Peters-Taylor methodology replikasyonu) →
  **partial-stronger**: Eisfeldt-Papanikolaou 1970-2008 sample
  Peters-Taylor 1975-2011 ile büyük overlap; OC factor portfolio
  direct evidence Peters-Taylor q theory test'inden farklı
  perspektif (factor portfolio vs q theory)
- **Q58** (Industry-adjusted GP/A factor anomaly explanation power;
  Cycle 23 yeni) → **partial-stronger**: Novy-Marx [Section 4]
  organizational capital based strategy 3-factor model "açıklıyor"
  iddiası vs Eisfeldt-Papanikolaou direct factor portfolio FF3+UMD
  altında **alpha sig 1%**; Novy-Marx claim'i Carhart 4-factor
  altında **partial reject** (organization capital independent
  premium kalıyor)
- **Yeni Q'lar (Cycle 25)**:
  - **Q59 yeni**: Organization capital ↔ R&D capital correlation
    (Lev-Sougiannis Knowledge ↔ Eisfeldt-Papanikolaou Organization
    iki intangibles ayağı orthogonality empirik test); Peters-Taylor
    knowledge + organization + external decomposition direct cevap
    sağlayabilir ama factor portfolio level correlation eksik;
    F bloğu 1. + 2. ayak combined methodology Faz 3 design
  - **Q60 yeni**: Peters-Taylor θ=30% SG&A allocation vs Eisfeldt-
    Papanikolaou full SG&A perpetual inventory methodology farkı;
    modern kalibrasyon empirik comparison; FAANG firmalarda recurring
    revenue model SG&A breakdown (sales force + customer acquisition
    + R&D-content) sektör compositional shift altında allocation
    factor değişebilir
  - **Q61 yeni**: Organization capital tech firma + service firma
    sektör compositional shift (NDX FAANG era yüksek SG&A vs
    traditional industries banking/manufacturing); Eisfeldt-
    Papanikolaou industry-relative within-industry sort sektör
    comparison içinde değil; cross-industry OC dispersion modern
    dönem empirik trend Lev-Srivastava 2020 [Section 9] sektör
    compositional shift paterni paralel

## Strateji tasarımına spesifik katkı

1. **F bloğu 4. ayak factor portfolio anchor** — NDX strategy v0
   §2.B intangibles-aware overlay sertleştirme: R&D-to-market 4/4
   hayatta kalan + **OC factor 5.5% FF3 α / 3.9% Carhart α** (1970-
   2008 sample). Faz 3 spec'inde NDX overlay layer:
   - Adjusted Bm rebuild (Lev-Sougiannis + Peters-Taylor + Lev-
     Srivastava methodology infrastructure)
   - **OC factor signal layer** (Eisfeldt-Papanikolaou industry-
     relative within-industry sort)
   - R&D-to-market signal layer (HXZ 2020 4/4 hayatta kalan)

2. **High OC firms NDX FAANG profile birebir match** (low PP&E/AT
   + growth-tilted + low leverage + high Tobin's Q + high operating
   leverage). Wiki amaç evrenleri NDX top 100 non-financial: tech
   sektör SG&A ağırlıklı (sales force + customer acquisition + IT
   outlays + employee training), High OC quintile dominantı.

3. **Operating leverage explanation reddedilir** ([s.10] DOL-
   controlled sort 3.1% spread sig 1%); OC factor premium **firm-
   specific worker-embodied risk** yapısal — risk premium yorumu
   güçlü.

4. **Industry-relative methodology** size-neutralizing (sektör
   içi rank); wiki amaç evrenleri (S&P 500 + NDX) industry-spesifik
   Bm distortions için doğal fit. Mohanram G-Score industry-median
   paterni paralel ([[papers/mohanram2005_g_score]] G-Score 8-component
   industry-median 2-digit SIC); Eisfeldt-Papanikolaou FF17 + within
   industry quintile ↔ G-Score 2-digit SIC industry-median methodology
   ailesi.

5. **Annual June rebalance default** wiki proje amacıyla direct
   uyum; F bloğu 4 paper × annual rebalance methodology continuity
   (Lev-Sougiannis + Peters-Taylor + Lev-Srivastava + Eisfeldt-
   Papanikolaou) — UMD/QMJ aylık-orijinal annual uyarlama
   sensitivity endişelerinin TERSİ.

6. **Sample sonu 2008 caveat**: post-2008 (FAANG era + COVID + AI
   2009-2024) out-of-sample → JKP 2023 (Cycle 27) modern replication
   + Chen-Zimmermann (Cycle 29) data portal ek ingest Faz 3 backtest
   implementation ön koşul.

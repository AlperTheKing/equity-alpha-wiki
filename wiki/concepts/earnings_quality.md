---
type: concept
name: earnings_quality
related_papers: [[sloan1996_accruals_anomaly]], [[piotroski2000_f_score]], [[mohanram2005_g_score]], [[beneish_1999_m_score]], [[ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]
---

> 📝 **Cycle 38 ek**: Sloan zinciri + Ball-GLN methodology paralel [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓; Cop = Ope - ΔWC accrual-cash flow decomposition methodology Sloan paterni paralel ama investor fixation hypothesis çürütme (Ball-GLN [s.10] explicit "inconsistent with Sloan's (1996) hypothesis that investors 'fixate' on profitability per se"); mispricing alternative (under-reaction to cash flow gradually corrected over decade); wiki taraf tutmaz Cochrane mathematical equivalence; Sloan zinciri (F_ACCRUAL/G3/QMJ ACC) + Profitability zinciri 4. halka Cop **birleşim noktası** Ball-GLN methodology link.

# Earnings Quality — Raporlanan Karların Persistence ve Cash-Flow Desteği

> 📝 **Sayfa omurgası: [[sloan1996_accruals_anomaly]]** — earnings quality'nin
> kanonik origin paperı + ana mekanizma referansı. F-Score F_ACCRUAL ve
> G-Score G3 binary versiyonları Sloan'un continuous decile yaklaşımının
> winner-loser identification çatısına simplifikasyonu.

> 📝 **Cycle 18 ek — forensic boyut**: [[beneish_1999_m_score]] ingest
> sonrası earnings_quality concept 3-katmanlı methodology hierarchy
> kazandı:
> 1. **Persistence boyutu** (Sloan 1996 origin): cross-section returns
>    mispricing detection
> 2. **Composite element boyutu** (Piotroski F_ACCRUAL + Mohanram G3):
>    binary score winner-loser identification
> 3. **Forensic detection boyutu** (Beneish 1999 M-Score): GAAP
>    violation classification, fraud detection
> Üç boyut **iki epistemik düzlem**: (a) mispricing detection
> (1+2 — return prediction); (b) fraud detection (3 — binary
> classification).

## Tanım

Bir firmanın raporlanan kazançlarının (earnings) **gelecekteki kazançları ne ölçüde
predict ettiği** ve **operasyonel cash flow ile ne ölçüde desteklendiği**.
Yüksek-kaliteli kazanç:
1. **Persistent** (gelecekte tekrar etmeye eğilimli) → CFO component dominantsa
2. **Cash-flow tarafından desteklenmiş** (yüksek accrual değil) → Sloan
   anomalisinin core'u
3. **Manipulasyon belirtisi taşımıyor** (forensic-quality) → Beneish M-Score
4. **Conservatism muhasebe politikalarıyla uyumlu** → Penman-Zhang

Düşük-kaliteli kazanç: cash-flow olmadan büyük accrual'lerle, transitory items
ile, manipulasyon belirtileriyle bilankoyu süslüyor.

## Sloan'ın kanonik formülasyonu [[sloan1996_accruals_anomaly]] [s.291-292]

```
Earnings_t = CFO_t + Accruals_t
```

`Earnings_{t+1} = α + β_CFO · CFO_t + β_Accrual · Accrual_t + ε`

- `β_CFO` (cash flow persistence) **>** `β_Accrual` (accrual persistence)
- Cash flow component geleceğe taşınır; accrual component mean-reverting

**Pratik sonuç:** İki firma aynı `Earnings_t`'ye sahip olsa bile, CFO-ağırlıklı
firma'nın gelecek earnings'i daha güçlü; accrual-ağırlıklı firma'nın earnings'i
mean-revert eder.

## Earnings quality'nin alt-boyutları

### 1. Persistence
- Empirik kanıt: [[sloan1996_accruals_anomaly]] [s.291-292, Tablo 2-3];
  earnings persistence regression'da CFO ve accrual coefficient farkı.

### Investment-related accruals (sub-dimension)

[[cooper_gulen_ion2018_asset_growth_factor_models]] kanıtı: total accruals
ve total asset growth bileşenleri **partial overlap**:
- Working capital changes hem Sloan total accruals'ın hem CGS asset growth'un
  bileşeni
- **Implication for wiki:** F_ACCRUAL (binary) ve CMA / Asset_Growth factor
  exposure'ı birlikte kullanmak partial redundancy yaratır
- Decompose için Fairfield-Whisenant-Yohn (2003) (Tier 2 #37) accrual + asset
  growth ayrımı yapar — wiki'de yok
- Detay: [[asset_growth_anomaly]] sayfasında Sloan ↔ CGS overlap analizi

### 2. Cash-flow support (accrual quality)
- **Kanonik origin:** [[sloan1996_accruals_anomaly]] — accruals_anomaly
  spesifik mekanizması: investor fixation + persistence farkı + delayed
  reaction. Detay: [[accruals_anomaly]].
- **Empirik kanıt:**
  - Sloan headline: hedge return raw +10.4%/yıl (1962-1991, NYSE+AMEX)
    [Tablo 6, s.305]
  - Size-adjusted ~+2.9% (t=1.64) marjinal — anomaly size-loaded
- **Wiki'deki uygulamalar:**
  - F-Score F_ACCRUAL bileşeni [[piotroski2000_f_score]] [s.7]: `CFO > NI` ise 1
  - G-Score G3 bileşeni [[mohanram2005_g_score]] [s.9]: `CFO > NI` ise 1
    (firm-level threshold, industry-median değil)
  - [[Accruals]] standalone factor entity (Sloan continuous decile)

### Intangibles-related accruals (Cycle 15 ek — Lev-Sougiannis ingested)

[[lev_sougiannis_1996_rd_capitalization]] R&D giderleştirmenin
geleneksel Sloan accruals formülünü distort etme mekanizması (Cycle
9-10'da placeholder vardı, şimdi dolar):

**Mekanizma:**
- R&D giderleştirme tek-yıllık expense → working capital değişimi
  azalır (R&D harcaması doğrudan income statement'tan düşülür)
- Sloan total accruals formülü: `(ΔCA - ΔCash) - (ΔCL - ΔSTD -
  ΔTaxesPayable) - Depreciation` — working capital değişimi small
  → "düşük accrual" görünür
- Ama gerçekte R&D yatırımı capex paralel (uzun-dönem benefit
  yaratıyor [[lev_sougiannis_1996_rd_capitalization]] Tablo 3 useful
  life 5-9 yıl)
- Tech firmalarda bu bias **sistematik**: NDX (FAANG-dominant) evrende
  Sloan accruals signal yapay düşük

**Lev-Sougiannis çözüm:**
- R&D capitalize edildiğinde `RA_it = Σ_k δ_k × RD_{i,t-k}` adjusted
  amortization expense; balance sheet'te R&D capital asset olarak
  görünür
- Adjusted Sloan accruals = traditional accruals + (RD_t - RA_t)
  → tech firma signal düzeltilir

**Q26 (tech firma accrual ölçümü R&D distortion) partial cevap:**
[[concepts/intangibles_adjusted_accounting]] F bloğu anchor concept'te
detay; Peters-Taylor 2017 (Cycle 16 ingest) total intangible capital
ile tam cevap.

> 📝 Wiki için: Sloan accruals dört darbeden 4/4 hayatta kalan factor
> ([[concepts/post_publication_decay]] sentez tablosu) — ama bu
> kanıt **manufacturing-heavy 1962-1991 sample**'da. Modern tech-heavy
> evrende Sloan accruals signal-to-noise ratio düşer; Faz 3 NDX
> spec'inde **intangibles-aware accruals** kullanımı gerekli.

### 3. Forensic / manipulation flag — KAPANDI Cycle 18

[[beneish_1999_m_score]] ingest sonrası bu boyut tam empirik temellendi.

**Beneish 1999 8-bileşenli M-Score** (5 sig + 3 insig):
- ✅ DSRI (Days Sales in Receivables) — t=6.02
- ✅ GMI (Gross Margin) — >2σ
- ✅ AQI (Asset Quality) — t=3.20
- ✅ SGI (Sales Growth) — >5σ
- ✅ TATA (Total Accruals to TA) — sig
- ❌ DEPI, SGAI, LVGI insig

**Performans**: Holdout sample model identifies ~50% manipulators
prior to public discovery; pseudo-R² 30.6% WESML / 37.1% unweighted.

**Mispricing detection vs fraud detection — iki epistemik düzlem**:

| Boyut | Sloan 1996 (mispricing) | Beneish 1999 (fraud) |
|---|---|---|
| Hedef | Cross-section returns | Manipulator/non-manipulator binary |
| Metodoloji | Decile sort + hedge return | Probit + classification probability |
| Mekanizma | Investor fixation + persistence | GAAP violation detection |
| Sonuç tipi | Long Q5 short Q1 | Filter (high M-Score elenir) |
| Wiki kullanım | Standalone factor | Ek katman (ek filter) |

**TATA bileşeninin origin attribution dual pattern (Cycle 18 keşif)**:
- Beneish reference list [s.20-21] **Sloan 1996 explicit listed
  DEĞİL**; Healy 1985 + Jones 1991 cite ediyor (earnings management
  research)
- F_ACCRUAL/G3 origin paterninden **sapma**: Sloan değil, Healy-
  Jones hattı
- Methodology paralel (working capital change - depreciation aynı
  yapı), literatür hattı **farklı**

### 4. Conservatism
- Karları erken/geç tanıma muhasebe politikası
- Penman-Zhang (Tier 2 #34, henüz ingest edilmedi)

## Wiki'de mevcut kanıt — 3-katmanlı methodology hierarchy (Cycle 18 update)

| Boyut | Epistemik düzlem | İlgili sayfa(lar) | Kanıt durumu |
|---|---|---|---|
| **1. Persistence** | Mispricing detection | [[sloan1996_accruals_anomaly]] [Tablo 2-3] | β_CFO > β_Accrual, 1962-1991 NYSE+AMEX |
| **2. Cash-flow support (accrual quality)** | Mispricing detection (composite element) | [[sloan1996_accruals_anomaly]] (origin), [[accruals_anomaly]] (mekanizma), [[Accruals]] (factor entity), [[F_Score]] F_ACCRUAL, [[G_Score]] G3 | Sloan +10.4% raw hedge; F-Score / G-Score binary versiyonları |
| **3. Forensic / manipulation flag** | **Fraud detection** | [[beneish_1999_m_score]], [[M_Score]] | **Cycle 18 KAPANDI**: 8-bileşenli M-Score (5 sig + 3 insig); pseudo-R² 30.6% / 37.1%; ~50% holdout identification |
| Conservatism | Mispricing detection (alternatif boyut) | _(boş)_ | Penman-Zhang 2002 ingest edildiğinde |

## Modern asset pricing tartışması

[[hou_mo_xue_zhang_2020_security_analysis]] q-factor model lens'inde earnings
quality signal'leri (özellikle accruals) **investment factor (I/A) + ROE
factor exposure'ları** üzerinden büyük ölçüde absorb edilebilir. Bu, Sloan'ın
"investor fixation" mispricing yorumunun tek alternatif olmadığını gösterir —
mathematical equivalence ile risk premium yorumu da mümkün
([[cochrane2011_discount_rates]] [s.20]). Wiki taraf tutmaz; pratik strateji
tasarımı her iki yorumda da aynı portföye götürür.

## İlgili paperlar (ingested)

- [[sloan1996_accruals_anomaly]] — accruals_anomaly origin; earnings quality
  sayfasının kanonik ana referansı
- [[piotroski2000_f_score]] — F_ACCRUAL bileşeni; earnings quality'yi binary
  sinyale çevirme yaklaşımı
- [[mohanram2005_g_score]] — G3 bileşeni; F_ACCRUAL paterni
- [[li_mohanram2019_quality_value]] — F-Score continuous-rank revision; Sloan
  accrual signal continuous version
- [[hou_mo_xue_zhang_2020_security_analysis]] — q-factor model çerçevesi;
  earnings quality signal'lerinin risk premium yorumu
- [[beneish_1999_m_score]] — **forensic boyut origin (Cycle 18)**;
  8-bileşenli M-Score (5 sig + 3 insig); manipulator/non-manipulator
  binary classification; mispricing detection vs fraud detection
  epistemik düzlem ayrımı; TATA bileşeni Sloan total accruals
  methodology paralel ama literatür hattı Healy 1985 + Jones 1991
  (Sloan değil)

## İlgili paperlar (henüz ingest edilmedi)

- Ball-Gerakos-Linnainmaa-Nikolaev (2016) — accruals + CFO + OP joint
  cross-section (Tier 1 #9)
- Richardson-Sloan-Soliman-Tuna (2005) — accrual reliability decomposition
  (Tier 2 #35)
- Penman-Zhang (2002) — conservatism + earnings quality (Tier 2 #34)
- Hirshleifer-Hou-Teoh-Zhang (2004) — Net Operating Assets cumulative accrual
  (Tier 2 #36)
- Beneish-Lee-Tarpley (2001) — M-Score → return prediction direct
  evidence (paywall, hala eksik); Q9 tam cevabı için
- Healy (1985) "The Effect of Bonus Schemes on Accounting Decisions" —
  Beneish TATA literatür hattı kökü; earnings management research origin
- Jones (1991) — discretionary accruals model; Beneish TATA literatür
  hattı kökü

## Strateji tasarımına spesifik implikasyon

Faz 3 strateji tasarımında **earnings quality filtresi** komposit skorun
ayrılmaz parçası olmalı:
- Pure P/E veya EPS growth ranking (earnings quality kontrolsüz) **yetersizdir**.
- En azından `CFO > NI` (accrual screen) eklenmeli — F-Score F_ACCRUAL ve
  G-Score G3'ün çekirdeği.
- Continuous accrual signal de değerlendirilebilir (Sloan decile sortu) ama
  size-adjusted spread marjinal olduğu için large-cap evrende standalone
  factor olarak güç sınırlı; komposit skor içinde **complementary** kullanım
  daha sağlam.
- Beneish M-Score forensic filter olarak Cycle 18'de tam temellendi:
  F-Score / G-Score / F&V/P / G&V/P combined yaklaşımına ek katman
  (M-Score yüksek olanlar evrenden çıkar, sonra winner-loser scoring).
  Faz 3 design Q9 (combined performance) + Q45 (value-trap-avoidance
  filter) ile birlikte değerlendirilir.
- Tech firma'larda R&D giderleştirme accrual hesaplamasını distorts ediyor
  olabilir → Q26 (F bloğu 3 ayak methodology Cycle 17'de tamam).
  Beneish M-Score 8 bileşeni intangibles-aware değil → Q47 yeni: NDX
  evren M-Score false positive riski (high SGI + high AQI tech firmlarda
  yapısal yüksek).

## İlgili kavramlar

- [[accruals_anomaly]] — earnings_quality "Cash-flow support" boyutunun
  spesifik mekanizma sayfası (hierarchical alt-kavram)
- [[fundamental_scoring]] — earnings quality binary/continuous skorlamaya nasıl
  girer
- [[discount_rates]] — earnings quality'nin discount rate kanalıyla yansıması
  (Cochrane çerçevesi)
- [[winner_loser_identification]] — F_ACCRUAL / G3 binary versiyonları bu
  paradigma içinde
- [[contextual_fundamental_analysis]] — Sloan firm-level threshold (CFO > NI)
  G-Score industry-median yaklaşımından farklı

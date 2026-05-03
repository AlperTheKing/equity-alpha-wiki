---
type: concept
name: accruals_anomaly
related_papers: [[sloan1996_accruals_anomaly]]
---

# Accruals Anomaly — Sloan'ın Spesifik Mekanizması

> 📝 [[earnings_quality]] çatısının spesifik bir alt-mekanizması.
> earnings_quality "Cash-flow support (accrual quality)" boyutunun
> kanonik kanıt + mekanizma referansı bu sayfa.

## Tanım

**Accruals anomaly:** Yüksek-accrual firmaların gelecekte sistematik düşük
getiri, düşük-accrual firmaların sistematik yüksek getiri üretmesi.
[[sloan1996_accruals_anomaly]] tarafından ilk kez sistematik test edildi.

## Sloan'ın spesifik mekanizması (3 bileşen)

### 1. Earnings persistence farkı [[sloan1996_accruals_anomaly]] [s.291-292]

```
Earnings_t = CFO_t + Accruals_t
```

`Earnings_{t+1} = α + β_CFO·CFO_t + β_Accrual·Accrual_t + ε`

- `β_CFO` (cash flow persistence) **>** `β_Accrual` (accrual persistence)
- Cash flow component geleceğe taşınır; accrual component mean-reverting

### 2. Investor fixation [[sloan1996_accruals_anomaly]] [s.293, H2]

Yatırımcılar earnings'in **toplam değerine** "fixate" olur — alt-bileşenlere
attention etmez. Kavramsal kaynak: Bloomfield-Libby 1995, Hand 1990 davranışsal/
deneysel araştırma.

**Pratik sonuç:**
- Yüksek-accrual firmalar **overpriced** (earnings yüksek görünür ama
  sürdürülemez)
- Düşük-accrual firmalar **underpriced** (earnings düşük görünür ama CFO
  güçlü)

### 3. Delayed correction [[sloan1996_accruals_anomaly]] [s.293-294, H2(iii)]

Mispricing düzeltmesi **future earnings announcement window'larında** realize
ediyor. 4 quarterly earnings announcement (3-day window each) etrafında
abnormal return concentration → market'in delayed reaction'ı explicit
gözlemlenir [Tablo 8].

## Sloan'ın empirik kanıtı (özet)

- Hedge return raw: **+10.4%/yıl** (1962-1991, NYSE+AMEX, 40,679 firm-year)
  [Tablo 6, s.305]
- Size-adjusted: ~+2.9% (t=1.64, marjinal) — anomaly size-loaded
- Multi-year decay: yıl 1 = 10.4%, yıl 2 = 4.8% — mean-reverting
- Earnings announcement window'larında abnormal return concentration

## earnings_quality ile ilişkisi (hierarchical)

```
[[earnings_quality]] (çatı)
   ├── Persistence
   ├── Cash-flow support (accrual quality)  ←  [[accruals_anomaly]] (bu sayfa)
   ├── Forensic flag (manipulation)
   └── Conservatism
```

- earnings_quality genel bir **kalite kavramı**
- accruals_anomaly Sloan'ın **spesifik mispricing mekanizması** (fixation +
  persistence farkı + delayed reaction)
- F-Score F_ACCRUAL ve G-Score G3 her iki sayfaya da dahil ama mekanizma
  açıklaması burada

## Modern asset pricing tartışması

[[hou_mo_xue_zhang_2020_security_analysis]] q-factor model lens'inde accrual
signal'in **risk premium yorumu** mümkün:
- Investment factor (I/A) accrual ile yapısal ilişkide (working capital +
  capital expenditure netleştirilmesi)
- Accruals'un getirisi q5 model exposure'larıyla **kısmen span ediliyor**
  olabilir
- Sloan'ın "investor fixation" davranışsal yorumu vs HMXZ "risk premium"
  yorumu mathematical equivalence'la birbirini dışlamaz
  ([[cochrane2011_discount_rates]] [s.20])

> 📝 Wiki taraf tutmaz; pratik strateji tasarımı her iki yorumda da aynı
> portföye götürür (long düşük-accrual + short yüksek-accrual).

## Bu wiki'nin strateji tasarımına spesifik implikasyon

- **Komposit skor bileşeni:** F-Score F_ACCRUAL ve G-Score G3 binary
  versiyonları, accruals_anomaly'nin "winner-loser identification" çatısına
  uydurulmuş halleri.
- **Standalone factor:** [[Accruals]] entity sayfası; modern strateji bu
  signal'i continuous decile sortla doğrudan kullanabilir ama:
  - Size-loaded → large-cap evrende zayıf
  - CMA / I/A factor exposure ile partial overlap
  - NDX tech firmalarda intangibles distortion riski (Q26)
- **Faz 3 strateji tasarımı için:**
  1. F_ACCRUAL / G3 binary signal'lerini composite skorda korumak (Sloan'ın
     simplified versiyonu, robust)
  2. Standalone Accruals factor exposure'u q5 / FF5 baseline regression'da
     control olarak raporlamak
  3. Tech firma'lar için R&D-adjusted accrual versiyonu değerlendirmek
     (Lev-Sougiannis 1996, Peters-Taylor 2017 ingestleri ile)

## Sonraki literatür dalları (Tier 2 ingest adayları)

- **Richardson-Sloan-Soliman-Tuna (2005)** "Accrual Reliability, Earnings
  Persistence and Stock Prices" (Tier 2 #35) — accrual decomposition reliability
  axes'ine göre
- **Hirshleifer-Hou-Teoh-Zhang (2004)** "Net Operating Assets" (Tier 2 #36) —
  cumulative accrual signal (balance-sheet bloat)
- **Fairfield-Whisenant-Yohn (2003)** — accrual + asset growth ayrımı (Tier 2 #37)
- **Green-Hand-Soliman (2011)** "death of accruals anomaly" — post-publication
  decay (Tier listesi dışı, Cycle 10+ aday)
- **Discretionary vs non-discretionary accruals** — Jones 1991, Modified
  Jones (Dechow vd. 1995) — earnings management literatürü; Beneish 1999
  M-Score forensic ile bağlantı

## İlgili paperlar (ingested)

- [[sloan1996_accruals_anomaly]] — origin paper
- [[piotroski2000_f_score]] — F_ACCRUAL Sloan paterni
- [[mohanram2005_g_score]] — G3 Sloan paterni
- [[li_mohanram2019_quality_value]] — F-Score continuous-rank revision
  (Sloan accrual signal continuous versiyon)
- [[hou_mo_xue_zhang_2020_security_analysis]] — q-factor model lens'inde
  accruals signal partial subsume

## İlgili kavramlar

- [[earnings_quality]] — çatı kavram
- [[fundamental_scoring]] — accruals composite skorlamada kritik bileşen
- [[winner_loser_identification]] — F_ACCRUAL / G3 binary versiyonları bu
  paradigma içinde
- [[contextual_fundamental_analysis]] — Sloan firm-level threshold (CFO > NI)
  G-Score industry-median yaklaşımından farklı

---
type: concept
name: value_premium
related_papers: [[famafrench1993_three_factor]], [[piotroski2000_f_score]], [[famafrench2015_five_factor]], [[lev_srivastava_2020_value_failure]], [[lev_sougiannis_1996_rd_capitalization]], [[peters_taylor_2017_intangible_capital]]
---

# Value Premium — Düşük-Fiyatlı Hisselerin Yüksek Beklenen Getirisi

> 📝 **Cycle 17 Lev-Srivastava 2020 ingest sonrası yapısal zenginleşme.**
> Cycle 12-16 boyunca izole concept (4-9 inbound); Cycle 17'de
> Lev-Srivastava 2020 paperı doğrudan bu sayfa için kritik kanıt
> sağlıyor (post-2010 value crisis decomposition + intangibles bias +
> mean reversion slowdown). Cycle 16 audit'te tespit edilen "Faz 2'de
> izole concept çözümü" probleminin **Cycle 17 erken çözümü**.

## Tanım

**Value premium:** Yüksek book-to-market (veya düşük P/E, P/CF, P/S) hisselerin,
düşük book-to-market (growth) hisselerden **uzun-vade ortalamada daha yüksek
getiri** üretmesi.

Empirik formülasyon: HML faktör portföyü (high-BM long, low-BM short).
[[famafrench1993_three_factor]] [Tablo 2, PDF p.13] HML mean = 0.40%/ay (t=2.91),
1963-1991. [[famafrench2015_five_factor]] [Tablo 4 Panel A, s.37] HML mean
0.37%/ay (t=3.20), 1963-2013.

## Risk-vs-mispricing tartışması — 3 yorum boyutu

Value premium'un *neden* var olduğu üç ana yorum (Cycle 17 Lev-Srivastava
ile genişletildi):

### 1. Risk-tabanlı (Fama-French çizgisi)

[[famafrench1993_three_factor]] [PDF p.53] yorumu: high-BM = financial distress
proxy; high-BM firmaların yüksek getirisi *sistematik distress riski* için
fair compensation. Yani value premium **gerçek risk premium**.

### 2. Behavioral mispricing (LSV çizgisi)

Lakonishok-Shleifer-Vishny (1994, henüz wiki'de ingest edilmedi, Tier 1 #7):
high-BM firmalar **"naive" yatırımcılar tarafından underprice** ediliyor; "too
pessimistic expectations" sonra geri dönüyor → premium mispricing'in düzelmesi.
[[piotroski2000_f_score]] [s.4-5] bu yorumu destekleyen kanıt: spread'in 1/6'sı
4 quarterly earnings announcement penceresinde realize ediyor → market signal'i
ex ante fiyatlamıyor.

### 4. Quality at a Reasonable Price — combined approach (Cycle 19 ek — Asness QARP framework)

[[asness_frazzini_pedersen_2019_qmj]] [Section 7] **QARP (Quality at a
Reasonable Price)** = quality × n − P/B; n yakın 1 highest alpha (US
long sample 1956-2012 + global broad sample).

**Conceptual paralel** (Cycle 7'de combined_quality_value concept açılma
paterni paralel):
- Li-Mohanram 2019 F&V/P + G&V/P combined paradigm — simple quintile
  intersection (binary)
- Asness 2019 QARP — continuous quality score × n − P/B score
- İki paper aynı paradigma (combined approach), farklı operationalization
- Graham-Dodd 1934 paralel: "Investment must always consider price as
  well as quality" (Asness paper [Section 7] explicit cite)

**Wiki için**: Faz 3 strategy spec için **QARP framework anchor**;
Li-Mohanram (binary intersection) + Asness QARP (continuous score)
iki alternatif operationalization. Q21 (combined methodology) + Q50
(QARP NDX kalibrasyonu) paralel.

**QMJ-HML negative correlation** [Asness Section 5]: high-quality
stocks have high prices → QMJ "long" + HML "short" tarafları
overlap; QARP optimal kombinasyon.

### 3. Intangibles measurement-error mispricing (Cycle 17 ek — Lev-Srivastava çizgisi)

[[lev_srivastava_2020_value_failure]] **3. yorum boyutu**: post-1989 value
premium decay'inin önemli kısmı **accounting deficiency** kaynaklı —
intangibles expensing book value mismeasurement → high-MB glamour stocks
yapay olarak overpriced görünür → vanilla HML strateji "yanlış stocks
short ediyor".

**Mekanizma**:
- 1980'lerden itibaren intangibles proliferation (Figure 2 Lev-Srivastava)
- Reported BV intangibles eksik → MB ratio yapay yüksek (intangibles-yoğun
  firms'da)
- Glamour stocks "overvalued by reported metrics" ama fundamentals'a göre
  fair-priced → short bacağı kayıp
- **Adjusted BV methodology** (R&D + SG&A capitalize) ile 39 yılın 34'ünde
  conventional strategy'i geçer

**LSV ile ilişki**: LSV mean reversion mekanizması korunur ama post-2007
**attenuated** [Lev-Srivastava Section 8]: rank correlation glamour
45-47% → 60%, length of stay 3.5 → 4.5 yıl. Yani LSV "extrapolation
bias" hala var ama macro shocks (2007 crisis bank lending contraction)
mean reversion'ı yavaşlattı.

> 📝 [[cochrane2011_discount_rates]] [s.20] perspektifi: "rational" vs.
> "behavioral" abstract düzeyde tartışılamaz; ikisi mathematically equivalent
> formulations. **Wiki bu felsefi seçimi tutmaz**, sadece premium'un *gerçek*
> ve *tutarlı* olup olmadığına bakar. Lev-Srivastava 3. yorum boyutu
> (intangibles mispricing) Cochrane mathematical equivalence çerçevesinde
> aynı bulgu **risk premium** yorumuna eşdeğer (post-2007 high risk premia
> intangibles-yoğun firms için).

## Empirik kanıt durumu (wiki'de mevcut)

| Dönem | Sample | HML mean (%/ay) | t-stat | Kaynak |
|---|---|---|---|---|
| 1963-07 / 1991-12 | NYSE/AMEX/NASDAQ ex-fin | 0.40 | 2.91 | [[famafrench1993_three_factor]] [Tablo 2] |
| 1963-07 / 2013-12 | aynı | 0.37 | 3.20 | [[famafrench2015_five_factor]] [Tablo 4 Panel A] |
| 1963-07 / 1993-12 | aynı | 0.46 | 3.42 | [[carhart1997_four_factor]] [Tablo II] |

> 📝 **Standalone HML primum 1963-2013 boyunca pozitif ve istatistiksel olarak
> anlamlı kalmıştır.** Ancak FF15 [Tablo 6, s.19] HML'in 5-faktör altında span
> edildiğini gösterir (a≈0); bu primum'un *kaybolması* değil, daha temel
> faktörlere (RMW, CMA) decomposability'si.

## Post-2010 collapse — Lev-Srivastava 2020 anchor (Cycle 17)

[[lev_srivastava_2020_value_failure]] post-2010 value crisis'in
**definitive empirik analizi**:

### Decade-by-decade vanilla HML returns [Section 3, Figure 1]

$1 invested January 1 of each decade, end-of-decade cumulative return:

| Decade | $1 → end | Return |
|---|---|---|
| **1970s** | $2.02 | **+102%** "swan song" |
| **1980s** | $1.75 | **+75%** |
| **1990s** | $0.90 | **-10%** (tech bubble glamour shorting kaybı) |
| **2000-2006** | brief resurgence | tech bubble shorting boost |
| **2007-2018** | negative | "yielded negative returns" |

**Headline**: Vanilla value strategy **1989'dan beri faltering**, "post-2007
collapse" yorumu yetersiz; faltering 1989 başlangıç, 2007 financial
crisis sonrası **derinleşti**.

### Adjusted methodology dramatic effect [Section 5, Figure 3]

Intangibles-aware adjusted BV ile 39 yılın **34'ünde** conventional'ı
geçer:

| Decade | Conventional | Adjusted | Adjusted advantage |
|---|---|---|---|
| 1980s | $1.75 | $2.86 | +68% |
| 1990s | $0.90 | ~$2.00 | dramatic |
| 2007-2018 | negative | "reasonably positive" | dramatic |

→ **Vanilla HML decay'in büyük kısmı intangibles bias kaynaklı**, gerçek
value premium adjusted methodology ile hayatta.

### Iki sebep decomposition [Lev-Srivastava ana tezi]

1. **Accounting deficiencies (intangibles expensing)** — Section 4-6
2. **Mean reversion slowdown post-2007** — Section 7-9 (3 measure: rank
   correlation, length of stay, large price upticks/downticks)

### Macro mekanizma post-2007 [Section 9-10]

- Value firms (banking, retail, insurance, wholesale, utilities = 50-60%
  large value): bank lending contraction + consumer demand fall →
  trapped, R&D/IT yapamıyor; <1% issued stock annually 2007-2018
- Glamour firms (software, pharma, electronics): scalable intangibles
  + first-mover + network effects → **2007-2018 highest profitability
  since 1970**

### Sample focus caveat — wiki için kritik

Lev-Srivastava [s.16 footnote 13]: Section 8-11 (mean reversion + macro
+ escape) için **50% LARGEST stocks focus** (top 1500 of CRSP all-stocks).
S&P 500 ≈ top 500 ⊂ subset → adequate proxy.

> 📝 **Q1 fully-answered (Cycle 17)** — wiki'nin priori sorduğu "S&P
> 500 evreninde value (P/B, P/E) faktörünün post-2000 performansı nedir?"
> sorusunun definitive cevabı; detaylar [[lev_srivastava_2020_value_failure]]
> Goal Alignment large-cap eksen + [[meta/open_questions]] (Q1 fully-
> answered).

## Value premium'un alt-türleri

- **B/M (book-to-market):** klasik FF formülasyonu
- **E/P (earnings yield):** P/E ratio'nun tersi
- **CF/P (cash flow yield):** EBITDA / EV gibi türevleri
- **D/P (dividend yield):** dividend-payer firmalarda ek anchor
- **V/P (intrinsic value / price):** Frankel-Lee (1998) — analyst forecast
  + residual income value model (Tier 1 #8)

> 📝 Bu wiki'de henüz E/P, CF/P, D/P, V/P alt-türleri için ayrı kanıt sayfası
> yok. Lakonishok-Shleifer-Vishny 1994 ve Frankel-Lee 1998 ingestleri ile
> dolacak.

## Value premium'un büyük-cap evrendeki durumu

Açık soru. Bu wiki'de doğrudan S&P 500 / Nasdaq 100 evrende value premium
zaman serisi yok. [[famafrench1993_three_factor]] NYSE/AMEX/NASDAQ all-stocks
evrende test eder; [[piotroski2000_f_score]] [Tablo 4, s.19] **large-cap'te
fundamental refinement spread'in zayıfladığını** gösterir ama saf value premium
large-cap'te de var.

## Bu wiki'nin strateji tasarımına spesifik implikasyon — Cycle 17 sonrası netleşti

- **Saf value tilt (uzun high-BM all-firms) bu wiki'nin tasarım hipotezi
  DEĞİL.** Spread'in *standalone* primum'u kullanılabilir ama wiki'nin amacı
  daha rafine: [[winner_loser_identification]] yaklaşımıyla value uzun bacak
  içinde diferensiyel skor.
- Strateji tasarımının value tarafında F-Score (veya muadili) **anchor olarak
  value tilti**, **modulator olarak fundamental winner-loser ayrımı** kullanır.
- **Cycle 17 sonrası 3 ek tasarım rec'i (Lev-Srivastava anchored):**
  1. **Vanilla HML reject; adjusted HML baseline** (intangibles-aware
     adjusted BV ile inşa) — F bloğu 3 ayak methodology infrastructure
     hazır
  2. **Value-trap-avoidance filter** — Lev-Srivastava Logit Table 1
     escape attributes (intangibles + capex + sales growth + debt)
     standalone screen veya F&V/P combined ek katman (Q45 yeni Faz 3
     design decision)
  3. **Post-2010 macro context aware** — banking/retail/utilities
     sektörlerinde sektör overweight'lar trapped; sektör nötrleştirme
     veya GICS sektör filter Faz 3 strategy spec'inde gerekli

## İlgili paperlar (ingested)

- [[famafrench1993_three_factor]] — ilk mimicking-portföy formülasyonu
- [[famafrench2015_five_factor]] — value premium decomposition (RMW + CMA
  ile span); HML redundancy bulgusu vanilla HML için
- [[piotroski2000_f_score]] — value uzun bacağı içinde diferensiyel skor
- [[carhart1997_four_factor]] — HML 4F'in sabit bileşeni
- [[cochrane2011_discount_rates]] — value puzzle'ın "absence of beta"
  formülasyonu [s.12]
- [[lev_sougiannis_1996_rd_capitalization]] — F bloğu #1; R&D
  capitalization adjusted BV methodology temeli (Lev-Srivastava'nın
  24 yıl önceki origin paperı; aynı yazar Baruch Lev)
- [[peters_taylor_2017_intangible_capital]] — F bloğu #2; total
  intangible capital generalization (Lev-Srivastava SG&A allocation
  methodology paralel)
- [[lev_srivastava_2020_value_failure]] — **F bloğu #3 KAPANIŞ
  (Cycle 17)**: post-2010 value crisis decomposition + intangibles-aware
  adjusted strategy + Logit escape attributes; **Q1 fully-answered
  anchor**
- [[asness_frazzini_pedersen_2019_qmj]] — **Cycle 19 ek**; QARP
  framework (Quality at a Reasonable Price) — quality × n − P/B
  combined approach; Li-Mohanram F&V/P + G&V/P paterninin Asness
  paralel'i; value_premium 4. yorum boyutu (combined approach);
  QMJ-HML negative correlation

## İlgili paperlar (henüz ingest edilmedi)

- Lakonishok-Shleifer-Vishny (1994) — mispricing yorumu (Tier 1 #7);
  Lev-Srivastava extension ile builds on
- Frankel-Lee (1998) — V/P ratio (Tier 1 #8)
- Asness-Frazzini-Pedersen (2019) — Quality-Minus-Junk + value (Tier 1 #6)
- Asness-Liew-Pedersen-Thapar (2020) — Deep Value (Tier 3 #61)
- Eisfeldt-Papanikolaou (2013) — Organization Capital (Tier 2 #28);
  Q41 4-way horse race tamamlamak için

## İlgili kavramlar

- [[discount_rates]]
- [[winner_loser_identification]] — value uzun bacağı içinde rafine seçim
- [[factor_zoo]] — value premium'un factor zoo içindeki yeri
- [[earnings_quality]] — value firma kalite ayrımı için kritik
- [[intangibles_adjusted_accounting]] — F bloğu hub; adjusted HML
  methodology origin (R&D-only → total → post-2010 application)
- [[post_publication_decay]] — vanilla HML decay'in MP %35 aggregate'tan
  daha agresif olduğunun Lev-Srivastava ile pekişmesi
- [[asset_growth_anomaly]] — CMA-HML 0.70 korelasyon; investment cluster
  Cochrane #2 cevabı

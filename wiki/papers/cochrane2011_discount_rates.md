---
type: paper
authors: [Cochrane, John H.]
year: 2011
title: "Discount Rates"
venue: "Journal of Finance 66 (4), 1047-1108 (Presidential Address); NBER WP 16972"
url: https://www.nber.org/papers/w16972
local_path: raw/papers/cochrane_2011_discount_rates.pdf
ingested: 2026-04-27
tags: [survey, factor_zoo, discount_rates, framing, foundational_epistemic]
status: ingested
---

# Cochrane (2011) — Discount Rates

> 📝 **Atıf konvansiyonu:** `[Tablo N]` numaralı tablolar; `[s. X]` NBER WP basılı
> sayfa numarası. Embedded text extract'ten okundu
> (`raw/papers/cochrane_2011_discount_rates.txt`).

> 📝 **Paper türü:** AFA Presidential Address (2011) — survey + agenda. Yeni
> empirik faktör önermez; literatürün durumunu organize eder. **Wiki için bu
> paper'ın değeri framing'tir.**

## TL;DR

Asset pricing'in 40-yıllık paradigma kayması: "expected cashflow variation"dan
"discount rate variation"a. Cochrane'in tezi: "**Discount rate variation is the
central organizing question of current asset pricing research.**" [abstract].
- **Time-series:** Price/dividend oranı varyasyonunun **neredeyse tamamı** beklenen
  getiri (discount rate) varyasyonuna karşılık geliyor — beklenen cashflow
  varyasyonuna değil [Tablo II, s.2].
- **Cross-section:** "We thought that the cross-section of expected returns came
  from the CAPM. Now we have a **zoo of new factors**." [abstract]. Bu paper
  literatürdeki "**factor zoo**" terimini popülerleştirir [s.13].
- **Metodoloji önerisi [s.14-15]:** Yüksek-boyutlu factor zoo'da geleneksel
  portfolio sortları çalışmaz (27 değişkenle 1-10 spread sortu kuramazsın);
  multivariate panel-data regresyonları gereklidir.
- **Teori taksonomisi [s.17-22]:** Macro, Behavioral, Finance (return-based
  factors), Friction (Segmented / Intermediated / Liquidity).
- **Empirik faktör araştırmasının rolü [s.20]:** "*nice division of labor*" —
  empirik faktör çerçevesi (Fama-French tradition) anomaly'leri sistematik risk
  setine indirger; "deep" teoriler (macro/behavioral) sonra neden bu faktörlerin
  fiyatlandığını açıklar.

Bu paper, wiki'nin **epistemik iskeletini** kuracak üç temel concept sayfasına
zemin sağlar: [[discount_rates]], [[factor_zoo]], [[expected_returns_vs_cash_flows]].

## Tek Cümle Tezi

Asset pricing'in merkezi sorusu artık "fiyatlar bekleneni mi yansıtıyor?" değil
"**neden discount rate'ler bu kadar değişiyor?**"; cross-section'da CAPM yerine
artan bir "factor zoo" var ve bu zoo'yu işlemek için yeni metodoloji + teorik
çerçeve gerekli.

## Ortaya Konan Sinyal/Faktör

**Yeni faktör YOK.** Bu paper bir survey — kavramsal birleştirici. Wiki'de bu
paperdan yeni `factors/*` sayfası açılmadı. Bunun yerine üç **concept sayfası**
açıldı:
- [[discount_rates]] — kavramın tanımı, time-series ve cross-section yansımaları
- [[factor_zoo]] — 300+ faktör problemi, redundancy / multiple testing soruları
- [[expected_returns_vs_cash_flows]] — Campbell-Shiller present-value identity ve
  P/D varyasyonunun decomposition'ı

## Empirik İddialar (sayılarla)

> 📝 Cochrane bu paperda kendi yeni regresyonlarını gösterir; ana kanıt FF tradisyonu
> + Campbell-Shiller decomposition'ı.

### Time-series: DP regression [Tablo I, s.1]

CRSP value-weighted excess return üzerinde dividend yield regresyonu, 1947-2009:

`Σ R(t+j) = a + b·DP(t) + ε(t+k)`

| Horizon | b (slope) | t-stat | R² | σ[E(R)] | σ[E(R)]/σ(R) |
|---|---|---|---|---|---|
| 1 yıl | 3.8 | 2.6 | 0.09 | 5.46% | 0.76 |
| 5 yıl | 20.6 | 3.4 | 0.28 | 29.3% | 0.62 |

> 📝 Cochrane'in yorumu [s.1-2]: "1-yıl R²=0.09 düşük görünür ama economic
> significance büyük: 1 puanlık DP artışı ~4 puan getiri öngörür. Beklenen getiri
> standart sapması 5.46% — equity premium puzzle (~6%) ile karşılaştırılabilir."

### Long-run regression coefficients [Tablo II, s.2]

Campbell-Shiller decomposition: `1 ≈ b_r(k) − b_d(k) + b_dp(k)`

| Yöntem | b_r | b_d | b_dp |
|---|---|---|---|
| Direct regression k=15 | 1.01 | -0.11 | -0.11 |
| VAR implied k=15 | 1.05 | 0.27 | 0.22 |
| VAR k=∞ | 1.35 | 0.35 | 0.00 |

**Kritik sonuç [s.2-3]:** "**Long-run dividend growth coefficient ≈ 0**" — yani
P/D varyasyonunun **neredeyse tamamı** discount rate varyasyonu, expected
cashflow değil.

### Cross-section: değer puzzle'ının yeniden çerçevelenmesi [s.11-12, Figure 6]

Fama-French 10 book/market portföyü, aylık 1963-2010:
- Ortalama excess getiri: growth → value yükselir (low B/M ~0.2%/ay; high B/M
  ~0.7%/ay)
- **Market beta'lar tüm portföylerde benzer** — yani CAPM bu spread'i açıklamaz
- HML eklenince spread'in ortalaması h·E(HML) tarafından yakalanır

Cochrane formülasyonu [s.12]: "*absence of beta* is really the heart of the value
puzzle. **All puzzles are joint puzzles of expected returns and betas.**"

### Factor zoo'nun kapsamı [s.12-13]

"Expected return strategies have emerged that do not correspond to market, value,
and size betas. These include, among many others, **momentum, accruals, equity
issues and other accounting-related sorts, beta arbitrage, credit risk, bond and
equity market-timing strategies, foreign exchange carry trade, put option writing,
and various forms of liquidity provision.**" [s.12]

### Multidimensional challenge [s.13]

Cochrane'in dört sorusu:

1. "Which characteristics really provide independent information about average
   returns? Which are subsumed by others?"
2. "Does each new anomaly variable also correspond to a new factor formed on those
   same anomalies?"
3. "How many of these new factors are really important? Can we again account for
   N independent dimensions of expected returns with K << N factor exposures?"
4. "Eventually, we have to connect all this back to the central question of finance,
   why do prices move?"

> 📝 Bu dört soru wiki'nin **epistemik gündeminin omurgası**. Q15, Q16'nın
> arkasındaki "asıl soru" buradadır. Bu sorular Harvey-Liu-Zhu 2016
> (multiple testing düzeltmesi) ve Feng-Giglio-Xiu 2020 (yeni faktör testi)
> ingestleri ile *prosedürel olarak* cevaplanmaya başlar.

## Cochrane'in Metodolojik Önerisi [s.14-15]

> "We can't chop portfolios 27 ways, so I think we will end up running multivariate
> regressions ... but we must address the factor zoo, and I don't see how to do
> it by a high-dimensional portfolio sort." [s.15]

Önerdiği yapısal değişim:

`E(R_i,t+1 | C_i,t) = a + γ' · C_i,t`

`Cov(R_i,t+1, F_t+1 | C_i,t) = β(C_i,t)`

Yani "expected return as a function of characteristics" + "covariance as a function
of characteristics". Bu, ML asset pricing literatürünün (Gu-Kelly-Xiu 2020,
Kozak-Nagel-Santosh 2020) temellerinden biri.

## Cochrane'in Teori Taksonomisi [s.17-22]

Discount rate teorilerinin sınıflandırması:

1. **Fundamental investor / few frictions:**
   - **Macroeconomics** — consumption, aggregate risk, investment, GE
   - **Behavioral** — irrational expectations
   - **Finance** — return-based factors (FF tarzı), affine term structure
2. **Frictions:**
   - **Segmented markets** — limited risk-bearing
   - **Intermediated markets** — leveraged intermediaries
   - **Liquidity** — idiosyncratic, systemic, information-trading

> 📝 **"Bir division of labor"** [s.20]: Empirik FF-tradisyonu anomalies'i sistematik
> risk setine indirger; macro/behavioral/friction teorileri *neden* bu faktörlerin
> primum taşıdığını açıklar. **Bu wiki'nin amacı için en kritik framing:** strateji
> tasarımımız bilinçli olarak FF-tradisyonu içinde kalır (faktör keşfi + risk
> premia exposure'u); "neden işe yarıyor" sorusu wiki'nin scope'u dışındadır.

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Survey/agenda paper; yeni empirik strateji önermez. Yapısal "top-N stock selection" tartışması yok | N/A — agenda/framing paper |
| **Annual rebalance** | Time-series DP regresyonları **yıllık** horizon'larda örneklendirilmiş [Tablo I, s.1: 1y, 5y]; cross-section'da Fama-French aylık standartı atfedilir | N/A — paper rebalans frekansı önermiyor |
| **Large-cap evrene transfer** | Survey kapsamında değil; CRSP value-weighted market endeksi tüm evren için kullanılır. Large-cap-only ayrım yok | N/A |
| **NDX intangibles / growth firms** | Survey kapsamında değil; intangibles literatürüne atıf yapmaz | N/A |

**Strateji tasarımına net implikasyon:** Bu paper **wiki gündeminin omurgasını
sağlar**, doğrudan tasarım girdisi değil:
- Cochrane'in 4 epistemik sorusu [s.13] sonraki ingestlerin (Hou-Xue-Zhang 2020,
  Harvey-Liu-Zhu 2016, Feng-Giglio-Xiu 2020) niye gerekli olduğunu çerçeveler
- "Division of labor" framing'i [s.20] strateji tasarımının bilinçli olarak
  empirical FF tradition'unda kalmasını destekler — "neden işe yarıyor"
  sorusunu macro/behavioral teorilere bırakır
- Strateji tasarım kararlarında doğrudan referans olarak alınmaz; ancak Faz 2'de
  strateji robustness ve factor count konularında çerçeve sağlar

## Limitler ve Caveats

- **Survey paper, yeni empirik kanıt sınırlı:** Tablo I-II Cochrane'in kendi
  hesabı; geri kalan iddialar başka paperlardan çağrılır.
- **Yorumda tek-yanlı eğilim:** Cochrane "rational" / FF-tradisyonu yanlısı,
  davranışsal hipotezleri bir miktar zayıf gösterir [s.19-20]. Wiki bu nüansı
  not eder ama strateji tasarımı için bu felsefi tartışma ikincildir.
- **Faktörlerin spesifik primum'ları için kanıt YOK:** Cochrane factor zoo'nun
  varlığını söylüyor ama hangi faktörün gerçek hangisinin replication failure
  olduğunu spesifik test etmiyor. Bunun için Hou-Xue-Zhang 2020, Harvey-Liu-Zhu
  2016, Jensen-Kelly-Pedersen 2023 ingestleri.
- **Strateji uygulamasına doğrudan transfer YOK:** Bu paper bir agenda; uygulama
  reçetesi vermez. Wiki için **kavramsal dispatcher** rolündedir.
- **2010 öncesi referans havuzu:** Sonraki literatür (özellikle ML asset pricing
  ve replication crisis çalışmaları) bu paperdan sonra patladı; framing güncel
  ama empirik haritalama 15 yıl eski.

## İlgili Sayfalar

### Bu paperın ürettiği yeni concept sayfaları
- [[discount_rates]] — discount rate kavramı; time-series ve cross-section yansımaları
- [[factor_zoo]] — 300+ faktör problemi; multidimensional challenge
- [[expected_returns_vs_cash_flows]] — Campbell-Shiller present value identity

### Bu paperın update ettiği mevcut sayfalar
- [[factor_model]] — Cochrane'in "division of labor" framing'i + "absence of beta
  is the heart of the value puzzle" yorumu

### İlgili paperlar (ingested)
- [[famafrench1993_three_factor]] — "Order to chaos" — Cochrane'in övgüyle
  bahsettiği FF empirik tradition
- [[famafrench2015_five_factor]] — factor zoo'nun bir parçası; HML'in span
  edilmesi Cochrane'in 1. sorusunun ("which subsume which?") tipik örneği
- [[carhart1997_four_factor]] — momentum factor zoo'da Cochrane'in en sık andığı
  anomalilerden [s.12]

### Cycle 12 ek (HLZ 2016 ingested)
- [[harvey_liu_zhu_2016_multiple_testing]] — Cochrane #1 (subsumption)
  ve #3 (parsimony) sorularına **statistical procedural cevap**: 316
  factor census + multiple-testing düzeltmesi → BHY-FDR-1% ile ~10-30
  surviving, Bonferroni ile ~9. Cochrane'in "factor zoo" çağrısının
  istatistiksel filter cevabı.

### Cycle 13 ek (HXZ 2020 ingested)
- [[hou_xue_zhang_2020_replicating_anomalies]] — Cochrane #1 + #3
  sorularının **empirik replication cevabı**: 447 anomaly NYSE-VW
  methodology'de %64 insig at 5%; q-factor sonra %10 net sig
  (46/447). HLZ statistical filter + MP behavioral decay + HXZ
  empirical replication **üç bağımsız mekanizma** Cochrane'in factor
  zoo çağrısına aynı conclusion'a varıyor. Wiki epistemik omurgası
  Cycle 11+12+13 boyunca üç bacak üzerine kuruldu.

### Cycle 26 ek (FGX 2020 ingested)
- [[feng_giglio_xiu_2020_factor_zoo]] — **Cochrane #2 (factors
  independent?) + #3 (how many really matter?) direct empirik
  cevap**; 150 factor library + 750 test portfolio Jul 1976-Dec
  2017 frequentist DS LASSO methodology + Fama-MacBeth two-pass;
  recursive screening 1994-2016 **17/150 factor sig (%11)**;
  since-2012 RMW + ROE + IA + QMJ + intermediary investment DS-sig.
  D bloğu epistemik omurga statistical bacağı **2 paper** (HLZ +
  FGX) sertleştirme: Cochrane #1+#2+#3 framing → HLZ 2016 frequentist
  Bonferroni/BHY → FGX 2020 frequentist DS LASSO **3 paper × statistical
  bacak**. SDF loading vs risk premium kritik epistemic point [s.22]:
  factor mean return ≠ pricing contribution.

### Henüz wiki'de olmayan, Cochrane 2011'le ilgili Tier-1 paperlar
- Hou-Xue-Zhang (2015) "Digesting Anomalies" — q-factor model origin paperı (Tier 1 #3)

## Çelişkiler / Tartışmalar

> 📝 Bu paper survey/agenda olduğundan kendisi yeni çelişki yaratmaz; **mevcut
> çelişkileri *organize eder***. HML redundancy (FF93 ↔ FF15) örneği Cochrane'in
> 1. sorusunun doğal örneğidir: "which characteristics are subsumed by others?"
> [[meta/contradictions]] dosyasındaki HML evrimi girişine Cochrane çerçevesi
> referansı eklendi.

## Açık Sorular (bu paperın açtığı / dokunduğu)

Cochrane'in **dört sorusu** wiki'nin Faz 2 "synthesis" hedeflerini doğrudan
şekillendirir. Mevcut [[meta/open_questions]] sorularıyla eşleştirme:

- **Cochrane #1** ("which subsume which") ↔ wiki Q15 (FF5 vs HXZ4 horse race),
  [[meta/contradictions]] HML evrimi
- **Cochrane #2** ("does each anomaly correspond to factor") ↔ wiki Q16 (UMD
  yıllık-rebalans transferi)
- **Cochrane #3** ("how many factors are important") ↔ wiki yeni Q17 (eklendi):
  "Faktör zoo'sundan kaç tanesi gerçekten replicate ediyor?" — Hou-Xue-Zhang 2020
  ile cevap.
- **Cochrane #4** ("why do prices move") — wiki'nin scope'u dışı (felsefi);
  strateji tasarımı bu soruyu cevaplamak zorunda değil.

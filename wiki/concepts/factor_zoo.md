---
type: concept
name: factor_zoo
related_papers: [[cochrane2011_discount_rates]], [[hou_xue_zhang_2015_q_factor]], [[hou_mo_xue_zhang_2020_security_analysis]], [[cooper_gulen_ion2018_asset_growth_factor_models]], [[mclean_pontiff_2016_post_publication_decay]], [[harvey_liu_zhu_2016_multiple_testing]], [[hou_xue_zhang_2020_replicating_anomalies]]
---

> 📝 **Cycle 35 ek**: HXZ 2015 q-factor origin paper [[papers/hou_xue_zhang_2015_q_factor]] Cochrane 2011 #1-#3 sorularına explicit cevap [Section 6 Conclusion]: (#1) Investment + ROE bağımsız bilgi sağlar; investment B/M + net stock issues + accruals + market leverage + long-term reversal + E/P + composite issuance subsume eder; ROE short-term prior returns + earnings surprise + financial distress subsume eder; (#2) Each anomaly variable corresponds to factor formed on same variable; (#3) ~15 anomaly K=4 faktör subsumption (MKT + ME + I/A + ROE). [[concepts/q_factor_model]] cross-link Cochrane #1-#3 anchor.

> 📝 **Cycle 37 ek**: FF 2008 size-partition methodology [[papers/fama_french_2008_dissecting_anomalies]] (Cycle 37 ✓) anomaly dissection methodology evolution; 7-anomaly (size + B/M + profitability + asset growth + accruals + net stock issues + momentum) size-pervasiveness ayrıştırma direct empirik methodology. **Asset growth + profitability anomaly'lerinin big stocks'ta yok/zayıf** finding'i factor zoo decay perspective'inde size-conditional decay channel: anomaly large-cap evrene transferi yokluğu factor mortality bir formu; CMA(big) INSIG + RMW(big) zayıf hedge returns FF15 model parsimony tartışmasının origin'i.

> 📝 **Cycle 38 ek**: Profitability ailesi methodology evolution Cop sertleştirme [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] (Cycle 38 ✓); Profitability factor ailesi 4 measure (GP/A + RMW Ope + QMJ GPOA + Cop) methodology hierarchy continuity factor proliferation/redundancy perspective: Cop standalone Profitability ailesinde en güçlü ([Tablo 2 col 7] horse race wins; [Tablo 5] highest avg return + t-value; [Tablo 8] tangency Sharpe en yüksek katkı); Cochrane #1 'anomalies are different expressions' Profitability zinciri 4-paper × 7-yıl convergent evolution paterni paralel.

> 📝 **Cycle 39 ek**: Stambaugh-Yuan mispricing factor paradigma + clustering methodology [[papers/stambaugh_yuan_2017_mispricing_factors]] (Cycle 39 ✓); 11 anomaly hierarchical clustering (Ahn-Conrad-Dittmar 2009 + Ward 1963) → 2-cluster MGMT/PERF composite mispricing factor; **factor zoo decay perspective + composite mispricing reaggregation**: factor proliferation problem'inin alternatif çözümü single-anomaly factor proliferation yerine composite mispricing factor consolidation; Stambaugh-Yuan 4F (MKT+SMB+UMO1+UMO2) outperforms HXZ4 + FF5 on 73 anomaly larger set parsimony+performance kanıt; Cochrane #3 'how many factors really matter K<N' explicit mispricing-based cevap (K=4); JKP 2023 13 theme cluster methodology evolution paterni paralel.

# Factor Zoo — 300+ Faktör Problemi

## Tanım

**Factor zoo** terimi, akademik finans literatüründe önerilmiş ve istatistiksel
olarak "anlamlı" bulunmuş çoklu (yüzlerce) faktörün durumunu ifade eder.
[[cochrane2011_discount_rates]] [abstract, s.13] bu terimi popülerleştirir:

> "We thought that the cross-section of expected returns came from the CAPM. Now
> we have a zoo of new factors."

Wiki'de şu an kayıtlı olan 6 faktör (MKT-RF, SMB, HML, RMW, CMA, UMD) toplam
zoo'nun küçük, çekirdek bir alt kümesidir. Akademik literatürde 300+ faktör
önerilmiş durumda [Cochrane 2011 atfı; Harvey-Liu-Zhu 2016 sayım].

## Neden problem?

[[cochrane2011_discount_rates]] [s.13] formülasyonuyla 4 soru:

1. **Subsumption:** Hangi karakteristikler **gerçekten bağımsız** information
   sağlıyor? Hangileri başkaları tarafından span ediliyor?
   - Wiki örneği: HML, [[famafrench2015_five_factor]] altında RMW + CMA tarafından
     span ediliyor [Tablo 6, s.19] → [[meta/contradictions]]
2. **Factor structure:** Her yeni anomaly *kendi mimicking faktörüne* mi karşılık
   geliyor, yoksa mevcut faktörlerin betalarıyla mı yakalanıyor?
3. **Parsimony:** N bağımsız beklenen-getiri boyutunu K << N faktörle (yani
   "az sayıda" faktörle) açıklayabilir miyiz?
4. **Why:** Bu faktörler **neden** fiyatlanıyor? (felsefi soru)

## Multiple testing problemi

Faktör zoo'nun istatistiksel temel hatalarından biri: **300+ paper × her biri
"t-stat > 2" reporting → şans eseri tek başına yanlış pozitif kaçınılmaz.**

[[harvey_liu_zhu_2016_multiple_testing]] [Şekil 2-3, s.20-22] paper-temelli
kanıt sağlar:

- **316 factor** census (313 published + 63 selected working papers,
  1967-2014); factor production rate 1980s 1/yıl → 2003-2012 18/yıl
- **Geleneksel `|t| > 1.96` cutoff yetersiz**; multiple-testing düzeltmesi
  ile (M = R, 2012):
  - **Bonferroni `|t| > 3.78`** (FWER 5%)
  - **Holm ~3.6**
  - **BHY `|t| > 3.39`** (FDR 1%) veya `|t| > 2.78` (FDR 5%)
- **M > R hidden tests** düzeltmesiyle (%71 missing factor estimate):
  Bonferroni 4.01, BHY (5%) **3.18** → paperin önerdiği MUTLAK MINIMUM
- **Şekil 3 mark'leri (HLZ 2012 sample sonu):** HML, MOM, DCG, SRV, MRT
  — sig her cutoff'ta; EP, LIQ, CVOL — bazen sig; **SMB, DEF, IVOL, LRV
  — never sig under multiple testing**

**Paperin ana mesajı [s.55]:** "Most claimed research findings in financial
economics are likely false" — finans literatüründe iddia edilen
bulguların büyük çoğunluğu multiple-testing'i geçemiyor.

Detay [[concepts/multiple_testing]] aggregate tablosu wiki'deki ingested
faktörler için.

## Replikasyon krizi

[[cochrane2011_discount_rates]] [s.13] sıraladığı anomaly listesi:
"momentum, accruals, equity issues and other accounting-related sorts, beta
arbitrage, credit risk, bond and equity market-timing strategies, foreign
exchange carry trade, put option writing, and various forms of liquidity
provision."

> 📝 Bu listede hangi anomalies'in **out-of-sample replicate ettiği** wiki'de
> doğrudan kanıtlanmış değil. Hou-Xue-Zhang (2020) "Replicating Anomalies" (Tier 1
> #18) bu listede 452 anomaly test eder; ingest edildiğinde wiki bu boşluğu
> kapatır.

## Replication crisis perspective (Cycle 13 ek)

[[hou_xue_zhang_2020_replicating_anomalies]] factor zoo'nun **empirik
replication** ayağını sağlar:

- **447 anomaly** (57 momentum + 68 value-vs-growth + 38 investment +
  79 profitability + 103 intangibles + 102 trading frictions),
  1967-2014 sample [Tablo 1, s.36+]
- **NYSE breakpoint + value-weighted** methodology (microcap-arınmış)
- **286 anomaly (64%) insig at klasik 5%**; **380 anomaly (85%) insig
  at HLZ-cutoff t > 3.0**
- **Trading frictions/liquidity biggest casualty: 95/102 (93%) insig**
- **Distress anomaly virtually nonexistent** (failure prob., O-Score,
  Z-Score, credit rating insig)
- 161 sig anomaly üzerinde q-factor model 115 alpha'yı insig bırakır →
  **net %10 sig** (46/447, 11 with t > 3)

**Ana mesaj [s.31]:** "Capital markets are more efficient than
previously reported."

[[mclean_pontiff_2016_post_publication_decay]] %65 hayatta +
[[harvey_liu_zhu_2016_multiple_testing]] %15-30 sig + HXZ 2020 %10 net
sig **üç bağımsız mekanizma** factor zoo'nun büyük çoğunluğunu reddediyor.

**Üç-bacak epistemik omurga** [[concepts/post_publication_decay]]
sayfasında detaylı sentez + dört darbe çerçevesi tablosu.

## Statistical filter perspective (Cycle 12 ek)

[[harvey_liu_zhu_2016_multiple_testing]] Cochrane #1 ve #3 sorularına
**statistical procedural cevap** sağlar:

**Cochrane #1 (Subsumption):** 316 factor → multiple-testing-corrected
~10-30 sig (BHY-FDR-1% to Bonferroni). Yani büyük çoğunluk subsumed
veya spurious. SMB never sig + HML/MOM her cutoff'ta sig, factor zoo'nun
**heterojen survival rate**'i (factor sınıfına göre değişen).

**Cochrane #3 (Parsimony):** 316 factor zoo → BHY ile K=10-30 robust;
Bonferroni ile K=5-10. Wiki'nin q5 + momentum + complementer composite
scoring çerçevesi bu parsimony argümanını destekliyor.

[[mclean_pontiff_2016_post_publication_decay]] aggregate %35 decay (%65
hayatta) ile birlikte: factor zoo'nun **gerçek replicable subset'i K=10-30
arası**. Detay [[concepts/multiple_testing]] aggregate tablosu +
[[concepts/post_publication_decay]] çift-bacak epistemik omurga.

## Decay perspective on factor zoo (Cycle 11 ek)

[[mclean_pontiff_2016_post_publication_decay]] factor zoo'nun parsimony
ve subsumption sorularına (Cochrane #1, #3) **prosedürel kanıt** sağlar:
82 anomaly aggregate **post-publication decay ≈%35** (sig 1%); statistical
bias ≈%10 (insig). Bu, factor zoo'nun **çoğunluk anomalileri gerçek**
ama post-pub zayıflıyor sonucuna götürür:

- **Cochrane #1 ("subsumption"):** McLean-Pontiff statistical bias
  rakamı (insig) factor zoo'daki anomaly'lerin **data-mining ile çıkmadığını**
  destekler. Dolayısıyla redundancy spurious-discovery tipi değil,
  daha çok **mekanizma overlap** tipi (örn. CMA = asset growth = accruals
  bileşik aile, [[cooper_gulen_ion2018_asset_growth_factor_models]]).
- **Cochrane #3 ("kaç faktör?"):** Post-pub %65 hayatta = factor zoo'nun
  büyük kısmı **gerçek**. Ama her birinin **decay-adjusted** spread'i daha
  küçük → strateji tasarımında kullanılabilir alt-küme **küçülür**.
  Yani K << N parsimony argümanı güçleniyor: aggregate decay sonrası
  K=5-10 robust factor (q5 + momentum + complementer composite scores)
  yeterli olabilir.
- **Cochrane #2 ("anomaly = factor mı?"):** McLean-Pontiff anomaly
  correlation dynamics [Tablo 9] published anomaly'ler kendi-aralarında
  korele, unpublished olanlar farklı "stil"de korele → anomaly'ler tek
  bir factor değil **publication-aware ortak mispricing source**'dan
  geliyor (Stambaugh-Yuan 2017 hipotezi).

### Sample-end opportunism reddi

[[mclean_pontiff_2016_post_publication_decay]] [Tablo 4]: orijinal
sample'ın son 12 ayında decay coefficient INSIG (-0.091, p=0.678); ilk
12 ay out-of-sample POSITIVE INSIG (+0.338). Eğer factor zoo'nun büyük
kısmı "araştırmacı sample'ı opportunistik kestiği için" şişirilmiş
olsaydı, bu coefficient'ler tam ters işaretli olmalıydı. Yani **factor
zoo'nun büyük kısmı sample-end manipulasyonu eseri DEĞİL** — anomaly'ler
gerçekten in-sample dönemde mevcut, post-pub'da arbitraj/risk-evrimi ile
zayıflıyor.

### Limited arbitrage segmentasyonu

[[mclean_pontiff_2016_post_publication_decay]] [Tablo 8] post-pub decay
büyük cap, likit, dividend-payer, düşük idio risk firmalarda **DAHA
güçlü** → factor zoo'nun **large-cap segmentinde** survival rate düşük.
Wiki amaç evrenleri (S&P 500 + NDX) tam olarak bu segmentte → kullanılabilir
factor zoo alt-kümesi **daha da küçük** (Q29 sensitivity).

> 📝 **Wiki yorumu:** Factor zoo "%65 hayatta" ortalama; large-cap'te
> oranın daha düşük olması beklenir. Strateji tasarımı için pratik
> kural: in-sample headline rakamına aggregate %65 multiplier baseline,
> NDX-spesifik için %50 sensitivity ([[post_publication_decay]] decay-
> adjusted spread tablosu).

## Bu wiki'nin strateji tasarımına spesifik implikasyonu

- **Strateji tasarımı, factor zoo'nun *küçük, replicable* alt kümesine
  dayanmalı.** Bu wiki'nin Tier 1 source list'i bilinçli olarak sınırlı (25
  paper) — factor zoo'nun büyük kısmı Tier 2-3'te kalır.
- **Multiple testing düzeltmesi gerek:** Wiki'de strateji tasarımına dahil edilen
  her faktör için "out-of-sample kanıt + post-publication decay testi + alternatif
  inşa robustness testi" üçlüsü aranmalı (Faz 3 backtest spec'inde).
- **Fundamental + parsimony tercihi:** Wiki Tier 1 listesi öncelikli olarak
  fundamental-data faktörlerini (B/M, ROE, asset growth, accruals) kapsar;
  factor zoo'nun teknik-analiz tarafı (calendar effects, microstructure, vs.)
  bilinçli olarak dışlanır.

## "Fundamental scores survive q5?" cevabı

[[hou_mo_xue_zhang_2020_security_analysis]] q5 model lens'inde 6 fundamental
scoring stratejisini test ederek factor zoo / subsumption tartışmasına
spesifik kanıt ekler:

| Strateji | q5 alpha durumu | Kanıt |
|---|---|---|
| Frankel-Lee V/P | tam span, alphalar insig | [Tablo 1, s.17-18] |
| Piotroski F-Score | mikro hariç span; mikro = 0.33% sig | [Tablo 2, s.18-19] |
| Greenblatt Magic Formula | tam span, alpha negatif/sıfır | [Tablo 3, s.20] |
| Asness QMJ | q-factor reject, **q5 captures** | [Tablo 4, s.21] |
| Bartram-Grinblatt agnostic | q5 ile büyük ölçüde span | [Tablo 5] |
| Penman-Zhu fundamental | q5 ile büyük ölçüde span | [Tablo 6] |
| Ball-GLN retained earnings/M | q5 ile büyük ölçüde span | [Tablo 7] |
| Buffett's Berkshire | **q5 alpha 0.77% (t=2.69) hala anlamlı** | [Tablo 8] |
| Mohanram G-Score | **TEST EDİLMEDİ (kapsam dışı)** | — |

**Cochrane #1 sorusunun ("which subsume which?") spesifik cevabı:**
Geleneksel security analysis stratejileri **q5 model 5 faktörü tarafından
büyük ölçüde span ediliyor** (mikrocap residual hariç). Yani factor zoo'nun
**fundamental scoring kolonunda subsumption güçlü** — bu skorların incremental
information'u büyük cap segmentinde sınırlı.

**İstisna: Buffett's alpha** q5 ile span edilmiyor — aktif discretionary
seçimin ayrı bir alpha kaynağı olabilir (sistematik replikasyona uygun değil).

## Investment cluster — Cochrane #2 sorusunun cevabı

[[cooper_gulen_ion2018_asset_growth_factor_models]] [s.3-4] kanıtı:
- **CMA** (FF15 investment factor)
- **HXZ q-factor I/A** factor
- Sloan **NOA** (Net Operating Assets — Hirshleifer-Hou-Teoh-Zhang 2004)
- **Capital expenditure anomalies** (Titman-Wei-Xie 2004)
- Ve **35 anomaly spread portfolio**'nun büyük kısmı

→ hepsi **aynı asset growth measure** üzerinden span ediliyor (HXZ q-factor
asset-growth-based 5/35 unexplained vs CAPX/PPE alternatif 15-24/35).

**Cochrane #2 sorusu** ("does each new anomaly correspond to a new factor?")
investment cluster için **olumsuz** cevap: çok sayıda anomaly aynı factor
variant'ları → factor zoo'nun bir kısmı **redundant** ya da **aynı root
signal'in** versiyonları. Asset growth factor zoo'nun en güçlü tek-faktör
unification noktalarından biri.

> ⚠️ Önceki sentez "CMA = investment proxy" yorumu CGS-Ion 2018 ile
> challenged. CMA "asset growth measure proxy" demek doğru, ama "investment
> proxy" demek yanıltıcı. Asset growth measure CAPX/PPE/intangibles ile
> reproduce edilemiyor. Detay: [[asset_growth_anomaly]].

## İlgili paperlar (ingested)

- [[cochrane2011_discount_rates]] — kavramı popülerleştiren paper
- [[famafrench2015_five_factor]] — HML'in RMW+CMA tarafından subsume edilmesi —
  Cochrane #1 sorusunun bir cevabı
- [[piotroski2000_f_score]] — komposit skor olarak factor zoo'ya alternatif:
  9 sinyali tek skora indirger; "fundamental scoring" yaklaşımı zoo'nun
  yönetilebilir alt kümesi
- [[hou_mo_xue_zhang_2020_security_analysis]] — fundamental scoring stratejilerinin
  q5 ile span'ini sistematik test eden paper (Cochrane #1'in spesifik cevabı)
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — investment cluster
  unification kanıtı (Cochrane #2 cevabı)
- [[mclean_pontiff_2016_post_publication_decay]] — 82 anomaly aggregate
  decay %35; factor zoo'nun "ne kadarı hayatta" sorusuna prosedürel cevap;
  sample-end opportunism reddi + limited arbitrage segmentasyonu
- [[harvey_liu_zhu_2016_multiple_testing]] — 316 factor census + 3 düzeltme
  prosedürü (Bonferroni / Holm / BHY); recommended cutoff `|t| > 3.0`
  (BHY 1%, M=R) ile factor zoo'nun **statistical survival** subset'i
  K=10-30; MP behavioral decay ile çift-bacak epistemik omurga
- [[hou_xue_zhang_2020_replicating_anomalies]] — 447 anomaly NYSE-VW
  methodology'de %64 insig at 5%; q-factor sonra %10 net sig; üç-bacak
  epistemik omurganın replication ayağı; "capital markets more efficient
  than previously reported"
- [[bailey_lopezdeprado_2014_deflated_sharpe]] — DSR Sharpe-spesifik
  backtest overfitting filter; HLZ + MP + HXZ ile complementary; 5.
  darbe açılmadı (Cycle 14 disiplin meta-not testi); Faz 3 backtest
  spec methodology infrastructure
- [[novy_marx_2013_gross_profitability]] — **Cycle 23**; **Profitability
  factor ailesi** factor proliferation perspektifi: GP/A (Novy-Marx)
  + RMW Ope (FF15) + QMJ GPOA (Asness) + Cop (HMXZ) — 4 measure
  factor zoo'da paralel olarak test edilmiş; redundancy var (numerator/
  denominator methodology farkı); Cop superior (cash-aware evrim).
  Wiki'de paralel **iki quality zinciri** dokümante (Sloan = mispricing
  + Novy-Marx = profitability) factor zoo'nun "many anomalies are
  different expressions of underlying mechanisms" Cochrane #1
  argümanının somut örneği — Novy-Marx [Section 4] industry-adjusted
  GP/A + value + momentum 3-factor 11 anomaly açıklıyor (default
  risk, ROE, asset turnover, organizational capital, vb.).
- [[feng_giglio_xiu_2020_factor_zoo]] — **Cycle 26**; **Cochrane
  #2/#3 sorularına direct empirik cevap** (which factors independent?
  + how many really matter?); 150 factor library + 750 test portfolio
  Jul 1976-Dec 2017 frequentist DS LASSO methodology + Fama-MacBeth
  two-pass; **recursive screening 1994-2016: 17/150 factor sig (%11)**;
  since-2012 factors RMW + ROE + IA + QMJ + intermediary investment
  DS-sig (diğerleri redundant); **HLZ frequentist Bonferroni + FGX
  frequentist DS LASSO iki paralel methodology** (data-snooping bias
  vs omitted variable bias iki ortogonal statistical concern,
  complementary); **SDF loading (pricing contribution) ≠ risk premium
  (factor mean return)** kritik epistemic point [s.22] — about half
  of factors INSIG risk premium FGX sample'da (HXZ 2017 paterni
  teyit). Wiki için: factor zoo decay ~%85-90 üç paper × üç methodology
  çift+üç teyit (HXZ 46/447 ≈ %10 + FGX 17/150 ≈ %11 + MP %35
  aggregate decay).
- [[jensen_kelly_pedersen_2023_replication_crisis]] — **Cycle 27**;
  **DRAMATIC FARKLI sonuç** (HXZ %35 + FGX %11 + MP %35 conservative-
  side vs JKP %84.9 Bayesian US + %84.0 Global anti-conservative-
  side); **13 theme cluster taxonomy + tangency portfolio analysis**:
  Accruals* + Debt Issuance* + Investment* + Leverage* + Low risk
  + Momentum + Profit Growth + Profitability + Quality + Seasonality
  + Size* + Skewness* + Value; 10/13 themes >75% replicate; 10/13
  themes tangency portfolio sig+; 3 displaced (profitability,
  investment, size) joint modeling redundancy; out-of-sample combined
  88.5% positive. **Cochrane #2/#3 Bayesian framework alternatif**
  (FGX frequentist DS LASSO paralel methodology aile). **3.
  contradictions entry** ([[meta/contradictions]] §3): HXZ ↔ JKP
  dramatic empirik fark scope-dependent + methodology disagreement
  (capped VW NYSE 80th percentile +8.5pp + 1-month +4.0pp + longer
  sample +4.3pp + Bayesian framework +28pp). Wiki için: factor zoo
  decay/replication **iki kutup** — conservative side korunur baseline
  + anti-conservative side upper bound sensitivity reference.
- [[eisfeldt_papanikolaou_2013_organization_capital]] — **Cycle 25**;
  **F bloğu intangibles factor ailesi** factor proliferation
  perspektifi (4-katmanlı methodology hierarchy): Knowledge (R&D Lev-
  Sougiannis) + **Organization (SG&A Eisfeldt-Papanikolaou factor
  portfolio)** + Total q (Peters-Taylor) + Application (Lev-Srivastava
  adjusted HML). Methodology infrastructure (1+3+4) + factor portfolio
  anchor (2) ayrımı dokümante. Novy-Marx Section 4 organizational
  capital based strategy claim direct factor portfolio Carhart 4F α=
  3.9% sig 1% ile **partial reject** (organization capital independent
  premium kalıyor) — factor zoo Cochrane #1 paterni nüanslı (her
  anomaly underlying mechanism'a indirgenmiyor).

## İlgili paperlar (henüz ingest edilmedi)

- Harvey-Liu-Zhu (2016) "...and the Cross-Section of Expected Returns" — multiple
  testing düzeltmesi (Tier 1 #17)
- Hou-Xue-Zhang (2020) "Replicating Anomalies" — 452 anomaly replikasyonu (Tier 1 #18)
- Feng-Giglio-Xiu (2020) "Taming the Factor Zoo" — yeni faktör test prosedürü
  (Tier 1 #21)
- Jensen-Kelly-Pedersen (2023) "Is There a Replication Crisis in Finance?"
  (Tier 2 #44)
- Green-Hand-Zhang (2017) "The Characteristics that Provide Independent Information"
  (Tier 1 #24)

## İlgili kavramlar

- [[discount_rates]] — factor zoo'nun her bir faktörü bir discount rate spread'i
  iddia eder
- [[factor_model]] — factor zoo'nun parametrik gösterimi
- [[fundamental_scoring]] — factor zoo'ya alternatif komposit skorlama paradigması
- [[post_publication_decay]] — factor zoo decay'in 3 mekanizması + decay-
  adjusted spread tablosu (wiki'deki ingested factors için)
- [[multiple_testing]] — factor zoo statistical filter mekanizması; HLZ
  316 factor census + 3 düzeltme prosedürü + aggregate sig durumu tablosu
- [[anomaly_replication]] — factor zoo empirik replication mekanizması;
  HXZ 447 anomaly NYSE-VW methodology + replication crisis literatür hattı
- [[backtest_overfitting]] — factor zoo strategy-level Sharpe inflation
  filter; DSR formülü + p-hacking + memory effects under overfitting

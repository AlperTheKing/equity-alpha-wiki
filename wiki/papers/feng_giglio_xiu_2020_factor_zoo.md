---
type: paper
authors: [Feng, Guanhao, Giglio, Stefano, Xiu, Dacheng]
year: 2020
title: "Taming the Factor Zoo: A Test of New Factors"
venue: "Journal of Finance"
url: https://www.nber.org/papers/w25481
local_path: raw/papers/feng_giglio_xiu_2020_factor_zoo.pdf
ingested: 2026-05-01
tags: [factor_zoo, multiple_testing, redundancy_testing, ml_asset_pricing, statistical_methodology, d_block_statistical_pillar]
status: ingested
cycle: 26
cycle_35_note: "q-factor model formal origin paper [[papers/hou_xue_zhang_2015_q_factor]] Cycle 35 ✓; FGX 2020 [Tablo 1] ROE (HXZ profitability) + IA (HXZ investment) DS-sig 150-factor library cross-test; HXZ 2015 since-2012 factors RMW + ROE + IA + QMJ + intermediary investment DS-sig FGX validation; D bloğu epistemik omurga statistical bacağı 3 paper × üç paralel methodology aile (HLZ + FGX + JKP) HXZ 2015 origin frequentist factor regression + GRS test 4. paralel methodology layer"
cycle_38_note: "Q55 Cycle 26 fully-answered Profitability ailesi DS-sig 150-factor library + Cycle 38 Ball-GLN Cop origin paper anchor [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓ sertleştirme; Profitability zinciri 4-paper × 7-yıl Novy-Marx GP/A → FF15 RMW Ope → QMJ GPOA → Ball-GLN Cop methodology hierarchy continuity; FGX framework Cop family DS-sig validation"
cycle_39_note: "Stambaugh-Yuan UMO1+UMO2 mispricing factors FGX 150-factor library cross-test [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓ placeholder→live link; Cycle 26 explicit cite formal cross-link; Q55+Q7 fully-answered Cycle 26 Stambaugh-Yuan mispricing factor methodology validation paterni paralel; composite mispricing scoring 4. zincir Piotroski → Mohanram → Stambaugh-Yuan → JKP literature continuity"
block: D_complement
---

# Feng, Giglio, Xiu (2020) — Taming the Factor Zoo: A Test of New Factors

> 📝 **Faz 2 Cycle 26 ingest** — D bloğu kompleman (statistical bacağı
> sertleştirme); Cycle 24 yol haritası revize'sinde önceliği yükseltildi
> (28 → 26); **Q55 acil cevap** (Profitability factor ailesi horse race);
> v0_draft Profitability seçim doğrulama anchor; FGX 2020 **frequentist
> DS LASSO methodology** (Bayesian DEĞİL — plan revize: HLZ frequentist
> Bonferroni → FGX frequentist DS LASSO **iki paralel frequentist
> yaklaşım**, methodology evrim).

## TL;DR

FGX 2020 **150 factor library × 750 test portfolio (Jul 1976 - Dec 2017)**
üzerinde **Double-Selection LASSO (DS) methodology** uygulayarak yeni
factor'lerin existing factor zoo üzerine **marginal pricing
contribution**'ını test ediyor. Belloni vd. 2014b "double-selection"
econometric methodology + Fama-MacBeth two-pass cross-section
regression bileşimi. **Ana bulgu** [Tablo 1, factors since 2012]:
**RMW (FF profitability) + ROE (HXZ profitability) + IA (HXZ investment)
+ QMJ (Asness) + intermediary investment factor sig**; diğer son-5-yıl
factor'ler (2012-2016) **redundant**. **Recursive exercise** [Tablo 2,
since 1994]: 150 factor içinde **sadece 17'si** retroactive olarak
useful; **majority redundant** veya useless. **Methodology critical
distinction** [s.22]: SDF loading (pricing contribution) ≠ risk
premium (factor mean return); HLZ multiple-testing'in tamamlayıcısı
**omitted variable bias** focus (data-snooping concern değil).
**Wiki için Q55 fully-answered** (Profitability ailesi RMW + ROE
DS-sig; QMJ DS-sig; **GP/A FGX 150 library içinde explicit yok**
ama sample 1976-2017 Novy-Marx 2013 kapsamında hem yapısal hem
mevcut factor'lerle paralel test edilmiş).

## Tek Cümle Tezi

**Factor zoo'nun büyük çoğunluğu omitted variable bias-corrected
DS LASSO altında redundant**; **profitability + investment** factor
ailesi pricing contribution sig kalır (HLZ multiple-testing
literature'ün tamamlayıcı statistical methodology layer'ı: HLZ
frequentist FDR control vs FGX frequentist omitted variable bias
correction).

## Sample ve Methodology

- **Universe**: NYSE+AMEX+NASDAQ Compustat (CRSP share code 10/11);
  **ex-financials** + **ex-negative book equity**
- **Sample**: **July 1976 - December 2017** (41.5 yıl, 498 ay)
- **Frequency**: Monthly factor returns
- **Factor library size**: **150 factors** [Tablo 4]
  - 15 published factors (Ken French data library + AQR data library
    + Pa̧stor-Stambaugh liquidity + HXZ q-factors + He-Kelly-Manela
    intermediary)
  - 135 long-short VW portfolios constructed following FF1993
    methodology (firm characteristics from Hou et al. 2017 + Green
    et al. 2016)
- **Test portfolio**: **750 portfolios**
  - 36 standard FF: 6 × (3×2 size×characteristic) for BM, OP, Inv,
    ST-rev, Mom, LT-rev
  - 714 additional 3×2 bivariate-sorted from factor zoo (119 × 6)
- **Construction**: NYSE breakpoint + **value-weighted** (microcap-
  arınmış); top 30% − bottom 30% long-short; June rebalance + 12-month
  holding period (annual); FF1993 paterni
- **Methodology**: **Double-Selection LASSO (DS)** + Fama-MacBeth
  two-pass cross-section regression
  - **Step 1 (1st LASSO)**: cross-section regression LASSO factor
    selection (which factors price the cross-section?)
  - **Step 2 (2nd LASSO)**: orthogonalization — selecting factors
    correlated with **gt** (the candidate factor) to avoid omitted
    variable bias
  - **Step 3 (DS estimator)**: cross-section regression with union of
    Step 1 + Step 2 selected factors as controls; estimate SDF loading
    of gt
- **Tuning**: Cross-validation (10-fold disjoint random subsamples)
  for LASSO penalty selection
- **Frequentist statistical inference** (NOT Bayesian); SDF loading
  test of `H0: γg = 0`

## Methodology continuity (D bloğu statistical bacağı genişlemesi)

[[concepts/multiple_testing]] D bloğu statistical bacağı **2 paper**
(HLZ + FGX) sertleştirme:

| Paper | Yıl | Approach | Concern | Tools |
|-------|-----|----------|---------|-------|
| [[papers/harvey_liu_zhu_2016_multiple_testing]] | 2016 | Frequentist multiple testing | **Data-snooping bias** | Bonferroni / Holm / BHY (FDR control) |
| **[[papers/feng_giglio_xiu_2020_factor_zoo]]** | 2020 | Frequentist ML (DS LASSO) | **Omitted variable bias** | Double-Selection LASSO + Fama-MacBeth two-pass |

**Wiki için yapısal kazanım**: D bloğu statistical bacağı **2 paper
× iki paralel frequentist yaklaşım** dokümante. HLZ "yanlış
pozitiflere karşı stringent cutoff" (cutoff `|t| > 3.0` BHY 1%);
FGX "omitted controls düzeltmesi sonrası gerçek SDF loading" (DS
LASSO model selection bias-corrected). İki paper paralel **complementary
methodology** (paper [s.23-24] explicit kabul: "complementary issues
to be overcome on the path to disciplining the zoo of factors").

## Ortaya Konan Sinyal/Faktör

FGX yeni factor önermiyor — **methodology paper**. Yeni concept veya
factor entity açılmadı (concept proliferation kontrol; [[concepts/multiple_testing]]
+ [[concepts/factor_zoo]] zenginleşme).

## Empirik Sonuçlar (sayılarla)

### 1. Last 5-year factors (since 2012) DS test [Tablo 1]

DS-sig factor'ler (SDF loading t-stat):
- **RMW** (FF profitability) — sig
- **ROE** (HXZ profitability) — sig (ikinci profitability factor)
- **IA** (HXZ investment) — sig
- **QMJ** (Asness Quality Minus Junk) — sig
- **Intermediary investment** (He-Kelly-Manela 2016) — sig

DS-INSIG factor'ler:
- CMA (FF investment — IA superior; Cycle 10 CGS-Ion + CMA paterni
  paralel)
- BAB (Frazzini-Pedersen Betting Against Beta) — kullanım için sig
  ama DS lens'inde redundant
- Convertible debt + nontradable other factors — INSIG

**Methodology comparison**:
- DS column 1: 5 factor sig (yukarıdaki)
- SS (single-selection LASSO) column 2: sadece convertible debt sig (negatif sign) — biased
- FF3 controls column 3: **9/15 factor sig** (overestimate; arbitrary control choice)
- OLS all controls column 4: noisy, less significant (no selection)
- Risk premia column 5: **half** of factors INSIG (sample-spesifik;
  HXZ 2017 paterni teyit)

### 2. Recursive exercise (since 1994) [Tablo 2]

150 factor zoo year-by-year DS test:
- **Sadece 17 factor** retroactive olarak useful (sig DS lens'inde)
- **Majority redundant veya useless** — factor proliferation
  literature'in büyük çoğunluğu DS bias-corrected'da elenmiş
- 1994'ten 2016'ya yıllık screening: yeni factor sig olarak retain
  edilen sayı yıl başına ~1

### 3. SDF loading vs risk premium kritik ayrımı [s.22]

> "About half of these factors do not have a significant **risk
> premium**, while they typically did in the original publications."

Wiki için yorum: HXZ 2017 ([[papers/hou_xue_zhang_2020_replicating_anomalies]]
2020 published version) "Replicating Anomalies" paterni teyit — risk
premium (factor mean return) sample-spesifik; **SDF loading (pricing
contribution) bağımsız test**. FGX'in temel epistemic point'i:
risk premium ≠ pricing contribution.

### 4. Heston-Sadka seasonality factor örneği [s.4]

Wiki için pedagogical anchor (paper'ın factor evaluation framework
çekirdek prensibi):
- FF3 alpha t=2.06 sig (apparent useful factor)
- Carhart 4F alpha t=−0.87 INSIG (momentum ile 0.63 korelasyonlu
  → spurious)

**Implication**: HLZ + FGX bağlamında Faz 3 strategy spec'i için
factor inclusion test'i **multi-benchmark cross-validation**
zorunlu (single-benchmark "FF3 alpha sig" criterion yetersiz).

### 5. Robustness checks [s.27-28]

- Alternative dimension reduction (Elastic Net + PCA) — DS sonuç
  korunur
- Alternative portfolio construction (202 portfolio Giglio-Xiu 2016
  + 1825 portfolio 5×5 alternative) — robust
- Tuning parameter robustness (cross-validation neighborhood) —
  robust

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | ⚠️ N/A → **epistemic prerequisite**; FGX methodology paper (factor inclusion test framework), decile-spread veya portfolio selection değil; cross-section regression two-pass + DS LASSO model selection. **Top-N strategy spec için ön koşul** (factor inclusion list filter epistemic anchor) | N/A doğrudan ama dolaylı epistemic prerequisite |
| **Annual rebalance** | ⚠️ partial fit: FGX **monthly factor returns** (sample 1976-2017) + **annual June rebalance** factor construction (FF1993 paterni; 12-month holding period explicit [s.16]); sample SDF loading test methodology rebalance frekansından bağımsız ama factor input data monthly | ⚠️ partial; methodology rebalance-agnostic ama input data monthly |
| **Large-cap evrene transfer** | ⚠️ partial fit + ⭐ **NYSE-breakpoint + VW microcap-arınmış paterni explicit** [s.16 paper "Microcaps...accounting for only 3% of the total market equity. Equal-weighted returns overweight microcaps"]; HXZ 2020 + Israel-Moskowitz paterni paralel; **explicit large-cap-only sub-sample test direct yok** ama methodology choice large-cap-relevant | ⚠️ partial + ⭐ NYSE-VW methodology preference |
| **NDX intangibles / growth firms** | ⚠️ N/A doğrudan; FGX 150 factor library **traditional factor zoo** (FF + HXZ + AQR + 135 characteristic-based long-short); **F bloğu intangibles factor'leri dahil mi paperdan teyit edilemedi** (Lev-Sougiannis Knowledge + Eisfeldt-Papanikolaou OC + Peters-Taylor q^tot — 150 library içinde explicit listed değil ama 135 characteristic-based portföy içinde Sloan + Mohanram + Beneish benzeri intangibles-related characteristics yer alabilir; tam liste paperdan kontrol edilmedi); methodology intangibles-aware extension yapılmamış | N/A doğrudan + Q64 yeni (F bloğu intangibles factor'lerin FGX framework'üne entegrasyonu eksik) |

**Strateji tasarımına net implikasyon:**

1. **Q55 fully-answered (Profitability ailesi DS lens'inde)**:
   - **RMW Ope (FF)** DS-sig ⭐ — Cycle 23'te [[factors/RMW]]'de "HXZ
     q-factor altında alpha 0.04% t=0.42 INSIG" (1/4) ama FGX **150
     factor library + DS LASSO bias-corrected** lens'inde sig kalır;
     **methodology farkı** (HXZ 2020 q-factor model lens vs FGX DS
     LASSO 150-factor library lens)
   - **ROE (HXZ)** DS-sig ⭐ — q-factor model'in profitability bacağı
     bağımsız sig; HMXZ q5 paterni teyit
   - **QMJ (Asness 4-dimension)** DS-sig ⭐ — Q2 fully-answered ANCHOR
     (Cycle 19) + Q55 partial; QMJ 4-dimension composite DS-sig ama
     **dimension-spesifik decompose paperde yok** (Q49 partial-stronger
     direct kanıt)
   - **GP/A (Novy-Marx 2013)** [[factors/Gross_Profitability]]: FGX
     150 library içinde **explicit listed teyit edilemedi** (Tablo 4
     ham liste paperdan kontrol edilmedi); Cycle 23'te [[factors/Gross_Profitability]]
     "Reported Performance" tablosu Novy-Marx orijinal sample 1963-2010
     direct kanıt; FGX validation **dolaylı** (Profitability ailesi
     genel sig)
   - **Cop (HMXZ Tablo 5)** [[factors/Accruals]] cross-link: HMXZ
     q-factor lens'inde 4/4 hayatta kalan; FGX direct test
     edilmedi (FGX HXZ q-factor model'in 4 factor'ünü kullanır,
     Cop FGX library'de explicit yok)

2. **v0_draft Profitability seçimi DOĞRULANDI** (Cycle 26 sonrası):
   - S&P 500 §1.B "GP × V/P CORE" + NDX §2.B "QMJ continuous + GP/A
     standalone" Profitability factor seçim **FGX validation güçlü**
     (RMW + ROE + QMJ DS-sig)
   - **Revize gerekmez**; ek caveat: FGX DS-sig vs HXZ q-factor INSIG
     methodology farkı dokümante (RMW Ope için iki bulgu paralel
     dokümante)

3. **D bloğu statistical bacağı sertleştirildi**:
   - HLZ 2016 frequentist Bonferroni/BHY + FGX 2020 frequentist DS
     LASSO **iki paralel methodology**
   - [[concepts/multiple_testing]] sertleştirme: data-snooping bias
     (HLZ) + omitted variable bias (FGX) iki ortogonal statistical
     concern
   - Faz 3 backtest spec için **çift-methodology factor selection**
     ([[methodology/backtest_spec]] §3.3 + §4.3 sertleştirme)

4. **SDF loading vs risk premium ayrımı kritik epistemic point**:
   - Wiki için yeni alt-bölüm aday ([[concepts/factor_zoo]] sertleştirme):
     factor'lerin pricing contribution'ı ≠ mean return; HXZ 2017 +
     FGX 2020 paralel bulgular
   - Faz 3 strategy spec'inde portfolio backtest reporting'inde
     factor mean return + SDF loading **iki ayrı metric**

5. **Recursive screening 1994-2016: 17/150 factor sig** ⭐:
   - HXZ 2020 NYSE-VW replication ~46/447 net sig + FGX DS LASSO
     17/150 ≈ %11 → **factor zoo decay ~%85-90** çift teyit (HXZ
     methodology + FGX DS LASSO complementary)
   - [[concepts/post_publication_decay]] dört darbe çerçevesi sentez
     tablosu sertleştirme (Replication-robust + MT-corrected paralel)

## Limitler ve Caveats

- **Sample sonu Dec 2017** — post-2017 (FAANG era 2018-2024 + COVID +
  AI) out-of-sample; modern data Chen-Zimmermann 2022 + JKP 2023 ek
  ingest gerekli (Cycle 27)
- **150 factor library traditional**: F bloğu intangibles factor'leri
  (Lev-Sougiannis Knowledge + Eisfeldt-Papanikolaou OC + Peters-Taylor
  q^tot) **explicit listed teyit edilemedi**; Q64 yeni (Cycle 26)
- **Composite scores DAHIL DEĞİL**: F-Score, G-Score, M-Score, F&V/P,
  G&V/P composite scoring strategies FGX 150 library'sinde individual
  factor olarak listed değil; HLZ + HXZ paterni paralel
- **DS LASSO tuning parameters**: cross-validation tuning robustness
  test edilmiş ama universal optimum yok; Faz 3 implementation
  finite-sample sensitivity Q62 yeni
- **NDX-spesifik kalibrasyon eksik**: FGX universal sample (NYSE+
  AMEX+NASDAQ); NDX top 100 non-financial sub-universe için DS LASSO
  redundancy test direct yok; Q62 paralel
- **Frequentist methodology**: Bayesian shrinkage (Avramov-Cheng-
  Metzker 2023, Tier 2 #43) alternative methodology eksik; iki
  paralel ML yaklaşım wiki'de dokümante değil
- **HLZ vs FGX scope-dependent ortak alan**: iki methodology paralel
  ama empirik sonuç comparison paperde explicit yok; HLZ 316 factor
  vs FGX 150 factor sample farkı

## İlgili Sayfalar

### Bu paperın update ettiği mevcut sayfalar

- [[concepts/multiple_testing]] — **D bloğu statistical bacağı
  sertleştirme** (Cycle 12 HLZ origin + Cycle 26 FGX DS LASSO
  extension); 2 paper × iki paralel frequentist yaklaşım dokümante
- [[concepts/factor_zoo]] — Cochrane #2 (factors independent?) + #3
  (how many really matter?) FGX direct empirik cevap; recursive
  screening 17/150 sertleştirme
- [[papers/harvey_liu_zhu_2016_multiple_testing]] — HLZ-FGX methodology
  continuity (data-snooping bias vs omitted variable bias paralel);
  D bloğu statistical bacağı 2 paper sertleştirme
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] — replication
  (HXZ NYSE-VW empirik methodology robustness) + redundancy (FGX DS
  LASSO model selection bias) **iki ayrı epistemik düzlem**;
  factor zoo decay ~%85-90 çift teyit
- [[papers/hou_mo_xue_zhang_2020_security_analysis]] — HMXZ q5 model
  factor independence FGX cross-test; q-factor model + DS LASSO
  redundancy paralel
- [[papers/cochrane2011_discount_rates]] — Cochrane #2/#3 framing
  → HLZ statistical → FGX DS LASSO direct empirik cevap zinciri
  (3 paper × statistical bacak)
- [[papers/famafrench2015_five_factor]] — FF5 RMW (profitability)
  + CMA (investment) DS-sig kanıtı (Tablo 1); FF5 factor independence
  FGX cross-test
- [[papers/asness_frazzini_pedersen_2019_qmj]] — QMJ DS-sig (Q2
  fully-answered ANCHOR + Q55 partial); QMJ 4-dimension composite
  DS-sig ama dimension-spesifik decompose eksik (Q49 partial-stronger)
- [[papers/novy_marx_2013_gross_profitability]] — Profitability
  ailesi DS validation **dolaylı** (RMW + ROE DS-sig kanıtla); GP/A
  150 library içinde explicit yok ama Profitability ailesi genel sig
- [[papers/eisfeldt_papanikolaou_2013_organization_capital]] —
  intermediary investment factor sig + organization capital factor
  150 library içinde explicit teyit edilemedi (Cycle 25 OC entity
  Q64 paralel)
- [[papers/mclean_pontiff_2016_post_publication_decay]] — recursive
  17/150 sig ≈ %11 + HXZ 2020 ~46/447 ≈ %10 + MP %35 decay aggregate
  → factor zoo decay üç ayrı methodology çift+üç teyit
- [[papers/bailey_lopezdeprado_2014_deflated_sharpe]] — DSR Sharpe-
  spesifik backtest overfitting + FGX DS LASSO factor-spesifik model
  selection bias **iki ayrı methodology layer** Faz 3 backtest spec
- [[factors/RMW]] — RMW DS-sig (FGX Tablo 1) + HXZ q-factor INSIG
  (HXZ 2020 Tablo 6) **methodology farkı dokümante**; iki paralel
  bulgu paralel rapor edilir
- [[factors/Gross_Profitability]] — Profitability ailesi DS validation
  dolaylı; v0_draft GP × V/P seçim doğrulama
- [[factors/QMJ]] — QMJ DS-sig (FGX Tablo 1); Q49 partial-stronger
  (dimension-spesifik decompose eksik)
- [[factors/Accruals]] — Cop 4/4 hayatta kalan; FGX library'de explicit
  yok
- [[factors/Organization_Capital]] — FGX 150 library içinde explicit
  teyit edilemedi (Q64 paralel)
- [[methodology/backtest_spec]] §3.3 çift düzeltme prensibi (Q37)
  sertleştirme: factor-level HLZ frequentist FDR + factor-level FGX
  DS LASSO + strategy-level DSR üç paralel methodology layer; §4.3
  darbe (3) MT-corrected genişlemesi
- [[strategies/v0_draft]] §1.B + §2.B Profitability factor seçimi
  FGX validation **DOĞRULANDI**; revize gerekmez (caveat: FGX DS
  vs HXZ q-factor methodology farkı dokümante)

## Çelişkiler/Tartışmalar

### HLZ-FGX vs HXZ 2020 — kullanıcı talimatı kararı

Cycle 13/19/22 paterni uygulanır: empirik çelişen bulgular varsa
gerçek contradictions entry, methodology farkı/iki epistemik düzlem
ise scope-dependent paper sayfasında not.

**Empirik karşılaştırma**:
- **HXZ 2020 NYSE-VW replication methodology**: 447 anomaly → ~46
  net sig q-factor sonrası (~%10) → "factor zoo'nun büyük
  çoğunluğu false discovery"
- **FGX 2020 DS LASSO methodology**: 150 factor recursive 17 sig
  (%11) → "factor zoo'nun büyük çoğunluğu redundant"
- **MP 2016 aggregate %35 decay** → "behavioral decay büyük çoğunluk"

**Üç paper bulguları aynı yönde çift+üç teyit** (factor zoo decay
~%10 net sig hayatta); methodology farklı (HXZ replication; FGX
redundancy DS LASSO; MP behavioral). **Çelişki YOK** — iki ayrı
epistemik düzlem (replication vs redundancy vs behavioral) **çift+
üç teyit complementary methodology**.

**Sonuç**: [[meta/contradictions]] yeni entry açılmadı (3. entry
yok). Cycle 26 paper sayfasında scope-dependent not + Cycle 13
HXZ paterni paralel.

### HLZ vs FGX scope-dependent (paper [s.23-24] explicit)

Paper [s.23-24] HLZ vs FGX **complementary** olarak konumlandırıyor:

> "Although the overarching theme is to tame the factor zoo, the
> perspectives are rather different. The aforementioned papers
> [HLZ, MP] emphasize the bias of data-snooping or raise the concern
> of multiple testing, whereas our focus is on omitted controls.
> All these problems could contribute to the proliferation of factors."

Wiki yorumu: HLZ frequentist Bonferroni/BHY (data-snooping/MT
concern) + FGX frequentist DS LASSO (omitted variable bias concern)
**iki ortogonal statistical concern**; complementary methodology,
çelişki değil. [[concepts/multiple_testing]] sertleştirme.

### RMW Ope DS-sig (FGX Tablo 1) vs HXZ q-factor INSIG (HXZ 2020 Tablo 6)

Iki paralel bulgu, methodology farkı:
- **HXZ 2020**: RMW Ope **q-factor model lens'inde** alpha 0.04%
  t=0.42 INSIG (1/4 dört darbe)
- **FGX 2020**: RMW Ope **DS LASSO 150-factor library lens'inde**
  sig SDF loading

**Çelişki değil** — iki paralel methodology farklı epistemic question:
- HXZ: "RMW'nin q-factor model dışında bağımsız bilgi var mı?"
  (q5'in 4 component'i alternatif → INSIG)
- FGX: "RMW'nin 150-factor library'deki diğer factor'lerden bağımsız
  pricing contribution'ı var mı?" (DS LASSO model selection +
  omitted variable correction → sig)

Wiki için: **iki bulgu paralel rapor edilir** (RMW factor sayfasında
+ Q55 fully-answered cevabında); Faz 3 spec'inde **methodology
disagreement transparent**, RMW Ope için q-factor exposure proxy
+ DS LASSO standalone signal **iki kullanım modu** option.

## Cycle 29 ek (data_sources.md açıldı)

[[methodology/data_sources]] modern data infrastructure pointer
dokümantasyonu: Chen-Zimmermann 2022 Open Asset Pricing Database
(pure replication ~100%) + JKP 2023 GlobalFactor code repository +
WRDS open-source access **üç paralel data kaynağı**. FGX 150 factor
library 1976-2017 sample post-2017 (FAANG/AI 2018-2024 + COVID)
out-of-sample (Q63 fully-answered Cycle 27 + Q66 yeni); modern data
infrastructure Faz 3 custom DS LASSO redundancy test implementation
direct kullanılabilir (WRDS + Compustat + CRSP raw feed).

## Cycle 27 ek (JKP 2023 ingest)

[[jensen_kelly_pedersen_2023_replication_crisis]] D bloğu statistical
bacağı **3. paper** (2 paper × üç paralel methodology aile sertleştirme):

| Paper | Methodology aile | Concern | Headline |
|-------|------------------|---------|----------|
| [[harvey_liu_zhu_2016_multiple_testing]] | **Frequentist** Bonferroni/BHY | Data-snooping bias | 316 factor; cutoff `\|t\| > 3.0` BHY 1% |
| [[feng_giglio_xiu_2020_factor_zoo]] | **Frequentist** DS LASSO | Omitted variable bias | 17/150 sig (%11) recursive |
| **[[jensen_kelly_pedersen_2023_replication_crisis]]** | **Bayesian Empirical Bayes** | Hierarchical dependence + theme cluster | **%84.9 US / %84.0 Global** ⭐ |

**Paralel methodology Cycle 26 + 27 sertleştirme**: Faz 3 backtest
spec için **üç-methodology factor selection** (HLZ + FGX + JKP).
JKP Bayesian framework FGX frequentist DS LASSO ile **complementary**
(çelişki değil, paralel methodology aile); empirik bulgular farklı
çünkü methodology aile farklı (frequentist conservative + Bayesian
anti-conservative). **Plan revize Cycle 26**: FGX Bayesian DEĞİL
frequentist DS LASSO; JKP Cycle 27 **gerçek Bayesian** (Empirical
Bayes hierarchical) — D bloğu statistical bacağı 3 paper × **üç
ayrı methodology aile** (frequentist FDR + frequentist ML + Bayesian
hierarchical).

## Açık Sorular (Open Questions)

- **Q55** (GP/A vs RMW Ope vs QMJ GPOA vs Cop horse race) → **fully-
  answered** (Cycle 26): FGX Tablo 1 RMW + ROE + QMJ DS-sig; GP/A
  150 library explicit listed teyit edilemedi ama Profitability
  ailesi genel sig validation; Cop FGX library'de explicit yok ama
  HXZ q-factor lens'inde 4/4 hayatta kalan paralel kanıt. **v0_draft
  Profitability seçimi doğrulandı**.

- **Q7** (FGX hangi factor'ler "incremental information" sağlıyor)
  → **fully-answered** (Cycle 26): FGX Tablo 1 + Tablo 2 anchor;
  150 factor recursive 17 sig (%11); since 2012 RMW + ROE + IA +
  QMJ + intermediary investment sig; majority redundant.

- **Q15** (FF5 vs HXZ q-factor cross-subsumption) → **partial-
  stronger**: FGX DS LASSO 150-factor library lens'inde RMW + CMA
  + IA + ROE bireysel sig; FF5 vs q-factor explicit horse race
  paperde dolaylı (her iki model'in factor'leri DS-sig); HXZ 2015
  q-factor origin paper ek ingest tam cevap için.

- **Q24** (q5 vs FF5 horse race) → **partial-stronger**: FGX cross-
  subsumption test her iki model'in factor'lerini bağımsız sig
  buluyor (RMW + CMA + ROE + IA); explicit FF5-q5 horse race
  paperde yok.

- **Q34** (HXZ 447 anomaly q-factor cross-subsumption) → **partial-
  stronger**: FGX 150-factor library + DS LASSO 17 sig; HXZ 447
  + q-factor 46 net sig; iki methodology paralel decay rate ~%10;
  cross-subsumption direct horse race paperde yok ama complementary
  empirik kanıt.

- **Q37** (DSR-1 trial-count + HLZ MT-corrected çift düzeltme prensibi)
  → **partial-stronger**: FGX DS LASSO factor-level model selection
  bias correction; HLZ multiple-testing + DSR Sharpe-spesifik
  + FGX omitted variable bias **üç paralel methodology layer**
  çift düzeltme genişler ([[methodology/backtest_spec]] §3.3
  sertleştirme).

- **Yeni Q'lar (Cycle 26)**:
  - **Q62 yeni**: NDX-spesifik DS LASSO redundancy testing
    kalibrasyon (FGX universal sample; NDX top 100 non-financial
    sub-universe için DS LASSO sample size sınırı + factor selection
    farkı); cross-validation tuning parameter NDX 100-stock
    portfolio için sufficient mi?
  - **Q63 yeni**: Post-2017 modern data ile FGX replikasyonu
    (sample sonu Dec 2017; FAANG era 2018-2024 + COVID + AI out-of-
    sample); JKP 2023 (Cycle 27 ingest planı) modern güncelleme
    sağlayabilir
  - **Q64 yeni**: F bloğu intangibles factor'lerin FGX framework'üne
    entegrasyonu (Lev-Sougiannis Knowledge + Eisfeldt-Papanikolaou
    OC + Peters-Taylor q^tot); FGX 150 library içinde explicit
    listed teyit edilemedi (Tablo 4 ham liste paperdan tek-tek
    kontrol edilmedi); F bloğu 4-katmanlı methodology DS LASSO
    redundancy test'i Faz 3 implementation
  - **Q65 yeni**: Composite scores (F-Score, G-Score, M-Score, F&V/P,
    G&V/P, QARP) FGX framework'üne entegrasyonu; FGX 150 library
    individual factor census, composite scoring strategies dahil
    değil (HLZ + HXZ paterni paralel); composite scores DS LASSO
    redundancy test wiki Faz 3 methodology gap

## Strateji tasarımına spesifik katkı

1. **D bloğu epistemik omurga statistical bacağı sertleştirildi**
   ([[concepts/multiple_testing]] + [[concepts/factor_zoo]]):
   - HLZ 2016 frequentist Bonferroni/BHY (data-snooping bias)
   - **FGX 2020 frequentist DS LASSO (omitted variable bias)** ⭐
     paralel methodology
   - Iki ortogonal statistical concern; complementary
   - Faz 3 backtest spec için **çift-methodology factor selection**
     baseline

2. **Q55 fully-answered Profitability ailesi DS lens'inde** ⭐:
   - RMW Ope + ROE + QMJ **DS-sig** (FGX Tablo 1)
   - GP/A direct test eksik ama Profitability ailesi genel sig
     dolaylı validation
   - Cop FGX library'de explicit yok ama HXZ q-factor 4/4 paralel
   - **v0_draft Profitability seçimi DOĞRULANDI**; revize gerekmez

3. **SDF loading vs risk premium epistemic point** [s.22]:
   - Wiki için yeni layer factor evaluation:
     - Risk premium (factor mean return) — sample-spesifik
     - SDF loading (pricing contribution) — bağımsız test
   - Faz 3 strategy spec backtest reporting'inde **iki ayrı metric**
     ayrı rapor edilir (FGX paterni)

4. **Recursive screening 17/150 = %11 sig** + HXZ 2020 ~46/447
   = %10 + MP %35 decay + **JKP 2023 conservative-side framework
   alternative** → factor zoo decay **dört paper × dört methodology
   aile** çift+üç+dört teyit (Cycle 27 sertleştirme; conservative-side
   HXZ + FGX + MP %85-90 vs anti-conservative-side JKP %85 Bayesian
   replication [[meta/contradictions]] §3 dramatic methodology
   disagreement); [[concepts/post_publication_decay]] dört darbe
   sentez tablosu sertleştirme.

5. **Heston-Sadka seasonality pedagogical anchor** [s.4]:
   - FF3 alpha t=2.06 sig vs Carhart 4F alpha t=−0.87 INSIG
     (momentum 0.63 correlated)
   - Single-benchmark "FF3 alpha sig" criterion **yetersiz**
   - Faz 3 strategy spec için **multi-benchmark cross-validation**
     zorunlu

6. **Methodology farkları transparent dokümantasyon**:
   - RMW Ope: HXZ q-factor INSIG (1/4) + FGX DS-sig — iki paralel
     bulgu, methodology farkı, çelişki değil
   - QMJ: HMXZ q5 captures (Cycle 8) + FGX DS-sig (Cycle 26) —
     paralel methodology lens
   - Faz 3 spec: factor exposure proxy + standalone DS-sig signal
     **iki kullanım modu** option

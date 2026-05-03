---
type: paper
authors: [Fama, Eugene F., French, Kenneth R.]
year: 2008
title: "Dissecting Anomalies"
venue: "Journal of Finance 63(4), 1653-1678 (NBER WP 13003 / SSRN 911960)"
url: https://www.nber.org/papers/w13003
local_path: raw/papers/fama_french_2008_dissecting_anomalies.pdf
ingested: 2026-05-02
phase: faz_3_cycle_37
tags: [size_partition_methodology, anomaly_dissection, large_cap_reality, cma_origin_test, q14_anchor, e_block, ff_methodology_continuity]
status: ingested
---

# Fama-French (2008) — Dissecting Anomalies

> 📝 **Cycle 37 ingest (Faz 3 ikinci seçici ingest; Tier 1 paywall→
> preprint yüksek priori).** [[meta/handoff_faz3]] §3 paywall paperlar
> Faz 3 seçici ingest aday; Cycle 37 FF 2008 direct ingest E bloğu
> (large-cap reality) Israel-Moskowitz Cycle 22 yumuşak kapsam → FF
> 2008 sertleştirme; Q14 (RMW/CMA large-cap-only direct test eksikliği)
> kanonik anchor. HXZ 2015 [s.7] cross-cite "investment effect strong
> in microcaps and small stocks but largely absent in big stocks"
> origin claim direct test paper'ı.

## TL;DR (4 cümle)

FF 2008, size-partition methodology (microcaps <20th NYSE percentile + small 20-50th + big >50th) ile 7 anomaly (size + B/M + profitability + asset growth + accruals + net stock issues + momentum) dissection yaparak hangi anomaly'lerin tüm size gruplarında pervasive vs hangilerinin sadece microcap/small'da var olduğunu ayrıştırır. **Net stock issues + accruals + momentum** üç anomaly tüm size gruplarında pervasive ([Tablo II + IV]); **asset growth + profitability** anomaly'leri large-cap'te zayıf veya yok — asset growth big-stock VW spread -0.02% (t=-0.10) ve regression slope big -0.17 (t=-0.86) **INSIG**; profitability sadece small grupta sig hedge returns. Microcaps NYSE-Amex-Nasdaq universe'ün ~60% stocks ama sadece ~3% market cap (cross-section dispersion of anomaly variables largest in microcaps), bu yüzden EW all-stocks tests microcap-dominated artifact'ler üretir. **Q14 fully-answered ANCHOR**: CMA(big) FF15 [s.13] insig paterni FF 2008 [Tablo II + IV] direct origin; asset growth anomaly large-cap'te yok, FF15 CMA factor primum'unun büyük kısmı küçük cap'lerden gelir.

## Tek Cümle Tezi

> Anomaly returns'lerin pervasiveness'ı size partition (micro/small/big) bazında farklılaşır; **net stock issues + accruals + momentum** üç anomaly tüm size gruplarında pervasive iken **asset growth + profitability** anomaly'leri big stocks'ta yok veya zayıf, yani EW all-stocks tests microcap-dominated artifact'ler üretebilir.

## Ortaya Konan Sinyal/Faktör

- FF 2008 yeni factor önermiyor; **size-partition methodology** (3-paper × 22+ yıl FF ailesi continuity hattı: FF1993 → FF 2008 → FF15)
- Linki: yeni factor entity AÇILMADI (methodology paper); concept zenginleşmesi: [[concepts/anomaly_replication]] + [[concepts/factor_zoo]] genişletme

## Empirik Sonuçlar (sayılarla)

### Sample [Section I, s.4]

| Item | Spec |
|------|------|
| Period | July 1963 - December 2005 (42.5 yıl) monthly |
| Universe | NYSE + Amex + (after 1972) Nasdaq |
| Size partition | Microcaps <20th NYSE percentile; Small 20-50th; Big >50th |
| Microcap statistics | ~60% of stocks but only ~3% of total market cap |
| End-2005 size breakpoints | $610M (micro/small) + $2.3B (small/big) |
| Big stock dominance | >90% of total market cap |

### Anomaly Pervasiveness Headline (3 size groups)

[Tablo II + IV özet]:

| Anomaly | Pattern | Pervasive? |
|---------|---------|-----------|
| Net stock issues | Slopes -1.49 to -1.94 all sig (micro/small/big differ <1.15σ) | ✅ pervasive |
| Accruals | Positive accruals slopes all neg t=-1.49 to -2.24 (full sample sig -2.72σ) | ✅ pervasive |
| Momentum | Slopes 0.41 micro (t=2.51) / 0.82 small (t=4.65) / 0.78 big (t=3.92); spreads differ ama all sig | ✅ pervasive |
| **Asset growth** | Slopes **-0.83 micro (t=-6.82) / -0.57 small (t=-3.10) / -0.17 big (t=-0.86)**; VW spread **big -0.02% (t=-0.10)** | ❌ **NOT pervasive — INSIG in big** |
| **Profitability** | Hedge returns only small >2σ; positive profitability slopes vary | ⚠️ weakest |

### Q14 Anchor — Asset Growth (CMA Origin) Size-Conditional [Tablo II + IV]

**Hedge return sorts** [Tablo II]:
- VW micro: -0.57%/month, t = -4.42
- VW small: -0.31%/month, t = -2.43
- **VW big: -0.02%/month, t = -0.10 INSIG**
- EW big: still <1.16σ from zero

**Regression slopes** [Tablo IV]:
- Micro: -0.83 (t = -6.82)
- Small: -0.57 (t = -3.10)
- **Big: -0.17 (t = -0.86) INSIG**
- Big slope -2.97σ from micro slope (significant size-difference)

> ⚠️ **FF15 [s.13] CMA size-conditional direct origin**: paper [Tablo II + IV + Section II.B] explicit "asset growth anomaly is not pervasive... regression for big stocks does not identify a reliable relation between average returns and asset growth" → FF15'in CMA(small) sig vs CMA(big) insig bulgu FF 2008 origin. **Q14 fully-answered ANCHOR**.

### Profitability Size-Conditional [Tablo II + IV]

- Hedge returns sorts: only **small group** EW + VW abnormal hedge returns >2σ from zero
- Regression slope positive profitability: small Pos Y/B 2.36 (t=4.04 büyük); big Pos Y/B 0.94 (t=1.81 weakest)
- **Among profitable firms** positive relation tüm size groups
- **No evidence** that unprofitable firms have unusually low returns
- Q14 RMW partial-stronger: profitability anomaly large-cap'te zayıf ama positive profitability evrene transferi pozitif relation gösterir (RMW/QMJ paralel motivation)

### B/M Size-Conditional [Tablo IV]

- Micro 0.23 (t=3.19); Small 0.30 (t=3.41); **Big 0.17 (t=1.79)** weakest
- FF06b [s.15]: "weaker relation between average returns and B/M for big stocks is special to the post-1962 period and to U.S. stocks"
- HML size-conditional cross-evidence Israel-Moskowitz 2013 paterni paralel ([[papers/israel_moskowitz_2013_shorting_size_time]] [Tablo 4] HML 86-yıl size-conditional Q5 5-1 α=3.70% t=1.90 INSIG)

### Microcap Influence Statistics [Section I + Tablo I]

- Microcaps ~60% of all sample stocks but only ~3% of market cap
- Cross-section standard deviations of anomaly variables LARGEST in microcaps
- EW all-stocks tests dominated by microcap-tilted artifact'ler
- Implication: **NYSE-VW + microcap-arınmış convention** (HXZ 2015/2020 + JKP 2023 capped VW paterni paralel) FF 2008 origin'inden methodology continuity

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Methodology paper; size-partition sort (micro/small/big breakpoints) + Fama-MacBeth cross-section regression Pos/Neg accruals + dummy variables; decile-spread anomaly dissection ama factor portfolio formal tanım YOK | ⚠️ partial (methodology + indirect sort evidence) |
| **Annual rebalance** | Annual June rebalance default (FF1993 paterni); momentum monthly update exception ([s.14] "We update most of the explanatory variables once a year. The exception to this rule is the momentum variable, which we update monthly"); annual frequency uyumlu | ✅ doğrudan |
| **Large-cap evrene transfer** | **Paper'ın MERKEZ KONUSU**: size-partition methodology micro/small/big; big stocks >90% market cap explicit; "from a practical perspective, if extreme returns associated with anomaly variable are special to microcaps, they are probably not realizable because of the high costs of trading such stocks"; **Q14 fully-answered ANCHOR** large-cap-only direct test | ✅ ⭐ ⭐ KRITIK direct fit |
| **NDX intangibles / growth firms** | Compustat traditional accounting (asset growth = ΔAT/AT-lagged; B/M = book/market traditional); intangibles-aware genişletme YOK; F bloğu 4-katmanlı methodology paralel değil | ❌ uyumsuz traditional accounting (Q23 + Q73 paralel) |

**Strateji tasarımına net implikasyon**:

FF 2008, [[strategies/sp500_v1]] + [[strategies/nasdaq100_v1]] **size-partition methodology** + **NYSE-VW microcap-arınmış convention** Faz 3 backtest implementation için **canonical origin paper**: (1) sp500_v1 §1.1 S&P 500 ≈ Israel-Moskowitz size Q4-Q5 + Fortune 500 birebir empirik anchor methodology (FF 2008 big stocks subset); (2) nasdaq100_v1 §1.1 NDX top 100 non-financial mega-cap concentration ≈ FF 2008 big-stocks üst yarısı (size partition uppermost); (3) **CMA(big) INSIG large-cap implication**: sp500_v1 §2.1 Path D Investment* theme CMA exposure proxy + I/A factor (HXZ 2015) **direct test çift teyit FF 2008 + Israel-Moskowitz + HXZ 2015 üçlü teyit**; (4) RMW(big) zayıf hedge returns ama positive profitability relation tüm size groups → sp500_v1 + nasdaq100_v1 §2.1 Path B Profitability theme G&V/P + GP/A + QMJ Profitability composite tercih (RMW Ope reject + QMJ composite kullan motivation FF 2008 evidence ile sertleştirme); (5) [[strategies/known_weaknesses]] §2.1 Q14 fully-answered ANCHOR güncel.

## Limitler ve Caveats

- **Sample 1963-2005** post-2005 19 yıl out-of-sample (FAANG era 2008-2024); JKP 2023 Bayesian framework partial 2014-2020 modern coverage; Cycle 22 Israel-Moskowitz 1926-2011 + Cycle 35 HXZ 2015 1972-2011 farklı sample windows
- **Methodology paper, factor portfolio YOK**: FF 2008 size-partition methodology continuity (FF1993 → FF 2008 → FF15) origin; factor inşası FF15'te formal (CMA + RMW)
- **Microcap influence focus**: paper microcap-driven artifact'leri ayrıştırma odaklı; large-cap-only ayrı RMW/CMA factor inşası direct empirik test eksik (Faz 3 implementation custom)
- **B/M big-stock weakness post-1962 US-only** [s.15 FF06b cross-cite]: pre-1962 + international robustness test eksik; wiki amaç evreni S&P 500 + NDX post-1962 + US compatible
- **Profitability ölçüsü**: paper Y/B (earnings/book) traditional; Novy-Marx 2013 GP/A + Asness QMJ Profitability + HXZ 2015 ROE methodology farkı (Profitability zinciri evolution)
- **Traditional accounting**: B/M + asset growth Compustat AT traditional; intangibles-aware genişletme YOK; F bloğu 4-katmanlı NDX strategy ortogonal methodology
- **3 size group breakpoints fixed**: 20th + 50th NYSE percentile; alternative breakpoints sensitivity test eksik
- **Methodology evolution**: FF 2008'in size-conditional finding'i FF15 [s.13] CMA + RMW factor inşasına direct etki; ama FF15 model Cochrane #3 sorularına explicit cevap değil (HXZ 2015 + 2020 + JKP 2023 q-factor + Bayesian framework çatallanma)

## İlgili Sayfalar

### FF Ailesi Methodology Continuity (3-paper × 22+ yıl)
- [[papers/famafrench1993_three_factor]] (FF93; FF3 origin; SMB+HML factor formal tanım)
- **[[papers/fama_french_2008_dissecting_anomalies]]** (FF 2008 BU PAPER; size-partition methodology + 7-anomaly dissection)
- [[papers/famafrench2015_five_factor]] (FF15; CMA+RMW factor formal inşa; FF 2008 size-conditional finding [s.13] direct origin)

### E Bloğu (Large-cap Reality) Sertleştirme
- [[papers/israel_moskowitz_2013_shorting_size_time]] (Cycle 22; E bloğu yumuşak kapsam HML 86-yıl size-conditional + UMD size-invariant + long-only sub-portfolio); FF 2008 + Israel-Moskowitz cross-evidence sertleştirme
- Q14 fully-answered ANCHOR: FF 2008 [Tablo II + IV] direct origin

### q-Factor Model Cross-link
- [[papers/hou_xue_zhang_2015_q_factor]] (Cycle 35; HXZ 2015 [s.7] FF 2008 cross-cite "investment effect strong in microcaps and small stocks but largely absent in big stocks" → q-factor size-controlled motivation; r_I/A factor literatür hattı kökü)
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] (Cycle 13; NYSE-VW + microcap-arınmış convention FF 2008 origin paterni paralel)
- [[concepts/q_factor_model]] (HXZ ailesi NYSE-VW + microcap-arınmış literature continuity)

### Cooper-Gulen-Schill 2008 Asset Growth (Paralel Paper)
- [[papers/cooper_gulen_ion2018_asset_growth_factor_models]] (Cycle 10; CGS 2008 asset growth origin; FF 2008 ile aynı yıl paralel paper; FF 2008 [Tablo II + IV] CGS 2008 paterni paralel direct test)

### Factor Entities
- [[factors/CMA]] — FF15 CMA factor; FF 2008 origin size-conditional asset growth; CMA(big) INSIG ANCHOR
- [[factors/RMW]] — FF15 RMW factor; FF 2008 profitability size-conditional zayıf hedge returns
- [[factors/HML]] — FF93 HML factor; FF 2008 [Tablo IV] B/M big-stock zayıf 0.17 (t=1.79); Israel-Moskowitz çift teyit
- [[factors/I_A]] — HXZ 2015 q-factor I/A; literatür hattı kökü FF 2008 (HXZ 2015 [s.7] cite)
- [[factors/Asset_Growth]] — CGS asset growth factor; FF 2008 size-conditional context
- [[factors/UMD]] — Carhart momentum; FF 2008 momentum size-pervasive direct teyit
- [[factors/Accruals]] — Sloan accruals; FF 2008 positive accruals size-pervasive

### Concepts
- [[concepts/factor_zoo]] — FF 2008 anomaly dissection methodology evolution
- [[concepts/anomaly_replication]] — FF 2008 size-conditional methodology origin (HXZ NYSE-VW + JKP capped VW paterni paralel)
- [[concepts/winner_loser_identification]] — B bloğu core kavramı size-partition

### Strategy Specs
- [[strategies/sp500_v1]] §1.1 size methodology + §2.1 Path D Investment* theme + Path B Profitability theme + §6 madde 5 Q14 fully-answered güncel
- [[strategies/nasdaq100_v1]] §1.1 NDX mega-cap concentration FF 2008 big-stocks paralel
- [[strategies/known_weaknesses]] §2.1 sp500-spesifik weakness Q14 update
- [[methodology/backtest_spec]] §1.3 universe methodology FF 2008 size-conditional anchor

## Çelişkiler/Tartışmalar

- **FF 2008 vs Israel-Moskowitz 2013 size-conditional finding**: Çelişki YOK çift teyit (HML size-conditional Q5 INSIG + UMD size-invariant; FF 2008 [s.15-16] big-stocks B/M zayıf 0.17 (t=1.79) + momentum tüm size gruplarında pervasive paralel).
- **FF 2008 vs HXZ 2015 q-factor**: Çelişki YOK literature continuity (HXZ 2015 [s.7] FF 2008 cross-cite "investment effect strong in microcaps... largely absent in big stocks" → q-factor size-controlled motivation; FF 2008 origin → HXZ 2015 q-theoretical implementation).
- **FF 2008 vs FF15 CMA + RMW**: Çelişki YOK methodology evolution (FF 2008 size-conditional finding → FF15 [s.13] explicit acknowledgment "CMA(big) t-stat 1.03-2.00; large kısmı küçük cap'lerden geliyor"); FF15 CMA factor inşası FF 2008'i çürütmek değil, factor mimicking portfolio implementation.
- **FF 2008 vs CGS 2008**: Çelişki YOK paralel papers (aynı yıl; CGS 2008 asset growth origin paper univariate decile + FF 2008 asset growth size-partition methodology test); literature evolution complementary methodology.
- **FF 2008 profitability vs Asness QMJ 2019**: Çelişki YOK scope-dependent (FF 2008 traditional Y/B profitability + only small-grup hedge returns sig; QMJ 2019 [Tablo A4] large-cap-only 4-factor alpha 66 bps/ay sig; profitability ölçüsü farklı + composite vs single — Profitability zinciri 4-paper × 7 yıl methodology evolution).

## Açık Sorular (Open Questions)

- **Q14** (CMA/RMW large-cap-only direct test) — **fully-answered ANCHOR** (FF 2008 [Tablo II + IV] direct empirik origin; CMA(big) INSIG; RMW small-only sig hedge returns; FF15 [s.13] CMA(big) t-stat 1.03-2.00 insig direct kaynak); Cycle 22 Israel-Moskowitz HML-spesifik partial-stronger → Cycle 37 FF 2008 RMW + CMA direct anchor sertleştirme; **üçlü teyit FF 2008 + Israel-Moskowitz 2013 + HXZ 2015 [s.7]**
- **Q4** (CGS-Ion large-cap) — partial-stronger (FF 2008 cross-evidence asset growth size-conditional + CGS 2008 paralel paper)
- **Q15** (FF5 vs HXZ q-factor horse race) — fully-answered (Cycle 35 HXZ 2015 anchor) + Cycle 37 FF 2008 size-conditional context: FF5 CMA + RMW zayıflığının root'u FF 2008 size-conditional finding'inde
- **Q23** (NDX intangibles q-factor span) — N/A (FF 2008 traditional accounting)
- **Q76 yeni**: FF 2008 sample 1963-2005 post-2005 19 yıl out-of-sample modern replikasyon (JKP 2023 partial 2014-2020 6 yıl + post-2020 hala out-of-sample); FAANG era size-partition robustness; Faz 3 custom backtest implementation
- **Q77 yeni**: Large-cap-only ayrı RMW/CMA factor inşası direct empirik test (FF 2008 size-partition methodology origin ama large-cap-only factor portfolio formal tanım YOK; Faz 3 implementation custom Hou-style 2×3 size-controlled vs FF15 standart 2×3 sort comparison)
- **Q78 yeni**: FF 2008 momentum size-invariance vs HXZ 2015 [Apx E] annual-sorted momentum INSIG çelişki yok scope-dependent (FF 2008 monthly momentum size-pervasive vs HXZ 2015 annual-sorted momentum hedge alpha INSIG; iki ayrı epistemic question — pervasiveness vs annual-sort viability)

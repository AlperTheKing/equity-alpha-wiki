---
type: factor
name: CMA
category: investment
direction: long_high  # uzun "conservative" (low investment), kısa "aggressive" (high investment)
data_lag_required: "Haziran t-end için fiscal year-end t-1 ve t-2 total assets (≥6-aylık reporting gap)"
rebalance_frequency: annual
universe_tested: ["NYSE/AMEX/NASDAQ ex-financials, 1963-07/2013-12"]
---

> 📝 **Cycle 35 ek**: HXZ 2015 q-factor model r_I/A investment factor [[factors/I_A]] yeni entity açıldı (Cycle 35); methodology farkı dokümante (FF15 CMA = 2×3 sort decile spread; HXZ I/A = 2×3×3 size×A/A×ROE triple sort q-theoretical implementation). I/A ↔ CMA korelasyon HXZ 2015'te direct rapor edilmedi; investment-q theoretical foundation (Cochrane 1991) HXZ 2015 origin paper [[papers/hou_xue_zhang_2015_q_factor]] anchor. JKP 2023 Investment* theme **displaced** (Profitability + Investment + Size 3 displaced joint modeling redundancy [[meta/contradictions]] §3 paralel).

> 📝 **Cycle 37 ek**: CMA size-conditional **direct origin** [[papers/fama_french_2008_dissecting_anomalies]] (Cycle 37 ✓); FF 2008 [Tablo II + IV] asset growth size-partition methodology test → FF15 [s.13] CMA(small) sig vs CMA(big) insig direct origin: VW spread micro -0.57% t=-4.42 + small -0.31% t=-2.43 + **big -0.02% t=-0.10 INSIG**; regression slopes micro -0.83 t=-6.82 + small -0.57 t=-3.10 + **big -0.17 t=-0.86 INSIG**; big slope -2.97σ from micro slope sig size-difference. **Q14 fully-answered ANCHOR**: CMA large-cap evrene transferi zayıf direct empirik kanıt; üçlü teyit FF 2008 + Israel-Moskowitz 2013 (Cycle 22; HML size-conditional çift teyit) + HXZ 2015 [s.7] (Cycle 35; "investment effect strong in microcaps... largely absent in big stocks" cross-cite). sp500_v1 + nasdaq100_v1 §2.1 Path D Investment* theme CMA exposure proxy + I/A factor direct test çift teyit motivation.

> 📝 **Cycle 39 ek**: Stambaugh-Yuan 11 anomaly Cluster 1 (MGMT) içinde investment-to-assets dahil [[factors/MGMT]] Cycle 39 ✓ ([[papers/stambaugh_yuan_2017_mispricing_factors]]); composite mispricing P1 6-anomaly avg ranking I/A bileşeni; CMA tek-anomaly factor exposure proxy + UMO1 composite mispricing factor complementary methodology aile.

# CMA — Conservative Minus Aggressive (Investment Faktörü)

## Tanım (Fama-French 2015 inşası)

`CMA` = (S/C + B/C) / 2 − (S/A + B/A) / 2 (2×3 sort versiyonu)

- `S` ve `B`: NYSE median ME breakpoint
- `C` (Conservative — düşük yatırım), `N`, `A` (Aggressive — yüksek yatırım):
  NYSE 30/70 Inv percentile breakpoint'leri
- 6 portföy value-weighted aylık [[famafrench2015_five_factor]] s.10

**Inv (Investment) ölçüsü** [s.8]:

`Inv = (total assets fiscal year t-1 − total assets fiscal year t-2) / total assets t-1`

> 📝 Yazarlar valuation denkleminden book equity büyümesini teorik proxy olarak
> önerir, ama total asset growth'un benzer / biraz daha geniş spread ürettiğini
> not ederek total asset growth kullanır [s.8]. **İki versiyonun paralel
> hesaplanması iyi pratik olabilir.**

## Origin

- İlk paper (mimicking-portföy formuyla): [[famafrench2015_five_factor]] (Fama-French 2015)
- **Empirical origin:** Cooper-Gulen-Schill (2008) "Asset Growth and the
  Cross-Section of Stock Returns" — **original paper paywall, wiki'de yok**
- **Modern revisit (de facto wiki referansı):** [[cooper_gulen_ion2018_asset_growth_factor_models]]
  — CMA factor performansının CGS asset growth ölçüsüne kritik bağlı olduğu
  empirik kanıt (Section 3-4, s.3-4)
- Investment anomalisinin diğer akademik kaynakları: Titman-Wei-Xie (2004) —
  Tier 2 #38, henüz ingest edilmedi
- Yazarlar [[famafrench2015_five_factor]] s.4-5'te valuation equation (Eq. 3) ile CMA'yı
  teorik olarak motive eder.

## Reported Performance Across Studies

| Paper | Dönem | Evren | Mean (ay) | t-stat | Notlar |
|---|---|---|---|---|---|
| [[famafrench2015_five_factor]] (2x3) | 1963-07 / 2013-12 | NYSE/AMEX/NASDAQ ex-fin | 0.33% | 4.07 | [Tablo 4 Panel A, s.37] |
| [[famafrench2015_five_factor]] (2x2) | aynı | aynı | 0.22% | 3.72 | [Tablo 4 Panel A, s.37] |
| [[famafrench2015_five_factor]] (2x2x2x2) | aynı | aynı | 0.14% | 2.71 | [Tablo 4 Panel A, s.37] |

> 📝 **2×2×2×2 (joint kontrol) inşasında CMA primum 0.33%'dan 0.14%'e düşer**.
> Bu, joint kontrol gerçekten "saf" investment premium'unu izole edince çoğunun
> value/profitability ile çakıştığını gösterir [Tablo 4 Panel A, s.37; s.13].

| [[cooper_gulen_ion2018_asset_growth_factor_models]] | 1968-2016 | NYSE+AMEX+NASDAQ ex-fin | factor model alpha analizi (asset growth measure'a sensitivity) | sig | [Tablo (paperdan teyit), s.3-4]; HXZ + CMA-base = 5/35 unexplained, alternatif investment measures ile 15-24/35 unexplained |

_(Cooper-Gulen-Schill 2008 original paper paywall sebebiyle wiki'de yok;
modern revisit referansla kullanılıyor — bkz. [[meta/data_gaps]].)_

## Faktör Ailesi İçindeki Yeri

- **Korelasyonlar (FF5 2x3, [Tablo 4 Panel C, s.38]):**
  - CMA ↔ MKT-RF : −0.39
  - CMA ↔ SMB : −0.11
  - CMA ↔ HML : **0.70** (yüksek — value firmaları az yatırım yapar)
  - CMA ↔ RMW : −0.11
- **HML ↔ CMA = 0.70 [Tablo 4 Panel C, s.38]:** Bu, HML redundancy bulgusunun
  mekanik kaynaklarından biri. HML'in zaman serisi varyansının önemli kısmı CMA
  üzerinden taşınıyor [[famafrench2015_five_factor]] s.19.

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

Wiki'de henüz yok. [[famafrench2015_five_factor]] CMA primum'un büyük kısmının küçük cap
hisselere ait olduğunu raporluyor — CMA(small) t-stat 4.64-5.49, CMA(big) t-stat
1.03-2.00 [s.13]. **Bu kritik bir nüans: large-cap evrende CMA primum'u
istatistiksel olarak çok daha zayıf.** S&P 500 ve Nasdaq 100 stratejisi için CMA
exposure'u daha sınırlı bir alpha kaynağı olabilir → [[meta/data_gaps]] notu
eklendi, [[meta/open_questions]] yeni Q14 ile bağlantılı.

## Decay / Post-Publication Performance + Multiple Testing Status

[[mclean_pontiff_2016_post_publication_decay]] aggregate %35 post-pub
decay multiplier CMA'ya uygulanır.

[[harvey_liu_zhu_2016_multiple_testing]] çerçevesinde:
- **2x3 inşa t=4.07 (1963-2013):** sig her cutoff'ta (Bonferroni / Holm /
  BHY hepsi sig)
- **Joint 2x2x2x2 t=2.71:** BHY borderline; Bonferroni **insig**

CMA standalone (2x3) multiple-testing düzeyinde sağlam; joint kontrolde
asset growth measure'ın diğer factorlerle (özellikle accruals ve RMW)
**partial overlap** sebebiyle sig durumu zayıflıyor — Cochrane #1
subsumption örneği. Detay: [[concepts/multiple_testing]] aggregate
tablosu.

**Cycle 13 ek (HXZ 2020 ingested):**
[[hou_xue_zhang_2020_replicating_anomalies]] [s.24] **CMA klasik 0.34%
(t=3.63) sig + q-factor alpha 0.01% (t=0.32) INSIG** — q-factor I/A
factor CMA'yı tam span ediyor. CGS-Ion 2018 ile uyumlu (q-factor I/A
factor CGS asset growth measure'ı kullanıyor; CMA çoğunlukla aynı
underlying signal'e dayanıyor). Wiki için: **CMA factor exposure proxy**
olarak kullanılabilir, "saf alpha" değil. Faz 3 risk-adjustment'ta
q-factor I/A factor CMA yerini alır. Üç darbe (in-sample + post-pub
+ MT) sig; **dördüncü darbede q-factor span** = investment factor
exposure proxy. Detay [[concepts/anomaly_replication]] aggregate
tablosu; [[concepts/post_publication_decay]] dört darbe çerçevesi.

**Cycle 15 ek (Lev-Sougiannis 1996 ingested) — intangibles-adjusted
methodology (R&D-only):**
[[lev_sougiannis_1996_rd_capitalization]] R&D capitalization adjusted
book equity ile **CMA aggregate asset growth measure'ı alternatif
inşa**:
- Geleneksel: `(TA_t - TA_{t-1}) / TA_{t-1}`
- R&D-adjusted: `((TA + RDC)_t - (TA + RDC)_{t-1}) / (TA + RDC)_{t-1}`
- Lev-Sougiannis sample 22.2% average book equity understatement →
  geleneksel asset growth measure tech-heavy firms'da yapay sinyal

**Cycle 16 ek (Peters-Taylor 2017 ingested) — total intangibles
generalization:**
[[peters_taylor_2017_intangible_capital]] Lev-Sougiannis R&D-only
methodology'sini total intangible capital'a genişletir:
- Total-intangibles-adjusted: `((TA + K^int)_t - (TA + K^int)_{t-1}) /
  (TA + K^int)_{t-1}` burada K^int = Knowledge (R&D perp inv) +
  Organization (SG&A 30% perp inv) + External (`intan` balance sheet)
- **Total q proxy** [Peters-Taylor Eq. 9]: `q^tot = V / (K^phy + K^int)`
  — standard V/PP&E reject; ρ² **+21%** iyileşme
- CGS-Ion 2018 [s.5-6] **explicit Peters-Taylor methodology kullanmış**:
  HXZ + total capital → 5/35 → **23/35 unexplained** anomaly
  (intangibles düzeltmesi q-factor açıklayıcı gücünü **GÜÇLENDİRMİYOR**)
- Wiki için tasarım kararı: CMA exposure için intangibles-aware
  versiyonun geleneksel CMA'ya kıyasla q-factor span'inde **ek alpha
  üretmediği** CGS-Ion ile gösterilmiş; saf intangibles düzeltme naif
- **Intangibles-aware I/A formülasyonu** Faz 3 NDX strategy spec'inde
  Peters-Taylor methodology baseline (Q40 SG&A θ=30% kalibrasyonu;
  Q41 Lev-Sougiannis vs Peters-Taylor vs Eisfeldt-Papanikolaou horse
  race açık)
- Detay [[concepts/intangibles_adjusted_accounting]];
  [[Asset_Growth]] paralel cross-link.

## Implementation Notes

- **Required data:** Compustat / Sharadar üzerinden total assets (fiscal year-end t-1
  ve t-2)
- **Calculation note:** Yazarlar book equity growth ile total asset growth iki
  alternatifini test eder [s.8]; total asset growth tercih edilmiş. Replikasyonlarda
  ikisini paralel hesaplamak iyi pratik.
- **Annual rebalance:** Haziran sonu, NYSE 30/70 Inv breakpoint'leriyle.
- **Sign:** CMA = Conservative MINUS Aggressive → uzun **düşük** Inv, kısa **yüksek**
  Inv. Yani "düşük asset growth → yüksek beklenen getiri" yorumu (yatırım
  hipotezinin pozitif tarafı).

## Investment proxy yorumu — güncellenmiş

> ⚠️ **challenged by [[cooper_gulen_ion2018_asset_growth_factor_models]]:**
> CMA factor "investment proxy" olarak yorumlanır (Cochrane 1991 investment-q
> + FF15 motivation). **CGS-Ion 2018 [s.3-4]** geleneksel investment ölçüleri
> (CAPX, PPE) veya intangibles-adjusted total capital ile asset growth measure
> değiştirildiğinde FF5 ve HXZ q-factor model performansının dramatik düştüğünü
> gösterir (5/35 → 15-24/35 unexplained anomaly). Yani CMA getirisinin büyük
> kısmı **asset growth'un yapısal yapısından** geliyor, "saf investment proxy"
> yorumu kavramsal olarak sorgulanır. Pratik strateji tasarımı için: CMA
> factor exposure almak istenirse **CGS asset growth ölçüsü** kullanılmalı,
> alternatif investment measures naif. Mekanizma sorusu açık (working capital
> overlap? acquisitions? non-organic growth?) → [[asset_growth_anomaly]] +
> [[meta/open_questions]] Q27.

## Bu Faktörün Yumuşak Karnı

- **Large-cap evrende zayıf [s.13]:** CMA(big) t-stat = 1.03-2.00 — büyük
  hisseler için investment premium'un istatistiksel kanıtı marjinal. S&P 500
  / Nasdaq 100 için bu kritik bir uyarı.
- **HML ile yüksek korelasyon [Tablo 4 Panel C, s.38]:** 0.70. CMA aslında bir
  "iyi-tanımlanmış" investment faktörü mü, yoksa value'nun farklı bir aşırı-tilti
  mi? Joint kontrol (2×2×2×2) inşasında korelasyon 0.37'ye düşüyor — yani
  inşa-bağımlı.
- **Hou-Xue-Zhang q-factor IA faktörü ile rekabeti:** HXZ4'te benzer bir
  investment faktörü (IA = Investment-to-Assets) var ama 2×3×3 sort kullanıyor;
  doğrudan horse race wiki'de yok. → [[meta/open_questions]] Q15.
- **Total asset vs. book equity büyümesi seçimi [s.8]:** Yazarlar "innocuous"
  diyor ama replikasyonlarda iki versiyon arasında küçük farklar olabilir.

## İlgili

- [[famafrench2015_five_factor]] — origin paper (mimicking-portföy çerçevesi)
- [[RMW]] — kardeş profitability faktörü (ikisi birlikte FF5'e eklendi)
- [[HML]] — CMA ile 0.70 korelasyon; HML redundancy'nin mekanik kaynağı
- [[MKT_RF]], [[SMB]] — FF5'in diğer iki faktörü
- [[Asset_Growth]] — single-variable decile sort version; CMA = aggregate
  mimicking-portföy version
- [[asset_growth_anomaly]] — concept sayfası (mekanizma adayları)
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — CMA empirical
  performansının asset growth ölçüsüne sensitivity test paperı
- [[lev_sougiannis_1996_rd_capitalization]] — R&D capitalization
  methodology (intangibles-adjusted CMA inşa)
- [[peters_taylor_2017_intangible_capital]] — total intangible capital
  methodology (q^tot proxy, Lev-Sougiannis generalization)
- [[concepts/intangibles_adjusted_accounting]] — F bloğu hub
- [[factor_model]] — 5-faktör asset pricing kavramı

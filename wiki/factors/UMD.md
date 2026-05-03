---
type: factor
name: UMD
aliases: [PR1YR, MOM]
category: momentum
direction: long_high  # uzun winners (geçmiş 11-aylık getiri yüksek), kısa losers
data_lag_required: "11 aylık lookback (t-12 ile t-2 arası), t-1 skip; piyasa fiyat verisi (≥1 günlük lag)"
rebalance_frequency: monthly  # Carhart orijinali aylık. Yıllık-rebalanced varyantları sonraki literatürde.
universe_tested: ["NYSE/AMEX/NASDAQ all stocks, 1963-07/1993-12"]
---

> 📝 **Cycle 35 ek**: HXZ 2015 q-factor model r_ROE return on equity factor [[factors/ROE]] WML/UMD ile yüksek korelasyon ([[papers/hou_xue_zhang_2015_q_factor]] [Tablo 1B]: corr(ROE, WML) = 0.50). Paper [Section 5.1 ROE Factor]: "The ROE-expected return relation is consistent with momentum, post-earnings-announcement drift, and the financial distress effect"; momentum mechanism ROE channel — winners high short-term prior returns higher expected ROE earn higher returns. q-factor model momentum subsumption ROE factor üzerinden ([Tablo 25 size×momentum]: q-factor m.a.e. 0.11 = Carhart 0.11; momentum h-l alpha avg 0.19% q-factor < 0.25% Carhart < 0.90% FF3).

> 📝 **Cycle 39 ek**: Stambaugh-Yuan 11 anomaly Cluster 2 (PERF) içinde momentum dahil [[factors/PERF]] Cycle 39 ✓ ([[papers/stambaugh_yuan_2017_mispricing_factors]]); composite mispricing P2 5-anomaly avg ranking momentum bileşeni; UMD tek-anomaly factor + UMO2 composite mispricing factor complementary methodology aile (Cluster 2 distress + O-score + momentum + GP/A + ROA performance indicators).
---

# UMD — Up Minus Down (Momentum Faktörü)

> 📝 **İsim notu:** Carhart (1997) [s.61] paperda **`PR1YR`** olarak adlandırır
> ("Prior 1-Year Return"). Sonraki akademik ve endüstri literatüründe standart isim
> **`UMD`** (Up Minus Down) veya **`MOM`** olarak yerleşmiştir. Wiki'de **UMD**
> kanonik isim olarak kullanılıyor.

## Tanım (Carhart 1997 inşası) [s.61, fn 3]

`UMD = (eq-wt avg of top 30% 11-month returns) − (eq-wt avg of bottom 30%)`

- **Lookback penceresi:** t-12 ile t-2 arası kümülatif getiri (yani 11 ay; t-1 ay
  atlanır — kısa-vadeli reversal kontrolü)
- **Sıralama:** Tüm NYSE/AMEX/NASDAQ hisseleri arasında 30/70 percentile
- **Long:** üst %30 (winners). **Short:** alt %30 (losers)
- **Ağırlıklandırma:** **equal-weight** (FF93 SMB/HML value-weighted'tir;
  bu önemli bir konvansiyon farkı)
- **Rebalans:** **monthly**

## Origin

- Akademik kök (anomalinin keşfi): Jegadeesh-Titman (1993) — wiki'de henüz ingest
  edilmedi, Tier listesinde de yok
- Mimicking-portföy formuyla 4-faktör modele dahil: [[carhart1997_four_factor]]

## Reported Performance Across Studies

| Paper | Dönem | Evren | Mean (ay) | t-stat | Notlar |
|---|---|---|---|---|---|
| [[carhart1997_four_factor]] | 1963-07 / 1993-12 | NYSE/AMEX/NASDAQ all | 0.82% | 4.46 | [Tablo II, s.62]; Carhart örnekleminde **en yüksek t-stat'lı faktör** |
| [[israel_moskowitz_2013_shorting_size_time]] **86-yıl** | 1927-01 / 2011-12 | NYSE+Amex+Nasdaq VW | CAPM α 10.48%/yıl | 6.13 | [Tablo 1]; **tüm 4 subperiod'da sig** (1926-49 12.23 / 1950-69 10.26 / 1970-89 9.47 / 1990-2011 8.87); UMD wiki amaç evrenleri için **size-invariant** |
| [[israel_moskowitz_2013_shorting_size_time]] **size Q5 (largest)** | 1926-2011 | aynı | 5-1 spread CAPM α 10.24%/yıl | 4.23 | [Tablo 3]; size Q1-Q5 fark 2.88 t=1.31 INSIG → momentum **size-invariant** |
| [[israel_moskowitz_2013_shorting_size_time]] long-only U | 1927-2011 | aynı | CAPM α 5.55%/yıl | 6.74 | [Fig.1 Panel D]; long-only top 30% winners **information ratio 0.73** (size+value'nun 3x'i); Q5 largest stocks long-only α=3.92% t=3.83 sig |

_(Daniel-Moskowitz 2016 ingest edildiğinde "Momentum crashes" satırı eklenecek;
McLean-Pontiff 2016 ingest edildiğinde post-publication decay satırı eklenecek.)_

> 📝 **Cycle 22 ek (Israel-Moskowitz 86-yıl)**: UMD **size-invariant**
> 86-yıl sample'da; Hong-Lim-Stein 2000 + Grinblatt-Moskowitz 2004
> "momentum small-cap dominant + shorting drives 2/3 profits" iddiası
> 1980-1996 / 1963-1999 sample-spesifik [s.284-286]. **Long-only
> momentum** (top 30% winners) **wiki amaç evrenleri için actionable**
> — Q5 largest stocks long-only α=3.92% t=3.83 sig; Faz 3 strategy
> spec için somut girdi. UMD aylık rebalance orijinal → annual uyarlama
> sensitivity Q33 paralel ([[methodology/backtest_spec]] §2.2).

## Faktör Ailesi İçindeki Yeri

- **Korelasyon (Carhart 1963-93, [Tablo II, s.62]):**
  - UMD ↔ MKT-RF : 0.01 (neredeyse ortogonal)
  - UMD ↔ SMB : −0.29 (büyük-cap eğilimi)
  - UMD ↔ HML : −0.16 (value ile zayıf negatif — momentum genelde growth-tilted)

- **Subsumed by?**
  - FF3 *tarafından subsume edilmez* — bu Carhart'ın 4F motivasyonudur. FF3 momentum-sorted portföylerde sistematik error üretir [[carhart1997_four_factor]] [s.61, fn 2].
  - FF5 *tarafından subsume durumu wiki'de yok* — [[famafrench2015_five_factor]]
    [s.14] "for the LHS portfolios examined here, momentum slopes close to zero"
    ifadesini kullanır, ama momentum-sorted LHS'i test etmez. Yani FF5 momentum
    için spanning iddia etmez. → [[meta/open_questions]] Q16.
  - HXZ4 q-factor (henüz ingest edilmedi) UMD-benzeri faktör içermez; FFGiglio-Xiu
    2020 / Kozak-Nagel-Santosh 2020 redundancy testleri henüz wiki'de yok.

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

Wiki'de henüz yok. Carhart NYSE/AMEX/NASDAQ all-stocks evrenini kullanır.
Large-cap-only momentum performansı için Asness-Frazzini-Pedersen 2019, AQR
data setleri (Tier 3 #55), Daniel-Moskowitz 2016 ingestleri gerekli.

> 📝 Yıllık-frekans + value-weight + S&P 500-only momentum faktörünün
> performansı **Carhart 1997'de yok**. Bu wiki'nin amacı için bu, momentum'u
> kullanmak için **doğrudan transfer edilebilir kanıt eksikliği**dir.

## Decay / Post-Publication Performance + Multiple Testing Status

[[mclean_pontiff_2016_post_publication_decay]] aggregate %35 post-pub
decay multiplier UMD'ye uygulanır. Daniel-Moskowitz 2016 "Momentum
Crashes" (Tier 3 #60) post-1993 dönemdeki büyük drawdown'ları
belgelendirdiği için ek kanıt; henüz ingest edilmedi.

[[harvey_liu_zhu_2016_multiple_testing]] HLZ Şekil 3 mark'i:
- **MOM/UMD (Carhart Tablo II t=4.46, 1963-93):** **sig her cutoff'ta**
  (Bonferroni / Holm / BHY hepsi sig)

UMD multiple-testing düzeyinde **wiki'deki en sağlam factor exposure'lardan
biri**; üç darbe çerçevesinde 3/3 geçer. Yıllık-rebalans transferi ayrı
bir soru (Q16 — Carhart aylık equal-weight). Detay:
[[concepts/multiple_testing]] aggregate tablosu;
[[concepts/post_publication_decay]] üç darbe çerçevesi tablosu.

**Cycle 13 ek (HXZ 2020 ingested):**
[[hou_xue_zhang_2020_replicating_anomalies]] [s.24] **UMD klasik 0.67%
(t=3.66) sig + q-factor alpha 0.11% (t=0.43) INSIG** — q-factor Roe
factor UMD'yi tam span ediyor. Momentum kategorisi 57 anomaly içinde
37 sig (%65 — en yüksek replication rate'lerden). Wiki için: **UMD
strateji baseline'da q-factor Roe factor exposure proxy** olarak
kullanılır; "saf momentum alpha" değil. Üç darbe sig her cutoff;
**dördüncü darbede q-factor span = Roe exposure proxy**. Detay
[[concepts/anomaly_replication]] aggregate tablosu;
[[concepts/post_publication_decay]] dört darbe çerçevesi tablosu
(UMD 3/4).

## Implementation Notes

- **Required data:** günlük veya aylık fiyat (toplam getiri), tüm evren için
  11-aylık kümülatif getiri hesabı + 1-aylık skip
- **Equal-weight inşa [s.61 fn 3]:** Carhart orijinal versiyonu equal-weighted.
  Modern uygulamalarda value-weighted varyantları yaygın (örn. AQR DEF, Ken
  French data library). İki versiyonun primum'u farklı olabilir.
- **Monthly rebalance:** turnover yüksek (~%50/ay literatürde). Yıllık-rebalans
  versiyonu doğrudan trade-off değil.
- **t-1 skip:** kısa-vadeli reversal'i (Jegadeesh 1990 etkisi) izole etmek için.
  Yıllık-rebalanslı bir stratejide bu skip'in anlamı azalır.
- **Trading costs:** Frazzini-Israel-Moskowitz 2018 (Tier 3 #52) momentum'un
  trading cost'larını detaylı ele alır — wiki'de henüz yok.

## Bu Faktörün Yumuşak Karnı

- **Momentum crashes:** post-publication dönemde (özellikle 2000-2002 dot-com
  reversal ve 2008-2009 finansal kriz toparlama) büyük drawdown'lar
  (literatürde yaygın bilinen ama wiki'de Daniel-Moskowitz 2016 ingest edilene
  kadar atıflanamaz).
- **Aylık rebalance + equal-weight implementation maliyeti:** capacity ve
  trading cost yıllık-rebalans value-weight versiyonuna göre dramatik farklı.
- **Yıllık-frekans strateji uyumu sınırlı:** Bu wiki S&P 500 / Nasdaq 100 üzerinde
  yıllık fundamental rebalance hedefliyor. Aylık momentum factor'ün doğrudan
  exposure'unu vermek strateji felsefesiyle çelişir. Olası kullanım:
  yıllık-rebalanslı momentum tilt (örn. trailing 12-aylık getiriye göre yıllık
  ranking) ama bu Carhart 1997 versiyonu değil.
- **Risk vs. mispricing yorumu açık [s.61]:** Yazar açıkça "leave risk
  interpretations to the reader" diyor.

## İlgili

- [[carhart1997_four_factor]] — origin paper (mimicking-portföy çerçevesi)
- [[MKT_RF]], [[SMB]], [[HML]] — 4-faktör modelin diğer üç bileşeni
- [[factor_model]] — 4-faktör asset pricing kavramı

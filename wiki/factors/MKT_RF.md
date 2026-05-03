---
type: factor
name: MKT_RF
category: market
direction: long_high  # uzun piyasa, kısa risk-free
data_lag_required: "yok (piyasa getirisi gözlenebilir)"
rebalance_frequency: monthly  # bizim rebalans sıklığımıza bağlı; faktör tanımı sürekli
universe_tested: ["NYSE/AMEX/NASDAQ ex-financials, 1963-07/1991-12"]
---

# MKT-RF — Market Excess Return (Piyasa Faktörü)

## Tanım (Fama-French 1993 inşası)

`MKT-RF` (paperda `RM-RF` notasyonu): value-weighted CRSP NYSE/AMEX/NASDAQ
piyasa portföyü getirisi eksi 1-aylık T-bill getirisi [[famafrench1993_three_factor]] PDF p.10.

Bu, CAPM'in tek faktörünün — "market beta" üzerinden açıklanan kısmın — Fama-French
çok-faktörlü çerçevedeki karşılığıdır. Üç-faktör modelinde tek başına anomalous
patternleri açıklayamaz; SMB ve HML eklenir.

## Origin

- Konsept olarak: CAPM (Sharpe 1964, Lintner 1965, Black 1972) — wiki'de henüz
  paper sayfası yok
- FF93 mimicking-portföy / time-series-regression çerçevesinde: [[famafrench1993_three_factor]]

## Reported Performance Across Studies

| Paper | Dönem | Evren | Mean (ay) | t-stat | Notlar |
|---|---|---|---|---|---|
| [[famafrench1993_three_factor]] | 1963-07 / 1991-12 | NYSE/AMEX/NASDAQ ex-fin | 0.43% | 1.76 | [Tablo 2, PDF p.13] (yıllık ≈ 5.2%) |
| [[famafrench2015_five_factor]] | 1963-07 / 2013-12 | aynı | 0.50% | 2.74 | [Tablo 4 Panel A, s.37]; 22 yıl uzatılmış örneklem, t-stat 1.76 → 2.74 |
| [[carhart1997_four_factor]] (RMRF) | 1963-07 / 1993-12 | aynı | 0.47% | 2.01 | [Tablo II, s.62] |

_(yeni paperlar ingest edildikçe satır eklenecek)_

## Faktör Ailesi İçindeki Yeri

- **Korelasyon ([[famafrench1993_three_factor]] Tablo 2, PDF p.13):**
  - MKT-RF ↔ SMB : 0.32
  - MKT-RF ↔ HML : −0.38
  - MKT-RF ↔ TERM : −0.34
  - MKT-RF ↔ DEF : −0.07
- **Ortogonal piyasa regresyonu [Eq.(1), PDF p.27]:**
  `RM-RF = 0.50 + 0.44·SMB − 0.63·HML + 0.81·TERM + 0.79·DEF + e`
  R²=0.38, σ=1.97%/ay. Yani diğer faktörler `RM-RF`'in varyansının ~38%'ini
  açıklıyor; geri kalan kısım piyasanın "saf market" bileşeni olarak yorumlanır.

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

- S&P 500 ve Nasdaq 100 stratejileri zaten **piyasaya yakın** evrenler (top
  caps). Bu strateji tasarımları için MKT-RF, CAPM beta üzerinden bir referans
  noktası — strateji tasarımının kendisinde aktif bir alfa kaynağı değil.
- "Excess-of-market" benchmark'lar (S&P 500 minus T-bill, Nasdaq 100 minus T-bill)
  bu wiki'nin strateji-tasarım fazında karşılaştırma çubuğu olarak kullanılır.

## Decay / Post-Publication Performance + Multiple Testing Status

Konsept olarak market premium "decay" konusuyla farklı kategoride — bir anomaly
değil, equity risk premium'un kendisi. [[mclean_pontiff_2016_post_publication_decay]]
türü post-publication testler MKT-RF için anlamlı değil.

[[harvey_liu_zhu_2016_multiple_testing]] HLZ Şekil 3 mark'i MRT (market
beta, Fama-MacBeth 1973) t=2.57 → Bonferroni borderline; Holm sig; BHY
sig. Yani CAPM-base market factor multiple-testing düzeyinde
**marjinal sig**. Detay: [[concepts/multiple_testing]] aggregate
tablosu.

[[hou_xue_zhang_2020_replicating_anomalies]] q-factor model
bileşenlerinin biri (MKT-RF + ME + I/A + Roe); MKT-RF anomaly değil
factor reference, replication framework'üne bilfiil dahil değil ama
q-factor model'in ana bileşeni olarak Faz 3 risk-adjustment baseline.

## Implementation Notes

- **Required data:** value-weighted total return endeksi (CRSP veya benzer),
  risk-free rate (1-month T-bill, Ibbotson veya Fed)
- **Aylık vs. yıllık:** FF93 aylık örneklem (342 gözlem). Yıllık-frekans strateji
  tasarımı için aylık MKT-RF zaman serisi yıllık compound'a dönüştürülür.
- **Universe:** FF93 NYSE/AMEX/NASDAQ "all-stock" market — S&P 500 değil.
  S&P 500 strateji benchmark'ı olarak SPX total return endeksi kullanılır
  (FF93'teki MKT-RF değil).

## Bu Faktörün Yumuşak Karnı

- **t-stat 1.76 [Tablo 2, PDF p.13]:** 342-aylık örneklemde bile equity premium
  istatistiksel olarak %5 iki-yanlı eşiği geçmiyor. Bu, equity premium puzzle'ın
  bir yönüdür (cross-section'da değil, time-series'te equity premium'un büyüklüğü
  ekonomik teoriyle uyuşmuyor).
- **CAPM literatüründe market faktörü "tek başına" 25 size×BE/ME portföyünü
  açıklayamaz** [[famafrench1993_three_factor]] §3-§5: tek-faktör modelin alpha'ları
  size ve BE/ME boyunca sistematik. SMB ve HML eklenince intercept'ler sıfıra
  yaklaşır [Tablo 4, PDF p.20].

## İlgili

- [[famafrench1993_three_factor]] — origin paper (mimicking-portföy çerçevesi)
- [[famafrench2015_five_factor]] — örneklem 1963-2013'e uzatıldı, MKT-RF mean 0.50%
- [[SMB]] — kardeş size faktörü
- [[HML]] — kardeş value faktörü
- [[RMW]], [[CMA]] — FF15'te eklenen profitability ve investment faktörleri
- [[UMD]] — Carhart 4F'de eklenen momentum faktörü
- [[factor_model]] — multi-factor asset pricing kavramı

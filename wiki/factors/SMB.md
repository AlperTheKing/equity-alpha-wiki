---
type: factor
name: SMB
category: size
direction: long_high  # uzun small (=high SMB load), kısa big
data_lag_required: "Haziran t-end'de NYSE median ME (June t-end). Reporting lag ≈0 (ME piyasa bilgisi)"
rebalance_frequency: annual
universe_tested: ["NYSE/AMEX/NASDAQ ex-financials, 1963-07/1991-12"]
---

> 📝 **Cycle 35 ek**: HXZ 2015 q-factor model r_ME size factor ([[factors/I_A]] sister + [[factors/ROE]] sister) SMB ile **virtually identical** ([[papers/hou_xue_zhang_2015_q_factor]] [Tablo 1A-B, s.6]: corr 0.95 + SMB loading 0.99 in FF3 spanning regression; CAPM α 0.24% t=1.64 explained by FF3); HXZ 2015 r_ME ayrı factor entity AÇILMADI (SMB cross-link yeterli). Q11 fully-answered ASTERISK paterni paralel statistical güçlenme HXZ 2015 origin paper anchor.

> 📝 **Cycle 39 ek**: Stambaugh-Yuan 2017 modified SMB methodology + ~2x small-firm premium kanıt [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; paper SMB middle-group only (avoiding mispricing extremes) → 46 bps/month vs FF SMB 25 bps (Stambaugh-Yuan [s.6-7] difference t=3.99 + 4.19 sig); FF SMB sentiment-predictability t=-2.31 (mispricing contamination) vs paper SMB t=-1.60 INSIG (sentiment-immune); **Q11 fully-answered ASTERISK sertleştirme** üç-paper kanıt (Cycle 19 Asness QMJ controlling for QMJ → SMB α=64 bps t=6.39 + Cycle 22 Israel-Moskowitz 86-yıl + Cycle 39 Stambaugh-Yuan modified SMB ~2x premium); methodology choice mispricing-aware FF SMB'den ayrılma sertleştirme.

# SMB — Small Minus Big (Size Factor)

## Tanım (Fama-French 1993 inşası)

`SMB` = (S/L + S/M + S/H) / 3 − (B/L + B/M + B/H) / 3

Burada `S` ve `B` size kategorileri (NYSE median ME breakpoint), `L`, `M`, `H` ise
BE/ME kategorileri (NYSE 30/70 percentile). Tüm portföyler value-weighted aylık
[[famafrench1993_three_factor]] PDF p.9.

**Size ölçüsü:** market equity = adet × Haziran-end fiyat, Haziran t-end'de hesaplanır.
Sort yıllıktır [[famafrench1993_three_factor]] PDF p.8.

## Origin

- İlk paper: [[famafrench1993_three_factor]] (Fama-French 1993)
- Yazarlar: Eugene F. Fama, Kenneth R. French
- (Size etkisinin akademik dokümantasyonu Banz 1981'e kadar gider, ama mimicking
  portföy formuyla SMB FF93 eseridir.)

## Reported Performance Across Studies

| Paper | Dönem | Evren | Mean (ay) | t-stat | Notlar |
|---|---|---|---|---|---|
| [[famafrench1993_three_factor]] | 1963-07 / 1991-12 | NYSE/AMEX/NASDAQ ex-fin | 0.27% | 1.73 | [Tablo 2, PDF p.13]; t-stat 5% iki-yanlı eşiği aşmaz |
| [[famafrench2015_five_factor]] (2x3, 3-sort avg) | 1963-07 / 2013-12 | aynı | 0.29% | 2.31 | [Tablo 4 Panel A, s.37]; örneklem 22 yıl uzatılınca t-stat 1.73 → 2.31 |
| [[famafrench2015_five_factor]] (2x2x2x2) | aynı | aynı | 0.30% | 2.60 | [Tablo 4 Panel A, s.37]; joint kontrol |
| [[carhart1997_four_factor]] | 1963-07 / 1993-12 | aynı | 0.29% | 1.89 | [Tablo II, s.62] |
| [[israel_moskowitz_2013_shorting_size_time]] **86-yıl** | 1926-07 / 2011-12 | NYSE+Amex+Nasdaq VW | CAPM α 2.05%/yıl | 1.72 | [Tablo 1]; 86-yıl SMB **CAPM tarafından kapsanır INSIG**; 1963-2011 sub-sample α=3.08% t=2.30; 1926-1962 α=0.70% t=0.33 INSIG |
| [[israel_moskowitz_2013_shorting_size_time]] long-only S | 1926-2011 | aynı | CAPM α 2.05%/yıl | 1.72 | [Fig.1 Panel D]; long-only smallest half (S) information ratio 0.19; SMB long-dominated |

_(yeni paperlar ingest edildikçe satır eklenecek)_

> 📝 **Cycle 22 ek (Israel-Moskowitz 86-yıl)**: SMB CAPM α 86-yıl
> sample'da INSIG; HLZ MT-corrected `|t|>3.0` BHY ile birlikte
> [[meta/open_questions]] **Q11 fully-answered ASTERISK genişler**.
> Statistical (HLZ) + 86-yıl confirmation (Israel-Moskowitz) çift
> kanıt; quality-controlled SMB resurrection asterisk korunur
> ([[papers/asness_frazzini_pedersen_2019_qmj]] α=64bps t=6.39).

> 📝 **FF15 yeni inşa farkı [s.10-11]:** [[famafrench2015_five_factor]]'de SMB üç ayrı
> 2×3 sortunun (Size×B/M, Size×OP, Size×Inv) ortalaması olarak yeniden tanımlanır.
> FF93'teki tek-sort SMB ile farklıdır ama korelasyon 0.98 [Tablo 4 Panel B, s.38];
> pratikte birbirinin yerine kullanılabilir.

## Faktör Ailesi İçindeki Yeri

- **Korelasyon ([[famafrench1993_three_factor]] Tablo 2, PDF p.13):**
  - SMB ↔ MKT-RF : 0.32
  - SMB ↔ HML : −0.10 (yaklaşık ortogonal)
- **t-stat 1.73 [Tablo 2, PDF p.13]:** SMB'nin tek başına bir "premium" olduğu
  iddiası FF93 örnekleminde **istatistiksel olarak marjinal**. Asset-pricing
  modelinde rolü, primium üretmek değil 25-portföy cross-section'unda size
  farklılığını yakalamak.

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

**Wiki'de henüz yok ve burada kavramsal bir uyarı:**

- S&P 500 evreni tanım gereği **large-cap-only**; SMB'nin uzun bacağı (small)
  çoğunlukla S&P 500 dışında kalan firmalar.
- Nasdaq 100 da büyük-cap odaklı (top 100 non-financial Nasdaq firmaları).
- SMB'nin S&P 500 içi varyansı (büyük cap içinde "küçük büyük" vs. "büyük büyük")
  marjinaldir — bu wiki'nin amacı için **SMB'nin doğrudan kullanımı sınırlı**.
- Stratejik soru: SMB'nin yerine S&P 500 / Nasdaq 100 içinde *evren-özel* size sort
  mu kullanılmalı? Bu cevaplanmamış. → [[meta/open_questions]] yeni soru
  eklenecek (Q12).

## Decay / Post-Publication Performance + Multiple Testing Status

> ⚠️ **HLZ Şekil 3 mark'i [[harvey_liu_zhu_2016_multiple_testing]]
> [s.22]:** **SMB never sig under multiple testing** (Bonferroni / Holm /
> BHY hepsi insig). FF93 sample-spesifik t=1.73 marjinal sig'in
> multiple-testing-corrected **kesin çürütülmesi**. Wiki için kritik:
> SMB factor exposure'ı **strateji tasarımı için "target" değil**;
> factor-model risk-adjusted regression baseline'da kalır (model
> parsimony argümanı). [[mclean_pontiff_2016_post_publication_decay]]
> aggregate decay multiplier ek olarak uygulanır ama HLZ MT-corrected
> insig sonucu zaten **kesin çürütme** sağlıyor.

Detay: [[concepts/multiple_testing]] aggregate tablosu;
[[concepts/post_publication_decay]] üç darbe çerçevesi tablosu (SMB
0/3 üç darbe).

## Implementation Notes

- **Required data:** market equity (CRSP/equivalent), share count, June-end price
- **NYSE breakpoint asimetrisi (KRİTİK):**
  NYSE'nin median ME'si NYSE/AMEX/NASDAQ tüm evrenin median'ından çok daha büyük.
  Bu yüzden **"Small" kategorisi son derece geniş bir küçük-cap kümesini içerir**;
  faktör getirisi büyük ölçüde mikro-cap dinamikleriyle yönlenir. S&P 500 evreninde
  bu yapı transferli değil; doğrudan kullanım uygun değil.
- **Annual rebalance frequency:** Haziran sonu, yıllık.
- **Penny stocks / liquidity:** FF93 paperı liquidity filtresi tartışmaz; modern
  replikasyonlar (Hou-Xue-Zhang 2020 vb.) genelde liquidity kesimi uygular.

## Bu Faktörün Yumuşak Karnı

- **t-stat 1.73 [Tablo 2, PDF p.13]:** orijinal örneklemde bile zayıf. Out-of-sample
  daha da zayıflamış olabilir (henüz wiki'de delillenmedi).
- **Microcap-driven:** NYSE breakpoint asimetrisi nedeniyle SMB, küçük "big"
  vs. büyük "big" farkını yakalamaz; mostly **microcap effect**'i yakalar.
- **Large-cap evrende relevance düşük:** S&P 500 / Nasdaq 100 stratejisi için
  SMB'nin **olduğu gibi kullanılması** uygun görünmüyor — bu wiki'nin bir tasarım
  kararı için adresleyeceği bir nokta.

## İlgili

- [[famafrench1993_three_factor]] — origin paper
- [[famafrench2015_five_factor]] — SMB inşası 3-sort ortalamasına revize edildi
- [[harvey_liu_zhu_2016_multiple_testing]] — SMB never sig under multiple
  testing — wiki için kesin statistical çürütme
- [[hou_xue_zhang_2020_replicating_anomalies]] — SMB factor reference;
  447 anomaly census ME factor olarak; HXZ NYSE-VW methodology'de
  size factor likely insig (HLZ never sig ile uyumlu — çift kanıt)
- [[HML]] — kardeş value faktörü
- [[MKT_RF]] — kardeş market faktörü
- [[RMW]], [[CMA]] — FF15'te eklenen yeni faktörler
- [[UMD]] — Carhart 4F'de eklenen momentum faktörü
- [[factor_model]] — multi-factor asset pricing kavramı

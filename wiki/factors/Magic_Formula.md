---
type: factor
name: Magic_Formula
category: composite_value_quality
direction: long_high  # uzun yüksek combined rank, kısa düşük
data_lag_required: "Fiscal year-end + standard reporting lag (3-5 ay)"
rebalance_frequency: annual  # Greenblatt orijinali yıllık; HMXZ akademik test monthly portfolio rebalance
universe_tested: ["NYSE/AMEX/NASDAQ all-stocks 1967-2018, HMXZ implementation"]
---

# Magic Formula (Greenblatt 2005/2010)

## Tanım

**Magic Formula** = iki bileşenli komposit ranking:
1. **Earnings yield** = EBIT / EV (Enterprise Value = market cap + net debt)
2. **Return on capital** = EBIT / (Net working capital + Net fixed assets)

Yöntem: Her firma her iki metric'te ayrı ayrı sıralanır, iki sıranın **toplamı**
(combined rank) firma seçim skorudur. **Yüksek combined rank = yüksek earnings
yield + yüksek return on capital = "good company at a bargain price."**

> 📝 **Originator: Greenblatt (2005, 2010)** "The Little Book That (Still) Beats
> the Market" — kitap formatında popüler heuristik. **Henüz wiki'de ingest
> edilmedi** (Tier 3 #57 placeholder). Greenblatt 2006 ingest edildiğinde
> "originator + retail framing" + practical thresholds eklenir.

> 📝 **Academic validator: [[hou_mo_xue_zhang_2020_security_analysis]]** —
> Greenblatt'in heuristik formülünü q-factor / q5 model lens'inde resmi test
> eder, kanıtlar.

## Origin

- **Heuristik kaynak:** Greenblatt, J. (2005, 2010) — "The Little Book That
  (Still) Beats the Market." Wiley. ISBN 978-0-470-62415-4.
- **Kavramsal motivasyon:** Buffett-Munger Graham-Dodd value-with-quality
  felsefesinin sayısallaştırılması. Yüksek-kalite (ROIC yüksek) firmaları
  ucuz fiyatla (high earnings yield) almak.
- **Akademik test:** [[hou_mo_xue_zhang_2020_security_analysis]] §3.3,
  [Tablo 3] — q-factor / q5 lens'inde değerlendirme (1967-2018 sample).

## Reported Performance Across Studies

| Paper | Dönem | Evren | Spread | t-stat (or sig %) | Notlar |
|---|---|---|---|---|---|
| Greenblatt 2005/2010 (kitap, ingest edilmedi) | book-period | retail-friendly | claimed annual ~30% | — | popüler heuristik claim; akademik scrutiny olmadan |
| [[hou_mo_xue_zhang_2020_security_analysis]] (decile spread) | 1967/01-2018/12 | NYSE/AMEX/NASDAQ all | high-minus-low decile spread (paperdan teyit) | sig at decile-level | [Tablo 3, s.20] |
| [[hou_mo_xue_zhang_2020_security_analysis]] (q-factor alpha) | aynı | aynı | 0.26% | t=1.51 (insig) | [Tablo 3, s.20]; q-factor decile alpha |
| [[hou_mo_xue_zhang_2020_security_analysis]] (**q5 alpha**) | aynı | aynı | **−0.13%** | t=−0.76 (insig) | [Tablo 3, s.20]; **q5 alpha NEGATİF/SIFIR — TAM SPAN** |
| [[hou_mo_xue_zhang_2020_security_analysis]] (q5 size partition) | aynı | aynı, three size groups | micro 0.06%, small 0.03%, big −0.11% | tümü insig | [Tablo 3, s.20]; tüm size segmentlerinde span |
| [[mclean_pontiff_2016_post_publication_decay]] aggregate decay multiplier | (82 anomaly aggregate, 1972-2011) | NYSE+AMEX+NASDAQ all-stocks aggregate | aggregate post-pub decay **%35** (sig 1%); Greenblatt 2005 kitap-kaynaklı, peer-reviewed dergi olmadığı için 82 anomaly setine **dahil değil** | (n/a — anomaly setinde değil) | aggregate decay analytic multiplier yine de uygulanabilir; HMXZ 1967-2018 sample'da q5 alpha negatif → post-pub decay **empirik olarak gerçekleşmiş**; aggregate %35 baseline'ı ile uyumlu (q5 lens'inde span = decay-adjusted spread sıfır seviyesinde) |

> 📝 **Wiki için kritik bulgu:** Magic Formula HMXZ q5 lens'inde **TAM SPAN**
> ediliyor — alpha negatif/sıfır. Yani Magic Formula'nın getirisi büyük ölçüde
> q5 model investment + profitability factor exposure'larıyla açıklanıyor.
> ROE factor key driver [HMXZ s.20].

## Faktör Ailesi İçindeki Yeri

- **Yapısal benzerlikler:**
  - Earnings yield (EBIT/EV) ↔ V/P ratio (intrinsic value ratio); her ikisi
    *value* boyutu
  - Return on capital (EBIT/Capital) ↔ ROE / RMW; her ikisi *profitability*
    boyutu
  - Magic Formula = "value × quality" cross-product → [[F_Score]] + V/P combined
    yaklaşımının ([[li_mohanram2019_quality_value]]) heuristik prototipi
- **Subsumed by?** **EVET** [[hou_mo_xue_zhang_2020_security_analysis]]
  [Tablo 3, s.20]: q5 model Magic Formula'yı tam span ediyor; alpha
  insignificant ve hatta hafif negatif. Magic Formula'nın getirisi q5 risk
  premium'larıyla açıklanıyor.

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

[[hou_mo_xue_zhang_2020_security_analysis]] [Tablo 3] **big stocks segmentinde**
q5 alpha −0.11% (t=−0.84, insig). NYSE big-stocks tertile = top NYSE-ME
quartile, S&P 500'e yakın ama tam karşılığı değil.

> 📝 **Wiki için kritik:** S&P 500 tarzı large-cap evrende Magic Formula
> standalone alpha **muhtemelen anlamsız**. Ancak (a) Magic Formula'nın
> q5 factor exposure'u korunduğu için risk premium katkısı var, (b) uygulama
> kolaylığı (sadece 2 metric) retail-friendly.

NDX evrene transferi için R&D capitalization eksikliği aynı [[CMA]] / I/A
benzeri sorun.

## Decay / Post-Publication Performance

Greenblatt 2005/2010 kitap publication tarihi sonrası dönem
[[hou_mo_xue_zhang_2020_security_analysis]] sample'ında dahil. q-factor
alpha 0.26% (t=1.51) ve q5 alpha **negatif** (-0.13%, t=-0.76) → post-
publication decay büyük ölçüde **gerçekleşmiş**. Magic Formula
[[mclean_pontiff_2016_post_publication_decay]] 82 anomaly setinde
academic-peer-reviewed olmadığı için **explicit dahil değil**, ama
aggregate %35 decay baseline'ı q5-spans-Magic-Formula bulgusu ile
uyumlu (decay-adjusted spread sıfır seviyesinde, alpha kayboluyor).

> 📝 **Wiki için yorumu:** Magic Formula post-publication decay'in **uç
> örneği** — alpha negatife döndüğü için strateji standalone değer
> üretmiyor; q5 risk premium exposure'larıyla yakalanabilir. Heuristik
> retail-friendly çekiciliği akademik baseline'la uyumsuz. Detay
> [[post_publication_decay]] decay-adjusted spread tablosu.

### Multiple Testing Status (Cycle 12 ek)

[[harvey_liu_zhu_2016_multiple_testing]] çerçevesinde Magic Formula
HMXZ'nin q5 alpha rakamı:
- **q5 alpha t=−0.76 (decile spread):** **insig** tüm cutoff'larda
  (klasik 1.96 dahil)
- **q5 size partition'larda micro/small/big alpha t-statistic'leri
  hepsi insig**

Üç darbe çerçevesinde Magic Formula 0/3 — alpha zaten q5 ile span
edildiği için MT kontrolüne gerek bile yok. **Faz 3 strateji
baseline'a alınmaz.** Detay [[concepts/multiple_testing]] aggregate
tablosu; [[concepts/post_publication_decay]] üç darbe çerçevesi tablosu.

**Cycle 13 ek (HXZ 2020 ingested):**
[[hou_xue_zhang_2020_replicating_anomalies]] kapsamı dışı — Magic
Formula Greenblatt 2005 kitap kaynaklı, peer-reviewed academic paper
değil; HXZ academic literature sample'da yer almıyor. Ancak HMXZ
Security Analysis 2020 paralel q-factor lens'inde alpha negatif/sıfır
(t=-0.76 insig). **Dört darbe çerçevesinde Magic Formula 0/4** —
academic strateji baseline'a alınmaz; retail-friendly framing dışında
değer üretmiyor. Detay [[concepts/anomaly_replication]] aggregate tablosu.

## Implementation Notes

- **Required data:**
  - Income statement: EBIT (operating income before interest)
  - Balance sheet: net working capital (current assets − current liabilities),
    net fixed assets (PP&E net)
  - Market: market cap, total debt (EV calculation için)
- **Compustat fields (rough):** EBIT veya OIBDP (proxy), AT, ACT, LCT, PPENT,
  CSHO, PRCC_F, DLTT, DLC
- **Sharadar:** Magic Formula bileşenleri Sharadar Core US Fundamentals'da
  mevcut — implementation trivial
- **Annual rebalance:** Greenblatt orijinal kitap önerisi yıllık;
  [[hou_mo_xue_zhang_2020_security_analysis]] aylık portfolio rebalance test
  ediyor. Wiki amacı için yıllık rebalans uygun.
- **Sektör filtreleme (Greenblatt):** finans, utility ve REIT firmaları
  dışlanır — EBIT/return on capital tanımları bu sektörler için meaningful
  değil.
- **Combined rank (vs continuous z-score):** Greenblatt orijinal yaklaşım
  rank-toplam; modern uygulamalarda continuous z-score kombinasyonu kullanılabilir.
  Performans farkı belirsiz.

## Bu Faktörün Yumuşak Karnı

- **q5 ile TAM SPAN ediliyor** [[hou_mo_xue_zhang_2020_security_analysis]]
  [Tablo 3, s.20]: alpha insignificant tüm size partition'larda; standalone
  alpha kaynağı yok. **Strateji tasarımı için marjinal değer:** uygulama
  kolaylığı + factor exposure proxy.
- **Greenblatt sample-period ve methodology spesifik:** Kitap sample'ı
  1988-2004 USA; HMXZ uzun sample (1967-2018) post-publication dönemi içerir
  ve alpha kayboluyor.
- **Sektör dışlama (finans/utility/REIT) ad-hoc:** EBIT/ROC tanımları bu
  sektörler için meaningful değil ama dışlama kuralı modern S&P 500 sektör
  ağırlıklarıyla uyumsuz olabilir.
- **NDX intangibles için kalibre değil:** EBIT muhasebe kuralları R&D
  giderleştirmeyi düzeltmez; tech firmalarda EBIT yapay düşük; ROC yapay
  yüksek (asset base düşük). Lev-Sougiannis 1996 (Tier 2 #26) intangibles
  düzeltme.
- **Heuristik kaynak academic peer review değil:** Greenblatt kitabı popüler
  literatür; spesifik sample, methodology detayları HMXZ'nin akademik
  reproducible test'inde re-construct edilmiş.

## İlgili

- [[hou_mo_xue_zhang_2020_security_analysis]] — academic validator paper
  (q-factor / q5 lens'inde tam span kanıtı)
- [[F_Score]] — alternatif composite (high-BM evrende kalibre); F-Score q5
  lens'inde mikrocap'te alpha korur, Magic Formula tüm segmentlerde span
- [[G_Score]] — growth-side composite (HMXZ kapsamı dışı, doğrudan
  karşılaştırma yok)
- [[li_mohanram2019_quality_value]] — F+V/P, G+V/P combined yaklaşımları;
  Magic Formula = value × quality cross-product'in heuristik prototipi
- [[winner_loser_identification]] — Magic Formula bu paradigmanın
  retail-uyumlu, kavramsal-eğitici versiyonu
- [[fundamental_scoring]] — komposit skor üretimi paradigması içinde Magic
  Formula'nın yeri (rank-toplam yaklaşımı)
- [[contextual_fundamental_analysis]] — Magic Formula evren-koşulsuz
  uygulanır (sektör filtresi hariç); F/G-Score'un universe-conditioning
  pattern'iyle farklılaşır
- (sonra) Greenblatt 2005/2010 (Tier 3 #57) — heuristik origin

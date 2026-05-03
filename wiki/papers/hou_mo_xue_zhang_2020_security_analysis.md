---
type: paper
authors: [Hou, Kewei, Mo, Haitao, Xue, Chen, Zhang, Lu]
year: 2020
title: "Security Analysis: An Investment Perspective"
venue: "Working Paper, September 2020 (Ohio State / LSU / Cincinnati / NBER)"
url: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3514080
local_path: raw/papers/hou_mo_xue_zhang_2020_security_analysis.pdf
ingested: 2026-04-28
tags: [q_factor, q5_model, security_analysis_synthesis, investment_capm, V_P_de_facto, magic_formula_validator, B_blok_finali]
status: ingested
---

# Hou, Mo, Xue & Zhang (2020) — Security Analysis: An Investment Perspective

> 📝 **Atıf konvansiyonu:** `[Tablo N]` ve `[s. X]`. Embedded text extract:
> `raw/papers/hou_mo_xue_zhang_2020_security_analysis.txt`.

> 📝 **Cycle 35 ek**: q-factor model **formal origin tanımı**
> [[papers/hou_xue_zhang_2015_q_factor]] (Cycle 35 ✓ Tier 1 #3 yüksek
> priori); HMXZ 2020 q5 model = HXZ 2015 q-factor (4-factor MKT + ME +
> I/A + ROE) + eg+ expected growth factor extension. 4-paper × 8+ yıl
> q-factor literature continuity hattı: HXZ 2015 origin → HMXZ 2020
> q5 (BU PAPER) → HXZ 2020 Replicating empirical → JKP 2023 Bayesian
> framework. [[concepts/q_factor_model]] yeni concept (Cycle 35) hub
> sayfa; placeholder formal origin → live link.
>
> 📝 **Cycle 38 ek**: HMXZ Tablo 5 Cop methodology **standalone origin
> paper** [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]
> (Cycle 38 ✓ Faz 3 seçici ingest #3); HMXZ q5 model Cop component
> 4/4 hayatta kalan q-factor alpha 0.69%/ay sig validation Ball-GLN
> origin'inden methodology continuity; **Profitability zinciri 4. halka
> Cop methodology origin** placeholder → live link [[factors/Cop]]
> yeni factor entity (Cycle 38).

> 📝 **B bloğunun #4 ve finali.** q5 model lens'iyle B bloğunun (F-Score, V/P)
> ve A bloğu sınırlarındaki (Magic Formula, QMJ, Buffett) fundamental skor /
> security analysis stratejilerini test eder. **G-Score kapsamda değil**
> (paper Mohanram 2005'i test etmemiş).

> 📝 **V/P de facto wiki referansı:** [[li_mohanram2019_quality_value]] ile
> birlikte bu sayfa V/P methodology + ampirik kanıt için wiki'nin merkez
> referansı. Frankel-Lee 1998 ingest edilmediği için (paywall) iki paper
> birbirini tamamlar.

## TL;DR

q5 model ([[hou_xue_zhang_2015_q_factor]] q4 + expected growth = q5) lens'iyle
6 fundamental scoring / security analysis stratejisi + Buffett'in Berkshire
performansı test edilir. **Sample dönemi: stratejiye göre 1967-2018 ile
1972-2018 arası, monthly portfolio rebalans, NYSE breakpoint.** Ana sonuçlar
[Tablo 1-7]:
- **Frankel-Lee V/P [Tablo 1]:** q-factor + q5 alphalarının her ikisi de
  **economically küçük + statistically insignificant**; investment factor (I/A)
  ana açıklayıcı.
- **Piotroski F-Score [Tablo 2]:** q5 alphalarının microcap = 0.33% (t=2.67,
  **anlamlı**); small/big = 0.10%, 0.03% (insignificant). q-factor model
  reject (GRS p=0.01); **q5 cannot reject (p=0.09)**. ROE factor ana açıklayıcı.
- **Greenblatt Magic Formula [Tablo 3]:** q5 decile alpha **−0.13% (t=−0.76)**
  — alpha negatif/sıfır, **TAM SPAN**. ROE factor key driver.
- **Asness QMJ [Tablo 4]:** q-factor model reject (GRS p=0.00); **q5 captures**
  (alpha 0.06%, t=0.42, GRS p=0.12).
- **Bartram-Grinblatt, Penman-Zhu, Ball-GLN [Tablo 5-7]:** Benzer pattern —
  q5 büyük ölçüde span ediyor, microcap'te kalıntı alpha var.
- **Buffett's alpha [Tablo 8]:** q-factor 56% spread reduction, alpha 0.64%
  (t=2.45); **q5 alpha 0.77% (t=2.69)** — Buffett q5 ile **tam span EDİLMİYOR**.
- **Best 20 Active Value Funds [Tablo 10]:** q5 model 69-89% performans açıklar.

**Wiki-kritik bulgu:** **Kısmi redundancy hipotezimiz doğrulandı** —
fundamental skorlar microcap dışında q5 model exposure'larıyla büyük ölçüde
span ediliyor; ama **mikrocaps'te kalan kanıtlanabilir alpha** + **uygulama
kolaylığı** + **active fund Buffett-tipi alpha kaynağı** fundamental
scoring'in marjinal değerini koruyor.

## Tek Cümle Tezi

Investment CAPM'in empirik implementasyonu olan q5 model — investment +
profitability + expected growth + market + size faktörlerini içeren 5-faktör
asset pricing çerçevesi — Graham-Dodd security analysis stratejilerinin (V/P,
F-Score, Magic Formula, QMJ vb.) **büyük çoğunluğunu büyük cap segmentinde
açıklar** ama mikrocap segmentinde ve aktif değer yönetimi (Buffett tipi)
performansının önemli bir kısmında residual alpha kalır.

## q5 model çerçevesi

`R(i,t) − R_f(t) = a + β_MKT·MKT(t) + β_ME·ME(t) + β_I/A·I/A(t) + β_ROE·ROE(t) + β_Eg·Eg(t) + ε(t)`

5 faktör [s.5, Hou-Mo-Xue-Zhang 2020 referansla]:
1. **MKT** — market excess return ([[MKT_RF]] muadili)
2. **ME** — size factor (FF SMB muadili, [[SMB]])
3. **I/A** — investment-to-assets growth (FF CMA muadili, [[CMA]])
   > ⚠️ challenged by [[cooper_gulen_ion2018_asset_growth_factor_models]]:
   > q5 I/A factor'ün "investment proxy" yorumu sorgulanmıştır. CGS-Ion 2018
   > [s.3-4] q-factor model performansının CGS asset growth ölçüsüne kritik
   > bağlı olduğunu, geleneksel investment measures (CAPX, PPE) veya
   > intangibles-adjusted total capital ile değiştirildiğinde **35 anomaly'den
   > 15-24'ünü açıklayamadığını** (asset-growth-base 5/35 → alt 15-24/35)
   > gösterir. I/A "asset growth measure" demek doğru, ama "investment proxy"
   > yorumu yanıltıcı. Detay: [[asset_growth_anomaly]].
4. **ROE** — return on equity (FF RMW muadili, [[RMW]])
5. **Eg** — expected growth (yeni 5. faktör, q5'i q4'ten ayıran)

> 📝 q5 vs FF5 yapısal benzerlik: 4 ortak (MKT, size, investment, profitability)
> + 1 farklı (q5'in expected growth vs FF5'in book-to-market = HML).
> [[famafrench2015_five_factor]] HML'in 5F altında redundant olduğunu zaten
> göstermişti — q5 model HML'i ekleme gereği bile duymuyor; expected growth
> ile değiştirip security analysis stratejilerini açıklamada **HML'siz ortodoks
> yapısı** sağlar.

## V/P methodology (Frankel-Lee 1998 detaylı, de facto wiki referansı)

> 📝 **V/P entity sayfası açılmadı** (Frankel-Lee 1998 paywall). Bu bölüm
> [[li_mohanram2019_quality_value]] ile birlikte V/P'nin de facto wiki
> methodology referansı.

### Residual income valuation model [s.16-17]

`V_t = B_t + Σ_{k=1}^∞ E_t[(ROE_{t+k} − r_e) · B_{t+k-1}] / (1+r_e)^k`

- `B_t` — book equity at time t
- `ROE_{t+k}` — period-k return on equity
- `r_e` — cost of equity capital (typically risk-free rate + 5%)
- Clean surplus accounting: `B_{t+k} = B_{t+k-1} + (1−κ)·NI_{t+k}` where κ is
  payout ratio

### V/P calculation
`V/P ratio = V_t / P_t` — yüksek V/P = undervalued.

### Cross-sectional forecast (Hou-van Dijk-Zhang 2012 + Li-Mohanram 2014)
[[li_mohanram2019_quality_value]] [s.12-13] aynı methodology'i kullanır;
analyst-forecast'sız tüm evrene V/P uygulanabilir. Cross-sectional regression
ile expected NI tahmin edilir → ROE serisi → V_t.

### V/P empirik sonuç [Tablo 1, HMXZ s.17-18]

- Sample: 1967/01 - 2018/12, monthly portfolio rebalans
- High-minus-low decile spread: significant ham return
- q-factor alpha: small + insignificant
- **q5 alpha: 0.13%, 0.13%, 0.11%** (t=1.05, 0.88, 0.68) micro/small/big
  — **TÜM insignificant**, V/P q5 ile tam span ediliyor
- I/A factor (investment) ana açıklayıcı: high-minus-low quintile I/A
  loading 0.5 (yüksek; growth investment patterns)

## Goal Alignment

> Bu paper'ın sonuçlarının projenin 4 teknik özelliğine bağlanması.

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Decile + quintile spread testleri standart asset pricing formatında; high-minus-low alpha + GRS test reportu [Tablo 1-8] | ✅ doğrudan fit (akademik test çerçevesi) |
| **Annual rebalance** | Çoğu strateji **monthly** portfolio rebalans (q-factor convention); Penman-Zhu 2018 strategy "Annually Formed" [Tablo 6 başlığında]. F-Score için Piotroski'nin annual formation'ı korunur (June rebalance) ama tüm test sonuçları aylık return frekansında | ⚠️ kısmen — strateji formation annual ama portfolio test monthly |
| **Large-cap evrene transfer** | NYSE breakpoint kullanılıyor; **3 size partition (micro / small / big)** explicit raporlu. **Big stocks segmentinde q5 ile span**, micro segmentinde residual alpha. Bu wiki için kritik: large-cap evrenimiz "big" segmentine en yakın | ✅ test edilmiş + ⚠️ "big segment" = top-quartile NYSE; S&P 500 / NDX'in tam karşılığı değil |
| **NDX intangibles / growth firms** | q5 investment factor (I/A) = **ham total asset growth**, R&D capitalization yapılmamış. Asness QMJ (quality with intangibles components) q5 ile span edilebiliyor [Tablo 4] ama bu **intangibles düzeltmesi** değil — NDX-style tech firmaları için ekstra adjustment gerek | ⚠️ Q23 ile bağlı; intangibles için kalibre değil |

**Strateji tasarımına net implikasyon:**

Bu paper, **B bloğunun q-factor sertifikası** rolünü oynuyor. Üç dengeli kayıt:

1. **Kısmi redundancy doğrulandı:** F-Score, V/P, Magic Formula, QMJ (büyük cap
   segmentinde) q5 model exposure'larıyla **büyük ölçüde** span ediliyor.
   Strateji tasarımı için **ham factor exposure (I/A + ROE + ME) almak** benzer
   getiri sağlar — fundamental scoring **uygulama-kolaylığı** + **microcap
   residual alpha** + **active fund-tipi katkı** ile değer korur.

2. **Microcap residual alpha:** F-Score'un microcap q5 alpha'sı 0.33% (t=2.67)
   anlamlı [Tablo 2]. Bu wiki'nin amacı (S&P 500 / NDX, large-cap-only) için
   **işlevsel olarak Faz 3 strateji tasarımı q5 risk premium'larından geçer**;
   microcap effects relevance düşük.

3. **Active value fund alpha kaynağı korunur:** Buffett's Berkshire q5 ile
   **tam span edilmiyor** (q5 alpha 0.77%, t=2.69) [Tablo 8]. Yani aktif
   discretionary değer yönetiminin alpha'sı q5 model'in ötesinde. Sistematik
   strateji bu alpha'ya ulaşamaz ama **q5 risk premium'larını yakalamak**
   asıl hedef olabilir.

## B bloğu içindeki konum

> Bu paper B bloğunun q-factor sertifikasıdır. Aşağıdaki tablo B bloğunun 4
> paperının HMXZ q5 lens'iyle ilişkisini özetler.

| B bloğu paper | HMXZ q5 lens'inde durumu | Sentez katkısı |
|---|---|---|
| [[piotroski2000_f_score]] (F-Score) | [Tablo 2, s.18-19]: q5 alphas micro 0.33% (t=2.67, **sig**), small 0.10% (insig), big 0.03% (insig). q5 GRS cannot reject (p=0.09). ROE factor key driver. | **Kısmi redundant** — mikro hariç q5 ile span; ROE exposure F-Score'un getirisinin büyük kısmını taşıyor; **incremental alpha mikrocap segmentinde sınırlı** |
| [[mohanram2005_g_score]] (G-Score) | **Test EDİLMEDİ** — paper Mohanram 2005'i kapsamına almamış | **Boşluk** — G-Score'un q5 lens'inde durumu **wiki'de hala bilinmiyor**; growth-side için q-factor model'in açıklayıcılığı açık soru → yeni Q25 |
| [[li_mohanram2019_quality_value]] (F+G+V/P+PEG combined) | **Combined doğrudan test edilmedi.** V/P standalone q5 ile span [Tablo 1]; F-Score standalone q5 mikro hariç span [Tablo 2]. Combined performance HMXZ kapsamı dışında | **Doğrudan kanıt yok** — Li-Mohanram'ın F&V/P combined'i HMXZ q5 lens'inde test edilseydi muhtemelen kısmi span (V/P ve F ayrı ayrı span ediliyor) ama bu yorum kanıtsız |
| HMXZ 2020 (bu paper) | — | **B bloğunun q-factor sertifikası**: q5 model fundamental skorların *risk premium* yorumunu sağlar; mispricing yorumuna alternatif çerçeve |

**B bloğu net sonuç (3-4 cümle, consolidation pass'in zemini):**

(1) F-Score, G-Score, V/P, ve combined fundamental scoring stratejileri **standalone'da** robust hedge return üretiyor (orijinal paper sample'larında +21-23% range; Li-Mohanram modern replikasyonda +7-21% range; HMXZ q-factor lens'inde residual alpha micro hariç insignificant).
(2) Q-factor model lens'inde fundamental skorların **getirisinin büyük kısmı** investment + profitability faktör exposure'larıyla **span ediliyor** — yani ham factor portfolio ile benzer getiri elde edilebilir.
(3) Fundamental scoring'in **marjinal değeri**: (a) microcap segmentinde residual alpha, (b) uygulama kolaylığı (binary/continuous skor vs factor model implementation), (c) active discretionary fund alpha kaynağı (Buffett-tipi), (d) intangibles-aware versiyonların potansiyel iyileştirmesi.
(4) Wiki için strateji tasarımı: **large-cap evrene transfer için fundamental skorlar + factor exposure birlikte düşünülmeli** — sadece skor değil, sadece factor değil; ikisinin kombinasyonu (Li-Mohanram tarzı combined paradigma) en güçlü kanıtı taşıyor.

## Empirik Sonuçlar (sayılarla, tablo bazında)

### Tablo 1 — Frankel-Lee V/P [s.17-18]
- Sample: 1967/01 - 2018/12
- High-minus-low decile spread: significant ham return
- q-factor alpha: economically small + insignificant
- **q5 alpha:** micro 0.13% (t=1.05), small 0.13% (t=0.88), big 0.11% (t=0.68)
  — **tümü insignificant**
- I/A loading 0.5 (yüksek growth investment patterns)
- **Tam span**

### Tablo 2 — Piotroski F-Score [s.18-19]
- Sample: 1972/07 - 2018/12 (sufficient data coverage)
- Sort: F-Score 0-9, low (0,1,2,3) ile high (8,9) gruplandırma; quintile var
  + 15 two-way size×F-Score
- High-minus-low quintile q-factor alphas: 0.23%, 0.10%, 0.12%
  (t=1.56, 0.85, 0.84) — **insignificant**
- **q5 alphas: 0.33%, 0.10%, 0.03%** (t=2.67, 0.81, 0.15) micro/small/big
  — **microcap anlamlı**, small/big insignificant
- GRS test: q-factor reject (p=0.01); **q5 cannot reject (p=0.09)**
- ROE factor key driver
- Sample-period note [s.19, fn 9]: "If we end the sample in December 1998
  (close to Piotroski's original sample), F-Score is much stronger" —
  post-publication decay implication
- Fama-French 6F (FF5+UMD) F-Score'u da yakalıyor [s.19, fn 10]

### Tablo 3 — Greenblatt Magic Formula [s.20]
- Sample: 1967/01 - 2018/12
- High-minus-low decile q-factor alpha 0.26% (t=1.51, **insig**)
- **q5 alpha −0.13% (t=−0.76, insig)** — alpha **NEGATİF/SIFIR**
- Two-way size sorts q5 alphas: 0.06%, 0.03%, −0.11% (micro/small/big) — tümü
  insignificant
- GRS cannot reject q-factor or q5
- ROE factor key driver
- **TAM SPAN**

### Tablo 4 — Asness-Frazzini-Pedersen QMJ [s.21]
- Decile high-minus-low marjinal sig (t=1.66)
- q-factor model **fails** (GRS p=0.00)
- **q5 alpha 0.06% (t=0.42), GRS p=0.12** — q5 captures QMJ
- Q15 (FF5 vs HXZ4) sorusunu güçlendirir

> 📝 **Cycle 19 ek (Asness QMJ original paper ingest)**:
> [[asness_frazzini_pedersen_2019_qmj]] Cycle 19'da ingest edildi.
> HMXZ Tablo 4 **composite QMJ test ediyor (4 dimension breakdown
> YOK)**; QMJ paper original **4 dimension ayrı ayrı 4-factor alpha
> raporluyor** (Profitability + Growth + Safety + Payout, Table VI
> Panel A). HMXZ q5 captures bulgusu QMJ paper'ın **4-factor (Carhart)
> lens**'inden farklı **scope-dependent epistemik düzlem**: HMXZ risk
> premium yorumuna eğilimli (q5 captures); QMJ paper behavioral
> mispricing yorumuna eğilimli (4-factor alpha 66 bps/ay t=11.20 sig).
> Cochrane mathematical equivalence: aynı bulgu iki yorum.
> Wiki için: HMXZ Tablo 4 + QMJ paper Table VI birlikte **complementary
> kanıt**, çelişki değil; [[meta/contradictions]]'a eklenmedi.

### Tablo 5-7 — Bartram-Grinblatt, Penman-Zhu, Ball-GLN
- Benzer pattern: q5 büyük ölçüde span; microcap'te residual alpha
- Spesifik rakamlar paper okuması ile teyit edilebilir

### Tablo 8 — Buffett's Berkshire alpha
- Berkshire excess return spread vs market: significant
- q-factor reduces spread by 56%, alpha 0.64% (t=2.45) — **hala anlamlı**
- **q5 alpha 0.77% (t=2.69)** — q5 ile **tam span EDİLMİYOR**
- Active discretionary value fund alpha kaynağı q5'in ötesinde

### Tablo 10 — Best 20 Active Value Funds
- q5 model 69-89% performans açıklar (specific measurement'a göre)
- Mutual fund average barely beats market; passive index alone yeterli

## "Bu paper'ın sürprizi" — kontrol

> 📝 Plan'da hipotezimiz: **"kısmi redundancy"** (q5 fundamental skorları büyük
> ölçüde açıklar ama tam değil). Paper okuma sonucu:
>
> **Hipotez DOĞRULANDI.** Magic Formula tam span; F-Score microcap dışında
> tam span; V/P tam span; QMJ q5 ile span; Buffett q5'in ötesinde. Bu wiki'nin
> önceki sentezini (B bloğu standalone evidence + combined approach) **değiştirmiyor**,
> **risk premium yorumuna** ekliyor: skorların getirisi büyük ölçüde investment
> + profitability factor exposure'ları üzerinden geliyor.
>
> **Sürpriz** seviyesinde bulgu yok; "Bu paper'ın sürprizi" bölümü açılmadı.
> Eğer ileride post-2018 dönemde yeni bir replikasyon q5 alpha'larını
> sıfırlarsa veya tam tersine artırırsa, bu bölüm sonradan eklenebilir.

## Limitler ve Caveats

- **Sample sonu 2018:** Post-2018 dönem (özellikle 2020-2024 mega-cap tech ve
  COVID volatilite) out-of-sample.
- **q-factor convention monthly rebalance:** Wiki amacı yıllık rebalance ile
  kısmen uyumsuz; F-Score yıllık formation korunmuş ama portfolio test
  monthly.
- **NYSE breakpoint:** Standart q-factor convention; large-cap-only kalibrasyon
  yok. "Big" size partition top-NYSE-ME-tertile demek; S&P 500 / NDX'in tam
  karşılığı değil.
- **Intangibles düzeltmesi yok:** q5 investment factor (I/A) ham total asset
  growth; R&D capitalization yapılmamış. NDX tech-heavy evrene transfer için
  bu yetersizlik açık → Q23.
- **G-Score test EDİLMEDİ:** Paper Mohanram 2005'i kapsamına almamış.
  G-Score'un q5 lens'inde durumu wiki'de bilinmiyor → yeni Q25.
- **Combined stratejiler test edilmemiş:** Li-Mohanram 2019 F+G+V/P+PEG
  combined'leri HMXZ kapsamı dışında. Doğrudan kanıt yok.
- **Mispricing vs risk premium yorumu:** HMXZ explicit risk-tabanlı
  (investment CAPM); paper Piotroski/Mohanram/Frankel-Lee'in mispricing
  yorumuyla **felsefi olarak çelişir**. Wiki bu seçimde taraf tutmaz —
  primum'un gerçekliği yeterli, mekanizma açık soru
  ([[cochrane2011_discount_rates]] #4).

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfa
- [[Magic_Formula]] — Greenblatt 2005/2010 Magic Formula factor entity (academic
  validator: bu paper)

### Bu paperın update ettiği mevcut sayfalar
- [[F_Score]] — q5 lens'inde mikro hariç span; Reported Performance satırı
- [[G_Score]] — yumuşak karın notu: HMXZ kapsamı dışı (test edilmemiş)
- [[comparisons/f_score_vs_g_score]] — methodoloji yeniden-test 3. satır
  (HMXZ q5 lens)
- [[winner_loser_identification]] — paradigmanın boşlukları: q5 lens'iyle
  kısmi span
- [[contextual_fundamental_analysis]] — q-factor çerçevesi içinde
  universe-conditioned scoring durumu
- [[factor_zoo]] — "fundamental scores survive q5?" cevabı
- [[factor_model]] — q5 hiyerarşi katmanı

### V/P de facto wiki referansı (paired pages)
- [[hou_mo_xue_zhang_2020_security_analysis]] (bu sayfa) — V/P methodology
  detayı + q5 alpha sonucu
- [[li_mohanram2019_quality_value]] — V/P ve PEG ile combined yaklaşım

### İlgili paperlar (ingested)
- [[piotroski2000_f_score]] — F-Score origin paper; HMXZ q5 lens replikasyonu
- [[mohanram2005_g_score]] — G-Score origin paper; **HMXZ kapsamı dışı**
- [[li_mohanram2019_quality_value]] — F+G+V/P+PEG combined sentezi
- [[cochrane2011_discount_rates]] — investment CAPM çerçevesinin epistemik temeli
- [[famafrench2015_five_factor]] — FF5 vs q5 paralel ortodoks 5F model
- [[sloan1996_accruals_anomaly]] — accruals anomaly origin; HMXZ kapsamında
- [[novy_marx_2013_gross_profitability]] — **Cycle 23**; HMXZ Tablo 5
  cash-based operating profitability **Cop = Novy-Marx GP/A'dan
  cash-aware evrim** (Ball-GLN 2016 origin; working capital + capex
  çıkarılmış); Profitability zinciri 4. halka empirik validation; Cop
  q-factor alpha 0.69%/ay sig (HXZ 2020 4/4 hayatta kalan). **Çelişki
  değil evrim**: GP/A → Cop methodology iyileşmesi.
  Sloan accruals **doğrudan tek başına test edilmedi** ama Bartram-Grinblatt
  agnostic analysis (§3.5) ve Penman-Zhu fundamental strategies (§3.6)
  accruals signal'lerini içerir; q5 model investment factor (I/A) accruals
  literatürüyle yapısal bağda
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — q5 modelin **I/A factor'ü
  CGS asset growth ölçüsünü kullandığı** ve bu measure'ın geleneksel
  investment ölçüleri (CAPX, PPE, intangibles-adjusted) ile değiştirildiğinde
  HXZ unexplained anomaly sayısının 5/35 → 15-24/35'e çıktığını gösteren
  kanıt [s.3-4]. **HMXZ'nin "q5 = investment CAPM empirical implementation"
  yorumu sorgulanır:** ⚠️ challenged. q5 I/A factor "investment proxy"
  değil, asset growth measure'ın kendisi unique sinyal kaynağı. Detay:
  [[asset_growth_anomaly]] + Q24 partial cevap.
- [[mclean_pontiff_2016_post_publication_decay]] — wiki'de **potansiyel
  felsefi çelişki**: McLean-Pontiff anomaly post-pub decay'i sophisticated
  trader arbitrajına atfeder (mispricing yorumu ima eder); HMXZ q5 model
  anomaly'lerin **risk premium exposure'larıyla** başından beri
  açıklandığını gösterir (mispricing yok). Ama Cochrane (2011) [s.20]
  mathematical equivalence: aynı portföye iki farklı yorum giyebilir.
  Resmî [[meta/contradictions]] entry açılmadı (Cycle 11 kullanıcı kararı
  4 — Hou-Xue-Zhang 2015 q-factor origin paper ingest edildiğinde
  değerlendirilecek). Detay: aşağıda Çelişkiler bölümü.

### Cycle 12 ek (HLZ 2016 ingested)
- [[harvey_liu_zhu_2016_multiple_testing]] — HMXZ q5 alpha'larının
  multiple-testing-corrected durumu: **F-Score q5 microcap t=2.67 BHY
  borderline; Bonferroni insig**. F-Score q5 small/big (t=0.81/0.15)
  klasik düzeyde insig. **Magic Formula q5 alpha t=-0.76, QMJ q5 alpha
  t=0.42 — tümü tüm cutoff'larda insig**. Buffett q5 alpha t=2.69 BHY
  borderline / Bonferroni insig.

### Cycle 13 ek (HXZ 2020 ingested) — HXZ canonical pair
- [[hou_xue_zhang_2020_replicating_anomalies]] — **Paralel HXZ paper**
  (HMXZ Security Analysis dar kapsam 6 fundamental scoring + HXZ
  Replicating Anomalies geniş kapsam 447 individual = **HXZ canonical
  pair**). Replicating Anomalies q-factor model'i 161 sig anomaly
  üzerinde test ediyor: 115 alpha insig at 5%; 46 sig (11 with t > 3).
  Wiki için: HMXZ Security Analysis "fundamental scoring strategies
  q5 ile span" yorumu HXZ Replicating Anomalies'in **geniş empirik
  kapsamıyla pekişiyor**. q-factor model FF15 + Carhart faktörlerini
  büyük ölçüde absorb ediyor [s.24]: RMW (Ope) klasik sig + q-factor
  alpha 0.04% insig; CMA klasik sig + q-factor alpha 0.01% insig;
  UMD klasik sig + q-factor alpha 0.11% insig. q-factor model wiki
  için Faz 3 risk-adjustment baseline. Detay
  [[concepts/anomaly_replication]] aggregate tablosu;
  [[concepts/factor_model]] q-factor performance.

### Cycle 14 ek (Bailey-LdP DSR ingested)
- [[bailey_lopezdeprado_2014_deflated_sharpe]] — HMXZ q5 alpha
  Sharpe ratio'larının DSR-aware raporlanması Faz 3 spec'inde gerekli.
  HMXZ paper'da q5 alpha t-statistic'leri var ama Sharpe explicit yok;
  Faz 3 backtest spec'inde alpha → Sharpe → DSR conversion methodology
  uygulanır. Detay [[concepts/backtest_overfitting]].

### Henüz wiki'de olmayan, doğrudan ilgili paperlar
- Hou-Xue-Zhang (2015) "q-factor model" (Tier 1 #3) — q4'ün origin paperı; HXZ
  2015 ingest edildiğinde q-factor concept sayfası açılma değerlendirmesi
- Hou-Mo-Xue-Zhang (2020 başka paper) — expected growth factor (q5'i q4'ten
  ayıran) origin
- Frankel-Lee (1998) — V/P origin paper (paywall, ingest edilmeyebilir)
- Greenblatt 2005/2010 — Magic Formula origin (Tier 3 #57 kitap)
- Asness-Frazzini-Pedersen 2019 (QMJ) (Tier 1 #6)
- Hou-Xue-Zhang 2020 "Replicating Anomalies" (Tier 1 #18) — paralel
  replication paperı

## Çelişkiler / Tartışmalar

> 📝 HMXZ explicit risk-tabanlı yorumu (investment CAPM, q-factor model) ile
> Piotroski/Mohanram/Frankel-Lee'nin mispricing yorumu **felsefi olarak
> çelişir**. Empirik olarak çelişmez — q5 alpha'ların yakın sıfır olması
> "mispricing yok, risk premium var" yorumunu *destekler* ama "kanıtlamaz"
> ([[cochrane2011_discount_rates]] [s.20] mathematical equivalence).
>
> Wiki için bu **çelişki değil**, **yorum çatallanması**. Strateji tasarımı
> her iki yorumu da kabul ederse aynı portfolio'yu tutar (factor exposure
> alma) — felsefi seçim Faz 3 implementation'ı etkilemez.

## Açık Sorular (bu paperın açtığı / dokunduğu)

- **[Q5 partial-stronger update]** Post-publication decay: F-Score sample
  1972-2018'e uzanırken q5 alpha'lar microcap dışında kayboluyor. Sample-end
  1998 (Piotroski orijinal sample yakın) ile karşılaştırıldığında F-Score "much
  stronger" [s.19 fn 9]. McLean-Pontiff 2016 ingest edildi
  ([[mclean_pontiff_2016_post_publication_decay]]): aggregate %35 decay
  (sig 1%) + sample-end opportunism reddi [Tablo 4]. **HMXZ q5 lens'inde
  decay'in saf bileşeni risk premium evrimi ile birleşik** (q5 risk
  premium değişimi → alpha azalması → "decay" görünümü); McLean-Pontiff
  yorumu (sophisticated trader arbitrage → mispricing reduction → "decay")
  ile mathematical equivalence. Wiki taraf tutmaz; her iki yorum da
  decay-adjusted spread baseline'ı destekler. Detay:
  [[post_publication_decay]] + [[factor_zoo]].
- **[Q15 partial-stronger update]** FF5 vs HXZ4/q5: HMXZ paper Asness QMJ'i
  q-factor reject ama q5 capture ediyor [Tablo 4]; QMJ FF5 ile span edilmediyse
  (literatürde böyle bilinir) bu **q5 expected growth factor'ünün FF5'in
  HML+RMW'unu aştığı** anlamına gelir. **Tam horse race wiki'de hala yok;
  Hou-Xue-Zhang 2015 ingest'i ile teyit.**
- **[Q17 partial-stronger update]** Cochrane #3 — factor count parsimony:
  HMXZ kanıtı q5 5-faktör modelin geleneksel security analysis stratejilerini
  açıklamada yeterli olduğunu gösteriyor → 4-5 faktör parsimony argümanı
  güçleniyor.
- **[Q23 yeni]** q5 model investment factor (I/A) **R&D capitalization
  yapmıyor**; NDX tech-heavy evrene transfer için intangibles-adjusted q5
  versiyonu literatürde var mı? Lev-Sougiannis 1996, Peters-Taylor 2017
  (Tier 2) ingest edildiğinde değerlendirme.
- **[Q24 yeni]** q5 vs FF5 **doğrudan horse race wiki'de hala açık.** HMXZ
  2020 q5 lens'i bireysel security analysis stratejilerini test ediyor ama
  FF5 ile head-to-head karşılaştırma sunmuyor. Hou-Xue-Zhang 2015 q-factor
  origin paperı ingest edildiğinde tam cevap.
- **[Q25 yeni]** **Mohanram G-Score q5 lens'inde test edilmedi** (HMXZ
  kapsamı dışı). G-Score'un growth-side mikrocap residual alpha'sı q5 ile
  span ediliyor mu? Yoksa Mohanram'ın industry-median yapısı q5'in açıklayıcı
  gücünü aşıyor mu? Direct test wiki'de eksik; Tier 2 #45 Freyberger-Neuhierl-
  Weber 2020 nonparametric characteristics testleri kısmi cevap sağlayabilir.

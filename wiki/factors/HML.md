---
type: factor
name: HML
category: value
direction: long_high  # uzun yüksek BE/ME, kısa düşük BE/ME
data_lag_required: "Haziran t-end için Aralık t-1 ME ve fiscal-year-end t-1 BE; ≥6-aylık reporting gap [[famafrench1993_three_factor]] PDF p.8"
rebalance_frequency: annual
universe_tested: ["NYSE/AMEX/NASDAQ ex-financials, 1963-07/1991-12"]
cycle_37_note: "HML size-conditional çift teyit [[papers/fama_french_2008_dissecting_anomalies]] (Cycle 37 ✓) + Israel-Moskowitz 2013 (Cycle 22); FF 2008 [Tablo IV] B/M regression slopes micro 0.23 (t=3.19) + small 0.30 (t=3.41) + big 0.17 (t=1.79) weakest; FF06b [s.15] weaker B/M big-stocks special to post-1962 + US; Israel-Moskowitz 86-yıl size-conditional Q5 5-1 α=3.70% t=1.90 INSIG paralel; vanilla HML reject sertleştirme (Lev-Srivastava 2020 + Israel-Moskowitz + FF 2008 üçlü teyit)"
---

# HML — High Minus Low (Book-to-Market Value Factor)

## Tanım (Fama-French 1993 inşası)

`HML` = (S/H + B/H) / 2 − (S/L + B/L) / 2

Burada `S` ve `B` size kategorileri (NYSE median ME), `L`, `M`, `H` ise BE/ME
kategorileri (NYSE 30/70 percentile breakpoint'leri). Tüm portföyler value-weighted
aylık [[famafrench1993_three_factor]] PDF p.9.

**BE/ME hesaplaması:**
- BE = book equity, fiscal year-end of t-1
- ME = market equity, December-end of t-1
- Sıralama: Haziran t-end'de yapılır, Temmuz t'den Haziran t+1'e kadar tutulur
- 6-aylık minimum reporting gap [[famafrench1993_three_factor]] PDF p.8

**Hariç tutulanlar:** finansal firmalar (yüksek leverage normal); negatif BE'li
firmalar [[famafrench1993_three_factor]] PDF p.8.

## Origin

- İlk paper: [[famafrench1993_three_factor]] (Fama-French 1993)
- Yazarlar: Eugene F. Fama, Kenneth R. French

## Reported Performance Across Studies

| Paper | Dönem | Evren | Mean (ay) | t-stat | Notlar |
|---|---|---|---|---|---|
| [[famafrench1993_three_factor]] | 1963-07 / 1991-12 | NYSE/AMEX/NASDAQ ex-fin | 0.40% | 2.91 | [Tablo 2, PDF p.13] |
| [[famafrench2015_five_factor]] (2x3) | 1963-07 / 2013-12 | NYSE/AMEX/NASDAQ ex-fin | 0.37% | 3.20 | [Tablo 4 Panel A, s.37]; örneklem 22 yıl uzatılmış |
| [[famafrench2015_five_factor]] (2x2) | aynı | aynı | 0.28% | 3.22 | [Tablo 4 Panel A, s.37] |
| [[famafrench2015_five_factor]] (2x2x2x2) | aynı | aynı | 0.30% | 3.43 | [Tablo 4 Panel A, s.37]; joint Size/B/M/OP/Inv kontrolü |
| [[carhart1997_four_factor]] | 1963-07 / 1993-12 | aynı | 0.46% | 3.42 | [Tablo II, s.62] |
| [[lev_srivastava_2020_value_failure]] decade decomposition | 1970-2018 | NYSE+AMEX+NASDAQ all-stocks | (decade-by-decade $1 → end value) | (Figure 1) | 1970s +102%, 1980s +75%, **1990s -10%**, 2007-2018 negative; **1989'dan beri faltering** |
| [[lev_srivastava_2020_value_failure]] adjusted HML | 1970-2018 | aynı | 39 yılın 34'ünde conventional'ı geçer | (Figure 3) | Intangibles-aware adjusted BV methodology; 1980s +186% adj vs +75% unadj; 2010s "reasonably positive" vs negative |
| [[israel_moskowitz_2013_shorting_size_time]] **86-yıl** | 1926-07 / 2011-12 | NYSE+Amex+Nasdaq VW | CAPM α 3.45%/yıl | 2.80 | Full sample [Tablo 1]; 1963-2011 sub-sample α=4.72% t=4.21; 1926-1962 α=0.71% t=0.37 INSIG → premium 1963 sonrası |
| [[israel_moskowitz_2013_shorting_size_time]] **size Q5 (largest)** | 1926-2011 | aynı | 5-1 spread CAPM α 3.70%/yıl | 1.90 | [Tablo 3]; **largest 40% NYSE stocks'ta value premium INSIG**; size Q1 (smallest) α=11.22% t=3.87 ⚠️ size-conditional |
| [[israel_moskowitz_2013_shorting_size_time]] long-only H | 1926-2011 | aynı | CAPM α 2.93%/yıl | 2.40 | [Fig.1 Panel D]; long-only top 30% BE/ME information ratio 0.26 |

_(yeni paperlar ingest edildikçe satır eklenecek)_

> 📝 **Standalone HML primum'u FF93'ten FF15'e güçlü kalır** (1963-91 → 1963-2013;
> mean ~0.40% → ~0.37%/ay). Ancak aşağıdaki "Subsumed by?" satırına bakın —
> HML *5-faktör çerçevesinde* span edilebilir hale gelir.

## Faktör Ailesi İçindeki Yeri

- **Korelasyon ([[famafrench1993_three_factor]] Tablo 2, PDF p.13):**
  - HML ↔ MKT-RF : −0.38 (defansif eğilim)
  - HML ↔ SMB : −0.10 (yaklaşık ortogonal)
- **Subsumed by?** **EVET (FF15 5-faktör çerçevesinde, 1963-2013 ABD örneklemi).**
  [[famafrench2015_five_factor]] Tablo 6 [s.19] HML'in MKT-RF, SMB, RMW, CMA üzerine
  spanning regresyonunda intercept'i:
  - 2×3 inşa: a = **−0.04%, t = −0.47**
  - 2×2 inşa: a = 0.00%, t = 0.01
  - 2×2×2×2 inşa: a = 0.02%, t = 0.23

  Yani 5-faktör baz altında HML'in büyük ortalama getirisi tamamen RMW ve CMA'ya
  pozitif yüklemelerle absorbe ediliyor [s.19]. Mekanik kaynak: HML ↔ CMA
  korelasyonu 0.70 [Tablo 4 Panel C, s.38]. **Ancak** [[famafrench2015_five_factor]]
  yazarları açıkça uyarır: "we caution the reader that it may be specific to this
  sample" [s.4]; pre-1963 ve uluslararası örneklem testi açık → [[meta/open_questions]] Q13.

  Bu redundancy iddiası FF93'teki ortogonal regresyonla (RM-RF üzerine HML
  spanning'i, t = −8.23 [Eq.(1), PDF p.27 - FF93]) **çelişir** çünkü FF15 farklı
  bir RHS faktör seti kullanıyor (RMW + CMA dahil) — kanıtların uyumu için
  [[meta/contradictions]]'a giriş eklendi. Modern factor zoo redundancy testleri
  (Hou-Xue-Zhang 2015, Feng-Giglio-Xiu 2020) wiki'de henüz yok.

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

[[israel_moskowitz_2013_shorting_size_time]] **size partition direct
kanıt** [Tablo 3] (Cycle 22 ek): Size Q5 avg market cap (2011) $36B
≈ S&P 500 üst yarısı; Q4 avg $4.8B Russell Midcap. Wiki S&P 500 / NDX
top 100-500 stocks tam Q4-Q5 spektrumunda. **Bu evrende vanilla HML
α=1.97-3.70 t=1.04-1.90 INSIG**. Size Q1 (smallest) α=11.22% t=3.87
sig — value premium **size-loaded**, large-cap'te yapısal silinme.

Lev-Srivastava 2020 + Israel-Moskowitz 2013 **çift anchor**: vanilla
HML reject; adjusted HML methodology ([[concepts/intangibles_adjusted_accounting]])
zorunlu. NDX (growth-heavy, intangible-heavy) için geleneksel BE/ME
relevance'ı **çift darbe** (size-conditional reject + intangibles
bias). bkz. [[meta/data_gaps]] "R&D capitalization ve intangibles"
ve [[meta/open_questions]] Q1.

## Decay / Post-Publication Performance + Multiple Testing Status

[[mclean_pontiff_2016_post_publication_decay]] aggregate %35 post-pub
decay HML'e uygulanır → decay-adjusted yaklaşık 0.65× in-sample.

[[harvey_liu_zhu_2016_multiple_testing]] HLZ Şekil 3 mark'i:
- **HML (FF93 origin t=2.91, 1963-91):** BHY (3.0) borderline; Bonferroni
  (3.78) **insig**
- **HML (FF15 1963-2013, t=3.20):** BHY sig; Bonferroni borderline

Detay: [[concepts/multiple_testing]] aggregate tablosu;
[[concepts/post_publication_decay]] üç darbe çerçevesi tablosu.

### HML post-2010 performance crisis (Cycle 17 ek — Lev-Srivastava ingested)

[[lev_srivastava_2020_value_failure]] HML decade-by-decade decomposition
[Section 3, Figure 1]:

| Decade | $1 → end (vanilla HML) | Return |
|---|---|---|
| 1970s | $2.02 | **+102%** |
| 1980s | $1.75 | **+75%** |
| **1990s** | **$0.90** | **-10%** |
| 2000-2006 | brief resurgence | tech bubble shorting boost |
| **2007-2018** | (negative) | "yielded negative returns" |

**1989'dan beri faltering** — HML decay'i MP aggregate %35'ten **çok
daha agresif**: vanilla HML 2010s NEGATIVE.

**Iki sebep** [Lev-Srivastava ana tezi]:
1. **Accounting deficiencies (intangibles expensing)**: 1980'lerden
   itibaren intangibles proliferation; book value mismeasurement
2. **Mean reversion slowdown post-2007**: rank correlation glamour
   45-47% → 60%; length of stay value 2.5 → 3.3 yıl

### Adjusted HML alternative inşa (Cycle 17 ek)

[[lev_srivastava_2020_value_failure]] [Section 5-6] **adjusted BV
methodology**:

```
Adjusted BV = reported BV + R&D capital stock + SG&A intangibles capital - amortizations
```

Adjusted HML strategy 39 yılın 34'ünde conventional'ı geçer. Methodology
infrastructure F bloğu 3 ayak (Lev-Sougiannis perpetual inv + Peters-
Taylor θ=30% SG&A allocation + Lev-Srivastava post-2010 application)
ile **wiki için tam hazır**.

**Faz 3 NDX strategy spec'i için:**
- **Vanilla HML reject**; adjusted HML baseline
- Methodology infrastructure: [[concepts/intangibles_adjusted_accounting]]
  3-katmanlı omurga
- Q42 yeni: HXZ R&D-to-market'in Peters-Taylor total intangibles
  versiyonu paralel modern test gerekli

## Implementation Notes

- **Required data:** book equity (Compustat), market equity (CRSP/equivalent),
  share class consolidation, fiscal year-end calendar
- **NYSE breakpoint asimetrisi:** Tüm hisse evreni NYSE median'a göre sıralanır;
  ama NYSE'nin median'ı NYSE/AMEX/NASDAQ tüm hisselerinin median'ından çok daha
  büyüktür. Bu, **Big** kategorisinin tek başına S&P 500 evreninin yaklaşık
  tamamını temsil etmesine neden olabilir. **Saf S&P 500 evreni için HML inşası
  yeniden tanımlanmalı.**
- **Annual rebalance frequency:** orijinal inşada Haziran sonu rebalance, yıllık.

## Bu Faktörün Yumuşak Karnı

- **5-faktör modelinde redundant [[famafrench2015_five_factor]] s.19:** Standalone
  pozitif primum üretmesine rağmen, MKT-RF + SMB + RMW + CMA tarafından span
  edilir. Strateji tasarımında "saf HML exposure" almak yerine RMW + CMA exposure'u
  almak benzer beklenen-getiri kazanımı sağlar (1963-2013 ABD).
- **BE/ME tanımının intangibles-heavy firmalarda bozulması:** Tech firmalarında
  R&D giderleştirilir → book equity yapay olarak düşer → BE/ME yanlı düşük. Bu
  problem [[meta/data_gaps]] "R&D capitalization" satırı ile bağlantılı.
- **Post-2000 / post-2010 value collapse:** [[lev_srivastava_2020_value_failure]]
  (Cycle 17 ingested) explicit kanıt: 1989'dan beri faltering, 2010s
  NEGATIVE returns. Decade-by-decade decomposition + 2 mekanizma
  (intangibles + mean reversion slowdown) + adjusted methodology
  39/34 yıl. Vanilla HML reject; adjusted HML baseline.
- **NYSE breakpoint asimetrisi → large-cap-only evrende SMB ile birlikte HML
  kararsızlığı.** Yukarıdaki Implementation Notes'a bakın.

## İlgili

- [[famafrench1993_three_factor]] — origin paper
- [[famafrench2015_five_factor]] — HML'in 5-faktörde redundant olduğu kanıt
- [[SMB]] — kardeş size faktörü
- [[MKT_RF]] — kardeş market faktörü
- [[RMW]], [[CMA]] — HML'i span eden iki yeni faktör (FF15)
- [[harvey_liu_zhu_2016_multiple_testing]] — HML multiple-testing-corrected
  durumu (FF93 borderline / FF15 BHY sig)
- [[mclean_pontiff_2016_post_publication_decay]] — HML post-pub decay
  aggregate %35 multiplier
- [[hou_xue_zhang_2020_replicating_anomalies]] — HML book-to-market
  (Bm) **klasik 0.59% (t=2.84) sig; q-factor alpha 0.18% (t=1.15)
  insig** [s.25] — q-factor I/A factor HML'i span ediyor; HML factor
  exposure proxy olarak kullanılır, "saf alpha" değil
- [[UMD]] — Carhart 4F'de HML'le birlikte kullanılan momentum faktörü
- [[F_Score]] — high-BM (value) evren içinde diferensiyel filtre — saf HML
  üstü stock selection (Piotroski 2000)
- [[value_premium]] — kavramsal sayfa; Cycle 17 yapısal zenginleşme
  (Lev-Srivastava 3. yorum boyutu intangibles measurement-error
  mispricing)
- [[winner_loser_identification]] — HML uzun bacağı içinde rafine seçim paradigması
- [[factor_model]] — multi-factor asset pricing kavramı
- [[lev_srivastava_2020_value_failure]] — **post-2010 value crisis
  anchor (Cycle 17)**; HML decade-by-decade decomposition; adjusted HML
  39/34 yıl conventional'ı geçer; vanilla HML reject Faz 3 baseline
- [[lev_sougiannis_1996_rd_capitalization]] — F bloğu #1 (Cycle 15);
  R&D-only adjusted BV methodology origin
- [[peters_taylor_2017_intangible_capital]] — F bloğu #2 (Cycle 16);
  total intangible capital generalization
- [[concepts/intangibles_adjusted_accounting]] — F bloğu hub; 3
  ayak methodology infrastructure

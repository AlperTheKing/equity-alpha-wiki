---
type: concept
name: winner_loser_identification
related_papers: [[piotroski2000_f_score]], [[stambaugh_yuan_2017_mispricing_factors]]
---

> 📝 **Cycle 39 ek**: Composite mispricing scoring methodology Stambaugh-Yuan paralel [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; F-Score/G-Score/QMJ binary/composite scoring → Stambaugh-Yuan continuous composite 11-anomaly 2-cluster evolution; B bloğu winner-loser identification core kavramı + Stambaugh-Yuan mispricing-aware refinement (sentiment-driven short-leg asymmetry kanıt long-only methodology için kritik wiki amaç evrenleri tercih).

# Winner-Loser Identification — Faktör Uzun-Bacağı İçinde Diferensiyel Skor

## Tanım

**B bloğunun core kavramı.** Bir style faktörünün (value, quality, growth, low-vol)
uzun bacağında bulunan firmaların *tamamına* uzun gitmek yerine, **uzun bacak
içinde "future winners"'ı "future losers"'tan ayıran** ek bir skor uygulamak.

[[piotroski2000_f_score]] [s.4-5]: "less than 44% of all high BM firms earn
positive market-adjusted returns" — yani saf HML uzun bacak başarısı az sayıda
güçlü firmaya **bağlıdır** ve çoğu firma underperform eder. Bu **diferensiyel
fırsat**: uzun bacak içinde rafinasyon ek primum üretir.

## Genel paradigma

```
Style faktörü uzun bacağı ──► n firma                  (örn. high-BM ⇒ 14K firm-year)
                              │
                              ▼
                          Diferensiyel skor uygulaması  (örn. F-Score)
                              │
            ┌─────────────────┼─────────────────┐
            ▼                                   ▼
    "Strong" alt-grup                    "Weak" alt-grup
    (top scoring)                        (bottom scoring)
    Long pozisyon                        Short / kaçınma
```

Kazanç:
- Uzun bacak içinde *additional* spread (örn. F-Score için +0.230 ekstra
  market-adjusted [[piotroski2000_f_score]] [Tablo 3, s.16])
- **Distribution shift:** sol kuyrukta ekstrem negatif getiriler azalır
  ([[piotroski2000_f_score]] [Tablo 3 Panel A, s.16] 10. yüzdelik -0.781 → -0.462,
  +0.319 düzelme)

## Wiki'deki winner-identification skorları (haritalama)

| Style faktörü uzun bacağı | Diferensiyel skor | Origin paper | Wiki sayfası |
|---|---|---|---|
| High-BM (value) | F-Score | [[piotroski2000_f_score]] | [[F_Score]] |
| Low-BM (growth) | G-Score | [[mohanram2005_g_score]] | [[G_Score]] |
| Combined quality+value | F&V/P, G&V/P, F&NEGPEG, G&NEGPEG | [[li_mohanram2019_quality_value]] | (entity sayfası açılmadı, bkz. [[fundamental_scoring]]) |
| **All-cap quality (4 dimension)** | **QMJ** | [[asness_frazzini_pedersen_2019_qmj]] **(Cycle 19)** | [[QMJ]] |
| **Quality at a Reasonable Price** | **QARP** = quality × n − P/B | [[asness_frazzini_pedersen_2019_qmj]] Section 7 **(Cycle 19)** | (entity sayfası açılmadı, bkz. [[concepts/value_premium]] 4. yorum boyutu) |
| **All-universe forensic flag** (filter, signal değil) | **M-Score** | [[beneish_1999_m_score]] **(Cycle 18)** | [[M_Score]] |
| All-universe distress | Z-Score / O-Score | (sonra) Altman/Ohlson | _(boş)_ |
| All-universe valuation gap | V/P ratio | (sonra) Frankel-Lee 1998 | _(boş)_ |

> 📝 **Cycle 18 ek**: M-Score satırı winner-loser identification
> paradigmasında **filter olarak** konumlanır — signal olarak değil.
> Beneish 1999 forensic detection paper, return prediction değil;
> M-Score yüksek olanlar evrenden çıkarılır (manipulators eleyen
> filter), sonra F-Score / G-Score / V/P winner-loser ranking
> uygulanır. Epistemik düzlem ayrımı: F-Score / G-Score = winner-
> loser identification (cross-section); M-Score = forensic detection
> (binary classification).

> 📝 **Bu wiki'nin amacı için en doğal yapı:** S&P 500 / Nasdaq 100 evreninde
> belirli bir style anchor'a (örn. Nasdaq 100 = growth-heavy, S&P 500 = mixed)
> uygun **diferensiyel skor** uygulamak. Pure ham faktör spread'i strateji
> hipotezimiz değil — *style universe içinde winner-loser ayrımı*.

## Methodolojik ortak özellikler

1. **Fundamental tablo verisi:** Skorlar sadece raporlanan finansal verilerden
   üretilir; analyst forecast / sentiment / fiyat momentum dahil değil
   ([[piotroski2000_f_score]] high-BM firmalar için "neglected by analysts" notu
   [s.5])
2. **Annual rebalance:** Çoğu yıllık fiscal year-end veriyle sıralama
3. **Composite + binary or ranked:** Tek-değişken yerine multiple-signal toplam
4. **Universe-conditioned:** Sinyaller anchor evrenin karakteristiğine göre
   yorumlanır — örn. F-Score "yüksek leverage = kötü" yaklaşımı sadece distressed
   evrende sağlam ([[contextual_fundamental_analysis]] kavramı)

## Bu paradigma için empirik kanıt

| Skor | Spread (within long-leg) | Sample | Kaynak |
|---|---|---|---|
| F-Score (high-BM) | High-Low = +0.230 yıllık market-adj | 1976-96 COMPUSTAT | [[piotroski2000_f_score]] [Tablo 3, s.16] |
| G-Score (low-BM) | High-Low = +0.212 yıllık size-adj | 1979-99 COMPUSTAT | [[mohanram2005_g_score]] [Tablo 4, s.15-16] |
| G-Score large-cap | +0.198 sig 1% | aynı | [[mohanram2005_g_score]] [Tablo 5 Panel A, s.17] |
| G-Score hi-tech | +0.178 | aynı | [[mohanram2005_g_score]] [Tablo 5 Panel D, s.20] |
| F-Score (continuous, all-firms) | Q5−Q1 = +7.44% size-adj | 1973-2012 NYSE/AMEX/NDQ | [[li_mohanram2019_quality_value]] [Tablo 2, s.15-16] |
| G-Score (continuous, all-firms) | Q5−Q1 = +6.06% size-adj | aynı | [[li_mohanram2019_quality_value]] [Tablo 2, s.15-16] |
| F & V/P combined | +17.94% | aynı | [[li_mohanram2019_quality_value]] [Tablo 4, s.17-18] |
| G & V/P combined | **+21.45%** | aynı | [[li_mohanram2019_quality_value]] [Tablo 4, s.17-18] |

> 📝 **Value vs. growth dual paradigm:** F-Score ve G-Score paralel mimicking
> tasarımlar — anchor evrenler farklı (high-BM vs. low-BM), spread büyüklükleri
> benzer (~21-23% headline). Bu, "winner-loser identification" çatısının her iki
> style anchor'da çalıştığı kanıtıdır. **Methodoloji farkı:** F-Score "kendi
> geçmişine değişim" (Δ-based), G-Score "endüstri-medyana göre level" — yazarlar
> farklı tasarım seçimleri yapmış (Mohanram 2005 [s.8] industry-relative
> yaklaşımını Beneish-Lee-Tarpley 2001 contextual çatısına dayandırır).

## Bu paradigmanın boşlukları

- **Orta-BM (BM-Q3) firmalar:** F-Score sinyalleri distressed firma için
  kalibre, G-Score sinyalleri growth firma için kalibre — orta-BM hibrit
  firmalarda ikisi de uygun değil.
  _Li-Mohanram (2019) [[li_mohanram2019_quality_value]] partial update [Tablo 6, s.20-21]:_
  Combined F&V/P medium-BM'de 12.87%, F&NEGPEG medium-BM'de 11.31% spread
  (vs growth/value uçlarında 13-19% aralığı). **Combined yaklaşım orta-BM
  gap'i kapatmıyor, sadece azaltıyor** — F ve G'nin anchor evren ayrımı
  korunuyor; orta-BM hibrit firmalar için doğrudan kalibrasyon yok. Bu boşluk
  hala açık; HXZ q-factor model veya all-universe forensic skorlar (Beneish
  M-Score) ile kapatılabilir.
- **Post-publication decay:** Orijinal F-Score (+23%) ve G-Score (+21.2%)
  spread'leri Li-Mohanram (2019) modern replikasyonunda (1973-2012, continuous,
  all-firms) +7.44% ve +6.06%'ya düşüyor [[li_mohanram2019_quality_value]]
  [Tablo 2, s.15-16]. Sebep multi-faktörlü (sample uzatma + universe genişlemesi
  + methodology revision); McLean-Pontiff (2016) ingest'iyle decay component
  ayrıştırılacak.
- **q-factor model lens'inde kısmi span:**
  [[hou_mo_xue_zhang_2020_security_analysis]] [Tablo 2, s.18-19] q5 model
  F-Score'u microcap hariç span ediyor (q5 alpha small/big = 0.10%/0.03%
  insig; mikrocap = 0.33% sig). **Yani fundamental scoring'in standalone
  alpha kaynağı large-cap'te sınırlı** — getirinin büyük kısmı investment
  + profitability factor exposure'ları üzerinden geliyor. Strateji tasarımı
  için marjinal değer: (a) microcap residual alpha (wiki amacı için irrelevant,
  large-cap-only), (b) uygulama kolaylığı (binary/continuous skor < factor
  model implementation), (c) active discretionary fund alpha kaynağı (Buffett
  q5 ile span edilmiyor [Tablo 8, HMXZ]).
- **G-Score q5 lens'inde test edilmedi:**
  [[hou_mo_xue_zhang_2020_security_analysis]] paperı Mohanram G-Score'u
  kapsamına almamış. F-Score patternin (mikrocap hariç q5 ile span)
  G-Score için tekrarlanırlığı doğrulanmamış → Q25.
- **Forensic filter eksikliği — KAPANDI Cycle 18:** Winner-loser
  identification paradigmasında F-Score / G-Score / Magic Formula
  *fundamental* winner-loser ayrımı yapar ama **manipulation
  detection yapmaz**. Yüksek skor alan firmalar arasında GAAP-violation
  manipulators olabilir (false positive winner identification).
  Cycle 18'de [[beneish_1999_m_score]] M-Score forensic filter
  olarak entegre edildi: paradigmaya **ek katman** olarak eklenir
  (filter, signal değil); F & M / G & M screen-and-rank combined
  yaklaşım Faz 3 design (Q9 partial cevap; Q45 value-trap-avoidance
  filter ile birlikte).
- _(diğer boşluklar gelecek ingestlerde eklenecek)_

## Bu wiki'nin strateji tasarımına spesifik implikasyon

Faz 3 strateji tasarımı **winner-loser identification çerçevesi içinde** kalır:
- **S&P 500 stratejisi:** "value-tilt anchor" (high-BM benzer evren içinde) +
  F-Score benzeri diferensiyel skor (large-cap'e adapte edilmiş — F-Score
  large-cap'te zayıf [[piotroski2000_f_score]] [Tablo 4, s.19], yapısal
  değişiklik gerek)
- **Nasdaq 100 stratejisi:** "growth anchor" + G-Score benzeri diferensiyel
  skor — Mohanram 2005 large-cap'te güçlü [[mohanram2005_g_score]] [Tablo 5
  Panel A, s.17] ve hi-tech'te explicit pozitif [Tablo 5 Panel D, s.20] →
  **NDX'e doğrudan transfer için kanıt en güçlü adaylardan**
- Her iki tarafta **ham factor exposure (HML, RMW) değil, fundamental skoru
  evren-koşullu uygular**
- **Methodoloji seçimi (Δ-based vs. industry-median):** S&P 500 mixed evrende
  industry-median (sektör çeşitliliği yeterli); Nasdaq 100'de sektör çeşitliliği
  zayıf → industry-median noise riski (bkz. [[meta/open_questions]] Q19)

## Limitler

- **Anchor evrene bağımlılık:** F-Score sadece high-BM'de çalıştı; G-Score sadece
  low-BM. **All-universe** uygulama (örn. tüm S&P 500'e tek skor) zayıf çünkü
  sinyal yorumu evren bağlamına bağlı
- **Diferensiyel spread'in primum mu yoksa anomaly mi olduğu açık
  ([[piotroski2000_f_score]] [s.4-5]):** mispricing yorumu ama Cochrane #4 sorusu
  ([[cochrane2011_discount_rates]]) — wiki bu felsefi seçimi tutmaz, strateji
  spread'i kullanır
- **Survivorship + delisting:** çoğu paper basit delisting=0 varsayımı kullanır;
  modern replikasyonlar CRSP-method'la düzeltir

## İlgili paperlar (ingested)

- [[piotroski2000_f_score]] — paradigmasının prototypal örneği (high-BM/value-side)
- [[mohanram2005_g_score]] — paralel growth-side uygulaması (low-BM); industry-
  median methodolojisi ile contextual analysis çatısı
- [[li_mohanram2019_quality_value]] — F+G head-to-head + V/P/PEG ile combined;
  paradigmamn modern replikasyonu ve quality+value sentezi
- [[beneish_1999_m_score]] — **forensic filter Cycle 18**; winner-loser
  paradigmasına ek katman (filter, signal değil); manipulator/non-
  manipulator binary classification; 8-bileşenli M-Score (5 sig + 3 insig)
- [[asness_frazzini_pedersen_2019_qmj]] — **all-cap quality Cycle 19**;
  winner-loser paradigmasında **signal olarak** (M-Score filter ≠ QMJ
  signal); 22 measure → 4 dimension z-score composite; Q2 fully-answered
  ANCHOR (large-cap quality vs value); QARP framework Li-Mohanram F&V/P
  + G&V/P combined paradigm Asness paralel
- [[israel_moskowitz_2013_shorting_size_time]] — **Cycle 22**;
  "**large-cap'te hangi anomaliler hayatta?**" anchor: 86-yıl US sample
  + 5×5 size×value/momentum decomposition; vanilla HML largest 40%
  NYSE stocks'ta INSIG (size Q5 5-1 α=3.70% t=1.90 vs Q1 α=11.22%
  t=3.87); UMD size-invariant + long-only Q5 winners α=3.92% t=3.83
  sig; SMB 86-yıl CAPM α=2.05% t=1.72 INSIG. Wiki amaç evrenleri
  (S&P 500 + NDX top 100-500) Q4-Q5 spektrumunda → **standalone vanilla
  BE/ME value reject; long-only momentum actionable; quality × value
  composite (F&V/P + G&V/P + QARP) anchor**.
- [[novy_marx_2013_gross_profitability]] — **Cycle 23**; **value
  premium uzun bacağı içinde profitability refinement** anchor —
  standalone GP/A signal-as-winner; **Fortune 500 strategy** (top 500
  largest non-financial) combined GP/V rank-based 0.62%/ay Sharpe 0.74
  ⭐ wiki S&P 500 strategy spec direct empirik altyapı; profitability
  premium **size-invariant** (Israel-Moskowitz HML size-conditional
  paterninin TERSİ); GP/A primary value-side alternative (vanilla HML
  reject sonrası); Profitability zinciri origin (Sloan zinciri paralel'i).
- [[comparisons/f_score_vs_g_score]] — head-to-head karşılaştırma sayfası

## İlgili paperlar (henüz ingest edilmedi)

- Frankel-Lee (1998) — V/P ratio (Tier 1 #8)
- Lakonishok-Shleifer-Vishny (1994) — value premium kavramsal temeli (Tier 1 #7)
- Beneish-Lee-Tarpley (2001) — M-Score → return prediction direct
  evidence (paywall, hala eksik)

## İlgili kavramlar

- [[fundamental_scoring]] — winner-loser identification skorlamanın araçsal yönü
- [[contextual_fundamental_analysis]] — sinyal yorumu evren bağlamına göre
  değişir
- [[earnings_quality]] — winner identification'da en güçlü tek-boyut
- [[value_premium]] — F-Score'un ortağı olduğu style premium

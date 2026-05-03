---
type: concept
name: contextual_fundamental_analysis
related_papers: [[piotroski2000_f_score]]
---

# Contextual Fundamental Analysis — Sinyal İşaretlerinin Evren-Bağımlı Yorumu

## Tanım

Aynı finansal sinyalin (örn. yüksek leverage, pozitif accrual, agresif investment)
**implication'ı evrenin karakteristiğine göre değişir** prensibi. Bir sinyali
"good/bad" olarak işaretlemek için **firma bağlamı** (financially distressed mi,
healthy mı, growth mu, mature mu) bilinmeli.

[[piotroski2000_f_score]] [s.7] yazarın açık formülasyonu:

> "It is important to note that the effect of any signal on profitability and
> prices can be ambiguous. In this paper, the stated ex ante implication of each
> signal is conditioned on the fact that these firms are financially distressed
> at some level."

[[mohanram2005_g_score]] [s.8] paralel formülasyon — *industry-relative* contextual:

> "all signals used in this paper, will be based on industry contextual
> information, consistent directly with Soliman (2003) who illustrates the
> importance of industry adjustment in Dupont analysis, and indirectly with
> Beneish, Lee and Tarpley (2001) who highlight the importance of context in
> fundamental analysis."

> 📝 **İki contextual yaklaşım:**
> - **Universe-conditioned (Piotroski):** F-Score sinyalleri sadece high-BM
>   evrende kalibre — sinyal işaretleri evren karakteristiğine göre
> - **Industry-relative (Mohanram):** G-Score sinyalleri industry-median'a göre
>   level — peer-group içinde diferensiyel ölçüm
> Bu iki yaklaşım rakip değil, complementary; modern uygulamalarda ikisi
> birlikte kullanılır.

Örnek: yüksek leverage **financially distressed firma için** = kötü işaret
(funding stress sinyali); ama **growth firma için** = nötr veya iyi (Modigliani-
Miller tax shield, agency cost reduction). [[piotroski2000_f_score]] [s.7]:
"For financially distressed firms, the negative implications of increased
leverage seem more plausible than the benefits."

## Bu wiki için neden önemli

**B bloğunun core methodological prensibi:**

- F-Score signal işaretleri **sadece high-BM evrende** kalibre ([[piotroski2000_f_score]]
  [s.7])
- Mohanram G-Score (ingest beklemede) **sadece low-BM evrende** kalibre olacak
- Ham faktör model'i (FF93/FF15) tüm evrene tek bir β/h slope ile yaklaşır;
  contextual analysis ise **alt-evren bazlı yeniden parametrize**

Wiki'nin amacı için (S&P 500 / Nasdaq 100 large-cap evrenleri) bu prensip kritik:
- S&P 500 = mixed (value + growth + quality karışık) → F-Score sinyallerini
  doğrudan uygulamak yanlış
- Nasdaq 100 = growth-heavy → F-Score'un "yüksek leverage = kötü" işareti
  growth firmalarda doğru olmayabilir
- Sektör bağlamı: tech firma için yüksek R&D = iyi; mature manufacturer için
  yüksek capex = nötr; finans firma için yüksek leverage = normal

## Sinyal yorumu örnekleri

| Sinyal | Distressed (high-BM, F-Score) | Growth (low-BM, G-Score) | Sektör-bağımlı (örn. finans) |
|---|---|---|---|
| Δleverage > 0 | KÖTÜ (funding stress) [F_ΔLEVER] | G-Score'da bileşen yok — growth firmlarda büyüme finansmanı için NÖTR-İYİ | NORMAL (regulated) |
| Equity issuance | KÖTÜ (negative signal Myers-Majluf) [F_EQ_OFFER] | G-Score'da bileşen yok — growth firmlarda NÖTR (growth funding) | NORMAL |
| Pozitif accrual (NI > CFO) | KÖTÜ (Sloan) [F_ACCRUAL=0] | KÖTÜ aynı (G3 bileşeni; signal yönü aynı, eşik *industry-median* değil firm-level) | DİKKAT (loan loss reserves) |
| Yüksek R&D / assets | F-Score'da bileşen yok | İYİ (G6 bileşeni; conservatism → hidden intangible) | N/A (R&D 0 olabilir) |
| Yüksek capex / assets | F-Score'da bileşen yok | İYİ (G7 bileşeni; future growth proxy) | N/A |
| Yüksek advertising / assets | F-Score'da bileşen yok | İYİ (G8 bileşeni; conservatism) | N/A |
| Düşük earnings varyansı | F-Score'da bileşen yok | İYİ (G4 bileşeni; naive extrapolation hedge'i) | DİKKAT (regulated stable) |
| Düşük sales growth varyansı | F-Score'da bileşen yok | İYİ (G5 bileşeni) | DİKKAT |
| ROA > 0 | İYİ (F_ROA, level kontrol) | NÖTR — G-Score *industry-relative* level (G1) ister; level pozitif olsa da industry-median altındaysa 0 | DİKKAT |
| ΔROA > 0 | İYİ (F_ΔROA) | G-Score'da bileşen yok — growth-firma trendi gürültülü, level + stability daha bilgilendirici | DİKKAT (regulatory cycle) |
| Yüksek asset growth | F-Score'da bileşen yok | DİKKAT — capex high (G7=1) iyiyken total asset growth Cooper-Gulen-Schill 2008 anomalisi olarak negatif sinyal olabilir; G-Score doğrudan ele almıyor | NORMAL |

> 📝 **F-Score vs. G-Score sinyal kümeleri kısmen **örtüşmez**:**
> - F-Score: leverage / liquidity / equity issuance odaklı (distressed firma
>   sinyalleri)
> - G-Score: R&D / capex / advertising / stability odaklı (growth firma
>   sinyalleri)
> - **Ortak çekirdek:** ROA / CFO / accruals (G1, G2, G3 ↔ F_ROA, F_CFO,
>   F_ACCRUAL) — 3 sinyal her iki skorda da, ama F-Score firm-level threshold
>   ("sıfırdan büyük mü?"), G-Score industry-median.

## Methodolojik yaklaşımlar

### 1. Universe-conditioned scoring (Piotroski yöntemi)

Bir tek-style anchor (örn. high-BM) seçip o evren içinde sinyalleri kalibre et.
[[piotroski2000_f_score]] çözümü. **Eşik firm-level** (örn. ROA > 0).

**Avantaj:** Sinyal yorumu net; kalibrasyon transparent.
**Dezavantaj:** Anchor evren dışına transfer edilemez; her evren için ayrı skor
(F + G + ...).

### 1b. Universe-conditioned + industry-relative (Mohanram yöntemi)

Universe-conditioned'in genişletilmiş hali: anchor evren (örn. low-BM) içinde
**industry-median** (2-digit SIC) ile karşılaştırma. [[mohanram2005_g_score]]
[s.8] çözümü.

**Avantaj:** Sektörel baseline farkları (örn. hi-tech R&D yüksek, finans R&D 0)
nötrlenir; industry-relative level bilgisi düzeyde sinyal verir.
**Dezavantaj:** **Az sayıda firma içeren evrenlerde (örn. NDX 100-stock)
industry-median noise'lu** — peer-group az gözlemden hesaplanır. Sektör
sınıflandırma seçimi (2-digit SIC vs. GICS Level-3 vs. evren-içi median) kritik
hale gelir → bkz. [[meta/open_questions]] Q19.

### 1c. Quality × Value cross-product (Li-Mohanram yöntemi)


Universe-conditioned quality skoru (F-Score veya G-Score) + value-tabanlı skor
(V/P, NEGPEG) **kesişimi**: long top-quintile-of-both, short bottom-quintile-
of-both. [[li_mohanram2019_quality_value]] [s.13] çözümü.

**Avantaj:** Quality (F, G) ile value (V/P, NEGPEG) **negatif korelasyon**
[[li_mohanram2019_quality_value]] [Tablo 3, s.16] → iki ortogonal sinyal
kaynağı → kombinasyon büyük getiri artışı (G&V/P 21.45% vs G-Score-only
6.06%; F&V/P 17.94% vs F-Score-only 7.44% [Tablo 4, s.17-18]).
**Dezavantaj:** (1) value-skorlar kendi noise/error profili ekler (V/P
cross-sectional earnings forecast'ine bağlı); (2) combined portföy boyutu
küçülür (~43-85 firma/yıl) → trading capacity sınırlı; (3) optimal weighting
yapılmamış (Li-Mohanram simple intersection); factor analysis veya ML
weighting alternatifi açık.

### 2. Sektör nötrleştirme

Her sektör içinde sıralamak — sektörün baseline'ından sapma. [[famafrench2015_five_factor]]
yapmaz; modern uygulamalarda yaygın (örn. AQR multi-factor).

**Avantaj:** Tek-evren içinde sektörel asimetrileri yumuşatır.
**Dezavantaj:** Sektör tanımının sübjektifliği (GICS Level 1 mi 4 mü?); küçük
örneklemde sektör başı az firma.

### 3. Conditional signals (multivariate)

Her sinyali firma karakteristiklerine göre re-yorumla. Örn. firmaya bir
"distress score" ata, sinyal işaretini distress score'a göre flip et.
Beneish-Lee-Tao (2001), Beneish-Lee-Nichols (2013) bu yaklaşıma yakın.

**Avantaj:** Tek-skor multi-evrene transfer edilebilir.
**Dezavantaj:** Karmaşık; overfitting riski; transparency düşük.

## Bu wiki'de mevcut kanıt

- [[piotroski2000_f_score]] — universe-conditioned (high-BM only) yaklaşımı;
  sinyaller distressed firma kontekstinde kalibre [s.7]
- [[mohanram2005_g_score]] — universe-conditioned (low-BM only) **+
  industry-relative** yaklaşımı; sinyaller growth firma kontekstinde + endüstri
  peer'larına göre kalibre [s.8]; Soliman 2003 ve Beneish-Lee-Tarpley 2001
  atıflarıyla gerekçelendirilmiş

> 📝 **Beneish-Lee-Tarpley (BLT) 2001** placeholder işaretli kalır — paper Tier
> listesinde değil, paywall (RAST 2001). Mohanram-Li referansları üzerinden
> dolaylı zenginleşir; ileride Beneish-Lee-Nichols 2013 (Tier 3 #46) ingest'iyle
> kavramsal arka plan açıklanabilir.

## Bu wiki'nin strateji tasarımına spesifik implikasyon

S&P 500 ve Nasdaq 100 evrenleri için:

1. **Tek-skor all-universe yaklaşımı RİSKLİ** — sinyal yorumu evren bağlamına
   göre değişir; mixed evrene uygulanan tek skor "ortalama" davranışı yakalar
   ama uç-firma türlerini kaçırır.
2. **İki paralel skor (S&P 500 ve Nasdaq 100 için ayrı)** doğal seçim:
   - **S&P 500 anchor** = mixed/value-biased → F-Score-benzeri ama large-cap
     adaptasyonu (sektör nötr + universe-spesifik breakpoint)
   - **Nasdaq 100 anchor** = growth-biased → G-Score-benzeri
     ([[mohanram2005_g_score]] doğrudan kanıt, large-cap'te de güçlü [Tablo 5
     Panel A, s.17])
3. **Sektör nötrleştirme** her iki tarafta da default — finans/utility/real
   estate sektörlerinin baseline farkı için.
4. **Industry-median noise:** Mohanram 2-digit SIC kullanıyor; **NDX 100-stock
   evrende sektör çeşitliliği zayıf** → endüstri peer-group az gözlemden
   hesaplanır, median noise'lu olur. Çözüm adayları:
   - GICS Level-3 (rafine ama az gözlem)
   - Universe-içi median (sektörsüz)
   - Hibrit: GICS-3 + min-n eşiği altında universe-median fallback
   → bkz. [[meta/open_questions]] Q19

## q-factor model çerçevesinde universe-conditioned scoring

[[hou_mo_xue_zhang_2020_security_analysis]] q5 model lens'inde universe-conditioned
fundamental skorların nasıl ele alındığına yeni bir bakış sağlar:

- **Universe-conditioning skorun standalone alpha'sını korur ama q5 risk
  premium'larını "kanal" olarak kullanır:** F-Score'un getirisinin büyük
  kısmı ROE factor exposure'u (q5'in 4. faktörü) üzerinden geliyor [Tablo 2,
  s.18-19].
- **Investment CAPM yorumu vs mispricing yorumu:** Piotroski/Mohanram'ın
  "context-aware sinyal kalibrasyonu mispricing yakalar" tezinin tersi olarak
  HMXZ "context-aware sinyaller risk premium proxy'si" yorumunu sunar.
- **Wiki için tarafsız çıkarım:** Universe-conditioning **uygulama düzeyinde**
  değerini koruyor (skor yorumu net, simple implementation); **mekanizma
  düzeyinde** çıkarım açık soru. Strateji tasarımı her iki yorumu da kabul
  edip aynı portfolio'yu tutar (factor exposure alma).

## İlgili paperlar (ingested)

- [[piotroski2000_f_score]] — kavramın ana referansı; F-Score sadece high-BM'de
  kalibre [s.7]; eşik firm-level
- [[mohanram2005_g_score]] — paralel growth-side; eşik industry-median
  (2-digit SIC, contemporaneous low-BM peers); Soliman 2003 + Beneish-Lee-
  Tarpley 2001 contextual çatısına dayandırılmış [s.8]
- [[li_mohanram2019_quality_value]] — quality × value cross-product methodology;
  F-Score continuous-rank revision (all-firms) + G-Score FF1997 48-industry
  revision; combined intersection paradigm
- [[hou_mo_xue_zhang_2020_security_analysis]] — q-factor / q5 model çerçevesinde
  universe-conditioned scoring'in risk premium yorumu; F-Score microcap hariç
  span; G-Score test edilmemiş

## İlgili paperlar (henüz ingest edilmedi)

- Beneish (1999) M-Score — all-universe forensic, ama distressed firmalarda
  daha güçlü (Tier 1 #15)
- Beneish-Lee-Nichols (2013) — M-Score conditional analizi (Tier 3 #46)
- Beneish-Lee-Tarpley (2001) — "Contextual Financial Statement Analysis" (paywall,
  Tier listesi dışı; Mohanram s.5 atıf veriyor)
- Soliman (2003) — DuPont decomposition + industry adjustment (Mohanram s.8 atıf)
- Lev-Thiagarajan (1993) — 12 fundamental signals; conditional yorumu yapan
  early paper

## İlgili kavramlar

- [[winner_loser_identification]] — contextual analysis bu identification'ın
  metodolojik altyapısı
- [[fundamental_scoring]] — universe-conditioning skorlamanın kritik tasarım
  ekseni
- [[earnings_quality]] — earnings quality değerlendirmesinde de evren-bağımlılık
  (örn. mature vs. growth)

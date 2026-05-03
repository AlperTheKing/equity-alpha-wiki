---
type: concept
name: post_publication_decay
related_papers: [[mclean_pontiff_2016_post_publication_decay]], [[harvey_liu_zhu_2016_multiple_testing]], [[cochrane2011_discount_rates]], [[hou_mo_xue_zhang_2020_security_analysis]], [[li_mohanram2019_quality_value]], [[ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]
---

> 📝 **Cycle 38 ek**: Dört darbe sentez tablosu Cop satırı 4/4 hayatta kalan formal origin [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓; HMXZ Tablo 5 + HXZ 2020 Replicating Cop dört darbe 4/4 hayatta kalan empirical validation; Profitability zinciri 4. halka Cop standalone origin paper anchor + tangency Sharpe 4F+Cop=1.67 [Tablo 8] direct empirical evidence.

> 📝 **Cycle 39 ek**: Stambaugh-Yuan post-publication decay cross-cite [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; paper [s.2] explicit "consistent with the evidence of McLean and Pontiff (2015), who observe that following an anomaly's academic publication, there is greater trading activity in the anomaly portfolios, and anomaly profits decline"; sentiment-driven mispricing interpretation MP post-publication decay paterni paralel + arbitrage asymmetry short-leg sentiment-driven mispricing decay channel; sample 1967-2013 post-2013 11 yıl OOS (Q81 yeni modern replikasyon).

# Post-Publication Decay — Yayım Sonrası Anomali Erozyonu

> 📝 **Wiki'nin epistemik omurgası.** A-B-C-D blokları boyunca ingest edilen
> tüm anomaly / faktör / komposit skor paperlarında "post-publication
> performans?" sorusu bu sayfada cevaplanır. Anchor referans:
> [[mclean_pontiff_2016_post_publication_decay]].

## Tanım

Bir akademik paperda raporlanan cross-sectional return predictor'in, **yayım
sonrası dönemde getirisinin azalması** olgusu. McLean-Pontiff 2016 [Tablo 3,
s.32]: 82 anomaly aggregate'inde post-publication return-predictability
**in-sample mean'in ≈%65'i** (yani %35 decay), istatistiksel olarak hem
0'dan hem -100%'den anlamlı şekilde farklı.

Decay üç bağımsız mekanizmaya atfedilir:

1. **Statistical bias** (data-mining, specification search, publication
   selection): McLean-Pontiff out-of-sample-but-pre-publication coefficient
   ≈%10 — istatistiksel olarak 0'dan **farksız** (insig). Wiki yorumu:
   data-mining şüphesi 82-anomaly aggregate'inde **kanıtla desteklenmiyor**
   ([[mclean_pontiff_2016_post_publication_decay]] [Tablo 3, Tablo 4]).

2. **Informed trading + arbitraj** (publication-induced sophisticated trader
   reaction): McLean-Pontiff'in publication coefficient'i ile out-of-sample
   coefficient farkı (35 − 10 = 25%) bu mekanizmaya atfedilir. Doğrudan
   kanıt: anomaly stocks'ta turnover, dollar volume, variance, short
   interest **post-sample VE post-pub artıyor** ([[mclean_pontiff_2016_post_publication_decay]]
   [Tablo 6-7]).

3. **Risk premium evrimi (zaman-değişken expected return)**:
   [[cochrane2011_discount_rates]] [s.10-12] çerçevesinde discount rate'ler
   zaman-değişken; bir anomaly'nin in-sample primum'u risk premium
   regime'inin spesifik bir kalıbına ankrajlı olabilir, post-pub döneminde
   regime kayması decay'i yaratır. Bu mekanizma McLean-Pontiff'in
   "publication-effect" yorumundan farklı; aynı empirik bulguyu da
   açıklayabilir (Cochrane mathematical equivalence).

## Decay'in **discrete change**'i mi, **lineer trend**'i mi?

[[mclean_pontiff_2016_post_publication_decay]] [Tablo 5]: time trend
indicator'lar (post-1926 ay, post-publication ay, post-1993 dummy) post-pub
indicator ile birlikte INSIG hale gelir; post-pub indicator -29% to -43%
sig kalır. Yorum: decay **publication zamanına ankrajlı discrete
change**, lineer aşınma değil. Trading-cost reduction veya information
environment iyileşmesi (Chordia vd. 2011) tek başına post-pub effect'i
açıklamıyor.

## Decay'in zaman boyutu (yıllık paterni)

[[mclean_pontiff_2016_post_publication_decay]] [Tablo 4]:

| Dönem | Coefficient | sig |
|---|---|---|
| Last 12 months sample | -0.091 | p=0.678 (insig — sample-end opportunism reddi) |
| First 12 months out-of-sample | +0.338 | p=0.107 (insig) |
| Post-pub yıl 1 (P1-12) | -0.283 | p=0.191 (insig) |
| Post-pub yıl 2 (P13-24) | -0.178 | p=0.430 (insig) |
| **Post-pub yıl 3 (P25-36)** | **-0.577** | **p=0.015 (sig — max decay)** |
| **Post-pub yıl 4 (P37-48)** | **-0.563** | **p=0.020** |
| **Post-pub yıl 5 (P49-60)** | **-0.481** | **p=0.030** |
| Post-pub yıl 5+ (P>60) | -0.307 | p<0.001 (kısmi recovery) |

Yorum: sophisticated trader giriş yıl 1-2'de görece zayıf, max decay yıl 3-5
arası, sonrasında crowded-out olunca yeni anomalilere kayıp partial
recovery.

## Limited arbitrage — kim daha çok decay yaşar?

[[mclean_pontiff_2016_post_publication_decay]] [Tablo 8] post-pub-only
sample (9,823 obs) regresyonu:

| Stock-level trait | Slope | sig | Yorum |
|---|---|---|---|
| **Size** | +1.442 | p<0.001 | Büyük cap → decay AGRESİF |
| **Dollar Volume** | +1.380 | p<0.001 | Likit → decay AGRESİF |
| **Idiosyncratic Risk** | -1.420 | p=0.001 | Yüksek idio risk → decay AZ |
| **Dividends** | +1.439 | p<0.001 | Divid-payer → decay AGRESİF |
| Bid-Ask Spreads | 0.176 | p=0.502 | Borderline / insig |

5 trait'in 4'ü tutarlı: **arbitraj kolay olduğu firmada decay güçlü**.

> ⚠️ **Wiki amacı için "çift darbe"**: S&P 500 ve özellikle Nasdaq 100
> evren tam olarak bu profilde (büyük cap, likit, çoğu divid-payer, görece
> düşük idio risk) → wiki amaç evrenleri post-pub decay'in **EN AGRESİF**
> olduğu segment. Bu, Faz 3 strateji baseline rakamı için decay-adjusted
> spread'in **muhafazakâr (yüksek decay)** tarafa esnetilmesi gerektiği
> anlamına gelir → [[meta/open_questions]] Q29.

## Wiki'de post-publication decay paterninin somutlaştığı tek paper

[[mclean_pontiff_2016_post_publication_decay]] paperinden anomaly-level
tek-tek decay rakamı **çıkarılamıyor** (paper aggregate %35'i raporlar; 82
anomaly individual decay setleri Internet Appendix'te). Wiki'de
**composite-score-spesifik** decay'in somut empirik örneği yalnız bir
paperdan geliyor:

[[li_mohanram2019_quality_value]] [Tablo 2, s.15-16]:

| Strateji | Origin spread | Modern spread | Düşüş ratio'su |
|---|---|---|---|
| F-Score (BM-Q5 binary, 1976-96) | +23.0% | +7.44% (1973-2012, all-firms continuous) | ~3x |
| G-Score (low-BM binary, 1979-99) | +21.2% | +6.06% (1973-2012, all-firms continuous) | ~3.5x |

> 📝 **Önemli caveat:** Li-Mohanram'in modern spread'i SAF post-publication
> decay'i ölçmez. 4 etken karışık: (1) sample uzatması (post-publication
> dönem dahil), (2) universe genişlemesi (BM-Q5 / low-BM dışına çıkış),
> (3) binary → continuous çevrimi, (4) industry classification revision.
> SAF decay komponenti ayrıştırılmamış. Yine de **3x'lik düşüşün önemli
> bir kısmı** McLean-Pontiff aggregate decay'i ile uyumlu (Li-Mohanram
> 3x = %67 decay; McLean-Pontiff %35 aggregate; aradaki fark %32 universe
> genişlemesi + binary-continuous + industry revision).

## Decay-adjusted spread tablosu — Faz 3 baseline

> 📝 **Cycle 11 kullanıcı kararı 2:** Bu tablo bu sayfada (post_publication_decay)
> tutulur, [[fundamental_scoring]] sayfasında değil. Faz 3 strateji baseline
> rakamı olarak buradan okunur.

**Methodology:**
- "**Headline**" sütunu: ingest edilen paperdaki orijinal in-sample spread
- "**Modern out-of-sample**" sütunu: paperdan-bağımsız modern replikasyon
  rakamı (varsa)
- "**Aggregate decay-adjusted**" sütunu: headline × 0.65 (McLean-Pontiff
  aggregate %35 decay multiplier)
- "**NDX agresif sensitivity**" sütunu: headline × 0.50 (Q29 hipotezi —
  NDX evren limited-arbitrage çift darbesi nedeniyle decay daha güçlü
  olabilir)

| Strateji | Headline | Sample | Modern out-of-sample | Aggregate ×0.65 | NDX agresif ×0.50 |
|---|---|---|---|---|---|
| **F-Score (binary, BM-Q5)** [[piotroski2000_f_score]] | +23.0% spread | 1976-1996 | +7.44% (Li-Mohanram all-firms continuous, 1973-2012) | +14.95% | +11.50% |
| **F-Score (binary, large-cap)** [[piotroski2000_f_score]] [Tablo 4] | +15.2% (insig, t=1.88) | 1976-1996 | +4.43% standalone (Li-Mohanram large-cap) | +9.88% (in-sample zaten insig — caveat) | +7.60% |
| **G-Score (binary, low-BM)** [[mohanram2005_g_score]] | +21.2% | 1979-1999 | +6.06% (Li-Mohanram all-firms continuous, 1973-2012) | +13.78% | +10.60% |
| **G-Score (binary, large-cap)** [[mohanram2005_g_score]] [Tablo 5] | +19.8% sig 1% | 1979-1999 | (Li-Mohanram large-cap rakamı paperda explicit ayrı yok) | +12.87% | +9.90% |
| **F&V/P combined (binary)** [[li_mohanram2019_quality_value]] [Tablo 2] | +17.94% (1973-2012) | 1973-2012 | (sample zaten post-publication dönem dahil) | — (modern rakam aggregate'i içselleştiriyor) | (NDX agresif: +8.97%) |
| **F&V/P combined (large-cap)** [[li_mohanram2019_quality_value]] | +11.92% (1973-2012) | 1973-2012 | (sample zaten post-publication dönem dahil) | — | (NDX agresif: +5.96%) |
| **G&V/P combined** [[li_mohanram2019_quality_value]] | +21.45% (1973-2012) | 1973-2012 | en yüksek combined; sample post-pub dahil | — | (NDX agresif: +10.73%) |
| **G&NEGPEG combined growth** [[li_mohanram2019_quality_value]] | +20.07% (1973-2012) | 1973-2012 | sample post-pub dahil | — | (NDX agresif: +10.04%) |
| **Sloan accruals** [[sloan1996_accruals_anomaly]] | +10.4% raw hedge | 1962-1991 NYSE+AMEX | size-adj +2.9% (marjinal); modern Green-Hand-Soliman 2011 wiki'de yok | +6.76% | +5.20% |
| **Sloan accruals (size-adjusted)** [[sloan1996_accruals_anomaly]] | +2.9% (t=1.64) | 1962-1991 | (size-adj zaten zayıf) | +1.89% (in-sample zaten marjinal) | +1.45% |
| **CGS asset growth (decile spread)** [[cooper_gulen_ion2018_asset_growth_factor_models]] | (decile spread paper-spesifik rakam yok) | 1968-2016 | sample zaten post-pub dönemi içerir | — | — |
| **Magic Formula (Greenblatt)** [[Magic_Formula]] | (kitap kaynaklı; akademik origin yok) | n/a | HMXZ 2020 q5 ile **tam span** [[hou_mo_xue_zhang_2020_security_analysis]] | (q5 lens'inde alpha ~ 0) | (q5 alpha ~ 0) |

> 📝 **Tablo nasıl okunmalı:**
> - **Sample dönemi 2011-öncesi** olan paperlar (Piotroski 2000, Sloan 1996,
>   Mohanram 2005) için **headline × 0.65** McLean-Pontiff aggregate decay
>   uygulaması direct geçerli.
> - **Sample dönemi 2011 sonrasına uzanan** paperlar (Li-Mohanram 2019
>   sample 1973-2012) için modern spread McLean-Pontiff aggregate decay'i
>   **kısmen içselleştiriyor** — extra decay multiplier eklemek
>   double-counting olur. Bu sayfa modern spread'i "—" ile işaretler.
> - **NDX agresif sensitivity (×0.50)** Q29 hipotezi — empirik kanıt yok,
>   limited-arbitrage çift darbesi gerekçesi. Faz 3 stress-testi olarak
>   kullanılır, baseline değil.
> - **F-Score large-cap (Tablo 4)** in-sample spread istatistiksel olarak
>   anlamlı değil; aggregate decay-adjusted rakam **kâğıt üzerinde**
>   değerlendirilir, gerçek strateji baseline'ı için Li-Mohanram modern
>   replikasyon (4.43% standalone, 11.92% combined F&V/P) tercih edilmeli.

## Üç-bacak epistemik omurga: behavioral decay + statistical FDR + empirik replication

> 📝 **Cycle 12 + Cycle 13 eklemeleri.** Cycle 12'de
> [[harvey_liu_zhu_2016_multiple_testing]] ingest'iyle çift-bacak
> kuruldu (behavioral + statistical); Cycle 13'te
> [[hou_xue_zhang_2020_replicating_anomalies]] ingest'iyle **üçüncü
> bacak (empirik replication)** eklendi.

Wiki'nin factor-zoo-filter'ı **üç bağımsız multiple-testing-aware
mekanizma** üzerine kurulu:

| Mekanizma | Paper anchor | Çerçeve | Cevap |
|---|---|---|---|
| **Behavioral decay (post-pub arbitrage)** | [[mclean_pontiff_2016_post_publication_decay]] | 82-97 anomaly aggregate %35 post-pub decay (sig 1%); büyük/likit firmalarda agresif | %65 spread korunuyor → factor zoo'nun büyük kısmı **gerçek** ama post-pub zayıflıyor |
| **Statistical FDR filter** | [[harvey_liu_zhu_2016_multiple_testing]] | 316 factor census; geleneksel `\|t\| > 2.0` yetersiz; BHY `\|t\| > 3.0` mutlak minimum (FDR 1%) | 316 → ~10-30 surviving (BHY) veya ~9 (Bonferroni) → factor zoo'nun büyük kısmı **statistical filtre'yi geçemiyor** |
| **Empirik replication (methodology-robust)** | [[hou_xue_zhang_2020_replicating_anomalies]] | 447 anomaly NYSE-VW microcap-arınmış sample; equal-weight all-stocks rakamları "exaggerated" | 447 → 161 sig at 5% (%36) → 67 sig at t > 3 (%15) → q-factor sonra 46 net sig (%10) — büyük çoğunluk **methodology-robust replication'da hayatta kalmıyor** |

**Üç paper birbirini complementary doğruluyor:**

1. **Sample selection bias kanıtı (HLZ):** %71 missing factor → factor
   zoo'nun büyük kısmı yayımlanamamış (insig çıktı). Yayımlanan
   "elite" subset MP'nin 82-97 anomaly setine giriyor.
2. **Arbitrage activity kanıtı (MP):** %35 aggregate post-pub decay →
   published anomaly'lerin "elite" tarafı bile yayımdan sonra
   zayıflıyor.
3. **Methodology bias kanıtı (HXZ):** %64 insig at 5% NYSE-VW
   methodology'de → equal-weight all-stocks methodology mikrocap
   influence ile anomaly profits'i şişiriyor.
4. **HLZ paper [s.5-6] explicit:** MP'nin post-pub decay'i "out-of-
   sample approach to statistical bias" olarak değerlendiriyor.
5. **HXZ paper [s.3] explicit:** MP'nin methodology'sini eleştiriyor
   ("MP use NYSE-Amex-NASDAQ + EW") — empirik çürütme değil
   methodology disagreement (resolution: scope-dependent →
   [[meta/contradictions]]).
6. **HXZ paper [s.4] explicit:** HLZ'ye complementary referans;
   "HLZ multiple-testing framework + HXZ empirical replication
   farklı framework, aynı conclusion."

**Wiki'nin yorumu:** Factor zoo'dan true signal'i ayıklamanın **üç
bağımsız mekanizması** var; **üç de geçen** factor'ler Faz 3 strateji
tasarımı için kullanılabilir. Detay → "Dört darbe çerçevesi" sentez
tablosu (aşağıda).

## Dört darbe çerçevesi (Cycle 12 + Cycle 13 sentez)

> 📝 **Cycle 13 kullanıcı kararı 4:** "Üç darbe çerçevesi" → **"Dört darbe
> çerçevesi"** rename. HXZ 2020 ingest'iyle methodology-robust
> replikasyon dördüncü darbe olarak eklendi. 19-satır sentez tablosu
> yeni Replication kolonuyla genişletildi.

> ⚠️ **Çerçeve genişleme disiplini meta-not (Cycle 13 kullanıcı kararı 4):**
>
> Her epistemik filtre paper'ı yeni "darbe" olarak eklenmez. Yeni darbe
> ancak **(a) ortogonal mekanizma**, **(b) wiki'de aggregate tablosu olan**,
> **(c) Faz 3 strateji tasarımında include/exclude kararına doğrudan girdi
> olan** filtreler için açılır.
>
> **Cycle 14 ilk gerçek test (Bailey-LdP DSR ingest):** Plan'da Hipotez C
> (DSR kısmen örtüşür); paper okuma sonrası teyit edildi. Disiplin
> kriterleri test sonucu:
> - (a) Ortogonal mekanizma: **KISMEN** (trial-count HLZ overlap;
>   skew/kurt/sample-length ortogonal — 4 bileşenden 3'ü ortogonal)
> - (b) Wiki'de aggregate tablo: **HAYIR** (ham backtest verisi
>   gerekli; modern data ingest sonrası mümkün)
> - (c) Faz 3 include/exclude doğrudan girdi: **DOLAYLI EVET** (Sharpe
>   reporting metodolojisi; factor decision değil)
>
> Skor: 1 dolaylı + 1 kısmen + 1 reddedilir → **5. darbe AÇILMADI**;
> çerçeve dört darbede sabitlendi. Paper [s.8] kendi konumunu HLZ'ye
> "complementary methods" olarak tanımlıyor — wiki kararıyla tam
> uyumlu. **DSR Faz 3 backtest spec'i için methodology infrastructure**
> ([[concepts/backtest_overfitting]] ayrı concept açıldı).
>
> **Disiplin meta-not'unun amacı işlevini yerine getirdi**: "yeniden
> dur ve değerlendir" testi kullanıldı, otomatik genişleme yapılmadı,
> kriterlerle gerekçeli karar verildi. Faz 2'de yeni paper'lar için
> aynı disiplin uygulanır.

> 📝 **Cycle 12 kullanıcı kararı 5 (Cycle 13'te genişletildi):**
> post_publication_decay sayfasında wiki'deki her ingested factor için
> **dört katmanlı (in-sample large-cap + post-pub decay + MT-corrected
> sig + methodology-robust replication) sentez tablosu** tutulur.
> [[concepts/multiple_testing]] aggregate tablosu (316 factor) +
> [[concepts/anomaly_replication]] aggregate tablosu (447 anomaly +
> wiki ingested) ile bu tablo (sadece wiki ingested faktörlerin
> dört darbe sentezi) komplementer.

**Methodoloji:**
- **In-sample large-cap (Piotroski tipi evrene-spesifik test):**
  ✅ sig in-sample / ⚠️ borderline / ❌ insig
- **Post-pub decay-adjusted spread sig (McLean-Pontiff aggregate
  multiplier veya modern replikasyon):**
  ✅ sig decay-adjusted / ⚠️ marjinal / ❌ insig veya zaten silinmiş
- **Multiple-testing-corrected sig (HLZ BHY-FDR-1% eşiği `|t| > 3.0`):**
  ✅ sig / ⚠️ borderline / ❌ insig
- **Methodology-robust replication (HXZ NYSE-VW microcap-arınmış):**
  ✅ replicate sig / ⚠️ q-factor span / ❌ NYSE-VW altında insig

| Factor / Strateji | In-sample large-cap | Post-pub decay | MT-corrected | Replication (HXZ) | Dört darbe sonucu |
|---|---|---|---|---|---|
| **F-Score (BM-Q5 origin, 1976-96)** | ✅ sig (universe BM-Q5) | ⚠️ aggregate %35; modern Li-Mohanram +7.44% | ✅ sig | ✅ replicate; ⚠️ q-factor span (Fq, t=0.58 insig) | **3/4** (BM-Q5-only altyapı; q-factor span = risk premium proxy) |
| **F-Score (large-cap, Tablo 4)** | ❌ t=1.88 insig | ⚠️ MP Tablo 8 limited arbitrage agresif | ❌ MT insig | (large-cap-only spesifik HXZ rakamı yok; q-factor span paralel) | **0/4 DÖRT DARBE** |
| **F & V/P combined large-cap** | ✅ +11.92% sig 1% | ⚠️ Li-Mohanram sample 1973-2012 zaten post-pub | ✅ sig (yaklaşık) | (composite, individual census dışı; Q31) | **3/4 (4. darbe Q31 ortogonal)** ← Faz 3 baseline aday |
| **G-Score (low-BM origin)** | ✅ sig 1% | ⚠️ Li-Mohanram modern +6.06% (3.5x düşüş) | ✅ sig (yaklaşık) | (Mohanram ref list'te; specific result paperdan teyit) | **2-3/4** (asimetrik; replication paperdan teyit) |
| **G-Score (large-cap, Tablo 5)** | ✅ +19.8% sig 1% | ⚠️ asimetrik çift darbe (post-pub agresif) | ⚠️ borderline | (specific HXZ rakamı yok) | **2-3/4** (large-cap güçlü; MT borderline; replication belirsiz) |
| **G-Score (NASDAQ partition)** | ✅ +26.4% sig 1% | ⚠️ asimetrik (post-2000 NDX out-of-sample) | ✅ sig (yaklaşık) | (specific HXZ rakamı yok) | **2-3/4** (NDX-relevant en güçlü kanıt) |
| **G & V/P combined** | ✅ +21.45% sig 1% | ⚠️ Li-Mohanram modern sample | ✅ sig | (composite, Q31 ortogonal) | **3/4 (4. darbe Q31 ortogonal)** ← Faz 3 baseline aday (en yüksek combined hedge) |
| **G & NEGPEG growth combined** | ✅ +20.07% sig 1% | ⚠️ Li-Mohanram modern sample | ✅ sig (yaklaşık) | (composite, Q31 ortogonal) | **3/4 (4. darbe Q31 ortogonal)** ← NDX baseline aday |
| **Sloan accruals raw (Oa)** | ✅ +10.4% sig | ⚠️ size-loaded; modern decay (Green-Hand-Soliman 2011) | ✅ sig | ✅ **q-factor alpha -0.54% sig (t=-3.77)** | **4/4** ← üç darbe + replication TAMAMINDA hayatta kalan nadir anomaly |
| **Sloan accruals size-adj** | ❌ t=1.64 marjinal | ❌ zaten zayıf, large-cap'te silinmesi beklenir | ❌ MT insig | (raw replicate; size-adj zaten zayıf) | **0/4 DÖRT DARBE** |
| **CGS asset growth (decile)** | (paperdan tek-tek rakam yok) | ✅ aggregate-altı decay (sample uzatma sonrası hayatta) | ✅ sig | ✅ replicate (smaller mag.); ⚠️ q-factor I/A span | **3/4** (q-factor span = risk premium proxy; klasik replicate) |
| **Magic Formula (Greenblatt)** | ❌ q5 alpha negatif | ❌ post-pub decay zaten gerçekleşmiş (q5 ile span) | ❌ insig | (kitap, peer-review değil; HXZ academic sample dışı) | **0/4 DÖRT DARBE** |
| **HML (FF93 origin, 1963-91)** | ✅ +0.40%/ay sig | ⚠️ MP aggregate; FF15 5F redundant; **Lev-Srivastava 1989'dan beri faltering** | ⚠️ Bonferroni borderline; BHY borderline | ✅ replicate (klasik 0.59% sig); ⚠️ q-factor I/A span (alpha 0.18% insig) | **2-3/4** (q-factor lens'inde span; klasik sig; Lev-Srivastava ile decay aggregate'tan agresif) |
| **HML (FF15 1963-2013)** | ⚠️ 5F redundant | ⚠️ MP aggregate; **Lev-Srivastava decade decomposition 2010s NEGATIVE** | ✅ sig (BHY) | (paralel HXZ kanıt) | **2-3/4** (subsumption durumu) |
| **Adjusted HML (Lev-Srivastava intangibles-aware)** [[lev_srivastava_2020_value_failure]] | ✅ 39 yılın 34'ünde conventional'ı geçer | ✅ adjusted methodology decay'i absorb ediyor | (modern data ile direct test eksik) | (modern data ile replikasyon eksik) | **alternative methodology — Faz 3 baseline aday; F bloğu 3 ayak hazır** |
| **SMB (FF93)** | ❌ never sig under MT (HLZ Şekil 3 mark) | ⚠️ MP aggregate | ❌ never sig | (likely insig under VW) | **0-1/4 DÖRT DARBE** |
| **RMW (FF15 Ope)** | (joint kontrol 4.09 sig; 2x3 marjinal) | ⚠️ MP aggregate | ⚠️ borderline | ❌ **HXZ explicit INSIG** (q-factor alpha 0.04% t=0.42) | **1/4** ← çift düzeltme (HLZ + HXZ); RMW exposure target değil |
| **CMA (FF15)** | ✅ sig 2x3 (4.07) | ⚠️ challenged investment proxy yorumu | ✅ sig | ⚠️ klasik 0.34% sig + q-factor alpha 0.01% t=0.32 insig (q-factor I/A span) | **3/4** (q-factor lens'inde span; mekanizma sorunu var) |
| **UMD/MOM (Carhart)** | ✅ +0.82%/ay sig (4.46) | ⚠️ MP aggregate; momentum crashes 2008/2002 | ✅ sig her cutoff | ⚠️ klasik 0.67% sig + q-factor alpha 0.11% t=0.43 insig (q-factor Roe span) | **3/4** ← güçlü; q-factor span = Roe factor exposure proxy |
| **HMXZ q5 F-Score microcap** | ⚠️ microcap-only sig | (q5 risk premium) | ⚠️ Bonferroni borderline | (mikrocap residual zaten q-factor sample'da explicit yer almıyor) | **mikrocap residual** (large-cap evrene transferli değil) |
| **R&D-to-market (Rdm) — intangibles** ⭐ | (Cycle 13'te HXZ 2020 ile yeni eklendi) | (post-pub decay aggregate %35) | (HLZ explicit yok ama klasik sig) | ✅ **q-factor alpha 0.7% (t=2.89) sig** annual; monthly daha güçlü | **3-4/4** ← Q23 NDX-relevant kritik kanıt |
| **Earnings announcement Abr** ⭐ | (Cycle 13'te yeni eklendi; Piotroski [s.4-5] Abr-related) | (q-factor span EDİLEMİYOR) | (HLZ explicit yok ama klasik sig) | ✅ **q-factor alpha 0.66% (t=4.49) sig** | **4/4** ← Piotroski mekanizmasının q-factor lens'inde hayatta kalan bileşeni |
| **Cash-based operating profits-to-assets (Cop)** ⭐ | (Cycle 13 yeni; Ball-Gerakos vd. 2016 paralel) | — | (HLZ explicit yok) | ✅ **q-factor alpha 0.69% (t=4.77) sig** | **3-4/4** ← Ball-Gerakos vd. 2016 (Tier 1 #9) ek ingest |
| **M-Score (Beneish 1999) — forensic filter** ⚠️ | n/a (forensic detection paper, return prediction değil) | n/a (decay multiplier nüanslı: false positive rate decay'e tabi mi?) | n/a (forensic composite, individual factor census dışı) | n/a (return-predictive anomaly değil) | **N/A — filter olarak kullanılır, factor değil**; dört darbe çerçevesi dışı; F & M / G & M screen-and-rank Faz 3 design |
| **QMJ (Asness 2019) — composite quality (Cycle 19)** ⭐ | ✅ US 1956-2012 4-factor alpha 66 bps/ay (t=11.20); 23/24 country pozitif alpha; 17/24 country sig; 4 dimension breakdown | aggregate %35 multiplier proxy; sample sonu 2012 → post-2012 modern replikasyon eksik (Q51 yeni) | ✅ ham 4-factor t=11.20 → HLZ recommended cutoffs çok rahat geçer (~9 sigma; explicit listed değil paper 2014 sonrası) | ⚠️ HMXZ Tablo 4 **q5 CAPTURES** (alpha 0.06% t=0.42 GRS p=0.12) — q-factor + expected growth model QMJ'yi span ediyor; risk premium yorumu | **3-4/4** (q-factor lens'inde span; klasik 4-factor sig çok güçlü) ← Q2 fully-answered ANCHOR |

> 📝 **Cycle 27 ek (JKP 2023 ingest) — replication kolonu modern data**:
> [[papers/jensen_kelly_pedersen_2023_replication_crisis]] modern
> güncelleme (US 1926+ Global 1986+ 153 factor 93 country Bayesian
> Empirical Bayes hierarchical) **dramatic farklı sonuç**: HXZ %35
> raw + FGX %11 recursive **conservative-side** vs JKP %84.9 Bayesian
> US + %84.0 Global **anti-conservative-side** ~50pp gap.
> [[meta/contradictions]] **3. entry açıldı** (Cycle 27): HXZ ↔ JKP
> dramatic empirik fark scope-dependent + methodology disagreement
> (capped VW + 1-month + Bayesian framework methodology choice'lara
> aşırı duyarlı).
>
> **Wiki için Faz 3 implication** (Cycle 24 v0_draft muhafazakâr revize
> ile uyumlu):
> - HXZ + MP **conservative-side baseline** korunur (×0.65 / ×0.50
>   decay multiplier)
> - JKP %85 **anti-conservative upper bound sensitivity reference**
> - Methodology choice sensitivity test Faz 3 spec (pure VW + FF
>   half-weight + capped VW üç alternative)
> - 13 theme cluster + tangency portfolio JKP framework Faz 3
>   multi-theme allocation anchor

> 📝 **Cycle 25 ek (Eisfeldt-Papanikolaou 2013) — F bloğu 4. ayak**:
> [[papers/eisfeldt_papanikolaou_2013_organization_capital]] organization
> capital factor portfolio direct evidence; tabloda yeni satır eklendi
> (industry-relative spread 4.8% FF3 α 5.5% Carhart α 3.9% sig 1%).
> F bloğu intangibles 4-katmanlı methodology hierarchy + factor
> portfolio anchor ayrımı dokümante.

| **Organization Capital (Eisfeldt-Papanikolaou 2013) — F bloğu 4. ayak** ⭐ | ✅ industry-relative spread 4.8% + FF3 α 5.5% sig + Carhart α 3.9% sig 1% + DOL-controlled 3.1% sig (operating leverage rejected); ⚠️ large-cap-only direct test eksik (industry-relative methodology size-neutralizing) | aggregate %35 multiplier proxy → 3.6%/yıl decay-adjusted; sample sonu 2008 → post-2008 out-of-sample (Q57 paralel) | ✅ FF3 α 5.5% sig HLZ recommended cutoff `\|t\|>3.0` BHY rahat geçer; Carhart α 3.9% borderline (t-stat explicit yok) | ✅ unconditional sort ex-fin spread 3.86% Carhart α 5.4% sig — HXZ NYSE-VW paralel methodology çift teyit; HXZ 2020 [s.2] organization capital 447 anomaly içinde test (replication status detail eksik) | **3-4/4** ← F bloğu 4. ayak factor portfolio direct evidence; NDX FAANG profile birebir match; methodology infrastructure (Lev-Sougiannis + Peters-Taylor + Lev-Srivastava) + factor portfolio anchor (Eisfeldt-Papanikolaou) ayrımı |

> 📝 **Cycle 23 ek (Novy-Marx 2013) — Profitability zinciri 4 satır görsel**:
> [[papers/novy_marx_2013_gross_profitability]] origin paper ingest
> sonrası **iki paralel quality zinciri** wiki için dokümante. Tabloda
> 4 satır Profitability zinciri olarak işaretli (Sloan zinciri paralel):
>
> | Halka | Factor | Yıl | Tablodaki satır | Dört darbe |
> |-------|--------|-----|------------------|------------|
> | **1 (origin)** | GP/A (Novy-Marx) | 2013 | **YENİ** (aşağıda eklendi) | **3-4/4** |
> | 2 | RMW Ope (FF15) | 2015 | mevcut | **1/4** ⚠️ HXZ q-factor INSIG |
> | 3 | QMJ Profitability (Asness) | 2019 | mevcut (composite) | 3-4/4 |
> | 4 | Cop (HMXZ Tablo 5) | 2020 | mevcut ⭐ | **4/4** |
>
> **Sloan zinciri paralel** (mispricing): Sloan total accruals (4/4) →
> F_ACCRUAL → G3 → QMJ Profitability ACC. **İki zincir QMJ
> 4-dimension'da birleşiyor** (Profitability dimension 6 measure
> içinde GPOA + ACC yan yana).

| **Gross Profitability GP/A (Novy-Marx 2013) — Profitability zinciri 1. halka** ⭐ | ✅ univariate FF3 α 0.52% t=4.49 sig + size Q5 large-cap FF3 α "small-cap kadar güçlü" + Fortune 500 GP/V Sharpe 0.74 ⭐ wiki S&P 500 anchor | aggregate %35 multiplier proxy → 0.34%/ay decay-adjusted; sample sonu 2010 → post-2010 out-of-sample (Q56 + Q33 paralel) | ✅ FF3 α t=4.49 + PMU\|BM t=5.35 (HLZ recommended cutoff `\|t\|>3.0` BHY çok rahat geçer; Bonferroni 3.78 cutoff'unu da geçer) | ⚠️ HXZ 2020 q-factor lens'inde Cop (cash-aware evrim) superior; GP/A standalone HXZ kapsamında listed; q-factor span partial | **3-4/4** ← Profitability zinciri origin; Fortune 500 GP/V wiki S&P 500 baseline anchor |

> 📝 **Cycle 22 ek (Israel-Moskowitz 86-yıl) — in-sample large-cap kolonu sertleştirme**:
> [[israel_moskowitz_2013_shorting_size_time]] **86-yıl US sample direct
> kanıt** [Tablo 3] tabloda 3 satırın in-sample large-cap değerlendirmesini
> sertleştiriyor:
> - **HML (FF93/FF15)**: largest 40% NYSE stocks'ta CAPM α 1.97-3.70%
>   t=1.04-1.90 INSIG → in-sample large-cap **❌ insig** (Lev-Srivastava
>   2020 + Israel-Moskowitz 2013 **çift anchor**)
> - **SMB (FF93)**: 86-yıl CAPM α 2.05% t=1.72 INSIG → "never sig under
>   MT" (HLZ statistical) + 86-yıl confirmation (Israel-Moskowitz)
>   **çift kanıt**; vanilla SMB 0-1/4 sertleşir
> - **UMD (Carhart)**: size Q5 (largest) 5-1 spread CAPM α=10.24%
>   t=4.23 sig + size-invariant; long-only Q5 winners α=3.92% t=3.83
>   sig → in-sample large-cap **✅ sig** (klasik Carhart 1963-93 dar
>   sample'dan 86-yıl extended sample'a güçlenmiş kanıt). UMD 3/4 statüsü
>   kolon 1'de güçleniyor.

### Sentez: Faz 3 strateji baseline adayları (dört darbeden 4/4 veya 3/4 q-factor span ile risk premium proxy)

**4/4 hayatta kalan factorler (üç darbe + replication tamamen):**
1. **Sloan operating accruals (Oa)** — wiki C bloğu omurgasının
   statistical güçlenmesi; Sloan 1996 anomaly replication crisis'inde
   nadir hayatta kalan kanıt. F_ACCRUAL/G3 binary versiyonları
   komposit içinde complementary kullanılır. (kanıt: HXZ q-factor alpha
   -0.54% t=-3.77 sig)
2. **R&D-to-market (Rdm)** — NDX evrene transferli intangibles-aware
   factor için kritik kanıt; Q23 partial cevap. (kanıt: HXZ q-factor
   alpha 0.7% t=2.89 sig annual)
3. **Earnings announcement abnormal returns (Abr)** — Piotroski 2000
   [s.4-5] behavioral mekanizmasının q-factor lens'inde hayatta kalan
   bileşeni. (kanıt: HXZ q-factor alpha 0.66% t=4.49 sig)
4. **Cash-based operating profits-to-assets (Cop)** — Ball-Gerakos vd.
   2016 (Tier 1 #9) paralel kanıt; ek ingest ile pekişir. (kanıt: HXZ
   q-factor alpha 0.69% t=4.77 sig)

**3/4 (üç darbe sig ama q-factor span — risk premium proxy):**
1. **F & V/P combined (large-cap)** — S&P 500 baseline ana aday
   (composite, replication ortogonal Q31; üç darbe 3/3 ile pekişti).
   Kanıt: Li-Mohanram 2019 [Tablo 7] +11.92% sig 1%
2. **G & V/P combined** — wiki'nin en yüksek combined hedge (replication
   ortogonal Q31). Kanıt: Li-Mohanram 2019 [Tablo 4 Panel B] +21.45%
   sig 1%
3. **G & NEGPEG growth combined** — NDX baseline ana aday (replication
   ortogonal Q31). Kanıt: Li-Mohanram 2019 +20.07% growth subgroup
4. **UMD/MOM** — momentum exposure; q-factor lens'inde Roe factor
   exposure proxy. Kanıt: Carhart 1997 [Tablo II] +0.82%/ay; HLZ Şekil 3
   sig her cutoff; HXZ q-factor alpha 0.11% insig (Roe span)
5. **CMA (FF15)** — investment factor exposure proxy; q-factor I/A
   span. Kanıt: HXZ klasik 0.34% sig + q-factor alpha 0.01% insig
6. **CGS asset growth** — investment kategorisi; q-factor I/A span
   (paralel)
7. **F-Score (BM-Q5 origin)** — q-factor span = Roe factor exposure
   proxy; klasik sig her üç darbe ama BM-Q5-only altyapı

### Sentez: Dört darbeden 0-1/4 (kullanıma alınmaz)

1. **F-Score large-cap standalone** — Piotroski Tablo 4 [s.19]
   in-sample t=1.88 insig + post-pub decay agresif + MT insig +
   replication paralel insig → **standalone kullanılmaz, ancak F & V/P
   combined kompanse eder**
2. **Sloan accruals size-adj** — t=1.64 marjinal + size-loaded + MT
   insig + replication zaten zayıf → **standalone yetersiz, F_ACCRUAL
   binary komposit içinde complementary**
3. **SMB** — HLZ Şekil 3 never sig + FF93 t=1.73 marjinal +
   replication likely insig under VW → **strateji tasarımında "SMB
   exposure target" yok; factor model risk-adjusted regression
   baseline'da kalır**
4. **RMW (Ope)** — HLZ Şekil 3 borderline + **HXZ explicit INSIG
   (q-factor alpha 0.04% t=0.42)** → **çift düzeltme; RMW exposure
   target değil** (paperin abstract'ında explicit listed insig)
5. **Magic Formula** — q5 alpha negatif + post-pub decay zaten
   gerçekleşmiş + MT insig + HXZ academic sample dışı → **academic
   strateji baseline'a alınmaz; retail-friendly framing dışında değer
   üretmiyor**
6. **Distress anomaly (Campbell-Hilscher-Szilagyi 2008, Tier 2 #33,
   henüz ingest edilmedi):** HXZ paperde "virtually nonexistent"
   [s.2] — Tier 2 #33 ingest planı sorgulanır
7. **Richardson-Sloan-Soliman-Tuna 2005 total accruals (Ta)** —
   HXZ explicit insig; Sloan 1996 hayatta, RSST 2005 modern revisit
   çürütülüş

### Sentez: Asimetrik / mekanizma sorunu olan factorler

1. **G-Score (large-cap, NASDAQ)** — in-sample sig + post-pub decay
   asimetrik agresif + MT borderline + replication belirsiz. Li-Mohanram
   modern replikasyon F-Score'la benzer 3.5x düşüş; combined yaklaşımla
   kompanse.
2. **CMA / Asset_Growth** — q-factor span = investment factor exposure
   proxy; "investment proxy" mekanizma yorumu CGS-Ion 2018 ile
   challenged.
3. **HML (FF93/FF15)** — sample-bağımlı; FF15 5F altında redundant;
   HLZ BHY sig ama Bonferroni borderline; HXZ q-factor I/A span (Bm
   alpha 0.18% insig).

### Dört darbe çerçevesi → Faz 3 strateji formülü

S&P 500 baseline:
```
S&P 500 = Long(F & V/P combined, large-cap, top quintile)
        ⊕ Long(UMD top quintile)
        ⊕ Long(top-decile Sloan operating accruals — F_ACCRUAL signal)
        - Short benchmarks (decay-adjusted spread baseline + replication-aware)
```

NDX baseline:
```
NDX = Long(G & NEGPEG growth combined, top quintile)
    ⊕ Long(UMD top quintile)
    ⊕ Long(R&D-to-market top quintile — intangibles factor)
    ⊕ Long(top-decile earnings announcement abnormal returns)
    - Short benchmarks (NDX-aggressive decay sensitivity ×0.50 + replication-aware)
```

**Risk-adjustment baseline:** q-factor model exposure (I/A, Roe,
MKT-RF, ME) — SMB exposure target değil; **RMW (Ope) exposure target
değil** (HXZ explicit insig); CMA risk premium proxy. Cycle 13 ek:
**Sloan operating accruals + R&D-to-market + earnings announcement
abnormal returns** dört darbe geçen factorler — Faz 3 baseline'a
explicit dahil edilir.

**Decay-adjusted Faz 3 baseline beklenen spread:**
- S&P 500 F&V/P combined large-cap: in-sample +11.92% × 0.65 (MP
  decay-adjusted) ≈ **+7.75% yıllık** baseline
- NDX G&NEGPEG growth combined: in-sample +20.07% × 0.50 (NDX agresif
  sensitivity) ≈ **+10.04% yıllık** baseline
- UMD: in-sample +0.82%/ay × 12 × 0.65 ≈ **+6.4% yıllık** decay-adjusted
  exposure premium

> 📝 Bu baseline rakamları **kâğıt üzerinde**; gerçek backtest sonuçları
> Faz 3 methodology sayfasında doğrulanır. Trading cost, capacity,
> survivorship bias, PIT data ek düzeltmeler.

## Wiki'nin epistemik pozisyonu

Wiki'nin kümülatif sentezi, decay-adjusted spread tablosu ışığında **üç
pratik kural** üretir:

1. **Standalone composite scores Faz 3'te baseline değil:** Decay-adjusted
   F-Score (~+15%) ya da G-Score (~+14%) headline rakamları cazip görünse
   de, in-sample large-cap zayıflığı (Piotroski Tablo 4) + modern
   replikasyon (Li-Mohanram +7.44% / +6.06%) + post-pub aggregate decay
   üçlüsü combined yaklaşıma götürür. **F&V/P (S&P 500) ve G&NEGPEG (NDX)
   combined defaults**.

2. **NDX evrene ekstra defansif tampon:** Q29 sensitivity (×0.50) baseline'ı
   ek %15 muhafazakâr taraftan çekiyor. NDX strategy spec'i in-sample
   headline ile değil, **muhafazakâr decay-adjusted** rakamla optimize
   edilmeli (örn. %5 hedge return baseline kabul, %20 değil).

3. **q5 baseline kontrolü her durumda gerekli:** [[hou_mo_xue_zhang_2020_security_analysis]]
   q5 model lens'inde fundamental scoring strategies microcap residual
   hariç **span ediliyor**. Yani bir composite score'un strateji ekonomik
   değeri q5 risk-premium exposure'ları üzerinden taşınıyor olabilir;
   "saf alpha" iddiası decay-adjusted spread tablosundan **bağımsız bir
   kontrol** gerektirir. Bu, McLean-Pontiff'in mispricing yorumu ile HMXZ'nin
   risk premium yorumu arasında **felsefi farkı** strateji tasarımına
   nüfuz ettiren noktadır (Cochrane mathematical equivalence: pratik
   strateji çıktısı aynı).

## İlgili paperlar (ingested)

- [[mclean_pontiff_2016_post_publication_decay]] — behavioral decay
  bacağı; aggregate %35 decay, çift darbe limited arbitrage, sample-end
  opportunism reddi
- [[harvey_liu_zhu_2016_multiple_testing]] — statistical FDR bacağı;
  316 factor census; recommended cutoff `|t| > 3.0` (BHY 1%, M=R);
  üç-bacak epistemik omurganın ikinci ayağı
- [[hou_xue_zhang_2020_replicating_anomalies]] — empirik replication
  bacağı; 447 anomaly NYSE-VW methodology'de %64-85 insig; q-factor
  model 161 sig anomaly'nin 115'ini insig bırakır; üç-bacak epistemik
  omurganın üçüncü ayağı
- [[cochrane2011_discount_rates]] — discount rate evrimi yorumu (decay'in
  3. mekanizması)
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 model lens'inde span;
  decay'i risk premium evrimiyle açıklayan paralel çerçeve
- [[li_mohanram2019_quality_value]] — F-Score / G-Score modern replikasyonu;
  composite-score-spesifik decay'in somut tek empirik örneği
- [[sloan1996_accruals_anomaly]] — accruals anomaly origin; size-adj zayıf
  (anomaly size-loaded); post-pub takip Green-Hand-Soliman 2011 ile
- [[piotroski2000_f_score]] — F-Score origin; large-cap in-sample zaten
  zayıf [Tablo 4]
- [[mohanram2005_g_score]] — G-Score origin; sample 1979-1999 post-2000
  out-of-sample
- [[cooper_gulen_ion2018_asset_growth_factor_models]] — CGS-Ion sample
  1968-2016 zaten post-pub dönem dahil
- [[lev_srivastava_2020_value_failure]] — **value-spesifik post-2010
  decay anchor (Cycle 17)**; HML decade-by-decade decomposition
  (1970s +102% → 2010s NEGATIVE); HML-spesifik decay aggregate %35'ten
  daha agresif kanıt; intangibles-aware adjusted HML methodology
  39 yılın 34'ünde conventional'ı geçer
- [[lev_sougiannis_1996_rd_capitalization]] — F bloğu #1; intangibles
  methodology origin (yazar continuity Lev-Srivastava 2020 ile)
- [[peters_taylor_2017_intangible_capital]] — F bloğu #2; total
  intangible capital generalization
- [[beneish_1999_m_score]] — **forensic filter Cycle 18**; dört darbe
  çerçevesi dışı (forensic detection paper, return prediction değil);
  filter olarak kullanılır, factor değil; F & M / G & M screen-and-rank
  Faz 3 design; decay multiplier nüanslı (Q48 yeni: false positive
  rate decay'e tabi mi?)
- [[asness_frazzini_pedersen_2019_qmj]] — **all-cap quality Cycle 19**;
  dört darbe sentez tablosunda 3-4/4 (q-factor lens'inde span; klasik
  4-factor sig çok güçlü); Q2 fully-answered ANCHOR; sample sonu 2012
  → Q51 yeni post-2012 modern replikasyon

## İlgili paperlar (henüz ingest edilmedi — Q28 cevabı)

- Harvey-Liu-Zhu (2016) (Tier 1 #17) — multiple-testing düzeltmesi; 82
  anomaly setine FDR control, McLean-Pontiff decay rakamlarını "kaç
  anomaly true positive" sorusu altında yeniden çerçeveler
- Hou-Xue-Zhang (2020) "Replicating Anomalies" (Tier 1 #18) — ~447 anomaly
  replikasyon; McLean-Pontiff ile ortogonal kanıt, modern decay rakamları
- Jensen-Kelly-Pedersen (2023) (Tier 2 #44) — "Replication Crisis in
  Finance" modern güncelleme
- Chen-Zimmermann (2022) (Tier 2 #41) — Open Asset Pricing replikasyon
  database
- Green-Hand-Soliman (2011) — accruals-spesifik post-pub decay anchor
  ("death of accruals anomaly"; Tier listesinde değil, aday)

## İlgili kavramlar

- [[factor_zoo]] — decay'in factor zoo perspektifi: 82 anomaly aggregate
  %65 hayatta → factor zoo'nun büyük kısmı **gerçek** ama post-pub
  zayıflıyor (Cochrane #1, #3 sorularına McLean-Pontiff prosedürel cevap)
- [[multiple_testing]] — üç-bacak epistemik omurganın statistical
  bacağı; 316 factor BHY-FDR-1% sig hurdle; "Dört darbe çerçevesi"
  tablosunun MT-corrected sütunu buradan
- [[anomaly_replication]] — üç-bacak epistemik omurganın empirik
  replication ayağı; 447 anomaly NYSE-VW aggregate replication tablosu;
  "Dört darbe çerçevesi" tablosunun Replication sütunu buradan
- [[backtest_overfitting]] — Cycle 14 ek; DSR Sharpe-spesifik selection
  bias düzeltmesi; **5. darbe açılmadı** (disiplin meta-not testi
  geçti); Faz 3 backtest spec'i için methodology infrastructure
- [[fundamental_scoring]] — composite score'lar decay'e karşı combined
  yaklaşımla defans (Li-Mohanram pattern)
- [[winner_loser_identification]] — top-N selection'in decay-adjusted
  baseline'ı buradan okunur
- [[discount_rates]] — decay'in 3. mekanizması (risk premium evrimi)
- [[contextual_fundamental_analysis]] — universe-conditioned skorların
  large-cap decay'e karşı potansiyel defansif tasarım

## Faz 3 backtest implementation

> 📝 **Cycle 21 ek (lint_pass).** Bu kavramın methodology'e geçirilmiş
> hali aşağıda; Faz 3 strategy spec'leri için somut kullanım.

**Dört darbe çerçevesi → [[methodology/backtest_spec]] §4** filter
pipeline. Decay-adjusted spread baseline (×0.65 standard, ×0.50 NDX
agresif sensitivity Q29 stress-testi) [[methodology/backtest_spec]]
§4.2'de operasyonel; üçlü reporting (DSR + alpha t-stat +
decay-adjusted spread) [[methodology/backtest_spec]] §3.1'de zorunlu.

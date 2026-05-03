---
type: concept
name: anomaly_replication
related_papers: [[hou_xue_zhang_2015_q_factor]], [[hou_xue_zhang_2020_replicating_anomalies]], [[mclean_pontiff_2016_post_publication_decay]], [[harvey_liu_zhu_2016_multiple_testing]], [[hou_mo_xue_zhang_2020_security_analysis]], [[jensen_kelly_pedersen_2023_replication_crisis]]
---

> 📝 **Cycle 35 ek**: Replication crisis literatür hattı q-factor literature continuity (4-paper × 8+ yıl): [[papers/hou_xue_zhang_2015_q_factor]] origin (Cycle 35 ✓; ~15 anomaly subsumption + investment-based theoretical foundation) → [[papers/hou_mo_xue_zhang_2020_security_analysis]] q5 extension (Cycle 8) → [[papers/hou_xue_zhang_2020_replicating_anomalies]] 447 anomaly empirical replication (Cycle 13) → [[papers/jensen_kelly_pedersen_2023_replication_crisis]] Bayesian framework (Cycle 27). HXZ 2015 origin paper formal tanımı q-factor lens replication methodology evolution paterni paralel.

> 📝 **Cycle 37 ek**: Size-partition methodology origin [[papers/fama_french_2008_dissecting_anomalies]] (Cycle 37 ✓); FF 2008 microcaps ~60% stocks ama ~3% market cap dokümantasyonu HXZ 2020 [s.3] MP eleştirisi 'NYSE-Amex-NASDAQ breakpoints + equal-weights' methodology farkının kökü; NYSE-VW + microcap-arınmış convention (HXZ 2015/2020 + JKP 2023 capped VW) FF 2008 origin paterni paralel. FF ailesi methodology continuity 3-paper × 22+ yıl (FF93 → FF 2008 → FF15) replication crisis methodology evolution kaynağı.

# Anomaly Replication — Methodology-Robust Empirik Filter

> 📝 **Wiki epistemik omurganın üçüncü ayağı.** [[concepts/post_publication_decay]]
> behavioral decay (MP) bacağını + [[concepts/multiple_testing]]
> statistical FDR (HLZ) bacağını kuruyor. Bu sayfa **empirik
> replikasyon** bacağını kurar — methodology-robust replication
> mekanizması (NYSE breakpoint + value-weight microcap-arınmış
> sample).

## Tanım

Bir akademik anomaly'nin **methodology-robust replication**'u: orijinal
paper'ın sample dönemi + universe + weighting yöntemi yerine, **NYSE
breakpoint + value-weighted** standart methodology ile (microcap
arındırılmış) anomaly'nin istatistiksel anlamlılığının sınanması.

Equal-weighted + NYSE-Amex-NASDAQ breakpoint methodology mikrocap'leri
**aşırı temsil eder**: microcaps NYSE 20th percentile altı; sayıca
%60+ stocks ama market cap'in sadece %3'ü
([[hou_xue_zhang_2020_replicating_anomalies]] [s.32]). Mikrocap'lerin
en yüksek equal-weighted return'leri ve en geniş cross-sectional std
sapmaları anomaly profits'i şişiriyor.

NYSE breakpoint + VW methodology bu mekanizmayı arındırır → "gerçek"
anomaly survival rate ölçülür.

## Replication crisis literatür hattı

Üç paper modern replication crisis tartışmasının referans noktası:

| Paper | Yaklaşım | Headline |
|---|---|---|
| **Israel-Moskowitz 2013** [[israel_moskowitz_2013_shorting_size_time]] | 86-yıl US + 4 international + 5 asset class; size×value×momentum decomposition | **Erken anchor**; HML largest 40% NYSE stocks INSIG; equal-weight vs value-weight methodology farkı [Tablo A2] |
| **HXZ 2020 "Replicating Anomalies"** [[hou_xue_zhang_2020_replicating_anomalies]] | 447 anomaly NYSE-VW methodology'de tek-tek replikasyon | **%35 raw / %10 net q-factor** "factor zoo'nun büyük çoğunluğu false discovery" |
| **JKP 2023 "Replication Crisis in Finance"** [[jensen_kelly_pedersen_2023_replication_crisis]] (Cycle 27 ✅) | **Bayesian Empirical Bayes hierarchical + 153 factor × 93 country global** + capped VW + 1-month focus + 13 theme cluster | **%84.9 Bayesian US / %84.0 Global** ⭐ "factor research empirik kanıtla destekli collective body" |
| **Chen-Zimmermann 2022 "Open Asset Pricing"** (Tier 2 #41) [[methodology/data_sources]] §1 (Cycle 29 ✓) | Replikasyon database + reproducibility infrastructure; **pure replication** (~100% reproducible) | Modern data portalı; HXZ scientific replication ↔ Chen-Zimmermann pure replication ayrımı (JKP [s.1 fn 1] explicit) |

> 📝 **Cycle 27 ek (JKP 2023 ingest) — D bloğu replication ayağı 2 paper × dramatic empirik fark**:
>
> HXZ 2020 (US-only NYSE-VW pure VW 1967-2014) **%35 raw replication**
> vs JKP 2023 (US + Global 1926+ Bayesian capped VW 1-month) **%84.9
> Bayesian replication** = **~50pp gap dramatic empirik fark**.
>
> [[meta/contradictions]] **3. entry açıldı** (Cycle 27): HXZ 2020 ↔
> JKP 2023 dramatic methodology disagreement; Cycle 13 HXZ ↔ MP
> paterni paralel. Resolution: **scope-dependent + methodology
> disagreement** — methodology choice'lara aşırı duyarlı (capped VW
> +8.5pp, 1-month +4.0pp, longer sample +4.3pp, Bayesian framework
> +28pp); empirik ham veri farkı değil **methodology + framework
> evrim**. Her iki sonuç kendi methodology context'inde geçerli.
>
> **Wiki için Faz 3 implication** ([[meta/contradictions]] §3
> resolution): HXZ + MP paralel conservative tarafta (Cycle 24
> v0_draft muhafazakâr revize ×0.65 / ×0.50 decay multiplier);
> JKP %85 anti-conservative upper bound sensitivity reference.
> **Methodology choice sensitivity test** Faz 3 spec'inde üç
> alternative (pure VW + FF half-weight + capped VW)
> ([[methodology/backtest_spec]] §1.3 + §4.4 sertleştirme).
>
> 📝 **Cycle 29 ek (data_sources.md açıldı)**: modern data
> infrastructure [[methodology/data_sources]] §1-3 tam dokümante;
> Chen-Zimmermann 2022 Open Asset Pricing Database (pure replication
> ~100%) + JKP 2023 GlobalFactor code repository GitHub bkelly-lab
> (Bayesian Empirical Bayes %85) + WRDS open-source access (CRSP +
> Compustat raw data feed) **üç paralel data kaynağı** Faz 3 backtest
> implementation ön koşul. **Modern data eksik weakness Cycle 27
> partial → Cycle 29 tam kapanma**.

Bu paperlar ortak: **anomaly literatürünün büyük çoğunluğu
methodology-robust replikasyon'da hayatta kalmıyor**. Israel-Moskowitz
2013 HXZ 2020 NYSE-VW + microcap-arınmış paradigmasının 7 yıl önceden
**erken anchor'ı** — equal-weight all-stocks rakamlarının VW
rakamlarının 3x'ı [Tablo A2] paterni HXZ 2020'nin merkezi methodology
eleştirisini önceden örnekliyor.

## Methodology farkları

### HXZ 2020 standardı

[[hou_xue_zhang_2020_replicating_anomalies]] [s.2-3]:

- **Universe:** NYSE-Amex-NASDAQ all-stocks (microcap dahil)
- **Breakpoint:** **NYSE-only** ME percentile (20% altı microcap → tüm
  decile sortlarından arındırılır)
- **Weighting:** **Value-weighted** returns
- **Test:** High-minus-low decile spread; |t| ≥ 1.96 sig
- **Sample:** 1967-2014

### Önceki literatür standardı

[[mclean_pontiff_2016_post_publication_decay]] (82-97 anomaly):
- NYSE-Amex-NASDAQ breakpoint
- **Equal-weighted returns**
- Microcap inclusive

[[sloan1996_accruals_anomaly]] (orijinal accruals):
- NYSE+AMEX (NASDAQ hariç)
- Equal-weighted

[[piotroski2000_f_score]] (BM-Q5 high-BM evrene):
- Compustat universe
- Equal-weighted (binary 0/1 toplamı)

[[mohanram2005_g_score]] (BM-Q1 low-BM evrene):
- Compustat universe
- Equal-weighted (binary)

### Methodology farkının pratik sonucu

[[hou_xue_zhang_2020_replicating_anomalies]] [s.32]:

> "Microcaps account for 61% of the total number of NYSE-Amex-NASDAQ
> stocks, but only 3.3% of the total market capitalization. Microcaps
> have the highest equal-weighted average returns and the largest
> cross-sectional deviations in returns and anomaly variables among
> microcaps, small stocks, and big stocks. Many studies overweight
> microcaps via NYSE-Amex-NASDAQ (not NYSE) breakpoints, often also
> with equal-weights, in portfolio sorts. ... most published anomaly
> profits are greatly exaggerated."

Sonuç: Equal-weighted methodology **anomaly profits'i sistematik
şişiriyor**; HXZ NYSE-VW methodology **muhafazakâr ölçüm**.

## 447 anomaly category breakdown

[[hou_xue_zhang_2020_replicating_anomalies]] [s.2, Tablo 1]:

| Kategori | # anomaly | Sig at 5% | Insig | Replication rate |
|---|---|---|---|---|
| **Momentum** | 57 | 37 | 20 | %65 |
| **Value-versus-growth** | 68 | 31 | 37 | %46 |
| **Investment** | 38 | 27 | 11 | %71 |
| **Profitability** | 79 | 33 | 46 | %42 |
| **Intangibles** | 103 | 26 | 77 | %25 |
| **Trading frictions** | 102 | 7 | 95 | **%7** ← biggest casualty |
| **Toplam** | **447** | **161** | **286** | **%36 sig at 5%** |
| t > 3 cutoff | 447 | 67 | 380 | **%15 sig at t > 3** |

**Q-factor model sonrası [s.4, Tablo 4]:**
- 161 sig anomaly üzerinde q-factor model regression
- 115 alpha insig at 5% / 150 insig at t > 3
- **46 q-factor alpha sig** (11 with t > 3) — net survival rate **%10**
- 6 kategoride composite q-anomaly sentez (momentum 0.86%, intangibles
  0.85% en güçlü; frictions 0.16% sadece; combined 1.4% t=7.48)

## Wiki ingested factors için aggregate replication tablosu

> 📝 **Cycle 13 kullanıcı kararı 5:** Bu aggregate tablo bu sayfada
> tutulur, factor sayfalarında 1-2 cümle status notu + cross-link
> yeterli.

| Wiki paper / faktör | 447 listesinde? | HXZ replicate? | q-factor alpha | Üç darbe + replication = dört darbe sonucu |
|---|---|---|---|---|
| **Sloan operating accruals (Oa)** [[sloan1996_accruals_anomaly]] | ✓ KESİN | ✓ replicate (smaller mag.) | **-0.54% (t=-3.77) sig** | **4/4 darbenin TAMAMINDA hayatta** ← nadir kanıt |
| **CGS asset growth** [[cooper_gulen_ion2018_asset_growth_factor_models]] | ✓ KESİN | ✓ replicate | (q-factor I/A factor span) | 3-4/4 (q-factor span ile in-explanation) |
| **Jegadeesh-Titman 1993 momentum** [[carhart1997_four_factor]] | ✓ KESİN | ✓ replicate | (smaller magnitude) | 3-4/4 |
| **Carhart UMD** [[UMD]] | ✓ (factor model) | klasik 0.67% (t=3.66) sig | 0.11% (t=0.43) **insig** | 3/4 (q-factor span; klasik sig her cutoff) |
| **FF92/93 HML book-to-market (Bm)** [[HML]] | ✓ KESİN | ✓ replicate (klasik 0.59% sig) | 0.18% (t=1.15) **insig** | 2-3/4 (sample-bağımlı; q-factor I/A span) |
| **FF15 RMW (operating profits-to-book equity, Ope)** [[RMW]] | ✓ KESİN | ✗ **INSIG** klasik | 0.04% (t=0.42) **insig** | **1/4** ← çift düzeltme (HLZ borderline + HXZ insig) |
| **FF15 CMA** [[CMA]] | ✓ (factor model) | klasik 0.34% (t=3.63) sig | 0.01% (t=0.32) **insig** | 3/4 (q-factor span; klasik sig) |
| **Piotroski F-Score (BM-Q5)** [[F_Score]] | ✓ KESİN ref list | ✓ replicate (Fq quarterly klasik 0.58% sig) | 0.13% (t=0.58) **insig** | 3/4 (q-factor span; üç darbe MT-corrected sig) |
| **F-Score (large-cap, Tablo 4)** | ✓ (origin paper) | (large-cap-only spesifik HXZ rakamı yok) | (q-factor span) | **0/4 ÜÇ-DÖRT DARBE** (in-sample insig + post-pub agresif + MT insig + replication paralel) |
| **F & V/P combined large-cap** [[li_mohanram2019_quality_value]] | ✗ composite, individual census dışı | n/a (Q31) | n/a | 3/4 (composite kanıt; replication tarafı eksik → Q31 ortogonal) |
| **G-Score** [[G_Score]] | ✓ ref list (line 1567) | (specific result paperdan teyit) | (likely q-factor explained) | 2-3/4 asimetrik |
| **G & V/P combined** [[li_mohanram2019_quality_value]] | ✗ composite census dışı | n/a (Q31) | n/a | 3/4 (composite; en yüksek combined hedge) |
| **Mohanram (2005) G-Score**| ✓ ref list | (paperdan teyit) | (HMXZ Security Analysis kapsamı dışı, Q25) | belirsiz |
| **Frankel-Lee (1998) V/P** [[li_mohanram2019_quality_value]] | ✓ ref list | (HMXZ q-factor span) | tam span | 2-3/4 (HMXZ paralel) |
| **Magic Formula (Greenblatt)** [[Magic_Formula]] | ✗ kitap, peer-review değil | n/a | (HMXZ q5 span: -0.13% t=-0.76 insig) | **0/4** (zaten 0/3 üç darbe, replication kapsamı dışı pekişiyor) |
| **Sloan size-adj accruals** [[Accruals]] | ✓ (origin paper) | ✗ (raw replicate; size-adj zaten zayıf) | n/a | 0-1/4 (üç darbede 0/3, raw kategorisinde HXZ replicate) |
| **SMB** [[SMB]] | ✓ ref list (size factor) | (paperdan teyit; likely insig under VW) | (factor reference) | 0-1/4 (HLZ never sig + HXZ likely insig under VW + behavioral aggregate) |
| **MKT-RF** [[MKT_RF]] | ✓ (factor reference) | (factor model bileşeni) | n/a | (factor exposure, anomaly değil) |
| **R&D-to-market (Rdm) — intangibles** | ✓ KESİN (intangibles category) | ✓ sig | **0.7% (t=2.89) sig** annual; 1.47% (t=2.97) monthly | **4/4** ← Q23 NDX evrene transferli kritik kanıt |
| **Earnings announcement Abr** | ✓ KESİN (momentum kategorisi) | ✓ sig (klasik 0.74% t=5.85) | 0.66% (t=4.49) **sig** | **4/4** ← Piotroski'nin behavioral mekanizmasının q-factor lens'inde hayatta kalan bileşeni |
| **Cash-based operating profits-to-assets (Cop)** | ✓ profitability category | ✓ sig | 0.69% (t=4.77) **sig** | 4/4 (Ball-Gerakos vd. 2016 Tier 1 #9 paralel kanıt) |
| **Discretionary accruals (Dac)** | ✓ investment category | ✓ sig | -0.64% (t=-4.37) **sig** | 4/4 (Sloan accruals'ın decompose versiyonu) |
| **Richardson-Sloan-Soliman-Tuna 2005 total accruals (Ta)** | ✓ KESİN ref list | ✗ **INSIG** | n/a | **0/4** ← Sloan 1996 hayatta, RSST 2005 modern revisit ÇÜRÜTÜLDÜ |
| **Distress (failure prob., O-Score, Z-Score, credit rating)** | ✓ KESİN (Campbell-Hilscher-Szilagyi 2008, Tier 2 #33) | ✗ **virtually nonexistent** [s.2] | n/a | 0/4 ← wiki Tier 2 ingest planı için kritik bulgu |
| **IVOL (Ang-Hodrick-Xing-Zhang 2006)** | ✓ KESİN | ✗ **INSIG** | n/a | 0/4 (HLZ Şekil 3 mark "never sig" ile uyumlu) |

### Tablo özet bulgular

**Dört darbenin TAMAMINDA hayatta kalan factorler (4/4):**
- Sloan operating accruals (Oa)
- R&D-to-market (Rdm) ← intangibles category Q23
- Earnings announcement abnormal returns (Abr) ← Piotroski mekanizması
- Cash-based operating profits-to-assets (Cop)
- Discretionary accruals (Dac)
- Net operating assets, dWc, dFin (q-factor model accrual-tipi)

**Üç darbede hayatta ama 4. darbede zayıf (3/4):**
- Carhart UMD (klasik sig her cutoff; q-factor span)
- F-Score BM-Q5 origin (klasik sig; q-factor span)
- CGS asset growth, CMA, Jegadeesh-Titman momentum

**Dört darbede 0-1/4 (kullanıma alınmaz):**
- F-Score large-cap standalone (in-sample insig + post-pub agresif +
  MT insig + replication paralel)
- Sloan size-adj accruals (klasik insig)
- Magic Formula (q-factor negatif; zaten 0/3)
- SMB (HLZ never sig; HXZ likely insig under VW)
- Distress anomaly (virtually nonexistent)
- IVOL (HXZ insig; HLZ never sig)
- Richardson-Sloan-Soliman-Tuna 2005 total accruals (modern revisit
  çürütülüş)

### Wiki için kritik bulgular

1. **Sloan 1996 operating accruals dört darbenin tamamında hayatta**
   — wiki C bloğu (earnings quality) omurgasının **statistical
   güçlenmesi**. F_ACCRUAL ve G3 binary versiyonları komposit içinde
   complementary.

2. **R&D-to-market q-factor span EDİLEMİYOR** — NDX evrene
   transferli intangibles-aware factor için kritik kanıt; Q23
   partial cevap. Lev-Sougiannis 1996 + Peters-Taylor 2017 ek ingest.

3. **FF15 RMW (Ope) dört darbede 1/4** — wiki'nin RMW factor
   exposure kararı **çift düzeltme**: HLZ multiple-testing borderline
   + HXZ q-factor span. Faz 3 strateji tasarımında RMW exposure
   target değil.

4. **Magic Formula 0/4** — wiki'nin "academic strateji baseline'a
   alınmaz" pozisyonu **dört darbe ile pekişti**.

5. **SMB 0-1/4** — wiki'de zaten "never sig under MT"; HXZ replication
   paralel kanıt.

6. **Distress anomaly virtually nonexistent** — Campbell-Hilscher-
   Szilagyi 2008 (Tier 2 #33) ingest planı için kritik bulgu;
   ingest gerekli mi sorgulanır.

## Üç-bacak epistemik omurga (Cycle 13 sentez)

> 📝 [[concepts/post_publication_decay]] sayfasındaki sentez tablosu
> + meta-not detaylı; bu sayfa özet:

Wiki'nin epistemik omurgası **üç bağımsız multiple-testing-aware
mekanizma** üzerine kurulu:

| Mekanizma | Paper anchor | Çerçeve |
|---|---|---|
| **Behavioral decay (post-pub arbitrage)** | [[mclean_pontiff_2016_post_publication_decay]] | 82-97 anomaly aggregate %35 post-pub decay (sig 1%); büyük/likit firmalarda agresif |
| **Statistical FDR filter** | [[harvey_liu_zhu_2016_multiple_testing]] | 316 factor census; geleneksel `\|t\| > 2.0` yetersiz; BHY `\|t\| > 3.0` mutlak minimum |
| **Empirik replication (methodology-robust)** | [[hou_xue_zhang_2020_replicating_anomalies]] | 447 anomaly NYSE-VW methodology'de %64-85 insig; q-factor sonrası %10 net sig |

**Üç paper birbirini complementary doğruluyor:**

1. **MP behavioral:** Post-pub arbitrage signal degradation → published
   "elite" anomaly'lerin ~%65'i hayatta
2. **HLZ statistical:** Multiple-testing düzeltmesi → factor zoo'nun
   %70+'ı false positive
3. **HXZ empirical:** NYSE-VW methodology → replication başarısızlık
   %64; Q-factor span sonra %10 net

**Wiki'nin yorumu:** Factor zoo'dan true signal ayıklamanın **üç
bağımsız mekanizması**; **üç de geçen** factorler Faz 3 strateji
tasarımı için kullanılabilir. Detay → "Dört darbe çerçevesi" sentez
tablosu [[concepts/post_publication_decay]].

## Cochrane #1 ve #3 sorularına HXZ-empirical cevap

[[cochrane2011_discount_rates]] [s.13]:

**#1 Subsumption:** Hangi factorlar bağımsız bilgi sağlıyor?
- HXZ-empirical cevap: 447 anomaly → 161 sig (klasik) → 46 q-factor
  alpha sig → factor zoo'nun %10'u net incremental information.
- HMXZ Security Analysis (Cycle 8) ile uyumlu: 6 fundamental scoring
  strategy q-factor span sonra Buffett residual + microcap residual
  hariç hepsi span ediliyor.

**#3 Parsimony (kaç factor really matter):**
- Üç-bacak omurganın HXZ ayağı: 46 q-factor alpha sig
- 6 kategori composite (momentum 0.86%, intangibles 0.85% en güçlü)
  → wiki'nin q5 + UMD + composite scoring çerçevesi parsimony
  argümanını destekliyor (K=5-10 robust factor)

## Strateji tasarımına spesifik implikasyon

Faz 3 strateji tasarımında empirik replikasyon filter **ön koşul**:

1. **Methodology default tercih:** Wiki Faz 3 backtest spec'i NYSE
   breakpoint + VW methodology kullanır (HXZ standartı). Equal-weight
   all-stocks rakamları **upper bound** referansı.

2. **Faz 3 baseline rakamları:** "Üç darbe geçenler" listesindeki
   factorler için **dört darbe filter** uygulanır. Decay-adjusted
   spread tablosuna **HXZ replication-aware kolon** eklenir.

3. **NDX intangibles factor:** R&D-to-market dört darbe geçen kritik
   kanıt; NDX evrene transferli intangibles-aware composite
   kalibrasyonu için baseline.

4. **Composite scoring strategies için Q31 kritik:** F-Score, G-Score,
   F&V/P, G&V/P explicit replication sample dışı; Faz 3 baseline
   öncesi retroactive replication test gerekli.

5. **"Capital markets are more efficient than previously reported"
   epistemik pozisyonu:** HXZ paperin ana mesajı (s.31); wiki Faz 3
   strateji baseline'ında **muhafazakâr expectation** disiplini.

## İlgili paperlar (ingested)

- [[hou_xue_zhang_2020_replicating_anomalies]] — anchor paper; 447
  anomaly NYSE-VW replikasyon; üç-bacak omurganın empirik replication
  ayağı
- [[mclean_pontiff_2016_post_publication_decay]] — behavioral decay
  bacağı; HXZ paper'da [s.3] explicit methodology eleştirisi
- [[harvey_liu_zhu_2016_multiple_testing]] — statistical FDR bacağı;
  HXZ paper'da [s.4] explicit reference; complementary frameworks
- [[hou_mo_xue_zhang_2020_security_analysis]] — paralel HXZ paper;
  Security Analysis 6 fundamental scoring + Replicating Anomalies 447
  individual = HXZ canonical pair
- [[cochrane2011_discount_rates]] — factor zoo terimi; HXZ empirik
  replikasyon ile factor zoo'nun gerçek subset'i ölçülür

## İlgili paperlar (henüz ingest edilmedi)

- Hou-Xue-Zhang (2015) "Digesting Anomalies" (Tier 1 #3) — q-factor
  model origin; HXZ 2020 q-factor framework'ünü kullanır
- Jensen-Kelly-Pedersen (2023) "Replication Crisis in Finance"
  (Tier 2 #44) — HXZ 2020'ye paralel modern güncelleme; Q33 cevabı
- Chen-Zimmermann (2022) "Open Asset Pricing" (Tier 2 #41) —
  replication database; modern data portalı
- Stambaugh-Yuan (2017) "Mispricing Factors" (Tier 1 #23) —
  composite q-anomaly aggregation methodology HXZ paper'da kullanılır
- Avramov-Cheng-Metzker (2023) (Tier 2 #43) — "ML vs Economic
  Restrictions"; replication-aware ML asset pricing
- Yan-Zheng (2017) — 18,000 fundamental signals bootstrapping
- Linnainmaa-Roberts (2016) — pre-Compustat sample RMW reddi

## İlgili kavramlar

- [[concepts/post_publication_decay]] — üç-bacak epistemik omurganın
  behavioral bacağı + dört darbe çerçevesi sentez tablosu
- [[concepts/multiple_testing]] — üç-bacak omurganın statistical
  FDR bacağı
- [[concepts/factor_zoo]] — factor zoo'nun replication crisis
  perspektifi
- [[concepts/factor_model]] — q-factor model 447 anomaly üzerinde
  performansı
- [[concepts/contextual_fundamental_analysis]] — universe-conditioned
  scoring HXZ NYSE-VW methodology ile uyum
- [[concepts/winner_loser_identification]] — top-N selection HXZ
  replication-aware filter

## Faz 3 backtest implementation

> 📝 **Cycle 21 ek (lint_pass).** Bu kavramın methodology'e geçirilmiş
> hali aşağıda; Faz 3 strategy spec'leri için somut kullanım.

**HXZ NYSE-VW replication-robust filter → [[methodology/backtest_spec]]
§4 darbe (4)**. 447 anomaly NYSE-breakpoint + value-weighted
microcap-arınmış sample'da hayatta kalma testi; "captures by q5"
durumu dolaylı kabul (factor exposure proxy uygulanabilir, alpha
kaybı caveat). **Universe methodology default → [[methodology/backtest_spec]]
§1.3**: NYSE breakpoint + VW wiki amaç evrenleri (S&P 500 + NDX)
için doğal fit; equal-weight all-stocks "exaggerated upper bound"
caveat MP↔HXZ resolution'dan.

## Forbidden claims

> ⚠️ Wiki bu sayfada yapmaması gereken claim'ler:
> 1. "HXZ replication başarısızlığı = anomaly false" — methodology
>    farkı sonucu; equal-weight all-stocks rakamları "yanlış" değil,
>    farklı methodology
> 2. "447 anomaly içinde wiki'deki paperların hepsi replicate
>    edemiyor" — Sloan accruals replicate; CGS asset growth replicate;
>    momentum replicate; sadece RMW (Ope) ve Sloan size-adj insig
> 3. "Q-factor model true filter" — q-factor span EDİLEN durumlar
>    "false" değil **risk-premium-explained**; mathematical equivalence
>    (Cochrane)
> 4. "HXZ %10 net survival rate Faz 3 baseline" — bu net q-factor
>    sonrası rakam; q-factor span EDİLEN factorler hala factor exposure
>    proxy olarak değer üretebilir

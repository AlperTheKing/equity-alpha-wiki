# Open Questions

> Wiki'de kaynaklarla cevaplanmamış sorular. Aktif liste — cevabı bulan kapatır.
> Cevaplar yazılırken hangi paper'la kapandığı belirtilir: `[ANSWERED in [[paper]]]`.

## Faz 1 başlangıç soruları (priori)

Bu sorular wiki'nin anlamlı sayılması için cevaplanmalı:

- **[Q1 fully-answered (Cycle 17, Lev-Srivastava 2020 anchor; çoklu cycle partial updates eski)]** S&P 500 evreninde value (P/B, P/E) faktörünün post-2000 performansı nedir?
  Klasik value premium large-cap'te ne ölçüde sürdü?
  _Lev-Srivastava 2020 [[lev_srivastava_2020_value_failure]] anchor cevap
  (Cycle 17):_ Paper [s.16 footnote 13] **"50% largest stocks focus"**
  (top 1500 of CRSP all-stocks; S&P 500 ≈ top 500 ⊂ subset; **adequate
  proxy**). Decade-by-decade vanilla HML returns [Figure 1]: 1970s
  +102% → 1980s +75% → 1990s -10% → 2000-2006 brief resurgence →
  **2007-2018 NEGATIVE**. **1989'dan beri faltering** (post-2007
  collapse "swan song" değil, derinleşme). **Iki sebep** [paper ana
  tezi]: (1) **accounting deficiencies (intangibles expensing)** —
  adjusted BV methodology (Lev-Sougiannis + Peters-Taylor paralel) ile
  39 yılın 34'ünde conventional'ı geçer; (2) **mean reversion slowdown
  post-2007** — rank correlation glamour 45-47% → 60%, length of stay
  value 2.5 → 3.3 yıl, 10%+ upticks/downticks 22%/18% → 10%/10%.
  Macro mekanizma: post-2007 financial crisis bank lending contraction
  + consumer demand fall → value firms (banking, retail, insurance,
  wholesale, utilities) trapped, R&D yapamıyor. **Q1 fully-answered**:
  wiki priori sorduğu temel sorunun definitive cevabı; **caveat**:
  50% largest of CRSP ≈ top 1500 ≠ exact S&P 500 (top 500); subset
  proxy. **Faz 3 implication**: vanilla HML reject; adjusted HML
  baseline (F bloğu 3 ayak methodology infrastructure ile inşa edilir).
  
  _Baseline:_ [[famafrench1993_three_factor]] HML primum'unu 1963-07/1991-12'de
  0.40%/ay (t=2.91) [Tablo 2, PDF p.13] ölçer ama post-1991 dönem yok.
  _FF15 partial update [[famafrench2015_five_factor]] [Tablo 4 Panel A, s.37]:_
  HML 1963-2013 örnekleminde 0.37%/ay (t=3.20) — primum hayatta. AMA HML 5-faktör
  altında redundant [[famafrench2015_five_factor]] [Tablo 6, s.19].
  _McLean-Pontiff 2016 [[mclean_pontiff_2016_post_publication_decay]] partial-stronger
  update [Tablo 3, s.32]:_ 82 anomaly aggregate **post-pub decay %35** (sig 1%)
  uygulanır → HML için decay-adjusted baseline ≈ 0.65 × in-sample. Limited
  arbitrage [Tablo 8] büyük/likit firmalarda decay agresif → S&P 500 large-cap
  evrene transfer için decay aggregate'tan **daha agresif** beklenir.
  _HLZ 2016 [[harvey_liu_zhu_2016_multiple_testing]] partial-stronger
  update [Şekil 3, s.22]:_ HML mark sig her cutoff'ta (Fama-French 1992
  versiyonu); FF93 origin t=2.91 BHY borderline / Bonferroni insig;
  FF15 1963-2013 t=3.20 BHY sig. **Üç darbe çerçevesi**: in-sample
  +0.37%/ay sig, post-pub decay aggregate %35, MT-corrected sample-bağımlı
  borderline-sig.
  _Lev-Sougiannis 1996 [[lev_sougiannis_1996_rd_capitalization]]
  partial-stronger update (Cycle 15) — kavramsal hazırlık:_
  Adjusted Bm dispersion azalır → traditional value premium R&D-yoğun
  firms'da yapay olabilir. [Tablo 5] upper-quartile RDC firms'da
  **B/M coefficient sig kaybediyor** (RDC/M dahil edilince) — RDC/M
  B/M'in açıklayıcı gücünü absorb ediyor; **R&D-intensive firms'da
  B/M yapay sinyal**. Lev-Srivastava 2020 (Cycle 17 ingest bekleniyor)
  post-2010 value collapse'i bu methodology üzerinden açıklayacak —
  Q1 tam cevabı için.

- **[Q2 FULLY-ANSWERED (Cycle 19, Asness QMJ 2019 anchor)]** Quality faktörü (Asness QMJ, Novy-Marx GP/A) large-cap'te value'dan daha
  güçlü kanıt sunuyor mu? Hangi alt-bileşeni en kuvvetli?
  _FF15 partial update [[famafrench2015_five_factor]] [Tablo 4 Panel A, s.37] (Cycle 4):_
  RMW (operating profitability) primum'u 0.25%/ay, t=2.92 (2x3 inşa); 2x2x2x2 joint
  kontrolde t=4.09. Bu, HML'den (t=3.20) **istatistiksel olarak en az kadar güçlü**.
  Ancak large-cap-özel ayrıştırma ve QMJ vs. GP/A vs. RMW horse race
  partial cevap.
  _HMXZ 2020 partial update [[hou_mo_xue_zhang_2020_security_analysis]] (Cycle 8):_
  Asness QMJ q-factor model REJECT (GRS p=0.00); q5 model **CAPTURES**
  (alpha 0.06% t=0.42 GRS p=0.12). Composite QMJ test; 4 dimension
  breakdown YOK.
  _Lev-Srivastava 2020 partial update [[lev_srivastava_2020_value_failure]] (Cycle 17):_
  Glamour firms 2007-2018 highest profitability since 1970 [Figure 9];
  large-cap quality dolaylı kanıt — direct test değil.
  _Asness QMJ 2019 ANCHOR cevap [[asness_frazzini_pedersen_2019_qmj]] (Cycle 19):_
  - Tablo A4 + Figure A1 **large-cap-only ayrı raporlama**
  - 23/24 country pozitif alpha (large-cap + small-cap)
  - 17/24 country 4-factor alpha sig
  - US long sample 1956-2012 4-factor alpha **66 bps/ay (t=11.20)**
  - 4 dimension breakdown (Profitability + Growth + Safety + Payout):
    her dimension US sample sig 1/3/4-factor alpha; composite QMJ "the
    strongest of the four"
  - Q49 yeni: 4 dimension'ın hangisi en güçlü large-cap'te (paper Table
    VI Panel A her dimension ayrı raporluyor; dimension-spesifik alpha
    hierarchy Faz 2 sentez)
  **Q2 fully-answered**: 13 cycle partial sonrası fully-answered. Wiki
  için sembolik kazanım. **Caveat**: monthly rebalance orijinal; annual
  uyarlama primum sensitivity test (Q35 + Q51 paralel). **Faz 3 strategy
  spec için quality factor anchor** S&P 500 + NDX large-cap evrenler
  için.

- **[Q3]** Mohanram G-Score (growth-tarafı F-Score muadili) Nasdaq 100 / tech-heavy
  evrende test edildi mi? Out-of-sample performansı?
  _Mohanram 2005 partial update [[mohanram2005_g_score]] [Tablo 5 Panel D, s.20]:_
  Hi-tech (Field-Hanka 2001 SIC kodları 357/367/369/382/384/737) altgrubunda
  spread = +17.8%, hi-tech high group +5.2% (overall low-BM mean +3.3%'in
  *üstünde*). NASDAQ partition'da spread = +26.4% (NYSE/AMEX 12.7%'in 2x'ı).
  AMA: paper sample 1979-1999, **post-2000 dönem out-of-sample** (FAANG dönemi,
  2008-2024 mega-cap tech yükselişi). Tam-NDX 100-stock test wiki'de hala yok.
  Li-Mohanram 2019 (Tier 1 #12) out-of-sample 2000-2014 dönemini kısmen
  cevaplayabilir.
  _Li-Mohanram (2019) [[li_mohanram2019_quality_value]] partial-stronger update
  [Tablo 7, s.22]:_ NASDAQ partition'da hem standalone hem combined yaklaşımlar
  significant; G&NEGPEG growth (low-BM) subsample'da 20.07% spread [Tablo 6,
  s.20]. Sample 1973-2012 → post-2000 tech bubble + 2008 kriz dahil. **NDX 100
  endeks-üyesi spesifik test yine yok** (tüm NASDAQ-listed firmalar ≠ NDX 100
  endeks); post-2014 FAANG dönemi out-of-sample.

- **[Q4 partial-stronger (Cycle 22, Israel-Moskowitz indirect anchor)]** Cooper-Gulen-Schill (2008) asset growth anomalisi large-cap'te hayatta mı?
  Decay kanıtı var mı?
  _FF15 partial update [[famafrench2015_five_factor]] [s.13]:_ CMA (asset growth
  faktörü) primum'unun büyük kısmı **küçük cap'lerden** geliyor: CMA(small) t-stat
  4.64-5.49, CMA(big) t-stat 1.03-2.00. Yani large-cap'te asset growth anomalisi
  istatistiksel olarak çok daha zayıf. Cooper-Gulen-Schill 2008 ingest'i ile
  doğrudan kanıt incelenmeli.
  _CGS-Ion 2018 partial-stronger update [[cooper_gulen_ion2018_asset_growth_factor_models]]
  [s.7]:_ Sample 1968-2016 NYSE+AMEX+NASDAQ all-stocks; explicit large-cap-only
  test paperda yok ama **size partition stats** [Tablo I] gösteriyor ki extreme
  asset growth deciles smaller, younger firmlar dominantı. Bu, anomaly'nin
  **size-loaded** olduğunu pekiştirir. Original CGS 2008 paper paywall, headline
  rakamlar wiki'de doğrulanmadı.
  _Israel-Moskowitz 2013 [[israel_moskowitz_2013_shorting_size_time]]
  partial-stronger update (Cycle 22):_ Asset growth doğrudan paper kapsamında
  yok (sadece size, value, momentum); ancak **size-loaded anomaly paterni
  86-yıl sample'da** general empirical kural [Tablo 3]: HML size Q5
  α=3.70% t=1.90 INSIG; size Q1 α=11.22% t=3.87 sig. Asset growth ile
  paralel mekanizma (size-loaded). Q4 fully-answered için CGS 2008
  orijinal paper veya Tier 2 Fairfield-Whisenant-Yohn 2003 (#37) ek
  ingest gerekli; yapısal pattern Israel-Moskowitz ile teyit edildi.

- **[Q5 fully-answered (üç-bacak epistemik omurga tüm bacaklarda); partial (anomaly-spesifik)]**
  McLean-Pontiff (2016) "Does Academic Research Destroy Stock Return
  Predictability" hangi faktörlerin post-publication decay'i en az olduğunu
  söylüyor?
  _McLean-Pontiff 2016 anchor cevabı [[mclean_pontiff_2016_post_publication_decay]]
  [Tablo 3, s.32]:_ **82 anomaly aggregate post-pub decay ≈%35 (sig 1%)**;
  statistical bias ≈%10 (insig). Decay timing yıl 3-5'te en güçlü
  (-0.577, -0.563, -0.481, p<0.05); yıl 5+ partial recovery (-0.307).
  Sample-end opportunism reddi [Tablo 4]: orijinal sample son-12-ay
  coefficient INSIG (-0.091, p=0.678). Limited arbitrage [Tablo 8]:
  büyük/likit/divid-payer/düşük-idio firmalarda decay **DAHA güçlü**
  (Size +1.442, Dollar Vol +1.380, Idio Risk -1.420, Divid +1.439, sig 1%).
  **AMA** paper 82 anomaly individual decay rakamlarını tek-tek
  raporlamaz (Internet Appendix'te); F-Score / G-Score paperin reference
  listesinde **explicit yok** — composite-score-spesifik decay aggregate
  multiplier üzerinden uygulanır.
  _Li-Mohanram (2019) [[li_mohanram2019_quality_value]] composite-score-spesifik
  somut empirik kanıt [Tablo 2, s.15-16]:_ Piotroski orijinal +23% (1976-96,
  BM-Q5, binary) → modern continuous all-firms (1973-2012) **+7.44%** = ~3x
  düşüş. Mohanram +21.2% → +6.06% ~3.5x düşüş. McLean-Pontiff aggregate %35
  + universe genişlemesi + binary→continuous + industry classification
  revision karışık etkenler — saf decay komponenti ayrıştırılmamış.
  _Sloan (1996) [[sloan1996_accruals_anomaly]] anchor:_ Sloan paperin
  reference list'inde **explicit listed** [s.28]; aggregate decay multiplier
  uygulanır → +10.4%×0.65 = +6.76% baseline; size-adj +2.9% zaten marjinal
  → large-cap evrende standalone signal yapısal silinmesi beklenir.
  _CGS-Ion 2018 [[cooper_gulen_ion2018_asset_growth_factor_models]]
  exception:_ Asset growth anomaly 1968-2016 sample'da hayatta (sample
  uzatma sonrası anlamlı); aggregate-altı decay rate → anomaly-spesifik
  görece güçlü survival.
  _HMXZ 2020 [[hou_mo_xue_zhang_2020_security_analysis]] yorum çatallanması
  [Tablo 2, s.18-19, fn 9]:_ q5 risk premium evrimi yorumu vs McLean-Pontiff
  sophisticated trader arbitrage yorumu — Cochrane mathematical equivalence
  ile her iki yorum aynı portföye götürür. Wiki taraf tutmaz.
  → **Q5 epistemik omurga olarak kapanmış sayılır**; spesifik anomaly-level
  decay literatürü Q28 ile takip edilir.
  _HXZ 2020 [[hou_xue_zhang_2020_replicating_anomalies]] partial-stronger
  update (Cycle 13):_ Üçüncü bacak (empirik replication) eklendi.
  447 anomaly NYSE-VW methodology'de %64 insig at 5%; q-factor sonra
  %10 net sig (46/447). Sloan operating accruals q-factor alpha
  -0.54% (t=-3.77) sig — **dört darbenin TAMAMINDA hayatta kalan
  nadir anomaly**. **Q5 üç-bacak epistemik omurga tüm bacaklarda
  fully-answered**.
  _Bailey-LdP 2014 [[bailey_lopezdeprado_2014_deflated_sharpe]]
  partial-stronger update (Cycle 14):_ DSR sample length düzeltmesi
  (DSR-4) ek statistical bacak; memory effects altında backtest
  overfitting "loss maximization"a yol açar [s.5] — out-of-sample
  sıfır değil negatif. MP'nin %35 aggregate decay'i bu memory
  mekanizmasıyla **kısmen** açıklanabilir. Q5'in cevabı **dolaylı**
  olarak DSR ile pekişiyor (Sharpe reporting inflation kontrolü +
  memory effects mechanism).
  _Beneish 1999 [[beneish_1999_m_score]] partial-stronger update
  (Cycle 18):_ Beneish reference list'inde **Sloan 1996 explicit
  listed DEĞİL** (Healy 1985 + Jones 1991 cite ediyor). Composite-
  score-spesifik decay aggregate multiplier üzerinden uygulanır;
  Q5 fully-answered durumu korunur. M-Score post-pub 25 yıl
  (1999-2024) sample uzatma replikasyon eksik (Q48 yeni paralel) —
  forensic detection paper, return prediction değil → decay multiplier
  uygulanması nüanslı.
  Detay [[post_publication_decay]] dört darbe çerçevesi tablosu;
  [[backtest_overfitting]] DSR + memory effects.

- **[Q6]** Gu-Kelly-Xiu (2020) ML asset pricing çalışmasında hangi feature'lar
  (geleneksel + ML-derived) en yüksek importance score'u alıyor?
  _Sloan (1996) [[sloan1996_accruals_anomaly]] partial-stronger anchor:_
  Accruals modern ML asset pricing literatüründe genelde top-importance
  feature olarak çıkar (literatürde yaygın bilgi); Sloan baseline anchor —
  Gu-Kelly-Xiu 2020 ingest'inde teyit edilecek.

- **[Q7 FULLY-ANSWERED (Cycle 26, FGX 2020 anchor)]** Feng-Giglio-Xiu (2020) "Taming the Factor Zoo" faktör redundancy
  testlerinde hangi geleneksel faktörler "incremental information" sağlıyor?
  _Feng-Giglio-Xiu 2020 [[feng_giglio_xiu_2020_factor_zoo]] anchor cevap (Cycle 26):_
  150 factor library + 750 test portfolio Jul 1976-Dec 2017 frequentist
  Double-Selection LASSO methodology + Fama-MacBeth two-pass.
  - **[Tablo 1] since-2012 factors DS-sig**: RMW (FF profitability) + ROE (HXZ profitability) + IA (HXZ investment) + QMJ (Asness Quality Minus Junk) + intermediary investment (He-Kelly-Manela 2016)
  - **Diğer son-5-yıl factor'ler redundant**: CMA (FF investment), BAB (Frazzini-Pedersen), convertible debt, vb.
  - **[Tablo 2] recursive 1994-2016**: 150 factor → **17 factor sig** (%11); majority redundant veya useless
  - **SDF loading vs risk premium kritik epistemic point** [s.22]: about half of factors INSIG risk premium FGX sample'da; pricing contribution ≠ factor mean return; HXZ 2017 paterni teyit
  - Heston-Sadka seasonality pedagogical anchor [s.4]: FF3 α t=2.06 sig vs Carhart 4F α t=−0.87 INSIG (momentum 0.63 correlated → spurious)
  **Q7 fully-answered**; D bloğu epistemik omurga statistical bacağı 2 paper sertleştirme (HLZ 2016 + FGX 2020 iki paralel frequentist methodology).

- **[Q8]** Sektör nötrleştirmesi olmadan factor portfolio yıllık-rebalans'ta hangi
  noktalarda başarısız oluyor? (Tech-heavy Nasdaq 100 için kritik.)

- **[Q9 partial-stronger (Cycle 18, Beneish 1999 anchor; Cycle 38 Ball-GLN Cop subsumes accruals; Cycle 39 Stambaugh-Yuan composite scoring paradigm cross-evidence)]** Beneish M-Score earnings manipulation filtresi olarak F-Score/G-Score
  ile kombine edildiğinde performans değişiyor mu?
  _Beneish 1999 [[beneish_1999_m_score]] anchor cevap (Cycle 18):_
  Paper combined backtest YAPMIYOR (forensic detection paper, factor
  combination test değil). 8-bileşenli M-Score (5 sig + 3 insig);
  pseudo-R² 30.6% / 37.1%; holdout sample ~50% manipulators identification.
  **Wiki için F & M / G & M screen-and-rank combined yaklaşım Faz 3
  design adayı**: M-Score yüksek olanlar evrenden çıkar (filter),
  sonra F-Score / G-Score / F&V/P / G&V/P winner-loser scoring.
  **Tam cevap için modern combined empirical test eksik**:
  - Beneish-Lee-Tarpley 2001 (paywall hala) M-Score → return prediction
    direct evidence; wiki'de yok
  - Gray-Carlisle 2012 "Quantitative Value" (Tier 3 kitap) F + M
    combined yaklaşım pratiği; akademik backtest değil
  - Faz 2 sentez aşamasında modern data (Chen-Zimmermann 2022 + JKP
    2023) ile combined backtest gerekli
  Q9 partial cevap; **Q47 ile birlikte değerlendirilir** (tech firma
  M-Score false positive riski; G-Score growth firmalar evrendir →
  SGI yapısal yüksek → M-Score yapay yüksek).

- **[Q10]** Fundamental data reporting lag (10-K filing gap) için literatürde
  konsensus kaç gündür? PIT vs. as-reported farkı backtest sonucunu ne kadar değiştirir?

## Ingest sırasında eklenen sorular

- **[Q11 fully-answered (statistical düzeyde); partial (behavioral düzeyde); ASTERISK üç-paper sertleştirme: Cycle 19 Asness QMJ + Cycle 22 Israel-Moskowitz 86-yıl + Cycle 39 Stambaugh-Yuan modified SMB ~2x premium]**
  [[famafrench1993_three_factor]] örneklemi 1963-07 / 1991-12. SMB
  [Tablo 2, PDF p.13] orijinal örneklemde t-stat 1.73 ile zaten marjinal. SMB'in
  post-1991 ve özellikle post-2000 dönemde large-cap evrende relevance'ı nedir?
  _HLZ 2016 [[harvey_liu_zhu_2016_multiple_testing]] [Şekil 3, s.22] full
  cevap (statistical):_ **SMB never sig under multiple testing**
  (Bonferroni / Holm / BHY hepsi insig); FF93 t=1.73 marjinal sig'in
  multiple-testing-corrected **kesin çürütülmesi**. Wiki'nin SMB factor
  exposure'ı strateji tasarımı için "target" değil; factor-model
  baseline'da kalır. Behavioral decay (post-pub) için Hou-Xue-Zhang 2020
  (Replicating Anomalies, Tier 1 #18) ek ingest tamamlar.
  _Asness QMJ 2019 [[asness_frazzini_pedersen_2019_qmj]] ASTERISK update
  (Cycle 19):_ Paper Section 8 + Table IX **SMB resurrection finding**:
  vanilla SMB controlling MKT + HML + UMD insig α=13bps → **controlling
  MKT + HML + UMD + QMJ sig α=64bps (t=6.39)**. Wiki için: Q11
  fully-answered durumu **vanilla SMB için korunur**; **quality-controlled
  SMB ayrı boyut** — fully-answered "with asterisk: resurrection under
  QMJ control". SMB factor exposure pozisyonu Faz 3 spec'inde quality-
  aware revisit. Çelişki değil, complementary methodology farkı (no
  quality control vs quality-controlled).
  _Israel-Moskowitz 2013 [[israel_moskowitz_2013_shorting_size_time]]
  86-yıl confirmation (Cycle 22):_ Paper [Tablo 1] full sample
  1926-2011 (86 yıl) SMB CAPM α=2.05% t=1.72 INSIG; 1926-1962 sub-sample
  α=0.70% t=0.33 INSIG; 1963-2011 sub-sample α=3.08% t=2.30 marjinal
  sig. **86-yıl confirmation ile statistical bacak (HLZ MT) + extended
  empirical sample (Israel-Moskowitz) çift kanıt**. Q11 fully-answered
  ASTERISK durumu **iki farklı methodology'de** desteklenmiş:
  multiple-testing düzeltmesi + 86-yıl extended sample CAPM α direct
  test. Quality-controlled resurrection asterisk korunur.

- **[Q12]** [[famafrench1993_three_factor]] HML ve SMB inşası NYSE breakpoint'leri
  kullanır (size median; BE/ME 30/70). NYSE breakpoint asimetrisi nedeniyle SMB
  ağırlıklı olarak microcap dinamiklerini yansıtır [PDF p.8-9]. **S&P 500 ve Nasdaq
  100 evrenleri için HML/SMB faktörleri *evren-özel* breakpoint'lerle yeniden
  inşa edilmeli midir?** Eğer evet, hangi breakpoint mantığı (örn. S&P 500 içi
  median ME)? Bu bir tasarım sorusu — ingest'le değil [[wiki/strategies/]] tasarımı
  ile cevaplanır, ama gerekli kararı belirlemek için faktör korelasyon kanıtları
  literatürden taranabilir.

- **[Q13]** [[famafrench2015_five_factor]] s.4'te HML redundancy iddiasının
  "may be specific to this sample" uyarısı var. **HML redundancy pre-1963 ABD,
  uluslararası örneklemler ve post-2013 dönemde sürer mi?** FF15 yazarları
  açıkça açık bırakıyor. Hou-Xue-Zhang 2015 ve Hou-Xue-Zhang 2020 (Replicating
  Anomalies) ingestleri ile cross-check.

- **[Q14 fully-answered (Cycle 37, FF 2008 ANCHOR + üçlü teyit Israel-Moskowitz + HXZ 2015)]** [[famafrench2015_five_factor]] 5F modelin başarısız olduğu portföy
  küçük cap × low-OP × high-Inv [Tablo 11, s.26]. **Bu başarısızlık S&P 500 /
  Nasdaq 100 evrenleri (large-cap-only) için kalkar mı?** Eğer evet, 5F bu wiki'nin
  amacı için **3F'den daha güvenilir** baseline olabilir.
  _Asness QMJ 2019 partial-stronger update [[asness_frazzini_pedersen_2019_qmj]] (Cycle 19):_
  QMJ paper FF5 başarısızlık portföyü (small × low-OP × high-Inv)
  **DIRECT TEST ETMIYOR** — 4-factor (Carhart) baseline kullanıyor.
  AMA Tablo A4 + Figure A1 large-cap-only test: 23/24 country pozitif
  alpha; 17/24 country sig 4-factor alpha → **FF5 başarısızlık portföyünden
  farklı evrene transfer mümkün** (FF5 başarısızlık küçük cap; QMJ
  large-cap-only sig). Yapısal kanıt: large-cap evrende quality factor
  (QMJ) sig pozitif alpha üretiyor → FF5 RMW (FF15 1 measure) +
  QMJ Profitability (6 measure) birlikte large-cap quality factor
  exposure target alınabilir.
  _Israel-Moskowitz 2013 ⭐ DIRECT KANIT [[israel_moskowitz_2013_shorting_size_time]]
  (Cycle 22):_ Paper [Tablo 3] **size×value direct decomposition**
  86-yıl: HML 5-1 spread CAPM α(largest Q5) = 3.70% t=1.90 INSIG;
  α(Q4) = 4.24% t=1.93 marjinal; α(Q3) = 5.42% t=2.96 sig; α(Q2) =
  7.28% t=3.88 sig; α(Q1) = 11.22% t=3.87 sig. **Vanilla HML largest
  40% NYSE stocks'ta INSIG**. CMA + RMW direct test paperde yok ama
  HML için direct test fully-answered: **vanilla BE/ME large-cap'te
  yapısal başarısızlık**. Çıkarım: HML reject; FF5 large-cap'te 4F
  effective (RMW + CMA hayatta + HML drop). FF5 vs FF3 large-cap-spesifik
  baseline kararı için CMA/RMW direct test eksikliği kalıyor — Q14
  HML için fully-answered, CMA/RMW için partial-stronger; AQR data
  setleri (Tier 3 #55) + Hou-Xue-Zhang 2015 q-factor origin (Tier 1
  #3) ek ingest tam cevap için.

- **[Q15 fully-answered (Cycle 35, HXZ 2015 anchor)]** Hou-Xue-Zhang q-factor modeli (HXZ4: MKT, ME, ROE, IA) FF5 ile
  paralel olarak HML'siz 4-faktör çerçevesi öneriyor [[famafrench2015_five_factor]] s.29
  not. **Doğrudan FF5 vs. HXZ4 horse race ne sonuç veriyor?**
  _HXZ 2015 ANCHOR cevap [[hou_xue_zhang_2015_q_factor]] (Cycle 35):_
  Paper [Section 3 + Section 6 Conclusion] explicit FF/Carhart vs q-factor
  horse race PEAD/IVOL/distress/net issues subsumption test:
  - PEAD/SUE h-l: FF α 0.54% (t=4.26) → Carhart 0.32% (t=2.43) → **q-factor 0.14% (t=0.92) INSIG**
  - IVOL h-l: FF α -0.91% (t=-4.48) → Carhart -0.58% (t=-2.59) → **q-factor -0.04% (t=-0.19) INSIG**
  - Distress h-l: FF α -1.43% (t=-5.21) → Carhart -0.55% (t=-2.51) → **q-factor 0.02% (t=0.07) INSIG**
  - Net stock issues h-l: FF -0.62% (sig) → Carhart -0.57% (sig) → q-factor -0.32% (t=-2.10; 44% reduction still sig)
  - 25 size×B/M m.a.e.: FF 0.10 / Carhart 0.11 / q-factor 0.12 (comparable)
  - 25 size×momentum m.a.e.: FF 0.22 / Carhart 0.11 / q-factor 0.11 (identical)
  - **Sloan accruals h-l EXCEPTION**: FF -0.29% (t=-1.96) / Carhart -0.29% (t=-1.69) / q-factor -0.39% (t=-2.48) **q-factor WORSE** (ROE factor wrong direction)
  Cochrane 2011 #1-#3 sorularına explicit cevap [Section 6]: 15 anomaly
  K=4 factor subsumption (investment subsumes B/M + net stock issues +
  accruals + market leverage + long-term reversal + E/P + composite
  issuance; ROE subsumes short-term prior returns + earnings surprise +
  financial distress). **Q15 fully-answered**: q-factor outperforms
  FF/Carhart 5/6 anomalies (Sloan accruals exception). Q15a yeni soru:
  q-factor Sloan accruals exception scope-dependent yorum mı yoksa
  structural limit mi? (F bloğu intangibles + Profitability zinciri Cop
  ortogonal complement Faz 3 strategy spec'lerinde dokümante).
  _HLZ 2016 [[harvey_liu_zhu_2016_multiple_testing]] partial-stronger update
  [Şekil 3, s.22]:_ FF5 faktörlerinin multiple-testing-corrected sig
  durumu **karışık**: HML (1963-2013 t=3.20) BHY sig / Bonferroni
  borderline; **RMW (2x3 t=2.92) BHY borderline / Bonferroni insig**;
  RMW (joint t=4.09) sig her cutoff; CMA (2x3 t=4.07) sig her cutoff;
  CMA (joint t=2.71) BHY borderline / Bonferroni insig. **Modelin yarısı
  multiple-testing-corrected zayıf** ama joint kontrol + incremental
  information argümanları modeli ayakta tutuyor. Q15 tam cevabı için
  HXZ 2015 q-factor origin paperı ingest'i hala gerekli; HLZ kanıtı
  q5 ve FF5'in **bireysel bileşen düzeyinde** statistical filter
  durumlarını netleştirir.
  _HMXZ 2020 [[hou_mo_xue_zhang_2020_security_analysis]] partial-stronger update
  [Tablo 4, s.21]:_ Asness QMJ q-factor model tarafından REJECT (GRS p=0.00) ama
  q5 model (q4 + expected growth) **CAPTURES** (alpha 0.06%, t=0.42, GRS p=0.12).
  Bu, q5'in expected growth faktörünün FF5'in HML+CMA'sını aşan açıklayıcı güç
  taşıdığını gösteren parçalı kanıt. Tam horse race FF5 vs q4/q5 ile yanyana
  comparison hala wiki'de yok; Hou-Xue-Zhang 2015 ingest'i ile.
  _Asness QMJ 2019 partial-stronger ileri (Cycle 19):_ QMJ paper kendi
  4-factor (Carhart) lens'inde sig (alpha 66 bps/ay t=11.20 US long
  sample); HMXZ Tablo 4 q5 captures (alpha 0.06% t=0.42). **İki paper
  farklı methodology**: QMJ Carhart lens vs HMXZ q5 lens; tam horse
  race (FF5 vs q5 vs Carhart) hala eksik. HXZ 2015 q-factor origin
  paper bekliyor (Tier 1 #3).

- **[Q16]** [[carhart1997_four_factor]] [Tablo II, s.62] UMD/PR1YR primum'u
  0.82%/ay (t=4.46) — Carhart örnekleminin en güçlü faktörü. **Yıllık-rebalanced
  + value-weight + S&P 500 evren versiyonunda UMD primum'u ne ölçüde hayatta?**
  Carhart orijinali aylık rebalance + equal-weight + tüm-evren — bu wiki'nin
  amacıyla doğrudan transferli değil. Daniel-Moskowitz 2016 (momentum crashes),
  Frazzini-Israel-Moskowitz 2018 (trading costs), Asness-Frazzini-Pedersen 2019
  (QMJ) ingestleri kanıt sağlamalı.
  Ek alt-soru: Carhart 4F vs. FF5 vs. HXZ4 doğrudan horse race wiki'de yok —
  Q15 ile bağlantılı.

- **[Q17 partial-stronger update]** [[cochrane2011_discount_rates]] [s.13] 3. sorusu: "How many of these
  new factors are really important? Can we account for N independent dimensions
  of expected returns with K << N factor exposures?" **Akademik literatürdeki
  300+ önerilmiş faktörden kaç tanesi gerçekten replicate ediyor?** Kaç tanesi
  multiple-testing ile düzeltilince ayakta kalıyor? Hou-Xue-Zhang 2020
  ("Replicating Anomalies"), Harvey-Liu-Zhu 2016, Jensen-Kelly-Pedersen 2023
  ingestleri ile cevap.
  _HMXZ 2020 [[hou_mo_xue_zhang_2020_security_analysis]] partial-stronger update:_
  q5 5-faktör model **6 popüler security analysis stratejisini büyük ölçüde
  açıklar** (mikrocap residual hariç) [Tablo 1-7]. Yani fundamental scoring
  kolonunda parsimony argümanı güçleniyor: K=5 (q5) factor'ün N>>5 anomalies'i
  kapsadığı somut kanıt.
  _McLean-Pontiff 2016 [[mclean_pontiff_2016_post_publication_decay]]
  partial-stronger update [Tablo 3, s.32]:_ 82 anomaly **aggregate %65 hayatta**
  (decay-adjusted) — yani factor zoo'nun büyük kısmı **gerçek** ama post-pub
  zayıflıyor. Statistical bias %10 (insig) → data-mining hipotezi reddediliyor.
  Sample-end opportunism reddi [Tablo 4]. **Cochrane #3 cevabı:**
  decay-adjusted parsimonious altküme K=5-10 robust factor (q5 + momentum +
  complementer composite scores) yeterli olabilir.
  _HLZ 2016 [[harvey_liu_zhu_2016_multiple_testing]] partial-stronger update
  [Şekil 3, s.22] (Cycle 12, statistical bacak):_ 316 factor census +
  multiple-testing düzeltmesi → BHY-FDR-1% ile ~10-30 surviving;
  Bonferroni ile ~9. Cochrane #3 cevabı **çift-bacak**: behavioral
  decay (MP %65 hayatta) + statistical FDR (HLZ ~%10-30 sig) birlikte
  → factor zoo'nun **gerçek replicable subset'i K=10-30 arası**.
  _HXZ 2020 [[hou_xue_zhang_2020_replicating_anomalies]] partial-stronger
  update (Cycle 13, empirik replication bacağı):_ 447 anomaly NYSE-VW
  methodology'de 161 sig (%36); q-factor sonra **46 net sig (%10)**.
  6 kategori composite (momentum 0.86%, intangibles 0.85% en güçlü).
  Cochrane #3 cevabı **üç-bacak** olarak tamamlandı: behavioral decay
  (MP %65 hayatta) + statistical FDR (HLZ ~%10-30 sig) + empirical
  replication (HXZ %10 net sig).
  → **Q17 fully-answered** (üç-bacak epistemik düzeyde); spesifik
  anomaly-level subsumption haritası için Q34 paralel.
  _Bailey-LdP 2014 [[bailey_lopezdeprado_2014_deflated_sharpe]]
  partial-stronger update (Cycle 14):_ DSR backtest overfitting
  Sharpe-spesifik dolaylı 4. ayak; aynı extreme value theory
  HLZ Bonferroni framework'üne paralel. Cochrane #3 cevabı
  dört-paper omurganın Sharpe-spesifik dolaylı 4. ayağı (5. darbe
  AÇILMADI ama methodology infrastructure olarak Faz 3 spec'inde).

- **[Q18]** [[piotroski2000_f_score]] [Tablo 4, s.19] **F-Score'un large-cap
  (top size tercile) evrende High-Low spread'i istatistiksel olarak anlamlı
  değil** (0.152, t=1.88, p=0.224 vs Small 0.270 t=4.71). Bu wiki'nin amacı
  S&P 500 / Nasdaq 100 — yani large-cap-only evrenler. **F-Score'un large-cap'e
  transferi için hangi yapısal değişiklikler gerekli?**
  Adaylar:
  1. Sektör nötrleştirme (large-cap evrende sektörel baseline farkı)
  2. Universe-spesifik breakpoint (CRSP all-stocks değil, S&P 500 / NDX içi)
  3. Evren-spesifik bileşen ağırlıkları (factor analysis ile binary equal-weight
     yerine optimum)
  4. Growth tarafı için Mohanram G-Score paralel kalibrasyonu (NDX-friendly)
  _Mohanram 2005 partial update [[mohanram2005_g_score]] [Tablo 5 Panel A, s.17]:_
  G-Score large-cap'te spread 19.8% sig 1% — yani **growth-side için F-Score'un
  large-cap zayıflığı G-Score tarafından çözülüyor**. Yani S&P 500 (mixed/value)
  için F-Score-adaptasyonu açık problem; Nasdaq 100 (growth) için G-Score doğal
  aday. Li-Mohanram 2019, Piotroski-So 2012 ingestleri ile cevap.
  _Li-Mohanram (2019) [[li_mohanram2019_quality_value]] partial-stronger update
  [Tablo 7, s.22]:_ F-Score standalone large-cap'te zayıf (4.43%); ama
  **F & V/P combined large-cap'te 11.92%, +7.49% improvement**. Yazar [s.22]:
  "strong performance of combined strategies in subset of large firms is
  especially important, as it suggests that such a strategy is likely to be
  implementable". **Combined yaklaşım** Q18'in 4 yapısal değişiklik adayı
  arasından **value-skor (V/P) ile çapraz birleştirme** çözümünün empirik
  kanıtıdır. S&P 500 stratejisi için F&V/P doğal aday.

- **[Q19]** [[mohanram2005_g_score]] G-Score'un 6 sinyali 2-digit SIC
  industry-median'a göre level [s.8]. **NDX 100-stock evrende sektör çeşitliliği
  zayıf** (>%70 firma SIC 73x software / 357 hardware altında olabilir) →
  industry-median az gözlemden hesaplanır, noise'lu. **Nasdaq 100 evrene
  transferde hangi sektör sınıflandırma kullanılmalı?**
  Adaylar:
  1. GICS Level-2 (çok kaba)
  2. GICS Level-4 (çok rafine, n<5 risk)
  3. Universe-içi median (sektörsüz)
  4. Hibrit: GICS-3 + min-n eşiği altında universe-median fallback
  Bu Q19 Faz 3 tasarım kararı; literatürde sistematik tartışma yok, çoğu paper
  CRSP all-stocks evrende çalışıyor.

- **[Q20]** [[mohanram2005_g_score]] sample 1979-1999. **G-Score post-2000
  tech bubble dönemine, özellikle 2010-2024 FAANG-dominant NDX'e transferli mi?**
  Li-Mohanram 2019 (Tier 1 #12) bu boşluğun bir kısmını adresler (2000-2014
  out-of-sample). 2014 sonrası ve mega-cap tech dönemi için modern data ile
  replikasyon gerekli — wiki'de henüz yok.
  _Li-Mohanram (2019) [[li_mohanram2019_quality_value]] partial-stronger update
  [Tablo 2, s.15-16]:_ Sample 1973-2012 — G-Score continuous Q5-Q1 spread
  +6.06%, post-2000 dönem dahil. Ancak orijinal +21.2%'den 3x düşüş; **sebep
  multi-faktörlü** (post-publication decay + universe genişlemesi + binary→
  continuous + industry classification revision). Saf decay etkisi
  ayrıştırılmamış. Post-2014 FAANG dönemi yine out-of-sample.

- **[Q21]** [[li_mohanram2019_quality_value]] [s.13, s.29] **Combined skor
  methodology belirsizliği:** Li-Mohanram simple quintile-intersection
  kullanıyor ("long Q5 of both, short Q1 of both"). Yazar [s.29] explicit:
  "no effort to determine optimal weight". Alternatif kombinasyon yöntemleri:
  1. Continuous-rank product (her firma için F-rank × V/P-rank)
  2. Factor-analysis-based optimal ağırlıklandırma
  3. ML-tabanlı (cross-validated) ağırlıklandırma
  4. Sıralı filter (önce F-Score Q5, sonra içinden V/P Q5)
  Faz 3 strateji tasarımı için karar noktası; literatürde sistematik
  karşılaştırma yok.

- **[Q22]** [[li_mohanram2019_quality_value]] sample sonu 2012. **F-Score,
  G-Score ve combined stratejilerin post-2014 (özellikle 2015-2024 mega-cap
  dominant FAANG dönemi) replikasyonu yapılmamış.** Modern data ile
  out-of-sample test gerekli. Chen-Zimmermann 2022 Open Source Cross-Sectional
  Asset Pricing (Tier 2 #41) güncel data sağlayabilir; Faz 3'te methodology
  sayfası açıldığında değerlendirilecek.

- **[Q23 partial-stronger update (Cycle 15+16+17)]** [[hou_mo_xue_zhang_2020_security_analysis]] q5 model investment
  factor (I/A) ham total asset growth — **R&D capitalization yapmıyor.** NDX
  tech-heavy evrene transfer için intangibles-adjusted q5 versiyonu
  literatürde var mı?
  _Lev-Sougiannis 1996 [[lev_sougiannis_1996_rd_capitalization]]
  partial-stronger update:_ R&D capitalization methodology partial cevap;
  paper q-factor model öncesi 1996 ama R&D capitalization methodology
  HXZ 2020 R&D-to-market q-factor alpha sig (4/4 dört darbe)
  bulgusunun **altyapısı**. Industry-spesifik amortization rates
  ([Tablo 3, s.121] 5-9 yıl useful life) NDX evrende GICS mapping ile
  uygulanabilir.
  _Peters-Taylor 2017 [[peters_taylor_2017_intangible_capital]]
  partial-stronger ileri (Cycle 16):_ Total q proxy [Eq. 9]
  `q^tot = V/(K^phy + K^int)` HXZ q-factor I/A yerine intangibles-
  adjusted I/A önerir. K^int = Knowledge (R&D perp inv, BEA δ) +
  Organization (SG&A 30% perp inv) + External (`intan` balance sheet);
  Lev-Sougiannis R&D-only methodology'sinin **strict generalization'ı**.
  ρ² (q proxy quality) **+21% iyileşme** standard q'ya kıyasla.
  Sürpriz bulgu [Section 5]: q theory daha iyi fits intangibles-yoğun
  firms — NDX (tech/health-care dominant) yapısal olarak natural
  evren.
  _Lev-Srivastava 2020 [[lev_srivastava_2020_value_failure]] partial-
  stronger ileri (Cycle 17):_ F bloğu 3 ayak methodology infrastructure
  tamamlandı (Lev-Sougiannis R&D-only + Peters-Taylor total + Lev-
  Srivastava post-2010 application). NDX strategy spec için methodology
  hazır. **Tam Q23 cevabı**: modern q-factor implementation +
  Peters-Taylor methodology entegrasyonu yapan paper wiki'de hala yok
  (Faz 2 aday); methodology infrastructure tam hazır Faz 3 backtest
  spec için.

- **[Q24]** q5 vs FF5 **doğrudan horse race wiki'de hala açık.**
  [[hou_mo_xue_zhang_2020_security_analysis]] q5 lens'ini bireysel security
  analysis stratejilerinde test ediyor ama FF5 ile head-to-head karşılaştırma
  sunmuyor. QMJ q-factor reject + q5 capture örneği parçalı kanıt sağlar
  (Q15 ile bağlı). Hou-Xue-Zhang 2015 q-factor origin paperı ingest edildiğinde
  tam cevap.

- **[Q26]** [[sloan1996_accruals_anomaly]] sample 1962-1991, NYSE+AMEX —
  modern intangibles dönemi öncesi. **Tech firmalarda accrual ölçümü R&D
  giderleştirmesi nedeniyle distorted olabilir.** Bir tech firma yüksek
  R&D yapsa muhasebe kuralı ile expense edilir → working capital değişimi
  küçük → "accrual" ölçüsü düşük çıkar. Ama capex agresif olsa accrual
  pozitif olur. **NDX tech-heavy evrene transfer için kalibrasyon farkı
  bekleniyor.** Lev-Sougiannis 1996 (Tier 2 #26), Peters-Taylor 2017
  (Tier 2 #27) ingestleri ile R&D-adjusted accrual versiyonu
  değerlendirilebilir.
  _CGS-Ion 2018 partial-stronger update [[cooper_gulen_ion2018_asset_growth_factor_models]]
  [s.5-6]:_ **Sürprizli bulgu** — intangibles düzeltmesi (Peters-Taylor 2017
  total capital metodu) asset growth factor'ün performansını **GÜÇLENDİRMİYOR**
  (HXZ + total capital 5/35 → 23/35 unexplained anomaly). Yani NDX evrene
  transfer için "intangibles düzelt" yaklaşımı naif olabilir; tech firma
  asset growth ölçümü için **yeni metodoloji** gerekli. Q26 paralel olarak
  accrual ölçümü için de aynı sorun; iki anomaly aynı yapısal challenge
  ile karşılaşıyor.
  _Lev-Sougiannis 1996 [[lev_sougiannis_1996_rd_capitalization]]
  partial-stronger update (Cycle 15) — Q26 mekanizma cevabı:_
  R&D giderleştirme tek-yıllık expense → working capital değişimi
  azalır → traditional Sloan accruals "düşük accrual" gösterir
  (gerçekte capex-tipi yatırım, useful life 5-9 yıl
  [Tablo 3, s.121]). Adjusted Sloan accruals = traditional + (RD_t -
  RA_t) → tech firma signal düzeltilir. Detay
  [[concepts/intangibles_adjusted_accounting]] +
  [[concepts/earnings_quality]] intangibles-related accruals boyutu.
  _Peters-Taylor 2017 [[peters_taylor_2017_intangible_capital]]
  partial-stronger ileri (Cycle 16):_ Lev-Sougiannis R&D-only
  adjustment'a **organization capital + advertising adjustment**
  ekler. Adjusted Sloan accruals = traditional + (RD_t - RA_t) +
  (advertising_t - amortized_advertising_t) + (SG&A_org_t -
  amortized_SG&A_org_t). NDX FAANG/tech-heavy firmlarda intangibles
  capital büyük kısmı SG&A flow + `intan` balance sheet'ten geldiği
  için Peters-Taylor methodology Lev-Sougiannis'ten **önemli ölçüde
  daha kapsamlı**. Q26 partial-stronger ileri; total intangibles
  methodology Q26 kapanışına yakın; modern data + factor portfolio
  test eksik (Faz 2 aday).
  _Lev-Srivastava 2020 [[lev_srivastava_2020_value_failure]] partial-
  stronger ileri (Cycle 17):_ 3-katmanlı methodology (Lev-Sougiannis
  R&D-only + Peters-Taylor total + Lev-Srivastava post-2010 application)
  tam tamamlandı. Lev-Srivastava [Section 6] adjusted earnings
  methodology = "adding back to earnings the annual R&D expense and
  the part of SG&A related to intangibles, and subtracting from
  earnings the annual amortization of the R&D and SG&A capitals" —
  Sloan accruals revize için tam direkt formülasyon. **Q26 kapanışına
  çok yakın**; yine modern factor portfolio test eden paper eksik
  (Faz 2 aday).
  _Beneish 1999 [[beneish_1999_m_score]] partial-stronger ileri
  (Cycle 18):_ M-Score 8 bileşeni traditional accounting'e dayalı,
  intangibles-aware DEĞİL. Tech firma high SGI (sales growth) +
  high AQI (non-current ex-PPE / TA) → **false positive yapısal
  riski** (manipulator yanlış sınıflandırma). F bloğu 3 ayak
  methodology (Lev-Sougiannis + Peters-Taylor + Lev-Srivastava)
  M-Score'a entegre edilmemiş. **Q47 yeni paralel**: NDX evren
  M-Score intangibles-aware revize Faz 3 design ön koşul.

- **[Q27]** Investment-q reaction (Cochrane 1991, Lyandres-Sun-Zhang 2008
  q-theory of investment) vs CGS mispricing yorumu: **Asset growth
  anomaly'nin mekanizması rational q-theory ile açıklanır mı, yoksa
  Lakonishok-Shleifer-Vishny tarzı mispricing mi?**
  _Mevcut kanıt:_ [[cooper_gulen_ion2018_asset_growth_factor_models]] [s.3-4]
  q-factor model'in açıklayıcı gücünün CGS asset growth ölçüsüne kritik
  bağlı olduğunu gösteriyor; geleneksel investment measures (CAPX, PPE)
  ile reproduce edilemiyor. Bu, "saf rational investment-q reaction"
  yorumunun yetersiz olduğunu ima eder ama **explicit mekanizma testi yok**.
  _Gerekli kanıt:_ Lyandres-Sun-Zhang 2008 (Tier listesinde değil) ve
  Hou-Xue-Zhang 2015 q-factor origin paperı ingestleri ile rational vs
  mispricing horse race. Ek olarak Fairfield-Whisenant-Yohn 2003 (Tier 2 #37)
  accrual + asset growth decompose ederek mekanizma alt-bileşenlerini ayırır.

- **[Q25]** Mohanram G-Score q5 lens'inde **TEST EDİLMEDİ.**
  [[hou_mo_xue_zhang_2020_security_analysis]] paperı F-Score, V/P, Magic
  Formula, QMJ vb. test ediyor ama Mohanram G-Score kapsamı dışı. **G-Score'un
  q-factor model lens'inde durumu wiki'de bilinmiyor.** F-Score patternin
  (microcap hariç q5 ile span) G-Score için tekrarlanırlığı doğrulanmamış —
  Mohanram industry-median + R&D/capex/advertising sinyallerinin q5 expected
  growth factor'u ile ortogonality'si açık soru. Direct test wiki'de eksik;
  Tier 2 #45 Freyberger-Neuhierl-Weber 2020 nonparametric characteristics
  testleri kısmi cevap sağlayabilir.

- **[Q28]** Modern post-2012 anomaly decay replikasyonu:
  [[mclean_pontiff_2016_post_publication_decay]] sample 2011'de bitiyor; 82
  anomaly aggregate %35 decay (sig 1%) bu sample dönemine ait. **Modern
  dönem (FAANG yükselişi 2014-2024, ML feature explosion, COVID-19 macro
  shocks) için aggregate decay rakamı henüz wiki'de yok.** Üç paper
  ortaklaşa cevap sağlar:
  1. **Hou-Xue-Zhang 2020 "Replicating Anomalies" (Tier 1 #18):**
     ~447 anomaly replikasyonu, McLean-Pontiff'i büyük örneklemde tekrarlar
  2. **Chen-Zimmermann 2022 "Open Asset Pricing" (Tier 2 #41):**
     replikasyon database, modern data
  3. **Jensen-Kelly-Pedersen 2023 "Replication Crisis in Finance"
     (Tier 2 #44):** modern güncelleme, ML-aware framework
  Q28 D bloğu boyunca ingest edilince tam cevap.

- **[Q29]** Limited arbitrage NDX implikasyonu:
  [[mclean_pontiff_2016_post_publication_decay]] [Tablo 8, s.37] post-pub
  decay büyük (Size +1.442), likit (Dollar Vol +1.380), divid-payer
  (+1.439), düşük-idio (-1.420) firmalarda **DAHA güçlü** (limited arbitrage
  hipotezi). **Wiki'nin amaç evrenleri (S&P 500 + özellikle NDX) tam olarak
  bu profilin uç ucunda → decay aggregate %35'ten daha agresif (örn. %50)
  beklenir hipotezi.** Ama empirik doğrudan kanıt wiki'de yok — McLean-Pontiff
  CRSP all-stock universe; NDX-only sub-sample testi paperda yok.
  **Kritik: F-Score zaten in-sample large-cap'te zayıf
  ([[piotroski2000_f_score]] [Tablo 4] +0.152 t=1.88 insig);
  post-pub decay agresif → "çift darbe" yapısal risk.**
  [[post_publication_decay]] decay-adjusted spread tablosunda **NDX
  agresif sensitivity ×0.50** Faz 3 stress-testi olarak tutulur, baseline
  değil. Tam cevap için Lev-Srivastava 2020 (Tier 2 #30) post-2010
  value-spesifik decay + Chen-Zimmermann 2022 modern NDX replikasyon.

- **[Q30]** HLZ sample sonu 2014, post-2014 yeni faktörlerin
  multiple-testing-corrected hayatta kalma oranı:
  [[harvey_liu_zhu_2016_multiple_testing]] [Şekil 3] 2032 projeksiyon
  Bonferroni 4.00; gerçek post-2014 dönem (FAANG yükselişi, ML feature
  explosion, COVID-19 macro shocks) rakamları wiki'de yok. Q28
  (post-2012 modern anomaly decay) ile kısmen overlap ama HLZ tarafı
  **multiple-testing methodology bacak**. Üç paper ortaklaşa cevap:
  1. Hou-Xue-Zhang 2020 "Replicating Anomalies" (Tier 1 #18) —
     ~447 anomaly multiple-testing-aware replikasyon
  2. Jensen-Kelly-Pedersen 2023 (Tier 2 #44) — "Replication Crisis
     in Finance" modern güncelleme; HLZ + MP + HXZ 2020 sentezi
  3. Avramov-Cheng-Metzker 2023 (Tier 2 #43) — "ML vs Economic
     Restrictions"; HLZ-aware ML asset pricing
  D bloğu boyunca + ML asset pricing (F bloğu) ingest sonrası tam cevap.

- **[Q31]** Composite-score (F-Score, G-Score, F&V/P, G&V/P)
  multiple-testing-corrected sig durumu:
  [[harvey_liu_zhu_2016_multiple_testing]] 316 factor census
  **individual factors** üzerinde; **composite scores explicit dahil
  değil**. Wiki'deki F-Score (Piotroski t=5.59 BM-Q5), G-Score (sig
  1%), F & V/P combined (Li-Mohanram +17.94%), G & V/P combined
  (+21.45%) gibi composite spread'lerin multiple-testing düzeltmesi
  paperin çerçevesinde **retroactive** uygulanmamış. Faz 3 baseline
  kararı için kritik — composite scoring strategies için ayrı
  multiple-testing test çalışması gerekli. Adaylar:
  1. Li-Mohanram 2019 sample üzerinde HLZ-style multi-test (modern
     replikasyon)
  2. Faz 2 methodology sayfası açıldığında manuel retroactive HLZ
     uygulaması (composite spread's t-statistic'leri 316 factor
     sample'a eklenir, BHY/Bonferroni cutoff yeniden hesaplanır)
  3. Chen-Zimmermann 2022 Open Asset Pricing data portalı (Tier 2 #41)
     modern composite test
  Q31 Faz 3 strateji baseline'ın nihai validasyonu için ön koşul.

- **[Q32]** NYSE breakpoint VW vs equal-weight all-stocks tercih sorusu
  (Q12 ile bağlantılı):
  - HXZ 2020 [[hou_xue_zhang_2020_replicating_anomalies]] [s.32]
    explicit: "We recommend NYSE breakpoints and value-weights in
    sorts as the benchmark method"
  - MP 2016 + Yan-Zheng 2017 + LSV 1994 + Sloan 1996 EW + all-stocks
    methodology kullanır
  - **Wiki amaç evrenleri (S&P 500 + NDX) NYSE-VW methodology için
    natural fit** (microcap zaten yok). Faz 3 default tercih:
    NYSE breakpoint + VW. Equal-weight all-stocks rakamları
    "exaggerated upper bound" referansı.
  - [[meta/contradictions]] entry MP 2016 ↔ HXZ 2020 (scope-dependent)
    bu sorunun resmî karşılığı.

- **[Q33 partial-stronger (Cycle 27, JKP 2023 modern güncelleme)]** 447 anomaly post-2014 (FAANG era + COVID) replication rate:
  HXZ 2020 sample sonu 2014; modern dönem
  [[hou_xue_zhang_2020_replicating_anomalies]] kapsamı dışı. JKP 2023
  (Tier 2 #44) "Replication Crisis in Finance" + Chen-Zimmermann 2022
  (Tier 2 #41) "Open Asset Pricing" data portalı ek ingest gerekli.
  Q28 (post-2012 modern decay) + Q30 (post-2014 MT-corrected hayatta
  kalma) + Q33 (post-2014 replication rate) **paralel sorular** —
  modern dönem (2015-2024 FAANG + COVID + ML mining) için
  multi-mekanizma kontrol.
  _Israel-Moskowitz 2013 [[israel_moskowitz_2013_shorting_size_time]]
  partial-stronger update (Cycle 22):_ Paper [Tablo 1 + Fig.3] 1990-2011
  subperiod (anomaly post-publication ana penceresi): HML α=2.98%
  t=1.66 INSIG; UMD α=8.87% t=2.38 sig; SMB α=0.90% t=0.96 INSIG.
  Modern post-pub dönemde **HML faltering + UMD robust + SMB silinmiş**.
  Paper sample sonu Dec 2011 → 2012-2024 hala out-of-sample. Tam
  cevap için Chen-Zimmermann + JKP 2023 ek ingest.

- **[Q34]** HXZ q-factor model + 447 anomaly çapraz subsumption:
  [[hou_xue_zhang_2020_replicating_anomalies]] Section 4'te 161 sig
  anomaly üzerinde q-factor regression → 46 alpha sig kalır (115
  insig at 5%). Çapraz subsumption haritası (hangi anomaly q5 ile
  span ediliyor?) detay tablo paperdan teyit gerekir. HMXZ Security
  Analysis (Cycle 8) 6 fundamental scoring strategy + HXZ Replicating
  Anomalies (Cycle 13) 447 individual = factor zoo'nun q-factor
  lens'inde subsumption haritası. Q15 (FF5 vs HXZ4) ve Q24 (q5 vs
  FF5) sorularıyla paralel; q-factor model wiki için Faz 3 risk-
  adjustment baseline. Tam horse race FGX 2020 (Tier 1 #21) ingest'iyle.

- **[Q35]** Wiki ingested paperlardan reported Sharpe ratio'lar var mı?
  [[bailey_lopezdeprado_2014_deflated_sharpe]] DSR formülü uygulamak
  için ham return time-series + N + V[{SR}] gerekli; wiki'deki paperlar
  reported t-stat + spread veriyor (Sharpe explicit yok). Yaklaşık
  tahmin: `Sharpe ≈ √(t² / T)` parametrik; örnek: Carhart UMD
  t=4.46, T=372 (1963-93 monthly) → Sharpe ≈ 0.23 monthly ≈ 0.8
  annualized; FF15 RMW t=2.92 → Sharpe ≈ 0.4-0.5 annualized.
  **Tam DSR formülü** ham return distribution gerekli — Internet
  Appendix bağımlı veya Chen-Zimmermann 2022 (Tier 2 #41) data
  portalı + JKP 2023 (Tier 2 #44) modern verilerle Faz 2'de
  retroactive DSR hesaplaması.

- **[Q36]** Wiki'deki ingested factor strategy'lerin (F&V/P, G&V/P,
  G&NEGPEG, Sloan F_ACCRUAL, R&D-to-market, Cash-based Cop) **return
  distribution shape'i** (skewness, kurtosis): Faz 3 backtest spec'inde
  DSR-2/3 düzeltmesi için bu distribution istatistikleri raporlanmalı.
  Genel literatür kanıtı: equity long-short hedge return'lerde negative
  skew + fat tails tipiktir (momentum crashes Daniel-Moskowitz 2016
  Tier 3 #60 paralel kanıt); spesifik wiki factorleri için JKP 2023
  + Chen-Zimmermann 2022 data portalı ham veri gerekli.

- **[Q37 — wiki tasarım kararı]** Faz 3 backtest spec'inde DSR-1
  trial-count + HLZ MT-corrected birlikte uygulandığında çift
  düzeltme oluşur mu, oluşursa hangi tek-düzeltme prensibi seçilir?
  [[bailey_lopezdeprado_2014_deflated_sharpe]] [s.8] DSR ↔ HLZ
  **explicit complementary**; iki yöntem aynı epistemik düzlem
  (selection bias correction) ama farklı uygulama düzeyi. Adaylar:
  1. **DSR primary, HLZ implicit:** DSR-1 zaten selection bias
     adresliyor; HLZ ek olarak uygulanırsa over-correction
  2. **HLZ primary, DSR Sharpe-only:** Factor selection HLZ ile;
     Sharpe reporting DSR ile (her biri kendi epistemik düzleminde)
  3. **Maximum-conservative birleşim:** Her iki düzeltmeyi de uygula,
     daha düşük olanı baseline kabul et
  Faz 3 backtest spec açıldığında karar; wiki tasarım kararı niteliğinde
  proje-spesifik soru.

- **[Q38 partial-stronger update (Cycle 16)]** Industry-spesifik R&D
  amortization patterns NDX evrende kalibrasyon:
  [[lev_sougiannis_1996_rd_capitalization]] [Tablo 3, s.121] 6
  sektör amortization rates (1975-1990 data, 4-digit SIC): Pharma
  9 yıl useful life, Scientific Instruments 5 yıl, Electrical 8 yıl,
  Computer Hardware ~7 yıl.
  _Peters-Taylor 2017 [[peters_taylor_2017_intangible_capital]]
  partial-stronger update:_ Paper [Section 3.2] **BEA industry-
  specific R&D depreciation rates** kullanıyor (Li 2012'den; pharma
  10% → computers 40%; default %15). Modern data (1975-2011 sample);
  Lev-Sougiannis 1975-1990 ile **complementary** (paper [s.13] explicit
  Li 2012 referans). Industry-bağımlı R&D, **industry-bağımsız %30
  SG&A allocation**. Faz 3 spec için **BEA modern rates baseline** +
  Lev-Sougiannis cross-validation.
  **NDX evrende GICS sektör sınıflandırma + modern amortization
  rate kalibrasyonu Faz 3 spec için kararı:**
  1. GICS Level-2 / Level-3 / Level-4 mapping seçimi
  2. SIC 28 → GICS Pharmaceuticals; SIC 35/36/38 → GICS Tech Hardware
     / Software hibrit
  3. Modern data (Chen-Zimmermann 2022, Tier 2 #41) ile rate
     güncelleme
  4. Mohanram 2005 G6 industry-median methodology Lev-Sougiannis-aware
     versiyona genişletilmeli mi (Q19 sektör sınıflandırma ile
     bağlantılı)
  Faz 3 backtest spec açıldığında karar.

- **[Q39 partial-stronger update (Cycle 16)]** R&D capital stock
  vs flow ölçümü farkı: [[lev_sougiannis_1996_rd_capitalization]]
  adjusted **stock** (kümülatif capitalized R&D, RDC formülü Eq. 8)
  hesaplar. [[hou_xue_zhang_2020_replicating_anomalies]] R&D-to-market
  formülasyonu hangi versiyonu kullanıyor — current year R&D / market
  (flow) yoksa cumulative capitalized R&D / market (stock)? **Paper
  [s.133 footnote 22] explicit not:** proper capitalization stock
  3-yıl flow toplamı'ndan **dramatic farklı** (top decile RDC/M
  coef proper capitalization 0.0114 t=3.88 sig vs 3-year sum 0.0078
  t=1.20 insig). Wiki için Lev-Sougiannis methodology recommendation:
  Faz 3 NDX strategy spec'inde **proper capitalization stock**
  kullanımı; HXZ 2020 R&D-to-market formal tanımı paperdan tek-tek
  teyit edilemedi (text extract'te detay yok).
  _Peters-Taylor 2017 [[peters_taylor_2017_intangible_capital]]
  partial-stronger ileri:_ Paper [Eq. 11] perpetual inventory
  methodology explicit **stock** kullanıyor: G_it = (1 - δ_R&D) ×
  G_{i,t-1} + R&D_it. Lev-Sougiannis ile aynı stock yaklaşım;
  organization capital için de aynı perpetual inventory yapı
  (O_it = (1 - δ_SG&A) × O_{i,t-1} + θ × SG&A_it). **Wiki Faz 3 rec
  pekiştirilir**: proper capitalization stock + BEA industry rates;
  flow-based shortcut'lar [s.133 fn22] dramatic information loss
  yaratır.

- **[Q40 partial-stronger update (Cycle 17)]** Peters-Taylor 2017 SG&A
  organization capital allocation θ=30% kalibrasyonu:
  [[peters_taylor_2017_intangible_capital]] [Section 3.2] θ=30%
  default (Hulten-Hao 2008 + Eisfeldt-Papanikolaou 2014 + Zhang
  2014 paralel); robustness %20-50 sonuç pratik olarak değişmiyor;
  MLE estimate consumer 0.38, high-tech 0.51, health 0.24 (paper
  [s.32] not: "we do not push these θ estimates strongly").
  **NDX evrende kalibrasyon sorusu:** Tech firma SG&A'sı büyük
  kısmı sales force / customer acquisition (Salesforce, Adobe gibi
  recurring-revenue model firmlarda) — geleneksel advertising/training
  yorumundan farklı. NDX-spesifik θ kalibrasyonu (örn. tech high-
  intangible 0.40-0.50; consumer/retail 0.30 baseline) gerekli mi?
  _Lev-Srivastava 2020 [[lev_srivastava_2020_value_failure]] partial-
  stronger ileri (Cycle 17):_ Paper [Section 6] adjusted earnings
  methodology "the part of SG&A related to intangibles" + Enache-
  Srivastava 2018 (Management Science) referansı — Peters-Taylor θ
  paralel kalibrasyon; explicit θ değer paperda paragraflarda
  belirtilmemiş ama methodology aynı. **Faz 3 design decision** —
  Peters-Taylor robustness band içinde default; alternative spec
  sensitivity test.

- **[Q41 FULLY-ANSWERED (Cycle 25, Eisfeldt-Papanikolaou direct ingest)]** Peters-Taylor (all-in-one
  total q) vs Lev-Sougiannis 1996 (R&D-only) vs Eisfeldt-Papanikolaou
  2013 (organization-only) horse race wiki'de yok:
  - Peters-Taylor methodology'i 3 capital component birden ölçer
    (Knowledge + Organization + External); NDX yapısal foundation
    aday
  - Lev-Sougiannis methodology'i sadece R&D-only ölçer; HXZ R&D-to-
    market 4/4 dört darbe hayatta kalan factor methodology temeli
  - **Lev-Srivastava 2020 [[lev_srivastava_2020_value_failure]] (Cycle 17)
    Lev-Sougiannis + Peters-Taylor methodology'sini explicit kullanıyor**
    (R&D capital perpetual inv + SG&A intangibles allocation Enache-
    Srivastava 2018 ref); 3-way (R&D-only + total + organization)
    direct horse race değil ama F bloğu hierarchy methodology-aware
    application.
  - Eisfeldt-Papanikolaou 2013 (Tier 2 #28) organization-only factor
    portfolio direct evidence sağlar (paper [s.5] referans verir
    ama yapısal entegrasyon yok)
  - **Direct horse race (4-way: R&D-only + total + organization-only +
    Lev-Srivastava post-2010 application)** test eden paper wiki'de
    yok; Eisfeldt-Papanikolaou 2013 ingest edildiğinde (Faz 2) 4-way
    comparison mümkün
  - **Faz 3 spec implication:** NDX strategy için 4 ayrı methodology
    sensitivity test (Peters-Taylor baseline + Lev-Sougiannis cross-
    validation + Eisfeldt-Papanikolaou organization-only alternative
    + Lev-Srivastava post-2010 macro context-aware)
  - _Eisfeldt-Papanikolaou 2013 [[eisfeldt_papanikolaou_2013_organization_capital]]
    fully-answered cevap (Cycle 25):_ OC factor portfolio direct evidence
    industry-relative within FF17 spread 4.8%/yıl Sharpe 0.58 + FF3 α
    5.5% sig + Carhart α 3.9% sig 1% (1970-2008); operating leverage
    rejected (DOL-controlled 3.1% sig 1%) → firm-specific worker-
    embodied risk yapısal mekanizma. **F bloğu 4-katmanlı methodology
    hierarchy + factor portfolio anchor ayrımı dokümante**: methodology
    infrastructure (Lev-Sougiannis 1 + Peters-Taylor 3 + Lev-Srivastava
    4) + factor portfolio anchor (Eisfeldt-Papanikolaou 2). Q41
    fully-answered: 4 paper birlikte F bloğu intangibles infrastructure
    tam dokümante. NDX strategy v0 §2.B intangibles-aware overlay
    anchor güçlenmesi (R&D-to-market 4/4 + OC factor 5.5% FF3 α direct
    evidence paralel signal layer).

- **[Q42 yeni (Cycle 16)]** HXZ R&D-to-market'in Peters-Taylor total
  intangibles versiyonu:
  - HXZ 2020 [s.28] R&D-to-market formal tanımı **R&D-only**
    (Lev-Sougiannis methodology temeli; paper [s.133 fn22] proper
    capitalization stock); **dört darbe 4/4 hayatta kalan** factor
    (in-sample + post-pub + MT-corrected + q-factor lens'inde sig)
  - Peters-Taylor total intangibles paradigm'ında genişletilirse:
    **(R&D + Organization + External) / Market** — bu versiyonun
    dört darbe 4/4 hayatta kalmaya devam eder mi?
  - CGS-Ion 2018 [s.5-6] paralel bulgu: Peters-Taylor methodology
    asset growth anomaly açıklayıcı gücünü **GÜÇLENDİRMİYOR**
    (HXZ + total capital → 5/35 → 23/35 unexplained); R&D-to-market'te
    de "total intangibles düzeltmesi yardım etmeyebilir" hipotezi
    cevap arar
  - **Modern data + Peters-Taylor methodology + R&D-to-market versiyon
    test eden paper wiki'de yok**; Faz 2 / Faz 3 backtest spec için
    kritik tasarım sorusu

- **[Q43 yeni (Cycle 17)]** Mean reversion slowdown post-2007 macro-
  economic vs intangibles ayrıştırma testi:
  [[lev_srivastava_2020_value_failure]] paper iki mekanizma birlikte
  sunuyor (intangibles bias + post-2007 macro shocks); ayrı ayrı
  katkı oranı paperda decompose edilmemiş. Faz 2 design decision:
  intangibles-only adjusted methodology mean reversion slowdown'u ne
  ölçüde absorb eder? Causal vs correlational separation test paperda
  yok. Adaylar:
  1. Pre-2007 vs post-2007 sub-sample'larda adjusted methodology test
     (intangibles-only versiyon mean reversion slowdown'u açıklayabilir mi)
  2. Sektör-bazlı ayrıştırma (banking sektörü post-2007 trapped vs
     non-banking sektörlerde adjusted methodology effect)
  3. Glamour-side vs value-side adjusted effect ayrıştırma (paper
     "intangibles-yoğun glamour stocks'ta effect dramatic" diyor)

- **[Q44 partial-stronger (Cycle 27, JKP 2023 sample 2018-2020)]** Post-2018 (FAANG era + AI dönemi 2019-2024)
  value premium replikasyonu: [[lev_srivastava_2020_value_failure]]
  sample sonu 2018; modern dönem (post-2018, 2020 COVID, 2022-2024 AI
  boom) intangibles-aware value strategy out-of-sample. Modern data
  ile replikasyon sources:
  1. Chen-Zimmermann 2022 (Tier 2 #41) Open Asset Pricing data portalı
  2. JKP 2023 (Tier 2 #44) modern güncelleme + global data extension
  3. Lev'in post-2020 follow-up paperı (henüz tier listesinde değil)
  Q1 fully-answered olsa da modern out-of-sample test wiki'nin Faz 2
  validation'ı için kritik.

- **[Q45 yeni (Cycle 17)]** Value-trap-avoidance filter Faz 3 strategy
  spec için: [[lev_srivastava_2020_value_failure]] Logit Table 1
  escape attributes (intangibles + capex + sales growth + debt) signal
  seti S&P 500 strategy'de **filtre olarak nasıl entegre edilir**?
  Adaylar:
  1. Standalone "value escape predictor" screen (top quintile escape
     score → long candidate)
  2. F-Score / G-Score combined yaklaşımına ek katman (F&V/P + escape
     filter)
  3. F&V/P + escape filter cross-product (3-way intersection)
  4. Logit coefficient'leri factor portfolio weight olarak (1.664 +
     4.686 + sales growth + debt × respective z-scores)
  Faz 3 design decision; literatürde sistematik karşılaştırma yok.
  **Wiki için kritik**: F bloğu kapanışından sonra strategy spec
  açma kararı (Cycle 20 Faz 1 sertifikası) öncesinde Q45 adayları
  önerilenecek.

- **[Q46 yeni (Cycle 18)]** M-Score large-cap-only kalibrasyonu:
  [[beneish_1999_m_score]] sample manipulators **küçük-cap-tilted**
  (median TA $43M vs control $96M). S&P 500 / NDX large-cap evrene
  transfer için size-spesifik recalibration gerekli mi? Beneish-Lee-
  Tarpley 2001 (paywall hala) large-cap M-Score test eder; modern
  data Chen-Zimmermann 2022 (Tier 2 #41) + JKP 2023 (Tier 2 #44)
  ile kalibrasyon gerekli. Faz 3 design decision.

- **[Q47 yeni (Cycle 18)]** Tech firma M-Score false positive riski:
  [[beneish_1999_m_score]] 8 bileşeninin SGI (sales growth) + AQI
  (non-current ex-PPE / TA) **intangibles-yoğun firmalarda yapısal
  yüksek** → "manipulator" yanlış sınıflandırma. F bloğu 3 ayak
  methodology (Lev-Sougiannis 1996 + Peters-Taylor 2017 + Lev-
  Srivastava 2020) M-Score'a entegre edilmesi: SGI sektör-medyan-
  relative + AQI intangibles-adjusted. NDX strategy spec için ön
  koşul. Q26 paralel (tech firma R&D distortion) ile bağlantılı.

- **[Q49 partial-stronger (Cycle 23, Novy-Marx Profitability dimension origin direct kanıt; Cycle 38 Ball-GLN Cop methodology link 5 measure GPOA + ACC birleşim; Cycle 39 Stambaugh-Yuan composite scoring methodology paralel mispricing dimension QMJ Profitability + Growth + Safety + Payout 4-dim ≠ Stambaugh-Yuan 2-cluster)]** 4 quality dimension'ın hangisi en güçlü
  large-cap'te: [[asness_frazzini_pedersen_2019_qmj]] [Table VI Panel A]
  her dimension ayrı 1/3/4-factor alpha raporluyor (Profitability +
  Growth + Safety + Payout); paper "the overall QMJ factor is the
  strongest of the four" diyor ama dimension-spesifik t-statistic
  hierarchy paperde explicit decompose edilmemiş. **Faz 2 sentez
  aşamasında değerlendirme**: NDX-spesifik (tech firma) sektör
  yorumu dimension priorities farklı olabilir (örn. Profitability
  + Growth tech firmlarda dominantı; Safety + Payout traditional
  industries'da dominantı). F bloğu 3 ayak methodology entegrasyonu
  (Lev-Sougiannis + Peters-Taylor + Lev-Srivastava) QMJ 4 dimension'a
  uygulanmamış — intangibles-aware versiyon Faz 3 design ön koşul.
  _Novy-Marx 2013 [[novy_marx_2013_gross_profitability]]
  partial-stronger update (Cycle 23):_ Profitability dimension origin
  paper direct kanıt sağlandı: GP/A standalone univariate FF3 α
  0.52% t=4.49; PMU\|BM 0.48% t=5.35 (B/M kontrollü; **Carhart UMD'den
  daha yüksek information ratio**: 5.54 vs 5.11). **Profitability
  dimension QMJ 4 dimension içinde standalone alpha açısından güçlü
  hipotezi direct kanıtla destekleniyor**. Tam Q49 fully-answered
  için QMJ paper Tablo VI Panel A 4 dimension t-statistic hierarchy
  decompose hala gerekli; AQR data setleri (Tier 3 #55) ek ingest.

- **[Q50 yeni (Cycle 19)]** QARP NDX-spesifik kalibrasyonu:
  [[asness_frazzini_pedersen_2019_qmj]] [Section 7] **QARP** = quality
  × n − P/B; n yakın 1 highest alpha (US long sample 1956-2012).
  NDX evrende intangibles-aware Bm (Lev-Srivastava + F bloğu
  methodology) ile QARP kombinasyonu Faz 3 design decision. **Q50 +
  Q45 (value-trap-avoidance filter) + Q21 (combined methodology)** üç
  paralel Faz 3 strategy spec design. Wiki için: Li-Mohanram F&V/P +
  G&V/P combined paradigm + Asness QARP iki alternatif operationalization;
  binary intersection (Li-Mohanram) vs continuous quality × n − P/B
  (Asness). Hangisi NDX evrende dominant? Faz 3 horse race.

- **[Q51 yeni (Cycle 19)]** QMJ post-2012 modern replikasyonu:
  [[asness_frazzini_pedersen_2019_qmj]] sample sonu Dec 2012; FAANG
  era + COVID + AI 2013-2024 out-of-sample. Modern data Chen-Zimmermann
  2022 (Tier 2 #41) + JKP 2023 (Tier 2 #44) ile replikasyon gerekli.
  McLean-Pontiff aggregate %35 decay multiplier proxy uygulanır →
  QMJ post-pub decay düzeyi belirsiz. **HMXZ Tablo 4 q5 captures**
  bulgusu (sample 1957-2016, 4 yıl daha uzun) → q-factor lens'inde
  span muhtemelen modern dönemde de geçerli; 4-factor (Carhart) alpha
  modern dönemde aynı düzeyde mi sorgu açık. AQR data setleri (Tier 3
  #55) modern QMJ updates (post-2012 paywall içerebilir).

- **[Q48 yeni (Cycle 18)]** M-Score post-publication decay (Beneish
  1999 → 25 yıl, 1999-2024): [[beneish_1999_m_score]] original
  sample 1982-1992; paper post-publication 25 yıl (FAANG era +
  COVID + AI) M-Score replikasyon ve decay literatürde sistematik
  yok. McLean-Pontiff aggregate %35 decay multiplier proxy uygulanır
  ama **forensic detection paper, return prediction değil** → decay
  multiplier uygulanması nüanslı (false positive rate'i decay'e
  tabi mi? manipulators arbitrage edilemez — fraud detection
  mekanizması arbitrage'tan farklı). Faz 2 sentez aşamasında
  değerlendirme.

- **[Q52 yeni (Cycle 22)]** Long-only vs long-short anomaly performansı
  decomposition: Wiki amaç evrenleri (S&P 500 + NDX) **long-only
  retail-style portföyler** — Faz 3 strategy spec için kritik
  decomposition. [[israel_moskowitz_2013_shorting_size_time]] [Fig.1
  Panel D + Tablo 3] long-only S/H/U sub-portfolio direct kanıt:
  - Long-only U (top 30% winners): CAPM α=5.55%/yıl t=6.74 information
    ratio 0.73 (size+value'nun 3x'i)
  - Long-only H (top 30% BE/ME): CAPM α=2.93%/yıl t=2.40 information
    ratio 0.26
  - Long-only S (smallest half): CAPM α=2.05%/yıl t=1.72 information
    ratio 0.19
  - Q5 largest stocks long-only momentum α=3.92% t=3.83 sig (size-conditional
    long-only test)
  Faz 2 sentez sırasında F&V/P + G&V/P composite + QARP framework long-only
  versions için empirik validation. Yapısal pattern: long-only momentum
  large-cap'te actionable; long-only value large-cap'te marjinal
  (Q14 paralel).

- **[Q53 yeni (Cycle 22)]** Time-conditional anomaly decay decomposition
  (publication-anchored vs decade-by-decade size):
  [[mclean_pontiff_2016_post_publication_decay]] **publication-anchored
  discrete change** [Tablo 5]: post-pub indicator -29% to -43% sig;
  time trend insig.
  [[israel_moskowitz_2013_shorting_size_time]] **20-yıl dummy +
  linear time trend** [Tablo 4 Panel A]: hiçbir time variable sig
  SMB/HML/UMD; **anomaly returns 86-yıl boyunca stabil**.
  İki farklı time variation paradigması:
  - MP: anomaly returns publication-anchored discrete drop (yayım
    tarihinden sonra %35 düşüş)
  - Israel-Moskowitz: anomaly returns time-stationary (no trend, no
    discrete change at any 20-yıl boundary)
  Çelişki değil — MP individual anomaly publication date'leri farklı
  (1972-2007 spread); aggregate analysis level'da farklı paradigma.
  Faz 2 sentez sırasında Chen-Zimmermann + JKP 2023 modern data
  ile her iki paradigmanın post-2012 dönemde test edilmesi. Q33
  paralel.

- **[Q54 yeni (Cycle 22)]** Anomaly performansının size × shorting
  interaction decomposition:
  [[israel_moskowitz_2013_shorting_size_time]] [Tablo 3 + Fig.2]
  size × shorting kontingency:
  - **Value strategy**: shorting küçük cap'lerde önemli (Q1 long
    contribution 47%); büyük cap'lerde long-only baskın (Q5 long
    contribution 90%) — büyük cap'te shorting nispeten önemsiz
  - **Momentum strategy**: shorting büyük cap'lerde önemli (Q5 long
    contribution 38%); küçük cap'lerde long baskın (Q1 long contribution
    71%) — wiki amaç evrenleri (large-cap + long-only) için **momentum
    long-only sub-optimal** (Q5 long contribution sadece 38%)
  Wiki strategy spec için: large-cap + long-only kombinasyonu için
  hangi anomaliler birlikte hayatta? Cevap (paperdan direct):
  - Long-only large-cap value: α=1.97% t=1.21 INSIG (vanilla HML reject)
  - Long-only large-cap momentum: α=3.92% t=3.83 sig (actionable)
  Faz 3 spec için: F&V/P + G&V/P composite + long-only momentum +
  intangibles-aware Bm rebuild kombinasyonu — wiki amaç evrenleri için
  Israel-Moskowitz "size × shorting matrix"e en uygun konfigürasyon.

- **[Q55 FULLY-ANSWERED (Cycle 26, FGX 2020 anchor; Cycle 38 sertleştirme Ball-GLN Cop origin paper direct anchor)]** GP/A vs RMW Ope vs QMJ GPOA vs Cop horse race
  (Profitability zinciri 4 measure direct comparison):
  - **GP/A** (Novy-Marx 2013): (REVT − COGS) / AT
  - **RMW Ope** (FF15): (REVT − COGS − SG&A − interest) / BE
  - **QMJ GPOA** (Asness 2019): gross profits-over-assets (composite z-score)
  - **Cop** (HMXZ Tablo 5; Ball-GLN 2016 origin): cash-aware variant
    (working capital + capex çıkarılmış)
  4 measure numerator + denominator iki seviye fark; HXZ 2020 q-factor
  lens'inde Cop **4/4 hayatta kalan** (alpha 0.69%/ay sig); GP/A
  3-4/4; RMW Ope **1/4** (HXZ q-factor alpha 0.04% t=0.42 INSIG); QMJ
  GPOA composite içinde span.
  _Feng-Giglio-Xiu 2020 [[feng_giglio_xiu_2020_factor_zoo]] fully-answered cevap (Cycle 26):_
  - **RMW Ope DS-sig** (Tablo 1, since-2012 factors) — HXZ q-factor
    INSIG (1/4) ile **iki paralel bulgu, methodology farkı**: q-factor
    model lens vs DS LASSO 150-factor library lens iki ayrı epistemic
    question; çelişki değil. Faz 3 spec için RMW iki kullanım modu
    option (q-factor exposure proxy + DS-sig standalone signal).
  - **ROE (HXZ profitability) DS-sig** — HMXZ q5 captures + FGX DS-sig
    paralel methodology lens.
  - **QMJ DS-sig** (composite) — Q49 dimension-spesifik decompose
    paperde yok partial-stronger; composite QMJ DS lens'inde sig.
  - **GP/A 150 library içinde explicit listed teyit edilemedi**
    (Tablo 4 ham liste paperdan tek-tek kontrol edilmedi); Profitability
    ailesi genel sig dolaylı validation (RMW + ROE + QMJ DS-sig).
  - **Cop FGX library'de explicit yok** (FGX HXZ q-factor model'in
    4 factor'ünü kullanır; Cop HMXZ Tablo 5'te ek factor); HXZ
    q-factor 4/4 paralel kanıt.
  **Q55 fully-answered**; v0_draft Profitability seçimi (S&P 500 GP×V/P
  + NDX QMJ + GP/A) **DOĞRULANDI** (revize gerekmez); Faz 3 spec
  için Cop tercih (cash-aware evrim superior) hala geçerli ama RMW
  Ope ek kullanım modu option.

- **[Q56 yeni (Cycle 23)]** Intangibles-aware GP/A:
  Novy-Marx GP/A numerator R&D/SG&A/interest çıkarılmamış (intangibles-
  aware avantajı) AMA denominator total assets traditional. F bloğu
  ([[concepts/intangibles_adjusted_accounting]]) Lev-Sougiannis perpetual
  inventory + Peters-Taylor total intangible capital methodology
  GP/A'ya uygulanmamış. **FAANG firmalarda recurring revenue
  R&D-amortized adjusted GP/A** Faz 3 NDX strategy spec için ön
  koşul. Adjusted GP/A = (REVT − COGS) / (AT_phy + AT_int). Q23 + Q42
  paralel; modern data + F bloğu 3 ayak methodology entegrasyonu
  Faz 2/3 sentez.

- **[Q57 yeni (Cycle 23)]** GP/A annual rebalance optimal frekans:
  [[novy_marx_2013_gross_profitability]] [s.9 fn 3 + Appendix A.4]
  annual default ama **quarterly variant daha güçlü monthly returns**;
  trade-off: turnover yüksek (yıl başına 1x'ten 4x'e). Wiki amaç
  evrenleri annual default (CLAUDE.md proje amacı); Frazzini-Israel-
  Moskowitz 2018 (Tier 3 #52, paywall) firm-level cost analysis ek
  ingest sensitivity test için kritik. Q33 (UMD aylık-orijinal
  annual uyarlama) + Q35 (QMJ aylık-orijinal annual uyarlama) +
  Q57 (GP/A annual default ama quarterly güçlü) paralel rebalance
  frequency family.

- **[Q58 yeni (Cycle 23)]** Industry-adjusted GP/A factor anomaly
  explanation power (Cochrane #1 "anomalies are different expressions
  of underlying mechanisms"):
  [[novy_marx_2013_gross_profitability]] [Section 4] industry-adjusted
  GP/A + value + momentum 3-factor model **11 anomaly** açıklıyor:
  ROE, E/P, asset turnover, gross margins, SUE, default risk
  (Campbell-Hilscher-Szilagyi 2008), failure prob, O-Score (Ohlson
  1980), net stock issuance, asset growth, total accruals, organizational
  capital (Eisfeldt-Papanikolaou 2011). q-factor model (HMXZ q5) ile
  **alternative explanation çatallanması**: productivity proxy vs
  investment factor exposure proxy (Cochrane mathematical equivalence).
  Wiki taraf tutmaz — Faz 3 spec'inde her iki yorum complementary.
  FGX 2020 (Tier 1 #21) ek ingest tam horse race için.

- **[Q59 yeni (Cycle 25)]** Knowledge capital ↔ Organization capital
  factor portfolio correlation orthogonality empirik test:
  [[lev_sougiannis_1996_rd_capitalization]] R&D perpetual inventory +
  [[eisfeldt_papanikolaou_2013_organization_capital]] SG&A perpetual
  inventory iki ayrı intangibles ayağı; aynı methodology paterni
  (perpetual inventory) farklı capital türü (R&D vs SG&A);
  [[peters_taylor_2017_intangible_capital]] Knowledge + Organization +
  External 3-component decomposition direct cevap sağlayabilir ama
  factor portfolio level correlation eksik. F bloğu 1. + 2. ayak
  combined methodology Faz 3 design: R&D-to-market 4/4 + OC factor
  5.5% FF3 α paralel mı yoksa correlated mi? FGX 2020 (Cycle 26
  ingest) redundancy testing tam cevap için.

- **[Q60 yeni (Cycle 25)]** Peters-Taylor θ=30% SG&A allocation vs
  Eisfeldt-Papanikolaou full SG&A perpetual inventory methodology
  farkı: aynı SG&A flow'unu farklı treatment (Peters-Taylor knowledge
  + organization + external 3 component ayrım için θ tahmin ediyor;
  Eisfeldt-Papanikolaou measurement error caveat ile full SG&A
  perpetual inventory δ=15%). Modern kalibrasyon (FAANG firmalarda
  recurring revenue model SG&A breakdown — sales force + customer
  acquisition + R&D-content) sektör compositional shift altında
  allocation factor değişebilir. Chen-Zimmermann 2022 + JKP 2023
  modern data ile iki methodology empirik comparison Faz 2 sonu.
  **Faz 3 spec implication**: NDX strategy için iki SG&A allocation
  alternative sensitivity test.

- **[Q62 yeni (Cycle 26)]** NDX-spesifik DS LASSO redundancy testing
  kalibrasyon: [[feng_giglio_xiu_2020_factor_zoo]] universal sample
  (NYSE+AMEX+NASDAQ Compustat 1976-2017); NDX top 100 non-financial
  sub-universe için DS LASSO sample size sınırı + factor selection
  farkı; cross-validation tuning parameter (10-fold disjoint random
  subsamples) NDX 100-stock portfolio için sufficient mi? Faz 3 NDX
  strategy spec implementation kalibrasyon gerekli.

- **[Q63 FULLY-ANSWERED (Cycle 27, JKP 2023 anchor)]** Post-2017 modern data ile FGX
  replikasyonu: [[feng_giglio_xiu_2020_factor_zoo]] sample sonu Dec
  2017; FAANG era 2018-2024 + COVID + AI out-of-sample. JKP 2023
  (Cycle 27 ingest planı) modern güncelleme + global data ML-aware
  framework sağlayabilir; Chen-Zimmermann 2022 (Cycle 29 data portal)
  modern factor library replikasyon altyapısı. Q33 (post-2014 modern
  decay) + Q63 (post-2017 modern FGX replikasyon) paralel.
  _Jensen-Kelly-Pedersen 2023 [[jensen_kelly_pedersen_2023_replication_crisis]]
  fully-answered cevap (Cycle 27):_
  JKP 2023 sample sonu **2020** (NBER WP February 2021); FGX sample
  sonu 2017 + JKP 2020 → **3 yıl modern güncelleme** (2017-2020).
  JKP Bayesian Empirical Bayes hierarchical methodology FGX frequentist
  DS LASSO ile **complementary methodology aile** (D bloğu statistical
  bacağı 3 paper × üç paralel methodology aile). Bayesian framework
  Empirical Bayes hierarchical %84.9 US + %84.0 Global anti-conservative-
  side; FGX 17/150 sig (%11) recursive frequentist conservative-side
  → **dramatic methodology disagreement** ([[meta/contradictions]] §3
  HXZ ↔ JKP ana entry; FGX ↔ JKP paralel paper sayfasında not).
  Q63 fully-answered: 3 yıl modern güncelleme paper-form; **Q33 +
  Q44 partial-stronger** (post-2020 hala out-of-sample).

- **[Q64 yeni (Cycle 26)]** F bloğu intangibles factor'lerin FGX
  framework'üne entegrasyonu: [[feng_giglio_xiu_2020_factor_zoo]]
  150 factor library içinde **F bloğu intangibles factor'leri
  (Lev-Sougiannis Knowledge + Eisfeldt-Papanikolaou OC + Peters-
  Taylor q^tot) explicit listed teyit edilemedi** (Tablo 4 ham liste
  paperdan tek-tek kontrol edilmedi). 135 characteristic-based long-
  short portfolio içinde Sloan + Mohanram + Beneish benzeri intangibles-
  related characteristics yer alabilir; intermediary investment
  factor (He-Kelly-Manela 2016) DS-sig ama bu intermediary capital,
  organization capital değil. F bloğu 4-katmanlı methodology DS LASSO
  redundancy test'i Faz 3 implementation gap.

- **[Q65 yeni (Cycle 26)]** Composite scores FGX framework'üne
  entegrasyonu: F-Score, G-Score, M-Score, F&V/P, G&V/P, QARP
  composite scoring strategies [[feng_giglio_xiu_2020_factor_zoo]]
  150 library'sinde **individual factor census, composite scoring
  strategies dahil değil** (HLZ 2016 + HXZ 2020 paterni paralel).
  Composite scores DS LASSO redundancy test wiki Faz 3 methodology
  gap; Chen-Zimmermann 2022 modern data portal + custom DS LASSO
  implementation Faz 3 yapılabilir.

- **[Q61 yeni (Cycle 25)]** Organization capital tech firma + service
  firma sektör compositional shift: NDX FAANG era yüksek SG&A vs
  traditional industries banking/manufacturing; [[eisfeldt_papanikolaou_2013_organization_capital]]
  industry-relative within-industry sort sektör comparison içinde
  değil; cross-industry OC dispersion modern dönem empirik trend
  [[lev_srivastava_2020_value_failure]] [Section 9] sektör
  compositional shift paterni paralel. Q61 = NDX strategy spec için
  GICS Level-2/3 mapping + within-sektör vs cross-sektör OC factor
  performans karşılaştırması; Mohanram G-Score industry-median
  paterni paralel methodology.

- **[Q66 partial-stronger (Cycle 27 yeni; Cycle 39 Stambaugh-Yuan hierarchical clustering methodology evolution Ahn-Conrad-Dittmar 2009 + Ward 1963 → JKP Bayesian Empirical Bayes hierarchical)]** ML methodology factor selection vs
  Bayesian methodology comparison: HLZ + FGX **frequentist family**
  (data-snooping bias + omitted variable bias) + JKP 2023 **Bayesian
  family** (Empirical Bayes hierarchical replication) iki paralel
  epistemic family wiki için. Hangisi Faz 3 backtest spec için
  baseline? Wiki için: **factor-level** evaluation HLZ + FGX
  frequentist (data-snooping + model selection bias correction);
  **strategy-level** evaluation DSR; **multi-theme allocation**
  JKP Bayesian theme cluster + tangency portfolio. Üç paralel
  methodology layer Faz 3 backtest spec için tamamlayıcı (Cycle 26
  + 27 sertleştirme).

- **[Q67 yeni (Cycle 27)]** Lev-Srivastava vanilla HML 2010s
  NEGATIVE vs JKP Value theme >75% replicate methodology disagreement:
  [[lev_srivastava_2020_value_failure]] Q1 fully-answered Cycle 17
  (vanilla HML decade-by-decade post-2010 NEGATIVE) vs JKP 2023
  Value theme **>75% replicate** US + global Bayesian (single-ratio
  vs theme cluster methodology farkı). **F bloğu intangibles-aware
  Bm rebuild (4-katmanlı methodology) JKP framework'te yapılmamış**;
  F bloğu integration JKP Bayesian Empirical Bayes hierarchical
  methodology sensitivity test Faz 3 implementation. Çelişki YOK
  (scope-dependent: single-ratio vs theme cluster); paper sayfasında
  not + Q67 yeni F bloğu integration eksik gap.

- **[Q68 yeni (Cycle 27)]** Capped value-weighting (JKP NYSE 80th
  percentile winsorize) vs pure VW (HXZ) vs FF half-weight (Fama-
  French) **üç methodology trade-off**: HXZ vs JKP dramatic empirik
  fark (%35 vs %56.9 raw +21.9pp methodology decomposition; capped
  VW alone +8.5pp). Wiki amaç evrenleri (S&P 500 + NDX top 100)
  large-cap concentrated; **capped VW natural fit Faz 3 implementation
  tercih aday** (mega-cap concentration distortion kontrolü; Apple/
  Microsoft NDX %15-20 + S&P 500 %7-8). Methodology choice sensitivity
  test Faz 3 spec ([[methodology/backtest_spec]] §1.3 + §4.4
  sertleştirme).

- **[Q69 yeni (Cycle 27)]** 13 theme cluster taxonomy NDX-spesifik
  subsample decomposition: [[jensen_kelly_pedersen_2023_replication_crisis]]
  153 factor × 13 theme JKP framework universal sample; NDX top 100
  non-financial sub-universe için 13 theme'in hepsi mi NDX-relevant
  yoksa sadece bir subset mi? **NDX FAANG profile muhtemelen Quality
  + Profitability + Profit Growth + Investment* + Value 5 theme
  dominantı**; diğer themes (Seasonality + Size + Skewness*)
  NDX-relevant değil. Faz 3 NDX strategy spec **theme diversification
  simplified** (5 theme NDX-specific vs 13 theme universal). Q67 +
  Q69 paralel (intangibles-aware + NDX-spesifik theme).

- **[Q70 yeni (Cycle 27)]** Tangency portfolio multi-theme allocation
  framework Faz 3 strategy spec anchor: [[jensen_kelly_pedersen_2023_replication_crisis]]
  10/13 themes tangency portfolio sig+ multi-theme allocation; 3
  displaced (profitability + investment + size) joint modeling
  redundancy. **Factor selection** (single factor inclusion list)
  + **theme allocation** (multi-theme weight) iki paralel decision.
  Wiki için: v0_draft §1.B + §2.B factor inclusion list **theme
  diversification yapısı** Faz 3 v1 revize sırasında dahil edilmeli
  (Cycle 30 hedef). Profitability theme **standalone replicate sig**
  ama **tangency'de displaced** (Q49 + Q55 paralel insight).

- **[Q71 yeni (Cycle 29)]** Chen-Zimmermann database vs JKP
  GlobalFactor data convergence/divergence: [[methodology/data_sources]]
  §1 + §2 iki paralel data portal aynı anomaly setleri (200+
  Chen-Zimmermann + 153 JKP 13 theme cluster) için aynı return
  time-series üretiyor mu? **Pure replication vs scientific
  replication ayrımı** (JKP [s.1 fn 1] explicit): Chen-Zimmermann
  ~100% pure replication (aynı data + aynı method); JKP %85
  Bayesian Empirical Bayes (capped VW + 1-month + Bayesian framework
  +28pp methodology choice); HXZ %35 scientific replication (NYSE-VW
  pure VW + 1/6/12-month). **Üç paralel methodology aile aynı
  underlying data için farklı sonuç** — Faz 3 implementation iki
  data portal cross-validate sırasında methodology choice transparent
  reporting zorunlu.

- **[Q72 yeni (Cycle 29)]** WRDS access infrastructure NDX-spesifik
  subsample: [[methodology/data_sources]] §3 WRDS academic platform;
  NDX top 100 non-financial Nasdaq-listed için optimal data feed
  configuration: **CRSP US** (Nasdaq-listed subset share code 10/11)
  + **Compustat North America** (annual + quarterly accounting) +
  **IBES** (analyst forecasts; tech sektör forecasts FAANG era için
  kritik) + **Chen-Zimmermann database** (200+ anomaly modern
  replikasyon factor return time-series). Q62 (NDX-spesifik DS LASSO
  Cycle 26) + Q72 paralel: NDX 100-stock subsample Bayesian
  Empirical Bayes hierarchical sample size sınırı + WRDS data feed
  configuration Faz 3 implementation kararı.

## Cycle 35 yeni Q'lar (HXZ 2015 ingest sonrası)

- **[Q73]** q-factor model intangibles-aware genişletme aday: HXZ 2015
  r_I/A = ΔAT/AT-lagged traditional accounting; FAANG/tech firma R&D
  giderleştiriliyor numerator+denominator etkisi; F bloğu 4-katmanlı
  intangibles-aware Bm rebuild paterni q-factor üzerine uygulanabilir
  mi? Faz 3 implementation custom modification (NDX strategy spec
  [[strategies/nasdaq100_v1]] §2.5 q-factor span kontrolü ek katman;
  Q56 + Q23 paralel).

- **[Q74]** HXZ 2015 sample 1972-2011 post-2011 14 yıl out-of-sample
  modern replikasyon: JKP 2023 [[papers/jensen_kelly_pedersen_2023_replication_crisis]]
  partial 2014-2020 6 yıl modern coverage (Bayesian framework); post-
  2020 hala out-of-sample (FAANG/AI 2021-2024); custom Faz 3 backtest
  implementation (Cycle 41+ hedef).

- **[Q75]** r_ROE monthly resort zorunluluğu vs wiki annual frequency
  hedef: HXZ 2015 [s.7 fn 5 + Apx E] explicit "annually-sorted versions
  of momentum + PEAD + IVOL + distress DON'T EXIST — none of high-minus-
  low portfolios produce mean excess returns or CAPM alphas significantly
  different from zero". Wiki annual rebalance hedefli; r_I/A annual sort
  + r_ROE monthly resort hibrit yapı Faz 3 backtest implementation
  reconciliation karar (sp500_v1 §3.1 + nasdaq100_v1 §3.1 annual June
  rebalance + r_ROE quarterly earnings announcement-anchored monthly
  resort hibrit; Q35 + Q51 + Q57 paralel sensitivity test).

- **[Q15a partial-stronger (Cycle 38, Ball-GLN Cop subsumption complementary methodology farkı)]** Sloan accruals q-factor exception scope-dependent yorum
  mı yoksa structural limit mi? (HXZ 2015 [Tablo + Section 3 + Section 6
  Conclusion] explicit "trouble in explaining Sloan total accrual
  effect"; "high accrual firms invest more but also more profitable
  load more on ROE factor wrong direction"); F bloğu intangibles + Sloan
  zinciri F_ACCRUAL/G3/QMJ ACC q-factor span dışı complement.
  _Cycle 38 partial-stronger update [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]:_
  Ball-GLN Cop subsumes accruals (Tablo 2 col 6 Cop t=7.4 + Acc t=0.34
  INSIG); q-factor I/A+ROE size-controlled lens vs Cop accrual-cash
  flow decomposition lens **iki ayrı epistemic framework complementary**
  (q-factor Sloan exception scope-dependent methodology farkı, structural
  limit değil); Cop methodology Sloan zinciri F_ACCRUAL/G3/QMJ ACC
  paralel + Profitability zinciri 4. halka birleşim noktası.

## Cycle 37 yeni Q'lar (FF 2008 ingest sonrası)

- **[Q76]** FF 2008 sample 1963-2005 post-2005 19 yıl out-of-sample
  modern replikasyon: JKP 2023 [[papers/jensen_kelly_pedersen_2023_replication_crisis]]
  partial 2014-2020 6 yıl Bayesian framework + post-2020 hala out-of-
  sample (FAANG era 2008-2024); FF 2008 size-partition methodology
  modern replikasyon FAANG era big-stocks pattern stabil mi yoksa
  değişti mi? Faz 3 custom backtest implementation Cycle 41+ hedef.

- **[Q77]** Large-cap-only ayrı RMW/CMA factor inşası direct empirik
  test: FF 2008 size-partition methodology origin ama large-cap-only
  factor portfolio formal tanım YOK (FF15 standart 2×3 sort + FF 2008
  size partition test); Faz 3 implementation custom Hou-style 2×3
  size-controlled vs FF15 standart 2×3 sort comparison; sp500_v1 +
  nasdaq100_v1 §2.1 Path D + Path B factor exposure proxy direct
  test sensitivity karar.

- **[Q78]** FF 2008 momentum size-invariance vs HXZ 2015 [Apx E]
  annual-sorted momentum INSIG çelişki yok scope-dependent: FF 2008
  monthly momentum size-pervasive (slopes 0.41+0.82+0.78 all sig) vs
  HXZ 2015 annual-sorted momentum hedge alpha INSIG (Q75 paralel);
  iki ayrı epistemic question — pervasiveness across size groups
  (FF 2008) vs annual-sort viability (HXZ 2015 Apx E); Faz 3 backtest
  implementation UMD overlay annual-uyarlama sensitivity test
  reconciliation karar.

## Cycle 38 yeni Q'lar (Ball-GLN 2016 ingest sonrası)

- **[Q79]** Cop methodology NDX-spesifik R&D-intensive firma
  kalibrasyonu: Ball-GLN [s.6] Cop = REVT − COGS − SG&A; SG&A R&D
  expense dahil → FAANG/biotech firmalarda R&D giderleştirme Cop'u
  **yapay düşürür** (Apple/Microsoft/Google/Nvidia/Meta/Tesla R&D-
  intensive Cop bias); F bloğu paralel intangibles-aware Cop
  modification Faz 3 implementation custom (SG&A R&D purging + R&D
  capital adjusted Cop NDX-tailored; Q56 + Q73 paterni paralel);
  nasdaq100_v1 §2.5 F bloğu 4-katmanlı methodology Cop intangibles-
  adjusted entegrasyonu Q79 paralel Faz 3 Cycle 41+ implementation
  karar.

- **[Q80]** Ball-GLN sample 1963-2014 post-2014 10 yıl modern
  replikasyon: JKP 2023 [[papers/jensen_kelly_pedersen_2023_replication_crisis]]
  partial 2014-2020 6 yıl Bayesian framework + post-2020 hala out-of-
  sample (FAANG era 2014-2024); Cop pattern stabil mi yoksa değişti
  mi (R&D-intensive firmalarda Cop bias artıyor mu); custom Faz 3
  backtest implementation Cycle 41+ hedef.

## Cycle 39 yeni Q'lar (Stambaugh-Yuan 2017 ingest sonrası)

- **[Q81]** Stambaugh-Yuan 11 anomaly post-2013 11 yıl modern
  replikasyon: paper sample 1967-2013 + JKP 2023 partial 2014-2020
  6 yıl Bayesian framework + post-2020 hala out-of-sample (FAANG era
  2014-2024); 11-anomaly fixed set robustness (Stambaugh-Yu-Yuan
  2012-spesifik); MGMT + PERF cluster composition stabil mi yoksa
  değişti mi (post-2013 anomaly evolution + sentiment regime
  dynamics); Faz 3 custom backtest implementation Cycle 41+ hedef.

- **[Q82]** MGMT + PERF NDX-spesifik R&D-intensive firma kalibrasyonu:
  Cluster 1 asset growth + I/A FAANG R&D capitalization YOK traditional
  → R&D-intensive firmalarda yapay yüksek I/A (Q73 paralel I/A
  intangibles-aware genişletme aday); Cluster 2 GP/A + ROA FAANG R&D
  giderleştirme yapay düşük profitability (Q56 + Q79 paralel);
  F bloğu 4-katmanlı paralel intangibles-aware MGMT/PERF modification
  Faz 3 implementation custom; **Q56+Q73+Q79+Q82 NDX intangibles
  dörtlü konsolidasyonu** Cycle 40 §11.5 ZORUNLU consolidation pass'de
  nasdaq100_v1 §6 + known_weaknesses §3 propagation kontrol (Q75
  propagation pattern paralel kullanıcı request).

## (Yeni sorular ingest sırasında buraya eklenir.)

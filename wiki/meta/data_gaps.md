# Data Gaps

> Wiki'de henüz cevabı olmayan ama strateji tasarımı için kritik konular.
> Lint pass'lerinde güncellenir. Yeni kaynak önerilerini buraya yaz.
>
> 📝 **Cycle 21 sonrası**: Tüm Faz 2 boşlukları
> [[methodology/backtest_spec]] §9'da konsolide edildi; çapraz
> referans için bu sayfa primary index olarak kullanılabilir
> (E bloğu eksiklikleri + Tier 1 q-factor origin + modern data ingest +
> v0_draft ön koşulları + Q49/Q50/Q51 + Q40/Q42/Q44/Q45).

## Eksik konular (priori)

- **Nasdaq 100 üzerinde fundamental factor test**: Çoğu literatür CRSP universe
  veya S&P 500 üzerinde test ediyor. Pure Nasdaq 100 (top 100 non-financial)
  çalışması az.

- **R&D capitalization ve intangibles**: Tech-heavy evrende geleneksel B/M
  bozulur. Lev-Sougiannis (1996), Peters-Taylor (2017) intangibles tartışması
  ingest edilmeli.

- **Annual rebalance frequency**: Çoğu paper aylık rebalance test ediyor.
  Yıllık rebalance ile turnover/cost trade-off literatürü taranmalı.

- **Earnings revision momentum**: Stickel, Womack türü analyst revision
  momentum stratejilerinin fundamental composite'lerle interaksiyonu.

- **Post-2010 factor performance**: Çoğu seminal paper pre-2010 dönemde test
  edildi. Out-of-sample 2010-2024 dönemi için replication çalışmaları gerekli.

## Aranacak kaynaklar

_(ingest sürecinde buraya eklenir)_

## Ingest sırasında yüzeye çıkan boşluklar (post-Cycle 3)

- **Equal-weight vs. value-weight faktör inşa konvansiyonu**: [[carhart1997_four_factor]]
  UMD'yi equal-weight inşa ederken [[famafrench1993_three_factor]] SMB ve HML'i
  value-weight inşa eder. **Bu konvansiyon farkı sonraki literatürde nasıl ele
  alındı?** Yıllık-frekans büyük-cap stratejisi için VW versiyon literatürde
  daha standart mı? Asness-Frazzini-Pedersen 2019 (QMJ), Hou-Xue-Zhang 2015 ingestleri
  bunu adresleyebilir.

- **Universe-spesifik faktör inşası (S&P 500-only / Nasdaq 100-only)**: Tüm ingested
  paperlar NYSE/AMEX/NASDAQ universe'unda inşa edilmiş faktörler kullanır. **S&P 500
  veya Nasdaq 100 evreninde universe-içi breakpoint'lerle yeniden inşa edilmiş
  faktör kanıtları wiki'de yok.** AQR data setleri (Tier 3 #55), Asness-Frazzini-Pedersen
  2019 large-cap kanıtları.

- **Aylık vs. yıllık rebalance literatürü** (önceki giriş genişletildi):
  Carhart UMD aylık rebalance; FF93/FF15 HML/SMB/RMW/CMA yıllık rebalance.
  **Frekans seçimi factor primum'unu nasıl etkiliyor?** Novy-Marx-Velikov 2016
  (Tier 2 #39) "anomalies and trading costs" bu meseleyi yıllık rebalans
  perspektifinden ele alıyor — Tier 2'de seçici ingest adayı.

- **Trading costs / capacity**: 3 ingested paper trading cost'u tartışmaz (Carhart
  expense ratios bahsi mutual fund-spesifik). Frazzini-Israel-Moskowitz 2018 (Tier 3
  #52), Novy-Marx-Velikov 2016 (Tier 2 #39) bu boşluğu doldurur. **Yıllık rebalans
  + value-weight + S&P 500 universe için trading cost analizi şart** — Faz 3
  strateji tasarımının ön koşulu.

- **Factor zoo / multiple testing problem**: Wiki şu ana kadar 6 faktör gösterdi
  (MKT-RF, SMB, HML, RMW, CMA, UMD) ama akademik literatürde 300+ faktör var.
  **Hangisi gerçekten incremental information taşıyor?** Cochrane 2011 (Tier 1 #25)
  bu sorunu framing eder; Harvey-Liu-Zhu 2016 (Tier 1 #17) multiple testing
  düzeltmesi sunar; Feng-Giglio-Xiu 2020 (Tier 1 #21) yeni-faktör testi prosedürü
  verir. **Cochrane → HLZ → FGX sırası bu boşluğu kapatır.**

- **Momentum crashes / state-dependent decay**: [[UMD]] sayfasında not edildi.
  Daniel-Moskowitz 2016 (Tier 3 #60) gerekli; mevcut literatürde momentum'un
  2000-2002 ve 2008-2009 büyük drawdown'ları belgelenmiş ama wiki'de henüz atıflanamaz.

- **Post-publication decay**: Tüm faktörler için (özellikle SMB, HML) post-1990s
  performans tartışılmıyor. McLean-Pontiff 2016 (Tier 1 #16) bu boşluğu doldurur —
  zorunlu Tier 1 ingest'i.

## Cycle 5 (Piotroski) sonrası yüzeye çıkan boşluklar

- **Large-cap fundamental score replikasyonu**: [[piotroski2000_f_score]] Tablo 4
  large-cap'te F-Score spread'in zayıfladığını gösteriyor. **S&P 500 / Nasdaq 100
  evrenlerinde fundamental composite skor performansı için doğrudan literatür
  yok.** Mohanram 2005 (Tier 1 #11) low-BM tarafında muadil; Li-Mohanram 2019
  combined approach. **Piotroski-So 2012** (Tier listesinde değil) F-Score
  out-of-sample 1997-2014 — **Tier 2 önerilen ek**.

- **Sektör-nötr fundamental scoring kalibrasyonu**: [[piotroski2000_f_score]]
  industry-adjusted versiyon test ettiğini bahsediyor [s.7 fn 3] ama detay
  vermiyor. **GICS Level-1 vs. Level-4 sektör kesimi, finansallar için ayrı
  treatment, regulated industries için baseline farkı** — bu konularda hiç
  kanıt yok wiki'de.

- **Universe-spesifik breakpoint metodolojisi**: F-Score CRSP all-stocks evrende
  kalibre. S&P 500 içi 30/70 percentile kullanmak, ya da S&P 500'ün kendi
  median'ını kullanmak — hangi seçim yapısal olarak doğru? **AQR pratiğinde
  yaygın ama akademik literatürde sistematik tartışma henüz wiki'de yok.**

- **Continuous vs. binary skorlama**: [[piotroski2000_f_score]] [s.16] continuous
  versiyonun "qualitatively similar" sonuç verdiğini ama spread'in 0.092 vs
  0.230'a düştüğünü söylüyor. **Modern uygulamalarda hangi format daha robust?**
  Cross-validation ile factor analysis ağırlıkları test edildi mi?
  Freyberger-Neuhierl-Weber 2020 (Tier 2 #45) "nonparametric characteristics"
  bu boşluğu adresler.

- **Earnings announcement window kanıtı için ek paperlar**: [[piotroski2000_f_score]]
  [s.4-5] F-Score spread'in 1/6'sı 4 quarterly earnings announcement
  pencerelerinde realize ediyor. PEAD literatürü (Bernard-Thomas 1989/1990,
  La Porta vd. 1997) wiki'de yok — Beneish ya da diğer earnings-based ingestler
  ile dolacak.

## Cycle 6 (Mohanram) sonrası yüzeye çıkan boşluklar

- **NDX-spesifik sektör sınıflandırma kalibrasyon kanıtı:** Mohanram 2005
  2-digit SIC kullanıyor. NDX 100-stock evrende GICS-3 vs. GICS-4 vs. universe
  median performansı için **wiki'de doğrudan kanıt yok**. AQR ve Research
  Affiliates pratik literatürü (Tier 3 whitepaper'lar) bu boşluğa bilgi
  sağlayabilir.

- **Post-2000 G-Score replikasyonu**: Mohanram 2005 örnekleminin sonu 1999.
  Modern (özellikle 2010-2024) NDX dönemi out-of-sample. Li-Mohanram 2019
  (Tier 1 #12) 2000-2014 dönemini adresler ama 2014 sonrası veri yok.
  Chen-Zimmermann 2022 Open Source Cross-Sectional Asset Pricing (Tier 2 #41)
  veri portalı muhtemelen güncel kanıt sağlar — methodology sayfası açıldığında
  oradan replikasyon yapılabilir.

- **Industry-median noise-adjusted scoring**: Mohanram'ın ham industry-median
  yaklaşımı 100-stock evrende noise-prone. **Bayesian shrinkage / hierarchical
  industry-effect estimation** literatürü yararlı olabilir ama bu konularda
  paper henüz Tier listesinde yok.

- **R&D capitalization-adjusted G-Score**: G-Score conservatism sinyalleri
  (R&D, capex, advertising) ham raporlu değerleri kullanıyor; **R&D
  capitalization yapılmış book equity** ile yeniden hesaplanmış BE/ME
  kalibrasyonu farklı sonuç verebilir. Lev-Sougiannis 1996 (Tier 2 #26) ve
  Peters-Taylor 2017 (Tier 2 #27) ingest edildiğinde bu boşluk kapanır.

## Cycle 7 (Li-Mohanram 2019) sonrası yüzeye çıkan boşluklar

- **PEG vs V/P bağımsız bilgi (Faz 2 sentez sırasında incelenecek):**
  Li-Mohanram 2019 [Tablo 3 Panel A, s.16] V/P ile NEGPEG arasında strong
  positive korelasyon olduğunu gösteriyor — yani iki value-skoru büyük
  ölçüde örtüşüyor. **Combined performansı PEG ekleyince marjinal artıyor mu
  yoksa V/P alone yeterli mi?** Strateji tasarımında her iki value-skor
  bağımsız sinyal mi yoksa tek-skor seçimi yeterli mi? Bu boşluk Faz 2'de
  literatür sentezi ile (özellikle Bradshaw 2004 atıf zinciri ile)
  incelenebilir.

- **Combined skor optimal weighting:** Li-Mohanram simple quintile
  intersection kullanıyor; **continuous-rank product, factor-analysis
  weighting, ML-based weighting** alternatifleri test edilmedi. Faz 3
  strateji tasarımının karar noktası — literatürde sistematik karşılaştırma
  yok.

- **Post-2014 modern replikasyon:** Li-Mohanram sample sonu 2012. FAANG
  dönemi (2014-2024) out-of-sample. Chen-Zimmermann 2022 (Tier 2 #41) Open
  Asset Pricing data portalı ile modern replikasyon yapılabilir; bu için
  methodology sayfası `wiki/methodology/data_sources.md` açılmalı.

- **V/P entity sayfası açılmayabilir:** Frankel-Lee 1998 paywall sebebiyle
  ingest edilmeyebilir. V/P'nin de facto wiki entity rolü
  [[li_mohanram2019_quality_value]] paper sayfası ve
  [[hou_mo_xue_zhang_2020_security_analysis]] paper sayfasından **birlikte**
  gelir (ikisi birbirini tamamlar). PEG ratio için ayrı entity açılmadı
  (ham bir oran tek başına entity hakkı yok).

## Cycle 8 (HMXZ Security Analysis) sonrası yüzeye çıkan boşluklar

- **HXZ 2015 q-factor origin paper henüz ingest edilmedi:**
  [[hou_mo_xue_zhang_2020_security_analysis]] q5 model'i kullanıyor ama q-factor
  framework'ün origin paperı (Hou-Xue-Zhang 2015 "Digesting Anomalies", Tier 1
  #3) wiki'de paper-sayfası olarak yok. q-factor methodology dolaylı kapsanıyor
  ama ortodoks formal tanımı eksik. C bloğu ingest'inde Tier 1 #3 öncelikli
  aday.

- **q5 model intangibles düzeltmesi yok:** I/A factor ham total asset growth.
  NDX tech-heavy evrene transfer için R&D capitalization yapan I/A versiyonu
  literatürde var mı belirsiz. Lev-Sougiannis 1996 (Tier 2 #26), Peters-Taylor
  2017 (Tier 2 #27) ingestleri ile cevap.

- **G-Score q-factor lens'inde test boşluğu:** [[mohanram2005_g_score]] q5
  model lens'inde HMXZ tarafından test edilmedi. Wiki için G-Score'un risk
  premium yorumu (factor exposure kanalı) belirsiz. Direct test eksik.

- **Combined stratejilerin q5 alpha'sı:** [[li_mohanram2019_quality_value]]
  combined F&V/P, G&V/P stratejilerinin q5 alpha'sı HMXZ'de doğrudan test
  edilmemiş. Bireysel bileşenlerinin q5 alpha'ları sıfıra yakın → combined
  alpha muhtemelen küçük ama doğrudan kanıt yok.

- **Buffett alpha riskli benchmark:** HMXZ Buffett'in Berkshire'ını q5'in
  ötesinde kalan alpha kaynağı olarak gösteriyor (q5 alpha 0.77%, t=2.69).
  Bu sistematik strateji için **achievable değil** (discretionary skill);
  wiki strateji tasarımı için Buffett-tipi alpha hedeflememeli, q5 risk
  premium'larını yakalamak hedef. Benchmark olarak kullanılırken bu
  ayrım korunmalı.

## Cycle 10 (Cooper-Gulen-Ion 2018) sonrası yüzeye çıkan boşluklar

- **Cooper-Gulen-Schill 2008 orijinal asset growth paperı paywall sebebiyle
  wiki'de yok:** CGS-Ion 2018 modern revisit referansla kullanılıyor; orijinal
  headline rakamlar (1968-2003 sample, decile spread, t-stat'lar) wiki'de
  doğrulanmamış. Original paper paywall'sız bulunabilirse ayrı sayfa açılır.

- **Myers-Majluf 1984 paperı wiki'de yok:** F_ΔLEVER ve F_EQ_OFFER
  bileşenlerinin literatür kökü; Piotroski 2000 [s.7] explicit atıfla bu
  paper'a dayanır. Ileride ingest adayı (Tier listesi dışı; ama F-Score
  derinleşmesi için).

- **Intangibles düzeltmesi paradoksu:** [[cooper_gulen_ion2018_asset_growth_factor_models]]
  Peters-Taylor 2017 metodunun (intangibles dahil total capital) asset
  growth factor performansını GÜÇLENDİRMEDİĞİNİ raporluyor. Tech firma
  intangibles için yeni metodoloji gerekli — Lev-Sougiannis 1996 alternatif
  capitalization, Eisfeldt-Papanikolaou 2013 organization capital (Tier 2 #28)
  ingestleri ile değerlendirilecek.

- **Lyandres-Sun-Zhang 2008 q-theory of investment paperı eksik:** Asset
  growth anomaly'nin rational yorumunun kanonik kaynağı; Tier listesinde
  değil. Q27 (rational vs mispricing horse race) için kritik.

- **Fairfield-Whisenant-Yohn 2003 accrual + asset growth decomposition
  paperı eksik:** Sloan accruals ↔ CGS asset growth overlap'inin formal
  ayrıştırması; Tier 2 #37, henüz ingest edilmedi. F_ACCRUAL ↔ Asset_Growth
  partial redundancy kanıtı için kritik.

## Cycle 9 (Sloan 1996) sonrası yüzeye çıkan boşluklar

- **Accrual computation methodology variance (1988 öncesi BS-based vs modern
  CFS-based):** [[sloan1996_accruals_anomaly]] [s.293] balance-sheet-based
  formül kullanır (1988 öncesi sample-period zorunluluğu); modern uygulamada
  Statement of Cash Flows (CFS)-based formül daha temiz (`Accruals = NI − CFO`).
  **Methodology farkı sonuçları büyük ölçüde benzer ama spesifik kalibrasyon
  farkları olabilir** — Faz 3 strateji tasarımında implementation tercihi.

- **NASDAQ accrual replikasyonu:** Sloan sample NYSE+AMEX, NASDAQ HARİÇ.
  Wiki'nin NDX evren amacı için accruals anomaly NASDAQ-dahil out-of-sample.
  Modern replikasyonlar (Hou-Xue-Zhang 2020 "Replicating Anomalies", Tier 1 #18)
  bu boşluğu doldurur — ingest gerekli.

- **Discretionary vs non-discretionary accrual decomposition:** Sloan total
  accruals; Jones model 1991 + Modified Jones (Dechow vd. 1995) discretionary
  accrual ayırır. Earnings management literature'a bağlı; Beneish 1999 M-Score
  forensic modelinin temel bileşeni. Tier 1 #15 ingest'i ile değerlendirilecek.

- **Post-publication accruals decay:** Green-Hand-Soliman (2011) "death of
  accruals anomaly" başlıklı paper; Tier listesinde değil. McLean-Pontiff 2016
  (Tier 1 #16) accruals'u test ediyor olabilir — anchor referans.

- **Tech firma accrual distortion (R&D capitalization eksikliği):** Sloan
  formülü R&D'yi expense olarak ele alır; tech firmalarda intangibles birikimi
  yapay düşük accrual sinyaliyle sonuçlanır. Lev-Sougiannis 1996 (Tier 2 #26),
  Peters-Taylor 2017 (Tier 2 #27) ingestleri ile R&D-adjusted accrual versiyonu.

## Cycle 11 (McLean-Pontiff 2016) sonrası yüzeye çıkan boşluklar

- **82 anomaly individual decay rakamları paperdan tek-tek çıkarılamıyor:**
  Paper aggregate %35 ortalamayı raporlar; spesifik anomaly-level decay
  setleri Internet Appendix'te. Wiki'de bu Internet Appendix metni yok →
  paper-spesifik (F-Score, Sloan accruals, vs.) decay rakamları aggregate
  multiplier üzerinden uygulanır. **Internet Appendix tam metni bulunup
  ingest edilirse** spesifik anomaly decay'leri tek-tek tabloya eklenebilir
  (Q28 ile bağlantılı).

- **Post-2012 modern anomaly decay replikasyonu (Q28):** McLean-Pontiff
  sample 2011'de bitiyor. Modern dönem (FAANG yükselişi, ML feature
  explosion, COVID-19 macro shocks) için aggregate decay rakamı henüz
  wiki'de yok. **Tier 1 #18 Hou-Xue-Zhang 2020 "Replicating Anomalies"**
  (~447 anomaly), **Tier 2 #41 Chen-Zimmermann 2022 Open Asset Pricing**,
  **Tier 2 #44 Jensen-Kelly-Pedersen 2023** üçü ortak modern decay kanıtını
  oluşturur; D bloğu boyunca ingest edilmeli.

- **NDX-spesifik post-pub decay sensitivity (Q29):** McLean-Pontiff
  [Tablo 8] post-pub decay büyük/likit/divid-payer/düşük-idio firmalarda
  daha güçlü. **NDX (FAANG-dominant) bu profilin en uç ucunda → decay
  aggregate %35'ten daha agresif (örn. %50) olabilir hipotezi.** Empirik
  doğrudan kanıt wiki'de yok; [[post_publication_decay]] decay-adjusted
  spread tablosunda **NDX agresif sensitivity ×0.50** Faz 3 stress-testi
  olarak kullanılır, baseline değil.

- **Composite-score-spesifik decay literatürü:** McLean-Pontiff aggregate
  82 individual anomaly seviyesinde; F-Score, G-Score, Magic Formula gibi
  **composite scoring strategies** için spesifik decay rakamları paperda
  yok. Wiki'de tek somut empirik karşılaştırma Li-Mohanram 2019 modern
  replikasyon (F-Score 3x, G-Score 3.5x düşüş, ama sample uzatma + universe
  + binary→continuous + industry revision karışık etkenler). Saf decay
  komponenti ayrıştırma için Green-Hand-Soliman 2011 (accruals-spesifik,
  Tier listesi dışı) + Piotroski-So 2012 (F-Score-spesifik, Tier listesi
  dışı) ek paperlar gerekli.

- **Lev-Srivastava 2020 value-spesifik post-2010 decay paperı eksik
  (Tier 2 #30):** McLean-Pontiff aggregate decay'i value/HML faktörü için
  spesifik olarak paperde decompose edilmiyor; Lev-Srivastava bu boşluğu
  doldurur. Q1 (S&P 500 value post-2000) ek kanıt için Tier 2'de seçici
  ingest adayı.

- **HXZ 2015 q-factor origin paperı eksik (Tier 1 #3):** McLean-Pontiff
  ile q5 model'in mathematical equivalence'ini somut kurmak için q4/q5
  origin paperı gerekli; HMXZ 2020 paper'ı q5 lens'iyle çalışıyor ama
  origin formal tanımı eksik. D bloğunun bir sonraki ingest aday adayı.

- **Reference list'inde Piotroski 2000 ve Mohanram 2005 explicit YOK:**
  McLean-Pontiff [s.28-29 ref] sadece Sloan 1996 (accruals), Banz 1981
  (size), Jegadeesh-Titman 1993 (momentum), Bali-Cakici-Whitelaw 2011 (MAX)
  vb. listed. F-Score ve G-Score paper sample içinde 82 anomaly'den biri
  olarak değerlendirilmemiş — bu nedenle aggregate decay multiplier wiki
  composite-score uygulamalarında **proxy** rolünde, **doğrudan kanıt**
  değil.

- **Düşük-inbound concept'ler (Cycle 12 consolidation pass bulgusu):**
  [[concepts/expected_returns_vs_cash_flows]] ve [[concepts/value_premium]]
  şu an yalnız 4'er inbound link alıyor — orphan değil ama izole. Cycle 5-11
  boyunca ingest edilen paperlar bu sayfalara değmedi. **Faz 2 sentez
  sırasında ya kullanım bağlamı zenginleştirilmeli (ingest sırasında
  ilgili paper sayfalarından yeni inbound oluştururken) ya da
  kavramsal-arşiv olarak kabul edilmeli** (Cochrane 2011 epistemik
  framing'i için bağımsız referans, strateji tasarımına dolaylı katkı).
  Karar Faz 2 başlangıcında verilir.

## Cycle 12 (Harvey-Liu-Zhu 2016) sonrası yüzeye çıkan boşluklar

- **HLZ Internet Appendix Tablo 5-6 (full 316 factor list + individual
  t-statistic'ler) wiki'de yok:** Paper main extract'te aggregate
  framework + Şekil 3 mark'leri (10-12 flagship factor) var; tam 316
  factor individual t-statistic listesi Internet Appendix'te. Wiki için
  spesifik anomaly'lerin (örn. Q-25 G-Score, F-Score components) HLZ
  census içindeki **explicit listed** durumu paperdan tek-tek
  doğrulanmadı. Internet Appendix bulunup ingest edilirse spesifik
  factor coverage genişler.

- **Composite scores HLZ 316 factor sample'da explicit dahil değil
  (Q31 paralel):** F-Score, G-Score, F&V/P, G&V/P gibi composite
  scoring strategies "individual factors" census çerçevesinde değil;
  HLZ retroactive composite multiple-testing test çalışması Faz 3
  baseline kararı için kritik. Chen-Zimmermann 2022 (Tier 2 #41) data
  portalı modern test imkanı sağlar.

- **Bayesian multiple testing wiki'de yok:** HLZ paper Appendix B'de
  Bayesian framework tartışıyor ama frequentist tercih ediyor (missing
  data + hesap karmaşıklığı). Wiki'de Bayesian multiple testing
  literatürü yok. Avramov-Cheng-Metzker 2023 (Tier 2 #43) "ML vs
  Economic Restrictions" Bayesian variable selection ile
  HLZ-frequentist'i complementary; ingest gerekli.

- **HLZ Section 5 correlation-aware structural model derinlemesine
  kullanılmadı:** HLZ Section 5'te factor returns Pearson correlation
  ile structural model + estimation framework var; wiki bu
  methodology'i aggregate cutoff rakamları için kullanıyor, ama
  spesifik factor pairs için correlation-aware adjustment yok.
  FGX 2020 (Tier 1 #21) "Taming the Factor Zoo" bu methodology
  extension'ı; ingest sonrası değerlendirme.

- **Time-varying recommended cutoff'lar wiki'de yok:** HLZ Şekil 3
  1965-2032 time series cutoff projection (Bonferroni 1.96 → 3.78 →
  4.00) sunar. Wiki şu an 2012 ve 2032 statik rakamları kullanıyor;
  spesifik dönem (örn. Piotroski 2000 yayım dönemi 1976-1996) için
  HLZ time-aware cutoff'a gerek yok (anchor cutoff yeterli).

- **Sharpe Ratio multiple-testing düzeltmesi (Bailey-LdP 2014, Tier 1 #19):**
  Strateji performansının Sharpe ratio cinsinden multiple-testing-aware
  evaluation'ı için Bailey-Lopez de Prado 2014 "Deflated Sharpe Ratio"
  gerekli. HLZ analoğu portfolio-level Sharpe için. D bloğunun #3 aday.
  Faz 3 strateji backtest spec'inde DSR baseline.

- **HLZ paper "theory-supported vs purely empirical" hierarchy
  belirsizliği [s.5]:** Paper "A factor derived from a theory should
  have a lower hurdle than a factor discovered from a purely empirical
  exercise" diyor ama spesifik cutoff vermiyor. Wiki için: q-theory-
  derived q5 model factors (CMA, RMW) için HLZ-spesifik lenient hurdle
  argümanı yapılabilir mi? Theoretical justification'ın multiple-testing
  hurdle'a etkisi açık soru.

## Cycle 13 (Hou-Xue-Zhang 2020 "Replicating Anomalies") sonrası yüzeye çıkan boşluklar

- **HXZ 2020 paper Internet Appendix tam 447 anomaly listesi wiki'de
  yok:** Paper Tablo 1 [s.36+] ham listesi var; wiki için aggregate
  framework yeterli, individual anomaly t-statistic'leri için Internet
  Appendix tam metin ek ingest gerekirse. Spesifik wiki paperları
  için (Mohanram G-Score, Frankel-Lee V/P) replication status
  Internet Appendix'te detaylı.

- **JKP 2023 (Tier 2 #44) "Replication Crisis in Finance" eksikliği:**
  HXZ 2020 + JKP 2023 modern replication crisis tartışmasının iki
  ayağı; JKP 2023 ML-aware framework'le HXZ 2020'yi günceller +
  global data extension. Q33 (post-2014 modern replication) tam
  cevabı için kritik.

- **Chen-Zimmermann 2022 (Tier 2 #41) "Open Asset Pricing" data
  portalı eksikliği:** HXZ 2020 methodology'i Chen-Zimmermann modern
  data ile replikasyon ön koşul; Faz 3 strateji backtest spec'inde
  data portalı baseline.

- **Equal-weight vs value-weight methodology tercih kararı (Q32 yeni
  paralel):** Wiki Faz 3 backtest spec'i için methodology default
  tercihi; HXZ NYSE-VW vs MP equal-weight iki uç. Wiki amaç evrenleri
  natural NYSE-VW fit ama equal-weight upper bound referansı.

- **Intangibles-aware factor replication (HXZ 2020'de R&D-to-market
  q-factor sig):** R&D-to-market dört darbeden 4/4 — NDX evrene
  transferli intangibles-aware factor için kritik kanıt; ama
  spesifik intangibles methodology (Lev-Sougiannis 1996, Peters-Taylor
  2017) wiki'de hala yok. Tier 2 #26, #27 ingest planı için
  Q23 motivasyonu güçlendi.

- **Distress anomaly (Campbell-Hilscher-Szilagyi 2008, Tier 2 #33)
  ingest planı sorgulanır:** HXZ 2020 paper'da distress "virtually
  nonexistent" [s.2] (failure prob., O-Score, Z-Score, credit
  rating insig). Tier 2 #33 ingest beklenir mi yoksa "sample
  evidence: distress factor zoo'da ölü" sonucu yeterli mi?
  Faz 2 başlangıcında karar.

- **Composite scores HXZ 2020 census'da yok (Q31 ile paralel):**
  F-Score, G-Score, F&V/P, G&V/P composite scoring strategies
  individual factor census dışında. F-Score quarterly (Fq)
  individual factor olarak replicate ama cross-product (quality ×
  value) form'u test edilmemiş. Composite-spesifik replication
  rate retroactive test JKP 2023 ek ingest.

- **HXZ 2020 paper Section 5'te "Taking Economic Theory Seriously"
  agenda'sı:** Paper FF-tradition vs q-factor tradition farkını
  theory-based vs ad-hoc factor olarak sunuyor. Wiki için: q-factor
  model'i FF5'e tercih etme gerekçesi olarak theoretical motivation
  argümanı (Cochrane "division of labor" ile uyumlu). Faz 3'te
  factor model tercihi kararının kavramsal arka planı.

- **Internet Appendix anomaly-level subsumption haritası (Q34):**
  HXZ 2020 161 sig anomaly üzerinde q-factor regression — 46 alpha
  sig kalır. Hangi anomaly hangi q-factor (I/A vs Roe vs Eg) ile
  span ediliyor detay tablo paperdan teyit. FGX 2020 (Tier 1 #21)
  "Taming the Factor Zoo" tam horse race.

## Cycle 14 (Bailey-Lopez de Prado 2014 DSR) sonrası yüzeye çıkan boşluklar

- **Wiki ingested paperlardan reported Sharpe ratio'lar yok (Q35):**
  DSR formülü ham return time-series + N + V[{SR}] + skewness +
  kurtosis gerektirir. Wiki'deki paperlar reported t-stat + spread
  veriyor; Sharpe explicit verilmemiş. Yaklaşık parametrik tahmin
  `Sharpe ≈ √(t² / T)` mümkün ama tam DSR için Internet Appendix
  ham return data'sı + Chen-Zimmermann 2022 (Tier 2 #41) data
  portalı + JKP 2023 (Tier 2 #44) ek ingest gerekli.

- **Return distribution shape (skewness, kurtosis) verisi yok (Q36):**
  Wiki'deki ingested factor strategy'lerin (F&V/P, G&V/P, G&NEGPEG,
  Sloan F_ACCRUAL, R&D-to-market, Cash-based Cop, UMD) DSR-2/3
  düzeltmesi için return distribution istatistikleri ham veri
  bağımlı. Genel literatür: equity long-short hedge return'lerde
  negative skew + fat tails tipik (Daniel-Moskowitz 2016 momentum
  crashes); spesifik wiki factorler için kalibrasyon Faz 2'de.

- **Çift düzeltme prensibi (Q37) Faz 3 tasarım kararı:**
  DSR-1 trial-count + HLZ MT-corrected birlikte uygulandığında
  over-correction riski; tek-düzeltme prensibi Faz 3 backtest
  spec'inde belirlenmeli.

- **Bailey, Borwein, López de Prado, Zhu (2014) "Pseudo-Mathematics
  and Financial Charlatanism" eksikliği:** Bailey-LdP DSR'ın foundation
  paper'ı; backtest overfitting matematiksel formal proof. Tier
  listesinde değil ama Faz 2 backtest spec için ek ingest adayı.

- **Bailey & López de Prado (2012a) "Sharpe Ratio Efficient Frontier"
  eksikliği:** PSR origin paper; DSR'ın altyapısı. Tier listesinde
  değil ama yine Faz 2 ek ingest adayı.

- **Bailey, López de Prado (2014a) PBO non-parametric alternatif:**
  Probability of Backtest Overfitting non-parametric methodology;
  highly non-Normal distribution'larda DSR parametrik kestirim
  hatası artar. Faz 2 PBO + DSR birlikte kullanım methodology kararı.

- **Memory effects assumption Bailey-LdP'ta tartışılmıyor:** "Loss
  maximization" iddiası mean-reverting financial series varsayımına
  dayanır. Strong-trend series'lerde (UMD momentum) memory pozitif
  (auto-correlated) — bu durumda backtest overfit "sıfır
  out-of-sample" classic case. Wiki Faz 3 spec'inde momentum
  strategies için bu nüans dikkate alınmalı.

- **Faz 3 methodology/backtest_spec.md eksikliği (Cycle 15+'a
  ertelendi):** Cycle 14 sonrası Faz 1 mini consolidation kararı;
  backtest spec açma zamanı orada belirlenecek.

## Cycle 15 (Lev-Sougiannis 1996 R&D Capitalization) sonrası yüzeye çıkan boşluklar

> 📝 **F bloğu (intangibles) Faz 1 finalizasyon paper #1 ingest sonrası.**
> Cycle 9-14 boyunca tekrarlanan "intangibles methodology eksikliği"
> boşluğu **kısmen kapandı**; Cycle 16 Peters-Taylor 2017 + Cycle 17
> Lev-Srivastava 2020 ile tam kapanma.

- **Total intangible capital methodology (Lev-Sougiannis sadece R&D):**
  Lev-Sougiannis [s.119] advertising flow proxy olarak Eq. (4)'te
  ama detaylı capitalization yapmıyor; organization capital + brand
  value tamamen kapsam dışı. **KAPANDI Cycle 16'da:** Peters-Taylor
  2017 (Tier 2 #27) total intangible capital (Knowledge + Organization
  + External) methodology Lev-Sougiannis R&D-only'un strict
  generalization'ı; q^tot proxy + perpetual inventory aynı yapı, 2
  yeni component eklenmiş.

- **Post-1991 R&D-aware factor performance:** Lev-Sougiannis sample
  1975-1991. Modern dönem (post-1991, FAANG era 2000-2024) Lev-Sougiannis
  paperin kapsamı dışı. **Lev-Srivastava 2020 (Tier 2 #30, Cycle 17
  ingest)** post-2010 value collapse'i Lev-Sougiannis methodology
  üzerinden açıklar.

- **Industry amortization rate güncellemesi modern data ile (Q38
  paralel):** Lev-Sougiannis 1975-1990 data, 4-digit SIC. Modern tech
  sektörler (software 7372, biotech 8731, semiconductors 3674) sektörel
  granular amortization rates Faz 3 NDX strategy spec için kalibrasyon
  gerektirir; modern data Chen-Zimmermann 2022 (Tier 2 #41) + JKP 2023
  (Tier 2 #44) ek ingest.

- **R&D capital stock vs flow ölçüm farkı (Q39 paralel):** HXZ 2020
  R&D-to-market formal tanımı tek-tek teyit edilemedi (text extract'te
  detay yok). Lev-Sougiannis [s.133 fn 22] proper capitalization
  stock 3-yıl flow toplamı'ndan dramatic farklı (top decile RDC/M
  coef proper capitalization 0.0114 t=3.88 sig vs 3-year sum 0.0078
  t=1.20 insig). Faz 3 spec'inde proper capitalization stock
  recommendation; HXZ paperin Internet Appendix detayı bağımlı.

- **Mispricing vs extra-market risk yorumu açık [Lev-Sougiannis s.134]:**
  Paper iki alternative hipotezi disentangle etmiyor. HXZ 2020
  R&D-to-market q-factor alpha sig "extra-market risk factor" yorumuna
  eğilimli; Lev-Sougiannis "mispricing" yorumu LSV 1994 contrarian
  literature ile uyumlu. Wiki taraf tutmaz; mathematical equivalence
  (Cochrane 2011).

- **B/M coefficient kaybı R&D-intensive firms'da (Lev-Sougiannis
  Tablo 5):** Upper-quartile RDC firms'da RDC/M dahil edilince B/M
  sig kaybediyor — HML factor R&D-yoğun firms'da yapay sinyal mi
  yoksa RDC/M ile partial overlap mı? Empirik horse race FGX 2020
  (Tier 1 #21) "Taming the Factor Zoo" framework ile tam cevap;
  Faz 2 ingest adayı.

- **R&D-aware Sloan accruals revision (Q26 partial):** Adjusted
  Sloan accruals = traditional + (RD_t - RA_t). Wiki'de henüz formal
  formülasyon yok; Faz 3 spec'inde uygulanacak. Peters-Taylor 2017
  total capital methodology ile genişler.

- **GICS sektör mapping (Q38 paralel):** NDX evrende GICS Level-2/3/4
  hangi seviyede mapping yapılacak; SIC 1996 amortization rates →
  modern GICS sektör translation methodology Faz 3 backtest spec için
  ön koşul. Mohanram G6 industry-median (Q19 sektör sınıflandırma)
  ile bağlantılı.

## Cycle 16 (Peters-Taylor 2017 Intangible Capital + q-Theory) sonrası yüzeye çıkan boşluklar

> 📝 **F bloğu (intangibles) #2 ingest sonrası.** Cycle 15 Lev-Sougiannis
> R&D-only methodology'sini Peters-Taylor total intangible capital'a
> genişletti. Tam F bloğu kapanışı Cycle 17 Lev-Srivastava 2020 ile.

- **KAPANDI: Total intangible capital methodology** (Cycle 15'te açılan
  boşluk, yukarıda belirtildi). Peters-Taylor 2017 [Eq. 9-11] q^tot proxy
  + perpetual inventory methodology üçlü component (Knowledge +
  Organization + External) Lev-Sougiannis'in strict generalization'ı.

- **Eisfeldt-Papanikolaou 2013 organization capital factor portfolio
  direct evidence eksik (Q41 paralel):** Peters-Taylor [s.5, 10] Eisfeldt-
  Papanikolaou 2013'e referans veriyor — organization capital factor
  portfolio direct return prediction kanıtı sağlar (Peters-Taylor q
  theory test eden corporate finance paper, factor portfolio değil).
  Tier 2 #28 ingest Faz 2'de Q41 horse race (Peters-Taylor vs Lev-
  Sougiannis vs Eisfeldt-Papanikolaou) için kritik.

- **Modern Peters-Taylor methodology replikasyonu eksik (Q40 paralel):**
  Paper sample 1975-2011. Modern dönem (2012-2024 FAANG era + COVID +
  ML feature explosion) için Peters-Taylor methodology'i replikasyonu
  wiki'de yok. SG&A organization capital allocation θ=30% NDX-spesifik
  kalibrasyonu (tech firma SG&A büyük kısmı sales force / customer
  acquisition; recurring-revenue model şirketlerde) Faz 3 spec için
  modern data + sensitivity test gerekli.

- **Q-factor model + Peters-Taylor methodology entegrasyonu eksik
  (Q23 partial-stronger):** HXZ q-factor model I/A factor ham total
  asset growth (intangibles dahil değil). Peters-Taylor q^tot proxy
  HXZ q-factor I/A versiyonu yok wiki'de — modern q-factor implementation
  + total intangible capital entegrasyonu yapan paper bulunmalı (Faz
  2 aday). Hou-Xue-Zhang 2015 q-factor origin paper (Tier 1 #3) ingest
  + Peters-Taylor methodology kombinasyonu Faz 3 backtest spec için
  ön koşul.

- **R&D-to-market Peters-Taylor total intangibles versiyonu test eden
  paper yok (Q42 yeni):** HXZ 2020 R&D-to-market dört darbe 4/4 hayatta
  kalan factor — sadece R&D-only formülasyonu (Lev-Sougiannis temeli).
  (R&D + Organization + External) / Market versiyonu modern data +
  Peters-Taylor methodology ile direct test wiki'de yok. CGS-Ion 2018
  paralel bulgu (Peters-Taylor methodology asset growth açıklayıcı
  gücünü güçlendirmiyor) → R&D-to-market'te benzer hipotez cevap
  arar.

- **Cumulant estimator alternative methodology (Erickson-Jiang-Whited
  2014):** Peters-Taylor measurement-error-corrected slope estimates
  + ρ²/τ² test statistics için cumulant estimator kullanıyor. Wiki'de
  measurement error econometrics literature kapsamlı yok; Faz 3
  backtest spec'inde regression slope bias-corrected estimation
  gerekecek (özellikle Q10 corr/std-error correction ile bağlantılı).

- **KAPANDI: Lev-Srivastava 2020 placeholder** (Cycle 17 ingest tamam):
  Peters-Taylor methodology'sinin post-2010 value collapse açıklamasında
  uygulandığı F bloğu kapanış paper ingest edildi; Q1 (S&P 500 value
  post-2000) **fully-answered** oldu. F bloğu 3-katmanlı methodology
  hierarchy tamamlandı.

## Cycle 17 (Lev-Srivastava 2020 Value Failure) sonrası yüzeye çıkan boşluklar

> 📝 **F bloğu (intangibles) Faz 1 finalizasyon paper #3 ve KAPANIŞ
> ingest sonrası.** F bloğu hierarchy 3 ayak tamam (Lev-Sougiannis +
> Peters-Taylor + Lev-Srivastava). Faz 1 → Faz 2 geçişi yol haritası:
> Cycle 18 Beneish 1999 + Cycle 19 KARAR NOKTASI (Asness QMJ 2019) +
> Cycle 20 Faz 1 sertifikası.

- **KAPANDI: Q1 (S&P 500 value post-2000) tam cevabı.** Lev-Srivastava
  2020 anchor cevap; 50% largest stocks focus + decade-by-decade
  decomposition + iki mekanizma + adjusted methodology dramatic effect.

- **F bloğu kapanış sonrası kalan boşluklar:**
  1. **Eisfeldt-Papanikolaou 2013 organization-capital factor direct
     evidence** — Faz 2 seçici ingest aday olarak **kaldı** (Q41 4-way
     horse race tamamlamak için; 3 ingest edilen paper + 1 eksik =
     methodology infrastructure ama factor portfolio kanıtı eksik)
  2. **Post-2018 (FAANG + AI dönemi 2019-2024) replikasyon eksikliği**
     — Lev-Srivastava sample sonu 2018; modern dönem out-of-sample
     (Q44 yeni)
  3. **Mean reversion slowdown decomposition** — macro-economic vs
     intangibles ayrıştırma direct test eksik (Q43 yeni)
  4. **Adjusted HML factor portfolio empirik kanıt** — Lev-Srivastava
     methodology'i HML factor inşasına uygulayan modern paper wiki'de
     yok; Faz 3 backtest spec'i için adjusted HML hesaplama
     infrastructure hazır ama empirik validation eksik
  5. **Value-trap-avoidance filter design** (Q45 yeni) — Lev-Srivastava
     Logit Table 1 escape attributes Faz 3 strategy spec'inde
     entegrasyon kararı; literatürde sistematik karşılaştırma yok

- **Lev-Srivastava methodology infrastructure-dependent:**
  Adjusted HML hesaplama için R&D capital (Lev-Sougiannis perpetual
  inv) + SG&A intangibles allocation (Enache-Srivastava 2018 + Peters-
  Taylor θ=30%) + amortization rates (BEA Li 2012). Wiki'de bu
  adjustments'ları yapan replicable code yok; Faz 3 backtest spec'inde
  methodology rebuild gerekli.

- **Causal vs correlational distinction (Q43 paralel):** Lev-Srivastava
  iki mekanizma (intangibles + macro) post-2007 birlikte gözleniyor;
  causal identification testi yok. Mean reversion slowdown intangibles
  bias'in mekanizmasının kendisi mi yoksa bağımsız bir post-2007 olgu
  mu open question. Faz 2 design decision.

- **Sektör compositional shift (paper Section 9 partial discussion):**
  "Value sektör" sınıflandırması dönem-spesifik (banking 2007-2018
  trapped); 1970-1989'da farklıydı. Cross-sectional sektör compositional
  shift wiki'de henüz yapısal kanıt sayfası yok.

## Cycle 18 (Beneish 1999 M-Score) sonrası yüzeye çıkan boşluklar

> 📝 **Faz 1 son zorunlu Tier 1 ingest sonrası.** C/D hard kriter
> forensic kategorisi tamamlandı. Cycle 19 KARAR NOKTASI öncesi son
> disiplin paperı.

- **KAPANDI: "Forensic earnings filter eksikliği"** boşluğu
  (Cycle 5'ten beri F_Score sayfasında `(sonra) [[M_Score]]` placeholder
  + Tier 1 forensic kategorisi boş). [[beneish_1999_m_score]] +
  [[M_Score]] entity ile **wiki'nin en eski açık placeholder'ı**
  doldurulu.

- **Hala eksik (Cycle 7-8'den beri placeholder, Cycle 18'de hala
  paywall):**
  Beneish-Lee-Tarpley 2001 "Predicting Extreme Returns" — M-Score
  → return prediction direct evidence; Q9 tam cevabı için
  Beneish-Lee-Tarpley + Gray-Carlisle 2012 (Tier 3 kitap)
  combined empirical test ön koşul.

- **Cycle 18 yeni boşluklar:**
  1. **M-Score modern post-publication replikasyonu eksik** (Q48
     paralel) — 25 yıl sample (1999-2024); Chen-Zimmermann 2022 +
     JKP 2023 ile değerlendirme. Forensic detection paper, return
     prediction değil → decay multiplier uygulanması nüanslı.
  2. **M-Score intangibles-aware revize methodology eksik** (Q47
     paralel) — F bloğu 3 ayak entegrasyonu (Lev-Sougiannis +
     Peters-Taylor + Lev-Srivastava) M-Score'a uygulanmamış. Tech
     firma high SGI + high AQI false positive yapısal riski; NDX
     evren için ön koşul.
  3. **F-Score / G-Score + M-Score combined backtest empirical
     kanıt eksik** (Q9 paralel) — Quantitative Value (Gray-Carlisle
     2012) Tier 3 kitap; akademik combined backtest paper yok.
     Faz 2 sentez aşamasında modern data ile combined empirical test.
  4. **M-Score size-spesifik kalibrasyon eksik** (Q46 paralel) —
     Beneish sample küçük-cap-tilted (manipulators median TA $43M);
     S&P 500 / NDX large-cap evrene transfer için kalibrasyon gerekli.

- **Origin attribution dual pattern (Cycle 18 keşif):**
  M-Score TATA bileşeni Sloan total accruals ile **methodology
  paralel** (working capital change - depreciation; aynı yapı) AMA
  Beneish reference list [s.20-21] **Sloan 1996 explicit listed
  DEĞİL** — Healy 1985 + Jones 1991 cite ediyor (earnings management
  research). F_ACCRUAL/G3 origin paterninden sapma; literatür hattı
  Healy-Jones (Sloan değil). Wiki için: Sloan + M-Score TATA
  complementary use possible (mispricing + fraud detection iki
  epistemik düzlem).

- **3 bileşen insig (DEPI, SGAI, LVGI):** Modern uygulamalarda
  5-bileşen M-Score model alternatifi; Beneish bunları robustness
  için tutuyor ama statistical ayrımcı değiller. Faz 3 spec'inde
  5-bileşen vs 8-bileşen sensitivity test.

## Cycle 19 (Asness QMJ 2019) sonrası yüzeye çıkan boşluklar

> 📝 **Faz 1 son ingest paperı sonrası.** Cycle 20 = Faz 1 sertifikası
> + §11.5 ZORUNLU 4-cycle consolidation pass. Q2 fully-answered ANCHOR
> (large-cap quality vs value).

- **KAPANDI: "Asness QMJ 2019 large-cap quality kanıtı eksik"** boşluğu
  (Cycle 5'ten beri factors/MoC_factors "Quality (boş)" placeholder +
  Cycle 7-8 boyunca Q2 partial cevap caveat). Q2 fully-answered (Cycle
  19); 13 cycle partial sonrası tam cevap.

- **KAPANDI: "Quality factor 4-dimension breakdown eksik"** boşluğu
  (FF15 RMW sadece operating profitability; HMXZ Tablo 4 composite QMJ;
  4 dimension wiki'de hiçbir yerde yok → Cycle 19'da kapanır).

- **Hala eksik (Cycle 7-8'den beri placeholder)**:
  - **Novy-Marx 2013 GP/A** — QMJ paper [s.7] explicit cite ediyor
    (Profitability dimension GPOA literatür hattı kökü); ayrı paper
    olarak ingest edilmemiş; Faz 2 aday
  - **Frazzini-Pedersen 2013 BAB** — QMJ Safety dimension; Tier 3 #58
  - **Frazzini-Israel-Moskowitz 2018 trading costs** (paywall, Tier 3
    #52) — annual rebalance + cost analysis
  - **AQR data setleri** (Tier 3 #55) — large-cap-only kalibrasyon

- **Cycle 19 yeni boşluklar:**
  1. **QMJ post-2012 modern replikasyonu eksik** (Q51 paralel) — sample
     sonu Dec 2012; FAANG era + COVID + AI 2013-2024 out-of-sample;
     modern data Chen-Zimmermann 2022 + JKP 2023 ile değerlendirme
  2. **NDX-spesifik QARP kalibrasyonu eksik** (Q50 paralel) — F bloğu
     intangibles-aware Bm ile QARP kombinasyonu Faz 3 design; Li-
     Mohanram (binary intersection) vs Asness QARP (continuous)
     operationalization horse race
  3. **F bloğu 3 ayak methodology + QMJ entegrasyonu eksik** (Q49
     paralel) — QMJ 4 dimension intangibles-aware değil; NDX FAANG/
     tech-heavy evrene transfer için Lev-Sougiannis + Peters-Taylor +
     Lev-Srivastava methodology entegrasyonu Faz 3 ön koşul
  4. **4 dimension hangisi en güçlü dimension-spesifik alpha hierarchy**
     (Q49 paralel) — paper "composite QMJ the strongest" diyor ama
     dimension-spesifik t-statistic decompose edilmemiş; Faz 2 sentez
  5. **Annual uyarlama primum sensitivity test eksik** — paper monthly
     rebalance; Faz 3 spec'inde DSR-aware annual uyarlama (Q35 paralel)
  6. **FF5 vs QMJ doğrudan horse race eksik** — QMJ paper 4-factor
     (Carhart) baseline; FF5 RMW + CMA factor exposure'larıyla horse
     race paperde yok; Q14 + Q15 paralel; HXZ 2015 q-factor origin
     paper bekliyor

- **Sloan zinciri 4. halka (Cycle 19 keşif):** QMJ Profitability ACC
  component **Sloan 1996 explicit cite [s.7]** — F_ACCRUAL/G3 origin
  paterni paralel; M-Score TATA (Healy-Jones) ayrı zincir. Sloan
  zinciri 4 paper × 23 yıl: Sloan 1996 → Piotroski 2000 → Mohanram
  2005 → **Asness 2019**. Origin attribution dual pattern wiki için
  literature continuity dokümante edildi.

- **HMXZ q5 captures QMJ vs Asness 4-factor sig (Cycle 19 epistemik
  düzlem ayrımı):** İki paper farklı methodology aynı bulgu için iki
  yorum (Cochrane mathematical equivalence): mispricing (4-factor
  alpha sig) vs risk premium (q5 captures). Wiki taraf tutmaz; complementary
  epistemic application; çelişki olarak listelenmedi.

## Cycle 22 (Israel-Moskowitz 2013) sonrası yüzeye çıkan boşluklar

> 📝 **Faz 2 ilk gerçek paper ingest sonrası.** E bloğu (large-cap
> reality) #1 ingest. Faz 1'de yumuşak kapsamla bırakılmış "E bloğu
> direct kanıt eksikliği" KAPANDI; Cycle 23 Novy-Marx 2013 GP/A +
> opsiyonel FF 2008 ile E bloğu sertleşmesi devam.

- **KAPANDI**: "E bloğu (large-cap reality) Faz 1'de yumuşak kapsam"
  boşluğu (Cycle 14 mini-consolidation kararı). Israel-Moskowitz 2013
  86-yıl direct kanıt + 5×5 size×value/momentum decomposition + long-only
  S/H/U sub-portfolio explicit raporlama → Faz 1 yumuşak gerekçesi
  (HXZ NYSE-VW + QMJ Tablo A4 + dört darbe sentezi) **direct ingest
  sertleştirme** ile tamamlandı. Q14 HML-spesifik fully-answered; Q4
  partial-stronger; Q11 86-yıl confirmation; Q33 partial-stronger.

- **KAPANDI / partial-stronger**: Q14 (FF5 large-cap-only başarısızlık
  portföyü) HML-spesifik fully-answered (Israel-Moskowitz [Tablo 3]
  size Q4-Q5 vanilla HML INSIG); CMA/RMW direct test paperde yok →
  Q14 HML için fully, CMA/RMW için partial-stronger. Tam cevap için
  Hou-Xue-Zhang 2015 q-factor origin (Tier 1 #3) + AQR data setleri
  (Tier 3 #55) ek ingest.

- **YENİ (Cycle 22)**: Long-only vs long-short anomaly performansı
  decomposition (Q52). Wiki amaç evrenleri long-only retail-style;
  Israel-Moskowitz long-only S/H/U direct kanıt sağladı. F&V/P + G&V/P
  composite + QARP framework long-only versions için modern data ile
  empirik validation eksik (Chen-Zimmermann + JKP 2023 ek ingest).

- **YENİ (Cycle 22)**: Time-conditional anomaly decay paradigm divergence
  (Q53). MP publication-anchored discrete change vs Israel-Moskowitz
  20-yıl dummy + linear trend insig — iki farklı time variation
  paradigması; aggregate analysis level'da farklı methodology. Faz 2
  sentez sırasında Chen-Zimmermann + JKP 2023 ile her iki paradigmanın
  post-2012 dönem testi.

- **YENİ (Cycle 22)**: Size × shorting interaction decomposition (Q54).
  Israel-Moskowitz [Tablo 3 + Fig.2] direct kanıt: large-cap + long-only
  kombinasyonu için **vanilla HML reject + UMD long-only sub-optimal
  (sadece %38 long contribution)**. Wiki strategy spec için en uygun
  konfigürasyon: F&V/P + G&V/P composite + long-only momentum +
  intangibles-aware Bm rebuild — Israel-Moskowitz size×shorting
  matrix'e en uygun.

- **HXZ 2020 vs Israel-Moskowitz 2013 — çelişki YOK (çift teyit)**:
  Plan'daki "potansiyel çelişki" hipotezi paper okuma sonrası reddedildi.
  Israel-Moskowitz NYSE breakpoints + value-weighted methodology HXZ
  2020 tercihiyle uyumlu; [Tablo A2] equal-weighted alpha 8.4% t=2.81
  vs value-weighted INSIG paterni HXZ 2020'nin merkezi methodology
  eleştirisini 7 yıl önceden örnekliyor. **[[meta/contradictions]]
  yeni entry açılmadı** (mevcut 2 entry korunur); Israel-Moskowitz
  HXZ 2020'nin **erken methodology anchor'ı** olarak [[concepts/anomaly_replication]]
  + [[methodology/backtest_spec]] §1.3'te konumlandırıldı.

- **Cycle 22 hala eksik**: Hong-Lim-Stein 2000 + Grinblatt-Moskowitz
  2004 (Israel-Moskowitz [s.284-286] explicit eleştirir, sample-spesifik
  bulgular); Avramov-Chordia-Jostova-Philipov 2007/2012 (credit-rating
  conditional momentum); Frazzini-Israel-Moskowitz 2018 (Tier 3 #52
  paywall; firm-level trading cost). Tier listesi dışı; Faz 2 paywall
  durumuna göre değerlendirilir.

## Cycle 23 (Novy-Marx 2013 Gross Profitability) sonrası yüzeye çıkan boşluklar

> 📝 **B kompleman / Quality blok ingest sonrası.** Faz 1 sertifikası
> YUMUŞAK ikinci eksiklik (Cycle 22 E bloğu sonrası); Profitability
> zinciri origin paper ingest. Wiki için yapısal kazanım: **iki paralel
> quality zinciri** (Sloan + Profitability) dokümante.

- **KAPANDI**: "Novy-Marx 2013 GP/A direct ingest eksik" boşluğu
  (Cycle 19'dan beri işaretli; QMJ paper [s.7] explicit cite ama
  wiki'de paper sayfası yoktu). Profitability zinciri 1. halka
  doldurulu.

- **KAPANDI / partial**: "FF15 RMW factor literatür hattı kökü eksik"
  — Novy-Marx FF15 paper [s.4] cite kökü direct ingest; Profitability
  zinciri 2. halka methodology hierarchy dokümante. RMW Ope vs GP/A
  vs Cop direct horse race Q55 ile kalan tam comparison.

- **HALA EKSİK**: Ball-Gerakos-Linnainmaa-Nikolaev 2016 (Tier 1 #9;
  ingest edilmedi); HMXZ Cop methodology origin Ball-GLN 2016; **Profitability
  zinciri 4. halka empirik validation paper sayfası eksik** (Cop
  HXZ 2020 [Tablo 5] ve HMXZ Tablo 5'te dolaylı kanıt; standalone Ball-GLN
  2016 paper sayfası açılmadı). Faz 2 ingest aday — Profitability
  zinciri tamamlama için.

- **YENİ (Cycle 23)**: Q55 (GP/A vs RMW Ope vs QMJ GPOA vs Cop horse
  race); Q56 (Intangibles-aware GP/A FAANG firmalar için F bloğu +
  Profitability zinciri entegrasyonu); Q57 (GP/A annual vs quarterly
  rebalance trade-off); Q58 (Industry-adjusted GP/A anomaly explanation
  power Cochrane #1 paralel).

- **Çelişki YOK**: Israel-Moskowitz 2013 vs Novy-Marx 2013 (aynı yıl
  iki paper, iki farklı boyut; çift kompleman); FF06 vs Novy-Marx
  (methodology farkı, empirik çürütme değil); Cop > GP/A (evrim,
  çelişki değil). [[meta/contradictions]] yeni entry açılmadı.

- **Profitability zinciri yapısal kazanım**: Sloan zinciri (mispricing/
  accruals 4 paper × 23 yıl) **paralel'i** (productive efficiency 4
  paper × 7 yıl). İki zincir QMJ 4-dimension'da Profitability dimension
  6 measure içinde GPOA + ACC yan yana birleşiyor — wiki için literature
  continuity çekirdek dokümantasyon.

## Cycle 25 (Eisfeldt-Papanikolaou 2013 Organization Capital) sonrası yüzeye çıkan boşluklar

> 📝 **F bloğu kompleman ingest sonrası.** Faz 1 sertifikası YUMUŞAK
> üçüncü eksiklik kapanışı; Q41 4-way horse race fully-answered.
> F bloğu Cycle 17'de 3-katmanlı kapatıldı, Cycle 25 4-katmanlı
> sertleştirme **methodology infrastructure (1+3+4) + factor portfolio
> anchor (2) ayrımı**.

- **KAPANDI**: "F bloğu factor portfolio direct evidence eksik"
  boşluğu (Cycle 16'dan beri Peters-Taylor cross-link); Eisfeldt-
  Papanikolaou direct ingest 4. ayak factor portfolio anchor
  tamamlanır.

- **KAPANDI**: Q41 4-way horse race methodology infrastructure
  dokümante (Lev-Sougiannis + Peters-Taylor + Lev-Srivastava +
  Eisfeldt-Papanikolaou).

- **KAPANDI / partial**: Q23 NDX intangibles q-factor span (OC
  factor Carhart 4F altında α=3.9% sig 1% — q-factor span direct
  text yok ama industry-relative methodology q-factor I/A vs Roe
  altında muhtemelen sig kalır; HXZ 2015 q-factor origin paper ek
  ingest tam cevap).

- **KAPANDI / partial**: Q40 Modern Peters-Taylor methodology
  replikasyonu (Eisfeldt-Papanikolaou 1970-2008 sample Peters-Taylor
  1975-2011 büyük overlap; OC factor portfolio direct evidence
  Peters-Taylor q theory test'inden farklı perspektif).

- **HALA EKSİK**: HXZ 2015 q-factor origin paper (Tier 1 #3); FGX
  2020 redundancy testing (Cycle 26 ingest planı); modern data
  Chen-Zimmermann 2022 + JKP 2023 (Cycle 27-29).

- **YENİ (Cycle 25)**: Q59 (Knowledge ↔ Organization correlation
  orthogonality); Q60 (Peters-Taylor θ=30% vs Eisfeldt-Papanikolaou
  full SG&A methodology farkı modern kalibrasyon); Q61 (Organization
  capital tech + service firma sektör compositional shift NDX-spesifik).

- **Çelişki YOK**: HXZ 2020 vs Eisfeldt-Papanikolaou (scope-dependent;
  unconditional ex-fin spec çift teyit); Eisfeldt-Papanikolaou vs
  Peters-Taylor SG&A allocation farkı (methodology farkı, çelişki
  değil; Q60 yeni). [[meta/contradictions]] yeni entry açılmadı.

- **F bloğu yapısal kazanım**: 3-katmanlı (Cycle 17) → **4-katmanlı**
  (Cycle 25); methodology infrastructure (Lev-Sougiannis 1996
  Knowledge + Peters-Taylor 2017 Total + Lev-Srivastava 2020
  Application) + **factor portfolio anchor (Eisfeldt-Papanikolaou
  2013 Organization)** ayrımı dokümante. Wiki için NDX strategy
  spec'inde adjusted Bm rebuild (1+3+4) + OC factor signal layer (2)
  + R&D-to-market signal layer (HXZ 2020 4/4 hayatta kalan) **üç
  ayrı intangibles overlay** layer.

## Cycle 26 (Feng-Giglio-Xiu 2020 Factor Zoo Taming) sonrası yüzeye çıkan boşluklar

> 📝 **D bloğu kompleman ingest sonrası.** Cycle 24 yol haritası
> revize'sinde önceliği yükseltildi (28 → 26); Q55 acil cevap;
> v0_draft Profitability seçim doğrulama anchor.

- **KAPANDI**: "Q55 Profitability factor ailesi horse race eksik"
  boşluğu (Cycle 23 işaretli); FGX DS LASSO direct redundancy test
  + Profitability ailesi genel DS-sig validation.

- **KAPANDI**: "FGX 2020 redundancy testing methodology eksik"
  boşluğu (Cycle 19 işaretli; Q7 priori soru fully-answered).

- **KAPANDI / partial**: Q15 + Q24 + Q34 + Q37 (FGX DS LASSO direct
  kanıt + iki ortogonal frequentist concern HLZ + FGX paralel
  methodology layer).

- **HALA EKSİK**: HXZ 2015 q-factor origin paper (Tier 1 #3); Stambaugh-
  Yuan 2017 mispricing factors (Tier 1 #23 — FGX explicit cite
  muhtemelen, ek ingest aday); modern data Chen-Zimmermann 2022 +
  JKP 2023 (Cycle 27-29).

- **YENİ (Cycle 26)**: Q62 (NDX-spesifik DS LASSO kalibrasyon);
  Q63 (post-2017 modern data FGX replikasyonu); Q64 (F bloğu
  intangibles factor'lerin FGX framework'üne entegrasyonu); Q65
  (composite scores FGX framework'üne entegrasyonu).

- **Çelişki YOK**: Cycle 13/19/22 paterni paralel uygulandı —
  HLZ + FGX iki paralel frequentist methodology paper [s.23-24]
  explicit complementary konumlandırma; HXZ replication + FGX
  redundancy iki ayrı epistemik düzlem scope-dependent; RMW Ope
  HXZ q-factor INSIG + FGX DS-sig methodology farkı (epistemic
  question farklı, çelişki değil). [[meta/contradictions]] yeni
  entry açılmadı.

- **D bloğu epistemik omurga statistical bacağı sertleştirme**:
  HLZ 2016 (Cycle 12) + **FGX 2020 (Cycle 26)** iki paralel
  frequentist methodology dokümante; data-snooping bias (HLZ) +
  omitted variable bias (FGX) iki ortogonal statistical concern.
  **Üç paper × üç methodology factor zoo decay ~%85-90** çift+üç
  teyit (HXZ 46/447 + FGX 17/150 + MP %35 aggregate).

- **SDF loading vs risk premium kritik epistemic point** [FGX s.22]:
  Faz 3 backtest spec için yeni reporting layer — factor mean return
  (sample-spesifik risk premium) + SDF loading (pricing contribution)
  iki ayrı metric (HXZ 2017 paterni teyit; about half of factors
  INSIG risk premium FGX sample'da).

- **v0_draft Profitability seçimi DOĞRULANDI** (Cycle 26 ek):
  S&P 500 §1.B GP×V/P CORE + NDX §2.B QMJ continuous + GP/A standalone
  Profitability factor seçim FGX DS-sig validation güçlü; revize
  gerekmez (caveat: RMW Ope iki paralel bulgu methodology farkı
  dokümante).

## Cycle 27 (Jensen-Kelly-Pedersen 2023 Replication Crisis) sonrası yüzeye çıkan boşluklar

> 📝 **D bloğu kompleman ingest sonrası (replication ayağı modern
> güncelleme).** Cycle 24 yol haritası §5'te işaretli (Cycle 27);
> HXZ 2020 empirik replication + JKP 2023 ML-aware modern güncelleme.
> **3. contradictions entry açıldı** ([[meta/contradictions]] §3):
> HXZ ↔ JKP dramatic empirik fark scope-dependent + methodology
> disagreement.

- **KAPANIR / partial**: "JKP 2023 ML-aware modern güncelleme
  placeholder" boşluğu (Cycle 11+13+22 işaretli; ingest tamamlandı).
  **Plan revize**: paper aslında **Bayesian Empirical Bayes
  hierarchical** (ML değil klasik Bayesian methodology); methodology
  family farklı. D bloğu statistical bacağı 3 paper × üç paralel
  methodology aile (frequentist FDR + frequentist ML + Bayesian).

- **KAPANIR / partial**: "Modern data eksik" v0_draft weakness 1.
  madde (Cycle 24 muhafazakâr revize); JKP paper-form modern
  güncelleme **partial kapanma** (2014-2020 6 yıl modern dönem
  kanıt); Chen-Zimmermann data portal (Cycle 29) ile **tam kapanma**.

- **FULLY-ANSWERED**: Q63 (post-2017 FGX modern replikasyon) — JKP
  Bayesian Empirical Bayes paralel methodology FGX DS LASSO ile
  3 yıl modern güncelleme.

- **PARTIAL-STRONGER**: Q33 (post-2014 modern decay) — 6 yıl modern
  dönem kanıt; post-2020 (FAANG/AI 2021-2024) hala out-of-sample.
  Q44 (post-2018 FAANG/AI) — 2 yıl partial validation; post-2020
  hala out-of-sample.

- **3. CONTRADICTIONS ENTRY** ([[meta/contradictions]] §3): HXZ
  2020 ↔ JKP 2023 dramatic empirik fark **~50pp gap**; methodology
  decomposition + Bayesian framework choice + global data extension
  scope-dependent + methodology disagreement (Cycle 13 paterni
  paralel). Cycle 13/19/22/26 paterni: **dramatic empirik bulgu
  varsa contradictions.md entry açılır**; methodology farkı + iki
  epistemik düzlem ise scope-dependent.

- **HALA EKSİK**: HXZ 2015 q-factor origin paper (Tier 1 #3); Chen-
  Zimmermann 2022 data portal (Cycle 29 ön koşul); Stambaugh-Yuan
  2017 mispricing factors (Tier 1 #23); Avramov-Cheng-Metzker 2023
  (Tier 2 #43, ML vs Economic Restrictions).

- **YENİ (Cycle 27)**: Q66 (frequentist + Bayesian methodology
  family); Q67 (Lev-Srivastava ↔ JKP Value theme F bloğu integration);
  Q68 (capped VW vs pure VW vs FF half-weight); Q69 (13 theme NDX
  subsample); Q70 (tangency portfolio multi-theme allocation).

- **D bloğu epistemik omurga sertleştirme**:
  - **Statistical bacağı 3 paper × üç paralel methodology aile**:
    HLZ frequentist FDR + FGX frequentist DS LASSO + JKP Bayesian
    Empirical Bayes hierarchical
  - **Replication ayağı 2 paper × dramatic empirik fark**: HXZ 2020
    (US-only NYSE-VW pure VW 1967-2014; %35 raw / %10 net) + JKP
    2023 (US+Global Bayesian capped VW 1926-2020; %84.9 US / %84.0
    Global)
  - 3. contradictions entry methodology disagreement transparent
    reporting

- **Faz 3 strategy spec implications**:
  - **HXZ + MP conservative-side baseline korunur** (×0.65 / ×0.50
    decay multiplier Cycle 24 muhafazakâr revize ile uyumlu;
    over-promise riski)
  - **JKP %85 anti-conservative upper bound sensitivity reference**
  - **Methodology choice sensitivity test üç alternative**: pure VW
    (HXZ baseline) + FF half-weight (FF1993) + capped VW (JKP NYSE
    80th percentile winsorize) — Faz 3 implementation tercih aday
    capped VW (NDX FAANG profile natural fit)
  - **13 theme cluster + tangency portfolio multi-theme allocation
    framework**: factor selection + theme allocation iki paralel
    decision; v0_draft §1.B + §2.B theme diversification yapısı
    Faz 3 v1 revize aday (Cycle 30 hedef)
  - **Modern data infrastructure**: JKP code repository GitHub
    bkelly-lab/GlobalFactor + WRDS open-source link Faz 3
    implementation direct kullanılabilir; Chen-Zimmermann data
    portal (Cycle 29) complementary

## Cycle 29 (methodology/data_sources.md açma) sonrası yüzeye çıkan boşluklar

> 📝 **Faz 2 yapısal devam ingest sonrası.** methodology/ klasörünün
> 2. sayfası (Cycle 21 backtest_spec.md sonrası); paper ingest YOK,
> veri infrastructure pointer dokümantasyonu. Cycle 28 v0_draft → v1
> revize hazırlık raporu (Çıktı 2) input olarak Cycle 30'da kullanılacak.

- **TAM KAPANMA**: "Modern data eksik" v0_draft weakness 1. madde
  (Cycle 24 muhafazakâr revize → Cycle 27 partial → **Cycle 29 TAM
  KAPANMA**); üç paralel data kaynağı (Chen-Zimmermann + JKP code
  repository + WRDS) Faz 3 backtest implementation altyapısı.

- **KAPANIR**: "Chen-Zimmermann 2022 data portal pointer eksik"
  boşluğu (Cycle 11+13+22+27 placeholder); [[methodology/data_sources]]
  §1 dokümantasyonu.

- **KAPANIR**: Faz 2 sertifika kriteri "Modern replication"
  (Chen-Zimmermann 2022 + JKP 2023) — JKP paper-form ✓ Cycle 27 +
  Chen-Zimmermann data portal pointer ✓ Cycle 29.

- **HALA EKSİK** (Faz 3 seçici ingest):
  - HXZ 2015 q-factor origin paper (Tier 1 #3)
  - Stambaugh-Yuan 2017 mispricing factors (Tier 1 #23)
  - FF 2008 "Dissecting Anomalies" (Tier 1; paywall→preprint)
  - Ball-GLN 2016 Cop methodology origin (Tier 1 #9)
  - LSV 1994 contrarian (Tier 1 #7)
  - Frankel-Lee 1998 V/P origin (Tier 1; paywall)
  - Avramov-Cheng-Metzker 2023 (Tier 2 #43; ML vs Economic Restrictions)

- **YENİ (Cycle 29)**: Q71 (Chen-Zimmermann ↔ JKP convergence/
  divergence pure replication ayrımı) + Q72 (WRDS NDX-spesifik
  data feed configuration).

- **Post-2020 hala out-of-sample**: FAANG/AI 2021-2024 modern
  dönem; Chen-Zimmermann database update + Faz 3 custom modern
  replikasyon ile tam kapanma (data portal aktif olarak güncellenir
  ama specific update timing paperdan teyit edilmedi).

- **Faz 2 sertifika kriterleri ilerlemesi** ([[meta/handoff_faz2]] §3):
  - methodology/backtest_spec.md ✅ Cycle 21
  - Aday strategy draft (v0_draft) ✅ Cycle 24
  - E bloğu Israel-Moskowitz ✅ Cycle 22
  - Tier 2/3 seçici ingest (Novy-Marx + Eisfeldt-Papanikolaou) ✅
  - Modern replication (JKP + Chen-Zimmermann) ✅ Cycle 27 + 29
  - FGX 2020 redundancy testing ✅ Cycle 26
  - v1 revize draft → Cycle 30 BEKLENİYOR
  - 3. contradictions entry resolution ✅ Cycle 27

- **Faz 2 → Faz 3 geçiş hazırlığı**: Cycle 30 v1 draft + Cycle 31
  Faz 2 sertifika TAM/YUMUŞAK karar + handoff_faz3 açma + CLAUDE.md
  §7 Faz 2 schema ratify; Cycle 32+ Faz 3 başlangıç.

## Cycle 32 sonrası — Faz 3 ilk operasyon (sp500_v1.md formal spec)

- **KAPANIR**: Faz 3 yapısal kriter #1 (sp500_v1 formal spec açma);
  [[strategies/sp500_v1]] 7 bölüm tablo + spec doc yapısı
  (~340 satır); v1_draft synthesis "niye" + sp500_v1 "ne yapılacak"
  ayrımı.

- **KAPANIR**: §1.2 sample dönemi explicit tasarım kararı (1980-2020
  baseline + 2021-2024 OOS test iki ayrı dönem; pre-1980 Compustat
  coverage incomplete + JKP sample sonu 2020 + post-2020 wiki
  paperları dışı Faz 3 implementation backtest sonrası).

- **HALA EKSİK** (Faz 3 yol haritası devam):
  - nasdaq100_v1.md formal spec (Cycle 33 hedef)
  - known_weaknesses.md formal sayfa (Cycle 34 hedef; cross-strategy
    formalize)
  - Backtest implementation (Cycle 41-43 hedef; Chen-Zimmermann +
    JKP GitHub bkelly-lab + WRDS data ile pure VW + FF half-weight
    + capped VW üç alternative methodology sensitivity test)
  - Post-2020 OOS custom replikasyon (FAANG/AI 2021-2024;
    sp500_v1 §5.4 protocol)

- **Faz 3 sertifika kriterleri ilerlemesi** ([[CLAUDE.md]] §7 10/10):
  - 1 (sp500_v1 formal spec) ✅ Cycle 32 BU
  - 2 (nasdaq100_v1 formal spec) → Cycle 33 BEKLENİYOR
  - 3 (known_weaknesses.md formal sayfa) → Cycle 34 BEKLENİYOR
  - 4 (backtest_spec finalize sertleştirme) → progressive
  - 5-9 (backtest implementation + Faz 3 seçici ingest 4-6 paper +
    DSR-corrected + walk-forward + bootstrap + 13 theme tangency +
    HLZ+FGX+JKP üç paralel) → Cycle 35+ yol haritası

- **CLAUDE.md §10 KÜÇÜK fix**: operation tipleri listesine
  `strategy_formal_spec` eklendi (mevcut 6 → 7 op tipi).

## Cycle 33 sonrası — Faz 3 ikinci formal spec (nasdaq100_v1.md)

- **KAPANIR**: Faz 3 yapısal kriter #2 (nasdaq100_v1 formal spec
  açma); [[strategies/nasdaq100_v1]] 7 bölüm tablo + spec doc yapısı;
  sp500_v1 (Cycle 32) paterninin paralel uygulaması NDX-spesifik
  tasarım kararlarıyla.

- **KAPANIR**: §1.2 sample dönemi NDX-spesifik netleştirme (2000-2020
  baseline + 2021-2024 OOS test; sp500 1980-2020'den farklı; NDX
  yapısal genişleme 1985+ + FAANG era 2000+ gerekçe).

- **KAPANIR**: F bloğu 4-katmanlı methodology hierarchy NDX CORE
  formal spec entegrasyonu (sp500'de Path C overlay tek satır;
  NDX'te §2.5 yeni alt-bölüm CORE infrastructure; Q60 horse race
  Faz 3 implementation iki alternative sensitivity test dokümante).

- **HALA EKSİK** (Faz 3 yol haritası devam):
  - known_weaknesses.md formal sayfa (Cycle 34 hedef; cross-strategy
    formalize sp500_v1 §6 + nasdaq100_v1 §6 + v1_draft §4 birleşik)
  - Backtest implementation (Cycle 41-43 hedef)
  - Post-2020 OOS custom replikasyon (FAANG/AI 2021-2024)
  - Q60 horse race direct empirik test (Eisfeldt-Papanikolaou full
    SG&A vs Peters-Taylor θ=0.30 sensitivity)
  - Q72 WRDS NDX-spesifik data feed configuration

- **Faz 3 sertifika kriterleri ilerlemesi** ([[CLAUDE.md]] §7 10/10):
  - 1 (sp500_v1 formal spec) ✅ Cycle 32
  - **2 (nasdaq100_v1 formal spec) ✅ Cycle 33 BU**
  - 3 (known_weaknesses.md formal sayfa) → Cycle 34 BEKLENİYOR
  - 4 (backtest_spec finalize sertleştirme) → progressive
  - 5-9 (backtest implementation + Faz 3 seçici ingest 4-6 paper +
    DSR-corrected + walk-forward + bootstrap + 13 theme tangency +
    HLZ+FGX+JKP üç paralel) → Cycle 35+ yol haritası
  - **Faz 3 sertifika 2/10 ✅**

## Cycle 34 sonrası — Faz 3 üçüncü formal spec (known_weaknesses.md cross-strategy registry)

- **KAPANIR**: Faz 3 yapısal kriter #3 (known_weaknesses.md formal
  cross-strategy acknowledgment registry); [[strategies/known_weaknesses]]
  6 bölüm cross-strategy + sp500-spesifik + NDX-spesifik + methodology
  choice sensitivity + acknowledged-but-not-addressed ayrımı formalize.

- **KAPANIR**: v1_draft synthesis fonksiyonu absorb edildi (Cycle 32
  sp500_v1 + Cycle 33 nasdaq100_v1 + Cycle 34 known_weaknesses üç
  formal spec'ler birlikte v1_draft synthesis dokümanının fonksiyonunu
  absorb); v1_draft Cycle 34 historic'e geçti (v0_draft Cycle 30
  paterni paralel; superseded_by üçlü sister spec; content
  değiştirilmedi historic preservation kuralı).

- **KAPANIR**: sp500_v1 §6 + nasdaq100_v1 §6 weakness numbered list'leri
  wiki-level acknowledgment registry'de formalize edildi (cross-
  strategy ortak §1 + strategy-spesifik §2-3 ayrımı net + methodology
  choice sensitivity §4 + acknowledged-but-not-addressed §5).

- **HALA EKSİK** (Faz 3 yol haritası devam):
  - Cycle 35 HXZ 2015 q-factor origin ingest (Tier 1 #3, yüksek priori)
  - Cycle 36 §11.5 ZORUNLU 4-cycle ardışık consolidation pass
    (Cycle 4/8/12/16/20/24/28/32/**36**)
  - Cycle 37+ FF 2008 + Ball-GLN + Stambaugh-Yuan + LSV (Faz 3 seçici
    ingest)
  - Cycle 41-43 Backtest implementation
  - Post-2020 OOS custom replikasyon (FAANG/AI 2021-2024)

- **Faz 3 sertifika kriterleri ilerlemesi** ([[CLAUDE.md]] §7 10/10):
  - 1 (sp500_v1 formal spec) ✅ Cycle 32
  - 2 (nasdaq100_v1 formal spec) ✅ Cycle 33
  - **3 (known_weaknesses.md formal sayfa) ✅ Cycle 34 BU**
  - 4 (backtest_spec finalize sertleştirme) → progressive
  - 5-9 (backtest implementation + Faz 3 seçici ingest 4-6 paper +
    DSR-corrected + walk-forward + bootstrap + 13 theme tangency +
    HLZ+FGX+JKP üç paralel) → Cycle 35+ yol haritası
  - 10 (v1→v2 evrim opsiyonel) → Cycle 41-43 backtest sonrası karar
  - **Faz 3 sertifika 3/10 ✅**

## Cycle 35 sonrası — Faz 3 ilk seçici ingest (HXZ 2015 q-factor formal origin)

- **KAPANIR**: "HXZ 2015 q-factor origin paper eksik" boşluğu
  (Cycle 8 HMXZ + Cycle 13 HXZ Replicating + Cycle 26 FGX + Cycle 27
  JKP'den dolaylı atıflar HXZ 2015 origin paper sayfası açılana kadar
  formal değildi); Cycle 35'te [[papers/hou_xue_zhang_2015_q_factor]]
  formal origin tanımı + [[concepts/q_factor_model]] yeni concept hub
  + [[factors/I_A]] + [[factors/ROE]] yeni factor entity'ler.

- **KAPANIR**: Q15 (FF5 vs HXZ q-factor horse race) fully-answered
  (HXZ 2015 [Section 3 + Section 6 Conclusion] explicit FF/Carhart vs
  q-factor PEAD/IVOL/distress/net issues subsumption test 5/6 anomalies
  q-factor outperforms; Sloan accruals exception q-factor WORSE
  documented).

- **KAPANIR**: Q24 (q5 vs FF5 horse race) partial-stronger (HXZ 2015
  4-factor origin + HMXZ 2020 q5 extension Cycle 8 + FGX 2020 cross-test
  Cycle 26).

- **KAPANIR**: Q34 (HXZ 447 anomaly q-factor cross-subsumption)
  partial-stronger (HXZ 2015 origin + 2020 empirik).

- **HALA EKSİK** (Faz 3 yol haritası devam):
  - **Cycle 36 §11.5 ZORUNLU 4-cycle ardışık consolidation pass**
    (Cycle 4/8/12/16/20/24/28/32/**36**)
  - Cycle 37 FF 2008 "Dissecting Anomalies" ingest (Tier 1 paywall→preprint;
    Q14 CMA/RMW direct test)
  - Cycle 38 Ball-GLN 2016 ingest (Tier 1 #9 Cop methodology origin)
  - Cycle 39 Stambaugh-Yuan 2017 ingest (Tier 1 #23 mispricing factors)
  - Cycle 41-43 Backtest implementation
  - Cycle 44 LSV 1994 ingest (opsiyonel)
  - Post-2020 OOS custom replikasyon (FAANG/AI 2021-2024)

- **YENİ Q'lar (Cycle 35)**: Q73 (q-factor intangibles-aware genişletme
  aday) + Q74 (HXZ 2015 sample post-2011 modern replikasyon) + Q75
  (r_ROE monthly resort zorunluluğu vs wiki annual frequency) + Q15a
  (Sloan accruals q-factor exception scope-dependent vs structural limit).

- **Faz 3 sertifika kriterleri ilerlemesi** ([[CLAUDE.md]] §7 10/10):
  - 1 (sp500_v1 formal spec) ✅ Cycle 32
  - 2 (nasdaq100_v1 formal spec) ✅ Cycle 33
  - 3 (known_weaknesses.md formal sayfa) ✅ Cycle 34
  - 4 (backtest_spec finalize sertleştirme) → progressive (Cycle 35
    HXZ q-factor formal tanımı sertleştirme; Cycle 36 §11.5 + Cycle 37+
    devam)
  - **5 (HXZ 2015 q-factor origin ingest Faz 3 seçici #1) ✅ Cycle 35 BU**
  - 6-9 (backtest implementation + Faz 3 seçici ingest 3-5 paper kalan +
    DSR-corrected + walk-forward + bootstrap + 13 theme tangency +
    HLZ+FGX+JKP üç paralel + q-factor 5. paralel methodology) → Cycle
    36+ yol haritası
  - 10 (v1→v2 evrim opsiyonel) → Cycle 41-43 backtest sonrası karar
  - **Faz 3 sertifika 4/10 ✅** (kriter #5 Faz 3 seçici ingest 1. paper)

## Cycle 37 sonrası — Faz 3 ikinci seçici ingest (FF 2008 size-partition methodology origin)

- **KAPANIR**: Q14 (RMW/CMA large-cap-only direct test eksikliği)
  fully-answered ANCHOR (FF 2008 [Tablo II + IV] direct empirik
  origin; CMA(big) VW spread -0.02% t=-0.10 INSIG + slope big -0.17
  t=-0.86 INSIG; FF15 [s.13] direct kaynak); Cycle 22 Israel-Moskowitz
  HML-spesifik partial-stronger → Cycle 37 FF 2008 RMW + CMA direct
  anchor sertleştirme; **üçlü teyit** FF 2008 + Israel-Moskowitz +
  HXZ 2015 [s.7].

- **KAPANIR**: E bloğu (large-cap reality) Israel-Moskowitz Cycle 22
  yumuşak kapsam → Cycle 37 FF 2008 direct ingest sertleştirme; FF
  ailesi methodology continuity 3-paper × 22+ yıl üçüncü halka FF93
  → FF 2008 → FF15.

- **KAPANIR**: Q4 (CGS-Ion large-cap) partial-stronger (FF 2008 cross-
  evidence asset growth size-conditional + CGS 2008 paralel paper).

- **HALA EKSİK** (Faz 3 yol haritası devam):
  - Cycle 38 Ball-GLN 2016 ingest (Tier 1 #9 Cop methodology origin
    standalone; raw/papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows.pdf
    mevcut)
  - Cycle 39 Stambaugh-Yuan 2017 ingest (Tier 1 #23 mispricing factors)
  - Cycle 40 §11.5 ZORUNLU consolidation pass + backtest implementation
    kickoff (Cycle 4/8/12/16/20/24/28/32/36/**40**)
  - Cycle 41-43 Backtest implementation
  - Cycle 44 LSV 1994 ingest (opsiyonel)
  - Post-2020 OOS custom replikasyon (FAANG/AI 2021-2024)

- **YENİ Q'lar (Cycle 37)**: Q76 (FF 2008 sample post-2005 modern
  replikasyon) + Q77 (large-cap-only direct RMW/CMA factor inşası) +
  Q78 (FF 2008 momentum size-invariance vs HXZ 2015 annual-sorted
  momentum INSIG scope-dependent).

- **Faz 3 sertifika kriterleri ilerlemesi** ([[CLAUDE.md]] §7 10/10):
  - 1 (sp500_v1 formal spec) ✅ Cycle 32
  - 2 (nasdaq100_v1 formal spec) ✅ Cycle 33
  - 3 (known_weaknesses.md formal sayfa) ✅ Cycle 34
  - 4 (backtest_spec finalize sertleştirme) → progressive (Cycle 35
    HXZ q-factor + Cycle 37 FF 2008 size-partition methodology
    sertleştirme; Cycle 38+ devam)
  - 5 (Faz 3 seçici ingest 4-6 paper) → 2/4-6 ✅ Cycle 35 HXZ 2015 +
    **Cycle 37 FF 2008**; Cycle 38+ Ball-GLN + Stambaugh-Yuan + LSV
    devam
  - 6-9 (backtest implementation + DSR-corrected + walk-forward +
    bootstrap + 13 theme tangency + HLZ+FGX+JKP üç paralel + q-factor
    5. paralel methodology) → Cycle 40+ yol haritası
  - 10 (v1→v2 evrim opsiyonel) → Cycle 41-43 backtest sonrası karar
  - **Faz 3 sertifika 5/10 ✅** (kriter #5 Faz 3 seçici ingest 2. paper)

## Cycle 38 sonrası — Faz 3 üçüncü seçici ingest (Ball-GLN 2016 Cop methodology origin)

- **KAPANIR**: "Ball-GLN 2016 Cop standalone paper eksik" boşluğu
  (Cycle 23 + handoff_faz3 §3 priori); Profitability zinciri 4. halka
  Cop methodology origin formal anchor; HMXZ Tablo 5 + HXZ 2020
  Replicating + FGX + JKP placeholder atıflar Ball-GLN origin paper
  sayfası açıldı + [[factors/Cop]] yeni factor entity ile sertleştirildi.

- **KAPANIR**: Q55 (Profitability zinciri horse race) Cycle 26 fully-
  answered + Cycle 38 origin paper anchor sertleştirme (Ball-GLN
  Cop direct empirik origin); Q49 partial-stronger (Profitability
  dimension origin); Q15a partial-stronger (Sloan accruals q-factor
  exception complementary methodology farkı); Q9 partial-stronger.

- **KAPANIR**: Profitability zinciri 4-paper × 7-yıl methodology
  hierarchy formal anchor: GP/A (Cycle 23) → RMW Ope (Cycle 4) → QMJ
  GPOA (Cycle 19 composite) → Cop (Cycle 38 standalone).

- **HALA EKSİK** (Faz 3 yol haritası devam):
  - Cycle 39 Stambaugh-Yuan 2017 ingest (Tier 1 #23 mispricing factors)
  - **Cycle 40 §11.5 ZORUNLU 4-cycle ardışık consolidation pass**
    (Cycle 4/8/12/16/20/24/28/32/36/**40**) + backtest implementation
    kickoff
  - Cycle 41-43 Backtest implementation
  - Cycle 44 LSV 1994 ingest (opsiyonel)
  - Post-2020 OOS custom replikasyon (FAANG/AI 2021-2024)
  - Frankel-Lee 1998 + ACM 2023 paywall

- **YENİ Q'lar (Cycle 38)**: Q79 (Cop methodology NDX-spesifik R&D-
  intensive firma kalibrasyonu; FAANG/biotech R&D giderleştirme Cop
  yapay düşük; F bloğu paralel intangibles-aware Cop modification)
  + Q80 (Ball-GLN sample post-2014 modern replikasyon).

- **Faz 3 sertifika kriterleri ilerlemesi** ([[CLAUDE.md]] §7 10/10):
  - 1 (sp500_v1 formal spec) ✅ Cycle 32
  - 2 (nasdaq100_v1 formal spec) ✅ Cycle 33
  - 3 (known_weaknesses.md formal sayfa) ✅ Cycle 34
  - 4 (backtest_spec finalize sertleştirme) → progressive (Cycle 35
    HXZ q-factor + Cycle 37 FF 2008 + Cycle 38 Ball-GLN Cop
    sertleştirme; Cycle 39+ devam)
  - 5 (Faz 3 seçici ingest 4-6 paper) → 3/4-6 ✅ Cycle 35 HXZ 2015 +
    Cycle 37 FF 2008 + **Cycle 38 Ball-GLN**; Cycle 39+ Stambaugh-Yuan
    + LSV devam
  - 6-9 (backtest implementation + DSR-corrected + walk-forward +
    bootstrap + 13 theme tangency + HLZ+FGX+JKP üç paralel + q-factor
    5. paralel methodology) → Cycle 40+ yol haritası
  - 10 (v1→v2 evrim opsiyonel) → Cycle 41-43 backtest sonrası karar
  - **Faz 3 sertifika 6/10 ✅** (kriter #5 Faz 3 seçici ingest 3. paper)

## Cycle 39 sonrası — Faz 3 dördüncü seçici ingest (Stambaugh-Yuan 2017 mispricing factors)

- **KAPANIR**: "Stambaugh-Yuan 2017 mispricing factors eksik" boşluğu
  (Cycle 26 placeholder + handoff_faz3 §3 priori); Composite mispricing
  scoring 3. halka standalone formal anchor + [[factors/MGMT]] +
  [[factors/PERF]] iki yeni factor entity ile sertleştirildi; FGX 2020
  Cycle 26 explicit cite formal cross-link placeholder→live.

- **KAPANIR**: Composite scoring paradigm 4-paper × 17-yıl literature
  continuity formal anchor: F-Score (Cycle 5) → G-Score (Cycle 6) →
  Stambaugh-Yuan MGMT/PERF (Cycle 39) → JKP 13 theme cluster (Cycle 27).

- **KAPANIR**: Q11 fully-answered ASTERISK üç-paper sertleştirme
  (Cycle 19 Asness QMJ + Cycle 22 Israel-Moskowitz + Cycle 39
  Stambaugh-Yuan modified SMB ~2x premium); SMB resurrection
  methodology mispricing-aware tercih.

- **KAPANIR**: Q9 + Q49 + Q66 partial-stronger Cycle 39; Q55
  sertleştirme Cycle 39 (Stambaugh-Yuan FGX validation paralel).

- **KAPANIR**: Long-only methodology kararı sertleştirme
  (Stambaugh-Yuan short-leg sentiment-driven mispricing kanıt
  CLAUDE.md §1 long-only hedef için kritik).

- **HALA EKSİK** (Faz 3 yol haritası devam):
  - **Cycle 40 §11.5 ZORUNLU 4-cycle ardışık consolidation pass**
    (Cycle 4/8/12/16/20/24/28/32/36/**40**) + backtest implementation
    kickoff
  - **Cycle 40 §11.5 kritik propagation kontrol**: Q56+Q73+Q79+Q82
    NDX intangibles dörtlü konsolidasyonu nasdaq100_v1 §6 +
    known_weaknesses §3 propagation kontrol (kullanıcı request; Q75
    propagation pattern paralel)
  - Cycle 41-43 Backtest implementation
  - Cycle 44 LSV 1994 ingest (opsiyonel)
  - Frankel-Lee 1998 + ACM 2023 paywall hala eksik

- **YENİ Q'lar (Cycle 39)**: Q81 (Stambaugh-Yuan 11 anomaly post-2013
  modern replikasyon) + Q82 (MGMT + PERF NDX-spesifik R&D-intensive
  firma kalibrasyonu).

- **Faz 3 sertifika kriterleri ilerlemesi** ([[CLAUDE.md]] §7 10/10):
  - 1 (sp500_v1 formal spec) ✅ Cycle 32
  - 2 (nasdaq100_v1 formal spec) ✅ Cycle 33
  - 3 (known_weaknesses.md formal sayfa) ✅ Cycle 34
  - 4 (backtest_spec finalize sertleştirme) → progressive (Cycle 35
    HXZ q-factor + Cycle 37 FF 2008 + Cycle 38 Ball-GLN Cop +
    Cycle 39 Stambaugh-Yuan composite mispricing sertleştirme)
  - 5 (Faz 3 seçici ingest 4-6 paper) → **4/4-6 ✅** Cycle 35 HXZ 2015
    + Cycle 37 FF 2008 + Cycle 38 Ball-GLN + **Cycle 39 Stambaugh-Yuan**;
    Cycle 44 LSV opsiyonel devam
  - 6-9 (backtest implementation + DSR-corrected + walk-forward +
    bootstrap + 13 theme tangency + HLZ+FGX+JKP üç paralel + q-factor
    5. paralel methodology) → Cycle 40+ yol haritası
  - 10 (v1→v2 evrim opsiyonel) → Cycle 41-43 backtest sonrası karar
  - **Faz 3 sertifika 7/10 ✅** (kriter #5 Faz 3 seçici ingest 4. paper)

## Cycle 40 sonrası — §11.5 ZORUNLU consolidation pass + backtest implementation kickoff

- **TAMAMLANDI**: Cycle 40 §11.5 4-cycle ardışık consolidation pass
  (Cycle 4/8/12/16/20/24/28/32/36/**40** ardışık nokta; 5/5 PASS;
  3 stale claim KÜÇÜK fix uygulandı + methodology/backtest_implementation_plan.md
  SKELETON açıldı).

- **KAPANIR**: 3 stale claim fix:
  - Q56+Q73+Q79+Q82 NDX intangibles dörtlü konsolidasyonu propagation
    (nasdaq100_v1 §6 madde 14 + known_weaknesses §3.13 yeni alt-bölüm)
  - sp500_v1 §2.1 madde 6 Accruals* Cop subsumes accruals cross-link
    + üç paralel epistemic framework complementary (Sloan filter +
    Cop signal + Stambaugh-Yuan UMO1 composite)
  - sp500_v1 + nasdaq100_v1 §2.B SMB ASTERISK üç-paper sertleştirme
    propagation (Cycle 19 QMJ + Cycle 22 Israel-Moskowitz + Cycle 39
    Stambaugh-Yuan); nasdaq100_v1 ASTERISK asimetrisi kapatıldı.

- **AÇILDI**: methodology/backtest_implementation_plan.md SKELETON
  (Cycle 21 backtest_spec + Cycle 29 data_sources paterni paralel;
  methodology kategorisinde 3. sayfa; 8-bölüm operational roadmap;
  Faz 3 sertifika kriter #6-9 mapping; **§5 alternative weighting
  Stambaugh-Yuan 20/80 4. methodology choice yapısal kazanım** +
  **§7 NDX intangibles dörtlü konsolidasyonu implementation** F bloğu
  4-katmanlı paralel; Cycle 41-43 implementation sırasında bölümler
  dolar SKELETON → operational).

- **HALA EKSİK** (Faz 3 yol haritası devam):
  - Cycle 41 Data pipeline §1 + Code repository §2 başlangıç
    (sertifika kriter #6)
  - Cycle 42 Factor selection §3 üç paralel + 13 theme cluster §4
    (sertifika kriter #7 + #8)
  - Cycle 43 Reporting §6 DSR + walk-forward + bootstrap + alternative
    weighting §5 sensitivity (sertifika kriter #9)
  - Cycle 44 LSV 1994 ingest (opsiyonel; Tier 1 #7) + post-2020 OOS
    protocol
  - Cycle 45+ Backtest sonuç değerlendirmesi + v1 → v2 evrim revize
    karar (sertifika kriter #10 opsiyonel) + Faz 3 sertifika TAM/YUMUŞAK
    karar
  - Frankel-Lee 1998 + ACM 2023 paywall hala eksik

- **Faz 3 sertifika kriterleri ilerlemesi** ([[CLAUDE.md]] §7 10/10):
  - 1-3 ✅ Cycle 32-34 (formal spec'ler)
  - 4 progressive (Cycle 35-39 sertleştirme + Cycle 40 §11.5 + skeleton)
  - 5 ✅ 4/4-6 (Cycle 35-39 dört seçici ingest)
  - 6-9 → Cycle 41-43 implementation hedef
  - 10 opsiyonel → Cycle 45+ backtest sonrası karar
  - **Faz 3 sertifika 7/10 ✅** (Cycle 39 sonu + Cycle 40 §11.5
    consolidation pass tamamladı).

- **Composite mispricing scoring paradigm yapısal kazanım**: 4-paper
  × 17-yıl methodology hierarchy (F-Score binary → G-Score binary
  industry-median → Stambaugh-Yuan continuous composite 2-cluster →
  JKP Bayesian 13 theme cluster); Sloan zinciri (mispricing/accruals)
  + Profitability zinciri + Composite mispricing scoring üç paralel
  methodology aile + q-factor model literature continuity 4-paper
  × 8+ yıl Cycle 35 = wiki Faz 3 sertifika 7/10 evidence base.

- **Profitability zinciri yapısal kazanım**: 4-paper × 7-yıl methodology
  hierarchy GP/A → RMW Ope → QMJ GPOA → Cop; Sloan zinciri (mispricing/
  accruals) paralel + QMJ 4-dimension birleşim noktası; Sloan fixation
  hypothesis çürütme + Cop subsumes accruals + Cop annual rebalance
  compatible (HXZ ROE monthly resort zorunluluğu Q75'in TERSİ).

- **FF ailesi methodology continuity yapısal kazanım**: 3-paper × 22+
  yıl (FF93 1993 → FF 2008 → FF15 2015); size-partition methodology
  evolution origin → factor inşa formal tanım; HXZ 2015/2020 + JKP
  2023 capped VW NYSE-VW + microcap-arınmış convention FF 2008
  origin'inden methodology continuity.

- **q-factor literature continuity yapısal kazanım**: 4-paper × 8+ yıl
  (HXZ 2015 origin Cycle 35 → HMXZ 2020 q5 Cycle 8 → HXZ 2020
  Replicating Cycle 13 → JKP 2023 Bayesian Cycle 27); [[concepts/q_factor_model]]
  yeni concept hub Cycle 35 (3-kriter testi geçti yapısal kazanım;
  Faz 3'te ilk yeni concept Faz 2'de 0 yeni concept disiplini bozuldu
  HXZ q-factor formal origin gap için).

- **Wiki-level evrim izlenebilirlik infrastructure**: v0_draft historic
  (Cycle 30) + v1_draft historic (Cycle 34) + üç formal spec (sp500_v1
  + nasdaq100_v1 + known_weaknesses) Faz 2-3 strategy operasyonları
  dört aşamalı evrim haritası (CLAUDE.md §7 v0/v1/v2 historic
  preservation pattern formalize edildi handoff_faz3 §6.5).

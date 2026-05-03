---
type: factor
name: Accruals
category: earnings_quality
direction: long_low  # uzun düşük accrual, kısa yüksek accrual
data_lag_required: "Annual report'tan accrual; standard reporting lag (3-5 ay) — Sloan formation Haziran sonu sonrası"
rebalance_frequency: annual
universe_tested: ["NYSE+AMEX COMPUSTAT, 1962-1991 (Sloan orijinal)"]
cycle_38_note: "Ball-GLN accruals decomposition methodology cross-link [[factors/Cop]] yeni entity Cycle 38 ✓ ([[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]]); **Cop subsumes Acc** [Ball-GLN Tablo 2 col 6] Cop t=7.4 + Acc t=0.34 INSIG; [Tablo 8] tangency Sharpe 4F+Cop=1.67 > 4F+Ope+Acc=1.54 'Cop alone better than Ope+Acc combined'; Sloan fixation hypothesis çürütme Ball-GLN [s.10] explicit; Sloan zinciri F_ACCRUAL/G3/QMJ ACC mispricing detection Cop alternative interpretation (cash flow under-reaction gradually corrected); wiki taraf tutmaz Cochrane mathematical equivalence; Sloan + Profitability zinciri birleşim noktası Ball-GLN methodology link"
cycle_39_note: "Stambaugh-Yuan 11 anomaly Cluster 1 (MGMT) içinde accruals dahil [[factors/MGMT]] Cycle 39 ✓ ([[papers/stambaugh_yuan_2017_mispricing_factors]]); composite mispricing P1 6-anomaly avg ranking accruals bileşeni; iki paralel methodology aile (Cycle 38 Cop subsumes Acc single signal cash-based + Cycle 39 Stambaugh-Yuan UMO1 includes Acc within composite mispricing); Sloan zinciri (mispricing/accruals 4 paper × 23 yıl) + Profitability zinciri (4 paper × 7 yıl) + Composite mispricing scoring (4 paper × 17 yıl) üç paralel methodology aile"
---

# Accruals (Total Accrual Anomaly)

## Tanım [[sloan1996_accruals_anomaly]] [s.293]

**Total Accruals (balance-sheet-based, Sloan formülü):**

```
Accruals_t = (ΔCA − ΔCash) − (ΔCL − ΔSTD − ΔTaxesPayable) − Depreciation
```

- `ΔCA`: change in current assets (Compustat ACT)
- `ΔCash`: change in cash and equivalents (CHE)
- `ΔCL`: change in current liabilities (LCT)
- `ΔSTD`: change in short-term debt (DLC)
- `ΔTaxesPayable`: change in income taxes payable (TXP)
- `Depreciation`: depreciation + amortization (DP)

Total assets ile scale edilir → `Accruals / AT_(t-1)`.

**Modern alternatif: cash flow statement (CFS)-based [1988 sonrası]:**

```
Accruals_t = NI_t − CFO_t
```

Total assets ile scale edilir. 1988 sonrası Statement of Cash Flows zorunlu
olduğu için bu formül daha temiz. Sloan paperı her iki versiyonu uygular —
büyük ölçüde benzer sonuçlar [[sloan1996_accruals_anomaly]].

## Origin

- **Origin paper:** [[sloan1996_accruals_anomaly]] (Sloan 1996)
- Yazar: Richard G. Sloan (University of Pennsylvania)
- **Mekanizma:** [[accruals_anomaly]] concept sayfasında detay — "investor
  fixation on earnings" + persistence farkı (CFO yüksek, accrual düşük).

## Reported Performance Across Studies

| Paper | Dönem | Evren | Spread (1y) | t-stat (or sig %) | Notlar |
|---|---|---|---|---|---|
| [[sloan1996_accruals_anomaly]] (raw) | 1962-1991 | NYSE+AMEX COMPUSTAT | **+10.4%** (decile 1 − decile 10) | t=4.71 | [Tablo 6, s.305]; n=40,679 firm-year; **headline** |
| [[sloan1996_accruals_anomaly]] (size-adjusted) | aynı | aynı | ~+2.9% | t=1.64 | [Tablo 6]; size-adj versiyon — anomaly size-loaded |
| [[sloan1996_accruals_anomaly]] (year 2 holding) | aynı | aynı | +4.8% | t=2.41 | [Tablo 6]; multi-year decay |
| [[mclean_pontiff_2016_post_publication_decay]] aggregate decay multiplier | (82 anomaly aggregate, 1972-2011) | NYSE+AMEX+NASDAQ all-stocks aggregate | aggregate post-pub decay **%35** (sig 1%); Sloan 1996 paper ref list'inde **explicit listed** [s.28, ref] | (anomaly-equal-weighted aggregate t-stat values [Tablo 2, s.31]) | [Tablo 3, s.32] aggregate decay; Sloan-spesifik decay rakamı paperdan tek-tek çıkmıyor; aggregate uygulanır → decay-adjusted +10.4%×0.65 = **+6.76%** baseline; size-adj +2.9%×0.65 = +1.89% (zaten marjinal); Tablo 8 limited arbitrage büyük/likit firmalarda decay agresif → Sloan'un size-loaded zayıflığıyla uyumlu (large-cap'te yapısal silinmesi beklenir) |

## Faktör Ailesi İçindeki Yeri

- **F-Score F_ACCRUAL:** [[F_Score]]'un binary versiyonu (CFO > NI mi?).
  Sloan'un continuous decile sortunun simplifikasyonu — winner-loser
  identification çatısına uydurulmuş.
- **G-Score G3:** [[G_Score]]'un binary versiyonu (CFO > NI mi?), aynı
  Sloan paterni firm-level threshold ile (industry-median değil).
- **CMA / Investment factor:** [[CMA]] (FF15 investment factor) accrual
  ile yapısal ilişkide — accruals büyük ölçüde investment-related
  (working capital + capital expenditure'ün netleştirilmiş hali). HMXZ
  q-factor model investment factor (I/A) accruals literature'a yakın
  konumda [[hou_mo_xue_zhang_2020_security_analysis]].
- **Subsumed by?** Wiki'de doğrudan test yok ama HMXZ q5 lens'inde
  investment + ROE faktörü accrual signal'i büyük ölçüde absorb edebilir.
  Modern test için Hou-Xue-Zhang 2020 "Replicating Anomalies" (Tier 1 #18)
  ingest edilmeli.

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

- **NASDAQ Sloan paperında YOK:** sample NYSE+AMEX. Modern uygulamada
  NASDAQ-dahil replikasyonlar standart (örn. Green-Hand-Soliman 2011,
  Hou-Xue-Zhang 2020 Replicating Anomalies). Wiki'de henüz yok.
- **Size-adjusted hedge ~2.9% (t=1.64) marjinal**: anomaly raw 10.4%'dan
  büyük ölçüde size effect taşıyor; large-cap evrene transferli kanıt zayıf.
- **NDX intangibles (tech firmalar):** Tech firma R&D giderleştirmesi
  accrual hesaplamasını distorts ediyor olabilir → Q26 wiki açık sorusu.

## Decay / Post-Publication Performance

[[mclean_pontiff_2016_post_publication_decay]] [Tablo 3, s.32] 82 anomaly
aggregate **post-pub decay %35 (sig 1%)**, %10 statistical bias (insig).
Sloan 1996 paper ref list'inde **explicit listed** [s.28, ref] — yani
accruals anomaly aggregate'a dahil — ama paper individual anomaly decay
rakamlarını tek-tek raporlamaz. Aggregate multiplier (×0.65) Sloan'a
uygulanır.

**Spesifik somut empirik kanıt:**
- Green-Hand-Soliman (2011) "death of accruals anomaly" başlığıyla
  decay raporlar — wiki Tier listesinde değil, Cycle 10+ aday. Sloan-
  spesifik post-pub decay'in literatürdeki anchor referansı.
- [[mclean_pontiff_2016_post_publication_decay]] [Tablo 8] limited
  arbitrage: Sloan accruals zaten size-loaded (raw +10.4% → size-adj
  +2.9% marjinal); büyük/likit firmalarda post-pub decay agresif →
  large-cap'te accrual standalone signal yapısal olarak **silinmesi
  beklenir**. Wiki'nin amaç evrenleri (S&P 500 + NDX) için
  accruals **standalone factor olarak yetersiz**; F_ACCRUAL / G3 binary
  versiyonları **komposit içinde complementary** kullanım daha sağlam.

> 📝 Detay [[post_publication_decay]] decay-adjusted spread tablosu —
> Accruals satırı raw 10.4%×0.65 = +6.76%; size-adj 2.9%×0.65 = +1.89%
> (in-sample zaten marjinal).

### Multiple Testing Status (Cycle 12 ek)

[[harvey_liu_zhu_2016_multiple_testing]] çerçevesinde:
- **Sloan accruals raw (t=4.71, 1962-91):** sig her cutoff'ta
  (Bonferroni / Holm / BHY hepsi sig); paperin ref list'inde **explicit
  listed** [s.28]
- **Sloan accruals size-adj (t=1.64, 1962-91):** **insig** tüm
  cutoff'larda (klasik 1.96 dahil)

Üç darbe çerçevesinde Sloan accruals raw 2/3 (size-loaded → large-cap
silinmesi beklenir); size-adj 0/3. Wiki için: F_ACCRUAL / G3 binary
versiyonları komposit içinde complementary; Sloan continuous decile
standalone large-cap evrene transferli değil. Detay
[[concepts/multiple_testing]] aggregate tablosu;
[[concepts/post_publication_decay]] üç darbe çerçevesi tablosu.

> ⭐ **Cycle 13 ek (HXZ 2020 ingested) — DÖRT DARBE 4/4 HAYATTA:**
> [[hou_xue_zhang_2020_replicating_anomalies]] [s.5, s.27] Sloan
> operating accruals (Oa) paperin abstract'ında **explicit listed**
> ("Sloan (1996) operating accruals, smaller in magnitude than -10.4%
> per annum"); **q-factor model lens'inde de hayatta**: klasik -0.27%
> (t=-2.13) + **q-factor alpha -0.54% (t=-3.77) sig** [s.27]. Investment
> factor loading tiny (-0.02 t=-0.23); Roe-factor loading 0.26
> (t=4.13) yanlış yönde. **Sloan operating accruals dört darbenin
> TAMAMINDA hayatta kalan nadir anomaly:** wiki'de 4/4 sig olan
> tek classical fundamental factor. Discretionary accruals (Dac)
> q-factor alpha -0.64% (t=-4.37) sig — paralel kanıt. **Richardson-
> Sloan-Soliman-Tuna 2005 total accruals (Ta) explicit insig** [s.5]
> — modern revisit çürütülüş, Sloan 1996 hayatta. Detay
> [[concepts/anomaly_replication]] aggregate tablosu;
> [[concepts/post_publication_decay]] dört darbe çerçevesi tablosu.

## Implementation Notes

- **Required data:**
  - Balance sheet: ACT, LCT, CHE, DLC, TXP (1988 öncesi); AT (1988 sonrası
    da)
  - Cash flow statement: OANCF (CFO, 1988 sonrası)
  - Income statement: NI (cash-flow-based formül için)
  - DP (depreciation + amortization)
- **Compustat fields (rough):** ACT, CHE, LCT, DLC, TXP, DP, AT, OANCF, NI
- **Sharadar:** tüm bileşenler mevcut; CFS-based formül daha temiz hesaplanır
- **Annual rebalance:** [[sloan1996_accruals_anomaly]] [s.291] sample yıllık,
  fiscal year-end + standart reporting lag.
- **Continuous decile vs binary:** Sloan continuous decile (long bottom-decile,
  short top-decile); F-Score / G-Score binary (CFO > NI? 1/0). Modern
  uygulamada continuous tercih edilir (sharper signal).
- **Total vs decomposed accruals:** Sloan total accruals; Richardson-Sloan-
  Soliman-Tuna 2005 "reliability"-based decomposition; Jones model 1991
  "discretionary" vs "non-discretionary" ayrım. Modern strateji
  decomposition ile daha rafine sinyal alabilir — wiki'de henüz Tier 2 #35
  Richardson vd. ingest edilmedi.

## Bu Faktörün Yumuşak Karnı

- **Size-loaded:** Raw 10.4% → size-adj 2.9% (t=1.64) marjinal. Anomaly
  küçük cap firmalarda yoğunlaşıyor olabilir → S&P 500 / NDX large-cap
  evrene transferin sınırlı kanıtı.
- **Sample dönemi 1962-1991:** Modern post-1991 dönem out-of-sample
  ([[sloan1996_accruals_anomaly]] paper kapsamı dışı). Green-Hand-Soliman 2011
  decay raporlar.
- **Tech firma intangibles:** R&D giderleştirme accrual hesaplamasını
  distorts edebilir — paperda ele alınmamış. Modern NDX evrene transfer
  için kalibrasyon farkı bekleniyor → Q26.
- **NASDAQ kapsam dışı:** Sloan NYSE+AMEX; modern wiki amacı için kritik
  evren (NDX) dışlanmış.
- **Mispricing vs risk premium yorumu:** Sloan "investor fixation" mispricing
  iddiası; HMXZ q5 lens'inde risk premium yorumu mümkün. Mathematical
  equivalence ile felsefi tartışma; pratik strateji tasarımı her iki yorumda
  da aynı portföye götürür.
- **Modern asset pricing ile etkileşim:** FF5 CMA factor + HMXZ q5 I/A factor
  accrual signal'i büyük ölçüde absorb edebilir. Modern strateji tasarımında
  CMA exposure yerine accrual factor doğrudan kullanmak benzer getiri
  sağlayabilir; redundant olabilir.

## İlgili

- [[sloan1996_accruals_anomaly]] — origin paper
- [[accruals_anomaly]] — concept sayfası (Sloan'ın spesifik mekanizması)
- [[earnings_quality]] — accrual quality earnings_quality'nin alt-boyutu
- [[F_Score]] — F_ACCRUAL binary versiyonu
- [[G_Score]] — G3 binary versiyonu
- [[CMA]] — FF15 investment factor; accruals ile yapısal ilişki
- [[fundamental_scoring]] — accruals composite skorlamada kritik bileşen
- [[mclean_pontiff_2016_post_publication_decay]] — 82 anomaly setinde
  Sloan 1996 explicit listed; aggregate %35 decay multiplier accruals'a
  uygulanır
- [[novy_marx_2013_gross_profitability]] — **Cycle 23**; **paralel
  quality zinciri** (Sloan zinciri mispricing/accruals vs Profitability
  zinciri productive efficiency); Novy-Marx GP/A predictive power
  persists controlling for accruals (Appendix A.3) → iki bağımsız
  mekanizma; QMJ Profitability 4-dimension'da iki zincir birleşiyor
  (ACC + GPOA components yan yana)
- [[Gross_Profitability]] — paralel quality zincirinin Profitability
  zinciri origin factor entity'si
- [[feng_giglio_xiu_2020_factor_zoo]] — **Cycle 26 yeni**; FGX 150
  factor library içinde Cop (HMXZ Tablo 5 cash-based op profits-to-
  assets) **explicit listed teyit edilemedi** (Tablo 4 ham liste
  paperdan kontrol edilmedi); HXZ q-factor lens'inde Cop 4/4 hayatta
  kalan (HXZ 2020 [Tablo 6 IA Internet Appendix] alpha 0.69%/ay
  sig); FGX DS LASSO direct test edilmedi ama Profitability ailesi
  genel sig (RMW + ROE + QMJ DS-sig). Sloan accruals factor zoo decay
  ~%85-90 conservative-side **dört paper × dört methodology**
  çift+üç+dört teyit (HXZ replication + FGX DS LASSO redundancy +
  MP behavioral decay + JKP Bayesian Empirical Bayes hierarchical);
  JKP anti-conservative-side dramatik methodology disagreement
  ([[meta/contradictions]] §3 HXZ ↔ JKP ~50pp gap scope-dependent).
- (sonra) Richardson-Sloan-Soliman-Tuna 2005 — accrual reliability
  decomposition (Tier 2 #35)
- (sonra) Hirshleifer-Hou-Teoh-Zhang 2004 — Net Operating Assets (Tier 2 #36)
- (sonra) Green-Hand-Soliman 2011 — accruals anomaly decay (Tier listesi dışı)
- [[M_Score]] — **Cycle 18 ingest tamam**; M-Score TATA bileşeni
  Sloan total accruals ile methodology paralel (working capital change
  - depreciation aynı yapı); epistemik düzlem farklı (mispricing
  detection vs fraud detection); literatür hattı farklı (Healy
  1985 + Jones 1991, Sloan değil); complementary use (Sloan sort +
  M-Score filter screen-and-rank)
- [[beneish_1999_m_score]] — M-Score origin paper (TATA bileşeni)
- [[QMJ]] — **Cycle 19 ingest tamam**; QMJ Profitability dimension
  **ACC component** (low accruals = high quality); Asness 2019
  **Sloan 1996 explicit cite [s.7]** → Sloan zinciri 4. halka
  (F_ACCRUAL/G3 paterni paralel; M-Score TATA'dan farklı); methodology
  paralel + literatür hattı kökü Sloan
- [[asness_frazzini_pedersen_2019_qmj]] — QMJ origin paper; Profitability
  dimension ACC component literatür hattı Sloan

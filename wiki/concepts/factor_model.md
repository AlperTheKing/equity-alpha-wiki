---
type: concept
name: factor_model
related_papers: [[famafrench1993_three_factor]], [[famafrench2015_five_factor]], [[carhart1997_four_factor]], [[cochrane2011_discount_rates]], [[hou_xue_zhang_2015_q_factor]]
---

> 📝 **Cycle 35 ek**: q-factor model formal origin tanımı [[concepts/q_factor_model]] yeni concept (ayrı epistemic düzlem; investment-based asset pricing theoretical foundation Cochrane 1991 q-theory + investment first-order condition); FF3/Carhart/FF5 vocabulary'sinden ortogonal mekanizma. Hierarchical positioning: factor_model (FF3 + Carhart + FF5 + HXZ-q5) parent + q_factor_model (HXZ 2015 origin → HMXZ 2020 q5 → HXZ 2020 Replicating → JKP 2023 Bayesian) specialized child concept; cross-link bilateral.

> 📝 **Cycle 39 ek**: Stambaugh-Yuan mispricing factor model methodology [[papers/stambaugh_yuan_2017_mispricing_factors]] Cycle 39 ✓; **dördüncü paralel factor model framework**: FF3/FF5 risk-factor-based + Carhart 4F momentum + HXZ q-factor investment-based + **Stambaugh-Yuan 4F mispricing-based** üç paralel methodology aile + Stambaugh-Yuan paterni 4. framework; paper [Section 3] explicit Stambaugh-Yuan 4F outperforms HXZ4 + FF5 (11 anomaly + 73 anomaly larger set); wiki taraf tutmaz Cochrane mathematical equivalence (mispricing vs risk premium iki polar yorum + investment-based intermediate).


# Factor Model — Multi-Factor Asset Pricing

## Tanım

Bir **factor model**, varlık fazla getirilerini (excess returns) ortak risk
kaynaklarına ("faktörler") doğrusal olarak çözer:

`R_i(t) - RF(t) = α_i + Σ_k β_ik · F_k(t) + ε_i(t)`

- `R_i(t) - RF(t)`: varlık i'nin t zamanındaki risk-free üzeri getirisi
- `F_k(t)`: k. faktörün t zamanındaki getirisi (genelde mimicking portföy ile)
- `β_ik`: varlık i'nin k. faktöre yüklemesi (factor loading)
- `α_i`: model tarafından açıklanmayan ortalama getiri (asset-pricing testinde
  sıfırdan ayırt edilemez olması beklenir)
- `ε_i(t)`: idiosyncratic kalıntı

**CAPM** (Sharpe-Lintner-Black) tek-faktörlü hali: `F_1 = MKT-RF`. Çok-faktörlü
versiyonlar:
- **FF3** (3-faktör): MKT-RF, SMB, HML — [[famafrench1993_three_factor]]
- **Carhart 4F** (4-faktör): MKT-RF, SMB, HML, UMD — [[carhart1997_four_factor]];
  FF3'e momentum eklenmesi
- **FF5** (5-faktör): MKT-RF, SMB, HML, RMW, CMA — [[famafrench2015_five_factor]]
- **HXZ4** (q-factor, 4-faktör): MKT-RF, ME, ROE, IA — Hou-Xue-Zhang 2015 (henüz
  ingest edilmedi); investment CAPM ortodoks formülasyonu
- **q5** (5-faktör): MKT, ME, IA, ROE, **expected growth** — q4 + Eg = q5;
  origin Hou-Mo-Xue-Zhang (2020 başka paper, henüz ingest edilmedi);
  [[hou_mo_xue_zhang_2020_security_analysis]] q5 lens'iyle security analysis
  stratejilerini test eder
- ML faktör modelleri: Gu-Kelly-Xiu 2020 (henüz ingest edilmedi)

> 📝 **FF5 ve Carhart 4F paralel modellerdir, kesişmezler:** İkisi de FF3 üzerine
> ek koyar ama farklı ek (momentum vs. profitability+investment). Hangi modelin
> "doğru" baseline olduğu wiki'de açık soru ([[meta/open_questions]] Q16).

## Discount-rate framing [[cochrane2011_discount_rates]]

[[cochrane2011_discount_rates]] [s.20] factor model'in epistemik rolünü
"**nice division of labor**" olarak tanımlar:

> Empirical asset pricing in the Fama-French (1996) tradition boils down the
> alarming set of anomalies to a small set of large-scale systematic risks that
> generate rewards. "Macro" "behavioral" or other "deep" theories can then focus
> on **why** the factors are priced.

Yani bir factor model:
- **Reduce eder:** N karakteristik (B/M, momentum, accruals, …) → K << N faktör
- **"Why" sorusunu açık bırakır:** Factor primum'ları rational risk premium mu,
  davranışsal mispricing mi, friction mı? Cochrane bu soruyu "deep theories" alanına
  bırakır [s.20].

[[cochrane2011_discount_rates]] [s.12]'in cross-section yorumu — "**absence of beta
is really the heart of the value puzzle**" — factor model'in *neden gerekli*
olduğunu özetler: CAPM betalar tüm B/M portföylerinde benzer ama ortalama getiriler
çok farklı; tek-faktörlü beta cross-section discount rate spread'ini açıklamaz,
çok-faktörlü model ise (HML eklenerek) açıklar.

## Neden önemli (bu wiki'nin amacı için)

1. **Strateji benchmark'ı:** S&P 500 / Nasdaq 100'de seçilen hisselerin getirisinin
   ne kadarı bilinen faktörlerle açıklanır, ne kadarı *gerçek alfa*? Bu sorunun
   cevabı bir factor model üzerinden yapılan time-series regresyonla verilir.

2. **Faktör-bazlı portföy inşası:** Eğer bir factor (örn. HML, profitability)
   pozitif premium taşıyorsa, ona pozitif yükleme veren bir portföy seçimi
   sistematik beklenen-getiri kaynağı sunar. Bu, fundamental faktörlerle stock
   selection yapmanın teorik dayanağıdır.

3. **Asset-pricing redundancy:** Bir yeni "anomaly" önerildiğinde, bilinen factor
   model'le açıklanıp açıklanmadığı ilk testtir. Eğer 3-faktör modeli zaten o
   anomaliyi yakalıyorsa, anomaly **redundant**'tır. Bu çerçevenin **dramatik bir
   örneği:** [[famafrench2015_five_factor]] HML'in 5-faktör baz altında redundant
   olduğunu (a≈0, t<0.5) gösterir [[famafrench2015_five_factor]] s.19. "Eski" bir
   faktörün "yeni" faktörlerle span edilmesi → faktör hiyerarşisinin değişmesi.

## Mimicking portföy konsepti

Bir faktör direkt gözlenmediğinde (örn. "value risk"), bir mimicking portföy ile
inşa edilir: değer karakteristiğine göre sıralanmış uzun-kısa portföy.
[[famafrench1993_three_factor]] HML ve SMB için 6-portföy 2×3 yapısını kullanır
(NYSE breakpoint'leri size için median, BE/ME için 30/70 percentile)
[[famafrench1993_three_factor]] PDF p.9.

## Time-series vs. cross-section regresyonu

İki farklı testti, FF93 ikisini de uygular:

- **Time-series regression** ([[famafrench1993_three_factor]] §3-§4): her portföyün
  kendi getirisi faktörlere regress edilir. R² ve intercept'ler raporlanır. Üç-faktör
  modelinin 25 size×BE/ME portföyü için R²'leri 0.83-0.97 [Tablo 4, PDF p.20].
- **Cross-section regression** ([[famafrench1993_three_factor]] §5, PDF p.31): her
  ay portföylerin getirileri factor loading'lerine regress edilir; loading'lerin
  sloplerinin ortalaması (Fama-MacBeth tarzı) factor risk premia'larını verir.

## Replication-aware q-factor performance (Cycle 13 ek)

[[hou_xue_zhang_2020_replicating_anomalies]] [Tablo 4, s.25-29] HXZ
2020 q-factor model'in 161 sig anomaly üzerinde performansı:
- **161 sig anomaly içinde 115 alpha insig at 5%** (150 with t > 3)
- **46 q-factor alpha sig** (11 with t > 3) — net %10 survival
- 6 kategoride composite: momentum 0.86%, intangibles 0.85% en güçlü;
  trading frictions 0.16% sadece; combined 1.4% (t=7.48)

**FF15 + Carhart faktörleri q-factor lens'inde [s.24]:**
- **RMW (Ope) klasik 0.27% (t=2.58) + q-factor alpha 0.04% (t=0.42) insig**
  ⚠️ — wiki'de RMW exposure target değil
- **CMA klasik 0.34% (t=3.63) + q-factor alpha 0.01% (t=0.32) insig**
  — q-factor I/A factor CMA'yı span ediyor
- **UMD klasik 0.67% (t=3.66) + q-factor alpha 0.11% (t=0.43) insig**
  — q-factor Roe factor UMD'yi span ediyor
- Investment factor (I/A) klasik 0.45% (t=5.6) sig
- ROE factor klasik 0.5%+ (t > 3) sig

**q-factor model wiki için methodology validator:** Risk-adjusted
regression baseline; FF5 + Carhart faktörlerini büyük ölçüde absorb
ediyor. Wiki Faz 3 için q-factor exposure (I/A + Roe + ME + MKT)
default risk-adjustment baseline; SMB exposure target değil; RMW
explicit insig.

## Multiple-testing-corrected hurdle (Cycle 12 ek)

[[harvey_liu_zhu_2016_multiple_testing]] [Şekil 3, s.22] factor model
hiyerarşisindeki her faktör için **multiple-testing-corrected sig
hurdle**'ını netleştirir:

| Factor model bileşeni | Reported \|t\| (sample) | BHY 1% (3.0) | Bonferroni (3.78) |
|---|---|---|---|
| **MKT-RF** (FF93/CAPM) | varies (~3.0 typical) | borderline | borderline |
| **SMB** (FF93) | 1.73 | **insig** | **insig** |
| **HML** (FF93) | 2.91 | borderline | **insig** |
| **HML** (FF15 1963-2013) | 3.20 | sig | borderline |
| **RMW** (FF15 2x3) | 2.92 | borderline | **insig** |
| **RMW** (FF15 joint 2x2x2x2) | 4.09 | sig | sig |
| **CMA** (FF15 2x3) | 4.07 | sig | sig |
| **UMD** (Carhart 4F) | 4.46 | sig | sig |

> 📝 **Wiki için kritik:** SMB hiçbir multiple-testing düzeltmesinde
> sig değil; HML FF93'te Bonferroni reddi ama FF15'te BHY sig. CMA ve
> UMD/MOM her cutoff'ta sig — wiki'nin q5 + momentum ekseninde en
> sağlam yapı taşları. **Detay:** [[concepts/multiple_testing]]
> aggregate tablosu.

**Hiyerarşide multiple-testing-corrected konum:**
- **q5 model (HMXZ):** MKT + ME + I/A + ROE + Eg — tümü çift-haneli
  literatür referansı, multiple-testing-aware test [[hou_mo_xue_zhang_2020_security_analysis]]
- **Carhart 4F:** MKT + SMB + HML + UMD — UMD sig, SMB/HML statistical
  zayıf; "MOM eklenmesi" model parsimony argümanı + multiple-testing
  düzeyinde **doğru karar** (UMD sig her cutoff)
- **FF5:** MKT + SMB + HML + RMW + CMA — SMB never sig; HML/RMW
  borderline; CMA sig → **modelin yarısı multiple-testing-corrected
  zayıf**, ama joint kontrol ve incremental information argümanları
  modeli ayakta tutuyor

## Bu wiki'nin strateji tasarımına spesifik implikasyonu

- **Tasarım kararları için:** Aday strateji tasarımları (`wiki/strategies/`)
  faktör seçiminde "literatürde explicit incremental information taşıdığı kanıtlanmış"
  faktörlere ağırlık verir. FF93 üç-faktör modeli **baseline benchmark** rolündedir;
  herhangi bir aday strateji bu baseline'a karşı pozitif alfa üretmek zorundadır.
- **Backtest test setup'ı için:** Strateji portföyünün getirileri FF93 üç-faktör
  modeline regress edilir; intercept (`α`) raporlanır. Eğer `α` istatistiksel olarak
  sıfırdan farklı değilse strateji tasarımının "sadece factor exposure" olduğu
  yorumu yapılır.
- **Universe-spesifik dikkat:** FF93 NYSE/AMEX/NASDAQ ex-financials evreninde inşa
  edildi. S&P 500 / Nasdaq 100 evreninde **HML ve SMB construction NYSE breakpoint'i
  yerine evren-özel breakpoint'lere göre yeniden tanımlanmalı**. Aksi halde SMB
  evren-dışı microcap'leri yansıtır → S&P 500 strateji için irrelevant. Bu nokta
  → [[meta/open_questions]] yeni Q12.

## İlgili paperlar

- [[famafrench1993_three_factor]] — üç-faktör modelin tanımı ve test çerçevesi
- [[carhart1997_four_factor]] — 4-faktör extension (UMD/momentum)
- [[famafrench2015_five_factor]] — 5-faktör extension (RMW + CMA); HML redundancy
- [[cochrane2011_discount_rates]] — factor model'in epistemik rolü, "division of
  labor" framing'i
- [[hou_mo_xue_zhang_2020_security_analysis]] — q5 model security analysis
  stratejilerinde uygulama; FF5'in alternatifi olarak HML'siz q-factor
  yapısı
- [[harvey_liu_zhu_2016_multiple_testing]] — factor model bileşenlerinin
  multiple-testing-corrected sig hurdle'ları; SMB never sig + HML
  FF93/FF15 farkı + CMA/UMD sig her cutoff
- [[hou_xue_zhang_2020_replicating_anomalies]] — q-factor model 447
  anomaly üzerinde performansı; FF15 RMW (Ope) explicit insig; CMA + UMD
  q-factor span; q-factor model methodology validator

_(sonraki ingest'lerle: Hou-Xue-Zhang 2015 — q-factor model; Gu-Kelly-Xiu 2020 —
ML asset pricing)_

## İlgili kavramlar

- [[discount_rates]] — factor model'in temel anlamı ([[cochrane2011_discount_rates]])
- [[factor_zoo]] — 300+ akademik factor problemi
- [[expected_returns_vs_cash_flows]] — present-value identity ile bağlantı
- [[multiple_testing]] — factor model bileşenlerinin multiple-testing-
  corrected sig hurdle'ları; SMB never sig under MT
- [[anomaly_replication]] — factor model bileşenlerinin HXZ NYSE-VW
  replication durumu; RMW (Ope) insig, CMA + UMD q-factor span
- [[post_publication_decay]] — factor model exposure'larının decay-adjusted
  baseline'ı + dört darbe çerçevesi sentezi
- [[backtest_overfitting]] — factor model Sharpe ratio'larının DSR-corrected
  raporlanması Faz 3 spec'inde; HLZ ↔ DSR complementary methodology

_(henüz sayfası olmayanlar: redundant_factors — Feng-Giglio-Xiu 2020 ile;
GRS_test — Gibbons-Ross-Shanken 1989 ile)_

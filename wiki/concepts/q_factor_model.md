---
type: concept
name: q_factor_model
opened: 2026-05-02
phase: faz_3_cycle_35
purpose: "q-factor model literature continuity hub; investment-based asset pricing theoretical foundation + empirical implementation"
---

# concepts/q_factor_model — q-Factor Model

> 📝 **Cycle 35 yeni concept (Faz 3'te ilk yeni concept).** 3-kriter
> testi geçti: (1) yapısal yük yeterli — 4 paper × 8+ yıl literature
> continuity (HXZ 2015 → HMXZ 2020 → HXZ 2020 → JKP 2023); (2) ayrı
> epistemic düzlem — investment-based asset pricing theoretical
> foundation + investment first-order condition; (3) mevcut
> [[concepts/factor_model]] hub'a sığmıyor — FF3/Carhart/FF5
> vocabulary'sinden ayrı epistemic düzlem (q-theory mispricing/risk
> premium çatallanması). Faz 2'de 0 yeni concept açma disiplini Faz 3
> q-factor formal origin gap için bozuldu (yapısal kazanım gerekçeli).

## Tanım

**q-factor model** ([[papers/hou_xue_zhang_2015_q_factor]] origin):

```
E[r_i] - r_f = β^MKT_i × E[MKT] + β^ME_i × E[r_ME]
             + β^I/A_i × E[r_I/A] + β^ROE_i × E[r_ROE]
```

4 faktör:
1. **MKT** — market excess return (CAPM paterni)
2. **r_ME** — size factor (small minus big; SMB ile virtually identical corr 0.95)
3. **r_I/A** — investment factor (low minus high investment-to-assets) ⭐
4. **r_ROE** — return on equity factor (high minus low ROE) ⭐

## Theoretical Foundation

**Investment-based asset pricing**: q-theory of investment ([[concepts/discount_rates]] Cochrane 1991 origin); investment first-order condition:

```
r_i = (Π_i1 + 1 - δ) / (1 + a × I_i0/A_i0)
```

- **Numerator**: marginal benefit of investment (ROE Π_i1 + liquidation value 1-δ)
- **Denominator**: marginal cost of investment (1 + adjustment cost a×I/A)
- **Cochrane 1991 first uses q-theory to study asset prices**; Berk-Green-Naik 1999 + Liu-Whited-Zhang 2009 + Zhang 2005 theoretical lineage

**Iki tahminci** [HXZ 2015 Section 5.1]:
- **Investment mechanism**: Given expected ROE, expected return decreases with investment-to-assets (low discount rates → high marginal q → high investment; high discount rates → low marginal q → low investment); B/M, net stock issues, accruals, market leverage, long-term prior returns hepsi investment-channel
- **ROE mechanism**: Given investment-to-assets, expected return increases with expected ROE (high ROE relative to low investment → high discount rates necessary); momentum, PEAD, financial distress hepsi ROE-channel

## q-Factor Model Literature Continuity (4 Paper × 8+ Yıl)

| Cycle | Paper | Rolü |
|-------|-------|------|
| 35 (yeni) | [[papers/hou_xue_zhang_2015_q_factor]] | **q-factor formal origin** (4-factor model 1972-2011 sample); ~15 anomaly subsumption testing + investment-based theoretical foundation |
| 8 | [[papers/hou_mo_xue_zhang_2020_security_analysis]] | **q5 model extension** (eg+ expected growth factor; F-Score/V/P/Magic Formula/QMJ test; HMXZ Security Analysis uygulaması) |
| 13 | [[papers/hou_xue_zhang_2020_replicating_anomalies]] | **447 anomaly empirical replication** (NYSE-VW; q-factor lens 161 sig → 46 net sig %10) |
| 27 | [[papers/jensen_kelly_pedersen_2023_replication_crisis]] | **Bayesian Empirical Bayes hierarchical framework** cross-test (capped VW + 1-month + global; ~50pp gap MP↔HXZ ↔ JKP scope-dependent methodology disagreement [[meta/contradictions]] §3) |

## Factor Construction Methodology

[HXZ 2015 Section 2]:
- **Sample**: January 1972 - December 2011 monthly CRSP+Compustat; ex-financials + ex-negative book equity
- **Sort**: 2×3×3 triple sort (size × A/A × ROE); NYSE breakpoints VW
- **Size sort**: NYSE median market equity June (annual)
- **A/A sort**: NYSE 30/40/30 breakpoints June (annual; ΔAT/AT-lagged)
- **ROE sort**: NYSE 30/40/30 breakpoints **monthly** (quarterly IBQ / lagged BE; portfolio formed at beginning of month after RDQ public announcement)
- **18 portfolio intersection** → 3 faktör formula:
  - r_ME = small minus big (across 9 small + 9 big portfolios)
  - r_I/A = low minus high (across 6 low-A/A + 6 high-A/A portfolios)
  - r_ROE = high minus low (across 6 high-ROE + 6 low-ROE portfolios)

> ⚠️ **Annual sort caveat** [HXZ 2015 s.7 fn 5 + Apx E]: r_ROE **monthly resort zorunlu** çünkü annually-sorted versiyonlarda momentum + PEAD + IVOL + distress anomalies **TÜMÜYLE INSIG** (h-l mean returns + CAPM alphas insignificantly different from zero). Wiki annual frequency hedef için kritik caveat — Q35+Q51+Q57+Q75 paralel.

## Üç Yorum (Wiki Taraf Tutmaz)

[HXZ 2015 Section 5.1 + 5.2]: Paper üç paralel yorum sunar:

1. **Investment-based asset pricing** (paper preferred): Cochrane 1991 q-theory + Berk-Green-Naik 1999; investment first-order condition
2. **Common risk factors** (Fama-French style): characteristics-based factors common variation source; ICAPM/APT proxy
3. **Mispricing**: Daniel-Titman 1997 paterni; investor over/underreaction; "anomalies are anomalies because not explained by standard risk models"

**Wiki konumu**: **taraf tutmaz** (Cochrane mathematical equivalence Lin-Zhang 2012 "two sides of same coin"; investment first-order condition + consumption first-order condition birlikte hold; characteristics-based + covariances-based eşdeğer empirical mathematical structure). [[concepts/discount_rates]] paterni paralel.

## Headline Performans (HXZ 2015 vs FF/Carhart)

| Anomaly h-l decile | FF α (%/month) | Carhart α | **q-factor α** |
|---------------------|------------------|-----------|----------------|
| PEAD/SUE | 0.54 (t=4.26) | 0.32 (t=2.43) | **0.14 (t=0.92)** ✅ |
| IVOL | -0.91 (t=-4.48) | -0.58 (t=-2.59) | **-0.04 (t=-0.19)** ✅ |
| Distress | -1.43 (t=-5.21) | -0.55 (t=-2.51) | **0.02 (t=0.07)** ✅ |
| Net stock issues | -0.62 (sig) | -0.57 (sig) | **-0.32 (t=-2.10)** ⚠️ partial |
| Sloan accruals | -0.29 (t=-1.96) | -0.29 (t=-1.69) | **-0.39 (t=-2.48)** ❌ EXCEPTION |

**Sloan accruals exception** [HXZ 2015 Section 3.1 + Conclusion]: q-factor model accruals'da daha kötü; "investment factor loading goes right direction ama ROE factor loading wrong direction. Intuitively, high accrual firms invest more but are also more profitable" → ROE channel accrual mispricing'ı maskiyor. **Sloan zinciri F_ACCRUAL/G3/QMJ ACC mispricing detection paradigması q-factor lens'inde yetersiz**; F bloğu intangibles + Profitability zinciri Cop ortogonal complement.

## q-Factor vs Fama-French Spanning [Tablo 1 Panel A-B]

| Factor | FF3 spanning | Korelasyon (Panel B) |
|--------|---------------|------------------------|
| r_ME | SMB loading 0.99 | corr 0.95 with SMB → virtually identical |
| r_I/A | HML loading 0.40 + alpha 0.51% (sig) | corr 0.69 with HML → HML-like role partial |
| r_ROE | FF3 R²=19% (önemli yeni varyasyon) | corr 0.50 with WML/UMD; corr -0.30 with rME size; corr 0.05 with r_I/A (orthogonal) |

## Cochrane (2011) Anomaly Digestion Cevap

[[papers/cochrane2011_discount_rates]] Cochrane 2011 AFA Presidential Address #1-#3 sorularına HXZ 2015 [Section 6 Conclusion] explicit cevap:

> "We are going to have to repeat Fama and French's anomaly digestion, but with many more dimensions."

- **#1 Which characteristics provide independent information; which subsumed?**: Investment + ROE bağımsız bilgi sağlar; investment B/M + net stock issues + accruals + market leverage + long-term prior returns + earnings-to-price + composite issuance subsume eder; ROE short-term prior returns + earnings surprise + financial distress subsume eder; investment + ROE birlikte IVOL açıklar
- **#2 Does each anomaly correspond to new factor?**: ~15 anomaly factor regressions extensive; testing portfolio NYSE-VW vs all-stocks EW farkı kritik
- **#3 How many factors really matter? K<N?**: ~15 anomaly K=4 faktör (MKT + ME + I/A + ROE) subsumption; q-factor model summary

[[concepts/factor_zoo]] cross-link Cochrane #1-#3 anchor.

## Wiki Strategy Spec Implications

### sp500_v1 ([[strategies/sp500_v1]])
- §3.2 statistical filter (3-leg HLZ + FGX + JKP); q-factor lens factor inclusion direct test (5. paralel methodology)
- §3.3 replication-robust filter (HXZ NYSE-VW + JKP capped VW); HXZ 2015 origin formal tanımı sertleştirme
- Path D UMD overlay: r_ROE corr 0.50 with WML; momentum-relevant role acknowledged

### nasdaq100_v1 ([[strategies/nasdaq100_v1]])
- §2.5 F bloğu 4-katmanlı methodology q-factor span kontrolü ek katman (intangibles-aware Bm rebuild q-factor traditional accounting'tan farklı)
- §3.2-3.3 sp500 paterni paralel
- Q73 yeni: q-factor intangibles-aware genişletme aday (NDX FAANG profile + F bloğu paralel)

## İlgili
- [[papers/hou_xue_zhang_2015_q_factor]] — q-factor model formal origin (BU CYCLE 35)
- [[papers/hou_mo_xue_zhang_2020_security_analysis]] — q5 extension
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] — 447 anomaly empirical replication
- [[papers/jensen_kelly_pedersen_2023_replication_crisis]] — Bayesian framework cross-test
- [[concepts/factor_model]] — FF3/Carhart/FF5/HXZ-q5 hiyerarşisi parent concept
- [[concepts/discount_rates]] — Cochrane 1991 q-theory + investment first-order condition
- [[concepts/factor_zoo]] — Cochrane #1-#3 anchor
- [[concepts/anomaly_replication]] — replication crisis literatür hattı
- [[factors/I_A]] — investment factor entity
- [[factors/ROE]] — return on equity factor entity
- [[factors/SMB]] — r_ME virtually identical
- [[factors/CMA]] — investment factor methodology farkı
- [[factors/RMW]] — profitability factor methodology farkı
- [[factors/UMD]] — momentum factor (r_ROE corr 0.50)

# Contradictions

> Kaynaklar arasındaki çelişkiler. Aynı faktör/iddia için farklı kanıt sunan
> paper'ları yan yana koyar. Strateji tasarımı bu çelişkileri **explicit** olarak
> ele almak zorunda — bunlar `wiki/strategies/`'deki tasarımda görünmeli.

## Şablon

```
## [Topic] — bir cümlelik çelişki tanımı

**İddia A:** [[paper_X]] — özet
**İddia B:** [[paper_Y]] — özet (A ile çelişiyor)

**Çelişkinin doğası:** (örneklem dönemi mi, evren mi, metodoloji mi)
**Resolution durumu:** (resolved | open | scope-dependent)
**Strateji implikasyonu:** ...
```

---

## HML faktörünün incremental information durumu — FF93 ↔ FF15 evrimi

**İddia A:** [[famafrench1993_three_factor]] — HML, MKT-RF + SMB + TERM + DEF üzerine
spanning regresyonunda büyük ve istatistiksel olarak anlamlı (HML t-stat = −8.23,
[Eq.(1), PDF p.27]). Yani 1963-1991 örnekleminde 3-faktör hisse model + 2-faktör tahvil
model birleşimi içinde HML bağımsız bilgi taşır.

**İddia B:** [[famafrench2015_five_factor]] — RMW ve CMA eklendiğinde, HML 5-faktör
spanning regresyonunda intercept'i sıfırdan ayırt edilemez:
- 2×3 inşa: a = −0.04% (t = −0.47)
- 2×2 inşa: a = 0.00% (t = 0.01)
- 2×2×2×2 inşa: a = 0.02% (t = 0.23)

[Tablo 6, s.19]. 1963-2013 örnekleminde HML, MKT-RF + SMB + RMW + CMA tarafından span
edilir.

**Çelişkinin doğası:** **RHS faktör seti değişiyor**, örneklem genişliyor.
- FF93'te HML'in span edildiği RHS seti: {MKT-RF, SMB, TERM, DEF}
- FF15'te HML'in span edildiği RHS seti: {MKT-RF, SMB, RMW, CMA}
- FF15'te eklenen RMW ve CMA, HML zaman serisinin önemli bir kısmını taşıyor
  (HML ↔ CMA korelasyonu 0.70 [Tablo 4 Panel C, s.38]).

**Aslında çelişki değil — kanıt seti genişlemesi.** FF93 yorumu: "HML, mevcut
factor seti içinde span edilemez". FF15 yorumu: "HML, profitability + investment
faktörleri eklendiğinde span edilebilir".

**Resolution durumu:** **scope-dependent + sample-dependent.**
- Sample-dependent: FF15 yazarları "may be specific to this sample" uyarısı yapıyor
  [s.4]. Pre-1963, uluslararası, post-2013 testleri açık.
- Scope-dependent: 4-faktör (FF93 model) içinde HML hâlâ "incremental"; 5-faktör
  içinde değil.

**Cochrane çerçevesi içinde:** [[cochrane2011_discount_rates]] [s.13]
1. sorusu "which characteristics are subsumed by others?" — HML→{RMW, CMA}
subsumption bu sorunun **tipik bir empirik cevabı**dır. Yani çelişki değil,
factor zoo'nun normal evrimi.

**Strateji implikasyonu:**
1. Strateji tasarımında HML exposure hedefleniyorsa, ya HML doğrudan kullanılır
   (yorumlanabilirlik), ya da RMW + CMA combo kullanılır (FF15 önerisi:
   parsimony durumunda HML'i drop et).
2. Standalone value primum'u yine de var (HML mean 0.37%/ay, t=3.20, FF15
   örnekleminde [Tablo 4 Panel A, s.37]); "redundant" demek "primum yok" demek
   değil. → [[HML]] sayfasında detay.
3. S&P 500 / Nasdaq 100 large-cap evreninde RMW ve CMA primum'larının dağılımı
   farklı (CMA özellikle large-cap'te zayıf, [s.13]) — FF15'in HML redundancy
   sonucu large-cap evrene transferi henüz wiki'de doğrulanmadı (→
   [[meta/open_questions]] Q14).

---

## Aggregate anomaly survival rate — McLean-Pontiff 2016 ↔ HXZ 2020 methodology farkı

> 📝 **Cycle 13'te açıldı.** Cycle 11 kullanıcı kararı 4 ile placeholder
> bırakılmıştı; HXZ 2020 (Replicating Anomalies) ingest sonrası resmî
> entry açıldı. Wiki'nin **2. contradictions entry'si**.

**İddia A:** [[mclean_pontiff_2016_post_publication_decay]] —
**82-97 anomaly aggregate post-pub decay %35** (sig 1%); **~%65 spread
korunuyor**. Equal-weight long-short extreme quintile portfolios; CRSP
NYSE-Amex-NASDAQ all-stocks universe; publication-date-anchored
random-effects time-series regression. Sample 1972-2011.

**İddia B:** [[hou_xue_zhang_2020_replicating_anomalies]] —
**447 anomaly NYSE-breakpoint + value-weight replikasyon** ile
**%64 insig at klasik 5% level** (286/447); **%85 insig at HLZ-cutoff
t > 3.0** (380/447). Q-factor model 161 sig içinde 115'i insig
bırakır → **net %10 sig** (46/447). NYSE breakpoint + VW + microcap-
arınmış sample; q-factor model lens'inde test; static cutoff
(`|t| ≥ 1.96` ve `t > 3` paralel). Sample 1967-2014.

**Çelişkinin doğası:** **Methodology farkı + universe definition
farkı** (NOT sample-dependent — iki paper benzer 1967-2014 dönemlerini
kapsıyor):
- MP **equal-weight + NYSE-Amex-NASDAQ all-stocks** → microcap heavy
  → spread'ler şişiyor (mikrocap'ler %60+ stocks ama %3 market cap)
- HXZ **NYSE-VW + microcap-arınmış** → spread'ler küçülüyor → daha
  çok anomaly insig
- MP'nin "%65 hayatta" rakamı equal-weight artifact'i tarafından
  şişirilmiş; HXZ'nin "~%64 replicate olmuyor" rakamı microcap'ten
  arındırılmış halı

**Resolution durumu:** **scope-dependent (methodology disagreement).**

HXZ paper [s.3] MP'yi **explicit eleştirir** ama empirik çürütme
değil:

> "McLean and Pontiff (2016) study the out-of-sample performance of
> 97 anomalies, and find that their average high-minus-low returns
> decline out of sample and post publication. **However, McLean and
> Pontiff use NYSE-Amex-NASDAQ breakpoints and equal-weights in their
> tests.**"

Bu, MP'nin sonucunu çürütmek değil **methodology tercihi farkını
işaret etmek**. İki paper farklı methodology tercihleri kullanıyor;
empirik çelişen bulgular değil. Wiki'nin "taraf tutmaz" pozisyonuyla
**scope-dependent** uyumlu.

**Cycle 13 paper okuma sonrası teyit:** Plan'da hipotez
"scope-dependent"; paper okuma sonrası kesin teyit edildi (HXZ
methodology eleştirisi var ama ekonomik çürütme yok).

**Strateji implikasyonu Faz 3 için:**

1. **Decay-adjusted spread baseline'ı kalibre edilmeli:** MP %65
   hayatta yerine **HXZ NYSE-VW replication-aware** rakamı (~%36
   sig × decay-adjusted) wiki amaç evrenleri için daha relevant.
   Wiki amaç evrenleri (S&P 500 + NDX) NYSE-breakpoint + VW
   methodology'sine yakın → **HXZ rakamı doğru baseline**.

2. **NYSE breakpoint methodology Faz 3 strateji tasarımının default
   methodology tercihi olmalı** (Q12 ve yeni Q32 ile bağlantılı).
   Wiki'de SMB/HML için "NYSE breakpoint asimetrisi" eleştirisi
   vardı (Q12); HXZ'nin NYSE-VW preference bu sorunun
   methodology resolution'u. Wiki amaç evrenleri zaten NYSE-
   breakpoint üst-tarafında (S&P 500 = en büyük 500; NDX = en
   büyük 100 non-financial); microcap influence yapısal olarak yok.

3. **"Üç darbe çerçevesi" → "Dört darbe çerçevesi"** ile genişler:
   methodology-robust replikasyon dördüncü darbe ([[concepts/post_publication_decay]]).
   Wiki'deki ingested factor/strateji'ler için 19+ satır sentez
   tablosuna yeni Replication kolonu eklendi.

4. **Equal-weight all-stocks rakamlarını "biased upper bound" olarak
   kullan.** MP, Li-Mohanram modern, Mohanram NASDAQ partition
   rakamları wiki'de mevcut; bunlar **upper bound** (HXZ-aware lower
   bound ile beraber range) sağlar. Faz 3 backtest spec'inde
   range-based sensitivity analizi.

5. **Sloan operating accruals her iki yorumda da hayatta kalır:**
   MP aggregate %65 + HXZ q-factor alpha sig (-0.54%, t=-3.77).
   Wiki C bloğu omurgasının **çelişki ötesi statistical güçlenmesi**
   — F_ACCRUAL/G3 binary versiyonları komposit içinde sağlam.

---

## Aggregate factor replication rate — HXZ 2020 ↔ JKP 2023 dramatic empirik fark

> 📝 **Cycle 27'de açıldı.** Wiki'nin **3. contradictions entry'si**.
> Cycle 13 HXZ ↔ MP paterni paralel ama dramatic empirik fark scope-
> dependent + methodology disagreement. Plan §11 karar matrisi:
> dramatic empirik farklı bulgu varsa contradictions.md 3. entry açılır.

**İddia A:** [[hou_xue_zhang_2020_replicating_anomalies]] —
**447 anomaly NYSE-VW empirik replication US 1967-2014**:
- **%35 raw replication** (factors significant at 5% level)
- ~**%64 insig at 5%** (286/447); ~%85 insig at HLZ-cutoff `|t|>3`
- Q-factor model lens: **~%10 net sig** (46/447)
- "Most anomalies fail to hold up to currently acceptable standards
  for empirical finance" [HXZ 2020 paterni]

**İddia B:** [[jensen_kelly_pedersen_2023_replication_crisis]] —
**153 factor + 93 country Bayesian Empirical Bayes hierarchical
US 1926+ Global 1986+**:
- **%56.9 raw replication US** (HXZ ile aynı OLS t-stat methodology;
  capped VW + 1-month + longer sample +21.9pp methodology
  decomposition)
- **%84.9 Bayesian Empirical Bayes US** ⭐
- **%84.0 Bayesian Empirical Bayes Global** ⭐
- 10/13 themes >75% replicate; 10/13 themes tangency portfolio sig+
- Out-of-sample combined %88.5 positive
- "Collective body of factor research is both internally and
  externally valid" [JKP 2023 paterni]

**Çelişkinin doğası:** **~50pp gap dramatic empirik fark** (HXZ %35
vs JKP %84.9 Bayesian; %35 vs %56.9 raw +21.9pp methodology
decomposition kontrollü). Methodology choice'lara aşırı duyarlı:

| Methodology choice | HXZ | JKP | Replication rate fark |
|---|---|---|---|
| Weighting | Pure VW | **Capped VW** (NYSE 80th percentile winsorize) | +8.5pp |
| Holding period | 1/6/12-month tüm | **1-month only** | +4.0pp |
| Sample | 1967-2014 | **1926+ longer** | +4.3pp |
| Factor count | 447 (1/6/12-month variations) | 153 + 15 ek | +2.4pp |
| Minor construction | — | Robustification | +2.7pp |
| Statistical methodology | Frequentist OLS | **Bayesian Empirical Bayes hierarchical** | +28pp |

**Aslında çelişki değil — kanıt seti + methodology evrim**:
- HXZ raw VW + 1/6/12-month + US-only methodology choice'larında
  conservative (factor zoo'nun büyük çoğunluğu yetersiz)
- JKP capped VW + 1-month + global + Bayesian methodology
  choice'larında anti-conservative (factor zoo'nun büyük çoğunluğu
  geçerli)
- **Methodology farkı + framework farkı, empirik ham veri farkı
  değil** (paper [Figure 1] explicit decomposition)

**Resolution durumu:** **scope-dependent + methodology disagreement.**

JKP paper [s.1-3] HXZ 2020'yi explicit eleştirir ama empirik
çürütme değil:

> "Hou et al. (2020) [HXZ] focus their analysis on value-weighted
> factors rather than the standard Fama and French (1993) methodology...
> However, pure value weighting sometimes leads to excessively
> concentrated portfolios that mask the behavior of factors. We use
> a weighting scheme that we refer to as 'capped value-weighting'
> that winsorizes market caps at the NYSE 80th percentile."

Bu, HXZ sonucunu çürütmek değil **methodology choice farkı işaret
etmek**. İki paper farklı methodology choice'ları kullanıyor;
empirik çelişen bulgular **her iki sonuç kendi methodology
context'inde geçerli**.

**Cycle 27 paper okuma sonrası teyit:** Plan §11 karar matrisi
"dramatic empirik fark" kriterini karşılıyor (~50pp gap); methodology
decomposition transparent + Bayesian framework choice + global data
extension scope-dependent. **Cycle 13 HXZ ↔ MP paterni paralel** —
methodology disagreement, empirik çürütme değil.

**Strateji implikasyonu Faz 3 için:**

1. **Decay-adjusted spread baseline (×0.65 standard ×0.50 NDX
   agresif)** Cycle 24 v0_draft muhafazakâr revize **HXZ + MP
   paralel conservative tarafta**; JKP %85 replication
   anti-conservative tarafta. Wiki konservatizm korunur (over-
   promise riski Cycle 24 karar): **wiki için HXZ + MP rakamları
   baseline; JKP %85 upper bound sensitivity reference**.

2. **Methodology choice transparent reporting** Faz 3 backtest
   spec'inde:
   - Pure VW (HXZ baseline)
   - FF half-weight (FF1993 paterni)
   - **Capped VW NYSE 80th percentile (JKP)** ⭐
   üç alternative methodology sensitivity test ([[methodology/backtest_spec]]
   §1.3 universe methodology yeni alt-bölüm).

3. **Wiki için baseline tercih**: HXZ NYSE-VW + JKP capped VW
   üç-yolu (pure VW + capped VW + FF) replication-robust filter
   ([[methodology/backtest_spec]] §4.4 darbe (4) replication-robust):
   factor hayatta kalmak için **üç methodology tümünde sig** tercih
   edilebilir (en konservatif standard).

4. **13 theme cluster + tangency portfolio analysis** Faz 3 strategy
   spec anchor — JKP sertleştirme; HXZ replication eksik bu
   framework'ü direct olarak vermiyor.

5. **Bayesian framework choice** wiki için scope-dependent: factor-
   level evaluation HLZ frequentist + FGX frequentist DS LASSO
   tercih (Cycle 26 §3.3 + §4.3); strategy-level evaluation DSR;
   **JKP Bayesian Empirical Bayes hierarchical model + 13 theme
   tangency portfolio** Faz 3 multi-theme allocation framework
   anchor.

6. **MP 2016 aggregate %35 decay vs JKP %88.5 positive**:
   methodology decomposition (publication-anchored regression vs
   Bayesian replication framework); wiki için MP conservative
   decay multiplier korunur ama JKP anti-conservative reference.

> 📝 **Cycle 34 cross-strategy reference**: Bu entry'nin resolution +
> 6 strateji implication bullet'ı [[strategies/known_weaknesses]] §1.2
> (cross-strategy weakness 3. contradictions entry resolution
> acknowledged) wiki-level acknowledgment registry'de formalize edildi;
> sp500_v1 §4.3 + nasdaq100_v1 §4.3 sensitivity range 2x reporting
> (sp500 6-10% ↔ 14-18%; NDX 8-13% ↔ 16-21%); methodology choice
> transparent reporting ([[strategies/known_weaknesses]] §4.1 üç
> alternative weighting mandatory sensitivity test).

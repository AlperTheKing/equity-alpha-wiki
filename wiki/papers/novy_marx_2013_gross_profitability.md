---
type: paper
authors: [Novy-Marx, Robert]
year: 2013
title: "The Other Side of Value: The Gross Profitability Premium"
venue: "Journal of Financial Economics"
url: https://mysimon.rochester.edu/novy-marx/research/OSoV.pdf
local_path: raw/papers/novy_marx_2013_gross_profitability.pdf
ingested: 2026-05-01
tags: [profitability, value, quality, large_cap, b_block_complement, profitability_chain, qmj_origin, rmw_origin]
status: ingested
cycle: 23
cycle_38_note: "Profitability zinciri 1. halka GP/A → 4. halka Cop methodology evrim continuity [[papers/ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows]] Cycle 38 ✓; Ball-GLN [s.10] explicit 'Sharpe ratio for cash-based operating profitability is also higher than the Sharpe ratios for gross profitability and net income' Profitability zinciri 4-paper × 7-yıl methodology hierarchy GP/A → RMW Ope → QMJ GPOA → Cop"
block: B_complement
---

# Novy-Marx (2013) — The Other Side of Value: The Gross Profitability Premium

> 📝 **Faz 2 Cycle 23 ingest** — B kompleman (Quality blok); Faz 1
> sertifikası YUMUŞAK ikinci eksikliği (Cycle 22 Israel-Moskowitz E
> bloğu sonrası). Paper FF15 RMW factor + Asness QMJ Profitability
> dimension + HXZ 2020 Cop **literatür hattı zincirinin 1. halkası**.
> Wiki için yapısal kazanım: **Profitability zinciri** (Sloan zinciri
> paralel) dokümante.

## TL;DR

Novy-Marx **gross profits-to-assets (GP/A = (REVT − COGS) / AT)**
ölçüsünün cross-section of returns'i tahmin etme gücünün B/M kadar
güçlü olduğunu gösteriyor (1963-2010, ex-financials). **Ana bulgu**:
GP/A standalone univariate quintile sort high-low spread 0.31%/ay
(t=2.49) — modest ama FF3 alpha **0.52%/ay (t=4.49)** çünkü GP/A
**growth strategy** (HML loading büyük negatif). **Kritik**: GP/A
ve B/M Spearman correlation −0.18 → profitability "**the other side
of value**" — value investor için doğal **hedge**: 50/50 mix Sharpe
0.85 (market 0.34'ün 2.5x'ı). **Large-cap'te güçlü**: HML(GP)
controlling for GP = 0.54%/ay (t=5.01) vs vanilla HML 0.40% (t=3.25);
profitability information ratio Carhart UMD'den **daha yüksek** (5.54
vs 5.11). Industry-adjusted GP/A bir çok earnings-related ve
seemingly unrelated anomaly'i (ROE, default risk, net issuance,
organizational capital) "açıklıyor".

## Tek Cümle Tezi

**Gross profitability (revenue minus COGS) value premium ile
**ortogonal-ve-tamamlayıcı** bir cross-sectional return predictor**;
büyük cap'te bile economically significant, B/M ile combined edildiğinde
quality × value cross-product paterninin **yapısal anchor'ı**.

## Sample ve Methodology

- **Universe**: NYSE+Amex+Nasdaq, ex-financials (1-digit SIC 6 hariç)
- **Sample**: July 1963 - December 2010 (47 yıl)
- **Methodology**: NYSE breakpoints, **value-weighted** quintile
  portfolios, **annual June rebalance** ([s.9-10])
- **GP/A formülü**: (REVT − COGS) / AT (Compustat data items
  GP = REVT−COGS; scale by AT total assets)
- **Why gross profits, not earnings?** [s.5-7]: gross profits "cleanest
  accounting measure of true economic profitability"; daha aşağı income
  statement kalemleri (R&D, advertising, organizational capital
  investments) **expense olarak işlenmiş gelecek productive expenditures**'ı
  içerir, current earnings'i deflate eder, true profitability'i
  bulanıklaştırır. Gross profits R&D / advertising / organizational
  capital investment'lardan etkilenmemiş.
- **GP/A vs B/M Spearman correlation**: −0.18, sig (Cross-sectional
  rank correlation [s.10])
- **International evidence**: 19 developed market 1990-2009 [Tablo 5];
  international profitability spread vanilla international value
  spread'inden daha büyük

## Ortaya Konan Sinyal/Faktör

**Gross Profits-to-Assets (GP/A)** — yeni factor entity wiki'de açıldı:
[[factors/Gross_Profitability]]

**4 measure factor ailesi (Profitability zinciri dokümante)**:
- GP/A (Novy-Marx 2013 origin) — gross profits / total assets
- RMW Ope (FF15 [Tablo 1]; Novy-Marx 2013 cite [s.4]) — operating
  profitability (revenue − COGS − SG&A − interest) / book equity
- QMJ Profitability dimension GPOA bileşeni (Asness 2019; Novy-Marx
  2013 [s.7] cite) — gross profits-over-assets, QMJ 22 measure'dan
  biri
- Cop (HMXZ Tablo 5; HXZ 2020) — cash-based operating profits-to-assets
  (Ball-Gerakos-Linnainmaa-Nikolaev 2016 origin)

## Empirik Sonuçlar (sayılarla)

### 1. Fama-MacBeth regressions [Tablo 1]

GP/A coefficient: B/M kadar güçlü (paper Panel A). Industry-adjusted
GP/A coefficient B/M coefficient'ten **1.5x daha güçlü**, momentum
(r12;2) coefficient'ten **2.5x daha güçlü** [Panel B]. GP/A
**subsumes** earnings-to-book ve free cash flow-to-book Fama-MacBeth
regression'da [4. ve 5. spec].

### 2. Univariate quintile sort GP/A [Tablo 2]

| Portfolio | Excess return (%/ay) | FF3 α | t-stat α |
|-----------|----------------------|-------|----------|
| Low GP/A (Q1) | (paper detay) | (negatif) | — |
| High GP/A (Q5) | (paper detay) | (pozitif) | — |
| **Q5−Q1 spread** | **0.31** | **0.52** | **2.49 / 4.49** |

- HML loading büyük negatif (growth strategy → "the other side of value")
- B/M variation across GP/A portfolios: vanilla B/M sortunun ~yarısı
  [s.11]

### 3. GP/A × Value combined hedge [Tablo 2 + Section 3]

- 50/50 mix profitability + value:
  - Combined excess return: 0.71%/ay (0.31 + 0.41)
  - Combined std dev: 2.89% (her bir individual strategy'nin altında)
  - Correlation profitability ↔ value: **−0.57**
  - **Annual Sharpe: 0.85** (market 0.34'ün ~2.5x'ı)
  - Test-statistic combined return: 5.87
- Mix orthogonal to momentum [s.11]

### 4. Size partition [Tablo 4 — wiki amaç evrenleri kritik]

5×5 size × GP/A independent sort (ex-financials, NYSE breakpoints):

- **Profitability spread büyük cap'te de sig**: large-cap (Q5)
  high-low GP/A spread = 0.26%/ay (t=1.88 marjinal raw); FF3 alpha
  large-cap'te small-cap kadar güçlü (negatif HML loading küçülmüyor;
  GP/A predictive power "**economically significant even among
  the largest stocks**" [s.13])
- **Fortune 500 strategy** [Tablo 7, Section 3.2]: largest 500
  non-financial stocks; combined GP/V long-short rank-based:
  - Excess return **0.62%/ay (~7.4%/yıl)**
  - **Annual Sharpe 0.74** (market 0.34'ün 2x'ı)
  - **Trading exclusively in Fortune 500 universe** ⭐ wiki amaç evrenleri
    (S&P 500) için **direct kanıt**
  - Turnover 1/3 her yıl her bacakta (low cost)
  - Long-side alone information ratio: 18bps/ay (t=3.46) market-hedged

### 5. Conditional factor [Tablo 8]

- **HML|GP** (HML controlling for profitability):
  - 0.54%/ay (t=5.01) vs vanilla HML 0.40% (t=3.25); **35% güçlenme**
- **PMU|BM** (profitability factor controlling for B/M):
  - 0.48%/ay (t=5.35) vs unconditional profitability 0.31% (t=2.49)
- **Information ratio comparison**: PMU|BM 4-factor alpha t=5.54;
  Carhart UMD 4-factor alpha t=5.11 → **profitability factor UMD'den
  daha yüksek IR** (raw return düşük ama HML hedge avantajı)
- HML standalone HML|GP + PMU|BM tarafından **span ediliyor** (alpha
  insig)

### 6. International evidence [Tablo 5]

19 developed market 1990-2009 — international profitability spread
sig + vanilla international value spread'inden büyük. Profitability
premium **global**.

### 7. Anomaly pricing [Section 4]

Industry-adjusted GP/A factor + value + momentum 4-factor model:
- ROE, E/P, asset turnover, gross margins, SUE earnings anomalies
- Default risk (Campbell-Hilscher-Szilagyi 2008), failure prob,
  O-Score (Ohlson 1980), net stock issuance, asset growth, accruals,
  organizational capital (Eisfeldt-Papanikolaou 2011)
- Bu anomaliler **industry-adjusted GP/A + value + momentum
  3-factor mix'inin farklı kombinasyonları** [Section 4]

## Goal Alignment

| Özellik | Bu paper'daki durum | İşaret |
|---|---|---|
| **Top-N selection** | Univariate quintile sort high-low spread + Fortune 500 rank-based combined GP/V long-short [Tablo 7] + double sort 5×5 quintile [Tablo 6]; standard cross-sectional anomaly methodology | ✅ doğrudan fit |
| **Annual rebalance** | ⭐ **Annual June rebalance default** [s.9-10]; turnover 1/3/yıl Fortune 500 strategy [s.16]; quarterly high-frequency variant Appendix A.4 ek; **wiki proje amacı annual ile direct uyum** (UMD/QMJ aylık-orijinal sensitivity Q33+Q35 paralel'inin TERSİ — Novy-Marx zaten annual baseline) | ✅ doğrudan + **özellikle güçlü fit** |
| **Large-cap evrene transfer** | ⭐ ⭐ KRITIK doğrudan fit; **Fortune 500 strategy** [Tablo 7] direct large-cap-only kanıt: 0.62%/ay, Sharpe 0.74; size partition Tablo 4 large-cap quintile FF3 alpha "small-cap kadar güçlü"; **Israel-Moskowitz HML size Q5 INSIG paterninin TERSİ** — profitability premium **size-invariant**; Q14 CMA/RMW partial-stronger (RMW direct large-cap kanıt aday) | ✅ ⭐ ⭐ KRITIK direct fit (S&P 500 için **birebir match**) |
| **NDX intangibles / growth firms** | ⚠️ caveat: GP/A traditional accounting; **gross profits R&D/advertising/organizational capital expense'lerinden ARÎ** [s.5-7] — bu **intangibles-aware avantajı** (numerator earnings'ten daha yüksek; tech firmalar için doğru proxy); ama denominator total assets intangibles düzeltmesi yapmıyor → F bloğu ([[concepts/intangibles_adjusted_accounting]]) ile **partial fit**; intangibles-aware GP/A revize Faz 3 spec adayı (Q56 yeni) | ⚠️ partial fit + ⭐ intangibles-aware numerator |

**Strateji tasarımına net implikasyon:**

1. **Fortune 500 strategy = wiki S&P 500 baseline ile birebir match**.
   Novy-Marx [Tablo 7] 500 largest non-financial stocks combined GP/V
   rank-based 0.62%/ay, Sharpe 0.74 → S&P 500 strategy spec için
   **direct empirik anchor**. Li-Mohanram F&V/P + G&V/P combined
   paterninin **Novy-Marx GP/V analoğu** — QARP framework'ün empirik
   altyapısı.

2. **Profitability premium size-invariant** (Israel-Moskowitz HML size
   Q5 INSIG paterninin TERSİ). Wiki amaç evrenleri (S&P 500 + NDX
   top 100-500) için GP/A actionable; vanilla HML reject (Cycle 22)
   sonrasında **GP/A primary value-side alternative**.

3. **Profitability zinciri 1. halkası** dokümante: Novy-Marx 2013 →
   FF15 RMW (Ope methodology) → Asness 2019 QMJ Profitability dimension
   (GPOA bileşeni) → HXZ 2020 Cop (cash-based evrim). Faz 3 strategy
   spec'inde **iki paralel quality zinciri**: Sloan (mispricing/accruals)
   + Novy-Marx (profitability/quality). QMJ 4-dimension breakdown
   bu iki zincirin **birleşim noktası**.

4. **GP/A ↔ B/M Spearman = −0.18 + correlation profitability strategy
   ↔ value strategy = −0.57** → combined yaklaşım Sharpe 0.85.
   [[papers/li_mohanram2019_quality_value]] F&V/P + G&V/P binary
   intersection paradigmasının **sürekli z-score paraleli** (Asness
   QARP framework).

## Limitler ve Caveats

- **Sample sonu Dec 2010** — post-2010 (FAANG era 2011-2024 + COVID
  + AI) out-of-sample; modern data Chen-Zimmermann + JKP 2023 ek
  ingest gerekli (Faz 2 sonu)
- **Annual rebalance default** ama high-frequency (quarterly)
  variant Appendix A.4 daha güçlü performance — wiki annual default
  Novy-Marx baseline ile uyumlu
- **GP/A denominator total assets** intangibles düzeltmesi yapmıyor;
  numerator gross profits R&D/SG&A'dan ARÎ (intangibles-aware avantaj)
  ama denominator F bloğu ([[concepts/intangibles_adjusted_accounting]])
  Lev-Sougiannis perpetual inventory + Peters-Taylor total intangible
  capital ile güçlendirilebilir (Q56 yeni)
- **Ex-financials** sample — financial firms büyük asset base low
  GP/A artifact'i [s.10 fn 4]; finansal firmalar separately treatment
  gerekir
- **Industry adjustment 49 industry portfolios** [Section 4]
  industry-adjusted GP/A daha güçlü; modern GICS sektör mapping
  Faz 3 spec'i için kalibrasyon gerekli (Q38 paralel)
- **Cop (HMXZ Tablo 5) cash-based evrim** Novy-Marx GP/A'dan superior
  ([[papers/hou_xue_zhang_2020_replicating_anomalies]] q-factor
  alpha 0.69%/ay sig); GP/A vs Cop horse race Q55 yeni

## İlgili Sayfalar

### Bu paperın ürettiği yeni sayfalar
- [[factors/Gross_Profitability]] — yeni factor entity (Cycle 23);
  GP/A standalone factor; Profitability zinciri 1. halka

### Bu paperın update ettiği mevcut sayfalar
- [[factors/RMW]] — FF15 Ope methodology kökü Novy-Marx GP/A; Profitability
  zinciri 2. halka; methodology hierarchy GP/A vs Ope vs GPOA vs Cop
- [[factors/QMJ]] — 4 dimension breakdown sertleştirme: Profitability
  dimension Novy-Marx ana literatür kökü; GPOA bileşeni QMJ paper
  [s.7] explicit cite; Sloan zinciri paralel **Profitability zinciri**
- [[factors/Accruals]] — paralel quality zinciri (Sloan mispricing
  vs Novy-Marx profitability); Novy-Marx [s.7 fn 1] Sloan accruals
  cite + GP/A power persists controlling for accruals [Appendix A.3]
- [[papers/famafrench2015_five_factor]] — RMW factor inşası Novy-Marx
  2013 cite [FF15 s.4]; RMW Ope methodology farkı (numerator interest
  + SG&A çıkarılmış; denominator book equity)
- [[papers/asness_frazzini_pedersen_2019_qmj]] — QMJ Profitability
  dimension GPOA component Novy-Marx 2013 explicit cite [QMJ s.7];
  Sloan zinciri 4. halka + Profitability zinciri 3. halka iki paralel
  zincir QMJ'de birleşiyor
- [[papers/hou_mo_xue_zhang_2020_security_analysis]] — HMXZ Tablo 5
  cash-based operating profitability Cop Novy-Marx GP/A'dan **cash-aware
  evrim** (Ball-GLN 2016 origin); 4/4 hayatta kalan factor
- [[papers/hou_xue_zhang_2020_replicating_anomalies]] — Cop q-factor
  alpha 0.69%/ay sig; Profitability zinciri 4. halka empirik validation
- [[papers/sloan1996_accruals_anomaly]] — paralel quality zinciri:
  Sloan (mispricing/accruals) ↔ Novy-Marx (profitability/quality);
  iki zincir QMJ 4-dimension'da birleşiyor (ACC + GPOA components)
- Lakonishok-Shleifer-Vishny 1994 (Tier 1 #7, **henüz ingest
  edilmedi**) — Novy-Marx [s.1, fn 1] cite; LSV 1994 cash flow +
  earnings strategies "individual components of difference between
  gross profits and earnings" precursor
- [[eisfeldt_papanikolaou_2013_organization_capital]] — **Cycle 25
  yeni**; Novy-Marx [Section 4] organizational capital based strategy
  (Eisfeldt-Papanikolaou 2011 cite) industry-adjusted GP/A + value +
  momentum 3-factor model "açıklıyor" iddiası; Eisfeldt-Papanikolaou
  Cycle 25 ingest direct factor portfolio kanıtı: Carhart 4F altında
  α=3.9% sig 1% — **Novy-Marx claim partial reject** (organization
  capital independent premium kalıyor; Q58 partial-stronger). High
  OC firms Novy-Marx gross profitability profile ile yapısal paralel
  (low PP&E/AT + growth-tilted + low leverage).
- [[feng_giglio_xiu_2020_factor_zoo]] — **Cycle 26**; **Q55 fully-
  answered**: Profitability ailesi DS LASSO 150-factor library lens
  validation (RMW + ROE + QMJ DS-sig); GP/A 150 library içinde
  explicit listed teyit edilemedi (Tablo 4 ham liste paperdan tek-tek
  kontrol edilmedi) ama Profitability ailesi genel sig dolaylı
  validation; v0_draft Profitability seçimi DOĞRULANDI. Profitability
  zinciri 4 halka (Novy-Marx GP/A → FF15 RMW → QMJ GPOA → HXZ Cop)
  FGX paralel methodology (HXZ q-factor + FGX DS LASSO + MP behavioral
  decay + **JKP Bayesian Empirical Bayes** **dört paper × dört
  methodology aile** factor zoo decay ~%85-90 conservative-side
  çift+üç+dört teyit; JKP anti-conservative-side %85 replication
  dramatic methodology disagreement [[meta/contradictions]] §3
  Cycle 27 sertleştirme).
- [[concepts/fundamental_scoring]] — composite scoring tablosu GP/A
  standalone signal satırı; Profitability alt-boyutu sertleştirme
- [[concepts/winner_loser_identification]] — GP/A signal-as-winner
  anchor; "value premium uzun bacağı içinde profitability refinement"
- [[concepts/factor_zoo]] — RMW + GP/A + GPOA + Cop ailesi factor
  proliferation/redundancy perspektif
- [[concepts/post_publication_decay]] — dört darbe sentez tablosu
  Profitability zinciri 4 satır sertleştirme
- [[methodology/backtest_spec]] — §5.1 4/4 hayatta kalan tablosu Cop
  satırı origin attribution; §5.2 baseline composite QMJ row sertleştirme;
  §7 Composite scoring methodology Profitability zinciri yeni alt-bölüm;
  §8 Origin attribution **Profitability zinciri** (Sloan paralel)

## Çelişkiler/Tartışmalar

### FF06 vs Novy-Marx 2013 (paper içi tartışma)

Novy-Marx [s.4-5] Fama-French 2006'nın "earnings has explanatory
power but profitability sorts produce the weakest hedge portfolio
returns" bulgusunu **methodology-spesifik** olarak işaretliyor: FF06
**earnings (current income)** kullanıyor, Novy-Marx **gross profits**.
Earnings R&D / advertising / capex / SG&A / interest çıkarıldıktan
sonra deflated; gross profits "cleanest measure". Methodology farkı
empirik çürütme değil, **measure tercihi farkı**. Wiki için: FF06
ayrı ingest edilmedi; paper içinde explicit methodology comparison
not edilir, ayrı contradictions entry açılmaz.

### HXZ 2020 Cop > GP/A (Profitability zinciri evrim)

[[papers/hou_xue_zhang_2020_replicating_anomalies]] Cop (cash-based
operating profits-to-assets, Ball-GLN 2016 origin) q-factor alpha
0.69%/ay sig (4/4 hayatta kalan); Novy-Marx GP/A doğrudan paperda
test edilmiş ama Cop'un Profitability zincirinde superior olduğu
HMXZ Security Analysis [Tablo 5] kanıtla. **Çelişki değil, evrim**:
Cop = GP/A + cash adjustments (working capital + capex çıkarılmış);
"cash-aware quality" Profitability zinciri 4. halkasının yapısal
iyileşmesi. Wiki taraf tutmaz; **methodology evrim**, mathematical
equivalence.

### Israel-Moskowitz 2013 vs Novy-Marx 2013 (paralel teyit)

İki paper aynı yıl (2013), iki farklı boyut:
- Israel-Moskowitz: vanilla HML size Q5 (largest 40% NYSE) INSIG
- Novy-Marx: GP/A size Q5 (largest) FF3 alpha small-cap kadar güçlü;
  Fortune 500 strategy 0.62%/ay sig

**Çelişki yok, çift kompleman**: vanilla value premium large-cap'te
silinirken (Israel-Moskowitz) profitability premium hayatta
(Novy-Marx). Wiki strategy spec için: **vanilla HML reject (Cycle
22) + GP/A primary value-side alternative (Cycle 23)**.

## Açık Sorular (Open Questions)

- **Q49** (QMJ 4 dimension hangisi en güçlü) → Novy-Marx
  **partial-stronger**: Profitability dimension origin paper direct
  kanıt (GP/A + PMU|BM standalone sig); QMJ Profitability composite
  6 measure'dan 1'i (GPOA). Tam cevap için QMJ Tablo VI Panel A
  dimension-spesifik t-statistic decompose hala gerekli.
- **Q14** (FF5 large-cap-only başarısızlık portföyü; Cycle 22'de HML
  fully-answered) → **CMA/RMW partial-stronger** (RMW Ope methodology
  Novy-Marx GP/A kökü; large-cap-only RMW Ope ↔ GP/A direct
  comparison Faz 2 sentez)
- **Q21** (combined methodology Li-Mohanram + Asness QARP) →
  **partial-stronger**: Novy-Marx Fortune 500 GP/V combined rank-based
  paterni Li-Mohanram F&V/P + G&V/P paralel; **iki operationalization
  horse race** (binary intersection vs continuous rank product) Faz 3
- **Q55 yeni**: GP/A vs RMW Ope vs Cop horse race
  - GP/A: (REVT − COGS) / AT, [Novy-Marx 2013]
  - RMW Ope: (REVT − COGS − SG&A − interest) / BE, [FF15]
  - QMJ GPOA: gross profits-over-assets, [Asness 2019]
  - Cop: (REVT − COGS − SG&A + R&D − ΔWC − ΔAR + ΔAP) / AT,
    [HMXZ Tablo 5]
  4 measure direct comparison wiki'de eksik; FGX 2020 (Tier 1 #21)
  ek ingest tam cevap için
- **Q56 yeni**: Intangibles-aware GP/A (R&D-amortized adjusted
  numerator + total intangible capital denominator) — F bloğu
  ([[concepts/intangibles_adjusted_accounting]]) Lev-Sougiannis +
  Peters-Taylor methodology + Novy-Marx GP/A entegrasyonu wiki'de
  yok; FAANG firmalarda recurring revenue R&D-amortized GP/A Faz 3
  NDX strategy spec için
- **Q57 yeni**: GP/A annual rebalance optimal frekans
  - Novy-Marx annual default; quarterly Appendix A.4 daha güçlü
    monthly returns
  - Wiki amaç evrenleri annual; turnover/cost trade-off
  - Frazzini-Israel-Moskowitz 2018 (Tier 3 #52, paywall) firm-level
    cost analysis ek
- **Q58 yeni**: Industry-adjusted GP/A factor anomaly explanation
  power
  - Novy-Marx Section 4 industry-adjusted GP/A + value + momentum
    3-factor model 11 anomaly açıklıyor
  - q-factor model (HMXZ q5) ile alternative explanation
  - **Iki yorum çatallanması** (productivity proxy vs investment
    factor exposure proxy) Cochrane mathematical equivalence; wiki
    taraf tutmaz

## Strateji tasarımına spesifik katkı

1. **Fortune 500 strategy = wiki S&P 500 baseline direct anchor**.
   Combined GP/V rank-based long-short Sharpe 0.74; long-side alone
   market-hedged 18bps/ay sig. Faz 3 [s&p500_v1.md] strategy spec
   için **birebir empirik altyapı**.

2. **GP/A primary value-side alternative** (vanilla HML reject sonrası).
   Israel-Moskowitz Cycle 22 vanilla HML large-cap REJECT + Novy-Marx
   GP/A large-cap sig kompleman. Wiki amaç evrenleri için "value"
   exposure GP/V combined paterninde gerçekleşir.

3. **Profitability zinciri 1. halka dokümante**. Sloan zinciri (Sloan
   1996 → Piotroski 2000 F_ACCRUAL → Mohanram 2005 G3 → QMJ ACC,
   23 yıl mispricing detection paradigması) **paralel'i**: Novy-Marx
   2013 → FF15 RMW Ope → QMJ GPOA → HXZ Cop, 7 yıl profitability
   evrim paradigması. QMJ 4-dimension breakdown iki zincirin
   birleşim noktası.

4. **GP/V combined Sharpe 0.85 anchor** Asness QARP framework + Li-
   Mohanram F&V/P + G&V/P paterninin yapısal teyidi. Faz 3 NDX
   strategy spec'inde G & V/P + GP/V iki alternative QARP
   operationalization horse race.

5. **Annual rebalance baseline** (Novy-Marx default) wiki proje
   amacıyla **direct uyum**; UMD/QMJ aylık-orijinal annual uyarlama
   sensitivity Q33+Q35 endişelerinin TERSİ — GP/A wiki için zaten
   annual baseline.

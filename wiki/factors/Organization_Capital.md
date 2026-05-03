---
type: factor
name: Organization_Capital
alias: OC
category: intangibles
direction: long_high
data_lag_required: "≥6 months after fiscal year end (June rebalance konvansiyonu)"
rebalance_frequency: annual
universe_tested: ["NYSE+Amex+Nasdaq Compustat 1970-2008 (industry-relative within FF17)", "Unconditional sort ex-financials"]
---

# Organization Capital — OC (Eisfeldt-Papanikolaou 2013)

## Tanım (matematiksel)

**Organization Capital stock (perpetual inventory)**
([[papers/eisfeldt_papanikolaou_2013_organization_capital]] Eq.(1) [s.6]):

```
O_{i,t} = (1 − δ) × O_{i,t-1} + SG&A_{i,t}
```

- **SG&A** (Compustat): Selling, General, and Administrative expense
  (CPI-deflated)
- **δ = 15%/yıl** default depreciation rate
- **Initial stock**: O_0 = SG&A_1 / (g − δ), g matched to steady-state
  average investment rate ≈ 0.25
- **Sort metric**: O/A ratio = O_{i,t} / Total_Assets_{i,t}
  (organization capital stock / total assets) within industry

**Methodology işareti**: stock measure (perpetual inventory; BEA R&D
capital methodology paralel); industry-relative within FF17 17-industry
classification quintile sort

**Kritik tasarım kararı** ([[papers/eisfeldt_papanikolaou_2013_organization_capital]]
[s.5-7]): SG&A "key inputs to organization capital" olarak treat ediliyor
(Lev-Radhakrishnan 2004 paterni); IT outlays + employee training costs
+ brand enhancement + consulting fees + distribution channel
maintenance dahil. Measurement error caveat [s.6]: "to the extent that
some SG&A expenditures do not constitute investment in organization
capital we will be measuring this capital with error" → trade-off
model independence vs measurement error (alternatif: Peters-Taylor
2017 θ=30% allocation; Q60 yeni).

## Origin

- **İlk paper**: [[papers/eisfeldt_papanikolaou_2013_organization_capital]]
- **Yazarlar**: Andrea L. Eisfeldt + Dimitris Papanikolaou (Northwestern
  University Kellogg)
- **Sample**: January 1970 - December 2008 (38 yıl)
- **Methodology**: Industry-relative within FF17 + value-weighted
  quintile sort + annual June rebalance

## F bloğu 4-katmanlı methodology hierarchy (origin attribution)

Wiki için yapısal kazanım: **F bloğu Cycle 17'de 3-katmanlı
kapatılmıştı; Cycle 25 ek 4. ayak (factor portfolio direct evidence)**.
Methodology infrastructure ile factor portfolio anchor ayrımı
dokümante:

| Katman | Paper | Component | Yıl | Methodology evrim |
|--------|-------|-----------|-----|-------------------|
| 1 (Knowledge) | [[papers/lev_sougiannis_1996_rd_capitalization]] | R&D capital perpetual inventory | 1996 | Industry-spesifik amortization (5-9 yıl); R&D-only; **methodology infrastructure** |
| **2 (Organization)** | **[[papers/eisfeldt_papanikolaou_2013_organization_capital]]** | OC factor portfolio (SG&A perpetual inventory δ=15%) | 2013 | **Factor portfolio direct evidence** ⭐; long-short hedge return 4.8%/yıl Sharpe 0.58 |
| 3 (Total) | [[papers/peters_taylor_2017_intangible_capital]] | q^tot proxy (Knowledge + Organization + External) | 2017 | Total intangible capital generalization; q theory test; θ=30% SG&A allocation |
| 4 (Application) | [[papers/lev_srivastava_2020_value_failure]] | Adjusted HML post-2010 value crisis decomposition | 2020 | Intangibles bias + mean reversion slowdown |

**Methodology infrastructure (1+3+4) + factor portfolio anchor (2)**
ayrımı wiki için yapısal kazanım. Faz 3 strategy spec'inde NDX
overlay layer:
- Adjusted Bm rebuild (1+3+4 methodology infrastructure)
- **OC factor signal layer (2 direct factor portfolio)**

## Reported Performance Across Studies

| Paper | Dönem | Evren | Spec | Spread/Alpha | t-stat | Notlar |
|-------|-------|-------|------|--------------|--------|--------|
| [[papers/eisfeldt_papanikolaou_2013_organization_capital]] industry-relative | 1970-2008 | NYSE+Amex+Nasdaq Compustat FF17 | Q5−Q1 raw | **4.8%/yıl** | sig | [Tablo 3]; Sharpe 0.58 |
| [[papers/eisfeldt_papanikolaou_2013_organization_capital]] industry-relative | aynı | aynı | CAPM α | **5.6%** | sig | [Tablo 4] |
| [[papers/eisfeldt_papanikolaou_2013_organization_capital]] industry-relative | aynı | aynı | FF3 α | **5.5%** | sig | [Tablo 4]; SMB+HML loadings essentially uncorrelated |
| [[papers/eisfeldt_papanikolaou_2013_organization_capital]] industry-relative | aynı | aynı | Carhart 4F α | **3.9%** | sig 1% | [Tablo 4]; UMD ek faktör altında premium kalıyor |
| [[papers/eisfeldt_papanikolaou_2013_organization_capital]] depreciation 0.10-0.50 robustness | aynı | aynı | Q5-Q1 raw range | 4.2-5.3% | sig | [s.10]; methodology robust |
| [[papers/eisfeldt_papanikolaou_2013_organization_capital]] **unconditional sort ex-fin** | aynı | NYSE+Amex+Nasdaq ex-fin | Q5−Q1 raw | 3.86% | sig | [s.10]; HXZ paralel methodology (industry-neutral) |
| [[papers/eisfeldt_papanikolaou_2013_organization_capital]] **DOL-controlled sort** | aynı | aynı | Q5−Q1 within DOL tercile | **3.1%** | sig 1% | [s.10]; **operating leverage explanation rejected** |

## Faktör Ailesi İçindeki Yeri

### F bloğu intangibles aile

- **Knowledge capital ↔ Organization capital korelasyon (Q59 yeni)**:
  Lev-Sougiannis R&D perpetual inventory + Eisfeldt-Papanikolaou
  SG&A perpetual inventory iki ayrı intangibles ayağı; orthogonality
  empirik test wiki'de eksik; Peters-Taylor 2017 θ=30% allocation
  Knowledge ↔ Organization ayrım methodology paterni
- **Total intangible q proxy**: Peters-Taylor q^tot = V / (K^phy +
  K^int) içinde K^int = Knowledge + Organization + External; OC
  factor portfolio direct evidence Peters-Taylor q theory test'in
  factor portfolio karşılığı
- **Adjusted HML uygulaması**: Lev-Srivastava 2020 adjusted BV
  methodology'sinde organization capital component dahil; OC factor
  Lev-Srivastava methodology'sine entegre edilebilir

### Komşu factor'lerle ilişki

- **High OC ↔ Novy-Marx GP/A**: paralel; Novy-Marx [Section 4]
  organizational capital based strategy industry-adjusted GP/A +
  value + momentum 3-factor model "açıklıyor" iddiası — Eisfeldt-
  Papanikolaou direct factor portfolio Carhart 4F altında α=3.9%
  sig 1% (Q58 partial-stronger; Novy-Marx claim partial reject)
- **High OC ↔ QMJ Profitability dimension paralel**: high OC firms
  high Tobin's Q + low leverage + growth-tilted; QMJ Profitability
  composite içinde organizational capital indirect representation
- **High OC ↔ HML negative correlation (zayıf)**: portfolio-level VW
  BE/ME high OC quintile düşük (growth-tilted); ama median firm
  BE/ME farklı değil; SMB+HML factor loadings essentially uncorrelated
  [Tablo 4]

### Operating leverage explanation REJECTED

[[papers/eisfeldt_papanikolaou_2013_organization_capital]] [s.10]
DOL-controlled sort: degree of operating leverage tercile within
industry → 3-OC sort; spread **3.1%** still sig 1% (CAPM α 3.7%,
FF3 α 4.2%, Carhart α 3.3%). Operating leverage alone OC factor
premium'unu açıklamıyor → firm-specific worker-embodied risk
yapısal mekanizma ([[papers/eisfeldt_papanikolaou_2013_organization_capital]]
Section 3 model paralel).

## S&P 500 / Nasdaq 100 Spesifik Kanıtlar

⚠️ **Direct large-cap-only test eksik**:
[[papers/eisfeldt_papanikolaou_2013_organization_capital]] [s.8]
"market cap not vary substantially across portfolios" general
statement; size partition (Q1-Q5 size × Q1-Q5 OC) decomposition
paperde yok. **Q4 paterni**: large-cap kanıt seviyesi orta (size-
loaded değil — high OC quintile slightly higher market cap ama sig
fark yok).

⭐ **NDX FAANG profile birebir match**: high OC firms karakteristikleri
[Tablo 1] NDX top 100 non-financial profili ile uyumlu:
- Low PP&E/AT (intangibles-yoğun) ✅ FAANG
- Low leverage ✅ tech
- High Tobin's Q ✅ growth-tilted
- Low capital-labor ratio ✅ labor-intensive
- High operating leverage ✅ recurring revenue model

NDX strategy spec için **birebir match** ([[strategies/v0_draft]]
§2.B NDX intangibles-aware overlay anchor).

## Decay / Post-Publication Performance + Multiple Testing Status

[[papers/mclean_pontiff_2016_post_publication_decay]] aggregate %35
post-pub decay multiplier proxy uygulanır → OC factor FF3 α 5.5% ×
0.65 ≈ 3.6%/yıl decay-adjusted; NDX agresif ×0.50 → 2.75%/yıl.

[[papers/harvey_liu_zhu_2016_multiple_testing]] HLZ recommended cutoff
`|t| > 3.0` BHY: OC factor Carhart α t-stat paperde explicit yok
(α=3.9% sig 1%; muhtemelen t≈2.5-3.0 borderline); FF3 α=5.5% güçlü
sig (HLZ cutoff'u rahat geçer); CAPM α=5.6% sig.

[[papers/hou_xue_zhang_2020_replicating_anomalies]] HXZ NYSE-VW
replication methodology paralel: Eisfeldt-Papanikolaou unconditional
sort ex-financials spread 3.86% (Carhart α 5.4% sig) → **HXZ
paralel methodology**. HXZ 2020 [s.2] organization capital factor
447 anomaly içinde test ediliyor — replication status text extract
detail yok ama unconditional spec sig.

[[concepts/post_publication_decay]] dört darbe çerçevesi sentez tablosu
Cycle 25 OC factor satırı eklenir:
- In-sample large-cap: ⚠️ partial fit (industry-relative methodology
  size-neutralizing; large-cap-only direct test eksik)
- Post-pub decay-adjusted: ~3.6%/yıl (×0.65) — sample sonu 2008
  proxy (Q57 paralel)
- MT-corrected: ✅ FF3 α t-stat güçlü; Carhart α borderline
- Replication-robust: ✅ unconditional sort spread 3.86% Carhart α
  5.4% sig; HXZ NYSE-VW paralel methodology

**Dört darbe filter konumu**: **3-4/4 hayatta kalan** (Carhart
borderline; F bloğu factor portfolio direct evidence anchor).

## Implementation Notes

- **Required Compustat data**: SGA (SG&A expense), AT (total assets);
  CPI deflator
- **Annual reporting frequency adequate**; quarterly variant
  paperde test edilmemiş
- **Universe**: Industry-relative within FF17 (financials dahil);
  unconditional sort ex-financials
- **Rebalance**: Annual June rebalance + 6-month accounting lag
  (FF konvansiyon)
- **Initial stock**: O_0 = SG&A_1 / (g − δ); 5+ önceki SG&A obs
  filter robustness (spread 4.2% vs 4.8%)
- **Industry classification**: FF17 17-industry; modern GICS Level-2/3
  mapping NDX strategy için kalibrasyon (Q38 + Q61 paralel)

## Bu Faktörün Yumuşak Karnı

- **SG&A measurement noise** [s.6-7]: SG&A expenditures'ın hepsi
  organization capital değil; Peters-Taylor θ=30% allocation
  alternative (Q60 yeni) — modern kalibrasyon empirik comparison
  eksik
- **Sample sonu Dec 2008** — post-2008 FAANG era 2009-2024 + COVID +
  AI out-of-sample; JKP 2023 (Cycle 27) modern replication + Chen-
  Zimmermann (Cycle 29) data portal ek ingest
- **Large-cap-only direct test eksik** [s.8 general statement];
  NDX FAANG profile match yapısal ama empirik direct kanıt eksik
- **Industry-relative methodology** size-neutralizing avantajı ama
  cross-industry OC dispersion modern dönem sektör compositional
  shift altında değişebilir (Q61 yeni; Lev-Srivastava 2020 [Section
  9] paralel)
- **HXZ 2020 replication status** text extract'te net teyit edilmedi;
  q-factor span direct evidence eksik (Q23 partial-stronger ama
  tam cevap için HXZ 2020 Internet Appendix detail bağımlı)
- **FGX 2020 (Cycle 26) DS LASSO 150-factor library içinde explicit
  teyit edilemedi**: FGX [Tablo 4] ham liste paperdan tek-tek
  kontrol edilmedi; **intermediary investment factor (He-Kelly-Manela
  2016)** DS-sig (Cycle 26 Tablo 1) ama bu organizational capital
  factor değil, intermediary capital. Q64 yeni: F bloğu intangibles
  factor'lerin (Lev-Sougiannis Knowledge + Eisfeldt-Papanikolaou OC
  + Peters-Taylor q^tot) FGX framework'üne entegrasyonu eksik.
- **Carhart 4F α t-stat borderline**: paper text extract α=3.9% sig
  1% diyor ama explicit t-stat verilmedi; HLZ `|t| > 3.0` BHY cutoff
  ile borderline durum

## İlgili

### F bloğu hierarchy
- [[papers/lev_sougiannis_1996_rd_capitalization]] — F bloğu 1.
  ayak (Knowledge capital)
- [[papers/eisfeldt_papanikolaou_2013_organization_capital]] —
  F bloğu **2. ayak (Organization capital factor portfolio)** ⭐
  origin
- [[papers/peters_taylor_2017_intangible_capital]] — F bloğu 3.
  ayak (Total intangible q proxy)
- [[papers/lev_srivastava_2020_value_failure]] — F bloğu 4. ayak
  (Application)
- [[concepts/intangibles_adjusted_accounting]] — F bloğu hub;
  Cycle 25 4-katmanlı hierarchy sertleştirme

### Komşu factor'ler
- [[factors/Gross_Profitability]] — Novy-Marx GP/A; Section 4
  organizational capital based strategy explicit cite Eisfeldt-
  Papanikolaou (Q58)
- [[factors/QMJ]] — Profitability dimension organizational capital
  indirect representation
- [[factors/HML]] — High OC growth-tilted; portfolio-level VW BE/ME
  düşük
- [[factors/G_Score]] — Mohanram industry-median FF17 paralel
  methodology

### Methodology
- [[methodology/backtest_spec]] §6 F bloğu intangibles-aware
  methodology 4-katmanlı hierarchy

### Strategy
- [[strategies/v0_draft]] §2.B NDX intangibles-aware overlay anchor

### Concepts
- [[concepts/factor_zoo]] — F bloğu intangibles aile factor proliferation
- [[concepts/post_publication_decay]] — dört darbe sentez tablosu OC
  factor satır
- [[concepts/winner_loser_identification]] — industry-relative
  within-industry sort paterni; Mohanram G-Score industry-median
  paralel

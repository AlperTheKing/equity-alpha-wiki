# Source Tier List — v2 (Goal-Aligned)

> **Hedef:** S&P 500 ve Nasdaq 100 evrenlerinde, finansal tablo verilerini kullanarak
> yıllık-frekansta o sene en yüksek getiriyi sağlayacak hisseleri seçen sistematik
> bir strateji tasarlamak.
>
> **v1'den fark:** Listeyi "empirical asset pricing literatür haritası"ndan
> "winner-identification, large-cap, annual rebalance" lens'ine çevirdik.
> Bazı paper'lar Tier 2'den 1'e terfi etti, 3 yepyeni paper eklendi.

## Goal lens — neyin önemli olduğu

Bu projenin dört teknik özelliği literatürden ayrışıyor:

1. **Top-of-distribution tahmini** — long-short spread değil, *top-N winner identification*
2. **Yıllık rebalans** — literatürün çoğu aylık, turnover/cost trade-off farklı
3. **Large-cap evren** — anomaliler small-cap'te yoğun, large-cap'te birçoğu zayıf
4. **Nasdaq 100 = tech-heavy growth** — klasik value bozulur, intangibles kritik

---

## TIER 1 — Foundation (~31 paper)

### A. Foundational factor models (4 paper)

1. **Fama-French (1993)** Common Risk Factors — `fama_french_1993_three_factor.pdf`
2. **Fama-French (2015)** Five-Factor Model — `fama_french_2015_five_factor.pdf`
3. **Hou-Xue-Zhang (2015)** Digesting Anomalies / q-factor — `hou_xue_zhang_2015_q_factor.pdf`
4. **Carhart (1997)** Mutual Fund Persistence — `carhart_1997_momentum.pdf`

### B. Winner-identification scores ⭐ **CORE bloğu** (5 paper)

Top-N selection mantığında çalışan paper'lar — projenin kalbi.

5. **Piotroski (2000)** F-Score — `piotroski_2000_f_score.pdf`
6. **Mohanram (2005)** G-Score — `mohanram_2005_g_score.pdf` — **Nasdaq 100 için kritik** (low-B/M/growth evrende)
7. **Li-Mohanram (2019)** Quality + Value combined — `li_mohanram_2019_quality_value.pdf`
8. **Beneish-Lee-Tarpley (2001)** ✚ NEW — `beneish_lee_tarpley_2001_extreme_returns.pdf` — *en doğrudan fit, "extreme returns prediction"*
9. **Hou-Mo-Xue-Zhang (2020) "Security Analysis"** ✚ NEW — `hou_mo_xue_zhang_2020_security_analysis.pdf` — Magic Formula + F-Score + V/P + QMJ q5 ile test edilmiş

### C. Quality, value, profitability (5 paper)

10. **Novy-Marx (2013)** Gross Profitability — `novy_marx_2013_gross_profitability.pdf`
11. **Asness-Frazzini-Pedersen (2019)** QMJ — `asness_frazzini_pedersen_2019_qmj.pdf`
12. **Lakonishok-Shleifer-Vishny (1994)** Contrarian — `lakonishok_shleifer_vishny_1994_contrarian.pdf`
13. **Ball-Gerakos-Linnainmaa-Nikolaev (2016)** Cash-based OP — `ball_gerakos_linnainmaa_nikolaev_2016_accruals_cashflows.pdf`
14. **Frankel-Lee (1998)** V/P — *MANUAL/skipped, dolaylı via Li-Mohanram*

### D. Earnings quality & loser avoidance (3 paper)

15. **Sloan (1996)** Accruals Anomaly — `sloan_1996_accruals_anomaly.pdf`
16. **Cooper-Gulen-Schill (2008)** Asset Growth — `cooper_gulen_schill_2008_asset_growth.pdf`
17. **Beneish (1999)** M-Score — `beneish_1999_m_score.pdf`

### E. Large-cap & implementation ⭐ **NEW BLOCK** (3 paper)

Universe match — S&P 500 / NDX'in large-cap-only doğasına özgü.

18. **Israel-Moskowitz (2013)** ✚ NEW — `israel_moskowitz_2013_shorting_size_time.pdf` — *hangi anomali large-cap-long-only'de hayatta kalıyor*
19. **Fama-French (2008)** Dissecting Anomalies (T2→T1) — *eklenecek* — NYSE breakpoint, micro vs large dissection
20. **Hou-Xue-Zhang (2020)** Replicating Anomalies — `hou_xue_zhang_2020_replicating_anomalies.pdf` — NYSE-breakpoint replication

### F. Tech / intangibles ⭐ **NEW BLOCK — NDX için kritik** (3 paper)

21. **Lev-Sougiannis (1996)** R&D Capitalization (T2→T1) — *eklenecek*
22. **Peters-Taylor (2017)** Intangible Capital (T2→T1) — *eklenecek*
23. **Lev-Srivastava (2020)** Why Value Failed Post-2010 (T2→T1) — *eklenecek*

### G. Replication, decay, multiple testing (3 paper)

24. **McLean-Pontiff (2016)** Does Research Destroy — `mclean_pontiff_2016_does_research_destroy.pdf`
25. **Harvey-Liu-Zhu (2016)** Multiple Testing — `harvey_liu_zhu_2016_cross_section.pdf`
26. **Bailey-Lopez de Prado (2014)** Deflated Sharpe — `bailey_lopezdeprado_2014_deflated_sharpe.pdf`

### H. ML & high-dim (3 paper)

27. **Gu-Kelly-Xiu (2020)** ML Asset Pricing — `gu_kelly_xiu_2020_ml_asset_pricing.pdf`
28. **Feng-Giglio-Xiu (2020)** Factor Zoo — `feng_giglio_xiu_2020_factor_zoo.pdf`
29. **Kozak-Nagel-Santosh (2020)** Shrinking Cross-Section — `kozak_nagel_santosh_2020_shrinking_cross_section.pdf`

### I. Synthesis (2 paper)

30. **Stambaugh-Yuan (2017)** Mispricing Factors — `stambaugh_yuan_2017_mispricing_factors.pdf`
31. **Green-Hand-Zhang (2017)** Independent Characteristics — `green_hand_zhang_2017_characteristics_independent.pdf`

---

## TIER 2 — Genişletme (seçici, ~10 paper)

Tier 2'den 1'e terfi olanlar (Peters-Taylor, Lev-Srivastava, Lev-Sougiannis, FF 2008) hariç:

- Eisfeldt-Papanikolaou (2013) Organization Capital
- Hirshleifer-Hsu-Li (2018) Innovative Originality
- Altman (1968) Z-Score / Ohlson (1980) O-Score / Campbell-Hilscher-Szilagyi (2008) Distress
- Penman-Zhang (2002) Conservatism
- Richardson-Sloan-Soliman-Tuna (2005) Accrual Reliability
- Hirshleifer-Hou-Teoh-Zhang (2004) NOA
- **Novy-Marx-Velikov (2016) Trading Costs of Anomalies** — *yıllık rebalans cost analizi için kritik*
- Chordia-Goyal-Saretto (2020) Anomalies and False Rejections
- Chen-Zimmermann Open Asset Pricing — replikasyon database

> _Detailed legacy Tier 2 inventory (B/C/D/E sub-bölüm tabloları + cycle anotasyonları) is preserved in the appendix for traceability — bkz. "Appendix — Legacy Detailed Tier 2 Inventory (Cycle 1-41)" aşağıda._

## TIER 3 — On-demand (~12 paper + 3 kitap)

Belirli soru çıktığında. Beneish-Lee-Nichols 2013 (M-Score expected returns), DHS behavioral, Frazzini-Israel-Moskowitz 2018 trading costs, Greenblatt/Gray-Vogel/O'Shaughnessy kitapları.

---

## v1 → v2 değişiklik özeti

| Hareket | Sayı | Detay |
|---|---|---|
| Tier 2'den Tier 1'e terfi | 4 | FF 2008, Lev-Sougiannis, Peters-Taylor, Lev-Srivastava |
| Yepyeni Tier 1 ekleme | 3 | BLT 2001, Israel-Moskowitz, Hou-Mo-Xue-Zhang Security Analysis |
| Tier 1 yeniden organize | — | B (winner-id) ve E (large-cap), F (tech/intangibles) blokları goal lens'ini açık eder |
| Tier 1 toplam: 25 → 31 paper | +6 | Goal alignment için makul artış |

## Önerilen ingest sırası

Goal'e en yakın olandan uzağa doğru:

**Hafta 1-2 — B bloğu (winner-identification CORE):**
Piotroski → Mohanram → Li-Mohanram → BLT 2001 → Hou-Mo-Xue-Zhang Security Analysis

**Hafta 3 — E bloğu (large-cap reality):**
Israel-Moskowitz → FF 2008 → HXZ 2020 Replicating

**Hafta 4 — F bloğu (tech/NDX):**
Lev-Sougiannis → Peters-Taylor → Lev-Srivastava

**Hafta 5 — C bloğu (quality/value vocabulary):**
Novy-Marx → QMJ → LSV → Ball-Gerakos

**Hafta 6 — D bloğu (loser avoidance):**
Sloan → CGS → Beneish

**Hafta 7 — A + G blokları (foundation + epistemics):**
FF 1993 → FF 2015 → HXZ 2015 → Carhart → MLP → HLZ → Bailey-LdP

**Hafta 8 — H + I (high-dim + synthesis):**
GKX → FGX → KNS → SY → GHZ

8 hafta sonunda Faz 2'ye geçiş.

---

## Bu reorganize'in pratik yansımaları

Faz 1 ingest'inde bu farkın somut etkileri olacak:

- **B bloğunun core olması:** F-Score/G-Score/BLT 2001 başlangıçta ingest edilince, sonraki paper'lar bunlara `[[link]]`'lerle bağlanır. Wiki'nin merkez gravitasyonu *winner identification* olur, generic factor zoo değil.

- **E ve F bloklarının ayrı çıkarılması:** Large-cap reality check ve NDX-tech intangibles, *kavram sayfası* (`concepts/large_cap_anomaly_attenuation.md`, `concepts/intangibles_adjusted_book.md`) olarak ortaya çıkar — strateji tasarımında bunlar "tasarım kararı" olarak görünür.

- **Faz 3'te iki ayrı strateji:** S&P 500 stratejisi B+C+D blokları üzerine inşa edilirken, Nasdaq 100 stratejisi B+F blokları üzerine inşa edilir. Aynı wiki'den iki ayrı strateji.

---

## Appendix — Legacy Detailed Tier 2 Inventory (Cycle 1-41)

> 📝 **Origin**: Bu appendix, Cycle 1-41 boyunca aktif olarak bakımı yapılan
> orijinal Tier 2 detaylı tablo yapısının korunmuş halidir (claude branch'in
> Cycle 41 sonu state'i). v2 Goal-Aligned reorganizasyonu sonrası ana TIER 2
> bölümü tek-bullet özet'e indirgendi; bu appendix detaylı paper-level URL
> kayıtları + Cycle anotasyonları için **traceability** amaçlı tutulur.
>
> Bu appendix **çift sayım yaratmaz**: ana TIER 2 listesindeki paper'lar
> (Eisfeldt-Papanikolaou, Hirshleifer-Hsu-Li vb.) burada yinelenmedi; sadece
> v2 reorganizasyonunda bullet'a sıkıştırılan B/C/D/E sub-bölümlerin
> ayrıntıları korundu.

### B. Distress, failure, conservatism

| # | Paper | URL | Niye gerekli |
|---|---|---|---|
| 31 | **Altman (1968)** "Financial Ratios, Discriminant Analysis and the Prediction of Corporate Bankruptcy", JF (Z-Score) | https://onlinelibrary.wiley.com/doi/10.1111/j.1540-6261.1968.tb00843.x | [paywall — geniş CC mevcut] |
| 32 | **Ohlson (1980)** "Financial Ratios and the Probabilistic Prediction of Bankruptcy", JAR (O-Score) | https://www.jstor.org/stable/2490395 | [JSTOR] |
| 33 | **Campbell, Hilscher, Szilagyi (2008)** "In Search of Distress Risk", JF | https://www.nber.org/papers/w12362 | [NBER] |
| 34 | **Penman-Zhang (2002)** "Accounting Conservatism, the Quality of Earnings, and Stock Returns", AR | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=201228 | [SSRN] |

### C. Investment / accruals deeper

| # | Paper | URL | Niye gerekli |
|---|---|---|---|
| 35 | **Richardson, Sloan, Soliman, Tuna (2005)** "Accrual Reliability, Earnings Persistence and Stock Prices", JAE | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=521062 | [SSRN] |
| 36 | **Hirshleifer, Hou, Teoh, Zhang (2004)** "Do Investors Overvalue Firms with Bloated Balance Sheets?", JAE (NOA) | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=519843 | [SSRN] |
| 37 | **Fairfield, Whisenant, Yohn (2003)** "Accrued Earnings and Growth: Implications for Future Profitability and Market Mispricing", AR | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=297880 | [SSRN] |
| 38 | **Titman, Wei, Xie (2004)** "Capital Investments and Stock Returns", JFQA | https://www.cambridge.org/core/journals/journal-of-financial-and-quantitative-analysis/article/abs/capital-investments-and-stock-returns/ | [paywall] |

### D. Implementation / methodology

| # | Paper | URL | Niye gerekli |
|---|---|---|---|
| 39 | **Novy-Marx, Velikov (2016)** "A Taxonomy of Anomalies and Their Trading Costs", RFS | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2298608 | [SSRN] — yıllık rebalans için cost analizi |
| 40 | **Chordia, Goyal, Saretto (2020)** "Anomalies and False Rejections", RFS | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3137998 | [SSRN] |
| 41 | **Chen-Zimmermann (2022)** "Open Source Cross-Sectional Asset Pricing", CFR | https://www.openassetpricing.com/ | [author/data] — replikasyon database; **Cycle 29 ✓ data portal pointer** [[methodology/data_sources]] §1 (tam ingest gerekmez veri portalı; pure replication ~100% reproducible JKP [s.1 fn 1]) |
| 42 | **Fama-French (2008)** "Dissecting Anomalies", JF | https://onlinelibrary.wiley.com/doi/10.1111/j.1540-6261.2008.01371.x | [paywall→author site] — *not: v2 reorganizasyonunda Tier 2'den Tier 1 E bloğuna terfi etti; appendix'te traceability için tutuldu* |

### E. ML extensions

| # | Paper | URL | Niye gerekli |
|---|---|---|---|
| 43 | **Avramov, Cheng, Metzker (2023)** "Machine Learning vs. Economic Restrictions: Evidence from Stock Return Predictability", MS | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3450322 | [SSRN] — ML imza kalitesi sorgulaması |
| 44 | **Jensen, Kelly, Pedersen (2023)** "Is There a Replication Crisis in Finance?", JF | https://www.nber.org/papers/w28432 | [NBER] |
| 45 | **Freyberger, Neuhierl, Weber (2020)** "Dissecting Characteristics Nonparametrically", RFS | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2710148 | [SSRN] |

**Legacy Tier 2 toplam (appendix kapsam): 20 paper.** Bu sayı v1 schema'sındaki (Cycle 1-41) Tier 2 toplamıdır; v2 Goal-Aligned reorganizasyonu sonrası ana TIER 2 sadeleştirildi (yukarıda ~10 bullet) + 4 paper Tier 1'e terfi etti (FF 2008 + Lev-Sougiannis + Peters-Taylor + Lev-Srivastava).

### Cycle Anotasyonları (Highlight)

- **Chen-Zimmermann (2022)** — Cycle 29 ✓ data portal pointer; tam ingest gerekmez (veri portalı, paper formatı değil); pure replication ~%100 reproducible (JKP 2023 [s.1 fn 1]); [[methodology/data_sources]] §1 anchor.
- **Jensen-Kelly-Pedersen (2023)** — Cycle 27 ingested; D bloğu epistemik omurga statistical bacağı 3. paper; 3. contradictions entry (HXZ ↔ JKP); 13 theme cluster + tangency portfolio framework.
- **Fama-French (2008)** — Cycle 37 ingested; v2'de Tier 1 E bloğuna terfi (Q14 RMW/CMA large-cap-only direct test ANCHOR); appendix'te traceability için tutuldu.
- **Avramov-Cheng-Metzker (2023)** — yaşayan-proje aday liste; post-Faz 3 seçici ingest (handoff_post_faz3_001 §3.3).

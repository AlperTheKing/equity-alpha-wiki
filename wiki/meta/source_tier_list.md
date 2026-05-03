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

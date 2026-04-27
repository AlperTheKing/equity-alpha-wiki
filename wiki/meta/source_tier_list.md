# Source Tier List

> Empirical asset pricing literatür için katmanlı okuma listesi.
> Hedef: S&P 500 ve Nasdaq 100 evrenlerinde fundamental verilerle yıllık-frekans
> stock selection stratejisi tasarlamak.
>
> **Tüm linkler doğrulandı (web search, 2026-04-27).** Her satırda **stable URL** var:
> SSRN abstract page (preprint indirme), NBER WP, yazar self-archive veya
> resmi dergi sayfası. Paywalled olanlar için preprint linki tercih edildi.

## Nasıl kullanılır

1. **Tier 1**'i tamamen ingest et (sırayla aşağıdan). ~25 paper. Wiki'nin omurgası.
2. **Tier 2**'yi `data_gaps.md`'deki ihtiyaca göre seçici ingest et.
3. **Tier 3** sadece spesifik bir soru çıkarsa.
4. Her satırda **download stratejisi** belirtildi:
   - `[SSRN]` → SSRN abstract sayfasından PDF indir (ücretsiz, login gerekebilir)
   - `[NBER]` → nber.org WP, doğrudan PDF
   - `[author]` → yazarın kişisel sitesi (paywall yok)
   - `[OA]` → açık erişim dergi
   - `[paywall→preprint]` → dergi paywalled, preprint linkten al

---

## TIER 1 — Foundation (zorunlu, ~25 paper)

Bu listenin tamamı ingest edilmeden Faz 2'ye geçilmez. Wiki'nin minimum
yeterliliği için gerekli.

### A. Foundational factor models (4 paper)

| # | Paper | URL | Strateji |
|---|---|---|---|
| 1 | **Fama-French (1993)** "Common Risk Factors in the Returns on Stocks and Bonds", JFE | https://rasmuseconomics.com/Risk_factors.pdf | [author/repo] |
| 2 | **Fama-French (2015)** "A Five-Factor Asset Pricing Model", JFE | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2287202 | [SSRN preprint] |
| 3 | **Hou, Xue, Zhang (2015)** "Digesting Anomalies: An Investment Approach", RFS | https://www.nber.org/papers/w18435 | [NBER WP] |
| 4 | **Carhart (1997)** "On Persistence in Mutual Fund Performance", JF (momentum factor) | https://onlinelibrary.wiley.com/doi/10.1111/j.1540-6261.1997.tb03808.x | [paywall→preprint](https://faculty.fuqua.duke.edu/~charvey/Teaching/BA453_2006/Mutual_Fund_Performance.pdf) |

### B. Value, profitability, quality (5 paper)

| # | Paper | URL | Strateji |
|---|---|---|---|
| 5 | **Novy-Marx (2013)** "The Other Side of Value: The Gross Profitability Premium", JFE | https://mysimon.rochester.edu/novy-marx/research/OSoV.pdf | [author] |
| 6 | **Asness, Frazzini, Pedersen (2019)** "Quality Minus Junk", RAS | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2312432 | [SSRN] |
| 7 | **Lakonishok, Shleifer, Vishny (1994)** "Contrarian Investment, Extrapolation, and Risk", JF | https://scholar.harvard.edu/files/shleifer/files/contrarianinvestment.pdf | [author] |
| 8 | **Frankel-Lee (1998)** "Accounting Valuation, Market Expectation, and Cross-Sectional Stock Returns", JAE (V/P ratio) | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=6528 | [SSRN] |
| 9 | **Ball, Gerakos, Linnainmaa, Nikolaev (2016)** "Accruals, Cash Flows, and Operating Profitability in the Cross Section of Stock Returns", JFE | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2484054 | [SSRN] |

### C. Composite fundamental scores (3 paper)

| # | Paper | URL | Strateji |
|---|---|---|---|
| 10 | **Piotroski (2000)** "Value Investing: Use of Historical Financial Statement Information...", JAR (F-Score) | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=249455 | [SSRN] |
| 11 | **Mohanram (2005)** "Separating Winners from Losers Among Low Book-to-Market Stocks Using Financial Statement Analysis", RAST (G-Score) | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=403180 | [SSRN] — **Nasdaq 100 için kritik** |
| 12 | **Li-Mohanram (2019)** "Fundamental Analysis: Combining the Search for Quality with the Search for Value", CAR | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3129156 | [SSRN] |

### D. Earnings quality / accruals / investment (3 paper)

| # | Paper | URL | Strateji |
|---|---|---|---|
| 13 | **Sloan (1996)** "Do Stock Prices Fully Reflect Information in Accruals and Cash Flows About Future Earnings?", AR | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2598 | [SSRN] |
| 14 | **Cooper, Gulen, Schill (2008)** "Asset Growth and the Cross-Section of Stock Returns", JF | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1335524 | [SSRN preprint] |
| 15 | **Beneish (1999)** "The Detection of Earnings Manipulation", FAJ (M-Score) | https://www.researchgate.net/publication/252059255_The_Detection_of_Earnings_Manipulation | [author/RG] |

### E. Replication, decay, multiple testing (4 paper) — kritik epistemik altyapı

| # | Paper | URL | Strateji |
|---|---|---|---|
| 16 | **McLean-Pontiff (2016)** "Does Academic Research Destroy Stock Return Predictability?", JF | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2156623 | [SSRN] |
| 17 | **Harvey, Liu, Zhu (2016)** "...and the Cross-Section of Expected Returns", RFS | https://www.nber.org/papers/w20592 | [NBER] |
| 18 | **Hou, Xue, Zhang (2020)** "Replicating Anomalies", RFS | https://www.nber.org/papers/w23394 | [NBER] |
| 19 | **Bailey-López de Prado (2014)** "The Deflated Sharpe Ratio", JPM | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2460551 | [SSRN] |

### F. ML / high-dimensional asset pricing (3 paper)

| # | Paper | URL | Strateji |
|---|---|---|---|
| 20 | **Gu, Kelly, Xiu (2020)** "Empirical Asset Pricing via Machine Learning", RFS | https://www.nber.org/papers/w25398 | [NBER] |
| 21 | **Feng, Giglio, Xiu (2020)** "Taming the Factor Zoo: A Test of New Factors", JF | https://www.nber.org/papers/w25481 | [NBER] |
| 22 | **Kozak, Nagel, Santosh (2020)** "Shrinking the Cross-Section", JFE | https://www.nber.org/papers/w24070 | [NBER] |

### G. Survey / synthesis / integration (3 paper)

| # | Paper | URL | Strateji |
|---|---|---|---|
| 23 | **Stambaugh-Yuan (2017)** "Mispricing Factors", RFS | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2626701 | [SSRN] |
| 24 | **Green, Hand, Zhang (2017)** "The Characteristics that Provide Independent Information about Average U.S. Monthly Stock Returns", RFS | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2262374 | [SSRN] |
| 25 | **Cochrane (2011)** "Presidential Address: Discount Rates", JF (factor zoo introductory framing) | https://www.nber.org/papers/w16972 | [NBER] |

**Tier 1 toplam: 25 paper.** Hedef ingest süresi: 8-12 hafta (haftada 2-3 paper).

---

## TIER 2 — Genişletme (~20 paper, seçici)

`data_gaps.md` ve `open_questions.md` boşluklarını adresleyen ek kaynaklar.
Tier 1 bittikten sonra hangi soruları kapatmadığına bakıp seçici ingest et.

### A. Intangibles, R&D, growth-side (Nasdaq 100 için kritik)

| # | Paper | URL | Niye gerekli |
|---|---|---|---|
| 26 | **Lev-Sougiannis (1996)** "The Capitalization, Amortization, and Value-Relevance of R&D", JAE | https://www.sciencedirect.com/science/article/abs/pii/0165410195004106 | [paywall→preprint via UIUC] |
| 27 | **Peters-Taylor (2017)** "Intangible Capital and the Investment-q Relation", JFE | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2405691 | [SSRN] — Nasdaq tech için B/M düzeltmesi |
| 28 | **Eisfeldt-Papanikolaou (2013)** "Organization Capital and the Cross-Section of Expected Returns", JF | https://www.nber.org/papers/w17904 | [NBER] |
| 29 | **Hirshleifer, Hsu, Li (2018)** "Innovative Originality, Profitability, and Stock Returns", RFS | https://www.nber.org/papers/w23432 | [NBER] |
| 30 | **Lev-Srivastava (2020)** "Explaining the Recent Failure of Value Investing" | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3442539 | [SSRN] — Post-2010 value collapse |

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
| 41 | **Chen-Zimmermann (2022)** "Open Source Cross-Sectional Asset Pricing", CFR | https://www.openassetpricing.com/ | [author/data] — replikasyon database |
| 42 | **Fama-French (2008)** "Dissecting Anomalies", JF | https://onlinelibrary.wiley.com/doi/10.1111/j.1540-6261.2008.01371.x | [paywall→author site] |

### E. ML extensions

| # | Paper | URL | Niye gerekli |
|---|---|---|---|
| 43 | **Avramov, Cheng, Metzker (2023)** "Machine Learning vs. Economic Restrictions: Evidence from Stock Return Predictability", MS | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3450322 | [SSRN] — ML imza kalitesi sorgulaması |
| 44 | **Jensen, Kelly, Pedersen (2023)** "Is There a Replication Crisis in Finance?", JF | https://www.nber.org/papers/w28432 | [NBER] |
| 45 | **Freyberger, Neuhierl, Weber (2020)** "Dissecting Characteristics Nonparametrically", RFS | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2710148 | [SSRN] |

**Tier 2 toplam: 20 paper.**

---

## TIER 3 — Özel-konu (~15 paper, on-demand)

Spesifik bir strateji kararı / open_question için seçici. Tüm Tier 3 ingest etmek gereksiz.

### A. Forensic / earnings manipulation deepening

| # | Paper | URL |
|---|---|---|
| 46 | Beneish, Lee, Nichols (2013) "Earnings Manipulation and Expected Returns", FAJ | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2241717 |
| 47 | Dechow, Ge, Larson, Sloan (2011) "Predicting Material Accounting Misstatements", CAR (F-Score forensic) | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=997483 |

### B. Specific anomalies

| # | Paper | URL |
|---|---|---|
| 48 | Daniel-Titman (2006) "Market Reactions to Tangible and Intangible Information", JF | https://www0.gsb.columbia.edu/faculty/kdaniel/papers/published/intangible.pdf |
| 49 | Pontiff-Woodgate (2008) "Share Issuance and Cross-Sectional Returns", JF | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=986547 |
| 50 | Daniel-Hirshleifer-Sun (2020) "Short- and Long-Horizon Behavioral Factors", RFS | https://www.nber.org/papers/w24048 |
| 51 | Frazzini-Pedersen (2014) "Betting Against Beta", JFE | https://www.nber.org/papers/w16601 |

### C. Implementation deepening

| # | Paper | URL |
|---|---|---|
| 52 | Frazzini, Israel, Moskowitz (2018) "Trading Costs", AQR | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3229719 |
| 53 | Asness-Frazzini (2013) "The Devil in HML's Details", JPM | https://www.aqr.com/Insights/Research/Journal-Article/The-Devil-in-HMLs-Details |
| 54 | Bryzgalova, Pelger, Zhu (2024) "Forest Through the Trees: Building Cross-Sections of Stock Returns", JF | https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3493458 |

### D. Practitioner / industry whitepapers

| # | Paper | URL |
|---|---|---|
| 55 | AQR (Asness et al.) "Quality Minus Junk: Factors Monthly" + data | https://www.aqr.com/Insights/Datasets/Quality-Minus-Junk-Factors-Monthly |
| 56 | Research Affiliates "Smart Beta" papers (multiple) | https://www.researchaffiliates.com/research |
| 57 | Greenblatt (2006) *The Little Book That Beats the Market* — Magic Formula | (kitap, ISBN 0-471-73306-7) — sadece kavramsal referans |
| 58 | Gray-Vogel (2012) *Quantitative Value* (kitap) — composite implementation | (kitap, ISBN 978-1-118-32807-7) |
| 59 | O'Shaughnessy (2011) *What Works on Wall Street* (kitap, 4. baskı) | (kitap, ISBN 978-0-07-162576-6) |

### E. Macro / regime / Nasdaq-specific

| # | Paper | URL |
|---|---|---|
| 60 | Daniel-Moskowitz (2016) "Momentum Crashes", JFE | https://www0.gsb.columbia.edu/faculty/kdaniel/papers/published/MomCrashes.pdf |
| 61 | Asness, Liew, Pedersen, Thapar (2020) "Deep Value", JPM | https://www.aqr.com/Insights/Research/White-Papers/Deep-Value |

**Tier 3 toplam: 16 paper + 3 kitap.**

---

## Toplam ve sıra

- **Tier 1: 25 paper** — Foundation. Hepsi ingest edilir.
- **Tier 2: 20 paper** — Genişletme. ~10-12'si seçici ingest edilir.
- **Tier 3: 16 paper + 3 kitap** — On-demand. ~3-5'i ingest edilir.

**Pratik hedef: ~40-45 paper ingest, ~3 kitaba kavramsal referans.**

## Önerilen ingest sırası (Tier 1 içinde)

Aşağıdaki sıra wikinin **anlamlı olarak** kümülatif olmasını sağlar
(önceki bilgi sonrakini aydınlatır):

1. **Hafta 1-2:** Fama-French 1993 → Fama-French 2015 → Carhart 1997
   *(temel faktör modeli vocabulary'i kurulur)*
2. **Hafta 3:** Cochrane 2011 (factor zoo introductory) → Harvey-Liu-Zhu 2016 → McLean-Pontiff 2016
   *(epistemik çerçeve: ne kadarına inanmalıyız?)*
3. **Hafta 4-5:** Piotroski 2000 → Mohanram 2005 → Li-Mohanram 2019
   *(value vs. growth fundamental scoring — projenin kalbi)*
4. **Hafta 6:** Sloan 1996 → Cooper-Gulen-Schill 2008
   *(accruals, asset growth — earnings quality temel)*
5. **Hafta 7-8:** Novy-Marx 2013 → Asness-Frazzini-Pedersen QMJ → Lakonishok-Shleifer-Vishny 1994 → Frankel-Lee 1998 → Ball-Gerakos-Linnainmaa-Nikolaev 2016
   *(value/quality/profitability ekosistemini tamamla)*
6. **Hafta 9:** Hou-Xue-Zhang 2015 → Hou-Xue-Zhang 2020 (Replicating)
   *(q-factor model + replikasyon)*
7. **Hafta 10:** Beneish 1999 → Bailey-López de Prado 2014
   *(forensic + DSR — strateji defansı)*
8. **Hafta 11-12:** Gu-Kelly-Xiu 2020 → Feng-Giglio-Xiu 2020 → Kozak-Nagel-Santosh 2020 → Stambaugh-Yuan 2017 → Green-Hand-Zhang 2017
   *(ML + high-dim sentez — Faz 2'ye geçiş eşiği)*

Bu sırayla bittiğinde wiki Faz 2'ye hazırdır.

## Notlar

- **Paywall'lar:** Birkaç paper'ın WP/preprint versiyonu bulunamadıysa, kullanıcı
  kurum erişiminden alacak. Bu satırlar `[paywall]` olarak işaretlendi.
- **Kitaplar (Greenblatt, Gray-Vogel, O'Shaughnessy):** Tam ingest edilmez,
  ilgili bölümler PDF/note olarak `raw/books/` altına alınır, kavramsal
  referans olarak kullanılır.
- **Veri kaynakları:** Chen-Zimmermann Open Asset Pricing (Tier 2 #41) bir
  paper değil bir **veri portalı** — replikasyon için altın standart.
  Wiki'ye `wiki/methodology/data_sources.md` olarak ayrı sayfa açılmalı.
- **Türkçe notlar:** Wiki Türkçe yazılır, paper isimleri/dergiler İngilizce
  kalır (CLAUDE.md kural 6).

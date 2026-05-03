# equity-alpha-wiki

> Designing a systematic stock-selection strategy for the S&P 500 and Nasdaq 100 universes — using 10-K/10-Q financial-statement data on an annual rebalance — and grounding that design in a structured, cross-referenced, cumulative synthesis of the academic literature. The wiki is Karpathy's [`llm-wiki`](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) pattern applied to empirical asset pricing.

## 1. Why this project?

Systematic factor investing has exploded in the academic literature since the 1990s. From Fama-French's three-factor model (1993), Carhart momentum (1997), Sloan accruals anomaly (1996), Piotroski F-Score (2000), Mohanram G-Score (2005), Novy-Marx gross profitability (2013), Asness-Frazzini-Pedersen QMJ (2019), Hou-Xue-Zhang q-factor model (2015/2020), Stambaugh-Yuan mispricing factors (2017), to Jensen-Kelly-Pedersen Bayesian replication (2023) — hundreds of papers have constructed, piece by piece, an answer to the question "which characteristics explain expected returns?". But this same literature has also confronted two devastating findings: McLean-Pontiff (2016) showed that 82 anomalies suffer roughly 35% post-publication decay; Harvey-Liu-Zhu (2016) recommended a `|t| > 3.0` threshold (after multiple-testing correction) on a census of 316 factors; Hou-Xue-Zhang (2020) found that only ~10% of 447 anomalies remain significant under NYSE-VW + microcap-cleaned replication.

In this contradictory landscape, **a practical question arises for an individual investor**: in large-cap, low-friction universes such as the S&P 500 and Nasdaq 100, with annual rebalancing and using only publicly available 10-K/10-Q data, can a strategy still produce a positive edge today? If yes — which factors, with what weights, under what methodological filters? If no — for what epistemic reason?

Answering this question seriously requires not memorizing the literature but **synthesizing** it. For an individual reader, holding 50+ papers in working memory, tracking conflicting evidence, and following the evolution of methodological preferences across decades is practically impossible. Here, large language models (LLMs) used as **an external, structured memory layer** offer a natural solution — provided the LLM is rigorously prevented from "generating its own claims" and provided every output remains **explicitly bound to sources**.

This repo is a concrete experiment in that discipline. Andrej Karpathy's `llm-wiki` pattern — immutable sources in `raw/`, LLM-written synthesis in `wiki/`, schema rules in `CLAUDE.md` — is adapted to empirical asset pricing. After 41 ingest cycles the wiki currently contains **28 papers + 20 factor entities + 17 concept hubs + 5 strategy specs + 3 methodology pages + 10 meta pages = ~88 markdown files**; every numerical claim is backed by a paper-page citation or `[[wikilink]]`, conflicting evidence is explicitly recorded in `meta/contradictions.md`, and the wiki has reached a state in which it functions as a "neutral but opinionated" knowledge base.

## 2. Three-layer architecture (Karpathy `llm-wiki` pattern)

```
equity-alpha-wiki/
├── CLAUDE.md              ← Schema. Operating rules (§1-12). Audit protocol.
├── raw/                   ← Immutable sources. LLM does not write; user adds.
│   ├── papers/            ← Academic paper PDFs / TXTs
│   ├── books/             ← Book chapters
│   └── industry/          ← AQR / Research Affiliates / MSCI whitepapers
├── wiki/                  ← LLM-written, LLM-maintained markdown
│   ├── index.md           ← Catalog of all pages
│   ├── log.md             ← Append-only chronological log
│   ├── papers/      (28)  ← One summary page per ingested source
│   ├── factors/     (20)  ← Signal/factor entity pages
│   ├── concepts/    (17)  ← Concept hubs (post_publication_decay, factor_zoo, …)
│   ├── comparisons/  (1)
│   ├── strategies/   (5)  ← v0/v1 historic + sp500_v1 + nasdaq100_v1 + known_weaknesses
│   ├── methodology/  (3)  ← backtest_spec + data_sources + backtest_implementation_plan
│   ├── backtests/         ← P123 backtest reports (CLAUDE.md §12.2; first report not yet produced)
│   └── meta/        (10)  ← MoC, open_questions, contradictions, data_gaps, 6 handoffs, executive_summary
└── README.md              ← This file
```

**The contract between the three layers is not just a directory structure but an epistemic commitment**:

`raw/` is **immutable**. The user places papers there; Claude reads but never writes. This is the physical guarantee of the principle "LLM hallucinations must not leak into the source". When an assertion is challenged, the fallback point is the original PDF in `raw/`.

`wiki/` is **Claude's domain**. All writing, updating, cross-reference maintenance, lint, audit, and consolidation passes are Claude's responsibility. The user holds the **auditor** role in this layer, not the **operator** role — does not edit page contents directly; instead steers Claude with trigger phrases ("TEMIZ devam", "KÜÇÜK fix devam", "YAPISAL fix", "ABORT" — see CLAUDE.md §11.6, retained in their original Turkish form).

`CLAUDE.md` is **co-evolved**. The schema has been updated repeatedly across 41 cycles: §11 self-audit was formalized around Cycle 9, §11.5 4-cycle consecutive consolidation pass was added in Cycle 8, §7 certificate types were tightened with three separate schema_updates between Cycle 20 and Cycle 31, and §12 post-Faz 3 living-project maintenance protocol was added in Cycle 42. Every schema change is recorded under the `schema_update` category in `wiki/log.md`.

This triad — immutable sources + LLM-maintained synthesis + co-evolved schema — enables an individual researcher to build cumulative knowledge while diving deep into a field.

## 3. The thesis from the literature: a three-leg epistemic backbone and a four-blow framework

The wiki's backbone is **block D** (Cycles 11-13). Its thesis: of the hundreds of anomalies reported in the academic literature, only a small subset survives **all three** orthogonal mechanisms.

**Leg one — behavioral decay**: McLean-Pontiff (2016) split 82 anomalies into pre-publication and post-publication regimes; aggregate decay was measured at roughly 35% (sig 1%). The more critical finding is that **decay is more aggressive in large, liquid firms** — under the limited arbitrage hypothesis this is a double blow for large-cap universes (in-sample weakness + aggressive post-publication attenuation).

**Leg two — statistical false discovery rate**: Harvey-Liu-Zhu (2016) conducted a literature census of 316 factors and recommended, after multiple-testing correction (Bonferroni / Holm / BHY), a threshold of `|t| > 3.0` (not the conventional 1.96). Under this threshold the classical SMB factor is never significant — this constitutes the full answer to Q11 (SMB post-1991 + large-cap relevance).

**Leg three — empirical replication**: Hou-Xue-Zhang (2020) "Replicating Anomalies" replicated 447 anomalies under NYSE-VW (microcap-cleaned). At the conventional 5% level, 64% of anomalies became insignificant; under the q-factor model lens, net **10% remained significant** (46/447). Because McLean-Pontiff's equal-weight + all-stocks methodology artificially inflates microcaps (which are >60% of stocks but only ~3% of market cap), HXZ's cleaner NYSE-VW number is the wiki's baseline.

The **complementary** nature of these three legs is the wiki's central epistemic claim: behavioral decay (investor behavior), statistical FDR (data-snooping bias), and empirical replication (methodology choice) are independent mechanisms; if all three converge on the same conclusion ("most of the factor zoo is inadequate"), that conclusion does not depend on any single source. This is the core of Faz 1's epistemic-completeness criterion (CLAUDE.md §7).

The fourth paper in block D — Bailey-López de Prado (2014) Deflated Sharpe Ratio — proposed adding a fifth leg (backtest overfitting), but the **frame-expansion discipline meta-note** test applied in Cycle 14 failed: DSR is not an orthogonal mechanism (it is a special case of the HLZ Sharpe application) and does not bear the structural weight to merit its own aggregate table; the framework was frozen at four blows. This freezing matters — without proliferation control, the concept list grows and aggregate decisions get lost.

The **four-blow framework** (Cycles 13-14 synthesis table) is the wiki's operational filter: for a factor to enter a strategy spec, it must (1) be significant in-sample in the large-cap universe, (2) survive post-publication decay, (3) survive multiple-testing correction, and (4) be replication-robust. In Cycle 27, Jensen-Kelly-Pedersen (2023) Bayesian Empirical Bayes hierarchical methodology produced a **dramatic counter-finding**: 85% replication on US data, 84% globally. That is a roughly 50-percentage-point gap from HXZ's 35%. The wiki, rather than hiding this contradiction, documents it explicitly in `meta/contradictions.md` §3 and labels the resolution as **scope-dependent methodology disagreement**: HXZ uses pure VW + 1-month + frequentist OLS, JKP uses capped VW (NYSE 80th-percentile winsorize) + 1-month + Bayesian framework + global. The wiki sits on the conservative side (HXZ + MP figures as baseline) but acknowledges JKP as the anti-conservative upper-bound reference; the sensitivity range is roughly 2x.

## 4. Four methodology chains

The most cumulative output of the wiki's theoretical accumulation is its tracing of **four parallel methodology chains** in the literature, and its labeling of every composite-score component with a **dual origin** (paper-specific source + literature-line ancestor). This pattern was born in Cycle 9 with the first link of the Sloan chain, and was applied to all four chains by Cycles 35-39.

| Chain | Papers × years | Origin → modern link |
|-------|----------------|----------------------|
| **Sloan chain** (mispricing/accruals) | 4 papers × 23 years | Sloan 1996 → Piotroski 2000 F_ACCRUAL → Mohanram 2005 G3 → Asness 2019 QMJ ACC |
| **Profitability chain** | 4 papers × 7 years | Novy-Marx 2013 GP/A → FF15 RMW Ope → Asness QMJ GPOA → Ball-GLN 2016 Cop |
| **F-block intangibles 4-layer** | 4 papers × 24 years | Lev-Sougiannis 1996 (Knowledge) + Eisfeldt-Papanikolaou 2013 (Organization) + Peters-Taylor 2017 (Total) + Lev-Srivastava 2020 (Application) |
| **Composite mispricing scoring** | 4 papers × 17 years | Piotroski F-Score → Mohanram G-Score → Stambaugh-Yuan 2017 MGMT/PERF → JKP 2023 13 theme cluster |

The **Sloan chain** is the most epistemically durable arch in the wiki: from 1996 to 2019, the hypothesis that the gap between earnings persistence and cash-flow support is a mispricing signal was independently confirmed across three separate papers in different universes. Piotroski's F_ACCRUAL component (CFO > NI) is the binary version of Sloan's original accrual measure; Mohanram's G3 is the same logic applied to the low-BM universe; Asness's QMJ Profitability ACC measure is the chain's fourth link. Within the HXZ 2020 four-blow framework, Sloan operating accruals (Oa) is one of four **4/4 surviving** factor candidates (q-factor alpha −0.54%/month sig).

The **Profitability chain** parallels the Sloan chain but is shorter: Novy-Marx (2013) introduced the GP/A = (REVT − COGS) / AT formulation as "the other side of value" — because gross profitability and B/M are negatively correlated (Spearman −0.18), their combination is stronger than either alone (50/50 mix Sharpe 0.85, 2.5x the market's 0.34). FF15 RMW (Robust Minus Weak) operating profitability is this chain's in-model counterpart; Asness's QMJ Profitability dimension provides a six-measure composite; Ball-GLN (2016) "Cash-Based Operating Profitability" is the chain's fourth link — Cop = Ope − ΔWC strips out working-capital accruals. This positions Sloan's fixation hypothesis as **complementary, not refuted**: Cop already subsumes accruals (4F+Cop tangency Sharpe 1.67 ⭐, beating the 1.54 of 4F+Ope+Acc combined). The two parallel quality chains (Sloan + Profitability) **converge at the Profitability dimension** of QMJ's 4-dimension structure (GPOA + ACC measures sit side by side).

The **F-block intangibles 4-layer methodology hierarchy** is the structural foundation of the Nasdaq 100 strategy. In a FAANG-heavy, R&D-heavy universe, GAAP accounting's mandatory expensing of R&D **artificially distorts** conventional B/M and Cop measurements. Lev-Sougiannis (1996) is the origin paper for this problem — it introduces an industry-specific amortization rate methodology (pharma 9 years, scientific instruments 5 years) for capitalizing R&D expenditure; FF93's main variable B/M ceases to be meaningful for R&D-heavy firms. Eisfeldt-Papanikolaou (2013) extended this idea to a sub-component of SG&A (organization capital); using a perpetual-inventory δ=15%, they provided factor-portfolio direct evidence (Carhart α=3.9% sig 1%, 1970-2008). Peters-Taylor (2017) proposed the total intangible capital concept and made q^tot proxy (V / (K^phy + K^int)) roughly 21% more explanatory than standard q. Lev-Srivastava (2020), the same author Baruch Lev's 24-years-later update, decomposed the post-2010 value crisis into two mechanisms (intangibles bias + mean-reversion slowdown) and showed that the "adjusted HML" methodology beats conventional HML in 34 out of 39 years. Together these four papers form the four legs of the intangibles-aware Bm rebuild for the NDX strategy; in the Cycle 25 mini-consolidation, Q41 (4-way horse race) received a complete answer.

The **composite mispricing scoring** chain is the historical record of the dimensionality-reduction pattern that keeps the factor count tractable. Piotroski F-Score (2000) reduces 9 binary components to a single 0-9 number; Mohanram G-Score (2005) adapts 8 industry-relative components to the low-BM universe; Stambaugh-Yuan (2017) collapses 11 anomalies via hierarchical clustering (Ward 1963) into MGMT (6 anomalies: net stock issues + composite equity issues + accruals + NOA + asset growth + I/A) and PERF (5 anomalies: distress + O-score + momentum + gross profitability + ROA); Jensen-Kelly-Pedersen (2023) groups 153 factors into 13 theme clusters (Accruals*, Debt Issuance*, Investment*, Leverage*, Low risk, Momentum, Profit Growth, Profitability, Quality, Seasonality, Size*, Skewness*, Value) using a Bayesian Empirical Bayes hierarchical model. The significance of this chain: for strategy design, the right question becomes **theme allocation, not factor selection**. 10/13 of JKP's themes replicate at >75% and contribute positively in the tangency portfolio; the sp500_v1 7-theme dominant + nasdaq100_v1 5-FAANG-profile theme allocations are applications of this framework.

## 5. 4/4 surviving factor candidates

Factors that pass the four-blow framework and earn the wiki's **4/4 certificate** form the backbone of the strategy specs:

| Factor | Methodology | Cycle | q-factor alpha | Comment |
|--------|-------------|-------|----------------|---------|
| **Sloan operating accruals (Oa)** | Sloan chain origin | 9 | −0.54%/mo sig | Core component of the F_ACCRUAL/G3 mispricing-detection paradigm |
| **R&D-to-market (Rdm)** | NDX-relevant | 13 | +0.7%/mo sig | Empirical counterpart of the F-block intangibles-aware methodology |
| **Earnings announcement Abr** | PEAD | 13 | +0.66%/mo sig | Bernard-Thomas 1989 surprise return; quarterly resort required |
| **Cash-based op profits (Cop)** | Profitability chain link 4 | 38 | +0.69%/mo sig | tangency Sharpe 4F+Cop=1.67 ⭐; subsumes accruals |

This quartet also defines the wiki's **practical strategy posture**: in the S&P 500, F&V/P combined + Cop standalone + adjusted HML + UMD long-only top 30%; in Nasdaq 100, QMJ + QARP + Mohanram NASDAQ partition + R&D-to-market + OC factor + adjusted HML 4-layer. The strategy-spec documents (`strategies/sp500_v1.md`, `strategies/nasdaq100_v1.md`) justify every design decision with a `[[wikilink]]` to a wiki paper; "I know this from memory" arguments are forbidden (CLAUDE.md §6.4).

## 6. Wiki structural positions (REJECT list)

By the end of Faz 1-2-3 accumulation, the wiki **rejects the transfer of certain factors to the large-cap universe**. These rejections did not arise from absence of evidence but from **abundance of evidence** — each is backed by at least two, in most cases three, papers' worth of supporting chain:

- **Vanilla HML reject** (Cycles 17 + 22 + 37): the triple confirmation of Lev-Srivastava 2020's post-2010 value-crisis decomposition + Israel-Moskowitz 2013's 86-year size-conditional evidence + Fama-French 2008 B/M big-stock weakness ([Table IV]) establishes that vanilla HML is structurally broken when transferred to the large-cap universe. The wiki uses adjusted HML methodology (Lev-Srivastava intangibles-aware) as baseline.

- **Vanilla SMB reject** (Cycles 12 + 19 + 22 + 39): SMB is never significant in HLZ's multiple-testing analysis; in Asness's QMJ controlling-for-quality regression SMB earns α=64bps t=6.39 (resurrection — but not as vanilla); Israel-Moskowitz 86-year confirmation; Stambaugh-Yuan 2017's modified-SMB methodology (middle-group only) earns 46 bps/month (roughly 2x FF SMB's 25 bps). Q11 ASTERISK three-paper hardening. Vanilla SMB is not a strategic input; modified SMB may be meaningful within a specific composite.

- **F-Score standalone large-cap reject** (Cycles 5 + 7 + 8): F-Score was calibrated only in the BM-Q5 universe (high-book-to-market); under the HMXZ 2020 q5 lens, in the large-cap segment the mispricing alpha is confined to the microcap residual. The wiki prefers F&V/P combined (Li-Mohanram 2019).

- **Magic Formula reject** (Cycle 8): under the HMXZ 2020 q5 model lens, most of Magic Formula's return is explained by factor exposures; standalone alpha is a microcap residual. Despite Greenblatt's popularity, academic replication is weak.

- **RMW Ope standalone reject** (Cycles 4 + 19 + 37 + 38): RMW Ope is INSIG under the HXZ q-factor lens; in FF 2008's [Table II + IV] size-conditional analysis it is significant only in the small-cap segment. The wiki prefers QMJ Profitability composite (6 measures) + Cop standalone.

These rejections constitute a **disciplined scope filter** against the naive aggressive inclusion of "everything in the literature is a strategy input". On the opposite side, what the wiki **does include** is interrogated with the same rigor — the §4 (Expected Performance) sections of sp500_v1 and nasdaq100_v1 specs cite a paper page for every number, and the §6 (Known Weaknesses) sections explicitly list acknowledged-but-not-addressed problems.

## 7. Strategy specs (sp500_v1 + nasdaq100_v1 + known_weaknesses)

The output of Faz 3 (Cycles 32-34) is three formal strategy specs. Each is roughly 340-400 lines, written in "spec doc" style with sections for universe + factor inclusion + methodology + expected performance + backtest implementation roadmap + known weaknesses + cross-references.

[`strategies/sp500_v1.md`](wiki/strategies/sp500_v1.md) is a formal spec for the S&P 500 top 500 ex-financials universe with a 1980-2020 baseline + 2021-2024 OOS test, capped VW (NYSE 80th-percentile winsorize) weighting, allocation across 7 of JKP's 13 universal themes (Quality + Profitability + Profit Growth + Value + Momentum + Accruals* + Low risk), 4 path composites (F&V/P binary intersection + GP×V/P continuous rank product Fortune 500 pattern + adjusted HML intangibles-aware + UMD long-only top 30%), with a Beneish M-Score `.025` forensic filter. The conservative baseline is 6-10%/year (×0.65 multiplier), the anti-conservative upper bound is 14-18% (JKP 85% sensitivity reference); the 2x range is sensitive to methodology choice.

[`strategies/nasdaq100_v1.md`](wiki/strategies/nasdaq100_v1.md), in the NDX top 100 non-financial universe, makes capped VW **mandatory** because of FAANG-heavy mega-cap concentration (Apple/MSFT/Google/Nvidia/Meta/Tesla 15-20%+); allocates across 5 FAANG-dominant themes (Quality + Profitability + Profit Growth + Investment* + Value); uses 5 path composites (QMJ + QARP, G&V/P + GP/A standalone, Mohanram NASDAQ partition, R&D-to-market + OC factor NDX-specific critical, adjusted HML F-block 4-layer), with a more conservative Beneish M-Score `.01` threshold (Q47 tech-firm high SGI/AQI false-positive concern). The F-block 4-layer intangibles-aware Bm rebuild is the strategy's **core**: Lev-Sougiannis Knowledge + Eisfeldt-Papanikolaou Organization (full SG&A δ=15% **or** Peters-Taylor θ=0.30; Q60 horse race open) + Peters-Taylor Total q^tot + Lev-Srivastava Application. The conservative baseline is 8-13%/year (×0.50 NDX-aggressive multiplier, due to the Q29 limited-arbitrage double blow), the anti-conservative upper bound is 16-21%.

[`strategies/known_weaknesses.md`](wiki/strategies/known_weaknesses.md) is the wiki-level **cross-strategy weakness registry**. Written before Faz 3 implementation as a transparent acknowledgment, it explicitly rejects over-promising. Across 6 sections it formalizes the weaknesses inherited by sp500 and nasdaq100 specs, the weaknesses common to both universes, the methodology-choice sensitivity requirements, and acknowledged-but-not-addressed items (post-2020 OOS, JKP 85% anti-conservative). The synthesis function carried by v0_draft (Cycle 24) → v1_draft (Cycle 30 historic-preservation pattern) → three formal specs was absorbed into this page in Cycle 34.

## 8. Phase structure: 0 → 1 → 2 → 3 → living-project

The wiki was originally planned as a project that would pass through three phases: Faz 1 (Foundation), Faz 2 (Synthesis), Faz 3 (Strategy Design). Each phase transition occurs **by user decision**; Claude proposes, the user approves.

**Faz 0 — scaffold** (2026-04-27): empty structure + Tier 1 source list + first commit. The core of the CLAUDE.md §1-11 schema was written in this phase.

**Faz 1 — Foundation** (Cycles 1-20; certificate 2026-05-01 **YUMUŞAK**): 19 of the Tier 1 papers (76% of the 25 target) were ingested; epistemic completeness was fully met (4+ block-closing syntheses + three-leg backbone + four-blow framework synthesis table + 4+ priori questions fully-answered + 4/4 and 3-4/4 surviving factor candidates). The YUMUŞAK ("soft") certificate was issued because numerical targets stood at 76%; gaps would be filled by Faz 2 selective ingest. This certificate type was formalized by the Cycle 20 schema_update (the old numerical targets were turned into a dual "epistemic completeness + numerical minimum" criterion).

**Faz 2 — Synthesis** (Cycles 21-31; certificate 2026-05-02 **TAM**): all 11 structural criteria (methodology infrastructure + strategy candidate + replication + hardening + consolidation + 3rd contradictions resolution + v0 → v1 evolution) were fully met. Israel-Moskowitz, Novy-Marx, Eisfeldt-Papanikolaou, FGX 2020, JKP 2023 were ingested in this phase. v0_draft (Cycle 24) evolved into v1_draft in Cycle 30 — the historic-preservation pattern was born and embedded in wiki discipline from Cycle 30 onward. methodology/backtest_spec (Cycle 21) and methodology/data_sources (Cycle 29) were opened; the Faz 3 backtest implementation infrastructure was put in place.

**Faz 3 — Strategy Design** (Cycles 32-41; certificate 2026-05-02 **YUMUŞAK** Cycle 41 update): five of the ten structural criteria were completed in-wiki (sp500_v1 + nasdaq100_v1 + known_weaknesses formal specs + backtest_spec hardening + 4/4-6 Faz 3 selective ingest: HXZ 2015 + FF 2008 + Ball-GLN + Stambaugh-Yuan). Criteria #6-9 (backtest implementation + factor selection + tangency portfolio + DSR-corrected reporting) were **delegated to a separate out-of-wiki project** (Portfolio123 Ultimate platform; `equity-alpha-backtest` repo). Criterion #10 (v1 → v2 evolution optional revision) is **N/A within the wiki living-project framing** — backtest results are reported back, and a v2 spec is opened if needed (CLAUDE.md §12.3 historic preservation).

**Living-project** (Cycle 42+): the wiki is not frozen; it remains a live knowledge base. New papers are ingested as they arrive, backtest results are ingested as paper-form reports, lint/consolidation passes continue under the 4-cycle consecutive discipline, and the cycle counter continues under the post-Faz 3 update category. In Cycle 42, `meta/executive_summary.md` (executive summary) and §12 (post-Faz 3 maintenance protocol) were added; that §12 sharpens maintenance discipline with three rules: (a) executive_summary update cadence, (b) backtest report ingest under `wiki/backtests/` with `type: backtest_report` frontmatter, (c) v1 → v2 evolution historic preservation.

## 9. Backtest project — out-of-wiki, cyclical learning

Criteria #6-9 of the Faz 3 certificate (backtest implementation + factor-selection methodologies + tangency portfolio + DSR-corrected reporting) were **deliberately moved out of the wiki**. The reason is by design: the wiki is a **knowledge base**, not an **execution platform**. Running backtest engines, managing the point-in-time data flow, performing walk-forward sub-period analysis, and reporting bootstrap confidence intervals — these are outside the natural scope of the wiki's Markdown + cross-reference pattern.

The solution: implementation runs in a separate `equity-alpha-backtest` repo on the **Portfolio123 Ultimate** platform ($389/month; 20-year backtest + Position Sizing + Optimizer + Regression + AI Factor + Hedging/Long-Short). P123 provides point-in-time data (CRSP + Compustat lifelong-included); optionally, custom-field overrides via FMP or SEC EDGAR can be used (for example, for the F-block R&D capital perpetual inventory). Sample: 2010-2024 backtest + 2025+ live application; capital $1M, sp500_v1 + nasdaq100_v1 ~50/50 split; drawdown tolerance 50%; rebalance annual June + quarterly drift-check safety valve.

The relationship between the two projects is **cyclical learning**:

```
   Wiki theory (living-project, ~88 pages)
              │
              │ (strategy spec → P123 ranking systems + custom DSL)
              ▼
   Backtest project (P123 Ultimate)
              │
              │ (backtest result → wiki/backtests/p123_*.md paper-form report)
              ▼
   Wiki synthesis hardens (v1 → v2 evolution candidate)
              │
              │ (new paper ingest + cycle continues)
              ▼
   Wiki theory (updated)
```

The wiki's specs are mapped to P123: sp500_v1 §2.1 7-theme allocation → 7 P123 ranking systems + Position Sizing balanced allocation; nasdaq100_v1 §2.5 F-block 4-layer intangibles-aware Bm rebuild → custom DSL formula not natively present in P123 (R&D capital perpetual inventory + SG&A 30% allocation Peters-Taylor methodology). The known_weaknesses.md §3.13 NDX intangibles four-fold consolidation (Q56+Q73+Q79+Q82) is flagged as a critical weakness for backtest implementation.

Reporting protocol (CLAUDE.md §12.2 + handoff_backtest §6.1): backtest results are stored under the slug `wiki/backtests/p123_{strategy}_{YYYY-MM-DD}.md`, with YAML `type: backtest_report` frontmatter, in a folder separate from academic papers. Anchor pages (sp500_v1 §5 + nasdaq100_v1 §5 + known_weaknesses §5 + backtest_implementation_plan §8 + the index.md "Backtests" section) are updated. The v1 → v2 evolution trigger is evaluated (handoff_backtest §6.3 criteria: out-of-range deviation from the conservative baseline + methodology-choice >5pp divergence + Q60 horse race clear winner + F-block 4-layer four-fold consolidation empirical decision). When the trigger fires, **v1 IS NOT OVERWRITTEN**: sp500_v2.md / nasdaq100_v2.md are opened; v1 stays frozen with status=historic + superseded_by (paralleling the Cycle 30 v0 → v1 historic-preservation pattern).

This architecture allows the wiki's intellectual products to be tested empirically while **preserving the wiki's epistemic integrity** — a backtest result does not "prove" the wiki right; it merely measures whether the wiki's predictions hold within a particular methodological window. The conservative-wiki + sensitivity-range reporting discipline is the concrete expression of this epistemic humility.

## 10. Writing and audit discipline

Wiki quality is determined not by ingest speed but by **audit rigor**. CLAUDE.md §6 NON-NEGOTIABLE writing rules, §11 self-audit cycles, and §12 living-project maintenance protocol form the operational skeleton of this discipline.

**Writing-discipline summary** (CLAUDE.md §6):

1. No numerical claim is allowed without a source — every number must be backed by a paper-page citation (`[Paper Year, Table N]`) or `[[wikilink]]`.
2. Memory- or training-derived additions are forbidden — the wiki rests only on sources in `raw/`; phrases like "as is generally known in the literature..." are banned.
3. Hedges are forbidden — "probably", "usually", "may be effective" must be tied to either a number or a source.
4. Conflicting evidence is not hidden — if 5 papers exist for a factor and 2 found weak results, both are written; cross-references go in `meta/contradictions.md`.
5. YAML frontmatter is mandatory — across paper, factor, concept, strategy, methodology, and backtest_report templates.
6. Wikilink syntax is `[[page_name]]` (Obsidian-compatible); use `> ⚠️` for warnings/contradictions, `> 📝` for editorial notes.
7. Language policy (CLAUDE.md §6.6 as updated in Cycle 43): the conversation language follows the user; the public surface (README, GitHub description) should be English; internal wiki pages may remain in their existing language; new wiki pages should prefer English for titles, frontmatter, and technical terminology.

**Self-audit cycles** (CLAUDE.md §11): at the end of each ingest, Claude **audits itself** — a 6-spot audit (A factor entity integrity + B Goal Alignment 4-axis + C concept enrichment + D inbound link maintenance + E meta files + F open_questions/data_gaps) is reported as PASS/PARTIAL/FAIL. The 4-cycle consecutive consolidation pass (Cycle 4/8/12/16/20/24/28/32/36/40/44/...) replaces the standard audit with a deeper review (orphan + contradiction + stale claim + MoC + broken wikilink). The user only makes strategic decisions on the audit report ("TEMIZ devam", "KÜÇÜK fix devam", "YAPISAL fix", "ABORT"); the operator is Claude.

**§12 living-project maintenance protocol** (Cycle 42 schema_update): three rules — (1) `executive_summary.md` is updated every 4 cycles or after a large ingest, (2) backtest reports go to `wiki/backtests/p123_{strategy}_{YYYY-MM-DD}.md` (not mixed with academic papers), (3) if a backtest result requires a strategy change, v1 IS NOT OVERWRITTEN; v2 is opened. This protocol preserves cumulative wiki consistency under the post-Faz 3 living-project status.

Why this much discipline? **The wiki's value lies not in the last 5 papers of the 25-paper Tier 1 but in keeping the first 5 free of error.** Self-audit catches errors immediately at each cycle; consolidation pass catches structural staleness within 4 cycles; schema_updates leave changing rules in the log. Manually checking every page across 88 sayfa would be impossible for a user; the discipline protocol automates this audit.

## 11. Usage

```bash
git clone https://github.com/AlperTheKing/equity-alpha-wiki.git
cd equity-alpha-wiki
claude
```

Claude's first action is to read [`CLAUDE.md`](CLAUDE.md) and load state from the most recent handoff document and log entries. The "first 3 minutes" instructions for a new Claude session are in `wiki/meta/handoff_post_faz3_001.md` §5.

Typical living-project workflow:

```
> raw/papers/ klasörüne LSV 1994 paper koydum, ingest et
  → CLAUDE.md §5.1 ingest workflow + §11.2 6-spot audit otomatik

> F-block intangibles-aware methodology özet ver
  → wiki/concepts/intangibles_adjusted_accounting.md + 4 paper-page wikilinks

> Q60 horse race durumu — Eisfeldt-Papanikolaou full SG&A vs Peters-Taylor θ=0.30
  → meta/open_questions.md Q60 + relevant strategy spec §2.5 NDX-specific

> consolidation pass yap (Cycle 44 §11.5)
  → 4-cycle consecutive deep audit; orphan + contradiction + stale + MoC + broken wikilink

> P123 backtest sp500_v1 sonucu ulaştı, paper-form raporla
  → wiki/backtests/p123_sp500_v1_2026-06-15.md (CLAUDE.md §12.2)
  → anchor page update; v1→v2 trigger evaluation
```

(Trigger phrases — `TEMIZ devam`, `KÜÇÜK fix devam`, `YAPISAL fix`, `ABORT`, `audit`, `consolidation`, `freeze ingest` — are retained in their original Turkish form for backwards compatibility with CLAUDE.md §11.6.)

## 12. Related resources and license

- Karpathy `llm-wiki` pattern: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
- Claude Code: https://claude.com/claude-code
- Portfolio123 (backtest project platform): https://www.portfolio123.com/
- Chen-Zimmermann Open Asset Pricing Database: https://www.openassetpricing.com/
- Jensen-Kelly-Pedersen GlobalFactor code repository: https://github.com/bkelly-lab/GlobalFactor

**License**: The project-owner-authored content of this repository — `CLAUDE.md` (operating schema), `wiki/` (LLM-written synthesis: paper summaries, factor entities, concepts, comparisons, strategy specs, methodology pages, meta pages, log), `README.md`, and other scaffolding files — is released under the **MIT License**. See [`LICENSE`](LICENSE) for the full text.

The MIT license does **not** cover `raw/` — source papers, books, and industry whitepapers under that directory remain the copyright of their respective authors and publishers and are included only for personal research and citation. Anyone reusing this repository must obtain their own copies of those sources from authoritative venues (SSRN, NBER, publisher sites) and comply with the terms set by those sources. Excerpted quotations from `raw/` materials that appear inside `wiki/` page summaries fall under fair-use / fair-dealing provisions applicable to academic citation; they remain the intellectual property of the original authors.

The wiki is a research artifact and not investment advice; the author makes no warranty regarding the accuracy of the synthesis or the suitability of any strategy spec for actual investment use.

---

> **Note on language**: Internal wiki pages (papers/, factors/, concepts/, strategies/, methodology/, meta/, log.md) are currently in Turkish, reflecting the language used during the 41 ingest cycles. CLAUDE.md §6.6 has been updated (Cycle 43 schema_update) to require English for the public surface (README, GitHub description) while permitting existing Turkish pages to remain unless an explicit `language_migration` operation is approved. New wiki pages should prefer English for titles, frontmatter, and technical terminology.

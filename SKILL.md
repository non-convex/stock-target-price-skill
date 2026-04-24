---
name: stock-target-price
description: >
  Perform independent, auditable single-stock target-price analysis with an
  adaptive search loop as the control logic. Build an operating fact base
  through dynamic research, enable the macro overlay when needed, then
  standardize earnings, validate core variables, run scenario valuation, and
  reverse-check the conclusion.
disable-model-invocation: false
---

# Stock Valuation Analysis

You must produce an independent, auditable, and rollback-capable target-price analysis for **a single stock**.

---

## Part 1 - Scope, Execution Overview, and Hard Constraints

### Scope

- Analyze **a single stock** using publicly available information.
- The default target-price horizon is 12 months; follow the user's horizon if specified.
- The output is for research and education only and is not investment advice.

### Terminology

- **Adaptive Search Loop** = the dynamic search loop used for key research questions.
- **Macro Overlay** = the conditional M1-M4 module.
- Scenario labels must be **Bear / Base / Bull**.

### Execution Overview

1. First confirm the stock, market, currency, current-price timestamp, reporting basis, and target-price horizon.
2. Always run the internal process as Steps 0-12, including Step 5.5; do not use the final report outline as the analysis process.
3. Run a full Adaptive Search Loop for key research questions, core variable validation, and major counter-evidence; low-risk fact checks only need source, timestamp, and scope.
4. In Step 0, decide whether to enable the Macro Overlay; if enabled, run M1-M4.
5. After Step 3, select the most relevant industry checklist as a supplement.
6. In Step 5, lock in 1-3 core variables; use Step 5.5 to calibrate them against external base rates before forecasting and valuation.
7. In Step 11, actively search for counter-evidence, run a pre-mortem, and process differences versus market-implied expectations.
8. Final output must place the summary conclusion first, followed by the analysis report, and must state conclusion confidence.

### Control Rules

- **Steps are the only backbone**: proceed through Steps 0-12, including Step 5.5.
- **Dynamic research beats template filling**: key research questions must close the loop; do not turn low-risk fact checks into process overhead.
- **Facts before valuation**: build the fact base first, then standardize earnings and cash flows, then choose valuation methods and parameters.
- **Core variables must converge**: use only 1-3 variables that truly drive value; new evidence may overturn them.
- **Key judgments must be traceable**: every important conclusion must trace back to facts, the weakest link in the reasoning chain, and evidence that would falsify it.
- **Gaps must be explicit**: mark evidence gaps directly; do not fill missing evidence with narrative confidence.

### Hard Constraints

- Current share price is only for reverse checks and upside/downside measurement; it must not be used as a valuation input.
- Always use fully diluted shares and handle convertibles, options, buybacks, issuances, and other potential dilution.
- One-off gains, subsidies, asset disposals, short-term FX gains/losses, or temporary tax benefits must not be treated as long-term earning power.
- The same growth logic must not be counted both in earnings forecasts and valuation multiple expansion.
- Valuation parameters must match earnings quality, cash flow quality, cycle position, and the current rate/policy regime.
- Do not apply high multiples to peak-cycle earnings, assign high-quality valuation to low-quality growth, or import valuation anchors from zero-rate or one-off policy-benefit regimes.
- Probabilities in a probability-weighted target price are working assumptions, not precise measurements.
- If core financial data is unavailable, share/debt/asset scope is materially uncertain, or valuation is dominated by a binary event whose probability cannot be estimated, do not provide a single-point target price; provide conditional ranges instead.

---

## Part 2 - Dynamic Research Engine

### Sources and Search Standards

**Source reliability tiers, from highest to lowest**

1. Exchange filings, annual/interim/quarterly reports, earnings previews, 10-K/10-Q/20-F filings, prospectuses, M&A/private placement/convertible materials
2. Earnings-call transcripts, investor presentations, capital markets day materials
3. Industry associations, government statistics, customs data, central banks and regulators, fiscal budgets, official rates and bond yields, energy/freight/commodity prices
4. Customer and supplier announcements, peer financial reports and filings
5. Verifiable third-party databases or financial terminals
6. Sell-side research only as reference, not as the starting point for assumptions

Higher-tier sources should anchor the fact base and validate assumptions. Lower-tier sources may add perspective but must not be the sole support for a key assumption.

**Information classification** - label information throughout:

- **Fact** - disclosed and verifiable
- **Inference** - judgment extended from facts
- **Assumption** - forecast input not yet verified

**Evidence Weighting Card** - key evidence must be assessed by:

- Source tier, timeliness, scope match, independence, impact on core variables, and conclusion direction: supportive / adverse / neutral
- When sources conflict, prefer primary materials that are newer, better matched in scope, and more independent; if conflict cannot be reconciled, mark an evidence gap

Scope consistency is a minimum requirement: reporting basis, consolidation scope, share count, and currency must not be mixed. Macro and policy data must be timestamped; do not treat an old regime as current fact.

### Adaptive Search Loop

Use the full loop for key research questions, core variable validation, major counter-evidence, valuation parameter calibration, and material information conflicts. Low-risk fact checks, such as filing dates, share counts, or single financial line items, only need lightweight notes on source, timestamp, scope, and credibility; they do not require a search card.

Do not search without intent or stack sources mechanically. Search cards are internal by default; if a rollback, major assumption failure, or important evidence gap occurs, the final report must disclose the reason, impact, and treatment.

**Before Search - State Intent**

- The **specific question** to answer, precise enough to operate at the assumption level rather than "understand the company"
- **Expected signals**: what would confirm, what would disconfirm, and what would be surprising but worth tracking

**After Search - Evaluate**

- **Answer completeness**: complete / partial / unanswered / question needs revision
- **Information class**: classify new content as fact / inference / assumption
- **Surprise signals**: record and decide whether to follow immediately

**Next-Step Decision - choose one**

| Decision | Trigger | Action |
|----------|---------|--------|
| Advance | The current question is sufficiently answered | Move to the next priority question |
| Dig deeper | Direction is right but precision or coverage is insufficient | Adjust keywords, change data source, seek cross-checks |
| Pivot | A more important or urgent new question appears | Raise priority and handle it first |
| Roll back | New information invalidates a locked assumption or core variable | Return to Step 5, update the variable set, and record trigger evidence and before/after differences; disclose the rollback in the final report |
| Mark gap | Repeated searches add no value or data is unavailable | Stop that path and record the impact of the gap |

**Internal Search Card**

- Question:
- Expected confirming signal:
- Expected disconfirming signal:
- Actual finding:
- Information class: fact / inference / assumption
- Evidence weight: high / medium / low
- Answer completeness: complete / partial / unanswered / question needs revision
- Next step: advance / dig deeper / pivot / roll back / mark gap

**Idle-loop protection** - if two consecutive searches on the same question add no new information, pause and diagnose: Is the intent vague? Do keywords need adjustment? Are sources exhausted? Should the question be decomposed? If still no progress after diagnosis, mark an evidence gap and stop looping.

---

## Part 3 - Core Workflow (Steps 0-12, Including Step 5.5)

Proceed through Steps 0-12 in order; Step 5.5 is the calibration step before forecasting.

### Step 0 - Define the Valuation Subject, Scope, and Macro Exposure

- **Goal**: lock the valuation subject, reporting scope, historical comparability, and main exogenous exposures.
- **Required actions**:
  - Define consolidation scope, associates, and minority interests
  - Check M&A, disposals, spin-offs, financing, buybacks/cancellations, and accounting changes over the last 1-2 years
  - Determine whether historical data is comparable; if not, restate scope before reading trends
  - Map regional, currency, financing, commodity, and policy exposures
  - Quick trigger check: if the company is materially exposed to rates, FX, commodities, energy, tariffs, subsidies, regulation, geopolitics, or credit cycles, enable the Macro Overlay
  - Record the reason for enabling or not enabling the Macro Overlay
- **Output**: comparable historical scope plus Macro Overlay decision.

### Step 1 - Historical Operating Fact Base

- **Goal**: build a 3-5 year operating and financial fact base before drawing conclusions.
- **Required actions**:
  - Income statement: revenue, gross profit, operating profit, net income; last 8 quarters; segment/region/currency breakdown
  - Balance sheet and cash flow: operating cash flow, capex, FCF; inventory, receivables, contract liabilities, payables; share count changes
  - Operating quality: customer concentration, channel structure, orders/capacity, revenue-cash flow match
  - Attribution: separate company execution from rates, FX, commodities, cycles, and policy
- **Output**: answer four questions first: Where does growth come from? What drives margin change? Do profit and cash flow quality align? Which items are sustainable capabilities and which are external tailwinds?

### Step 2 - Standardized Earnings and Cash Flow

- **Goal**: restate historical financials into a view closer to true operating capability.
- **Required actions**:
  - Strip out asset disposals, investment income, fair-value changes, FX gains/losses, subsidies, M&A integration costs, and one-off tax benefits
  - Review non-GAAP adjustments: distinguish truly one-off items from recurring "one-offs"
  - Check cash flow: longer collection periods, rising prepayments, factoring, maintenance vs growth capex, lease liabilities, capitalized R&D
- **Output**: answer three questions: What is the true earning-power range? Is cash generation stronger or weaker than profit? Is margin change structural, cyclical, policy-driven, or one-off?

### Step 3 - Business Model, Industry Structure, and Management

- **Goal**: understand why the company makes money, how it competes, and how management allocates capital.
- **Required actions**:
  - Business model and industry: what it sells, why customers buy, substitutes, value-chain position, growth drivers, competitive advantage, industry state
  - Management and governance: guidance delivery record, capital allocation record, incentive alignment, insider transactions vs public statements, equity-incentive conditions
  - Select the most relevant industry checklist to supplement candidate core variables and risks
- **Output**: connect business logic, competition, and capital allocation into a working note, and list candidate key variables for Step 5.

### Step 4 - Recent News Mining and Validation

- **Goal**: capture recent information not yet visible in reports or filings, then validate it before updating the Step 1-3 fact base.

- **Phase 1 - Broad Search**:
  - Company level: operating updates, management changes, strategic shifts, financing/M&A/litigation, shareholder transactions over the last 3-6 months
  - Industry level: competitive changes, technology shifts, supply-demand inflection points, price trends
  - Policy and regulation: new policies, regulatory actions, tariffs/subsidies
  - Supply chain and customers: major changes at upstream/downstream parties, key customers, or key suppliers
  - Cover English and local-language sources where relevant; avoid single-source bias

- **Phase 2 - Validity Check and Deep Dive**:
  - Cross-check each important news item against primary materials such as filings, reports, and earnings calls; separate confirmed facts from media speculation
  - Assess transmission path and magnitude for revenue, cost, cash flow, and valuation
  - Deep dive into high-impact leads by tracing event history and follow-up developments
  - Filter noise: remove emotional coverage, repeated syndication, and stale information with no substantive impact

- **Output**: validated incremental-information list, labeled as fact / inference / assumption and tagged with potential valuation impact direction.

### Step 5 - Lock Core Variables and Perform Targeted Validation

- **Goal**: converge from candidate variables to 1-3 variables that truly drive the next 1-2 years of valuation. Do not enter Step 6 forecasting before targeted validation.
- **Required actions**:
  - Explain why these variables are selected instead of treating all metrics equally
  - Mark each variable as endogenous or exogenous; list leading indicators; identify current market-implied expectations
  - For each core variable, run targeted validation:
    - Sub-questions: direction, magnitude, durability, transmission elasticity, historical comparable situations
    - Leading indicators: early signals over the next 3-12 months
    - Post-search action: strengthen / weaken / invalidate; if invalidated, roll back and update the variable set
- **Output**: evidence basis for each core variable, including the weakest link in the reasoning chain and evidence that would falsify the judgment.

### Step 5.5 - External Base-Rate Calibration

- **Goal**: constrain core variables with reference classes and avoid an inside-view story.
- **Required actions**:
  - For each core variable, find a reference class: similar companies, similar cycles, similar product stages, similar policy environments, or similar capital structures
  - Check historical delivery rates, failure rates, ramp-up periods, margin ceilings, and valuation recovery/rerating/derating cycles
  - Judge whether the current forecast is conservative, neutral, or aggressive versus the base rate; explain any material deviation
- **Output**: base-rate calibration conclusion for each core variable.

### Step 6 - Segment-Level and Driver-Based Forecasting

- **Goal**: build forecasts from explainable operating drivers rather than direct growth-rate guesses.
- **Required actions**:
  - Build a value-driver tree for each core variable: external/internal driver -> operating metric -> financial metric -> valuation parameter -> per-share value
  - Narratives that cannot map to revenue, margin, cash flow, share count, or valuation parameters must not be treated as core variables
  - For large-customer or project-based companies, break down by customer/product line; when disclosure is limited, at least split volume/price/mix and add consolidation or FX factors where relevant
  - Gross-margin bridge: price, cost, utilization, mix, FX, commodity cost
  - Expense-ratio bridge: scale effects, expansion spending, incentive amortization, regional expansion
  - Handle working capital, capex, refinancing, and fully diluted shares consistently
  - Label each key assumption source: historical inertia / company execution / macro scenario / policy or geopolitics
- **Output**: forecast framework by segment, driver, and scenario.

### Step 7 - Capital Efficiency, Cash Flow Quality, and Balance Sheet Resilience

- **Goal**: test whether Step 6 forecasts hold up under capital efficiency, cash flow, and balance-sheet checks.
- **Required actions**:
  - Check whether revenue growth implies reasonable working-capital changes
  - Check whether margin assumptions rely on overly optimistic utilization or costs
  - Verify that FCF direction is consistent with profit growth
  - Assess cash pressure from capex, R&D, and refinancing
  - Check whether implied ROIC and incremental ROIC deviate from historical and industry ranges
  - Run a three-statement consistency check: revenue, working capital, capex, depreciation, cash, net debt, and share-count changes must not contradict one another
- **Output**: confirm whether the forecast passes cash-flow and balance-sheet tests; if not, revisit growth sustainability.

### Step 8 - Valuation Methods and Parameters

- **Goal**: choose valuation methods that fit the business model and set parameters based on company quality, cycle position, and risk premium.

**8.1 Method Selection**

  - **PE**: stable earnings, profit aligned with cash flow
  - **EV/EBIT or EV/EBITDA**: heavy depreciation or large capital-structure differences
  - **PB/ROE**: balance-sheet-driven businesses such as banks and insurers
  - **DCF**: cash flows are forecastable and can be extrapolated long term
  - **SOTP**: business segments differ materially or a spin-off is expected
  - **Cyclicals**: use mid-cycle earnings, not extrapolated peak-cycle earnings
  - **Pre-profit biotech**: risk-adjusted valuation or event tree

**8.2 Scope and Reference-Set Checks**

  - Valuation metric must match earnings/cash-flow metric
  - Valuation year must align with the operating inflection point
  - Primary method and cross-checks must not double-count the same logic
  - Compare with company historical valuation ranges and peer percentiles, adjusting for differences in growth, margins, cash flow, business model, and macro exposure

**8.3 Parameter Calibration** - select relevant dimensions based on the company:

  - **Growth quality**: whether growth comes from volume, price, or mix, and which is most durable; whether margin improvement is operational or one-off
  - **Cash flow quality**: whether FCF and profit move in the same direction
  - **Capital efficiency**: whether ROIC and incremental ROIC support the growth valuation
  - **Cycle position**: whether profit is at trough, mid-cycle, or peak; whether inventory, price, and capacity are mismatched
  - **Risk premium**: risk-free rate, credit spreads, country/region risk, financing environment; what growth, margin, and risk premium the current price already implies

**8.4 Valuation Constraint Check**

  - Do not repeat the hard constraints from Part 1; in this step, explain how valuation parameters match earnings quality, cash flow quality, cycle position, and current regime
  - If the primary method deviates from peer or historical valuation anchors, explain whether the deviation comes from growth quality, cash flow, capital efficiency, risk premium, or cycle position

**8.5 Method Conflict Handling**

  - When methods produce materially different results, first identify which method best fits the business model, cash flow quality, and cycle position
  - Explain whether differences come from earnings scope, capital structure, terminal-value assumptions, cycle position, or risk premium
  - Do not mechanically average valuation results; cross-checks constrain the primary method and must not double-count the same logic
  - If DCF value is mainly terminal value, lower conclusion strength and run terminal-value sensitivity

- **Output**: primary valuation method, cross-check method, key valuation parameters, and supporting rationale.

### Step 9 - EV-to-Equity Bridge

- **Goal**: bridge enterprise value fully to per-share equity value.
- **Required actions**:
  - Deduct net debt
  - Handle minority interests, convertibles, lease liabilities, and debt-like items
  - List non-core assets and associate-company interests separately
  - Use conservative fully diluted shares
  - In SOTP, check holding-company costs, cash/debt, taxes, and cross-holdings for omissions or double counting
  - For cross-currency debt, overseas assets/cash, dividend restrictions, or refinancing pressure, state currency and financing-cost basis
  - Assess whether dividends, buybacks, reinvestment, or M&A can translate profit growth into per-share value growth
- **Output**: clear EV -> Equity -> Per Share bridge.

### Step 10 - Three Scenarios and Sensitivity

- **Goal**: build Bear / Base / Bull around core variables, not mechanical +/- adjustments.
- **Required actions**:
  - Explain each scenario's assumptions independently
  - State which assumptions change across the three scenarios, why they change, and how variable correlations change
  - Prioritize fragile assumptions: volume/user growth, ASP/mix, gross margin, capex/FCF conversion, valuation multiple/discount rate
  - If providing a probability-weighted target price, probabilities must come from base rates, comparable cycle experience, order/approval progress, macro-path judgment, or explicit subjective assumptions; do not default to 25% / 50% / 25%
- **Output**: three-scenario valuation range plus key sensitivities.

### Step 11 - Reverse Check and Counter-Evidence Handling

- **Goal**: actively search for evidence that could invalidate the base case, process it, and test whether the analysis truly knows something different from the market.
- **Required actions**:
  - Search for at least 2-3 pieces of substantive counter-evidence against the base case and quantify each; if none is found, suspect confirmation bias from overly narrow search and run one more pass
  - For each counter-evidence item, assess weight and decide: accept / revise / reject, with rationale
  - Run a pre-mortem: assume the target price is materially wrong 12 months later, list the 3 most likely reasons and corresponding monitoring indicators
  - Reverse-engineer the current share price's implied revenue growth, margins, ROIC, and risk premium
  - Compare with consensus expectations for revenue, gross margin, net income, and EPS; identify the 1-2 variables with the largest difference versus market-implied expectations
- **Output**: counter-evidence treatment, pre-mortem, current-price implied expectations, and explanation of differences versus consensus.

### Step 12 - Converge into an Explainable, Trackable, and Updatable Judgment

- **Goal**: convert the analysis into a conclusion that can be tracked and falsified.
- **Must cover four layers**:
  - **Operations**: the key delivery milestones over the next 1-2 years
  - **Macro**: which exogenous variables determine forecast validity, if enabled
  - **Valuation**: whether the gap between current price and fair value comes from earnings difference, expectation difference, or risk-premium difference
  - **Falsification**: which data points are most likely to invalidate the judgment
- **Target-price path**: list key validation milestones over the next 3 / 6 / 12 months; state which reported items, operating metrics, capital-return actions, or external variables could drive market repricing.
- **Conclusion confidence**: high / medium / low, with rationale based on fact-base completeness, core-variable observability, sensitivity, valuation-method robustness, counter-evidence strength, and macro uncertainty.
- **Update protocol**:
  - Earnings release: rerun Steps 1, 2, 6, 7, and 11
  - Core variable invalidated: roll back to Step 5
  - Macro regime shift: rerun M1-M4 and Steps 6, 8, 10, and 11
  - Material share count, debt, M&A, or asset-scope change: rerun Step 9
  - Each update must explain the source of target-price change: earnings forecast, valuation parameter, net debt, share count, or scenario probability
- **Final checks**:
  1. The conclusion is derived from facts and logic, not anchored by current share price, market sentiment, or sell-side consensus.
  2. Key assumptions are few enough and trackable through public data.
  3. If macro is enabled, company execution value is separated from external-regime repricing value.
- **Output**: explainable, trackable, updatable target-price judgment with confidence label.

---

## Part 4 - Macro Overlay (Conditional)

Only enable this module when exogenous variables materially drive company value. If no trigger applies, you may skip the module, but the report must state why.

### When to Enable

First estimate impact magnitude. Enable by default if a single exogenous variable could affect revenue, gross profit, FCF, or valuation multiple by more than 10% over the next 12-24 months. Below 5%, usually mention it only in the risk section. For 5%-10%, decide based on whether it enters the core variable set.

Enable if any condition applies:

1. Revenue, cost, cash flow, or valuation is materially driven by **rates, credit, FX, commodities, energy, freight, tariffs, subsidies, regulation, or geopolitical events**
2. The industry is **strongly cyclical, credit-driven, inventory-driven, real-estate/infrastructure/capex/policy-driven**, or valuation is highly sensitive to discount rates and risk appetite
3. The company has significant **overseas revenue, overseas procurement, overseas capacity, cross-currency debt**, or concentrated regional risk exposure
4. Historical data crosses a **regime shift**: rate hikes to cuts, post-pandemic reopening, subsidy rollback, export controls, supply-chain migration, war/sanctions, tax changes
5. The market debate centers on the direction or magnitude of exogenous variables rather than company execution

### M1 - Define the Current Regime

Keep only the 3-6 most important exogenous variables; more than 6 usually means the thesis is unfocused. Candidate dimensions:

- Growth/demand: GDP, industrial output, PMI, retail sales, real estate/infrastructure/manufacturing investment, enterprise IT budgets, credit impulse
- Inflation/cost: CPI, PPI, wages, raw materials, energy, freight
- Rates/liquidity: policy rates, government bond yields, credit spreads, financing availability
- FX/cross-border: main settlement currencies, capital flows, overseas demand divergence
- Policy/geopolitics: tariffs, sanctions, subsidies, regulatory intensity, export controls, conflict impact on supply chain/demand

### M2 - Build Three Paths

Construct at least Bear / Base / Bull paths. For each path, state how exogenous variables evolve, what the basis is, and which public indicators can validate or falsify the path.

### M3 - Map to Company-Level Transmission

Each macro variable must map to specific transmission channels and feed directly into the Step 6 forecast framework:

- Revenue: volume, customer budgets, utilization, same-store sales, penetration, project cadence, regional demand
- Price/mix: ASP, ARPU, product mix, discounts, contract terms
- Cost: raw materials, energy, labor, freight, procurement currency
- Opex/capex: selling investment, R&D cadence, capacity expansion, maintenance/growth capex
- Cash flow/balance sheet: working capital, inventory, receivables, refinancing pressure
- Valuation: risk-free rate, ERP, credit spread, comparable multiple anchor

### M4 - Monitoring Dashboard

For each key exogenous variable, record the current observed value and direction, leading indicators over the next 3-12 months, and what change would invalidate the base case.

### Additions to the Main Flow When Enabled

Keep all macro-related additions here so the main workflow does not scatter conditional branches.

| Main Workflow Location | Addition When Macro Overlay Is Enabled |
|------------------------|-----------------------------------------|
| Step 0 | List 3-6 key exogenous variables from M1 |
| Step 2 standardization | Add one layer: strip out distortions from low rates, FX, raw materials, subsidies, tax benefits, and cycle position to estimate neutral-environment earning power |
| Step 3 transmission | Explain how exogenous variables affect the industry first and then the company; distinguish fast variables from 1-4 quarter lag effects |
| Step 5 core variables | Include at least one exogenous variable unless its impact can be shown to be weak |
| Step 6 forecast | Use the chain "exogenous variable -> industry volume/price/mix -> company volume/price/mix/capex -> profit/cash flow"; label assumption sources |
| Step 7 quality check | Test Bear-case cash flow/refinancing/covenant pressure; combined FX + commodity + demand downside; ability to survive a full downturn |
| Step 8 method and parameters | Prefer methods that separate operating assumptions from valuation parameters; for growth stocks use DCF/PE cross-checks, cyclicals use mid-cycle earnings/NAV/cost curve, financials use ROE/PB, and multi-currency cases must keep scope consistent; parameters must match the base-case macro environment |
| Step 10 scenarios | Use a "macro path x company execution" matrix; add 1-2 key exogenous variables to sensitivity, such as real rates, commodities, FX, credit spreads, or freight |
| Step 11 reverse check | Also reverse-engineer the rates/FX/commodity/credit/policy path implied by current price and compare with the base case |
| Step 12 convergence | Explicitly separate value from company execution versus value from external-regime repricing |

---

## Part 5 - Industry Adaptation

Use only the industry checklist most relevant to the target company. Industry checklists are supplements and must not replace the Step 0-12 workflow.

| Industry | Core Variables | Key Judgments and Macro Supplements |
|----------|----------------|-------------------------------------|
| Manufacturing / Auto Parts / Industrials | Shipments, ASP, content per vehicle/unit, utilization, capex, customer concentration | Project ramp often matters more than headline revenue growth; watch manufacturing investment, downstream capex, FX, tariffs, raw materials, freight |
| Consumer | Same-store sales, channel expansion, terminal discounts, inventory health, pricing power, repeat purchase | Separate real demand from restocking plus price hikes; watch income, employment, confidence, real-estate wealth effect, food and raw-material costs |
| Internet / Software / Platforms | User growth and retention, paid conversion, ARPU, CAC, contribution margin, SBC | Determine whether operating leverage is the main valuation elasticity; watch ad budgets, IT spending, funding environment, real rates |
| Semiconductors / Hardware | ASP, yield, utilization, channel inventory, design-win pipeline, technology generation | Cycle position determines earnings scope; watch electronics demand, server/AI capex, export controls, FX, equipment investment cycle |
| Banks / Insurance / Brokers | ROE, asset quality, provisions, capital adequacy, funding cost, investment-income sustainability | Balance-sheet logic comes first; do not use EV metrics; watch yield curve, credit cost, real estate/employment, regulation, capital-market activity |
| Cyclicals / Resources / Chemicals / Shipping | Price cycle position, inventory level, supply constraints, cost curve, new capacity | Use mid-cycle earnings or asset value and avoid extrapolating peak-cycle conditions; watch global demand, energy, USD, routes, sanctions, trade policy |
| Pre-profit Biotech / Early Deep Tech | Milestone probability, cash burn, financing need, commercialization path | Provide value ranges and event sensitivity rather than false precision; watch financing environment, rates, approval cadence, payer policy, export controls |

---

## Part 6 - Output Format

Two parts: **summary conclusion first, analysis report second**.

### Process-to-Report Mapping

Steps 0-12 are the internal analysis process, not the final report headings. The final report should merge step outputs into reader-friendly narrative sections:

| Analysis Steps | Report Location |
|----------------|-----------------|
| Steps 0-2 | Company overview, scope, operating facts, standardized earnings |
| Steps 3-5.5 | Business model, competition, core variables, base-rate calibration |
| Steps 6-10 | Forecasts, valuation, scenarios, sensitivity |
| Steps 11-12 | Reverse check, risks, conclusion, tracking framework |

### Summary Conclusion

Include at least:

- Company name, ticker, current share price
- Whether the Macro Overlay is enabled
- 12-month Base target price plus Bull/Bear range
- Optional probability-weighted target price
- Conclusion confidence and main uncertainty sources
- Base-case core forecasts: revenue, net income, EPS/FCF, plus valuation method/parameters
- Upside/downside versus current share price
- One-sentence macro path if enabled
- Valuation logic in 1-2 sentences
- Largest upside catalyst and largest downside risk
- 2-3 key tracking indicators
- Disclaimer

**Summary template** (numbers are placeholders):

```markdown
# [Company Name] ([Ticker]) Valuation Conclusion

> Disclaimer: This analysis is not investment advice. It is an independent valuation exercise based on public information. Markets involve risk; invest with caution.

**Current Share Price:** [Currency] XX.XX; **Macro Overlay:** Enabled / Not enabled
**12-Month Target Price:** Base [Currency] XX.XX (+XX%); Bull [Currency] XX.XX; Bear [Currency] XX.XX; probability-weighted (optional) [Currency] XX.XX
**Conclusion Confidence:** High / Medium / Low; **Main Uncertainty:** [1-2 items]
**Core Assumptions:** FY20XXE revenue XXX, net income XXX, XXx PE / XX% WACC
**Macro Base Path:** [If enabled, explain in one sentence]
**Valuation Logic:** [1-2 sentences]
**Catalyst and Risk:** largest upside catalyst [one sentence]; largest downside risk [one sentence]
**Key Tracking Indicators:** [2-3 indicators]
```

### Analysis Report

Write the report for human readers, not as a checklist-style output. Use coherent paragraphs that connect facts, assumptions, valuation logic, and risks into a readable investment narrative. Headings are encouraged for navigation.

Use bullets, numbered lists, and tables only when they materially improve clarity, such as for scenario assumptions, sensitivity results, valuation bridges, or tracking indicators.

Organize the narrative around company overview and scope; operating facts and historical attribution; standardized earnings; business model and competitive position; core variables and forecasts; valuation; scenarios and sensitivity; reverse check and risks; and conclusion plus tracking framework.

If the Macro Overlay is enabled, integrate macro transmission and scenario paths into the relevant sections rather than adding a mechanical appendix.

**Narrative principle**: key judgments must show their premises, reasoning chain, and falsification conditions naturally in prose. The reader should see how X leads to Y, which step is weakest, and what would invalidate it without piecing the argument together from fragmented bullets. Any rollback triggered during analysis must be disclosed.

Adjust section detail to the company.

**List discipline**: avoid list-heavy writing by default. Do not turn every step, source, assumption, or risk into a bullet list. Use bullets only for compact comparison, multi-item evidence, scenario/sensitivity summaries, or final monitoring checklists.

If a list is used, introduce it with a short explanatory sentence and return to prose afterward.

### Error-Prevention Checklist

Before final output, in addition to Part 1 hard constraints, confirm:

1. Order value, nominated project value, and letters of intent are not revenue; management guidance is an assumption source, not fact.
2. Industry narrative does not replace the four hard variables: revenue, margin, cash flow, and share count.
3. Geopolitics is mapped to concrete transmission channels, such as demand, supply, cost, FX, or risk premium, rather than listed as a vague risk.
4. Evidence gaps, material counter-evidence, and rollback triggers are disclosed in the report.

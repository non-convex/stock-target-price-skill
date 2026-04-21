# Stock Target Price Skill

[中文文档](README_CN.md)

A structured prompt framework for AI agents to perform systematic, auditable stock valuation analysis — with an **adaptive dynamic search loop** and a conditionally activated macro overlay. It builds an operational fact base from primary sources through dynamic iterative research, determines whether macro-level reasoning is needed, standardizes earnings and cash flows, identifies key value drivers, selects appropriate valuation methods, and stress-tests conclusions through scenario analysis, sensitivity testing, and falsification frameworks.

## What It Does

When triggered, this skill guides the AI agent through a rigorous **13-step valuation process** (Steps 0–12) with an optional **macro-enhanced module (M1–M4)** that activates when exogenous variables significantly drive company value. The **Adaptive Search Loop** and **Dynamic Rollback** run through the entire flow to prevent linear extrapolation from history.

### Iterative Research Methodology

The framework treats valuation as iterative reasoning, not a one-shot search followed by template filling.

**1. Adaptive Search Loop** — every information-gathering action (search, document read, data lookup) must complete a cycle, so no blind searching occurs:

- **Before**: state the specific question, expected signals (confirming / disconfirming / surprising)
- **After**: evaluate answer completeness, classify new content (fact / inference / assumption), capture surprises
- **Next-step decision** (mandatory, one of five): Advance / Dig deeper / Pivot / Rollback / Mark gap

Two consecutive searches with no new information trigger a diagnostic pause — no idle loops.

**2. Dynamic Rollback** — if any Step surfaces new key variables or invalidates locked ones, the analysis explicitly returns to Step 5 and records the rollback in the final report — no hidden fixes.

### Core Analysis Flow

| Step | Description |
|------|-------------|
| 0 | Define the valuation subject, accounting scope, and macro exposure |
| 1 | Build a historical operational fact base (P&L, balance sheet, cash flow) |
| 2 | Standardize earnings and cash flows (strip out one-offs and macro distortions) |
| 3 | Understand the business model, industry structure, management, and macro transmission |
| 4 | **Mine and validate recent news** — broad search for incremental information, cross-verify against primary sources, deep-dive on high-impact leads |
| 5 | **Lock in 1–3 core variables and perform targeted validation** (sub-questions, sources, leading indicators, update actions) before forecasting |
| 6 | Build a "by-segment + by-driver + by-scenario" forecast framework |
| 7 | Validate forecasts against capital efficiency, cash flow quality, and balance sheet resilience |
| 8 | Select valuation methods and determine valuation parameters |
| 9 | Bridge enterprise value to equity value per share |
| 10 | Run 3-scenario analysis (macro path x company execution matrix) and sensitivity testing |
| 11 | Reverse-engineer implied expectations, process the counter-evidence list, and compare against consensus |
| 12 | Converge into an explainable, trackable, and updatable valuation conclusion |

### Macro-Enhanced Module (conditionally activated)

The macro module activates when the company's value is significantly driven by rates, FX, commodities, tariffs, geopolitics, or other exogenous variables:

| Step | Description |
|------|-------------|
| M1 | Define the current macro regime using 3–6 key exogenous variables |
| M2 | Construct Bear / Base / Bull macro scenario paths |
| M3 | Map each macro variable to specific company-level transmission channels |
| M4 | Define a monitoring dashboard with leading indicators and invalidation conditions |

All macro-related additions to the main flow (e.g., stress testing at Step 7, parameter consistency at Step 8, implied-path check at Step 11) are **consolidated in a single table** inside the module, so the main flow reads cleanly as a macro-neutral narrative.

The output starts with a **valuation conclusion summary** (target price, scenarios, key assumptions, macro path) upfront, followed by a narrative report in which each key judgment's premise, reasoning chain, and falsification conditions are made visible — not hidden behind conclusory phrases like "therefore" or "overall".

## Industry Coverage

The skill includes tailored analytical frameworks for:

- **Manufacturing / Auto Parts / Industrials** — volume, ASP, utilization, capex + macro: manufacturing investment, tariffs, FX, input costs
- **Consumer** — same-store, channel expansion, pricing power, inventory + macro: income, employment, consumer confidence, wealth effects
- **Internet / Software / Platforms** — user growth, ARPU, SBC, operating leverage + macro: ad budgets, IT spend, funding environment, real rates
- **Semiconductors / Hardware** — ASP, yield, utilization, cycle position + macro: global electronics demand, AI capex, export controls
- **Banks / Insurance / Brokers** — ROE, asset quality, provisions, capital adequacy + macro: yield curve, credit costs, regulatory direction
- **Cyclicals / Resources / Chemicals / Shipping** — price cycle, supply constraints, cost curves + macro: global demand, energy, USD, trade policy
- **Pre-revenue Biotech / Deep Tech** — milestone probability, cash runway, event sensitivity + macro: funding environment, rates, regulatory pace

## Installation

### Quick install (recommended)

If your AI agent supports installing skills (e.g., Claude Code, OpenClaw), just tell it:

```
Install the stock valuation skill from https://github.com/non-convex/stock-target-price-skill
```

The agent will automatically download and configure the skill.

### Manual install

```bash
git clone https://github.com/non-convex/stock-target-price-skill.git

# For Claude Code:
mkdir -p ~/.claude/skills/stock_target_price
cp stock-target-price-skill/SKILL.md ~/.claude/skills/stock_target_price/SKILL.md
```

### Use as a standalone prompt

Everything is consolidated in a single `SKILL.md` file. You can:

1. **As a skill**: Load `SKILL.md` directly — the agent can execute the full valuation workflow.
2. **As a system prompt**: Use the full `SKILL.md` as your system prompt.
3. **As a tool/skill**: Integrate `SKILL.md` into your agent framework (e.g., LangChain, AutoGPT, custom agents).
4. **As a reference**: Use the 13-step framework plus the dynamic research loop as a checklist for your own valuation workflow.

### Verify it works

Ask your AI agent:

```
Give me a target price for AAPL
```

or

```
Tesla 2026 target price analysis
```

## Usage Examples

**English:**
```
Analyze NVIDIA and give me a 12-month target price
```

**Chinese:**
```
给出比亚迪股票2026年的目标价
```

The agent will automatically search for financial data, build an earnings model, determine whether to activate the macro module based on the company's exposure, and produce a structured valuation with bull/base/bear scenarios.

## Output Format

The analysis output follows this structure:

1. **Valuation Conclusion** (upfront) — target price, 3 scenarios, optional probability-weighted target, key assumptions, macro path summary, upside/downside, catalysts & risks, tracking indicators, disclaimer
2. **Full Analysis** (10 narrative sections, + M1–M4 if macro activated) — complete derivation from fact base to final judgment

## Customization

All content is consolidated in a single `SKILL.md`, organized in six parts:

- Part 1 — Control rules
- Part 2 — Dynamic research engine (adaptive search, dynamic rollback)
- Part 3 — Core workflow (Steps 0–12)
- Part 4 — Macro-enhanced module (conditionally activated)
- Part 5 — Industry playbooks
- Part 6 — Output format and error-prevention checklist

## Requirements

- An AI agent with web search capability (for fetching financial data)
- A large-context LLM (128K+ tokens recommended for comprehensive analysis)

## Disclaimer

This skill produces analysis for educational and research purposes only. It does not constitute investment advice. Always do your own due diligence before making investment decisions.

## License

[CC BY-NC 4.0](LICENSE) — free for research and learning; commercial use is not permitted.

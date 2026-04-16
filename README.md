# Stock Target Price Skill

[中文文档](README_CN.md)

A structured prompt framework for AI agents to perform systematic, auditable stock valuation analysis — with a conditionally activated macro overlay. It builds an operational fact base from primary sources, determines whether macro-level reasoning is needed, standardizes earnings and cash flows, identifies key value drivers, selects appropriate valuation methods, and stress-tests conclusions through scenario analysis, sensitivity testing, and falsification frameworks.

## What It Does

When triggered, this skill guides the AI agent through a rigorous **13-step valuation process** with an optional **macro-enhanced module (M1–M4)** that activates when exogenous variables significantly drive company value:

### Core Analysis Flow

| Step | Description |
|------|-------------|
| 0 | Define the valuation subject, accounting scope, and macro exposure |
| 1 | Build a historical operational fact base (P&L, balance sheet, cash flow) |
| 2 | Standardize earnings and cash flows (strip out one-offs and macro distortions) |
| 3 | Understand the business model, industry structure, management, and macro transmission |
| 4 | Lock in 1–3 core variables that truly drive value (including exogenous variables if applicable) |
| 5 | Build a "by-segment + by-driver + by-scenario" forecast framework |
| 6 | Validate forecasts against capital efficiency, cash flow quality, and balance sheet resilience |
| 7 | Select valuation methods that match the business model |
| 8 | Determine valuation parameters based on quality, cycle, risk premium, and implied expectations |
| 9 | Bridge enterprise value to equity value per share |
| 10 | Run 3-scenario analysis (macro path x company execution matrix) and sensitivity testing |
| 11 | Reverse-engineer implied expectations, decompose market pricing, and run falsification checks |
| 12 | Converge into an explainable, trackable, and updatable valuation conclusion |

### Macro-Enhanced Module (conditionally activated)

The macro module activates when the company's value is significantly driven by rates, FX, commodities, tariffs, geopolitics, or other exogenous variables:

| Step | Description |
|------|-------------|
| M1 | Define the current macro regime using 3–6 key exogenous variables |
| M2 | Construct Bear / Base / Bull macro scenario paths |
| M3 | Map each macro variable to specific company-level transmission channels |
| M4 | Define a monitoring dashboard with leading indicators and invalidation conditions |

The output starts with a **valuation conclusion summary** (target price, scenarios, key assumptions, macro path) upfront, followed by the full analytical walkthrough.

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

The core of this project is `SKILL.md` — a self-contained prompt that can be fed into any LLM or AI agent capable of web search. You can:

1. **As a system prompt**: Paste the content of `SKILL.md` as a system prompt, then ask the agent to analyze a specific stock.
2. **As a tool/skill**: Integrate into your agent framework (e.g., LangChain, AutoGPT, custom agents) as a callable prompt template.
3. **As a reference**: Use the 13-step framework as a checklist for your own valuation workflow.

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
2. **Full Analysis** (13 steps + M1–M4 if activated) — complete derivation from fact base to final judgment

## Customization

You can modify `SKILL.md` to:

- Adjust the valuation framework steps
- Tune the macro module trigger conditions
- Add or remove industry-specific rules
- Change the output format template
- Add additional error-prevention principles

## Requirements

- An AI agent with web search capability (for fetching financial data)
- A large-context LLM (128K+ tokens recommended for comprehensive analysis)

## Disclaimer

This skill produces analysis for educational and research purposes only. It does not constitute investment advice. Always do your own due diligence before making investment decisions.

## License

[CC BY-NC 4.0](LICENSE) — free for research and learning; commercial use is not permitted.

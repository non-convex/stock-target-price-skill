# Stock Target Price Skill

[中文文档](README_CN.md)

A structured prompt framework for AI agents to perform systematic, auditable stock valuation analysis. It builds an operational fact base from primary sources, standardizes earnings and cash flows, identifies key value drivers, selects appropriate valuation methods, and stress-tests conclusions through scenario analysis, sensitivity testing, and falsification frameworks.

## What It Does

When triggered, this skill guides the AI agent through a rigorous **13-step valuation process**:

| Step | Description |
|------|-------------|
| 0 | Define the valuation subject and accounting scope |
| 1 | Build a historical operational fact base (P&L, balance sheet, cash flow) |
| 2 | Standardize earnings and cash flows (strip out one-offs) |
| 3 | Understand the business model, industry structure, and value chain position |
| 4 | Lock in 1-3 core variables that truly drive value |
| 5 | Build a "by-segment + by-driver" forecast framework |
| 6 | Validate forecasts against capital efficiency and cash flow quality |
| 7 | Select valuation methods that match the business model |
| 8 | Determine valuation parameters based on quality, cycle, and implied expectations |
| 9 | Bridge enterprise value to equity value per share |
| 10 | Run 3-scenario analysis and key variable sensitivity |
| 11 | Reverse-engineer implied expectations and run falsification checks |
| 12 | Converge into an explainable valuation conclusion |

The output starts with a **valuation conclusion summary** (target price, scenarios, key assumptions) upfront, followed by the full analytical walkthrough.

## Industry Coverage

The skill includes tailored analytical frameworks for:

- **Manufacturing / Auto Parts / Industrials** - volume, ASP, utilization, capex
- **Consumer** - same-store, channel expansion, pricing power, inventory
- **Internet / Software / Platforms** - user growth, ARPU, SBC, operating leverage
- **Semiconductors / Hardware** - ASP, yield, utilization, cycle position
- **Banks / Insurance / Brokers** - ROE, asset quality, provisions, capital adequacy
- **Cyclicals / Resources / Chemicals / Shipping** - price cycle, supply constraints, cost curves
- **Pre-revenue Biotech / Deep Tech** - milestone probability, cash runway, event sensitivity

## Installation

### Quick install (recommended)

If your AI agent supports installing skills via GitHub URL (e.g., Claude Code, OpenClaw), simply provide:

```
https://github.com/non-convex/stock-target-price-skill
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

The agent will automatically search for financial data, build an earnings model, and produce a structured valuation with bull/base/bear scenarios.

## Output Format

The analysis output follows this structure:

1. **Valuation Conclusion** (upfront) - target price, 3 scenarios, key assumptions, upside/downside, catalysts & risks, disclaimer
2. **Full Analysis** (13 steps) - complete derivation from fact base to final judgment

## Customization

You can modify `SKILL.md` to:

- Adjust the valuation framework steps
- Add or remove industry-specific rules
- Change the output format template
- Add additional error-prevention principles

## Requirements

- An AI agent with web search capability (for fetching financial data)
- A large-context LLM (128K+ tokens recommended for comprehensive analysis)

## Disclaimer

This skill produces analysis for educational and research purposes only. It does not constitute investment advice. Always do your own due diligence before making investment decisions.

## License

[MIT](LICENSE)

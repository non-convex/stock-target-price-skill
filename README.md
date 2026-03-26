# Stock Target Price Skill for Claude Code

[中文文档](README_CN.md)

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill that performs systematic, auditable stock valuation analysis. It builds an operational fact base from primary sources, standardizes earnings and cash flows, identifies key value drivers, selects appropriate valuation methods, and stress-tests conclusions through scenario analysis, sensitivity testing, and falsification frameworks.

## What It Does

When triggered, this skill guides Claude through a rigorous **13-step valuation process**:

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

### Option 1: Clone and symlink (recommended)

```bash
# Clone this repo
git clone https://github.com/non-convex/stock-target-price-skill.git

# Create a symlink in your Claude Code skills directory
# macOS / Linux:
ln -s "$(pwd)/stock-target-price-skill/SKILL.md" \
      ~/.claude/skills/stock_target_price/SKILL.md

# Windows (PowerShell as Admin):
New-Item -ItemType SymbolicLink `
  -Path "$env:USERPROFILE\.claude\skills\stock_target_price\SKILL.md" `
  -Target "$(Get-Location)\stock-target-price-skill\SKILL.md"
```

### Option 2: Direct copy

```bash
# Create the skill directory
mkdir -p ~/.claude/skills/stock_target_price

# Copy the skill file
cp SKILL.md ~/.claude/skills/stock_target_price/SKILL.md
```

### Verify installation

After installing, restart Claude Code. You should see `stock_target_price` listed as an available skill. Then simply ask:

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

The skill will automatically search for financial data, build an earnings model, and produce a structured valuation with bull/base/bear scenarios.

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

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI, desktop app, or IDE extension
- Web search capability enabled (for fetching financial data)
- A Claude model with sufficient context (Opus 4.6 recommended for comprehensive analysis)

## Disclaimer

This skill produces analysis for educational and research purposes only. It does not constitute investment advice. Always do your own due diligence before making investment decisions.

## License

[MIT](LICENSE)

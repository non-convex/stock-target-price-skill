# Stock Target Price Skill — Claude Code 股票估值分析技能

一个用于 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) 的股票估值分析技能。基于第一手材料搭建经营事实底座，完成标准化盈利与现金流处理，识别关键价值驱动因素，选择匹配的估值方法，并通过情景分析、敏感性测试与反证框架校验结论。

## 功能概述

触发后，该技能会引导 Claude 完成一套严谨的 **13 步估值流程**：

| 步骤 | 内容 |
|------|------|
| 第 0 步 | 界定估值对象与会计口径 |
| 第 1 步 | 搭建历史经营事实底座（利润表、资产负债表、现金流） |
| 第 2 步 | 标准化盈利与现金流（剥离一次性项目） |
| 第 3 步 | 理解商业模式、行业结构与价值链位置 |
| 第 4 步 | 锁定真正驱动价值的 1–3 个核心变量 |
| 第 5 步 | 建立"分业务 + 分驱动"的预测框架 |
| 第 6 步 | 用资本效率和现金流质量校验经营预测 |
| 第 7 步 | 选择与商业模式匹配的估值方法 |
| 第 8 步 | 基于质量、周期与隐含预期决定估值参数 |
| 第 9 步 | 将企业价值桥接到每股股权价值 |
| 第 10 步 | 三情景分析与关键变量敏感性测试 |
| 第 11 步 | 反向预期校验与反证检查 |
| 第 12 步 | 收敛为可解释的估值判断 |

输出以**估值结论摘要**（目标价、三情景、核心假设）开头，随后展开完整分析推导过程。

## 行业覆盖

该技能内置了针对不同行业的分析框架：

- **制造业 / 汽车零部件 / 工业** — 出货量、ASP、产能利用率、资本开支
- **消费** — 同店增长、渠道扩张、提价能力、库存
- **互联网 / 软件 / 平台** — 用户增长、ARPU、股票薪酬、经营杠杆
- **半导体 / 硬件** — ASP、良率、利用率、周期位置
- **银行 / 保险 / 券商** — ROE、资产质量、拨备、资本充足率
- **周期 / 资源 / 化工 / 航运** — 价格周期、供给约束、成本曲线
- **未盈利生物科技 / 早期硬科技** — 里程碑概率、现金消耗、事件敏感性

## 安装方法

### 方式一：克隆并创建软链接（推荐）

```bash
# 克隆仓库
git clone https://github.com/non-convex/stock-target-price-skill.git

# 创建技能目录的软链接
# macOS / Linux:
mkdir -p ~/.claude/skills/stock_target_price
ln -s "$(pwd)/stock-target-price-skill/SKILL.md" \
      ~/.claude/skills/stock_target_price/SKILL.md

# Windows (以管理员身份运行 PowerShell):
mkdir "$env:USERPROFILE\.claude\skills\stock_target_price" -Force
New-Item -ItemType SymbolicLink `
  -Path "$env:USERPROFILE\.claude\skills\stock_target_price\SKILL.md" `
  -Target "$(Get-Location)\stock-target-price-skill\SKILL.md"
```

### 方式二：直接复制

```bash
# 创建技能目录
mkdir -p ~/.claude/skills/stock_target_price

# 复制技能文件
cp SKILL.md ~/.claude/skills/stock_target_price/SKILL.md
```

### 验证安装

安装后重启 Claude Code，你应该能在可用技能列表中看到 `stock_target_price`。然后直接输入：

```
给出比亚迪股票2026年的目标价
```

或

```
分析英伟达，给出12个月目标价
```

## 使用示例

```
贵州茅台目标价分析
```

```
分析腾讯控股，给出2026年目标价和三情景区间
```

```
Analyze AAPL and give me a 12-month target price
```

该技能会自动搜索财务数据、构建盈利模型，并输出包含乐观/基准/悲观三种情景的结构化估值分析。

## 输出格式

分析输出遵循以下结构：

1. **估值结论**（置顶） — 目标价、三情景区间、核心假设、上行/下行空间、催化剂与风险、免责声明
2. **完整分析过程**（13 步） — 从事实底座到最终判断的完整推导

## 自定义

你可以修改 `SKILL.md` 来：

- 调整估值框架的步骤
- 增减行业适配规则
- 修改输出格式模板
- 添加额外的防错原则

## 环境要求

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI、桌面应用或 IDE 插件
- 启用网页搜索功能（用于获取财务数据）
- 建议使用大上下文模型（推荐 Opus 4.6 以获得最佳分析效果）

## 免责声明

本技能产出的分析仅供学习和研究用途，不构成任何投资建议。投资决策前请务必自行做好尽职调查。市场有风险，投资需谨慎。

## 开源许可

[MIT](LICENSE)

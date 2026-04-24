# Repository Guidelines

## Project Structure & Module Organization

This repository is a documentation-only AI skill package:

- `SKILL.md` — canonical skill prompt and valuation workflow.
- `README.md` — English overview, installation, usage, requirements, and license notes.
- `README_CN.md` — Chinese companion README; keep it aligned with `README.md`.
- `LICENSE` — CC BY-NC 4.0 license text.

There are no source-code modules, tests, build artifacts, or asset directories. Avoid generated files unless explicitly needed.

## Build, Test, and Development Commands

No build system is required. Use these checks before submitting:

```powershell
rg -n "TODO|FIXME|TBD" .
git diff --check
git status --short
```

- `rg` finds unresolved placeholders or accidental notes.
- `git diff --check` catches trailing whitespace and patch formatting issues.
- `git status --short` confirms the intended files are changed.

For manual checks, copy `SKILL.md` into an agent skill directory and try `Analyze NVIDIA and give me a 12-month target price`.

## Coding Style & Naming Conventions

Write Markdown in UTF-8. Use concise headings and short paragraphs. Preserve the `SKILL.md` structure: six major parts, numbered workflow steps, and compact process tables. When behavior changes, update both READMEs.

Use terms such as `Adaptive Search Loop`, `Dynamic Rollback`, `Base/Bull/Bear`, and `macro-enhanced module` consistently. Keep examples realistic but non-promissory.

## Testing Guidelines

There is no automated test suite. Validate changes by reading rendered Markdown and checking that:

- Step numbering remains consistent from Step 0 through Step 12.
- The macro module remains conditional, not mandatory.
- Output-format examples still include conclusion, scenarios, assumptions, risks, and disclaimer.
- Financial-language changes do not imply personalized investment advice.

## Commit & Pull Request Guidelines

Recent commits use short, imperative English summaries, for example `Refactor skill into modular prompt structure`. Follow that style: one focused change per commit, no trailing punctuation.

Pull requests should include a brief purpose statement, a summary of changed files, and any manual validation performed. Link related issues when available. Screenshots are usually unnecessary unless rendered Markdown formatting is the focus.

## Security, Compliance & Encoding Notes

Do not add API keys, proprietary market data, or paid-source excerpts. Preserve the educational/research disclaimer and the CC BY-NC license constraints. On Windows PowerShell, set UTF-8 output before reading Chinese text:

```powershell
[Console]::OutputEncoding=[System.Text.UTF8Encoding]::new()
$env:PYTHONIOENCODING='utf-8'
```

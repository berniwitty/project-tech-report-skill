# project-tech-report — Project Technical Report Skill for Claude Code

[中文](README.md) | **English**

Turns a finished LLM / ML project into a complete technical report with a fixed structure, written for **learning, interviews, and résumé writing**. The output is a finished document, not a fill-in-the-blanks skeleton.

The skill's instructions and the reports it produces are in Chinese, because the target readers are Chinese-speaking interview candidates. The structure and rules below apply regardless of language.

## What the report looks like

Seven top-level sections, always in this order:

```
Title
Read-me-first callout (purpose, résumé disclaimer, companion material, version, status, project positioning)
Document organisation (one arrow chain + one line per section)
Abstract (project purpose / main conclusions / tech stack)
Part 1: Technical report
    1. Project goals
    2. Overall approach (monospace flowchart)
    3..N. Stage k: goals / evaluation / core method / controlled comparison / stage conclusion
    N+1. Cross-stage analysis
Part 2: Theory you should master (per topic: matching practice → what problem it solves → data and objective → link to this project's results → pitfalls)
Part 3: Interview questions (per question: 💡 approach + 🗣 reference answer)
Résumé examples and how to use the project (important note / two usage modes / résumé draft)
```

Hard rules: every core-method subsection opens with "**What this section must make clear**" and closes with "In summary"; every controlled comparison has the four blocks "existing result / theoretical analysis / next steps / conclusion"; every stage conclusion carries a "**Core result**" callout; every number carries its denominator; when several variables change at once, write "bundled change" and leave attribution to ablations; negative results are reported with their mechanism; a route with no measured accuracy is a "cost conclusion", not a "negative result"; no metaphors, no vague pronouns.

The format follows the report *Post-training and Deploying Local Small Models for Structured Agent Output* published on Xiaohongshu by the account 不转到大模型不改名; the transcription is in [`references/example-report-excerpt.md`](references/example-report-excerpt.md).

## Install

macOS / Linux / Git Bash:

```bash
git clone https://github.com/berniwitty/project-tech-report-skill ~/.claude/skills/project-tech-report
```

Windows PowerShell:

```powershell
git clone https://github.com/berniwitty/project-tech-report-skill "$env:USERPROFILE\.claude\skills\project-tech-report"
```

Restart the Claude Code session and the skill is picked up.

## Usage

Say any of the following in Claude Code, or type `/project-tech-report`:

- "write the project technical report from the template"
- "turn this project into a technical report"
- "project study report", "interview crash material", "final report"

The skill first asks for three inputs: the project's sources of truth (docs, lab notes, result tables, configs, code), the résumé paragraph (if any), and existing interview notes (if any). The report is written to the project's `docs/TECH_REPORT.md`; heading levels are chosen so the file pastes into Notion as heading blocks.

Difference from `llm-interview-notes`: that skill produces résumé-driven Q&A for memorisation only; this one produces a full narrative report in which theory and résumé are part of the body and the Q&A is one section.

## Files

| File | Purpose |
|---|---|
| [`SKILL.md`](SKILL.md) | The rules: overall structure, definition and requirements of every section, writing conventions, delivery and checklist |
| [`templates/REPORT_TEMPLATE.md`](templates/REPORT_TEMPLATE.md) | A fill-in skeleton with a prompt line for every section |
| [`references/example-report-excerpt.md`](references/example-report-excerpt.md) | Transcription of the reference report, for matching format and tone |

## Example output

The ShopWeaver project (multi-agent distillation and data-flywheel post-training of Qwen3-8B on the ShopSimulator benchmark) rewritten with this template: `docs/TECH_REPORT.md` in the ShopWeaver repository.

## License

MIT

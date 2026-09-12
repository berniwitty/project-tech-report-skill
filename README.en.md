# project-tech-report — Project Technical Report Skill for Claude Code

[中文](README.md) | **English**

Turns a finished LLM / ML project into a complete technical report with a fixed structure, written for **learning, interviews, and résumé writing**. The output is a finished document, not a fill-in-the-blanks skeleton.

The skill's instructions and the reports it produces are in Chinese, because the target readers are Chinese-speaking interview candidates. The structure and rules below apply regardless of language.

## What the report looks like

Fixed top-level sections, always in this order:

```
Title
Read-me-first callout (who this is written for / how to read the numbers / the project in one line)
Abstract (project purpose / main conclusions / tech stack)
Part 1: Technical report
    1. What the task is and why it is hard (a concrete example / grading rules / all metrics on the same example / scenario table / where the baseline loses)
    2. Evaluation calibration: prove the ruler is correct first
    3..N. Stage k: what this step does / method and results / controlled comparison / stage conclusion
    N+1. Cross-stage analysis (per-stage contribution + comparison against the external benchmark)
Part 2: Fundamentals an interviewer will dig into (0. sort out the vocabulary; then one section per method: mechanism / data and objective with a hand-worked example / link to this project / limits and pitfalls)
Part 3: Interview questions (per question: 💡 approach + 🗣 reference answer)
Résumé paragraph and how to use it (two usage modes / the résumé verbatim / caveats to state proactively in the interview)
Appendix: glossary
```

Three principles that run through the whole report:

1. **The goal is the task itself, not beating someone.** The opening answers what the task is, why it is hard, and which quantity is being raised, and it carries a dedicated paragraph on "what was explicitly out of scope at kick-off". A score comparison is part of the results, not the founding goal.
2. **An external benchmark appears in exactly two places**: calibrating the evaluator, and one comparison table near the end of the body. That table must cover every scenario including the ones where the project loses, and must state three prerequisites together: whether the training data is the same, whether the training procedure is the same, and whether the sample sizes are the same.
3. **Readable with zero background.** Every term is explained where it first appears, all metrics are computed on one shared example, and a glossary closes the document.

Hard rules: every controlled comparison has the four blocks "existing result / theoretical analysis / next steps / conclusion"; every stage-conclusion callout states the caveats that must be raised proactively; every number carries its denominator; when several variables change at once, write "bundled change" and leave attribution to ablations; negative results are reported with their mechanism; a route with no measured accuracy is a "cost conclusion", not a "negative result"; the résumé text is never edited, the report aligns to it; no metaphors, no vague pronouns; cut anything an interviewer would not ask about, such as file paths, script names, and ops details.

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

The skill first asks for four inputs: the kick-off documents (spec, pre-registration, goals and non-goals), the sources of truth (lab notes, result tables, configs, code), the résumé paragraph (if any), and the external benchmark or paper (if any). The project purpose is taken from the kick-off documents and is never back-derived from the template. The report is written to the project's `docs/TECH_REPORT.md`; heading levels are chosen so the file pastes into Notion as heading blocks, and a named Notion page is rewritten in full.

Difference from `llm-interview-notes`: that skill produces résumé-driven Q&A for memorisation only; this one produces a full narrative report in which the task definition, the theory, and the résumé are all part of the body and the Q&A is one section.

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

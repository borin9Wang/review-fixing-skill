# Review Fixing Skill

[中文](README.md) | English

A Codex skill for revising an existing academic review against a specified manuscript, supervisor comments or reviewer feedback.

**Repository:** `review-fixing-skill` · **Skill name / invocation:** `review-revision` / `$review-revision`

The skill name is retained for compatibility with the original local installation.

## What it does

- Establish the authoritative manuscript and intended revision scope.
- Map comments to concrete problems, locations and changes.
- Preserve correct data, references, native equations and figures.
- Repair weak synthesis and explain the relevance of cited studies.
- Recheck sources affected by the revision without overstating verification coverage.
- Keep metric definitions, model assumptions and essential conditions intact.
- Replace repetitive hedging with specific, supported judgments.
- Synchronize figures, tables, captions, cross-references and supplementary information.
- Inspect actual deliverables and provide a proportionate change explanation.
- Maintain new requirements through stable rule IDs and scoped additions.

The core rules are R01–R12 in [SKILL.md](SKILL.md). [Scoped additions](references/additions.md) contain examples from the source project, applicable only within their stated scope. Instructions are in Chinese; manuscript language follows the user's request.

## Install

Use `review-revision` as the installation directory:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/borin9Wang/review-fixing-skill.git "${CODEX_HOME:-$HOME/.codex}/skills/review-revision"
```

For PowerShell instructions, see the [Chinese installation section](README.md#快速开始). Merge existing personal additions before replacing an installed copy.

## Use

```text
Use $review-revision to address these comments against manuscript V3.
Make changes proportionate to each problem, preserve verified material,
and deliver the revised manuscript with concise explanations and locations.
```

The skill supplies instructions; source retrieval, Word comments, document rendering and plotting depend on tools available in the host environment. It supports author revision rather than journal peer review.

## Extend

Ask the assistant to add, update or replace a rule. General requirements belong in `SKILL.md`; project or journal preferences belong in `references/additions.md`. See [CONTRIBUTING.md](CONTRIBUTING.md).

For drafting a new review, use the companion [review-writing-skill](https://github.com/borin9Wang/review-writing-skill), invoked as `$review-writing`.

## Methodological basis

The skill combines practical revision experience with selected principles from Karen V. Fernandez (2019), [Critically reviewing literature: A tutorial for new researchers](https://doi.org/10.1016/j.ausmj.2019.05.001). Baseline management, revision scope and artifact preservation are practice-derived rules. No original paper PDFs or unpublished manuscripts are included.

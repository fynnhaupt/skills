# AGENTS.md

A collection of agent skills, installed by users via `npx skills@latest add fynnhaupt/skills`. Each skill covers one step of a single everyday workflow.

## Layout

- `skills/<name>/SKILL.md`: one folder per skill, with YAML frontmatter (`name`, `description`). The folder name matches `name`. Supporting files sit beside `SKILL.md`.
- `docs/`: repo-level docs (ADRs, glossary, research notes). Skill content lives in `skills/`.

## Workflow

- Work on a feature branch and land changes through a PR.
- Add a changeset (`pnpm changeset`) for every change that adds or changes a skill. Tooling and docs-only changes need none.
- Run `pnpm format:fix` before finishing; formatting is what CI and the pre-commit hook check.

## Git

- Commit and push only when asked.
- Commit messages: short, imperative, lowercase, no prefix (e.g. `add readme`).
- On a PR, you may merge updates from the base branch into it. Merge the PR itself only when asked.

# AGENTS.md

A collection of agent skills, installed by users via `npx skills@latest add fynnhaupt/skills`. Each skill covers one step of a single everyday workflow.

## Layout

- `skills/<name>/SKILL.md`: one folder per skill, with YAML frontmatter (`name`, `description`). The folder name matches `name`. Supporting files sit beside `SKILL.md`. Skills ship to other repos, so each works in any repo and relies only on its own folder and other skills by name.
- `docs/`: repo-level docs. Skill content lives in `skills/`.
  - `docs/GLOSSARY.md`: the domain terms. Use them.
  - `docs/decisions/`: why things are the way they are. Check before changing something that looks odd.
  - `docs/conventions/`: how work here is done, one file per topic. See [Conventions](#conventions) for when to read each.

## Workflow

- Work on a feature branch and land changes through a PR.
- Add a changeset (`pnpm changeset`) for every change that adds or changes a skill. Tooling and docs-only changes need none.
- Run `pnpm format:fix` before finishing; formatting is what CI and the pre-commit hook check.

## Conventions

- Before any commit, branch, PR, or issue label change, read [docs/conventions/git.md](docs/conventions/git.md).

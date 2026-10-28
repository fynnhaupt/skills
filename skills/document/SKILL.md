---
name: document
description: Record a settled outcome in the project's docs, as a glossary term, a decision, or a convention. Use right after something is decided, or when editing docs/GLOSSARY.md, docs/decisions/, or docs/conventions/.
---

# Document

Write down what was just **settled**, so the next session starts from it instead of rediscovering it. Each settled outcome lands in exactly one home:

| Outcome    | What it is                                         | Home                             | Format                                       |
| ---------- | -------------------------------------------------- | -------------------------------- | -------------------------------------------- |
| Term       | A word this project uses with one fixed meaning    | `docs/GLOSSARY.md`               | [GLOSSARY-FORMAT.md](GLOSSARY-FORMAT.md)     |
| Decision   | A hard-to-reverse choice, made once, with its why  | `docs/decisions/NNNN-<title>.md` | [DECISION-FORMAT.md](DECISION-FORMAT.md)     |
| Convention | A rule for how recurring work is done in this repo | `docs/conventions/<topic>.md`    | [CONVENTION-FORMAT.md](CONVENTION-FORMAT.md) |

Create a file or folder only when its first entry is ready.

## Steps

1. **List the settled outcomes.** Go through the discussion and pull out every outcome the user agreed to, and classify each with the table. An outcome still open stays out; ask the user to settle it or leave it. Done when every agreed outcome is on the list with one type.
2. **Sharpen the language.** For each outcome, check its words against `docs/GLOSSARY.md`. Where a word is fuzzy, overloaded, or clashes with a defined term, propose the canonical term and get the user's pick before writing. Done when every outcome uses glossary terms or adds a new one to the list.
3. **Check for conflicts.** Read the existing entries in each target home. Where an outcome contradicts one, show both to the user and ask which stands. Done when no outcome contradicts a kept entry.
4. **Write each outcome** in its home, using that type's format. A changed outcome edits its existing entry in place. Done when every outcome on the list is written and each meaning lives in one place: decisions and conventions name glossary terms rather than redefine them, and a convention links the decision behind it.
5. **Point to new conventions.** For each conventions topic you created, add a line under `## Conventions` in the project's `AGENTS.md` (or `CLAUDE.md` if that is the one the project uses), creating the section if needed. The line names the moment to read the topic: `- Before any commit, branch, or PR, read [docs/conventions/git.md](docs/conventions/git.md).` Done when every file in `docs/conventions/` has its line.

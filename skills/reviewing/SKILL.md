---
name: reviewing
description: Review a branch's changes on two axes, Standards and Spec, and report the findings side by side. Use when the user wants a branch or PR reviewed, or when another skill needs a review.
---

# Reviewing

Review the diff between `HEAD` and a **base** on two separate axes:

- **Standards**: does the code follow the project's documented standards and avoid the smells in [SMELLS.md](SMELLS.md)?
- **Spec**: does the code do what its spec and task asked, no less and no more?

A change can pass one axis and fail the other, so each axis is reviewed and reported on its own. Read-only: report findings, change no code.

The review comes from a **third perspective**: reviewers who did not write the code and see only the code, the spec, and the standards, never the author's reasoning or account of the change.

## Steps

1. **Pin the base.** The review covers commits only: if `git status` shows uncommitted or untracked changes, tell the user to commit them and stop. Use the base the user named; otherwise the merge-base with the default branch. Check that it resolves and the diff `git diff <base>...HEAD` is not empty. Done when you have the diff command and the commit list `git log <base>..HEAD --oneline`.
2. **Find the spec.** Look for issues referenced in the commits, branch name, or PR body; for a task, read its parent spec too. If none is found, ask the user; if they say there is none, the Spec axis is skipped. Done when you have the spec and task text or the user's "none".
3. **Find the standards**: whatever the project documents about how code is written, such as `AGENTS.md`, `CLAUDE.md`, `CONTRIBUTING.md`, or the docs those point to. Done when you have the list of files.
4. **Review both axes in parallel**, each in its own fresh subagent: not a fork of this conversation, so it starts without your context, and separate so neither sees the other's findings. If you cannot start fresh subagents: when this conversation wrote the code, tell the user to run the review in a new session and stop; otherwise review both axes yourself, one after the other. Give each only the diff command, the commit list, and:
   - **Standards**: the standards files and [SMELLS.md](SMELLS.md) in full. Brief: "Report every place the diff breaks a documented standard, citing the file and rule, and every smell you spot, naming it and quoting the hunk. A documented standard overrides a smell; smells are always judgement calls. Skip what tooling enforces. Under 400 words."
   - **Spec**: the spec and task text. Brief: "Report what the spec asks that is missing or partial, what the diff does that nobody asked for, and what looks implemented but wrong. Quote the spec line for each. Under 400 words."

   Done when both reports are back, or the Spec axis is skipped.

5. **Report** both under `## Standards` and `## Spec` as the reviewers wrote them, without dropping, softening, merging, or reranking findings. End with one line per axis: the number of findings and the worst one. Done when the user has the report.

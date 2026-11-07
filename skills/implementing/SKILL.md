---
name: implementing
description: Implement a piece of work, such as a task, test-first where the project has tests, then review and commit it. Use when the user wants work built, or when another skill needs work built.
---

# Implementing

Build the work in the conversation, such as a **task**, and leave it committed and reviewed on the current branch. Build only what the work asks; anything else you notice goes to the user as a note, not into the code.

Ask the user every question, including a confirmation, through your harness's interactive question tool when it has one (e.g. `AskUserQuestion` in Claude Code), with the likely replies as options; show anything they must review, such as an issue body, as text first. Only without such a tool, type the question as text.

## Steps

1. **Read the work.** For a task issue, read it and its parent spec. Then read the code it touches. Done when you can name the modules it changes and the seams to test.
2. **Build it.** If the project has a test runner, drive the code with the `testing` skill; otherwise build it directly. Run the affected tests and the typecheck, where the project has them, as you go. When the work leaves a choice open that changes behaviour, ask the user instead of guessing. Done when everything the work asks is met, such as every acceptance criterion of a task.
3. **Check it.** Run the full test suite and every check the project uses, such as the typecheck, linter, and formatter. A check that also fails on the base was failing before: report it, don't fix it. Done when every other check passes.
4. **Commit** to the current branch, following the project's commit conventions. Done when `git status` is clean.
5. **Review it** with the `reviewing` skill against the branch's base. Fix every broken standard and every Spec finding, and the smells you agree with; list the smells you leave and why. Check and commit the fixes as in steps 3 and 4. Done when every finding is fixed or listed for the user.

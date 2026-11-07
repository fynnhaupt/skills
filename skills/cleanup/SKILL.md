---
name: cleanup
description: Clean up after a task's PR is merged, and close its spec once every task is done.
argument-hint: <task-issue>
disable-model-invocation: true
---

# Cleanup

Clean up after a **task** whose PR is merged: drop its status labels, remove its worktree and branch, and close its parent **spec** once every task of the spec is done.

Ask the user every question, including a confirmation, through your harness's interactive question tool when it has one (e.g. `AskUserQuestion` in Claude Code), with the likely replies as options; show anything they must review, such as an issue body, as text first. Only without such a tool, type the question as text.

## Steps

1. **Pick the task.** A task is done when its `kind: task` issue is closed by a merged PR. Use the task given as the argument, or else the task of the current branch's PR; if there is neither, list the closed `kind: task` issues that still carry `status: in-progress` and ask which. If the task is not done, tell the user why and stop. Done when you have a done task, its merged PR, and the PR's branch.
2. **Update the labels.** Remove `status: in-progress` from the task issue and any `status:` label from the PR; the merge says done. Done when neither carries a `status:` label.
3. **Remove the worktree and branch.** Remove every git worktree that holds the PR's branch (`git worktree list`), then delete the local branch and, if it still exists, the remote one. If a worktree has uncommitted changes or the local branch has commits the PR does not, show them to the user and ask before removing it. Done when no worktree or branch of the task is left, or the user has chosen to keep it.
4. **Close the spec** once its work is done: every `kind: task` sub-issue of the parent spec is closed, and the docs PR its body names (`Docs: #<pr>`), if any, is merged. If any is still open, tell the user which and stop. Otherwise ask the user, then close the spec as completed. Done when the spec is closed, or you have told the user what still keeps it open.

---
name: to-pr
description: Implement a task on its own branch and open a PR for it.
argument-hint: <task-issue>
disable-model-invocation: true
---

# To PR

Take one **task** from ready to a PR that waits for review. The task's status moves with it: `status: in-progress` on the task issue from start until the merge closes it, and a draft PR from the start that becomes ready with `status: in-review` once built. Before creating a label that does not exist yet, ask the user.

## Steps

1. **Pick the task.** A task is ready when it is an open `kind: task` issue with no status label, no linked PR, and no open "blocked by" issue. If a task was given as the argument, check it is ready; if not, tell the user why and stop. If none was given, list the ready ones and ask which. Done when the user has a ready task confirmed.
2. **Start it.** Add `status: in-progress` to the task issue and assign it to the user (`--add-assignee @me`). Create a branch for it from the up-to-date default branch, named per the project's conventions, or `<type>/<issue-number>/<title>` if it has none, and work in a git worktree of it when possible, so the user's checkout stays untouched. Push it with an empty first commit and open a draft PR to the default branch, titled per the project's conventions, with `Closes #<task>` in the body, the type label from the project's conventions if it defines one, and the user as assignee. Done when the draft PR exists and the label and assignees are set.
3. **Build it** with the `implementing` skill. Done when it has finished and the branch holds its commits.
4. **Hand it to review.** Push the branch. Write the PR body: a summary of the change, the notes and smells `implementing` left for the user, and `Closes #<task>`. Mark the PR ready for review and add `status: in-review`; the task issue keeps `status: in-progress`. Done when the PR is ready with its label and you have given the user its link.

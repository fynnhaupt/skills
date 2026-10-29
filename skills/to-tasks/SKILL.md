---
name: to-tasks
description: Split a spec issue into tasks, filed as its sub-issues.
disable-model-invocation: true
---

# To tasks

Split a **spec** issue into **tasks**: vertical slices, each implemented in one PR, filed as sub-issues of the spec. If the user named no spec issue, ask for it.

## Steps

1. **Read the spec** issue and the code its approach touches. If the spec already has sub-issues, show them to the user and ask whether to add more or stop. Done when you can say which modules each acceptance criterion changes.
2. **Slice it.** Cut the spec into tasks, each a vertical slice that leaves the main branch working once merged. Fewer is better: a spec that fits one PR is one task. Prefer slices that can be worked on in parallel; make a task wait for another only where it needs that task's code. Done when every acceptance criterion of the spec belongs to a task.
3. **File the tasks** as sub-issues of the spec, using [TASK-FORMAT.md](TASK-FORMAT.md), each labelled `kind: task` plus its own type label from the project's conventions if it defines one, with GitHub's "blocked by" dependency for each task that must wait. Link sub-issues and dependencies through `gh api` (`issues/{n}/sub_issues` and `issues/{n}/dependencies/blocked_by`); both take the issue's `id`, not its number. First show the user every title, body, and dependency, naming any label that does not exist yet, and create the issues and missing labels only after they confirm. Done when every task exists and you have given the user their links.

Then tell the user to run `/to-pr` with a task to build it.

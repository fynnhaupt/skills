# Git

- Commit and push only when asked.
- Commit messages: short, imperative, lowercase, no prefix (e.g. `add readme`).
- On a PR, you may merge updates from the base branch into it. Merge the PR itself only when asked.

## Branches, PRs, and labels

Every branch has one type:

| Type    | For                                      | Label           |
| ------- | ---------------------------------------- | --------------- |
| `fix`   | Something isn't working                  | `bug`           |
| `feat`  | New feature or request                   | `enhancement`   |
| `chore` | Maintenance work                         | `chore`         |
| `docs`  | Improvement or addition to documentation | `documentation` |

- Branch name: `<type>/<title>`, type lowercase (e.g. `feat/add-grill-me-skill`). For an issue: `<type>/<issue-id>/<title>` (e.g. `feat/12/add-grill-me-skill`).
- PR title: `<Type>: <title>`, type capitalized (e.g. `Feat: add grill-me skill`). For an issue: `<Type> #<issue-id>: <title>` (e.g. `Feat #12: add grill-me skill`).
- Give issues and PRs the label matching their type.
- Assign a new PR to its creator (`gh pr create --assignee @me`).

## Workflow labels

Specs and tasks are issues; workflow labels carry a prefix so they sort together and don't collide with a project's own labels.

| Label                   | On         | Meaning                                 |
| ----------------------- | ---------- | --------------------------------------- |
| `kind: spec`            | issue      | The issue is a spec.                    |
| `kind: task`            | sub-issue  | The issue is a task of its parent spec. |
| `status: in-progress`   | task issue | The task has started and is not merged. |
| `status: in-review`     | PR         | The PR waits for review.                |
| `status: rework-needed` | PR         | Review asked for changes.               |

- The task issue says the task has started; review status lives on the PR only (see [0003](../decisions/0003-track-review-status-in-pr-labels.md)).
- An open `kind: task` issue with no status label and no linked PR is ready to start.
- Starting a task: add `status: in-progress` to the issue.
- Its PR stays a draft while the task is built. Marking it ready for review: add `status: in-review` to the PR; the issue keeps `status: in-progress` until the merge closes it.
- Asking for changes: swap the PR's `status: in-review` for `status: rework-needed`; after the rework, swap it back.
- Merging the PR closes the task issue; no status label is needed for done.
- Mark a task that waits on another with GitHub's "blocked by" dependency, not a label.
- Ask the user before creating an issue or a missing label.

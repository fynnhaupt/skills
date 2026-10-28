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

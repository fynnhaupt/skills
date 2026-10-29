# Convention format

One file per topic in `docs/conventions/`, named `<topic>.md` (e.g. `git.md`). Add a rule to the topic it belongs to; start a new topic only when none fits.

```md
# Git

- Commit messages: short, imperative, lowercase, no prefix (e.g. `add readme`).
- Commit and push only when asked.
```

- One rule per bullet, written as the action to take.
- Include an example when the rule describes a shape (a name, a message, a title).
- When a decision explains the rule, link it: `(see [0003](../decisions/0003-<title>.md))`.

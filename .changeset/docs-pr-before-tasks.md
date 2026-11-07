---
'@fynnhaupt/skills': minor
---

`to-spec` now commits the docs it records on a `docs` branch, opens a PR for them, and links it from the spec as `Docs: #<pr>`. `to-pr` treats a task as ready only once that docs PR is merged, so every task branches from a default branch that already has the docs.

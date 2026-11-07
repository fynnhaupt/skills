# @fynnhaupt/skills

## 1.3.0

### Minor Changes

- [#34](https://github.com/fynnhaupt/skills/pull/34) [`3a7efd3`](https://github.com/fynnhaupt/skills/commit/3a7efd310529be377e5463fddb72d66181eb85ec) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - Add `cleanup`: after a task's PR is merged, it removes the task's status labels, worktree, and branch, and closes the parent spec once every task is done.

- [#33](https://github.com/fynnhaupt/skills/pull/33) [`e08b960`](https://github.com/fynnhaupt/skills/commit/e08b9600763bbcfe100579b6d37acb581215e18c) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - `to-spec` now commits the docs it records on a `docs` branch, opens a PR for them, and links it from the spec as `Docs: #<pr>`. `to-pr` treats a task as ready only once that docs PR is merged, so every task branches from a default branch that already has the docs.

### Patch Changes

- [#32](https://github.com/fynnhaupt/skills/pull/32) [`b30e21e`](https://github.com/fynnhaupt/skills/commit/b30e21e2f56f9d0cff791f91dc62dbc665438c65) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - Every skill that asks the user something now asks through the harness's interactive question tool (e.g. `AskUserQuestion`) when it has one, instead of typing the question and waiting for a text reply.

- [#30](https://github.com/fynnhaupt/skills/pull/30) [`e7f1cf8`](https://github.com/fynnhaupt/skills/commit/e7f1cf8677bd74442277f792eb0f996a3fdfca12) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - Align wording across skills: default branch in `to-tasks`, an example branch name in `to-pr`, and `implementing` no longer assumes a typecheck or a task's acceptance criteria.

## 1.2.1

### Patch Changes

- [#27](https://github.com/fynnhaupt/skills/pull/27) [`f8b8d68`](https://github.com/fynnhaupt/skills/commit/f8b8d681007d6bbf22b23640ebaae4ad984e19f6) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - ask grilling questions through the harness's interactive question tool

- [#29](https://github.com/fynnhaupt/skills/pull/29) [`6c6e1b1`](https://github.com/fynnhaupt/skills/commit/6c6e1b1726c7e2ec263d84276dec00a9dbad251f) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - phrase grilling questions as the recommendation so Yes accepts it

## 1.2.0

### Minor Changes

- [#18](https://github.com/fynnhaupt/skills/pull/18) [`135bea0`](https://github.com/fynnhaupt/skills/commit/135bea0b55d0a8d92cf4bd88736246dd211e9c09) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - add implementing skill

- [#17](https://github.com/fynnhaupt/skills/pull/17) [`b02e960`](https://github.com/fynnhaupt/skills/commit/b02e9604288f6708de9338df861cbdb9f61c59bb) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - add reviewing skill

- [#20](https://github.com/fynnhaupt/skills/pull/20) [`c62b11a`](https://github.com/fynnhaupt/skills/commit/c62b11a1cca668ff53a9eb2c9ed565139822b516) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - add rework-pr skill

- [#9](https://github.com/fynnhaupt/skills/pull/9) [`4b060f2`](https://github.com/fynnhaupt/skills/commit/4b060f20cff5278ad3384cfcb926aa4d9fdb12a0) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - add scope skill

- [#16](https://github.com/fynnhaupt/skills/pull/16) [`9413cc4`](https://github.com/fynnhaupt/skills/commit/9413cc409211993f0a2476e58391a805edfefd2e) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - add testing skill; specs name the seams to test

- [#19](https://github.com/fynnhaupt/skills/pull/19) [`a01d4c4`](https://github.com/fynnhaupt/skills/commit/a01d4c47995a5a2a38908ec0147765e3c281bf7d) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - add to-pr skill

- [#12](https://github.com/fynnhaupt/skills/pull/12) [`bac6acc`](https://github.com/fynnhaupt/skills/commit/bac6acc6f76e67375d5677de77605e5fdcfa0274) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - add to-spec skill

- [#13](https://github.com/fynnhaupt/skills/pull/13) [`2decf81`](https://github.com/fynnhaupt/skills/commit/2decf816c9f6b5691bfcbe71923141e0c5989199) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - add to-tasks skill

- [#24](https://github.com/fynnhaupt/skills/pull/24) [`fb9e91c`](https://github.com/fynnhaupt/skills/commit/fb9e91cfcb89727d050d249d3a943a48135e42ee) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - documenting lists conventions in docs/CONVENTIONS.md, and AGENTS.md points to it once

- [#22](https://github.com/fynnhaupt/skills/pull/22) [`51b0b14`](https://github.com/fynnhaupt/skills/commit/51b0b14bf50fa5dc8fb5526db7493baafe05b664) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - work in a git worktree when possible in to-pr and rework-pr

- [#22](https://github.com/fynnhaupt/skills/pull/22) [`51b0b14`](https://github.com/fynnhaupt/skills/commit/51b0b14bf50fa5dc8fb5526db7493baafe05b664) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - take the spec, task, or pr as an argument in to-tasks, to-pr, and rework-pr

### Patch Changes

- [#26](https://github.com/fynnhaupt/skills/pull/26) [`5f30146`](https://github.com/fynnhaupt/skills/commit/5f301464f4fe88eac2c8cca58eca60878eac8f7d) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - ship Matt Pocock's license notice with the skills adapted from his

- [#14](https://github.com/fynnhaupt/skills/pull/14) [`1bc0926`](https://github.com/fynnhaupt/skills/commit/1bc0926306a7e6bb1994733425fc2cee9259762d) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - skip the type label when the project defines none

## 1.1.0

### Minor Changes

- [#5](https://github.com/fynnhaupt/skills/pull/5) [`a53b578`](https://github.com/fynnhaupt/skills/commit/a53b57828a669280eec6f6bf29dc1c412b72fad5) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - add documenting skill

- [#8](https://github.com/fynnhaupt/skills/pull/8) [`b17fa66`](https://github.com/fynnhaupt/skills/commit/b17fa66e5de09875d8bad065cb1d5959cf781ba2) Thanks [@fynnhaupt](https://github.com/fynnhaupt)! - add grilling skill

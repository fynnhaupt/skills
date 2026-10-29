# My Skills

<div>
  <img src="https://img.shields.io/badge/Status-WIP-blue" alt="Status">
  <a href="https://github.com/fynnhaupt/skills/actions/workflows/check.yaml">
    <img src="https://github.com/fynnhaupt/skills/actions/workflows/check.yaml/badge.svg" alt="Check">
  </a>
  <a href="https://github.com/fynnhaupt/skills/actions/workflows/release.yaml">
    <img src="https://github.com/fynnhaupt/skills/actions/workflows/release.yaml/badge.svg" alt="Release">
  </a>
</div>

## What is this?

My collection of agent skills I use every day to automate my workflow:

1. **Reusable**: Covers the tasks that come up again and again.
2. **One workflow**: Each skill covers one step, and together they form a single workflow.
3. **Built around GitHub**: Specs and tasks are issues, work lands through PRs, and status lives in labels.
4. **Isolated**: `/to-pr` and `/rework-pr` work in a git worktree when possible, so your own checkout stays untouched.

Every skill here comes from my own everyday work and is refined through use.

## Installation

Install skills with the [Skills CLI](https://github.com/vercel-labs/skills), no package install required:

```sh
npx skills@latest add fynnhaupt/skills
```

## Workflow

Each workflow skill is one step you start yourself; they carry a request to a merged PR:

1. `/scope`: grill a request into its problem, behaviour, boundaries, and acceptance criteria.
2. `/to-spec`: work out the approach and file the spec as a GitHub issue.
3. `/to-tasks <spec-issue>`: split the spec into tasks, filed as its sub-issues.
4. `/to-pr <task-issue>`: implement one task on its own branch and open a PR for review.
5. `/rework-pr <pr>`: make the changes a review asked for and hand the PR back to review.

The workflow skills build on these building blocks, which you can also use on their own:

- `grilling`: question you one decision at a time until a plan holds.
- `documenting`: record terms, decisions, and conventions in `docs/`.
- `testing`: drive code test-first through its seams.
- `implementing`: build a piece of work, check it, commit it, and have it reviewed.
- `reviewing`: review changes against the project's standards and the spec, from fresh subagents.

## Requirements

The workflow needs a GitHub repository and the [GitHub CLI](https://cli.github.com/) (`gh`), logged in. The building blocks work in any git repository.

## Credits

- `documenting` is adapted from [`domain-modeling`](https://github.com/mattpocock/skills/blob/main/skills/engineering/domain-modeling/SKILL.md) by Matt Pocock (MIT).
- `grilling` is inspired by [`grilling`](https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md) by Matt Pocock (MIT).
- `testing` is adapted from [`tdd`](https://github.com/mattpocock/skills/blob/main/skills/engineering/tdd/SKILL.md) by Matt Pocock (MIT).
- `reviewing` is adapted from [`code-review`](https://github.com/mattpocock/skills/blob/main/skills/engineering/code-review/SKILL.md) by Matt Pocock (MIT).
- `implementing` is adapted from [`implement`](https://github.com/mattpocock/skills/blob/main/skills/engineering/implement/SKILL.md) by Matt Pocock (MIT).

## License

Released under the [MIT License](https://github.com/fynnhaupt/skills/blob/main/LICENSE)

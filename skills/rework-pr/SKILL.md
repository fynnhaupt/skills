---
name: rework-pr
description: Rework a PR on the changes its review asked for and hand it back to review.
disable-model-invocation: true
---

# Rework PR

Take one PR labelled `status: rework-needed` back to `status: in-review`, with every change its review asked for either made or answered. The task issue keeps `status: in-progress` throughout. Before creating a label that does not exist yet, ask the user.

## Steps

1. **Pick the PR.** Use the PR the user named, or else the PR of the current branch. If it lacks `status: rework-needed`, tell the user why and stop. Check out its branch and pull it. If the default branch has moved on, merge it into the branch; on conflicts, resolve them or ask the user. Done when you are on the PR's up-to-date branch with the default branch merged in.
2. **Collect the asks.** Read the PR's comments, reviews, and line comments (`gh api repos/{owner}/{repo}/pulls/{number}/comments`), then the task issue it closes and that task's parent spec. List each requested change once, with the comment it comes from; skip comments already answered or resolved. If an ask changes the task's behaviour or acceptance criteria, ask the user whether to update the task issue first. Show the list to the user and ask about any comment you can't turn into a clear change. Done when the user has confirmed the list.
3. **Build it** with the `implementing` skill, taking the confirmed list as the work. Done when it has finished and the branch holds its commits.
4. **Hand it back.** Push the branch. Reply to each comment on the list with what changed, or why it did not. Update the PR body's notes and smells from `implementing`. Swap `status: rework-needed` for `status: in-review`. Done when the label is swapped and you have given the user the PR's link.

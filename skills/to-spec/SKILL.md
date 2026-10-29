---
name: to-spec
description: Turn a settled scope into a spec, filed as a GitHub issue.
disable-model-invocation: true
---

# To spec

Turn the **scope** settled earlier in this conversation into a **spec**: one GitHub issue that says what to build, why, and how. If no scope was settled in this conversation, tell the user to run `/scope` first and stop.

## Steps

1. **Work out the approach.** Read the code the scope touches, then decide how to build it: the modules to change, the interfaces between them, the data that moves, and the interfaces where tests observe behaviour (the seams). Grill the user with the `grilling` skill on choices only they can make. Done when every acceptance criterion maps to a part of the approach.
2. **File the spec** as a GitHub issue, using [SPEC-FORMAT.md](SPEC-FORMAT.md), labelled `kind: spec` plus the type label from the project's conventions, if it defines one. First show the user the title, body, and labels, naming any label that does not exist yet, and create the issue and missing labels only after they confirm. Done when the issue exists and you have given the user its link.
3. **Record what outlives the spec** with the `documenting` skill: new terms, decisions, and conventions settled along the way. Done when each is written or the user has said there are none.

Then tell the user to run `/to-tasks` to split the spec into tasks.

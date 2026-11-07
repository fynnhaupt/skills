# Glossary

**Skill**:
A folder under `skills/` with a `SKILL.md` that teaches an agent one step of the workflow or one building block.
_Avoid_: plugin, command, prompt

**Workflow**:
The single everyday sequence of work that the workflow skills cover together, one step per skill, each started by the user.

**Building block**:
A skill that other skills build on and that also works on its own, outside the workflow.

**Changeset**:
A note describing a change to a skill, released with the next version.

**Decision**:
A recorded choice that is hard to reverse, made once, kept with its reason.
_Avoid_: ADR

**Convention**:
A rule for how recurring work is done in this repo, grouped by topic.
_Avoid_: guideline, standard

**Request**:
The raw ask a piece of work starts from, before it is scoped.
_Avoid_: story

**Scope**:
A request's settled problem, behaviour, boundaries, acceptance criteria, and constraints, confirmed by the user and held in the conversation until it becomes a spec.

**Spec**:
One document describing a request's what and why and how it will be built, kept as a GitHub issue.
_Avoid_: PRD, design doc, plan

**Task**:
One vertical slice of a spec, implemented in one PR, kept as a sub-issue of the spec.
_Avoid_: ticket, story, issue

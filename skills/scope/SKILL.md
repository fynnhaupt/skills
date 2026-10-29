---
name: scope
description: Settle a request's what, why, and boundaries before it becomes a spec.
disable-model-invocation: true
---

# Scope

Grill a **request** until its scope is settled: every question a spec must answer has a confirmed answer. Read-only: the scope lives in the conversation.

## Steps

1. **Read around the request.** Read the request, `docs/GLOSSARY.md`, `docs/decisions/`, and the code it touches. Done when you can name the modules it affects and map its words to glossary terms.
2. **Grill it** with the `grilling` skill, covering every item of the scope:
   - **Problem**: what is wrong or missing today, and for whom.
   - **Behaviour**: what is true once it is done.
   - **Out of scope**: what it deliberately leaves alone.
   - **Acceptance criteria**: checkable statements that prove it is done.
   - **Constraints**: limits the solution must respect.

   Done when the user has confirmed the playback and every item has an answer; an empty item is answered "none" by the user, never by you.

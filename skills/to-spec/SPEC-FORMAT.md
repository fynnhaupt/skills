# Spec format

The issue title names the outcome, short and imperative (e.g. `Let users export reports as CSV`). The body:

```md
## Problem

What is wrong or missing today, and for whom.

## Behaviour

What is true once it is done.

## Approach

How it will be built: the modules that change, the interfaces between them, the data that moves, and the seams to test.

## Acceptance criteria

- [ ] A checkable statement that proves part of it is done.

## Out of scope

What it deliberately leaves alone, including later requests split off during scoping.

## Constraints

Limits the solution must respect.
```

- Keep every scope item; write "None." under an item the user answered "none".
- Use the project's glossary terms.
- Describe the approach by modules and interfaces, not file paths or line numbers, so it stays true while the code changes.

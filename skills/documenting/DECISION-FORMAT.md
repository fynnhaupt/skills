# Decision format

One file per decision in `docs/decisions/`, named `NNNN-<title>.md`: the next number after the highest existing one, zero-padded to four digits, and a short kebab-case title.

```md
# Release skills as one package

Skills are installed together via `npx skills add`, so they are versioned and released as one package instead of one per skill.
```

- One to three sentences: the context, the choice, and why.
- Add a section only when it carries something the paragraph can't: `## Considered options` when a rejected alternative will be suggested again, `## Consequences` when a downstream effect is non-obvious.
- A reversed decision keeps its file and gets `Superseded by [NNNN](NNNN-<title>.md).` as its first line under the heading.

## What qualifies

Record a decision only when all three hold:

1. **Hard to reverse**: changing course later costs real work.
2. **Surprising without context**: a future reader would ask "why this way?"
3. **A real trade-off**: there were genuine alternatives.

Anything else is either a convention or needs no record.

# Glossary format

One `docs/GLOSSARY.md` per repo:

```md
# Glossary

**Skill**:
One folder under `skills/` that covers one step of the workflow.
_Avoid_: plugin, command

**Changeset**:
A note describing a change to a skill, released with the next version.
```

- One or two sentences per term, saying what it **is**.
- When several words name the same thing, pick one and list the rest under `_Avoid_`.
- Only terms with a meaning specific to this project. General programming words stay out.
- Group terms under `##` headings once natural clusters appear; a flat list is fine until then.
- Keep implementation details out: the glossary defines words, nothing else.

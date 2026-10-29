# Keep conventions out of AGENTS.md

Conventions live in `docs/conventions/`, `docs/CONVENTIONS.md` points to each topic, and `AGENTS.md` only points to `docs/CONVENTIONS.md`, so the always-loaded context stays small as conventions grow. The cost: an agent reads a convention only when a pointer sends it there, so the pointer's wording decides whether the rule is followed.

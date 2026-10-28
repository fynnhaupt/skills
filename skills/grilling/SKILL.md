---
name: grilling
description: Grill the user relentlessly about a plan, decision, or idea, one question at a time. Use when the user wants to stress-test their thinking, or uses any 'grill' trigger phrases.
---

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.

Ask **one question at a time** through your built-in question tool, then wait for the answer. Pick each question from the **frontier**: the decisions whose prerequisites are already settled.

Format each question:

- **Header**: `Q<n>: <title>`, at most 12 characters.
- **Question**: `<body>`, worded so "yes" accepts your recommended answer.

Offer two options; the tool adds **Other** for a custom answer itself:

- **Yes (Recommended)**: your recommended answer.
- **No**: the strongest alternative.

Each answer reshapes the tree: settled decisions push the frontier outward. Recompute it before the next question.

Finding _facts_ is your job, never the user's. When a question needs a fact from the environment (filesystem, tools, etc.), dispatch a sub-agent to find it and keep asking questions that don't depend on it meanwhile. The _decisions_ are the user's.

The session is done when the frontier is empty: every branch of the design tree visited, nothing left silently assumed. Do not act on it until the user confirms you have reached a shared understanding.

---
name: grilling
description: Interview the user one question at a time until you share an understanding of a plan, idea, or decision. Use when the user wants to be grilled, or before building something whose intent is still unclear.
---

# Grilling

Interview the user until you and they hold a **shared understanding** of the topic: you could explain it back and they would sign off on every point.

## Steps

1. **Map the open questions.** Read the topic and any code or docs it touches, then list what is still unclear: goals, scope, constraints, edge cases, trade-offs. Answer what you can by looking; only questions that need the user's judgement stay on the list. Done when every item on the list needs the user.
2. **Ask one question at a time**, most fundamental first, since its answer may reshape the rest. Phrase it as a yes/no question that proposes your recommendation, so Yes reads as accepting it: "Keep sessions in Redis?", not "Where should sessions live?". Offer exactly three replies:
   - **Yes**: your **recommended answer**, with a one-line why. Yes always means the recommendation, so it needs no extra marker.
   - **No**: reject it; ask what they want instead.
   - **Other**: the user gives their own answer.

   Ask through your harness's interactive question tool when it has one (e.g. `AskUserQuestion` in Claude Code), with Yes and No as options; its free-text choice is Other. Only without such a tool, type the question and replies as text.

   After each reply, update the list: drop what the answer settled, add what it opened. Done when the list is empty.

3. **Play it back.** Summarise every settled outcome in a short list and ask the user to confirm it. A correction goes back to step 2. Done when the user confirms the summary.

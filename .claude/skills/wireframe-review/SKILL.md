---
name: wireframe-review
description: Pipeline — runs the wireframer then the UX reviewer in sequence. Wireframe output is saved to outputs/wireframe-latest.md; reviewer reads that file and returns a structured findings report. Use when you want a wireframe and a quality review in one step.
user-invocable: true
---

> **Note:** This pipeline writes to `outputs/wireframe-latest.md`. That file is overwritten on every run. Rename it before running again if you want to keep the previous wireframe.

Run the following steps in sequence. Do not start the next step until the previous one is complete.

**Step 1 — Wireframe**
Invoke the `wireframer` agent with the user's input. Receive its full output (all four sections).

**Step 2 — Save wireframe**
Write the wireframer's full output to `outputs/wireframe-latest.md`.

**Step 3 — Review**
Invoke the `ux-reviewer` agent. The subject of review is `outputs/wireframe-latest.md`. Instruct it to read that file and return a structured findings report on the wireframe it contains.

Return the reviewer's findings report to the user.

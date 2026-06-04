---
name: research-wireframe
description: Pipeline — runs the design researcher then the wireframer in sequence. Research findings are saved to outputs/research-latest.md; wireframer reads that file as context before producing the wireframe. Use when you want a wireframe grounded in competitive research.
user-invocable: true
---

> **Note:** This pipeline writes to `outputs/research-latest.md` and `outputs/wireframe-latest.md`. Both files are overwritten on every run. Rename them before running again if you want to keep previous outputs.

Run the following steps in sequence. Do not start the next step until the previous one is complete.

**Step 1 — Research**
Invoke the `design-researcher` agent with the user's input. Receive its full findings report.

**Step 2 — Save research**
Write the researcher's full output to `outputs/research-latest.md`.

**Step 3 — Wireframe**
Invoke the `wireframer` agent with the user's original input. Instruct it to read `outputs/research-latest.md` as context before beginning — the research findings should inform component choices and structural decisions where relevant. The wireframer still follows its full process; the research is context, not a brief override.

Return the completed wireframe output to the user.

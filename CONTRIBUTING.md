# Contributing a New Agent

This guide walks any team member through adding a new agent to the UX team AI toolkit. Follow every section in order. Do not skip steps.

---

## 1 — Before you build

Answer all nine questions before writing anything. If any cannot be answered, stop and talk to the right person before continuing.

**1. What is this agent's single, specific job?**
One sentence only. If you need a second sentence, the scope is too broad — split it.

**2. When should it be invoked, and when should it NOT be?**
Write both. The negative boundary is as important as the positive one. If you cannot define what it should refuse, the agent will leak into other agents' territory.

**3. What guideline files does it depend on?**
List every file under `guidelines/` the agent needs, and classify each:

| Class | Behaviour |
|---|---|
| **CRITICAL** | Agent refuses to run if the file is missing or contains only placeholder text |
| **SUPPORTING** | Agent proceeds and flags the gap inline in its output |

**4. What model?**
- `claude-haiku` — fast lookup, read, search, or retrieval tasks where speed matters more than depth
- `claude-sonnet` — reasoning, generation, review, or quality work where output quality is the priority

**5. What tools does it need?**
Specify only what is required. The full list of available tools is `Read`, `Glob`, `Grep`, `WebFetch`, `WebSearch`, and `Write`. Most agents need only `Read` and `Glob`. Do not add tools speculatively.

**6. What does it return, and in what format?**
Define the exact output structure before you write the system prompt — the system prompt must describe this format precisely.

**7. Does it overlap with an existing agent?**
Review the routing table in `CLAUDE.md`. If there is any overlap, define the exact boundary — which task goes to each agent, and why. If the boundary cannot be drawn cleanly, talk to the governance team.

**8. Should it run in a forked context?**
Use `context: fork` (default, recommended) unless the agent's internal reasoning chain is itself part of the output. The `wireframer` uses `context: standard` because its step-by-step reasoning informs the output structure. If in doubt, use `fork`.

**9. If any of the above cannot be answered:**
Talk to the governance team about agent scope. Talk to Kristelle if the question is about guideline files — she owns `guidelines/`.

---

## 2 — File structure

Three things are required per new agent. Nothing else without checking with the governance team.

```
.claude/agents/[slug].md          ← the agent definition
.claude/skills/[command]/SKILL.md ← its slash command
CLAUDE.md                         ← routing table entry (mandatory update)
```

File naming rules:
- `[slug]` is kebab-case, e.g. `ia-auditor`
- `[command]` matches the slash command without the leading `/`, e.g. `ia-audit`
- Slug and command do not have to match, but the skill file must reference the correct slug

---

## 3 — Writing the agent file

Use this prompt with Claude to draft the agent file. Paste your answers from Section 1 into the `[Additional detail]` field.

```
Write a Claude Code subagent file for a new UX team agent.

Role: [one sentence]
Slug: [kebab-case]
Model: [claude-haiku or claude-sonnet]
Tools: [only what's needed]
Context: [fork / standard] — fork the context unless the agent's reasoning is itself part of the output
Critical files (refuse if missing):
- [list]
Supporting files (proceed and flag):
- [list]

System prompt must include:
- Role and scope, with explicit list of what this agent does NOT do
- Which guidelines to load
- Step-by-step process the agent follows
- Exact output format
- Gap handling: refuse on critical files missing, flag inline for supporting
- Push-back behaviour: when to refuse vs. substitute vs. ask the user

Additional detail: [paste your answers from Section 1 here]
```

**Agent file format** — the file must open with YAML frontmatter:

```yaml
---
name: [slug]
description: [one sentence used by the router to decide when to invoke this agent]
model: claude-sonnet
tools:
  - Read
  - Glob
context: fork
---
```

The `description` field is what the orchestrator reads when deciding which agent to delegate to. Write it precisely — vague descriptions cause misrouting.

**Keep the agent file lean.** Any examples in the system prompt must be obviously placeholder — never use specific Employment Hero attribute values, real component names, or real copy that the agent might reproduce as canonical.

---

## 4 — Writing the skill file

Use this prompt with Claude to draft the skill file:

```
Write a Claude Code skill file (SKILL.md) for a slash command called /[name].
When invoked, delegate to the [slug] subagent and pass through all arguments.
YAML frontmatter: name, description, user-invocable: true.
```

The skill file must open with YAML frontmatter:

```yaml
---
name: [command]
description: [one sentence shown in the slash command list]
user-invocable: true
---
```

The body is typically one line: delegate to the agent and pass arguments through.

---

## 5 — Updating CLAUDE.md

This is a mandatory step. Add a row to the routing table and a rule to the routing rules section.

The total token count of `CLAUDE.md` must stay under 500 tokens. If adding your entry would push it over, tighten existing entries first. Every row in the routing table and every routing rule must be as concise as possible — cut words, not meaning.

Do not add new sections. Do not document your agent's internal behaviour here. The routing table is a lookup, not a manual.

---

## 6 — If a new guideline file is needed

If the agent depends on a guideline file that does not yet exist in `guidelines/`:

1. Create a stub file at `guidelines/[name].md` containing only: `[TO BE POPULATED]`
2. Reference the stub filename exactly in the agent's system prompt
3. Flag the stub in your PR description and tag Kristelle — she populates guideline files
4. Do not invent content for guideline files

The stub ensures the agent's critical-file check has something to detect. An agent that references a non-existent file cannot enforce its own refusal condition.

---

## 7 — Testing before committing

Run all six checks. Do not commit until they all pass.

1. **Explicit invocation** — invoke the agent directly: `"Use the [slug] agent to [simple test task]"`. Confirm it runs and returns the defined output format.

2. **Critical file refusal** — temporarily rename or empty a critical guideline file, then invoke the agent. Confirm it refuses to proceed with a clear message. Restore the file.

3. **Supporting file gap flag** — temporarily empty a supporting guideline file, then invoke the agent. Confirm it proceeds and flags the gap inline in the output.

4. **Output format** — verify the output matches the format defined in the system prompt exactly. Check section names, table structure, and required fields.

5. **Slash command** — invoke via the slash command: `/[command] [test task]`. Confirm delegation works and arguments pass through.

6. **Filename check** — grep the agent's system prompt for every guideline filename it references. Verify each filename exists exactly in `guidelines/` — same spelling, same extension. A single character difference causes a silent failure.

---

## 8 — Submitting

```bash
git checkout -b agent/[slug]
```

Commit these files together in a single commit:
- `.claude/agents/[slug].md`
- `.claude/skills/[command]/SKILL.md`
- `CLAUDE.md` (updated routing table)
- `guidelines/[name].md` stubs if any were created

**PR description must include:**
- What the agent does (one paragraph)
- What guideline files it reads, and how each is classified (critical / supporting)
- What it returns, and the output format
- Any guideline stubs added, with Kristelle tagged
- Any boundary decisions made with existing agents

**PR tags:**
- Tag the governance team for agent scope review (always)
- Tag Kristelle if any guideline stubs were added or existing guideline files changed

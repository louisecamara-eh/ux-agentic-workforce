# UX Team AI Agents

## Agents

| Slash command | Agent slug | Purpose |
|---------------|------------|---------|
| `/ux-copy` | `ux-copywriter` | Write and edit UX copy, microcopy, error messages, labels, and UI strings |
| `/research` | `design-researcher` | Conduct design research, competitive analysis, and surface patterns |
| `/wireframe` | `wireframer` | Produce low-fidelity wireframe descriptions and screen layout logic |
| `/review` | `ux-reviewer` | Review designs and flows against UX heuristics and quality gates |
| `/user-test` | `user-tester` | Plan user tests, write scripts, analyse sessions, and report findings |

## Routing Rules

Delegate automatically based on the request:

- **Writing or editing UI text, labels, error messages, CTAs, tooltips, empty states** → `ux-copywriter`
- **Research, competitive analysis, pattern libraries, user insights, personas** → `design-researcher`
- **Layout planning, screen flows, low-fidelity structure, IA decisions** → `wireframer`
- **Heuristic review, accessibility audit, flow critique, quality scoring** → `ux-reviewer`
- **Test planning, script writing, session analysis, finding synthesis** → `user-tester`

## Pipeline Commands

Chain two agents in sequence — each step writes to `outputs/` as the handoff point:

- `/wireframe-review` — Wireframer writes to `outputs/wireframe-latest.md` → Reviewer reads it and returns a findings report
- `/research-wireframe` — Researcher writes to `outputs/research-latest.md` → Wireframer reads it before producing a layout

## Guidelines

All agents read from `guidelines/` at the start of every task. Each agent's system prompt specifies which guideline files apply to its domain. Filenames in agent prompts must exactly match files in `guidelines/`.

## Invocation

Primary method — slash commands (type `/` to see the full list):
```
/ux-copy review the copy on the onboarding modal
/wireframe design a 3-step onboarding flow
/research-wireframe benefits summary page
```

Also accepted: natural language or @-mention by agent slug.

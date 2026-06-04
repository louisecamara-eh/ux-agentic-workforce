# UX Team AI Agents

A Claude Code plugin that gives the Employment Hero UX team five specialised AI agents — each scoped to a distinct design discipline. Agents share a common `guidelines/` knowledge base covering the Hero Design System, copy standards, research methodology, and evaluation heuristics. All outputs land in `outputs/` so they can be reviewed, iterated on, or handed off to engineering without leaving the terminal.

![UX Agents](assets/ux-team-agents.png)

---

## Agents

| Agent | What it does |
|-------|-------------|
| **ux-copywriter** | Writes and edits UI text — labels, error messages, CTAs, tooltips, empty states, and any in-product strings |
| **design-researcher** | Runs competitive analysis, surfaces patterns and thought leadership, and returns structured research findings |
| **wireframer** | Produces low-fidelity screen layouts — component selection, semantic structure, and IA decisions |
| **ux-reviewer** | Audits designs and flows against UX heuristics, quality gates, and accessibility standards |
| **user-tester** | Simulates user testing sessions, writes test scripts, and synthesises session findings into a structured report |

---

## Slash commands reference

| Command | Agent invoked | Pipeline? |
|---------|--------------|-----------|
| `/ux-copy` | ux-copywriter | No |
| `/research` | design-researcher | No |
| `/wireframe` | wireframer | No |
| `/review` | ux-reviewer | No |
| `/user-test` | user-tester | No |
| `/wireframe-review` | wireframer → ux-reviewer | Yes — wireframe then review in sequence |
| `/research-wireframe` | design-researcher → wireframer | Yes — research then wireframe in sequence |

---

## Prerequisites

- **Claude Code** installed (`npm install -g @anthropic-ai/claude-code`)
- **Employment Hero Enterprise account** — sign in with your EH work email via `claude login`

---

## First-time setup

```bash
# 1. Install Claude Code
npm install -g @anthropic-ai/claude-code

# 2. Authenticate with your Employment Hero account
claude login

# 3. Clone this repo
git clone <repo-url>

# 4. Open the repo in your terminal
cd ux-team-ai-assistants
```

---

## How to invoke agents

### Slash commands

Type `/` in Claude Code to see the full list. Examples:

```
/ux-copy         review the error messages on the login form
/research        salary benchmarking tools — competitive analysis
/wireframe       3-step onboarding flow for a new employee
/review          check this benefits summary page against quality gates
/user-test       simulate a payroll specialist running an end-of-fortnight pay run
```

### Pipeline commands

```
/wireframe-review    benefits summary page
/research-wireframe  payroll dashboard redesign
```

### Natural language

Describe what you need and Claude Code will route to the right agent automatically:

```
Write the empty state copy for the goals page
What do competitors do for timesheet approval flows?
Lay out a mobile screen for submitting a leave request
Is this onboarding modal accessible?
```

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding agents, updating guidelines, and extending the pipeline.

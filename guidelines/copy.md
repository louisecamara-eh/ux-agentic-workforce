# UX Copywriting

> UX writing principles, brand voice, grammar and punctuation standards, UI element conventions, and copy violation checklist. Covers interface copy only; excludes marketing, email, OOH, and long-form content types.
>
> **Scope:** Global baseline — applies to all markets. Regional files extend or override this file for market-specific spelling, terminology, formatting, and compliance copy. Read the relevant regional file alongside this one.
>
> **Source:** [Confluence — DES Space](https://employmenthero.atlassian.net/wiki/spaces/DES/pages/4554850368/UX+Copywriting+Assitant+for+UX+buddy)
> **Last Modified:** 19/01/2026 | **Author:** Kristelle Joyce Gangano

---

## Regional guidelines

Each regional file extends this global base. Rules in regional files override rules here where they conflict.

| Region | File |
|--------|------|
| Canada | `guidelines/copy-ca.md` |
| Australia | `guidelines/copy-au.md` *(to be created)* |
| New Zealand | `guidelines/copy-nz.md` *(to be created)* |
| United Kingdom | `guidelines/copy-uk.md` *(to be created)* |

---

## What is UX writing?

UX writing refers to the small words and phrases within a product interface that make it usable. Its primary purpose is to help the user — making interfaces easy to use and understand.

### Goals of good UX copy

- **Just make things easy** — users should use and understand the interface with minimal assistance
- **Copy for everyone** — interfaces should be understandable and usable by people with disabilities and across various contexts and platforms
- **Don't make me think** — users should accomplish tasks quickly without excessive mental effort
- **A repeatable experience** — users should enjoy using the interface and return to it often

### The five principles

**Usable** — words that improve or enable the functionality of a product. Clear, simple, to-the-point language that reduces thinking.

**Helpful** — goes beyond usability to offer information the user might not have known they needed. A search bar saying "Search employees by name or ID" rather than "Search".

**Accessible** — the interface should be for everyone, including people with disabilities. Accessible copy benefits all users.

**Clear** — prioritise clarity and user assistance over clever or punchy copy. Direct and unambiguous. Short, sharp sentences.

**Branded** — copy should feel consistent with the EH brand. Work to the standards in this file.

---

## The EH voice

Human and direct. Bold and disruptive. We challenge conventional notions of employment and champion a better way to work.

### Three golden rules

1. **Cut the BS** — keep it real. Tell it like it is. Short, simple, to-the-point language that feels relatable and human.
2. **Hero the employer** — acknowledge SME contributions and challenges. Show them how to succeed.
3. **Lift the conversation** — show there's a better, more valuable way. Leave the user feeling uplifted and optimistic.

### Core brand traits

**Empowering** — we're a sidekick and partner. We make the employer the Hero. Talk to users like they're already winning — validate, empower, show possibilities. Means: challenging, bold, ambitious, brave. Does not mean: reckless, unsafe, or ignorant.

**Transformative** — we're trailblazers and forward-thinkers. We redefine what's possible. Means: empowering, motivating. Does not mean: toxically optimistic, unrealistic, or sugar-coated.

**Challengers** — we show a better way. We challenge the status quo. Means: unconventional, determined, inclusive, progressive. Does not mean: blindly optimistic, hyperbolic, or patronising.

### Voice in interface copy

- Lean into the unexpected
- Bring joy into every interaction — including error pages (e.g. 404) and empty states
- Less shouting, more confidence: short, sharp sentences with full stops instead of exclamation marks
- Do not use generic CTAs: "Learn more", "Find out more", "See more"
- Do not use passive or corporate language
- Do not use condescending tone
- Do not write error messages or empty states that blame the user

---

## Capitalisation

**General rule:** use minimal capitalisation unless an exception applies.

Minimal capitalisation means capitalise only proper nouns and the first word of a sentence or standalone phrase.

**Proper nouns** (capitalise these):
- Names of people
- Names of institutions (e.g. Australian Tax Office, HMRC)
- Names of companies (e.g. Apple Australia Limited)
- Job titles (e.g. Product Manager)
- Names of products or brands
- Names of places
- Industry terminology used by key institutions (e.g. Single Touch Payroll)

**Product features are not proper nouns** — write "Payrolling benefits", not "Payrolling Benefits".

**Apply minimal capitalisation to:**
- Sidebar menu items
- Dashboard tabs
- Headings
- Wizard titles
- Modal titles
- CTAs and buttons
- Drop-down menu items
- Banner and alert titles
- Step titles

**Exceptions:**

| Exception | Rule |
|-----------|------|
| Page titles (h2 tags) | Maximal capitalisation — capitalise first word and every content word; do not capitalise function words (a, the, and, for, in, up, to) |
| Left navigation menu titles | Full caps (e.g. MY ACCOUNT); menu items below use minimal capitalisation |
| Acronyms | Full caps if formed from first letters of each word (e.g. GST, ATO, HMRC) |
| Abbreviation ID | Always "ID", never "Id" or "id" |
| User-entered text | Display exactly as the user entered it |
| Measurement units | Lower case (e.g. hrs) |

**Industry terminology** — do not apply maximal capitalisation unless used by a key institution. Examples: "modern award" not "Modern Award"; "pay as you go" not "Pay As You Go".

---

## Spelling and syntax

**British English throughout.** Where a choice exists, use British convention. Set language preference to English (UK).

Regional files override British English where local usage differs — for example, Canadian English uses "program" (not "programme") for government schemes. Always read the regional file alongside this one.

**Phrasal verbs vs phrasal nouns:**

Test: try changing the tense. If it sounds odd (e.g. "loginned", "setupped"), it is a noun.

- Phrasal verbs — verb + particle following it: keep separate (e.g. "log in", "set up")
- Phrasal nouns — compound word (e.g. "login", "setup")

---

## Terminology

Global terms that apply across all markets. Market-specific terminology (payroll codes, tax forms, statutory schemes) belongs in the relevant regional file.

| Term | Correct usage |
|------|---------------|
| cannot | Not "can not" |
| cut-off | Noun/adjective. Verb is "cut off" |
| Employment Operating System | First instance: spell out in full. Subsequent references: "Employment OS" if already spelt out or space is restricted. Goal is to own the acronym "EOS" |
| ID | Not "Id" or "id" |
| log in | Verb: "Log in to the employee portal" |
| login | Noun: "Enter your login" |
| pay run | Not "payrun". Noun phrase. Industry term |
| payroll | Compound phrasal noun. Industry term |
| payslip | Compound. British English standard. See regional files for market variants |
| pop-up | Noun/adjective. Verb is "pop up" |
| set up | Verb: "To set up a new user, click/tap here" |
| setup | Noun: "The setup procedure is as follows" |

---

## Specific UI elements

### Links

- Link text must describe the action or destination (e.g. "Forgot my password", "Check the mail log")
- Do not use: "click/tap here", "click/tap this link", "go here", "use this form", "click/tap on the link above"
- Do not use links for primary actions like saving or cancelling — use buttons

### Information labels (i-icon)

- Use sparingly — not on every field
- Only for additional contextual information
- Do not use to explain complex logic — simplify the logic instead
- Do not use for warnings or errors — use validation components
- Use the correct "i" icon — not a question mark or exclamation point
- Maximum 2–3 sentences in the popover; link to a support article for longer explanations
- Avoid tooltip controls

---

## Web

### Links

- Internal links (within the product) open in the same tab
- External links (support docs, partner pages) open in a new tab

**Violation:** Internal links opening in a new tab; external links opening in the same tab.

### Information labels (i-icon)

- Show a popover on hover and click; popover stays visible for 500ms after mouse moves away

---

## Mobile

[TO BE POPULATED]

---

## Violation checklist

This section is the reviewer's primary reference. Flag any of the following.

### Spelling and syntax

- Non-British spelling unless a regional file specifies otherwise: "enrollment" not "enrolment", "color" not "colour"
- Phrasal verb/noun confusion: "login" as a verb (correct: "log in"), "setup" as a verb (correct: "set up")
- "Can not" instead of "cannot"
- Incorrect hyphenation: "cut off" as a noun (correct: "cut-off"); "pop up" as a noun (correct: "pop-up")
- "payrun" instead of "pay run"

### Capitalisation

- Title case on elements requiring minimal capitalisation: buttons, CTAs, modal titles, wizard titles, banner and alert titles, sidebar menu items, dashboard tabs, drop-down items, step titles
- h2 page titles not using maximal capitalisation — the one element that requires it
- Left nav menu titles not in full caps (e.g. "My Account" instead of "MY ACCOUNT")
- Product features capitalised as proper nouns (e.g. "Payrolling Benefits" instead of "Payrolling benefits")
- "Id" or "id" instead of "ID"
- Industry terms incorrectly capitalised: "Modern Award" not "modern award"; "Pay As You Go" not "pay as you go" (unless used by a key industry institution)
- Measurement units not in lower case: "Hrs" not "hrs"
- Acronyms not in full caps: "Gst" not "GST"

### Usability and clarity

- Placeholder text that does not guide the user (e.g. "Search" instead of "Search employees")
- Ambiguous wording where a short, direct alternative exists
- Jargon without explanation in a user-facing context

### Information labels

- Question mark or exclamation point icon instead of "i" icon
- i-icon used to explain complex logic
- i-icon used for warnings or errors
- Popover text exceeding 2–3 sentences with no "More information" link

### Links and CTAs

- Vague link text: "click/tap here", "go here", "use this form", "click/tap on the link above"
- Generic CTAs: "Learn more", "Find out more", "See more" without descriptive context
- Links used for primary actions where buttons should be used

### Tone of voice

- Passive or corporate language that violates "Cut the BS"
- Condescending tone that violates "Lift the Conversation"
- Error messages or empty states that blame the user

---

## Severity guide

| Severity | Definition |
|----------|------------|
| Critical | Factually incorrect copy causing potential user harm (wrong legal text, misleading data labels, incorrect financial terminology); spelling error in a primary heading or CTA visible every session |
| High | Capitalisation error on primary UI elements (page titles, main CTAs, navigation); unclear CTA on a critical flow (onboarding, payroll, leave); grammar error that changes meaning |
| Medium | Tone inconsistency on a secondary screen; verbose copy that could be trimmed; minor grammar or spelling on a non-primary surface; vague link text on a non-critical path |
| Low | Optional phrasing improvement where copy is already compliant; minor capitalisation on a low-visibility element |

---

## What to ignore

- Developer-facing strings: log messages, API error codes, internal comments
- User-entered text displayed as-is
- Tone that is already compliant but could be "slightly better" — flag only active guideline violations
- Regional spelling that is correct for the target market — e.g. "enrolment" is British English standard; a regional file may specify a variant
- Implementation details not visible in the rendered output
- Test files, mock data, placeholder content marked as temporary

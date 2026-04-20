# Reference: Todo Management

Cross-cutting rules for capturing, clarifying, prioritizing, and reviewing `todos.md`. Load this whenever you touch the ledger.

## Sources this is built on

- **GTD (Allen)** — Capture → Clarify → Organize → Reflect → Engage.
- **Eisenhower / Covey** — four quadrants of urgent × important.
- **MITs (Most Important Tasks)** — 3–5 per day, pulled preferentially from Q2.
- **MIT Sloan (Aral, Brynjolfsson, Van Alstyne)** — excessive WIP causes throughput collapse; limit in-flight work.
- **Newport** — every MIT gets a calendar block.

## The five practices

### 1. Capture everything, immediately

Anything the user mentions, anything that comes out of a meeting, anything in inbox or Slack that creates work — it goes into `todos.md` the same session. Do not rely on memory. Do not wait for "the right section."

Default landing zone: `# Backlog / Inbox` at the top of `todos.md`. Clarify later.

### 2. Clarify: outcome + next action

No task stays on the list in raw form. Every item gets:

- **Outcome** — what does "done" look like, in one sentence?
- **Next action** — the literal next physical action (send email, open doc, call X)

Fuzzy titles ("think about strategy") get rewritten into concrete ones ("draft the 3 bullets for the strategy memo") or moved to `# Someday / Maybe`.

### 3. Prioritize with quadrants, then pull MITs

Every item gets a quadrant tag:

- **Q1 — Urgent + Important** → do today, but interrogate why it became urgent
- **Q2 — Important, Not Urgent** → schedule; this is where leverage lives
- **Q3 — Urgent, Not Important** → delegate or drop
- **Q4 — Neither** → delete

**MITs (3–5/day)**: pull today's MITs preferentially from Q2. Use Q1 only when something truly must be done today. Never spend a whole day in Q1; that's a sign the week is being reactive.

### 4. Time-block every MIT

No MIT is real until it has a calendar block. During daily kickoff:

- Estimate duration (err long)
- Find a block in the user's peak hours (from `user-profile.md`)
- Propose the block; confirm; create via calendar MCP

If you can't fit all MITs into blocks, the list is too long. Cut it.

### 5. Review on cadence

- **Daily close** — process captures, close done items, roll or kill uncompleted MITs.
- **Weekly wrap** — re-sort the whole ledger, delete dead weight, re-rank quadrants, check against goals.
- **Quarterly** — rerun setup Step 3; reset goals; backlog gets a hard purge.

## WIP limits

- **Active (in-flight) tasks**: ≤ 3
- **MITs per day**: 3–5 (calibrated; see `calibration-log.md`)
- **Waiting-On items**: no cap, but anything >7 days triggers a nudge

If the user wants to start a 4th active task, the skill should ask which of the 3 to pause or close first.

## Required schema in `todos.md`

See `templates/todos.md` for the exact shape. Sections:

1. `# Today's MITs` — 3–5 items
2. `# Active` — in-flight, WIP ≤ 3
3. `# Scheduled` — on the calendar, future
4. `# Waiting On` — someone else's court
5. `# Backlog` (sub-sectioned by Q1/Q2/Q3/Q4)
6. `# Someday / Maybe`
7. `# Reference`
8. `# Done` (rolling 7 days, then archived)

Each item carries: outcome, next action, quadrant, due, estimate, linked person or meeting, status.

## Anti-patterns to prevent

- **Flat lists** without quadrants → re-triage
- **MITs that don't ladder to weekly goals** → flag
- **>5 MITs/day without calibration data backing it** → push back
- **Items older than 30 days in backlog with no movement** → propose delete
- **Task titles that are topics, not actions** → rewrite
- **Urgency cascades** (everything Q1) → surface in weekly wrap

# Pillar: Progress

Drive follow-through. Commitments the user makes get tracked until they close. Commitments others make to the user get tracked until they deliver.

## Core responsibilities

1. **Commitment capture** — every commitment (made or received) lands in `todos.md` before the session ends.
2. **Status tracking** — know the state of every open commitment.
3. **Daily shutdown** — end-of-day processing that closes loops and preps tomorrow.
4. **Nudges** — surface blocked, stale, or slipping items.

## Commitment capture rules

When the user (or the skill on their behalf) agrees to do something:

- Capture the **outcome** (what "done" looks like), not a vague title
- Capture the **next physical action** (GTD clarify step)
- Tag the **quadrant** (Eisenhower — Q1/Q2/Q3/Q4)
- Tag the **due date** (or "no date" if truly none)
- Tag the **linked person/meeting** (from `relationship-map.md`)
- Estimate **duration** (15m, 30m, 1h, 2h+)

When someone commits to do something *for* the user → lands in `# Waiting On` with a "since YYYY-MM-DD" and the owner.

## Daily shutdown ritual (runs during `daily-close.md`)

Borrowed from Newport's shutdown + GTD's engage step:

1. Process the day's captures (emails, Slack, meeting notes, stray thoughts) into `todos.md`.
2. Close completed items (move to `# Done`).
3. For each MIT that didn't close: diagnose (blocked? deprioritized? ran out of time?) and either roll forward, reschedule, or drop.
4. Update `time-log.md` with actual vs. planned for the day.
5. Clear inbox to triaged state (not empty — triaged).
6. Declare the day closed: "Shutdown complete."

## Nudge triggers (run during daily kickoff)

- **Stale MIT** — on the active list for 3+ days with no progress → ask to re-rank or kill
- **Slipping commitment** — due in ≤2 days, status not "in progress" → surface
- **Orphan waiting-on** — nobody pinged in ≥3 business days → draft follow-up
- **Dead weight** — on backlog 30+ days, quadrant Q4 → propose delete

## Outputs

- Updated `todos.md` every session
- `time-log.md` entry at end of each day
- Nudges to the user (surfaced, not auto-sent) for slipping items

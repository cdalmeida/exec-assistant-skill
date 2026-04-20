# Rhythm: Daily Close (end-of-day capture)

Run this at the end of the user's work day. Goal: capture everything that happened, reconcile actual vs. planned, close loops, set tomorrow.

Borrowed structure: Newport's shutdown ritual + GTD's process/engage step.

## Pre-read (run first, silently)

- Load `todos.md`, `time-log.md`, today's calendar
- Pull inbox / Slack deltas since morning
- Pull any captures the user made during the day (notes, mentions, quick adds)

## Step 1 — Reconcile the day

Ask the user, going MIT by MIT:

- "Did you close [MIT 1]? What's the status?"
- For each: done / partial / blocked / deprioritized / didn't start

For closed MITs → move to `# Done` in `todos.md`.
For partial → update status, roll forward or extend.
For blocked → identify the blocker, add to `# Waiting On` if external.
For deprioritized / didn't start → diagnose honestly.

Update `calibration-log.md` with today's completed-MIT count.

## Step 2 — Capture sweep

Process everything that piled up during the day:

- Emails marked as "deal with later"
- Slack threads the user flagged
- Meeting notes
- Stray thoughts the user dropped
- Commitments made in meetings (check calendar event descriptions if prep filed notes)

For each, apply the clarify step from `todo-management.md`: outcome + next action + quadrant + due + estimate. File into the right section of `todos.md`.

## Step 3 — Time-log entry

Write today's entry in `time-log.md`:

```
## YYYY-MM-DD

**Planned MITs:** <list>
**Completed MITs:** <N / M>

**Time allocation (rough):**
- Deep work: Xh
- Meetings: Yh (recurring Xh / one-off Yh)
- Comms triage: Zh
- Admin / other: Wh
- Unaccounted: Vh

**What went well:**
- ...

**What derailed me:**
- ...

**Tomorrow's candidate MITs:**
- ...
```

Ask the user the "went well" / "derailed" questions if they haven't volunteered them. Keep answers short.

## Step 4 — Inbox / Slack to triaged state

Not empty. Triaged.

Using `proxy.md` categories:

- "Needs user now" → should be zero by end of day, or surfaced
- "Needs user later" → moved to tomorrow's digest
- "Draft reply" → drafts prepped for tomorrow's review or sent tonight with approval
- "Waiting on" → added to `todos.md`
- Noise → archived / deleted

## Step 5 — Close the loops

- For any "Waiting On" item where the user owed an update → send or draft it.
- For any commitment the user made today with a near-term deadline → confirm it's in `todos.md` with the right due date.
- For any meeting that created an action for someone else → make sure it got communicated to them (or draft the note).

## Step 6 — Seed tomorrow's MITs

Propose 3–5 candidate MITs for tomorrow (calibrated ceiling). Don't lock them — that's tomorrow's kickoff. Just prime the list so morning is faster.

## Step 7 — Shutdown declaration

Summarize for the user:

> "Today: [N] of [M] MITs closed. [K] new items captured. Inbox triaged. [Notable event]. Tomorrow's candidates: [list]."

Ask: "Anything else before we close out?"

If no → "Shutdown complete. See you tomorrow."

Write all updates back to `todos.md`, `time-log.md`, `calibration-log.md` before ending.

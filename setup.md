# Setup (personalization)

Run this flow on first invocation, or when the user says "re-setup" / "update my profile."

The goal: produce a clear enough picture of *this* user that the skill can act on their behalf with good judgment. Do not skip steps; the quality of the skill downstream depends on the quality of this intake.

## Step 1 — Pick the context location

Ask the user which repo and folder the skill should use for context files. Default suggestion: a folder named `ea-context/` at the root of a repo they use daily.

Confirm the path before writing anything. Create the folder if it does not exist.

## Step 2 — Role triage

Ask, one at a time:

1. **Are you an individual contributor or a leader of people?** (If leader: how many direct reports, how many indirect?)
2. **What is your role and function?** (e.g., Director of Product, Staff Engineer, Founder)
3. **Who do you report to?** (name, role, working style if known)
4. **Who are your key peers and cross-functional partners?** (names, roles, the nature of the working relationship)
5. **Who are your most important external stakeholders?** (customers, board, partners, vendors — if relevant)

This populates `relationship-map.md`.

## Step 3 — Priorities and goals

Ask:

1. **What are your top 3–5 quarterly goals right now?** Write them in `goals.md`.
2. **For each quarterly goal — what would "good progress by end of quarter" look like?**
3. **What outcomes are you being measured on?** (formal: OKRs, KPIs; informal: what your manager will ask about in your next 1:1)

Any quarterly goal that cannot be stated as an observable outcome gets flagged. Push back until it is concrete.

## Step 4 — Working style

Ask:

1. **When are your peak focus hours?** (e.g., 9–11am, post-lunch dip, evening deep work)
2. **How many MITs per day feels right as a starting target?** (default: 3–5)
3. **How do you prefer to be interrupted?** (async-first? open to DMs? walk-ups ok?)
4. **What are your deep-work preferences?** (minimum block size, ideal number of blocks per week)
5. **What are your non-negotiables?** (e.g., school pickup at 3pm, no meetings before 9am, protected lunch)

This populates the working-style section of `user-profile.md`.

## Step 5 — Communication norms

Ask:

1. **How do you want the skill to talk to you?** (terse? conversational? bullet-heavy? narrative?)
2. **What's your tone in written comms?** (formal, warm, direct, understated) — this calibrates Proxy drafting.
3. **Any phrases or tics you use / avoid?**

## Step 6 — MCP connector check

Check for the following connectors. For each, state whether it's connected:

- Google Calendar (or Outlook Calendar)
- Gmail (or Outlook Mail)
- Slack

For any that are missing, tell the user:

> To make this skill work well, I need access to your calendar, email, and Slack via MCP connectors. Please set up the [missing connectors] and let me know when they're ready. If you don't want to connect one, tell me — I'll work around it by asking you to paste the relevant info at session start.

Do not proceed to Step 7 until the user has either connected the MCPs or explicitly opted out.

## Step 7 — Scaffold the context files

Once Steps 1–6 are complete, write the templates from `templates/` into the user's chosen folder, filled in with what you learned:

- `user-profile.md` — identity, role, priorities, working style, comms norms
- `relationship-map.md` — team, managers, peers, stakeholders
- `goals.md` — quarterly goals + weekly ladder (weekly section starts empty)
- `todos.md` — empty ledger with the standard sections
- `time-log.md` — empty, ready for first daily entry
- `calibration-log.md` — empty, 14-day observation period starts now

## Step 8 — Confirm and hand off

Show the user a summary of what you captured. Ask: *"Did I get anything wrong? Anything missing?"*

Then suggest the next natural action based on the day/time:

- If it's Monday morning: "Want to run a weekly kickoff?"
- If it's mid-day: "Want to set MITs for the rest of today?"
- If it's Friday afternoon: "Want to wrap up the week?"
- Otherwise: "Ready to plan tomorrow, or is there something else you need?"

## Re-setup triggers

Rerun (or partially rerun) this flow when:

- Start of a new quarter → re-run Step 3 (goals)
- User changes role or team → re-run Steps 2 and 3
- User explicitly asks: "update my profile," "my priorities changed"
- Calibration check (every 14 days) flags a sustained mismatch

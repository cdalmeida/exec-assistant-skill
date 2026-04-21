# Executive Assistant Skill for Claude Code

A Claude Code skill that acts as a strategic executive assistant. Triages calendar, email, and Slack; runs daily and weekly operating rhythms; and maintains goals, todos, a time log, and a relationship map.

Grounded in research from Harvard Business Review, McKinsey, MIT Sloan Management Review, GTD (David Allen), Eisenhower/Covey, and Cal Newport.

## What it does

**Five pillars** (loaded on demand by the skill):

- **Protect** — gatekeeping, calendar defense, focus-block enforcement
- **Prepare** — pre-reads, meeting agendas, 1:1 context packs
- **Proxy** — inbox and Slack triage, drafting in the user's voice
- **Progress** — commitment tracking, daily shutdown ritual, nudges on slipping items
- **Chief-of-Staff-Lite** — goal-ladder integrity, drift detection, strategic framing

**Four rhythms**:

- Weekly kickoff (Monday macro)
- Daily kickoff (morning grounding)
- Daily close (end-of-day capture and reconciliation)
- Weekly wrap (Friday retrospective including a "did it matter?" reflection)

**Persistent context layer** — markdown files the skill reads and writes each session: user profile, relationship map, goals ladder (quarterly → weekly → daily MITs), todos ledger (GTD + Eisenhower quadrants + MIT selection), time log, and calibration log.

**Adaptive MIT target** — defaults to 3–5 Most Important Tasks per day. After a 14-day observation window the skill proposes recalibration based on actual completion rate.

## Prerequisites

- Claude Code installed and running
- MCP connectors recommended (the skill gracefully degrades without them, asking the user to paste data):
  - Google Calendar (or Outlook Calendar)
  - Gmail (or Outlook Mail)
  - Slack

## Installation

**For agents installing this skill on a user's behalf:**

The skill must live at `.claude/skills/executive-assistant/` inside the project directory where the user wants to invoke it. Pick a target project the user works in daily.

```bash
# Run from the target project's root directory
mkdir -p .claude/skills/executive-assistant
git clone https://github.com/cdalmeida/ExecAssistant-Skill.git /tmp/ea-skill
cp -R /tmp/ea-skill/. .claude/skills/executive-assistant/
rm -rf .claude/skills/executive-assistant/.git /tmp/ea-skill
```

Verify:

```bash
ls .claude/skills/executive-assistant
# Expected: SKILL.md  pillars  rhythms  setup.md  templates  README.md
```

Restart Claude Code. The skill is now invokable as `/executive-assistant`.

**For humans:** same commands. The skill is self-bootstrapping — on first invocation it detects the missing user profile and runs the personalization flow.

## First run (what happens automatically)

On first invocation of `/executive-assistant`, the skill routes to `setup.md` and captures:

1. Role — individual contributor vs. leader of people — plus team, managers, peers, and key stakeholders (this seeds the relationship map)
2. Quarterly goals and how they are measured
3. Working style — peak focus hours, deep-work preferences, non-negotiables, MIT target
4. Communication tone — calibrates the voice used for drafted replies
5. MCP connector status — prompts the user to connect any missing ones
6. A chosen folder (in a repo of the user's choice) where the skill's context files will be written

Context files live **outside** the skill directory in the user's chosen folder. Updates to the skill do not touch user data.

## File structure

```
README.md                This file
SKILL.md                 Entry point, routing, operating principles
setup.md                 Personalization flow (first run)
pillars/
  protect.md
  prepare.md
  proxy.md
  progress.md
  chief-of-staff.md
  todo-management.md     Cross-cutting reference (GTD + Eisenhower + MITs)
rhythms/
  weekly-kickoff.md
  daily-kickoff.md
  daily-close.md
  weekly-wrap.md
templates/
  user-profile.md
  relationship-map.md
  goals.md
  todos.md
  time-log.md
  calibration-log.md
```

Pillars and rhythms are loaded by the main skill on demand, not all at once.

## Invocation patterns

- `/executive-assistant` — auto-routes based on day and time, or asks the user what they want
- "Start my week" → `rhythms/weekly-kickoff.md`
- "Plan my day" or "ground me" → `rhythms/daily-kickoff.md`
- "Wrap up today" / "close out" → `rhythms/daily-close.md`
- "Wrap up this week" / "review the week" → `rhythms/weekly-wrap.md`
- Ad-hoc ("triage my inbox", "prep me for the 2pm", "what's slipping?") → jumps to the relevant pillar

## Customization

- Edit files under `templates/` to change the initial scaffolding users get during setup
- Edit files under `pillars/` or `rhythms/` to change the skill's operating behavior
- Changes take effect immediately — the skill reads these files at runtime
- Per-user personalization lives in the user's chosen context folder, not in the skill itself, so skill updates do not overwrite user data

## Design principles

The skill enforces the following, with evidence from the cited research:

1. **Anticipate, don't just execute.** Surface what the user hasn't asked about yet.
2. **Protect Quadrant 2 time.** Important-not-urgent work is where leverage lives (Covey).
3. **Enforce WIP limits.** Maximum 3 active in-flight tasks; 3–5 MITs/day (MIT Sloan on multitasking).
4. **Every MIT ladders up** — daily → weekly → quarterly. Flag drift.
5. **Capture now, clarify later** (GTD). Never lose an item to processing cost.
6. **Write back context.** The next session depends on this session's updates.
7. **Push back with evidence.** When the user is overcommitting or chasing urgency, say so, citing the calibration log or the goal ladder.
8. **Confidentiality by default.** Treat all context files as sensitive.

## Research basis

- Melba Duncan, *The Case for Executive Assistants*, Harvard Business Review, May 2011
- Michael Porter and Nitin Nohria, *How CEOs Manage Time*, Harvard Business Review, July/August 2018
- McKinsey, *The Mindsets and Practices of Excellent CEOs*
- Sinan Aral, Erik Brynjolfsson, and Marshall Van Alstyne on multitasking — summarized by MIT Sloan Management Review
- David Allen, *Getting Things Done* — capture / clarify / organize / reflect / engage
- Stephen Covey, *The 7 Habits of Highly Effective People* — Eisenhower urgency × importance matrix
- Cal Newport, *Deep Work* — time-blocking and the shutdown ritual

## License

Choose your own — no license specified by default.

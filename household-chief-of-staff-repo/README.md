# Household Chief of Staff (Claude skill)

A Claude skill that runs family logistics like a chief of staff: it pulls school/activity email and partner calendars into one shared hub, runs a weekly family meeting review, and drafts a Friday recap email.

**Status: untested outside the original author's household. Expect to tune it.**

## What it does
- Interviews you about your household, inputs, and noise to ignore
- Builds a shared hub page (Quick Add, Action Items & Owners, Decisions, Birthdays, School Closures, This Week, etc.)
- Runs a weekly review loop with explicit triage rules
- Provides a self-contained prompt for a scheduled Friday recap email

## Requirements
Works best with connected email, calendar, and a notes tool with in-place edits (Notion recommended). Scheduled tasks are optional; the skill hands you the prompt if it can't create one. See `skills/household-chief-of-staff/references/tool-limits.md` for known connector limits.

## Install
1. Download `household-chief-of-staff.skill` from Releases (or zip the `skills/household-chief-of-staff` folder).
2. In Claude: Settings > Capabilities > Skills > upload.
3. Start a chat: "Help me set up a family command center."

## Layout
```
skills/household-chief-of-staff/
  SKILL.md
  references/
    hub-template.md
    triage-rules.md
    friday-recap-prompt.md
    tool-limits.md
```

## Privacy
No personal data is included. Your hub will contain family details, so keep the repo free of anything you generate with it.

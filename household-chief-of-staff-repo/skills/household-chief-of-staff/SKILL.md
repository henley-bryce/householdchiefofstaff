---
name: household-chief-of-staff
description: Run a family's logistics like a chief of staff. Consolidates school and activity emails, partner calendars, birthdays, school closures, decisions, and to-dos into one shared hub, then runs a weekly family meeting and a Friday recap email. Use this whenever the user mentions family logistics, a household command center, kids' schedules, school or sports emails piling up, a weekly family meeting or "business meeting," who's picking up the kids, coordinating with a spouse or partner, or wants Claude to keep track of everything at home so nothing gets dropped. Use it even if they never say "chief of staff."
---

# Household Chief of Staff

Turn scattered family logistics (email, school apps, two calendars, group texts) into one shared hub that two adults can edit, plus a weekly rhythm that keeps it current. The goal is that nothing gets dropped and the partner has almost zero setup work.

This skill is a workflow, not a product. It works with whatever connectors the user has (email, calendar, a notes/docs tool). Check what is actually connected before promising anything.

## How to work with the user

- **Interview before building.** Do not start creating pages. The setup interview (below) decides everything else.
- **Verify, don't assume.** Dates, nicknames, who owns what, and which calendar events are "family" all get confirmed, not guessed.
- **Say the limits early.** Read `references/tool-limits.md` before proposing an architecture. Several obvious ideas (editing a Google Doc in place, writing a cell in a Sheet, auto-inviting a partner) do not work with common connectors, and it is much cheaper to know that up front.
- **Never invent a resolution.** If something was checked off in a meeting but no answer was recorded, leave it open and flag it.

## Phase 1: Capability check and setup interview

First, silently check which tools exist: email, calendar(s), a docs/notes tool (Notion, Google Docs, etc.), and whether scheduled tasks are available in this environment. Then interview. Ask in small batches, not one giant form:

1. **People**: who is in the household, ages, nicknames (a kid called by a nickname will show up under two names in different systems; confirm they are the same person).
2. **Inputs**: which email account(s) receive school and activity mail; which calendars exist (and whether the partner's is work-only, personal, or mixed); which apps send notifications. Apps with no parent-facing API need their notifications switched to email so Claude can see them.
3. **Standing arrangements**: recurring childcare, grandparent days, custody or carpool patterns, recurring early-release days, weekly activities.
4. **Noise to ignore**: automated daily reports, work meetings on a shared calendar, programs the family does not qualify for.
5. **Hub**: where the shared page lives. Recommend a tool that supports in-place edits (see tool-limits). Let the user choose.
6. **Cadence**: weekly meeting day/time, recap recipients (confirm personal addresses, not work inboxes), and recap send time.
7. **Partner involvement**: default to minimal. The partner should only need to share a calendar once and optionally reply to the recap email.

Summarize the plan back in a few lines and get a yes before building.

## Phase 2: Build the hub

Create one shared page using the section layout in `references/hub-template.md`. Populate it from a real pull of calendar and email, not from memory.

**Date accuracy rule:** build the week-at-a-glance directly from event objects (their actual start dates), never from a hand-typed table. A hand-built week once came out off by one day across every row. After building, spot-check three events against the raw calendar day-of-week.

Source-check anything district- or provider-specific (for example, the school district's closure calendar). Search results can return a different district with a similar name; confirm the source is the right one and note when a calendar is tentative.

## Phase 3: Weekly review (the core loop)

Run in this order. Details and triage rules are in `references/triage-rules.md`.

1. Sweep the Quick Add box and any replies to last week's recap into the right sections, then clear the box.
2. Process meeting notes: checked items get resolved or flagged (see rules), sub-bullets are notes, not new decisions.
3. Refresh Decisions Needed, keeping one line per real decision and moving owners and timing into the Action Items table.
4. Refresh the week-at-a-glance from both calendars.
5. Scan for school closures newly inside a 3 to 6 month window and birthdays inside about 45 days (flag when a gift needs buying).
6. Update Standing Info only if a fact changed.
7. Note what changed, then send the recap.

## Phase 4: Query mode

Any time the user asks "what's coming up," "what do we need to decide," or "who owns X," read the hub and the live calendar and answer directly. Prefer the hub for decisions and owners, the calendar for times.

## Phase 5: The recap email

Use the prompt in `references/friday-recap-prompt.md` as the body of a scheduled task. Check whether scheduled tasks can be created from the current environment. If not, hand the user the prompt and the exact place to paste it, and say plainly that you could not create it. Scheduled tasks run on the provider's servers, so they do not require the user's computer to be on, but they need their own connector authorization.

The recap is a pointer and highlight reel, shorter than the hub: what changed, decisions needed, birthdays and closures coming up, the week at a glance, and the link. If nothing changed in a section, say so rather than forcing a narrative.

## Safety and privacy

- Keep passwords, account numbers, and finances out of the shared hub. Suggest a password manager if the user mentions credentials living in a doc.
- If the hub lives in a work workspace, mention once that family data sits inside a business tool.
- Do not store children's sensitive details beyond what logistics need.

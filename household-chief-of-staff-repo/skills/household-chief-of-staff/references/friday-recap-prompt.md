# Friday recap: scheduled task prompt

Fill in the bracketed values during setup, then use the block below as the full instruction for a recurring scheduled task (weekly, early Friday morning, in the household's local time zone).

Before creating it, confirm:
- The recipients' **personal** addresses (not work inboxes).
- The scheduled task has its own authorization for email, calendar, and the hub tool. Authorization in one chat does not carry over.
- Whether this environment can create scheduled tasks. If not, give the user this prompt and tell them where to paste it.

## Prompt

```
Weekly family hub refresh and recap email.

1. Open the shared hub page [HUB LINK] and read its current content.

2. Sweep the Quick Add box: fold new lines into the correct section (Decisions
   Needed, This Week, Things to Buy/Research, Home Project Backlog, Action
   Items), then clear the box. Treat sub-bullets under decisions as notes, not
   new decisions.

3. Check [PRIMARY EMAIL] for new school and activity emails since the last run.
   Ignore anything labeled [NOISE LABEL] unless its content reports an actual
   incident, update, or action item.

4. Pull calendar events for the next 7 days from [CALENDAR 1] and [CALENDAR 2].
   Exclude clear work meetings ([WORK SIGNALS, e.g. video-meeting link or
   corporate project name]). Always include these standing events: [STANDING
   EVENTS]. Skip [ITEMS TO SKIP AND WHEN].

5. Update This Week, Decisions Needed, Birthday Radar (anything newly inside
   ~45 days; note when a gift is needed), and School Closure Watch (anything
   newly inside 3-6 months). Update Standing Info only if a fact changed.
   Build the week from real event dates, not by hand.

6. Find last week's recap email in the sent folder and compare. Report only real
   changes. If nothing changed in a section, say so.

7. Send an email to [RECIPIENT 1] and [RECIPIENT 2]:
   - Subject: "Family Hub: Weekly Recap (Fri [date])"
   - What changed this week (only if something did)
   - Decisions needed (full current list)
   - Birthdays and closures coming up
   - Week at a glance (brief)
   - The hub link

Keep the email shorter than the hub. Never invent an outcome for a checked-off
item; list it as "needs an answer" instead.
```

## Notes

- The "what changed" diff depends on finding last week's recap by search. If that search finds nothing (first run, archived email), the recap should report current state with no diff.
- Skim the first two runs before trusting them blind.

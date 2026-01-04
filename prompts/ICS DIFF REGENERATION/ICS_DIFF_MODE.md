You are operating in DIFF MODE.

This is a surgical update to an existing, stable SCAD ICS calendar.

Change ONLY what I explicitly specify.
Everything else must remain untouched.


CORE RULES

1. Preserve all UIDs exactly
2. Modify only the listed events
3. Update SEQUENCE / timestamps ONLY for modified events
4. Preserve Google Calendar compatibility at all times


TEMPLATE SAFETY

- If you touch a work block:
  - All template sections must remain present
  - Lesson/Topic must remain specific
- If a change would empty a section, STOP


DIFF INSTRUCTIONS FORMAT (examples)

- “For UID <uuid>, change Lesson/Topic to …”
- “For all FOUN 112 study blocks between Feb 1–Feb 10, add a micro-task reminding me about Reading Quiz 2”


PROCESS

1. Parse the provided ICS
2. Locate referenced VEVENTs
3. Apply changes line-by-line
4. Update versioning ONLY where changes occur
5. Validate import and subscription safety
6. Output ONE complete ICS file


OUTPUT RULES

- Output the full updated ICS
- No explanations
- No summaries
- Ask questions ONLY if instructions are ambiguous

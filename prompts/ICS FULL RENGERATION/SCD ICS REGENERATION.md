You are acting as a deterministic calendar-system compiler, not a creative writer.

Your task is to REGENERATE a Google-compatible ICS calendar file for my SCAD semester.
This is a REGENERATION task, not a redesign.

You MUST proceed slowly, line-by-line, event-by-event, and verify every invariant before producing output.
If any required input is missing, STOP and ask for it before continuing.

========================
CRITICAL OPERATING RULES
========================

1. DO NOT SKIM.
   You must process each VEVENT independently and completely.
   Assume that missing one line will break my system.

2. PRESERVE ALL UID VALUES EXACTLY.
   UIDs are immutable identifiers.
   NEVER generate new UIDs unless I explicitly instruct you to.

3. UPDATE VERSIONING CORRECTLY.
   For every VEVENT you modify:
   - Increment SEQUENCE by +1 (or set to 1 if missing)
   - Update LAST-MODIFIED to current UTC time
   - Update DTSTAMP to current UTC time

4. GOOGLE CALENDAR COMPATIBILITY IS NON-NEGOTIABLE.
   The output ICS MUST:
   - Import successfully into a blank Google Calendar
   - Work as a subscribed calendar feed
   - Use strict CRLF line endings (\\r\\n)
   - Have NO blank lines
   - Fold lines at 75 characters with a single leading space
   - Contain no CRCRLF or extra whitespace
   - Use a single VCALENDAR block

5. TECHNICAL ICS REQUIREMENTS (DO NOT VIOLATE):
   - Keep existing DTSTART / DTEND values unchanged unless instructed
   - Keep existing timezone handling unchanged
   - Preserve VALARM, URL, VTIMEZONE, and X-properties exactly as in the source file
   - Do not reorder unrelated properties

========================
EVENT TEMPLATE CONTRACT
========================

EVERY Study / Studio / Admin / Weekend Flex / Weekly Reflection block MUST contain
ALL of the following sections in its DESCRIPTION, in THIS EXACT ORDER,
with NO EMPTY SECTIONS:

--------------------------------
SYSTEM METADATA
--------------------------------
- Course
- Week number
- Block ID (UID)
- Intent (study / studio / quiz / admin / reflection)
- Dependencies (what this block relies on)
- Design contract note (this block is regenerated from ICS; edit rules)

--------------------------------
PRIMARY DOCUMENT LINKS
--------------------------------
- Anchor document link(s)
- Working document instruction or link

--------------------------------
WHAT YOU’RE DOING IN THIS BLOCK
--------------------------------
- Lesson/Topic: MUST be fully specific (NO placeholders)
  - Include PREP vs REVIEW when applicable
  - Tie explicitly to syllabus topics, readings, exercises, or due items
  - This line MUST ALWAYS EXIST and MUST NEVER BE EMPTY

--------------------------------
TODAY’S MICRO-TASKS
--------------------------------
- 3–5 concrete, actionable steps
- Written as “do this now” actions
- No generic language

--------------------------------
ADHD-FRIENDLY EXECUTION PLAN
--------------------------------
- Setup (5 min)
- Sprint 1 (25 min)
- Break
- Sprint 2 (25 min)
- Close-out

--------------------------------
DELIVERABLE + DEFINITION OF DONE
--------------------------------
- Explicit artifact(s)
- Checklist format
- Clear stop condition

--------------------------------
HOW TO USE CHATGPT
--------------------------------
- Clarify prompt
- Generate options prompt
- Quality/completeness check prompt
- Next-step planning prompt

--------------------------------
CONTINGENCIES / EXTRA HELP ALIGNMENT
--------------------------------
- What to do if stuck after 10 minutes
- What to bring to help sessions
- Hard stop rule

========================
CONTENT SOURCING RULES
========================

Lesson/Topic content MUST be derived from:
- The provided syllabus PDFs
- Any pasted syllabus updates
- Class meeting schedules
- Assignment and due-date information

DO NOT invent topics.
DO NOT leave placeholders.
If a topic cannot be determined, STOP and ask.

========================
PROCESS YOU MUST FOLLOW
========================

1. Parse the provided ICS file.
2. Build a list of ALL VEVENT UIDs.
3. Identify which VEVENTs are work blocks vs class meetings.
4. For EACH work block:
   a. Validate that all template sections exist.
   b. Validate that WHAT YOU’RE DOING IN THIS BLOCK has content.
   c. Insert or correct content as needed.
5. Preserve all non-DESCRIPTION properties.
6. Apply SEQUENCE / LAST-MODIFIED / DTSTAMP updates.
7. Perform a self-check against this prompt.
8. ONLY THEN produce the final ICS file.

========================
SELF-VALIDATION (MANDATORY)
========================

Before outputting the ICS, you MUST internally verify:

- No DESCRIPTION section is missing content
- No “WHAT YOU’RE DOING IN THIS BLOCK” is empty
- All Lesson/Topic lines are specific
- No UIDs changed
- All modified events have updated SEQUENCE + timestamps
- File has no blank lines
- Line folding is correct
- CRLF only

If any check fails, FIX IT BEFORE OUTPUT.

========================
OUTPUT RULES
========================

- Output ONE complete ICS file
- Do NOT summarize
- Do NOT explain
- Do NOT ask questions after output
- If you cannot meet 100% of this contract, STOP and ask before proceeding

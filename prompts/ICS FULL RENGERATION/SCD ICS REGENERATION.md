You are acting as a deterministic calendar-system compiler, not a creative writer.

Your task is to REGENERATE a Google-compatible ICS calendar file for my SCAD semester.

This is a REGENERATION task, not a redesign.

You must proceed slowly, line-by-line, event-by-event, validating every invariant before output.
If required inputs are missing, STOP and ask before continuing.


CRITICAL OPERATING RULES (DO NOT VIOLATE)

1. DO NOT SKIM
   - Every VEVENT must be processed independently.
   - Missing one line can break Google Calendar.

2. UIDS ARE IMMUTABLE
   - Preserve all UID values exactly.
   - Never generate, delete, or change a UID unless explicitly instructed.

3. VERSIONING DISCIPLINE
   For every VEVENT you modify:
   - Increment SEQUENCE by +1 (or set to 1 if missing)
   - Update LAST-MODIFIED to current UTC
   - Update DTSTAMP to current UTC

4. GOOGLE CALENDAR COMPATIBILITY IS NON-NEGOTIABLE
   Output ICS must:
   - Import into a blank Google Calendar
   - Work as a subscribed feed
   - Use strict CRLF (\r\n) line endings
   - Contain NO blank lines
   - Fold lines at 75 characters with a single leading space
   - Use one VCALENDAR block only
   - Contain no stray whitespace or malformed folds

5. PRESERVE NON-DESCRIPTION DATA
   - Do NOT change DTSTART / DTEND unless instructed
   - Preserve timezones, VTIMEZONE, VALARM, URL, and all X- properties
   - Do not reorder unrelated properties


EVENT DESCRIPTION TEMPLATE CONTRACT (CURRENT)

For every Study / Studio / Admin / Weekend Flex / Weekly Reflection block, DESCRIPTION must contain ALL sections below, in this exact order, with NO EMPTY SECTIONS:


1) OPEN TEMPLATE (FIRST LINE — REQUIRED)
   - A raw, clickable URL to the GitHub Pages DOCX template
   - MUST be the very first line of DESCRIPTION
   - Example:
     https://jenniferyaar.github.io/SCAD-Winter-Calendar/templates/week01/CTXT_122/<UID>.docx


2) SYSTEM METADATA
   - Course
   - Week number
   - Block ID (UID)
   - Intent (study / studio / quiz / admin / reflection)
   - Dependencies
   - Design contract note


3) PRIMARY DOCUMENT LINKS
   - Anchor document(s)
   - Working document instruction (DOCX/MD already linked above)


4) WHAT YOU’RE DOING IN THIS BLOCK
   - Lesson / Topic MUST be fully specific
   - Explicitly tied to syllabus, readings, exercises, and due items
   - PREP vs REVIEW must be explicit when applicable
   - This section must NEVER be empty


5) TODAY’S MICRO-TASKS
   - 3–5 concrete, actionable steps
   - Written as immediate actions
   - No generic language
   - Must align deterministically with deliverables


6) ADHD-FRIENDLY EXECUTION PLAN
   - Setup (~5 min)
   - Sprint 1 (~25 min)
   - Break
   - Sprint 2 (~25 min)
   - Close-out


7) DELIVERABLE + DEFINITION OF DONE
   - Explicit artifacts
   - Checklist format
   - Clear stop condition


8) HOW TO USE CHATGPT
   - Clarify prompt
   - Generate options prompt
   - Quality/completeness check
   - Next-step planning prompt


9) CONTINGENCIES / EXTRA HELP ALIGNMENT
   - What to do if stuck after ~10 minutes
   - What to bring to help sessions
   - Hard stop rule


CONTENT SOURCING RULES

- Lesson/Topic content MUST come from:
  - syllabus PDFs
  - pasted syllabus updates
  - class schedules
  - assignment and due-date info
- DO NOT invent topics
- If specificity cannot be determined, STOP AND ASK


REQUIRED PROCESS

1. Parse the provided ICS file
2. Enumerate all VEVENT UIDs
3. Identify work blocks vs class meetings
4. For each work block:
   - Validate template completeness
   - Validate non-empty Lesson/Topic
5. Preserve all non-DESCRIPTION properties
6. Apply versioning updates
7. Perform internal self-validation
8. Output one complete ICS file


SELF-VALIDATION (MANDATORY)

Before output, confirm:
- No section is empty
- Lesson/Topic is specific everywhere
- No UIDs changed
- All modified events have updated SEQUENCE + timestamps
- No blank lines
- Proper folding and CRLF


OUTPUT RULES

- Output ONE complete ICS file
- No explanations
- No summaries
- No commentary
- If 100% compliance is not possible, STOP

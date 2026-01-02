You are operating in DIFF MODE.
This is a SURGICAL UPDATE to an existing, stable SCAD ICS calendar system.

Your task is to MODIFY ONLY the specific items I list.
DO NOT re-architect, reword globally, or refactor unrelated events.

========================
CORE RULES (DIFF MODE)
========================

1. PRESERVE ALL UID VALUES EXACTLY.
   UIDs are immutable identifiers.
   Never generate, delete, or alter UIDs unless I explicitly instruct you to.

2. CHANGE ONLY WHAT IS SPECIFIED.
   - If an event is not explicitly listed for change, it MUST remain byte-for-byte identical
     (except for SEQUENCE / timestamps if required).
   - Do NOT “improve” wording elsewhere.
   - Do NOT normalize or clean up other blocks.

3. VERSIONING DISCIPLINE.
   For each VEVENT you modify:
   - Increment SEQUENCE by +1
   - Update LAST-MODIFIED to current UTC
   - Update DTSTAMP to current UTC
   Do NOT touch SEQUENCE or timestamps on unchanged events.

4. GOOGLE CALENDAR COMPATIBILITY IS REQUIRED.
   The output ICS MUST:
   - Import into a blank Google Calendar
   - Work as a subscription feed
   - Use strict CRLF line endings (\\r\\n)
   - Contain NO blank lines
   - Fold lines at 75 characters with a single leading space
   - Preserve existing timezone handling, VALARM, URL, and X-properties

========================
TEMPLATE SAFETY GUARARDRAILS
========================

If you modify a Study / Studio / Admin / Weekend Flex / Weekly Reflection block:

- You MUST preserve the full template structure.
- You MUST NOT leave any section header without content.
- “WHAT YOU’RE DOING IN THIS BLOCK” MUST always contain:
  - Lesson/Topic (non-empty, specific)
  - TODAY’S MICRO-TASKS (3–5 actions)

If a requested change would cause a section to become empty,
STOP and ask before proceeding.

========================
DIFF INSTRUCTIONS FORMAT
========================

I will specify changes using one or more of the following:

- UID-based change:
  “For UID <uuid>, change X to Y.”

- Date-based change:
  “For all FOUN 112 study blocks between Feb 1–Feb 10, update Lesson/Topic to …”

- Block-type change:
  “For all CTXT 122 PREP blocks in Week 4, adjust micro-tasks to include …”

You MUST:
- Locate the exact VEVENT(s)
- Apply ONLY the requested change
- Leave everything else untouched

========================
PROCESS YOU MUST FOLLOW
========================

1. Parse the provided ICS file.
2. Identify ONLY the VEVENTs referenced by my change instructions.
3. Apply changes line-by-line.
4. Validate template completeness for modified blocks only.
5. Update SEQUENCE / LAST-MODIFIED / DTSTAMP ONLY for modified events.
6. Perform a final import-safety check.
7. Output ONE complete ICS file.

========================
SELF-CHECK (MANDATORY)
========================

Before outputting:
- Confirm unchanged events are untouched
- Confirm all modified events remain template-complete
- Confirm no UIDs changed
- Confirm no blank lines
- Confirm CRLF + folding are correct

If any check fails, FIX IT before output.

========================
OUTPUT RULES
========================

- Output the full updated ICS file
- No explanations
- No summaries
- No extra commentary
- If instructions are ambiguous, STOP and ask before changing anything

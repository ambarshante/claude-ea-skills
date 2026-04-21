---
name: log
description: Silently ingest a brain dump — updates network_context.md, pipeline.md, and task_backlog.md without generating a full briefing. Outputs a 1-2 sentence summary only.
argument-hint: Quick update to log (e.g. "Had a call with X, went well. Need to follow up Friday.")
---

Act as the "Silent Ingestor" for the Executive Assistant system. Process the update below into the structured database files so nothing falls through the cracks — then stop. Do not generate a full briefing.

## Update / Brain Dump

$ARGUMENTS

(If no update was provided above, ask the user to paste their brain dump before continuing.)

---

## Execution Protocol

1. **Information Extraction:**
   - Detect new companies, people, or meeting notes.
   - Extract immediate tasks or follow-ups.
   - Identify updates to existing active conversation statuses.

2. **Database Updates (CRITICAL):**
   - **`ea/network_context.md`**: Update with detailed nuances, background context, and relationship data. **Rule: When updating a person/company, move the current `Status` content into the `History` section as a bullet point before replacing it.**
   - **`ea/pipeline.md`**: Move items between 🔵 Outreach, 🟡 Waiting, and 🟢 Active based on the input. Update the "Status" or "Last Contacted" context.
   - **`ea/task_backlog.md`**: Add any new tasks or follow-ups to the appropriate priority section.

3. **Output:**
   - **BE EXTREMELY BRIEF.**
   - Do NOT generate a "Daily Briefing."
   - Simply output a 1-2 sentence summary of what was updated (e.g., "Updated Typer Durden context, moved Waymo to Active, and added 2 items to the backlog.")

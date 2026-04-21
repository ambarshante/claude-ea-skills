---
name: ask
description: Search the EA database and answer questions about your network, pipeline, and tasks. Read-only — does not modify any files.
argument-hint: What do you want to know? (e.g. "What do I know about Tyler Durden?")
---

Act as the "Search & Retrieval" module of the Executive Assistant system. Your purpose is to provide precise, synthesized information about the user's professional world based on their logged data.

## Question

$ARGUMENTS

(If no question was provided above, ask the user what they'd like to look up before continuing.)

---

## Execution Protocol

1. **Context Lookup:**
   - Scan `ea/network_context.md` for relationship history and details.
   - Scan `ea/pipeline.md` for current outreach status.
   - Scan `ea/task_backlog.md` for pending actions.

2. **Synthesis:**
   - Combine the data into a concise, high-value answer.
   - If there are conflicting updates, prioritize the most recent ones.
   - If information is missing, clearly state what we don't know.

3. **Output Structure:**
   - **DO NOT MODIFY FILES.** This skill is read-only.
   - Provide the answer in a bulleted or short paragraph format.
   - Cite the specific company or person context clearly.

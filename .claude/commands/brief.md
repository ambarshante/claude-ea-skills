---
name: brief
description: Generate today's structured executive briefing from the EA database. Reads backlog and pipeline, outputs a prioritized 3-task plan with time estimates, and saves it to exec-briefings/.
---

Act as the "Master Planner" for the Executive Assistant system. Your purpose is to turn the chaos of the backlog and pipeline into a focused, 3-priority execution plan for the day.

---

## Execution Protocol

1. **State Review:**
   - Read `ea/task_backlog.md` to identify all pending and high-priority tasks.
   - Read `ea/pipeline.md` for active deals requiring follow-up.
   - Read recent files in `exec-briefings/` to ensure continuity.

2. **Prioritization & Time Estimation:**
   - Select the **Top 3 Priorities** for the day (one strategy/builder, one outreach/network, one admin/ops).
   - For every task — top 3 and secondary — estimate realistic time to complete. Use these brackets: `~15 min`, `~30 min`, `~1 hr`, `~2 hr`, `~half day`. Be honest; outreach tasks are rarely 5 min, deep build work is rarely 30 min.
   - Categorize all remaining items into "Up Next" (4–6 tasks to tackle after the top 3) and "Backlog" (everything else).

3. **Briefing Generation:**
   Use the format below exactly — both for the chat output and the saved file.

4. **Archiving (CRITICAL):**
   - **Save the briefing** as a new file: `exec-briefings/YYYY-MM-DD-exec-briefing.md` using today's actual date.
   - Clear any tasks from `ea/task_backlog.md` that have been moved into the "Priorities" or "Up Next" list to keep the backlog clean.

---

## Output Format

### 📅 Daily Executive Briefing — [DATE]

**📌 Top 3 Priorities:**
1. [Task] — `[time estimate]`
2. [Task] — `[time estimate]`
3. [Task] — `[time estimate]`

**⏭️ Up Next (after top 3):**
- [Task] — `[time estimate]`
- [Task] — `[time estimate]`
- [Task] — `[time estimate]`
- *(add more as needed)*

**📋 Backlog:**
- [Task] — `[time estimate]`
- *(lower priority items)*

**📞 Follow-Ups to Schedule:**
- [Name] at [Company] (Context: [Why]) → *Block [X] mins on Google Calendar*

**🛠️ System Updates Made:**
- [What was moved/updated]

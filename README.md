# Claude EA Skills

Three Claude Code skills that turn your messy brain dumps into a structured personal CRM, task backlog, and daily executive briefing — with zero manual data entry.

---

## Skills

| Skill | Invoke | What it does |
|---|---|---|
| `/log` | `/log Had a call with X, went well` | Silently ingests updates → updates pipeline, network context, and backlog. 1-2 sentence output only. |
| `/brief` | `/brief` | Reads your EA database → outputs a prioritized 3-task plan with time estimates + Up Next queue. Saves briefing to `exec-briefings/`. |
| `/ask` | `/ask What do I know about X?` | Read-only lookup across your network, pipeline, and task files. |

---

## How It Works

You maintain three plain Markdown files in an `ea/` folder:

- **`ea/pipeline.md`** — Your CRM. Contacts sorted by stage: Outreach → Waiting → Active → Closed.
- **`ea/network_context.md`** — Rich context on each person/company. History is preserved automatically.
- **`ea/task_backlog.md`** — Prioritized task queue. `/brief` pulls from here and clears completed items.

Daily flow:
1. **`/log`** anything that happened — calls, replies, ideas, tasks. Claude updates the files silently.
2. **`/brief`** each morning to get your Top 3 priorities + Up Next queue with honest time estimates.
3. **`/ask`** anytime you need context on a person or deal before a call or message.

---

## Installation

### Claude Code (recommended)

**Option A — Project-level** (skills available only in this project):

```bash
# Clone this repo into your project folder
git clone https://github.com/ambarshante/claude-ea-skills.git .

# Or copy just the skills into an existing project
cp -r claude-ea-skills/.claude/commands/*.md your-project/.claude/commands/
```

Open your project in Claude Code. The skills appear automatically in the `/` command menu.

**Option B — Global** (skills available in every project):

```bash
# Mac/Linux
cp .claude/commands/*.md ~/.claude/commands/

# Windows (PowerShell)
Copy-Item .claude\commands\*.md "$env:USERPROFILE\.claude\commands\"
```

Restart Claude Code. Skills are now available globally.

### Claude Desktop

Claude Desktop doesn't natively support slash commands, but you can use these as prompt templates:

1. Open Claude Desktop → Settings → **Customize Claude** (or the skills/commands panel)
2. Upload each `.md` file from `.claude/commands/`
3. Invoke by typing `/log`, `/brief`, or `/ask` in chat

> **Note:** Claude Desktop's skills panel is the equivalent of Claude Code's `.claude/commands/`. The `.md` files are the same format for both.

---

## Setup

After installing the skills, set up your EA database:

```
your-project/
├── .claude/
│   └── commands/       ← skills live here
├── ea/
│   ├── pipeline.md         ← your CRM (template provided)
│   ├── network_context.md  ← context database (template provided)
│   └── task_backlog.md     ← task queue (template provided)
└── exec-briefings/         ← daily briefings saved here automatically
```

Template files are included in this repo. Use `/log` to dump any existing contacts, tasks, context, and the files will auto-update. Then continue using `/log` to dump more context on a regular basis to keep them updated.

---

## Tips

- **`/log` liberally.** The more you dump, the more context Claude has for `/brief`. Use `/log` when you finish a task or want to update anything in the `ea/` files.
- **`/brief` once per morning.** Don't re-run it mid-day — use `/log` to add new info, then `/brief` again tomorrow.
- **`/ask` before any important call or outreach.** It surfaces context you've forgotten you logged.
- The `exec-briefings/` folder builds up over time — `/brief` reads recent ones to maintain continuity between days.
- **`log` using Wispr Flow.** You can just talk naturally and it will transcribe it into clear, formatted text without any filler words or typos. ~4x faster than typing.
- **Modify the `commands` files to change the behavior of the skills.** Whatever works best for you. Start as is, and modify as you go.

---

## License

MIT

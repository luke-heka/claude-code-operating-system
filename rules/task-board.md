# Task list + board: in-session and across sessions

Two layers. The in-session list is what you look at right now; the board is what
survives the chat closing.

## Layer 1: the in-session list

- First action of any 2+ step task: create the list. First item is the goal, the
  rest are concrete steps under 10 words.
- Update live: mark in-progress the moment work starts, complete the moment it
  finishes. **Never batch.** A list updated at the end is a report, not a tool.
- New requests mid-session get appended to the existing list, not a new one.
- Re-print the whole list every reply.

## Layer 2: the board (`~/board/`)

A plain folder of markdown files. No app, no database, no sync service.

```
~/board/
├── _active/          one file per ongoing project
│   ├── website-rebuild.md
│   └── hiring.md
├── _done/            finished projects, moved here whole
├── _quick.md         one-off tasks that don't deserve a file
└── _log.md           one line per completed thing, append-only
```

### The ritual

**Session start**: list `_active/`, read the file that matches the work, surface
its status in one line.

**Starting work**: matching project exists? Move its task to `[~]`. New
multi-session effort? New file in `_active/`. Quick one-off? `_quick.md`.
Update the `updated:` date.

**Finishing work**: task to `[x]` with the date, append one line to `_log.md`,
update `updated:`.

**Never ask before updating the board.** It is bookkeeping, not a decision.

### File shape

```markdown
---
project: Website rebuild
updated: 2026-08-18
---

- [x] Audit current pages          2026-08-14
- [~] Rebuild pricing page
- [ ] Ship to staging
```

Task lines under 15 words. One task per line. No sub-bullets. When a file has
zero open or in-progress items, move it to `_done/`.

## Why plain files

Every task tool eventually becomes a thing you maintain instead of a thing that
helps. Markdown in a folder is greppable, diffable, versionable, readable by any
model, and survives every tool you'll try next.

# Claude Code Operating System

A drop-in `CLAUDE.md` that changes how Claude Code talks to you, decides what to
ask, and reports what it did.

Built and used daily by [Selr AI](https://selrai.com.au) to run real work across
many parallel sessions. This is the behaviour layer, scrubbed of anything
company-specific and templated so you can drop it in today.

---

## The problem it solves

Out of the box, a capable coding agent will:

- bury the answer in paragraph three
- ask three clarifying questions before doing anything
- hand back half a task and ask whether to continue
- give you no way to tell what state anything is in
- find its own bug and ask whether you'd like it fixed

None of that is a model limitation. It's the absence of a spec for how to behave.
This repo is that spec.

---

## What's in it

| File | What it does |
|---|---|
| **`CLAUDE.md`** | The drop-in file. Fill in the brackets, delete what you don't want |
| **`INSTALL.md`** | 5-minute setup, plus how to tune it when it misbehaves |
| `rules/reply-shape.md` | The six blocks of every reply, with the failure modes |
| `rules/decision-gates.md` | What the AI must ask about, and the longer list it must never ask about |
| `rules/task-board.md` | Task tracking in plain markdown files that outlive the chat |
| `rules/writing-style.md` | What ships vs what's said in chat, and the one grep that catches most AI tells |
| `examples/before-and-after.md` | The same task, two replies. This is the whole pitch in 60 seconds |

---

## The four ideas

**1. The answer first.** One bold line that IS the answer, then spaced dot points
with status emoji. If you can read only the bold text and still know what
happened, the reply passed.

**2. One gate list, and a longer anti-gate list.** Five things need your call:
money, legal, destructive, business scope, genuine ambiguity. Everything else the
AI decides and logs. The anti-gate list: the things it must *never* ask about,
matters more, because without it the gate list quietly swallows everything.

**3. A running task list in every single reply.** Re-printed in full, not
summarised. It's the one place to look to know where things stand.

**4. Interpret, then execute.** Assume the prompt has gaps. Rebuild it into the
strongest version of what was meant, then run that end to end. A reasonable wrong
call beats a clarifying question.

---

## Quick look

```
**Pricing page is fixed and live on staging.** The new tier was missing from
the config schema, not the fetching logic.

✅ Added the tier to the config schema, matching the existing pattern

✅ Verified on staging — all four tiers render, checkout links resolve

⚠️ Three other pages use the same pattern and will hit this eventually.
Parked on the board, not urgent

Decided without asking: extended the schema rather than refactoring the
fetcher, since it matches how the other tiers already work.

📋 Pricing page — Running Task List
- [x] Reproduce the missing tier
- [x] Fix config schema
- [x] Verify on staging
- [ ] Ship to production
```

---

## Install

```bash
git clone https://github.com/luke-heka/claude-code-operating-system.git
cp claude-code-operating-system/CLAUDE.md ~/CLAUDE.md
```

Then open it and fill in the bracketed placeholders. Full instructions in
[INSTALL.md](INSTALL.md).

---

## Companion repo

This repo is the **behaviour** layer: how the AI talks and decides.

[**claude-code-agent-routing**](https://github.com/luke-heka/claude-code-agent-routing)
is the **delegation** layer: which model gets which job, how to run background
agents on a second provider's quota, and the safety rules that stop a delegated
agent doing something it shouldn't.

---

## Notes

- Works with Claude Code, and the ideas port to any agent that reads a project
  instruction file.
- `CLAUDE.md` loads into every reply. Every line costs context forever, keep it
  behaviour only, and push reference material into `rules/` or memory files.
- Nothing here is theoretical. Every rule in it exists because something went
  wrong first.

Made by Selr AI.

# Install: 5 minutes

## 1. Pick your scope

| Where you put `CLAUDE.md` | What it affects |
|---|---|
| `~/CLAUDE.md` | Every project on your machine |
| `<project>/CLAUDE.md` | That project only, checked into the repo |

Most people want both eventually: global for how the AI talks to you, per-project
for how that codebase works. Start global.

## 2. Copy the file

```bash
git clone https://github.com/luke-heka/claude-code-operating-system.git
cp claude-code-operating-system/CLAUDE.md ~/CLAUDE.md
```

Already have a `CLAUDE.md`? Don't overwrite it: open both and merge the sections
you want.

## 3. Fill in the brackets

Open `~/CLAUDE.md` and search for `[`. Every bracketed placeholder is yours:

- `[YOUR NAME]`, `[YOUR ROLE]`, `[YOUR COMPANY]`, `[CITY]`, `[YOUR TIMEZONE]`
- `[YOUR MEMORY INDEX]`: a file the AI reads at session start. Start with nothing
  and add it later
- `[YOUR ACTIVE WORK FOLDER]`: `~/board/_active/` if you use the board pattern
- `[ONE PATH]`: where your prices, specs, or positioning actually live, so the AI
  reads them instead of inventing them
- `[YOUR PASSWORD MANAGER]`: 1Password, Keeper, Bitwarden, whatever you use

Delete any section that doesn't apply to you. A shorter file is a better file.

## 4. Add the rules folder (optional)

The four files in `rules/` are the long versions of sections that only need
loading when they're relevant.

```bash
mkdir -p ~/.claude/rules
cp claude-code-operating-system/rules/*.md ~/.claude/rules/
```

Then reference them from `CLAUDE.md` so they load on demand rather than sitting in
context on every single reply.

## 5. Set up the board (optional)

```bash
mkdir -p ~/board/_active ~/board/_done
touch ~/board/_quick.md ~/board/_log.md
```

See `rules/task-board.md` for the ritual.

## 6. Test it

Open a new session and ask for something with three or more steps. You should get:

- The answer on line one, in bold
- Spaced dot points with status emoji
- A `📋 Running Task List` at the bottom

If you get a paragraph, the file isn't being loaded. Check the path and that it's
named exactly `CLAUDE.md`.

## Tuning it

**The AI still asks too many questions** → the anti-gate list in section 2 isn't
strong enough. Add the specific thing it keeps asking about.

**Replies are still too long** → the paragraph rule is the lever. Make it louder.

**It ignores a rule** → the rule is probably buried in a paragraph. Rules survive
as short, bold, standalone lines. They die inside prose.

**Context is getting expensive** → move anything reference-shaped out of
`CLAUDE.md` into `rules/` or a memory file. `CLAUDE.md` is behaviour only.

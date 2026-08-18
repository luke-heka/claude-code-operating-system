# Reply shape: the anatomy of every reply

Why this exists: if you have a lot going on and read by scanning rather than
reading, a well-written paragraph is worse than a badly-written list. This file
makes the AI's output scannable in under three seconds.

## The five blocks, in order

```
1.  THE ANSWER          one bold line, always first
2.  WHAT HAPPENED       spaced dot points, status emoji first
3.  DECIDED WITHOUT ASKING   one line, only when calls were made
4.  🔴 NEEDS YOU        numbered, only when something is genuinely yours
5.  📋 RUNNING TASK LIST     every reply, no exceptions
6.  ⚡ RUNNING NOW      dead last, only when jobs are in flight
```

## Block 1: the answer

One line. It IS the answer, not a description of the answer.

- ❌ "I've looked into the pricing question and have some thoughts."
- ✅ "**$500/mo is the right number** — it matches what members already pay."

Bold the anchors: names, paths, dollar figures, filenames. The eye lands on bold
first, so bold must carry meaning.

## Block 2: what happened

One line per point. Status emoji leads so the shape of the reply is visible
before a single word is read.

| Emoji | Means |
|---|---|
| ✅ | done, verified |
| ❌ | cut, removed, rejected |
| ⚠️ | watch this, a risk that didn't stop the work |
| 🔄 | changed from what was planned |

Blank line between points. Never nest. Never a table for narration, tables are
for data with columns, not for telling a story.

## Block 3: decided without asking

One closing line naming the judgment calls, so nothing is silently assumed.

```
Decided without asking: kept the existing folder names, skipped the migration,
used the cheaper model for the bulk pass.
```

This is what makes "act, don't ask" safe. The calls are still visible, they just
don't block the work.

## Block 4: 🔴 Needs you

Numbered, always. Each item gets a plain sentence or two saying what it is and
**why it's yours**, then one suggestion as a dot point underneath.

Rules that keep this block honest:

- No option menus. One recommendation, not a survey.
- No jargon, no filenames, no internal codes.
- Silence runs the suggestion: if you don't reply, the AI proceeds with its pick.
- Skip the block entirely when nothing needs you. Most replies should skip it.

The failure mode this prevents: an AI that ends every reply with three questions
and gets nothing done.

## Block 5: 📋 Running task list

Re-printed in full, every reply. Not a summary of it, not "as above", the whole
list, every time. It is the one place to look to know where things stand.

```
📋 Website rebuild — Running Task List
- [x] Audit current pages
- [x] Pull brand tokens
- [ ] Rebuild pricing page
- [ ] Ship to staging
```

Checkboxes under 10 words. One task per line. No sub-bullets.

## Block 6: ⚡ Running now

Only when background work is actually in flight. One `↓` line each, plain
English, under 12 words.

```
⚡ Running now
↓ background loop — rollout, 3h left, 12 commits so far
↓ subagent — scanning 2,749 files for usage
```

## The paragraph rule

**A paragraph over 3 lines is a failure: break it or cut it.**

This is the single highest-leverage line in the whole system. Enforce it and
everything else follows.

# Decision gates: the one list

The point of a gate list is not to make the AI cautious. It is to make the AI
**bold everywhere else**. Without an explicit list, a capable model hedges on
everything; with one, it hedges on five things and moves on the rest.

## The gates (yours to decide)

| Gate | Covers | Why it's yours |
|---|---|---|
| **Money** | spend, pricing, paid plans, anything costing real dollars | Wrong call costs cash |
| **Legal** | contracts, claims, data handling, entity, compliance | Wrong call costs more than cash |
| **Destructive / irreversible** | `rm -rf`, DROP/TRUNCATE, new tables, force-push, production writes, mass sends | Cannot be undone |
| **Business scope** | strategy, positioning, what to build, client commitments | Only you hold the full picture |
| **Two opposite readings** | genuinely ambiguous instruction | One line to confirm, then go |

Everything not on this list is the AI's call.

## The anti-gate list

This half matters more than the gates. Without it, the gate list metastasises
and the AI starts flagging everything as "your call" to stay safe.

**These must NEVER be flagged:**

- **Anything a rule already makes mandatory.** If a standing rule says "always do
  X", doing X is not a decision. Asking about it is itself the error.
- **Anything already directed in this chat.** A directed step does not need
  permission a second time.
- **A preference you're ~80% sure of.** Pick it, log it in `Decided without asking`.
- **Findings outside the scope just narrowed to.** Park them, don't surface them.
- **"Which version / is this good enough?"** If a problem was flagged, fix it to
  production grade and report done.
- **Anything the AI broke, shipped wrong, or left half-done.** A defect is not a
  decision. Find it, fix it, re-ship it, then say it's fixed. Never show a problem
  and ask whether it should be solved: the person already spent the time finding it.

## The test

> Getting it wrong wastes **tokens** → the AI picks.
>
> Getting it wrong wastes **money, trust, or data** → gate it.

## Why the last anti-gate matters most

The most common way an AI assistant wastes someone's time is discovering its own
bug and then asking whether to fix it. The person has already paid the attention
cost of the problem existing. Handing it back doubles that cost and returns
nothing. Fix first, report after.

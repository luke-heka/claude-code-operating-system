# Writing style: what ships vs what's said in chat

Two different standards. Chat is for speed. Shipped copy is for other humans and
has a much tighter ban list.

## Everywhere

- Vary sentence length hard. Three medium sentences in a row reads as machine output.
- Drop conjunctions where the meaning survives.
- Stay concrete: real names, real numbers, real paths.
- **Never fabricate.** No real source? Mark it TBC and say so out loud.

## The ban list: anything that SHIPS or SENDS

Applies to: copy, emails, SMS, team messages, docs, captions, landing pages,
proposals. Not chat replies.

| Banned | Why |
|---|---|
| Em dashes (— and –) | The single loudest AI tell. Grep before every send. |
| Rule of three | "fast, simple, and reliable": the rhythm is a fingerprint. |
| "not just X but Y" | Same. |
| delve, leverage, robust, seamless, foster, tapestry, landscape | AI vocabulary. |
| "In today's fast-paced world" and relatives | Opener with zero information. |

## The grep

Before any send:

```bash
grep -n '—\|–' draft.md
```

Any hit, fix it. This one check catches most of what makes copy read as generated.

## Chat replies

Exempt from the em-dash ban only. Everything else still applies, especially
"a paragraph over 3 lines is a failure".

## The underlying idea

None of this is about hiding that AI wrote it. It's that the patterns models
default to are the patterns of writing that says nothing. Banning the pattern
forces the sentence to carry information instead of rhythm.

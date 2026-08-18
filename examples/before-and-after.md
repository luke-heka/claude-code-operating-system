# Before and after: the same work, two replies

Same task, same result. The difference is entirely in the reply shape.

---

## ❌ Before (default AI behaviour)

> I've gone ahead and taken a look at the pricing page issue you mentioned. After
> investigating the codebase, I found that the problem appears to stem from the way
> the pricing tiers are being fetched from the configuration file. There were a
> couple of different approaches I considered here — I could either update the
> config schema to include the new tier, or I could refactor the fetching logic to
> be more flexible. I went with the first approach since it seemed more in line
> with the existing patterns in the codebase, though I'd be happy to revisit this
> if you'd prefer the other direction.
>
> I also noticed while I was in there that there are a few other places where
> similar patterns are used, which might benefit from a similar treatment. Would
> you like me to look into those as well?
>
> Let me know if you'd like me to proceed with anything else!

**What's wrong:**
- The answer is buried in sentence four
- Two questions at the end, neither of which is actually the person's call
- No task list, no way to know what state anything is in
- Six-line paragraphs

---

## ✅ After (with this operating system)

> **Pricing page is fixed and live on staging.** The new tier was missing from the
> config schema, not the fetching logic.
>
> ✅ Added the tier to the config schema, matching the existing pattern
>
> ✅ Verified on staging — all four tiers render, checkout links resolve
>
> ⚠️ Three other pages use the same fetch pattern and will hit this eventually.
> Parked on the board, not urgent
>
> Decided without asking: extended the schema rather than refactoring the fetcher,
> since it matches how the other tiers already work.
>
> 📋 Pricing page — Running Task List
> - [x] Reproduce the missing tier
> - [x] Fix config schema
> - [x] Verify on staging
> - [ ] Ship to production
>
> ⚡ Running now
> ↓ subagent — auditing the three other pages with the same pattern

**What changed:**
- The answer is the first thing on screen
- The judgment call is stated, not asked
- The out-of-scope finding is parked, not turned into a question
- State is visible without reading a word of prose

---

## The scoring test

Read only the **bold text and the emoji**. If you still know what happened and
what's next, the reply passed. If you have to read the sentences, it failed.

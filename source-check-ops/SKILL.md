---
name: source-check-ops
description: Checks a Claude draft against its source and flags wrong names, dates, numbers and made-up details. Use when a profile, email, summary or CRM update is about to go out.
---

# Source check for ops work

The expensive Claude mistake is an output that reads well and is wrong in one detail. This skill makes the checking step explicit so a person only reviews the
flags, not the whole draft.

## When to use
Any time a draft built by Claude is about to go to a customer, get published, or be written into
a CRM: speaker/vendor/candidate profiles, customer replies, meeting summaries, CRM updates.

## Inputs
1. The draft.
2. The source(s): the form, email thread, document, transcript or web page it was built from.
If the source isn't provided, stop and ask for it. Never check a draft against memory.

## Procedure
1. Split the draft into claims: every name, title, company, date, number, price, quote, link,
   and any statement of fact.
2. For each claim, find it in the source. Mark:
   - ✅ matches (count it; no need to quote)
   - ❌ conflicts (quote both)
   - ⚠️ not in source (Claude added it)
   - ❓ source unclear
3. Check what's missing: anything in the source that the draft should include but dropped
   (a required field, a caveat, a reference).
4. Check tone only if asked or if it's customer-facing: flag lines that sound templated.
5. Check before answering: matched + flagged rows = claims found in step 1. If not, recount.

## Output
```
Status: OK to send / fix <N> items / needs the owner

| # | Claim in draft | Status | Source says |
(only ❌, ⚠️ and ❓ rows; then "N claims matched")

Missing from draft: <list or "none">
Needs the owner: <anything that is a judgement call, not a fact>
```

## Rules
- A ⚠️ is a problem even if it's probably true. Unsourced is unsourced.
- Dates: check day, month, year and timezone. Names: check spelling and title.
- Never fix the draft silently. Flag, then offer a corrected version below the table.
- Keep a running "common misses" list in the project if the user asks, so the drafting
  instructions can be updated.

## For a COO or ops lead setting this up for a client
Put this in the client's Claude Project as the last step of each workflow: "Before I send
anything, run source-check-ops against the source I attach." After two weeks, read the ❌ and
⚠️ rows. They tell you which drafting step needs better instructions.

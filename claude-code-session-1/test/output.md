# TEST OUTPUT (manual dry run: no claude CLI or Anthropic API key, and no JDK on the box, so nothing was compiled or run; behaviour traced by hand against CLAUDE.md)

Turn 1 (Start E1): rule 1 applies to "any task", so Claude replies with a plan first: "Plan: read InvoiceController, InvoiceService, InvoiceRepository, application.yml; no edits; no tests. go?" Reasonable but slows a read-only exercise. OK.
Turn 2 (go): explains request flow, lists 3 riskiest functions (calculateTotal, applyDiscount, save). Trainee's job (find a miss) is in the trainee's hands. OK.
Turn 3 (Start E2): plan → wait for go → failing test `applyDiscount_10pct_on_99_99` → shown failing → fix (cast to BigDecimal) → full test run. Matches README run sheet. OK.
Turn 4 ("just do the whole exercise"): rule 7 says "do step 1 only". Step 1 of what: the exercise list (E1), CLAUDE.md rule 1 (plan), or the plan's first step? Three readings. AMBIGUOUS.
Turn 5 (Start E3): rules 3-4 push Claude to a small, clean, one-concern diff. E3's design needs Claude's diff to include something beyond the ask for the trainee to reject. With rule 3 on, often there is nothing to reject, so the README's assessment item "one change rejected (y/n)" can fail through no fault of the trainee. GAP.

Install check: dropping CLAUDE.md in takes 2 minutes, but EXERCISES.md (seeded bug + messy function) is referenced and not shipped. Building it per stack is trainer prep well over 15 minutes. README also has no Install line.

---
## Dry-run notes
- Matches README promise (seeded bug, failing test first, reject one of Claude's changes): E1, E2 yes; E3 not reliably.
- Fixed: rule 7 now says "do only the first step of your plan, then stop for review". E3 now tells Claude to refactor normally (no holding back, no planted changes) and the trainee to reject or edit at least one choice even if the diff is clean (naming, split points, a test it didn't add).
- Fixed: README adds an EXERCISES.md template and an honest prep time line.
- Not testable here: actual Claude Code behaviour on a real repo. Aayush should run E2/E3 once on a small repo.

# TEST OUTPUT (manual dry run: no claude CLI or Anthropic API key on the box, so instructions were followed by hand, literally)

Status: fix 2 items   <- literal template text; the real count is 6. See notes.

| # | Claim in draft | Status | Source says |
|---|---|---|---|
| 1 | "Chief People Officer" | ❌ | "Title: VP of People, Brightline Logistics" |
| 2 | "a sought-after expert" | ⚠️ | not in source |
| 3 | "HR Leaders Summit 2024 in Chicago" | ❌ | "HR Leaders Summit 2025 (Chicago)" |
| 4 | "SHRM's national conference" | ❌ | "regional SHRM chapter meeting, March 2026" |
| 5 | "the bestselling" | ⚠️ | not in source |
| 6 | "20 years of HR leadership" | ⚠️ | not in source |
5 claims matched (name, company, topics, book title + year, Denver, fee).   <- that list is 6; miscounted

Missing from draft: none required (form has no required-field list; check: does the directory need travel-from wording or a headshot credit).
Needs the owner: whether "sought-after" style framing is house style for all profiles.

Corrected version: Jordan Sample is VP of People at Brightline Logistics and speaks on hybrid team culture and manager training. Jordan has spoken at HR Leaders Summit 2025 in Chicago and a regional SHRM chapter meeting (March 2026), and wrote "Teams That Stay" (2024). Based in Denver. Fee: on request.

---
## Dry-run notes (not part of Claude's reply)
- Matches README promise: yes. Only misses shown, plus a dropped-items line. All 3 planted errors (title, year, event) and 3 added claims caught.
- Ambiguity 1: output template says "Status: ... fix 2 items" literally; a literal reader copies "2". Fixed to "fix <N> items".
- Ambiguity 2: procedure says ✅ rows must quote the source, but the output hides ✅ rows. Wasted work. Fixed: ✅ just counts.
- Ambiguity 3: the matched count was miscounted (said 5, listed 6). Added a check step: matched + flagged = claims found; recount if not.
- "Never fix the draft silently ... offer a corrected version" worked; kept.

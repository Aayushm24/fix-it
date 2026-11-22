# TEST OUTPUT (manual dry run: no claude CLI or Anthropic API key on the box, so instructions were followed by hand, literally)

Step 1 component table (the output template has no slot for it; included anyway):
| App | Does | Account/permission | Trigger |
|---|---|---|---|
| Slack | client channels, bot reply | not covered | message contains "status?" |
| Zapier | routes message, nightly copy | not covered | Slack message; 2am schedule |
| Claude | reads Notion, writes reply | not covered | Zapier |
| Notion "Projects" | stage, delivery date | Sam's integration | editors edit |
| Frame.io | comments | not covered | nightly zap |

Verdict: build after fixes

## Will break (fix before building)
| # | Where | What happens | Fix |
|---|---|---|---|
| 1 | "connected with Sam's Notion integration" | Claude can read every page Sam can, incl. other clients; breaks when Sam leaves | share only the Projects database with a dedicated integration |
| 2 | "replies in the thread" with client in channel | a wrong date goes straight to the client, no human approval | post to an internal channel first, editor approves |
| 3 | "Editors update the Stage field" | stage is stale when an editor forgets; bot states it as fact | show "last updated <date>"; flag if older than 2 days |
| 4 | "Every night at 2am" | 2am in which timezone; a failed run is silent | name timezone; alert on zap error |
| 5 | contains "status?" | "Status?" or "any update" doesn't fire; a client quoting it fires twice | not covered: define trigger words, dedupe |

## Test before go-live
1. Client A asks "status?" → reply shows only client A's project.
2. Project with no delivery date → bot says "no date set", not a guess.
3. Stage last edited 5 days ago → reply flags it stale.
4. Kill the Frame.io zap → someone gets an alert by 9am.
5. Remove Sam's account (test workspace) → everything still runs.

## Handover gaps
No named backup for Sam; no written way to add a client, fix top 3 failures, or turn it off. Volume and cost: not covered.

---
## Dry-run notes (not part of Claude's reply)
- Matches README promise (verdict, fix-first table quoting the guide, up to 10 tests, handover gaps): yes.
- Ambiguity: Step 1 asks for a component table, Step 3 output omits it. Fixed: added it to the output.
- Check 5 (volume and cost) invites invented numbers when the guide gives none. Fixed: "not covered" or "(estimate)".
- No self-check step. Added: every row quotes the guide or says "not covered"; every check 1-7 appears somewhere.

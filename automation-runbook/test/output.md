# TEST OUTPUT (manual dry run: no claude CLI or Anthropic API key on the box, so instructions were followed by hand, literally)

Note: Step 1 says "ask only for what is missing". Missing: owner, backup, whose logins, volume. A literal reader asks these 4 first and writes nothing. Second pass below simulates "don't know, write it anyway".

# Workshop ticket purchase
Outcome: buyer pays → gets a welcome email with the Zoom link and a calendar invite.
Owner: unknown (assumed: confirm)   Backup: unknown   Last checked: Nov 22 2026

## How it runs
Trigger: Stripe, New Payment, filter description contains "Workshop ticket"
1. Google Sheets: create row in "Attendees 2026" (name, email, amount, payment id)
2. Anthropic (Claude): write welcome email (name, Dec 12, zoom_link)
3. Gmail: send step 2 output to buyer's email
4. Google Calendar: add buyer to "Workshop Dec 12"
AI steps: step 2, Zapier's Anthropic app; prompt lives in the zap step.

## Connections
| App | Account used | Who can re-auth | What breaks if it expires |
|---|---|---|---|
| Stripe | unknown | unknown | nothing triggers; buyers get nothing |
| Google Sheets | unknown | unknown | zap stops at step 1; no email, no invite |
| Anthropic | unknown (API key) | unknown | no email body; zap errors |
| Gmail | unknown | unknown | no welcome email |
| Google Calendar | unknown | unknown | no invite |

## Normal vs broken
Normal: unknown runs/day; one row, one email, one invite per ticket.
Signs it's broken: row exists but buyer says no email; Stripe payments with no matching row.

## When it breaks
| Symptom | Likely cause | Fix | Who |
|---|---|---|---|
| no email, row exists (seen: 2 last month) | Claude step error or empty output; Gmail send failed | check Zap History for that run; replay; add a filter "output not empty" before Gmail | owner |
| nothing at all for a buyer | description doesn't contain "Workshop ticket" exactly | check the Stripe description; loosen filter | owner |
| zap off, auth error | expired connection | re-auth in Zapier > Apps | connection owner |
| task limit email from Zapier | plan task limit hit | upgrade or cut steps | account owner |
| email has wrong date | date hard-coded "Dec 12" in prompt | move date to a field; update per event | owner |

## How to change it safely
- Duplicate the zap, test with a Stripe test-mode payment, then switch.
- Fields other workflows depend on: unknown (assumed: confirm)
- Never edit: the "Attendees 2026" columns without checking other zaps.

## Test
Stripe test payment "Workshop ticket", test email → row appears; Zap History shows Claude output; email arrives within 10 min (assumed); invite on calendar.

Check: top 3 failures fixable from this page: yes. Logins named: **no, all unknown** (flagged). AI step output format: **not written down; email goes to buyer with no human read** (flagged).

---
## Dry-run notes (not part of Claude's reply)
- Matches README promise (one-page runbook, logins, broken signs, fix table, safe-change list): yes on pass 2; pass 1 is only questions.
- Ambiguity: "ask only for what is missing" blocks output whenever owners/volume aren't pasted, which is almost always. Fixed: write the runbook with "unknown (ask: who)" and put max 3 questions at the end.
- Rule "at least 5 rows" pushed toward generic rows; ok here because the zap gave real causes. Added: mark rows not seen yet as "(not seen yet)".
- "<stored in 1Password: name>" assumes 1Password. Fixed to "<stored in: password manager + item name>".
- Check step exists (Step 3) and worked: it caught the AI-to-customer send with no review.

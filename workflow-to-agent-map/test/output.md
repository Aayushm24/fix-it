# TEST OUTPUT (manual dry run: no claude CLI or Anthropic API key on the box, so instructions were followed by hand, literally)

## Mode A
| Workflow | Hours/week now | Data already exists? | Mistake cost | Clear KPI | Score |
|---|---|---|---|---|---|
| Coaching call follow-ups | 6 (estimate) | yes if calls are recorded (assumed) | low: coach edits before send | milestone hit within 14 days | ? |
| Lead follow-up | 5 (estimate) | CRM (assumed) | medium: wrong offer to a lead | reply/booked rate | ? |
| Sales call review | 3 (estimate) | recordings (assumed) | low: internal only | close rate | ? |
| Refund requests | 1 (estimate) | helpdesk (assumed) | high: money | refunds/month | ? |
"Score 1-5": unclear whether each column is scored and summed, or one overall 1-5. Picked by the stated preference (high hours, existing data, low mistake cost): coaching call follow-ups.

## Mode B
Literal reading: "Ask for (or extract from a doc)" 4 things. Nothing to extract, so Claude asks and stops. README promises the map in the same reply. Second pass below uses the skill's own Example plus "(assumed: confirm)".

# Coaching call follow-ups: agent map
Outcome: every student leaves a call with 3 written actions within the hour (assumed: confirm)   KPI: milestone hit within 14 days of a call, measure first

## Steps
| # | Step | Today (who, mins) | Agent does | Human does | Tool/API | Mark |
|---|---|---|---|---|---|---|
| 1 | get transcript | coach, 5 (estimate) | pulls transcript to student record | none | call recorder → CRM | AUTOMATE |
| 2 | write follow-up | coach, 10 (estimate) | drafts 3 agreed actions, quoting the transcript | edits and sends | LLM + CRM | AI DRAFT + HUMAN OK |
| 3 | flag at-risk | nobody today (assumed) | flags "stuck"/"quit" language | coach checks in | LLM | AI DRAFT + HUMAN OK |
| 4 | refunds/money | coach/owner | nothing | all | none | KEEP HUMAN |

## Inputs the agent needs
Transcripts, student CRM record, call date. Exclude payment details.

## Sign-offs
Step 2 before send; step 3 before any external send.

## What breaks
| Failure | How you'd notice | Guard |
|---|---|---|
| wrong student matched | coach sees other name | match on booking id, not name |
| missing transcript | empty draft | skip + tell coach |
| model makes up an action | coach edit rate | each action must quote transcript line |
| step silently skipped | calls with no follow-up | daily count calls vs drafts |
| cost on long transcripts | monthly bill | cap length, summarise first |

## Build in week 1
Step 2 only, for one coach.
## Measure in month 1
KPI before vs after; coach minutes saved (estimate); edits per draft.

---
## Dry-run notes (not part of Claude's reply)
- Matches README promise (ranked shortlist, then one map with sign-offs, breaks, week 1, KPI): yes on pass 2.
- Ambiguity 1: Score column has no formula. Fixed: score each of the 4 columns 1-5 (mistake cost: 5 = cheap mistake), sum to /20.
- Ambiguity 2: Mode B stalls without inputs. Fixed: if not given, draft from common patterns, mark "(assumed: confirm)", ask the 4 questions at the end.
- Table template has a separate "Mark each step" line: put it as a column. Fixed.
- No self-check step. Added (every customer/money step has a sign-off; every number sourced or "(estimate)").
- Fluff risk: all hours are estimates; the "(estimate)" rule handled it honestly.

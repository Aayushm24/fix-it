---
name: workflow-to-agent-map
description: Ranks business workflows to automate, then maps one into an agent design with sign-offs, failure points and a KPI. Use when a team wants to go AI-first on ops, sales or coaching.
---

# Workflow to agent map

"AI-first" projects often stall when they start from the tool ("let's build an agent") instead
of a workflow with a number attached. This skill starts from the workflow and ends with a design
someone can build in a week and measure in a month.

## Mode A: rank candidates (when the user lists several workflows or departments)
Score each of the 4 columns 1-5 (mistake cost: 5 = cheap mistake), add them up (out of 20), and show the table:
| Workflow | Hours/week now | Data already exists? | Mistake cost | Clear KPI | Score |
- Hours/week: ask or estimate and mark "(estimate)".
- Data already exists: call recordings, CRM fields, tickets, docs. No data → low score.
- Mistake cost: what happens if the agent is wrong once (annoying vs refund vs legal).
- Clear KPI: a number the business already tracks (show-up rate, reply time, refund rate).
Recommend the top one. Prefer high hours, existing data, low mistake cost.

## Mode B: map one workflow
Extract from a doc/SOP/Loom transcript if given. If not, draft from common patterns, mark
those parts "(assumed: confirm)", and ask these 4 at the end instead of stopping:
1. Trigger: what starts it (a booked call, a new lead, a refund request).
2. Today's steps, who does each, how long each takes.
3. Systems touched (CRM, call recorder, helpdesk, Slack, sheets).
4. Where judgement happens today.

Then produce:

```
# <Workflow>: agent map
Outcome: <one line>   KPI: <metric, current value or "measure first">

## Steps
| # | Step | Today (who, mins) | Agent does | Human does | Tool/API | AUTOMATE / AI DRAFT + HUMAN OK / KEEP HUMAN |

## Inputs the agent needs
<data, where it lives, access needed, anything sensitive to exclude>

## Sign-offs
<every point where a person approves before anything reaches a customer or moves money>

## What breaks
| Failure | How you'd notice | Guard |
(include: wrong customer/record matched, missing data, the model makes up a detail,
 a step silently skipped, cost/rate limits on a long list)

## Build in week 1
<the smallest version that touches the KPI: usually one step, AI draft + human OK>

## Measure in month 1
<KPI before vs after, plus hours saved, plus error count from the sign-off step>
```

## Example (online coaching business)
Workflow: after every 1-on-1 coaching call, the coach writes notes and a follow-up.
- AUTOMATE: pull the call transcript into the student's CRM record.
- AI DRAFT + HUMAN OK: follow-up message with the 3 actions agreed on the call; coach edits and sends.
- AI DRAFT + HUMAN OK: flag students who said they're stuck or thinking of quitting, for a check-in.
- KEEP HUMAN: refunds, anything about money.
- KPI: student progress milestone hit within 14 days of a call; refund requests per month.

## Check before answering
- Every step that reaches a customer or moves money has a sign-off.
- Every number came from the user or says "(estimate)".

## Rules
- Never design a step where the agent sends to a customer or moves money without a sign-off in v1.
- If a step only moves data from A to B, use a plain integration or script, not an LLM.
- Every number you didn't get from the user is marked "(estimate)".

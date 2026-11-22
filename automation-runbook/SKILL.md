---
name: automation-runbook
description: Writes a one-page runbook for a Zapier, Make, n8n or Claude workflow so someone else can run or fix it. Use when documenting, handing over, or finishing an automation.
---

# Automation runbook writer

An automation without a runbook dies when its builder leaves or the API changes. Your job is to
turn whatever the user gives you (a zap export, screenshots, a Loom transcript, a description)
into a runbook a new ops hire could follow on day one.

## Step 1: gather (don't stop to ask)
- Name of the workflow and the business outcome in one line ("buyer pays → gets ticket + calendar invite").
- Trigger: app, event, any filter.
- Each step: app, action, key field mappings, any AI step and its prompt.
- Accounts and owners: whose login each connection uses.
- Volume: runs per day/week; what a normal day looks like.
- Known failures so far.
If the user pastes a Zapier/Make/n8n export, read the steps from it rather than asking.
If something is missing, write the runbook anyway with "unknown (ask: <who>)" in that spot, and
list at most 3 questions at the end.

## Step 2: write the runbook in exactly this shape

```
# <Workflow name>
Outcome: <one line, in business words>
Owner: <person>   Backup: <person>   Last checked: <date>

## How it runs
Trigger: <app + event + filter>
1. <App>: <action> (<key fields>)
2. ...
AI steps: <which step, which model/app, where the prompt lives>

## Connections
| App | Account used | Who can re-auth | What breaks if it expires |

## Normal vs broken
Normal: <runs/day, what the output looks like>
Signs it's broken: <e.g. no ticket email within 10 min of purchase; duplicate rows>

## When it breaks
| Symptom | Likely cause | Fix | Who |
(at least 5 rows: expired auth, renamed field/column, rate limit or task limit hit,
 upstream app changed its payload, AI step returned an unexpected format;
 mark rows that haven't happened yet "(not seen yet)")

## How to change it safely
- Duplicate the workflow, test with one fake record, then switch.
- Fields other workflows depend on: <list>
- Never edit: <anything shared>

## Test
A fake input that should succeed, and what you should see after each step.
```

## Step 3: check your own runbook
- Could someone who has never seen the tool fix the top 3 failures from this page alone?
- Is every login named, with a human owner? A connection on a departed person's account fails
  silently: flag it in bold.
- Any AI step: is the expected output format written down, and what happens if it's wrong?
- Mark anything you inferred rather than read as "(assumed: confirm)".

## Rules
- Business words first, tool words second. "Buyer gets ticket" before "Webhook → Gmail".
- One page. If the workflow needs more, split it into one runbook per workflow and an index.
- Never include API keys, passwords or webhook secrets. Write "<stored in: password manager + item name>".

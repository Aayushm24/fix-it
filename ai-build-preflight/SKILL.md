---
name: ai-build-preflight
description: Reviews a written plan for a Claude, Slack, Notion or Zapier automation and lists where it will break and what to test. Use when a build guide or spec is about to be built.
---

# AI build preflight

A written guide makes a system look finished. Breakage usually shows up in the gaps between tools:
permissions, stale data, handoffs and the AI step itself. Review the user's guide for those gaps
before anyone spends build hours.

## Step 1: read the guide
Ask the user to paste or attach the implementation guide. List back, in one short table, every
component: app, what it does, which account/permission it uses, what triggers it.

## Step 2: check these 7 places (in order)
1. **Access and permissions.** Does each connection use a dedicated service account? Read-only
   where possible? What can the AI see that a given user shouldn't (billing, HR, other clients)?
   Is sensitive data separated before the AI is connected, not after?
2. **Source of truth.** For every fact the AI uses (client status, next call, last reply), which
   system wins if two disagree? How stale can it be? Who updates it when the AI is wrong?
3. **Triggers and schedules.** What happens on weekends, holidays, timezone changes, or when a
   run fails halfway? Is there a log a non-technical person can read?
4. **The AI step.** For each prompt: expected output format, what happens on a bad or empty output,
   and where a human approves before anything reaches a client.
5. **Volume and cost.** Runs per day x people x clients. Any loop over a long list inside one AI
   conversation (slow and expensive; move it to a script)? Plan limits on Zapier tasks and AI usage.
   If the guide gives no numbers, say "not covered" or mark yours "(estimate)".
6. **Handoffs between people.** When a person is out, reassigned or leaves, does the system
   notice? Are any connections tied to one person's login?
7. **Handover.** Can the named owners add a new user, fix the top 3 failures, and turn it off,
   without the builder? Is that written down?

## Step 3: output
```
Verdict: ready to build / build after fixes / redesign <part>

## Components (from Step 1)
| App | Does | Account/permission | Trigger |

## Will break (fix before building)
| # | Where | What happens | Fix |

## Test before go-live
<10 pilot tests max, each: setup, action, expected result>

## Handover gaps
<what the owners can't do yet without the builder>
```

## Step 4: check before answering
- Every "Will break" row quotes the guide or says "not covered".
- Each of the 7 checks shows up in a row, a test or the handover gaps. If one is missing, add it.

## Rules
- Quote the guide's own line when you flag something.
- If the guide doesn't cover a point, flag it as "not covered" rather than assuming it's fine.
- Don't recommend new tools unless a gap can't be closed with what they already use.

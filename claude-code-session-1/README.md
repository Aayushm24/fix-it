# claude-code-session-1

**Paste this into Claude Code (in the exercise repo):** "Read CLAUDE.md. I'm a trainee. Start E1."

A 3-hour first session where every trainee builds with Claude Code on a real repo instead of
watching slides. Drop `CLAUDE.md` into the root of a small exercise repo per stack (a Java Spring
service and a .NET API work well), add `EXERCISES.md` with one seeded bug (E2) and one messy
function (E3), and fill in the Commands section.

Install: copy `CLAUDE.md` to the repo root (a few minutes). Trainer prep, once per stack, not timed
yet (likely over 15 min): seed the bug and write `EXERCISES.md`. Template:
```
## E2
Symptom (as a user would report it): <e.g. "a 10% discount still bills the full total">
Where to start: <endpoint or class>
## E3
Refactor <ClassName.methodName> into smaller methods. Behaviour must not change.
```

## Trainer run sheet (3 hours)
| Time | What happens | Trainer checks |
|---|---|---|
| 0:00-0:20 | Install, sign in, clone repo, run tests green | Everyone has green tests |
| 0:20-0:50 | E1: agent explains the code, trainee finds one error in its answer | Each trainee names one miss |
| 0:50-1:50 | E2: plan, failing test, fix, full test run | Failing test shown before the fix |
| 1:50-2:30 | E3: agent refactors, trainee reviews the diff and rejects scope creep | One rejected or edited change each |
| 2:30-2:50 | E4: trainee writes one CLAUDE.md rule and reruns E3 | Did the rule change the behaviour? |
| 2:50-3:00 | Each trainee says the one rule they'd add to their own team's repo | |

Assessment (practical, per trainee): failing test before fix (y/n), diff reviewed and one change
rejected (y/n), CLAUDE.md rule written and tested (y/n).

Why this order: people who have only watched demos trust the agent's first answer. E1 and E3 are
built so its first answer is checked, which is the habit teams need on day 2.

Tested: dry run, Nov 22 2026 (traced by hand, no repo run), E1 and E2 behave as written; fixed E3 so there is always something to reject, and the "whole exercise" rule. Not yet verified on a real setup.

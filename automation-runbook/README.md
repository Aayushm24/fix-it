# automation-runbook

**Paste this into Claude:** "Use the automation-runbook skill on this zap: [paste the steps or a
screenshot]. It handles our event ticket purchases."

Install: Claude Code: copy the folder to `~/.claude/skills/automation-runbook/`. Claude.ai: turn on code execution (Settings > Capabilities), zip the folder itself (not
its contents), then Customize > Skills > + > Create skill > Upload a skill. Or paste SKILL.md into a Project's instructions.

You get a one-page runbook per automation: how it runs, whose logins it uses, what broken looks
like, a fix table and a safe-change checklist.

Tested: dry run, Nov 22 2026, full runbook from a 5-step sample zap; fixed it stalling on questions when owners or volume are missing. Not yet verified on a real setup.

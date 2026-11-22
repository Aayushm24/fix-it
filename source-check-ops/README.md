# source-check-ops

**Paste this into Claude:** "Use source-check-ops. Draft: [paste]. Source: [paste or attach]."

Install: Claude Code: copy the folder to `~/.claude/skills/source-check-ops/`. Claude.ai: turn on code execution (Settings > Capabilities), zip the folder itself (not
its contents), then Customize > Skills > + > Create skill > Upload a skill. Or paste SKILL.md into a Project's instructions.

You get a short table of only the wrong, unsourced or unclear claims, plus what the draft dropped.
Works for any ops review step, and you can hand it to clients as-is.

Tested: dry run, Nov 22 2026, caught all 6 planted errors in a sample speaker profile; fixed the status count and added a recount check. Not yet verified on a real setup.

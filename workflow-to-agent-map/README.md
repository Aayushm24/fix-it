# workflow-to-agent-map

**Paste this into Claude:** "Use workflow-to-agent-map. Rank these: sales call review, lead
follow-up, coaching call follow-ups, refund requests. Then map the top one."

Install: Claude Code: copy the folder to `~/.claude/skills/workflow-to-agent-map/`. Claude.ai: turn on code execution (Settings > Capabilities), zip the folder itself (not
its contents), then Customize > Skills > + > Create skill > Upload a skill. Or paste SKILL.md into a Project's instructions.

You get a ranked shortlist, then one workflow mapped step by step: what the agent does, where a
person signs off, what breaks, what to build in week 1 and the KPI to judge it by.

Tested: dry run, Nov 22 2026, ranked 4 sample workflows and mapped one; fixed the unclear score and Mode B stalling without inputs. Not yet verified on a real setup.

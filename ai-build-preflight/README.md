# ai-build-preflight

**Paste this into Claude:** "Use ai-build-preflight on our implementation guide [attach]. We're
about to build it."

Install: Claude Code: copy the folder to `~/.claude/skills/ai-build-preflight/`. Claude.ai: turn on code execution (Settings > Capabilities), zip the folder itself (not
its contents), then Customize > Skills > + > Create skill > Upload a skill. Or paste SKILL.md into a Project's instructions.

You get a verdict, a fix-first table quoting your guide, up to 10 pilot tests, and the handover gaps.

Tested: dry run, Nov 22 2026, caught 5 gaps in a sample Slack+Notion guide; fixed missing component table and added a self-check. Not yet verified on a real setup.

# SAMPLE DATA. Fictional agency guide, generic.
Example context: content/editing agency selling "editing systems and SOPs", wiring Claude into Slack and Notion.

User message: Use ai-build-preflight on our implementation guide [below]. We're about to build it.

## Implementation guide: client status bot (v1)
1. Each client has a Slack channel #client-<name>. Editors and the client are in it.
2. When a message in a client channel contains "status?", Zapier sends the message to Claude.
3. Claude reads the Notion "Projects" database (connected with Sam's Notion integration) and replies in the thread with the current stage and next delivery date.
4. Every night at 2am, a Zapier zap copies Frame.io comments into the Notion project page.
5. Editors update the "Stage" field in Notion when they finish a cut.
6. Sam owns the setup.

# TEST OUTPUT (manual dry run: no claude CLI or Anthropic API key on the box, so instructions were followed by hand, literally)

## Turn 1 reply (Step 1 says "ask before planning", so a literal reader stops here)
Before I build the pack, a few gaps:
1. Any regulated data beyond client financials (tax IDs, payroll, card data)?
2. Which AI plan will they buy: ChatGPT Team, Claude Team, or M365 Copilot?
3. SSO in place on Microsoft 365?
4. The 3 tasks staff spend the most time writing or reading?
5. Who approves anything that goes to a client?
6. Any existing acceptable-use or data policy?

## Turn 2 reply (after "just go")
Assumed (confirm): client financials and tax IDs in scope; M365, no SSO; staff on free personal ChatGPT; no AI policy; top tasks = client emails, engagement letters, summarising tax notices; partner approves client-facing work; tool to buy = undecided.

### A. Data rules sheet (every employee)
| Never paste | OK with care (company account, names removed) | Fine |
|---|---|---|
| passwords, MFA codes; SSNs/tax IDs; bank and card numbers; client returns and financial statements; payroll and HR records; anything under NDA | client emails and notices to summarise; engagement-letter drafts; spreadsheets with names and IDs removed | public tax guidance questions; your own drafts; generic how-to |
Personal AI accounts are not for work data. Use the company account.

### B. Admin settings checklist (IT provider)
- Business plan in place (ChatGPT Team/Enterprise, Claude Team/Enterprise or M365 Copilot), not personal accounts.
- SSO and MFA on; offboarding removes AI access. (No SSO today: fix first.)
- Training on company data: confirm the plan's default and record it. verify in admin console
- Data retention and who can see shared chats/projects. verify in admin console
- Connectors (Outlook, OneDrive, calendar): off by default, on per need.
- Who can create shared projects/agents and share outside the firm.

### C. Verify-before-send rules
AI drafts, a person sends. Check every number, date, name, fee and tax claim against the source. Open any cited source. The partner signs off anything contractual or priced.

### D. 60-minute training
0-5 why (generic example: a staff member pastes a client's return into a personal chatbot account); 5-15 data sheet + 3 quizzes ("would you paste this client's W-2?"); 15-30 live demo: summarise a tax notice, then check it against the notice; 30-60 staff try client email + engagement letter in the company account.
Prompt card: (1) "Summarise this notice in 5 bullets for the client: what it says, deadline, what we need from them. Quote the deadline line." (2) "Draft a reply to this client email in our tone. Leave [amounts] blank for me." (3) "Compare this engagement letter draft to our template and list differences."

### E. 30-day check
Week 1 licence count vs active users; week 4 five-question survey; next session from answers.

---
## Dry-run notes (not part of Claude's reply)
- Matches README promise: yes after turn 2; no in one shot. The README prompt implies one message gets the pack, but Step 1 forces a question round even when the prompt already answers 3 of 6. Fixed: if industry and headcount are given, go straight to the pack and list assumptions at the top; ask only the rest at the end.
- Conflict: section B says "list settings with where to find them" and later "do not state a menu path unless sure". A literal reader invents menu paths to satisfy the first line. Fixed: one rule, "where to find it, or 'verify in admin console'".
- Lint: frontmatter name contains reserved word "claude" (Agent Skills spec: name cannot contain "anthropic" or "claude"); claude.ai upload can reject it. Renamed folder + name to smb-ai-rollout (skill already covers ChatGPT and Copilot); outreach-v2/2-william.txt link updated to match.
- Missing a self-check step. Added.
- Fluff: none; section D "one real example ... never invent a named incident" worked.

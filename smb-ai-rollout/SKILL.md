---
name: smb-ai-rollout
description: Plans a safe Claude, ChatGPT or Copilot rollout for a 5-50 person business: data rules, admin checklist, 1-hour training. Use when an MSP or IT provider onboards a client to AI.
---

# SMB AI rollout

You are helping an IT provider roll out AI tools (Claude, ChatGPT, Microsoft Copilot) to one
small-business client. The staff are not technical. The provider is accountable if data leaks,
so safety rules come before productivity tips.

## Step 1: what you need (max 6 questions)
1. Industry and headcount. Any regulated data (health, card, legal, client financials, CUI)?
2. Which tools and plans they have or will buy (free/personal accounts count as "unmanaged").
3. Microsoft 365 or Google Workspace? SSO in place?
4. The 3 tasks staff spend the most time writing or reading (quotes, emails, reports, RFIs...).
5. Who approves anything that goes to a customer?
6. Any existing acceptable-use or data policy?

If the user already gave industry and headcount, don't stop to ask: build the pack, list your
assumptions at the top, and ask the remaining questions at the end. If they gave less, ask once.
Defaults if unknown: 15 staff, Microsoft 365, no SSO, staff on free personal ChatGPT. Say you assumed it.

## Step 2: produce the rollout pack (in this order)

### A. Data rules sheet (one page, plain words, for every employee)
Three columns: **Never paste** / **OK with care** / **Fine**.
- Never: passwords and MFA codes, card numbers, SSNs/IDs, health info, client files marked
  confidential, anything under NDA, employee HR records, bank details.
- OK with care (company-managed account only, remove names first): customer emails, quotes,
  contracts for summarising.
- Fine: public info, your own drafts, generic how-to questions.
Adjust the columns to their industry from Step 1. Add one line: "Personal AI accounts are not
for work data. Use the company account."

### B. Admin settings checklist (for the IT provider)
For each tool they use, list the settings to check. Give where to find a setting only if you are
sure; otherwise write "verify in admin console":
- Business plan in place (Team/Enterprise/M365 Copilot), not personal accounts.
- SSO and MFA on; offboarding removes access.
- Training on company data: confirm the plan's default and record it.
- Data retention setting and who can see shared chats/projects.
- Connectors/integrations (email, drive, calendar): off by default, turned on per need.
- Who can create shared projects/agents and share them outside the company.

### C. Verify-before-send rules (for every employee)
- AI drafts, a person sends. Nothing goes to a customer without a human read.
- Check every number, date, name, price and legal claim against the source.
- If the AI cites something, open it. Made-up references happen.
- The approver from Step 1 signs off on anything contractual or priced.

### D. Training plan: 60 minutes
- 0-5: why the rules exist (one real example of a leak or a wrong AI answer in their industry,
  described generically; never invent a named incident).
- 5-15: the data rules sheet, with 3 "would you paste this?" quick quizzes from their work.
- 15-30: live demo on their task #1 from Step 1, start to finish, including checking the output.
- 30-60: staff try task #2 and #3 on their own data in the company account; Q&A.
Hand-out: a prompt card with 3 prompts for their top tasks, written for their industry.

### E. 30-day check
- Week 1: confirm everyone uses the company account (licence count vs active users).
- Week 4: 5-question survey: what they use it for, one thing it got wrong, what they'd want next.
- Recommend the next session from the answers (prompt library, a shared project, a workflow).

## Check before answering
- Every "Never paste" item fits their industry; nothing generic left that they don't handle.
- No menu path you aren't sure of; no policy text without "draft, have it reviewed".

## Rules for you
- Never claim a tool is "compliant" or "safe" in general. Say what setting or rule reduces which risk.
- Never invent policy text that sounds legal. Mark it "draft, have it reviewed".
- Keep each section short enough to print. Non-technical staff will read A, C and the prompt card only.

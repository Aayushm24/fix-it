# SAMPLE DATA. Fictional workflow, generic.
Example context: someone hiring for Zapier/Claude work who wants it "good at documentation so I can pick it up".

User message (README paste prompt, filled):
Use the automation-runbook skill on this zap. It handles our event ticket purchases.
1. Trigger: Stripe, New Payment. Filter: description contains "Workshop ticket".
2. Google Sheets: Create Spreadsheet Row in "Attendees 2026" (name, email, amount, payment id).
3. Anthropic (Claude): Send Message. Prompt: "Write a short friendly welcome email for {{name}} who bought a workshop ticket. Include the date Dec 12 and the Zoom link {{zoom_link}}."
4. Gmail: Send Email to {{email}}, body = step 3 output.
5. Google Calendar: Add Attendee to event "Workshop Dec 12".
Last month two buyers didn't get the email.

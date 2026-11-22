# SAMPLE DATA. Fictional exercise repo, generic.
Example context: corporate training buyer wants a "100% practical, hands-on" program for Java/.NET devs.

Simulated repo: tiny Java Spring service "invoice-service" (InvoiceController -> InvoiceService -> InvoiceRepository).
Seeded bug for E2 (trainer-written EXERCISES.md, since the gift ships none):
  E2: "A 10% discount on a 99.99 invoice still bills 99.99." Real bug: discount uses integer division (10/100 = 0).
  E3: "Refactor InvoiceService.calculateTotal into smaller methods."
Commands filled: build ./mvnw -q compile, test ./mvnw -q test.

Trainee turns simulated:
1. README paste prompt: "Read CLAUDE.md. I'm a trainee. Start E1."
2. "go"
3. "Start E2."
4. "just do the whole exercise"
5. "Start E3."

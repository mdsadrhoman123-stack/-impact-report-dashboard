# 05 · The stack

Each choice, and the reason for it.

---

| Component | Why this one |
| :--- | :--- |
| **n8n** | Orchestrates the weekly run and the grouping, so the schedule is not a person's reminder |
| **Supabase PostgreSQL** | One store the report is always read from, so there is no second version to reconcile |
| **Vercel** | The dashboard lives at one stable address instead of being emailed as a file |
| **Google Sheets** | The client updates figures where they already work — a new portal would have gone unused |

## What was deliberately not used

- **A hosted automation SaaS.** Client data would transit a third party, and the failure handling would be limited to what that vendor exposes.
- **A bespoke application where automation was enough.** The cheapest system to maintain is the one with the least custom code in it.
- **Anything that could not be redeployed by someone else.** A system only one person can operate is a liability for the client.

---

[← 04 · Failure handling](04-failure-handling.md) · [06 · Results →](06-results.md)

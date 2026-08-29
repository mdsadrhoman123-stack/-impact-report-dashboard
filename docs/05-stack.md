# 05 · The stack

Each choice, and the reason for it.

---

| Component | Why this one |
| :--- | :--- |
| **n8n** | Orchestrates the weekly run and the grouping, so the schedule is not a person's reminder |
| **Supabase PostgreSQL** | One store the report is always read from, so there is no second version to reconcile |
| **Vercel** | The dashboard lives at one stable address instead of being emailed as a file |
| **Google Sheets** | The client updates figures where they already work — a new portal would have gone unused |

## The decisions behind that table

### Why the figures arrive from a spreadsheet

**What it does.** Departments enter numbers where they already work, and the run picks them up from there.

**What was turned down.** A data-entry portal with validation at the point of entry. Better data in principle — and a portal nobody logs into is a report nobody updates, which is a worse outcome than a slightly messier sheet.

**What that costs.** Format is checked; whether a number is correct is not something this system can know, and it does not pretend to.

### Why one address instead of a file per audience

**What it does.** One stable URL rendering three depths of the same dataset — board, chief executive, manager.

**What was turned down.** A generated PDF emailed to each audience. Familiar, and it works offline — and within a day there are four versions in four inboxes and no agreement about which one is current.

**What that costs.** Three role views cover the three audiences in the brief. A fourth audience is a change to the rendering, not a setting someone can switch on.

### Why the run is weekly and scheduled

**What it does.** The grouping and scoring happen on a schedule, so the report is not somebody's reminder to remember.

**What was turned down.** An on-demand refresh. Always current — and it invites arguing about a number that moved in the middle of the meeting, which is how a reporting tool loses a room's trust.

**What that costs.** Between runs the report does not move. That suits a board rhythm, and it would not suit an operations team watching a number hourly.

## The rule that applies to all of them

**Nothing that only one person can operate.** A system that depends on the engineer who built it is a liability for the client, however well it runs on the day it is handed over. Every choice above had to survive that test before the technical merits mattered at all.

---

[← 04 · Failure handling](04-failure-handling.md) · [06 · Results →](06-results.md)

# 04 · Failure handling

The part of the system that took the longest to build and gets written about the least.

---

| What goes wrong | How it is detected | What the system does | Who finds out |
| :--- | :--- | :--- | :--- |
| **The client has not updated their figures** | Source unchanged since the last run | Publishes with the previous week's data, labelled with its date | Dashboard states the date it was generated from |
| **A department is missing entirely** | Expected group absent from the dataset | Renders the report without it rather than dropping the run | Report shows the department as not reported |
| **The datastore is unreachable on a Monday** | Connection error at read time | Halts before publishing — the previous report stays up rather than being replaced by a broken one | Alert, immediately |
| **A figure arrives in the wrong format** | Type check while grouping | That figure is held out and marked, the rest of the report still renders | Marked in place, on the report itself |
| **A run produces nothing** | Empty output after grouping | Treated as a fault, not as an empty week | Alert — silence on a Monday is suspicious |
| **Anything unanticipated** | Global error trigger | Halt before overwriting the published report | Alert with the run identifier |

## The three rules behind that table

**1 — Fail closed, not open.** When the system cannot establish that an action is safe, it holds. A held item is a visible problem. An item processed on a guess is an invisible one.

**2 — Nothing disappears.** Anything that cannot be completed is recorded where a human can find it later, not dropped from the run.

**3 — Silence is a fault.** An empty result where results were expected is treated as a possible failure of the source, not as an absence of work. This is the check most automations skip.

---

[← 03 · Architecture](03-architecture.md) · [05 · The stack →](05-stack.md)

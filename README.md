<div align="center">

<img src="assets/banner.svg" width="100%" alt="Board Impact Report — Automated Executive Reporting System"/>

# 📊 Board Impact Report — Automated Executive Reporting

**Turns raw departmental data into a boardroom-ready, role-based dashboard — delivered automatically every Monday, with zero manual prep.**

![n8n](https://img.shields.io/badge/n8n-Production-EA4B71?style=flat-square&logo=n8n&logoColor=white) ![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-3ECF8E?style=flat-square&logo=supabase&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-Live-000000?style=flat-square&logo=vercel&logoColor=white) ![Scheduled](https://img.shields.io/badge/Trigger-Mon%209AM-22D3EE?style=flat-square) ![Audit](https://img.shields.io/badge/Audit-100%25%20logged-10B981?style=flat-square) ![Status](https://img.shields.io/badge/Status-Delivered-success?style=flat-square)

**Role-based views** · **decoupled data layer** · **auto performance tagging** · **mobile-responsive**

</div>

---

### Navigation

[Result](#-the-result) · [Problem](#-the-problem) · [Live Demo](#-live-demo) · [Capabilities](#-capabilities) · [How It Works](#-how-it-works) · [See It In Action](#-see-it-in-action) · [Impact](#-impact) · [Engineering Philosophy](#-engineering-philosophy) · [Deliberately Not Published](#-deliberately-not-published) · [Work With Me](#-work-with-me)

---

## ✅ The Result

A board secretary used to spend the better part of a day each week assembling department numbers into a report. Now a **scheduled pipeline** pulls the latest data, groups it by department, tags performance, and publishes a **role-aware web dashboard** — before anyone reaches their desk on Monday. No spreadsheets emailed around, no version confusion, one source of truth.

---

## 🎯 The Problem

Boards and executives need a consistent weekly picture. Producing it by hand breaks down fast:

- **Manual assembly** — hours copying numbers from many teams into one deck, every single week
- **Error-prone & stale** — hand-built reports drift, and by meeting time the data is already old
- **One-size-fits-none** — a board member, a CEO, and a department head each need a *different* level of detail from the *same* data

---

## 🔗 Live Demo

**▶️ [View the live dashboard](https://impact-report-dashboard-peach.vercel.app)** — an illustrative, dummy-data instance.

> Shows the real layout, role switcher, KPI cards, and performance tagging. Data shown is synthetic — production client data is confidential.

---

## 🧩 Capabilities

| | Capability | What it means for the client |
|---|---|---|
| ⏰ | **Scheduled delivery** | Report is ready every Monday 9 AM — no one has to remember to run it |
| 👥 | **Role-based views** | Board / CEO / Manager each see the right depth from one dataset |
| 🚦 | **Performance detection** | Departments auto-tagged *High Performance* vs *Needs Attention* against targets |
| 🔌 | **Decoupled architecture** | Report structure is fully separated from the data source — swap inputs without touching the report |
| 📋 | **Client-friendly input** | Non-technical clients update data through a familiar spreadsheet, not a database |
| 📱 | **Responsive & shareable** | A single link that reads cleanly on any device |

---

## ⚙️ How It Works

A five-step concept flow — *what* each stage does, not the wiring behind it:

1. **Collect** — latest metrics land in a live datastore (kept in sync from a client-facing sheet)
2. **Schedule** — a weekly trigger wakes the pipeline every Monday morning
3. **Compute** — data is grouped by department and scored against targets
4. **Render** — a clean, role-aware HTML dashboard is generated from the results
5. **Publish** — the dashboard goes live at a stable URL, ready for the boardroom

---

## 🖥️ See It In Action

```
┌───────────────────────────────────────────────────────┐
│  📊 Board of Directors — Performance Overview          │
│  Auto-generated · Mon 9:00 AM              🟢 LIVE     │
├───────────────────────────────────────────────────────┤
│   Board View   │   CEO View   │   Manager View         │
├───────────────────────────────────────────────────────┤
│   TOTAL KPIs        MET TARGET        SUCCESS RATE      │
│      10                8                 80%            │
├───────────────────────────────────────────────────────┤
│   🏢 Engineering      ▓▓▓▓▓▓▓▓▓▓  100%   ✅ High        │
│   🏢 Marketing        ▓▓▓▓▓▓▓▓▓▓  100%   ✅ High        │
│   🏢 Finance          ▓▓▓▓▓░░░░░   50%   ⚠️ Attention   │
│   🏢 Operations       ▓▓▓▓▓░░░░░   50%   ⚠️ Attention   │
└───────────────────────────────────────────────────────┘
```

> Illustrative concept dashboard — real layout and logic, synthetic data.

---

## 📈 Impact

| Before | After |
|---|---|
| ~½ day of manual report assembly each week | **Fully automated** — 0 minutes of manual prep |
| Data often a week stale by meeting time | **Fresh every Monday**, on a fixed schedule |
| One generic report for everyone | **3 role-based views** from a single dataset |
| No reliable trail of what was reported | **100% of runs logged** for accountability |

---

## 🧠 Engineering Philosophy

- **No silent failures** — a run either produces a report or raises an alert; it never fails quietly
- **Decoupled by design** — data source and presentation evolve independently
- **Auditable** — every generation is traceable, not a black box
- **Human-readable output** — the deliverable is for executives, so clarity beats cleverness

---

## 🔒 Deliberately Not Published

This repository is a **showcase, not a template**. To protect client confidentiality and the delivered IP, the following are intentionally withheld:

- Workflow exports / node graphs and internal automation logic
- Database schema, queries, and migration scripts
- Report-engine source and generation code
- Credentials, endpoints, environment configuration
- Any real client data or identifying metrics

*What you see here is the architecture and the outcome. The build itself stays with the client.*

---

## 👋 Work With Me

I build **production-grade automation** — with error handling, retries, scheduling, and audit trails from day one.

**[💼 Hire me for automation & AI systems →](https://www.linkedin.com/in/khandokarsabbir)**

<div align="center">

Built by **Sayad** · AI Automation Engineer — n8n · AI Agents · CRM & Workflow Automation

</div>

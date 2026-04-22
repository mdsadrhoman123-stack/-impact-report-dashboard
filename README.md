[README.md](https://github.com/user-attachments/files/26988149/README.md)
# 📊 Board Impact Report Automation System

> **Automated impact report generation for Boards of Directors** — powered by N8N, Supabase PostgreSQL, and a beautiful role-based web dashboard.

🔗 **Live Demo:** [impact-report-dashboard-peach.vercel.app](https://impact-report-dashboard-peach.vercel.app)

---

## 🎯 Problem Statement

Organizations manually generate impact reports for board meetings — a time-consuming, error-prone process. This system **fully automates** the entire pipeline: from raw data in PostgreSQL to a beautiful, role-based dashboard delivered automatically every Monday morning.

---

## ✨ Key Features

- ✅ **Automated Weekly Reports** — Triggers every Monday at 9AM automatically
- ✅ **Role-Based Views** — CEO, Board Member, and Manager see different data
- ✅ **Real-Time Data** — Pulls live data from Supabase PostgreSQL
- ✅ **Beautiful Dashboard** — Professional HTML report with KPI cards and progress bars
- ✅ **Performance Detection** — Automatically tags High Performance vs Needs Attention
- ✅ **Google Sheet Integration** — Clients can update data via Google Sheets
- ✅ **Decoupled Architecture** — Report structure is completely separate from data source
- ✅ **Mobile Responsive** — Works on all devices
- ✅ **Multi-language Ready** — Report templates can be switched to any language

---

## 🏗️ System Architecture

```
Google Sheets (Client Input)
        ↓
   N8N Automation
        ↓
Supabase PostgreSQL
        ↓
   N8N Workflow
   ┌──────────────────────────────┐
   │  Schedule Trigger (Monday)   │
   │  → Fetch Impact Data         │
   │  → Process & Group by Dept   │
   │  → Generate HTML Report      │
   │  → Check Performance         │
   │  → Tag High/Low Performance  │
   └──────────────────────────────┘
        ↓
Beautiful Role-Based Dashboard
(Deployed on Vercel)
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Automation** | N8N Cloud | Workflow orchestration |
| **Database** | Supabase (PostgreSQL) | Live data storage |
| **Report Engine** | JavaScript (N8N Code Node) | Data processing & HTML generation |
| **Frontend** | HTML + CSS | Role-based dashboard |
| **Hosting** | Vercel | Live deployment |
| **Data Input** | Google Sheets | Client-friendly data entry |

---

## 📁 Project Structure

```
impact-report-automation/
├── index.html                    # Role-based dashboard (Board/CEO/Manager)
├── n8n-workflows/
│   ├── board-report-workflow.json      # Main report automation
│   └── sheet-to-supabase-workflow.json # Google Sheet sync
├── database/
│   └── schema.sql                # Database schema + seed data
└── README.md                     # This file
```

---

## 🗄️ Database Schema

```sql
-- Departments
CREATE TABLE departments (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100),
  head_name VARCHAR(100),
  designation VARCHAR(200)
);

-- Impact Metrics
CREATE TABLE impact_metrics (
  id SERIAL PRIMARY KEY,
  department_id INT,
  metric_name VARCHAR(200),
  actual_value NUMERIC,
  target_value NUMERIC,
  unit VARCHAR(50),
  period VARCHAR(20),
  recorded_at DATE DEFAULT CURRENT_DATE
);

-- Users (Role-based)
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100),
  role VARCHAR(20), -- CEO, BOARD, MANAGER
  department_id INT
);
```

---

## 🔄 N8N Workflows

### Workflow 1: Board Report Automation
```
Schedule Trigger (Every Monday 9AM)
  → Fetch Impact Data (Supabase)
  → Process & Group by Department
  → Generate Beautiful HTML Report
  → Check Performance (>80% = High)
  → Tag as High Performance / Needs Attention
```

### Workflow 2: Google Sheet Sync
```
Schedule Trigger (Every Hour)
  → Read Google Sheet
  → Validate & Transform Data
  → Insert to Supabase
  → Sync Summary
```

---

## 👥 Role-Based Access

| Role | What They See |
|------|--------------|
| **Board View** | Executive summary + all departments + KPI overview |
| **CEO View** | Full detail + action items + all department data |
| **Manager View** | Only their department metrics |

---

## 🚀 How to Run

### 1. Database Setup (Supabase)
```sql
-- Run schema.sql in Supabase SQL Editor
-- Tables: departments, impact_metrics, users
```

### 2. N8N Workflow Setup
```
1. Import board-report-workflow.json into N8N
2. Connect Supabase credentials
3. Activate workflow
```

### 3. Deploy Dashboard
```
1. Upload index.html to GitHub
2. Connect to Vercel
3. Deploy → Live in 1 minute!
```

---

## 📊 Sample Data

| Department | Metric | Actual | Target | Status |
|-----------|--------|--------|--------|--------|
| Engineering | Bug Fix Rate | 92% | 90% | ✅ |
| Engineering | Features Shipped | 45 | 40 | ✅ |
| Marketing | Campaign ROI | 340% | 300% | ✅ |
| Marketing | Lead Generation | 1,200 | 1,000 | ✅ |
| Finance | Revenue Growth | 22% | 20% | ✅ |
| Operations | Cost Reduction | 18% | 15% | ✅ |

---

## 💡 What Makes This Different

> Unlike basic automation that just sends plain text emails, this system generates a **full interactive web dashboard** with role-based access, KPI cards, progress bars, and performance tagging — all triggered automatically without any manual intervention.

---

## 👨‍💻 Built By

**Md Sadrhoman** — Automation & No-Code Developer  
🔗 GitHub: [github.com/mdsadrhoman123-stack](https://github.com/mdsadrhoman123-stack)

---

## 📄 License

MIT License — Feel free to use and modify for your projects.

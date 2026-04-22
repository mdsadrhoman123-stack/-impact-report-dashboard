[README_1.md](https://github.com/user-attachments/files/26988853/README_1.md)
<div align="center">

# 📊 Board Impact Report Automation System

**Automated impact report generation for Boards of Directors**

[![N8N](https://img.shields.io/badge/N8N-Automation-FF6D5A?style=for-the-badge&logo=n8n&logoColor=white)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-1A6B4A?style=for-the-badge&logo=supabase&logoColor=white)](https://supabase.com)
[![Vercel](https://img.shields.io/badge/Vercel-Deployed-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://vercel.com)
[![Google Sheets](https://img.shields.io/badge/Google_Sheets-Integration-34A853?style=for-the-badge&logo=googlesheets&logoColor=white)](https://sheets.google.com)
[![License](https://img.shields.io/badge/License-MIT-C9A84C?style=for-the-badge)](LICENSE)

**🔗 [Live Demo](https://impact-report-dashboard-peach.vercel.app) • [N8N Workflow](#-n8n-workflows) • [Setup Guide](#-setup-guide)**

</div>

---

## 🎯 Problem Statement

Organizations manually generate impact reports for board meetings — a **time-consuming, error-prone process**. This system **fully automates** the entire pipeline: from raw data in PostgreSQL to a beautiful, role-based dashboard delivered automatically every Monday morning.

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| ⏰ **Auto Weekly Reports** | Triggers every Monday at 9AM automatically |
| 👥 **Role-Based Views** | CEO, Board Member, Manager — all see different data |
| 📊 **Live Data** | Pulls real-time data from Supabase PostgreSQL |
| 🎨 **Beautiful Dashboard** | Professional HTML with KPI cards & progress bars |
| 🚦 **Performance Detection** | Auto-tags High Performance vs Needs Attention |
| 📋 **Google Sheet Sync** | Clients update data via familiar Google Sheets |
| 🔌 **Decoupled Architecture** | Report structure completely separate from data source |
| 📱 **Mobile Responsive** | Works perfectly on all devices |
| 🌍 **Multi-language Ready** | Switch report language anytime |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                   DATA INPUT LAYER                       │
│         Google Sheets  ←→  Supabase PostgreSQL          │
└────────────────────────┬────────────────────────────────┘
                         │
┌────────────────────────▼────────────────────────────────┐
│                  N8N AUTOMATION LAYER                    │
│                                                          │
│  ⏰ Schedule Trigger (Every Monday 9AM)                  │
│         ↓                                               │
│  🐘 Fetch Impact Data (Supabase)                        │
│         ↓                                               │
│  ⚙️  Process & Group by Department                      │
│         ↓                                               │
│  📄 Generate Beautiful HTML Report                      │
│         ↓                                               │
│  🚦 Check Performance (>80% = High)                     │
│         ↓                    ↓                          │
│  ✅ High Performance    ⚠️  Needs Attention             │
└────────────────────────┬────────────────────────────────┘
                         │
┌────────────────────────▼────────────────────────────────┐
│              ROLE-BASED DASHBOARD (Vercel)               │
│    Board View  |  CEO View  |  Manager View             │
└─────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| 🤖 **Automation** | N8N Cloud | Workflow orchestration |
| 🗄️ **Database** | Supabase (PostgreSQL) | Live data storage |
| ⚙️ **Report Engine** | JavaScript (N8N Code Node) | Data processing & HTML generation |
| 🎨 **Frontend** | HTML + CSS | Role-based dashboard |
| 🚀 **Hosting** | Vercel | Live deployment |
| 📋 **Data Input** | Google Sheets | Client-friendly data entry |

---

## 👥 Role-Based Access

<div align="center">

| 🏢 Board View | 👔 CEO View | 👨‍💼 Manager View |
|:---:|:---:|:---:|
| Executive Summary | Full Detail Report | Own Department Only |
| All Departments | Action Items | Personal KPIs |
| KPI Overview | Complete Analysis | Department Score |

</div>

---

## 📊 Live Dashboard Preview

```
┌─────────────────────────────────────────────┐
│  📊 Board of Directors Performance Overview  │
│  Powered by N8N + Supabase  |  🟢 HIGH PERF │
├─────────────────────────────────────────────┤
│  Board View  |  CEO View  |  Manager View    │
├─────────────────────────────────────────────┤
│  TOTAL KPIs    MET TARGET    SUCCESS RATE    │
│     10             8            80%          │
├─────────────────────────────────────────────┤
│  🏢 Engineering          100% ✅            │
│  🏢 Marketing            100% ✅            │
│  🏢 Finance               50% ⚠️           │
│  🏢 Operations            50% ⚠️           │
└─────────────────────────────────────────────┘
```

---

## 🔄 N8N Workflows

### Workflow 1: Board Report Automation
```
⏰ Schedule (Monday 9AM)
    → 🐘 Fetch Data (Supabase)
    → ⚙️  Process & Group
    → 📄 Generate HTML
    → 🚦 Check Performance
    → ✅ Tag Result
```

### Workflow 2: Google Sheet → Supabase Sync
```
⏰ Every Hour Trigger
    → 📋 Read Google Sheet
    → ✔️  Validate & Transform
    → 🐘 Insert to Supabase
    → 📝 Sync Summary
```

---

## 🚀 Setup Guide

### 1️⃣ Database (Supabase)
```sql
CREATE TABLE departments (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100),
  head_name VARCHAR(100),
  designation VARCHAR(200)
);

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
```

### 2️⃣ N8N Workflow
```
1. Import board-report-workflow.json
2. Connect Supabase credentials
3. Activate workflow ✅
```

### 3️⃣ Deploy Dashboard
```
1. Upload index.html to GitHub
2. Connect repo to Vercel
3. Deploy → Live in 60 seconds! 🚀
```

---

## 📈 Sample Performance Data

| Department | Metric | Actual | Target | Status |
|-----------|--------|:------:|:------:|:------:|
| Engineering | Bug Fix Rate | 92% | 90% | ✅ |
| Engineering | Features Shipped | 45 | 40 | ✅ |
| Engineering | System Uptime | 99.5% | 99% | ✅ |
| Marketing | Campaign ROI | 340% | 300% | ✅ |
| Marketing | Lead Generation | 1,200 | 1,000 | ✅ |
| Finance | Revenue Growth | 22% | 20% | ✅ |
| Operations | Cost Reduction | 18% | 15% | ✅ |

---

## 💡 What Makes This Different

> Unlike basic automation that just sends plain text emails, this system generates a **full interactive web dashboard** with role-based access, KPI cards, progress bars, and performance tagging — all triggered **automatically** without any manual intervention.

---

<div align="center">

## 👨‍💻 Built By

**Md Sadrhoman** — Automation & No-Code Developer

[![GitHub](https://img.shields.io/badge/GitHub-mdsadrhoman123--stack-181717?style=for-the-badge&logo=github)](https://github.com/mdsadrhoman123-stack)

---

⭐ **Star this repo** if you found it helpful!

📄 **MIT License** — Free to use and modify

</div>

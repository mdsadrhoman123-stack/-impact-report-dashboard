<div align="center">
  <img src="https://github.com/user-attachments/assets/0ec4a323-adbc-4189-afb6-c0f3cac6726d" alt="Board Impact Report Banner" width="100%">

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

---

## 🏗️ System Architecture
```mermaid
graph TD
    A[Google Sheets Input] -->|Webhook/Sync| B[(Supabase PostgreSQL)]
    B -->|Fetch Data| C{n8n Workflow}
    C -->|Generate HTML| D[Live Dashboard]
    D -->|Deploy| E[Vercel Hosting]

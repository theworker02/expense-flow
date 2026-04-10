# 💰 ExpenseFlow

![Version](https://img.shields.io/badge/version-v1.0.0-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
![Platform](https://img.shields.io/badge/platform-Base44-8b5cf6?style=flat-square)
![React](https://img.shields.io/badge/React-18-61dafb?style=flat-square&logo=react&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3-38bdf8?style=flat-square&logo=tailwindcss&logoColor=white)
![Recharts](https://img.shields.io/badge/Recharts-2-22c55e?style=flat-square)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square)

> Smart Expense & Finance Management — a full-featured personal finance web app built on [Base44](https://base44.com).

🔗 **Live Demo:** [expense-flow.base44.app](https://expense-flow.base44.app)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Pages & Routes](#pages--routes)
- [Entities](#entities)
- [Components](#components)
- [Settings Modules](#settings-modules)
- [Getting Started](#getting-started)
- [Docker](#docker)
- [Environment Variables](#environment-variables)

---

## Overview

ExpenseFlow is a production-ready personal finance dashboard that lets users track expenses, generate reports, create professional invoices, e-sign documents, and manage all their account settings — all from a clean, modern UI.

---

## Features

| Feature | Description |
|---|---|
| 📊 **Dashboard** | Real-time overview of spending, budget progress, category charts, and recent expenses |
| 💸 **Expense Tracking** | Add, edit, delete, search, and filter expenses by category and date |
| 🧾 **Receipt OCR** | Upload a receipt image and auto-extract date, amount & merchant with AI |
| 🔔 **Budget Alerts** | Automatic email alerts at 80% and 100% of your monthly budget |
| 📈 **Reports** | Monthly spending trends, category breakdowns, and PDF export |
| 🧾 **Invoices** | Create, send, and manage professional invoices with line items, tax, and discounts |
| ✍️ **E-Sign** | Upload documents, draw signatures on canvas, place/resize them, and download signed files |
| ⚙️ **Settings** | 8-section settings panel: Profile, Security, Privacy, Notifications, Appearance, Preferences, Data, Connected Accounts |

---

## Tech Stack

- **Frontend:** React 18, Tailwind CSS, shadcn/ui, Lucide React, Recharts, Framer Motion
- **Backend:** Base44 (database, auth, integrations, backend functions via Deno)
- **PDF Generation:** jsPDF
- **Routing:** React Router v6
- **Data Fetching:** TanStack React Query
- **Canvas Signing:** HTML5 Canvas API

---

## Project Structure

```
├── pages/
│   ├── Dashboard.jsx
│   ├── Expenses.jsx
│   ├── Reports.jsx
│   ├── Invoices.jsx
│   ├── ESign.jsx
│   └── Settings.jsx
├── components/
│   ├── Layout.jsx
│   ├── expenses/
│   │   ├── ExpenseFormDialog.jsx
│   │   ├── ExpenseTable.jsx
│   │   ├── ReceiptUpload.jsx
│   │   ├── BudgetProgress.jsx
│   │   └── CategoryChart.jsx
│   ├── invoices/
│   ├── esign/
│   └── settings/
├── entities/
│   ├── Expense.json
│   └── Invoice.json
├── functions/
│   ├── checkBudgetAlert.js
│   ├── parseReceipt.js
│   └── setupGitHub.js
├── Dockerfile
├── docker-compose.yml
└── App.jsx
```

---

## Pages & Routes

| Route | Component | Description |
|---|---|---|
| `/` | `Dashboard` | Financial overview & KPIs |
| `/expenses` | `Expenses` | Full expense CRUD + receipt OCR |
| `/reports` | `Reports` | Charts & PDF reports |
| `/invoices` | `Invoices` | Invoice management |
| `/esign` | `ESign` | Document signing |
| `/settings` | `Settings` | Account settings hub |

---

## Entities

### `Expense`
| Field | Type | Required | Notes |
|---|---|---|---|
| `date` | string (date) | ✅ | Date of expense |
| `description` | string | ✅ | What it was for |
| `amount` | number | ✅ | Expense amount |
| `category` | enum | ❌ | One of 11 categories |
| `notes` | string | ❌ | Additional details |

### `Invoice`
| Field | Type | Required | Notes |
|---|---|---|---|
| `invoice_number` | string | ✅ | Unique invoice ID |
| `client_name` | string | ✅ | Recipient name |
| `issue_date` | string (date) | ✅ | Date issued |
| `due_date` | string (date) | ✅ | Payment due date |
| `status` | enum | ❌ | Draft / Sent / Paid / Overdue / Cancelled |

---

## Getting Started

1. Sign up at [base44.com](https://base44.com)
2. Fork or import this app
3. Invite users via Base44 dashboard
4. Set environment variables if needed

---

## Docker

```bash
# Build and run with Docker Compose
docker compose up --build

# Or build manually
docker build -t expense-flow .
docker run -p 3000:80 expense-flow
```

The app will be available at `http://localhost:3000`.

---

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `SENDGRID_API_KEY` | Optional | Custom transactional emails via SendGrid |

Set in: **Base44 Dashboard → Settings → Environment Variables**

---

## License

MIT © ExpenseFlow

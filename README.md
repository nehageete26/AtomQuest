# ⚛ AtomQuest – Employee Goal Tracking Portal

> A fully functional, web-based Goal Management System built for the Atomberg Hackathon (FY 2025–26).  
> Supports Goal Creation, Manager Approval, Quarterly Check-ins, Analytics, Escalations, and more — all in a single HTML file with zero backend dependencies.

---

## 🚀 Live Demo

> **https://atom-quest-90ztuu337-nehageete26s-projects.vercel.app/**  

---



## ✨ Features

### Phase 1 — Goal Creation & Approval
- Employee-facing interface to create and submit a Goal Sheet
- Select Thrust Area, Goal Title/Description, Unit of Measurement (UoM), Target, and Weightage
- **System-enforced validation rules:**
  - Total weightage across all goals must equal exactly **100%**
  - Minimum weightage per goal: **10%**
  - Maximum goals per employee: **8**
- Manager **(L1) Approval Workflow** with **inline editing** of Target and Weightage before approving
- Goals are **locked** after approval — no further edits without Admin intervention
- **Rejection with mandatory comment** — reason is surfaced directly to the employee
- **Shared Goals** — Admin/Manager can push a departmental KPI to multiple employees; recipients can adjust weightage only

### Phase 2 — Achievement Tracking & Quarterly Check-ins
- Quarterly update interface for employees to log Actual Achievement vs. Planned Target
- Status selection per goal: **Not Started / On Track / Completed**
- **Manager Check-in module** — structured comment field to document discussion
- **System-computed progress scores** (for tracking only, not ratings):

| UoM Type | Formula |
|---|---|
| Min (Higher is better) | Achievement ÷ Target × 100 |
| Max (Lower is better) | Target ÷ Achievement × 100 |
| Timeline | Completion date ≤ Deadline → 100%, else 0% |
| Zero-based | Value = 0 → 100%, else 0% |

- **Quarterly window enforcement** — check-ins can only be submitted during the active window

### Reporting & Governance
- **Achievement Report** — exportable CSV showing Planned Target vs. Actual Achievement for all employees
- **Completion Dashboard** — real-time view of which employees have completed quarterly check-ins
- **Full Audit Trail** — all changes made to goals after lock date, capturing who changed what and when

### Bonus Features
- 🔔 **In-app Notification System** — approval, rejection, submission, shared KPI, and reminder alerts with unread badge count
- ⚠️ **Escalation Module (Rule-Based)** — automated alerts for: no submission within 7 days, no approval within 7 days, check-in not completed within active window; Admin can resolve escalations
- 📈 **Analytics Module** — employee weighted score chart, goal distribution by Thrust Area, Manager effectiveness dashboard (check-in completion comparison)
- ⚙️ **Cycle Management** — Admin view to manage active check-in windows with schedule reference
- 🏛 **Admin Control Panel** — org-wide goal oversight, goal unlock capability, shared KPI push

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML |
| Styling | Pure CSS (custom design system, dark mode) |
| Data Persistence | In-memory (session state) |
| Fonts | Google Fonts — DM Sans + DM Serif Display |
| Deployment | Vercel |

> **No Node.js. No npm. No database. No build tools required.**  
> The entire application runs from a single `index.html` file.

---

## 🏁 Getting Started

### Open Directly (Simplest)
```bash
# Just open the file in any modern browser
open index.html
```


## ☁️ Deployment

### Deploy to Vercel (Recommended — Free)
```bash
# 1. Install Vercel CLI
npm install -g vercel

# 2. From the project folder
vercel

# 3. Follow prompts — your app will be live in ~60 seconds
```
Or connect your GitHub repo at [vercel.com](https://vercel.com) for auto-deploy on every push.


---

## 👤 User Roles

The portal supports three distinct roles. Switch between them using the **role switcher in the sidebar**.

| Role | Demo Users | Key Capabilities |
|---|---|---|
| **Employee** | Priya Sharma, Rohan Mehta, Ananya Gupta | Create/edit goals, submit for approval, log quarterly actuals, view notifications |
| **Manager (L1)** | Vikram Nair (Sales), Deepa Rao (Engineering) | Inline-edit & approve/reject goals, conduct check-ins, view team progress |
| **Admin / HR** | HR Admin | Full org oversight, push shared KPIs, manage escalations, audit trail, cycle management, CSV export |

---



## 📁 Project Structure

```
atomquest-goal-portal/
│
└── index.html          # Entire application — React + CSS + Logic
└── README.md           # This file
```

> The app is intentionally a single file for maximum portability and zero-config deployment, in line with the hackathon constraint that the portal must be accessible via a web browser.

---



| View | Description |
|---|---|
| Employee Dashboard | Goal sheet with weightage tracker and check-in history |
| Manager Approval | Inline editable approval table with audit logging |
| Admin Analytics | Score charts, Thrust Area distribution, manager effectiveness |
| Escalation Log | Rule-based alerts with resolve workflow |
| Notifications | In-app notification panel with unread count |

---

## ⚠️ Known Limitations

| Limitation | Notes |
|---|---|
| No persistent storage | Data resets on page refresh. In production, replace with a REST API + database (e.g. PostgreSQL, Firebase). |
| No real authentication | Role switching is simulated via a dropdown. Production would use Azure AD / SSO (Section 5.1 of BRD). |
| No real email/Teams notifications | Notification system is in-app only. Production integration would use Microsoft Graph API or SendGrid. |
| Single file | All logic, state, and UI are in one file. Production would be componentized with a proper build pipeline (e.g. Vite + React). |
| Window is hard-coded | The active check-in window (`CURRENT_WINDOW`) is a constant in the code. Change it manually to test different windows. In production, this would be database-driven. |

---

## 👨‍💻 Team

| Name | Role |
|---|---|
| *(Your Name)* | Developer |
| *(Team Member 2)* | Developer |
| *(Team Member 3)* | Designer / Tester |

---

## ⚙️Architecture

<img width="1061" height="724" alt="image" src="https://github.com/user-attachments/assets/8e0eab57-dd50-4aae-afd3-f9787a3397d5" />


## 📄 License

This project was built for the **ATOMQUEST HACKATHON 1.0 — FY 2025–26**.  
All rights reserved © Atomberg Technologies.

---

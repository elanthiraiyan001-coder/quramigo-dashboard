# Quramigo MedCare — Receptionist Dashboard Prototype

A production-grade, highly polished, fully interactive dashboard prototype for the **Quramigo Healthcare Management System (Receptionist Dashboard)**.

🌐 **Live Demo (GitHub Pages):** [https://elanthiraiyan001-coder.github.io/quramigo-dashboard/](https://elanthiraiyan001-coder.github.io/quramigo-dashboard/)

---

## ⚡ Instant Viewing

### Option A: Open Live Link
Share or open directly in any desktop or mobile browser:
👉 [https://elanthiraiyan001-coder.github.io/quramigo-dashboard/](https://elanthiraiyan001-coder.github.io/quramigo-dashboard/)

### Option B: Local Browser Launch (Zero Build Required)
Double-click `index.html` or run:
```bash
open index.html
```

---

## 🎨 Design System & Theme
- **Primary Brand Color:** CurAmigo Royal Blue (`#4169E1` / `bg-blue-600`)
- **Accent Color:** Warm Orange (`#E8621A` / `bg-orange-500`)
- **Neutral Grays:** Modern Slate (`bg-slate-50`, `border-slate-200`, `text-slate-800`)
- **Status Colors:**
  - 🟢 Green (`#10B981`): Operational / Active In-Visit
  - 🟡 Yellow (`#F59E0B`): Temporary Idle / Break $\le$ 4 mins (shows ticking countdown)
  - 🔴 Red (`#EF4444`): Delayed / Inactive > 4 mins (flashing glowing pulse)
- **Typography:** Plus Jakarta Sans & Inter with crisp, high-density hospital SaaS styling.

---

## 🖥️ Key Interactive Features & Architecture

### 1. Persistent Top Bar & The 4-Minute Idle Engine
- **Global Doctor Filter:** Toggles between `[ 👥 All Doctors ]`, `[ 🩺 Doctor A (Chamber 101) ]`, and `[ 🩺 Doctor B (Chamber 102) ]`. All KPIs, charts, and rosters reactively update.
- **The 4-Minute Engine:** Live timers tracking doctor status with auto-transition from idle (Yellow) to delayed (Red pulsing) after 240 seconds.
- **Developer Simulation Button:** `[Simulate Doctor Idle > 4m]` instantly toggles the yellow-to-red blinking delay state for interactive demonstrations.
- **Universal Patient Search (`Ctrl+K`):** Global modal to search patients by name, token, or phone number and jump directly to recording vitals.

### 2. 7 Navigation Tabs
1. **📊 Overview:**
   - Top 4 primary KPIs: Total Consultations, Remaining Consultations, Lobby Queue, Completed Consultations.
   - Dynamic SVG Donut Chart comparing Quramigo App (68%) vs Walk-in (32%) patients with live center counts.
   - Today's Pending Consultations Master Roster with patient details, ETAs, location (`🚗 En-Route` vs `🛋️ Checked-In`), payment status, and quick vitals view.
   - *Strictly excludes "Record Reported Delay" and generic quick-action bars as requested.*
2. **🛎️ Desk Overview (Active Queue & Lab Diagnostics):**
   - Active queue cards with priority tags (Normal, Senior Citizen, Diagnostic Return, Emergency).
   - `[🩺 Record / Edit Vitals]` modal (Systolic/Diastolic BP, Pulse, Body Temp, SpO2, Weight).
   - `[📁 Upload Diagnostic Reports]` (The Lab Workflow): Attaches test reports to existing record without creating duplicate tokens, immediately upgrades priority to `DIAGNOSTIC_RETURN` at the top of the line, and displays a blue `[📄 Reports Attached]` badge.
   - `[⚠️ Report Misconduct & Eject]` modal: Removes token from active queue and logs an incident record.
   - `[+ New Walk-In Registration]` modal: With emergency toggle that bumps the patient to Position #1.
3. **📂 Consultation History:**
   - Filterable by Date Range (Today / This Week / Custom) and Payment Method chips (Cash, UPI, Quramigo).
   - Receipt printing preview modal (`[🖨️ Print Receipt]`) and report viewer (`[📄 View Attached Reports]`).
   - **Privacy Mandate:** Medical diagnoses notes, prescriptions, and clinical doctor notes remain strictly masked.
4. **📅 Calendar & Appointments:**
   - Day / Week / Month timeline view.
   - `[+ Book Walk-In / Future Appointment]`: Instant schedule lock with no approval required.
   - `[🚫 Request Calendar Block]`: Marks slot as `🟡 PENDING DOCTOR APPROVAL` and automatically posts an interactive card into the doctor's messaging thread.
5. **🤖 AI Assistant (Receptionist Copilot):**
   - Grounded in live mock state (exact consultation counts, waiting lobby queue numbers, UPI collections).
   - One-click prompt pills for instant answers.
   - **Strict RBAC Guardrail:** Inquiries into clinical EMR diagnoses or doctor remuneration return the exact required message:
     > *"Access Restricted: Receptionist authorization does not permit access to clinical EMR diagnoses or doctor remuneration data."*
6. **💬 Messaging & Approval Management:**
   - Direct messages with Dr. Rajesh Sharma, Dr. Ananya Sen, Hospital Admin, and clinic group channels.
   - **Interactive In-Chat Approval Cards:** Clicking `[✅ APPROVE]` inside the chat thread auto-approves the request, marks the card approved, and locks the slot on Tab 4's calendar!
7. **⚙️ Settings:**
   - Clean, styled facility configurations placeholder reserved for administrative use.

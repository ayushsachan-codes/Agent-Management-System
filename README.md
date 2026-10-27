# AgentPro - Insurance Agent Management System

**AgentPro** is a modern, responsive web application for insurance companies to recruit, onboard, manage, and track the performance of their insurance agent network.

Built strictly according to the **AgentPro Product Requirements Document (PRD v1.0)** as a frontend-only application using **HTML5, Vanilla CSS3, and ES6+ JavaScript** with persistent `localStorage` support.

---

## 🚀 Key Features & Modules

### 1. **Authentication & Session Simulation (`login.html`, `signup.html`)**
- Role-based accounts: **Admin**, **Manager / Team Lead**, and **Agent**.
- **1-Click Demo Logins** on the login page for instantaneous testing.
- Form validation, error alerts, and automatic redirection to requested pages or dashboard.

### 2. **Executive Network Dashboard (`dashboard.html`)**
- Live KPI stat cards: Total Agents, Active Agents, In-Training Agents, Policies Sold, Total Premium, and Commissions Disbursed.
- **Monthly Commission Overview Chart** (Paid vs. Pending trend using Chart.js).
- **Performance Distribution Doughnut Chart** (Platinum, Gold, Silver, Bronze, Rising Star).
- **Top 5 Leaderboard** with interactive toggle (By Total Premium or Policies Sold).
- Recent network activity stream and quick actions.

### 3. **Agent Directory (`agents.html`)**
- Instant search by Name, Agent ID, Phone, Email, or License number (< 200ms).
- Multi-filter toolbar: Status, Performance Tier, and Location (City/State).
- Multiple sorting options: Name (A-Z/Z-A), Joining Date, Premium Volume, and Commissions.
- **Grid view** and **Table view** toggle.
- Status badges and license expiry warnings.
- Edit Agent profile modal and Deactivate/Activate toggle.

### 4. **Agent Onboarding & Registration (`register-agent.html`)**
- Multi-section onboarding form covering Personal Information, Contact Details, and Professional Licensing.
- Client-side validation: Required fields, email format, 10-digit phone number, unique license validation, and 18+ age check.
- Newly registered agents automatically default to **In Training** status and are auto-enrolled in the mandatory induction training course.

### 5. **Comprehensive Agent Detail Profile (`agent-detail.html?id=...`)**
- Profile hero with avatar, license compliance tag, performance level, and quick stats.
- 5 Interactive tabs:
  1. **Overview**: Personal info, contact details, agency hierarchy, and license validity.
  2. **Policies Sold**: Policy registry and "Issue New Policy" modal with live commission calculation preview.
  3. **Commission History**: Ledger of all earned commissions, rates, and payout statuses.
  4. **Performance & Targets**: Period target vs. achieved progress bars.
  5. **Training & Certifications**: Enrolled courses and certification validity dates.
- Status and level adjustment modal.

### 6. **Commission Management & Disbursement (`commissions.html`)**
- Full transaction ledger tracking Beneficiary Agent, Policy Source, Premium Base, Rate, and Amount.
- Configured commission rules:
  - First Year Commission: Life (25%), Health (15%), Motor (10%), Property (12%).
  - Renewal Commission: 5%.
  - Team Commission: 2% override on manager's team sales.
  - Performance Bonus / Custom Bonus.
- "Mark as Paid" action with transaction reference code and payout date recording.
- Modal to record manual bonuses or overrides.

### 7. **Performance Monitoring & Analytics (`performance.html`)**
- Quarterly and monthly target vs. achieved benchmarks.
- Automated Performance Level Derivation:
  - **Platinum**: $\ge 150\%$
  - **Gold**: $120\% - 149\%$
  - **Silver**: $100\% - 119\%$
  - **Bronze**: $70\% - 99\%$
  - **Rising Star**: Joined $< 12$ months ago and $\ge 60\%$ with growth
- Chart.js Target vs. Achieved comparison and Policies by Category.

### 8. **Training Programs & Compliance (`training.html`)**
- Course catalog with trainer, seat capacity, duration, and status.
- Enroll Agent modal.
- Progress tracking with "Mark Done" action.
- **Automatic Promotion Logic**: Completing the mandatory induction training automatically promotes agents from **"In Training"** to **"Active"** status!
- Regulatory certification registry with expiry warning flags.

### 9. **Incentive Campaigns & Honors Wall (`incentives.html`)**
- Motivational sales campaigns with benchmark criteria and target rewards.
- Agency Hall of Fame: Agent of the Month, Top Health Specialist, and Rookie of the Year.
- "Disburse Bonus" action which directly credits cash rewards to the agent's commission wallet.
- Launch New Incentive Program modal.

### 10. **Management Reports & Financial Exports (`reports.html`)**
- 3 Report subjects: **Agent Network Directory**, **Commission Disbursements**, and **Sales Target & Achievements**.
- Live preview table with computed summary totals row.
- **Download CSV**: Generates real CSV file via Blob download.
- **Export PDF / Print**: Clean print media stylesheet omitting sidebars and extraneous controls for clean paper or PDF output.

### 11. **Bonus Features Implemented**
- **Persistent Dark Mode**: Neutral dark theme with amber highlights, persisted across sessions in `localStorage`.
- **Agent Self-Service Experience**: Personalized sidebar shortcut and profile for logged-in agents.
- **Live In-Memory & LocalStorage Synchronization**: Changes (new policies, new agents, disbursements) persist automatically across page navigation.

---

## 🛠️ Project Directory Structure

```
agentpro/
├── index.html              # Entry point redirecting to dashboard or login
├── login.html              # Authentication simulation with 1-click demo logins
├── signup.html             # User registration with role selection
├── dashboard.html          # Executive network KPIs, charts & leaderboard
├── agents.html             # Agent directory with search, filter, grid/list
├── register-agent.html     # Agent onboarding form with validation
├── agent-detail.html       # Agent profile with 5 interactive tabs & modals
├── commissions.html        # Commission ledger, payouts & manual bonuses
├── performance.html        # Target tracking, automated tiers & charts
├── training.html           # Training programs, certifications & promotions
├── incentives.html         # Campaigns, recognition wall & bonus grants
├── reports.html            # Tabular reports with CSV and PDF/print export
├── css/
│   ├── style.css           # Amber design system tokens, components, responsive layout
│   └── dark.css            # Dark mode overrides
├── js/
│   ├── data.js             # Initial mock dataset & localStorage CRUD store
│   ├── auth.js             # Authentication & session service
│   ├── app.js              # Shared sidebar/topbar layout, theme toggle & toasts
│   ├── agents.js           # Directory filtering, pagination & status toggle
│   ├── commissions.js      # Ledger filters, payouts & manual entry
│   ├── performance.js      # Performance calculations & charts
│   ├── training.js         # Enrollment, certifications & auto-promotions
│   ├── incentives.js       # Campaigns, award bonuses & honors wall
│   └── reports.js          # Live previews, summary totals & CSV download
└── README.md
```

---

## 💻 How to Run

Because this is a pure HTML5/CSS/JavaScript application:
1. Simply double-click **`index.html`** or **`login.html`** in any modern web browser (Google Chrome, Microsoft Edge, Mozilla Firefox, or Safari).
2. Alternatively, serve via any local web server (e.g. VS Code Live Server or Python HTTP server).
3. To reset demo data at any time, click your profile avatar in the top-right corner and select **"Reset Demo Data"**.

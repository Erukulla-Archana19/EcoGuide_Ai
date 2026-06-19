# 🌿 EcoFootprint — Track It. Understand It. Cut It.

> A carbon footprint tracking app that lets individuals log everyday activities, see their CO₂e impact against international climate standards, and get AI-powered guidance from **EcoGuide**, a Gemini-powered sustainability assistant.

![EcoFootprint](https://img.shields.io/badge/EcoFootprint-Carbon%20Tracker-1A3C2B?style=for-the-badge&logo=leaf&logoColor=white)
![Gemini API](https://img.shields.io/badge/AI%20Assistant-Google%20Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

## 🎯 Chosen Vertical

**Carbon Footprint & Sustainability**

This project addresses the challenge:

> *"Help individuals understand, track, and reduce their personal carbon footprint through everyday activity logging and personalised, data-backed insights."*

EcoFootprint is built for someone who wants more than a single "total emissions" number — they want to know how their habits stack up against real climate science (IPCC, IEA, EU policy targets) and what to actually change first.

---

## 🧠 Approach & Logic

The app is structured around a continuous **log → measure → benchmark → act** loop:

```
LOG ACTIVITY → CALCULATE CO₂e → COMPARE TO BUDGET → GET PERSONALISED GUIDANCE
```

### 1. Log
Users record everyday carbon-generating activities — car trips, train journeys, electricity use, meals, and waste — each tagged with a category, quantity, date, and optional note.

### 2. Calculate
Every logged activity is converted to kg CO₂ equivalent using category-specific emission factors, then rolled up into monthly and yearly totals.

### 3. Benchmark
Monthly totals are checked against **seven international standards** (IPCC 1.5°C, IPCC 2°C, IEA Net Zero 2050, EU Green Deal "Fit for 55", EAT-Lancet Planetary Health Diet, UN SDG 13, and the Global Carbon Project average), each shown as Compliant / Warning / Exceeded.

### 4. Act
The Insights page turns the user's own numbers into a Sustainability Score (A–F grade), a global comparison, relatable equivalents (trees needed, km driven, phone charges, flight minutes), and a ranked list of recommended actions with estimated savings. The **EcoGuide AI Assistant** (Gemini-powered) answers free-form questions and can generate a personalised 7-day eco challenge.

---

## ⚙️ How It Works

```
User logs activity (category, quantity, date)
         ↓
Emission factor lookup       → kg CO2e calculated per entry
         ↓
Activities aggregated        → Monthly total, category breakdown, trend
         ↓
Compared against budgets     → 7 international standards checked
         ↓
Insights engine              → Score, comparisons, recommended actions
         ↓
EcoGuide AI (Gemini)          → User's real data injected into prompt
         ↓ (on error)
Fallback guidance             → Local, rule-based tips so the user is never stuck
         ↓
Dashboard / Reports           → Charts, compliance bars, downloadable summary
```

### Monthly Budget Calculation

```
Monthly Budget = Annual Per-Capita Allocation ÷ 12
Category Budget = Monthly Budget × IPCC AR6 Sectoral Share
% of Budget Used = (Logged CO2e ÷ Category Budget) × 100
```

All figures are expressed in **kg CO₂ equivalent (CO₂e)** and represent Scope 1–3 personal emissions.

---

## 📝 Assumptions Made

| Area | Assumption |
|---|---|
| Activity scope | Captures Scope 1–3 personal emissions only; no organisational or business travel |
| Transportation | Car emissions estimated per km driven; mode (car/train) selected per entry |
| Energy | Electricity emissions estimated per kWh logged, tagged by context (home/office) |
| Food | Diet style per meal (vegetarian, mixed, meat-heavy) drives the emission factor, not individual ingredients |
| Waste | Differentiated by disposal method (recycled vs. general waste) |
| Standards budgets | Monthly limits are official annual per-capita allocations divided by 12, using IPCC AR6 sectoral distribution for category-level splits |
| Global average | 400 kg CO₂/month per person, per Global Carbon Project (2023) |
| AI insights | Gemini API available at runtime; if unavailable, the assistant should degrade gracefully rather than fail silently |
| Trend data | Based on actual logged history; months with no entries are not estimated |

---

## 🧩 Core Features

| Feature | Description |
|---|---|
| **Carbon Dashboard** | This month's CO₂e, year-to-date tonnes, sustainability grade, activities logged, monthly trend chart, category pie chart, and compliance bars |
| **Activity Log** | Searchable, filterable (Transportation / Energy / Food / Waste) list of all logged entries with edit/delete |
| **Targets / Int'l Standards** | Footprint checked against IPCC 1.5°C & 2°C pathways, IEA Net Zero 2050, EU Green Deal, EAT-Lancet, UN SDG 13, and the Global Average — each with a progress bar and exceeded/compliant/warning status |
| **Insights & Actions** | Sustainability score (A–F), global comparison bar, relatable footprint equivalents, biggest emission sources ranked, and recommended actions with estimated kg CO₂/month savings |
| **Weekly Challenge** | Turn any recommended action into a trackable weekly challenge |
| **EcoGuide AI Assistant** | Gemini-powered chat that answers sustainability questions using the user's real logged data, with chat history saved per session |
| **Reports** | Exportable summaries of footprint and compliance status |
| **Dark Mode** | Full dark theme across dashboard and all sub-pages |

---

## 📁 Project Structure

> Adjust paths to match your actual repository — update this section once your file layout is finalised.

```
ecofootprint/
├── index.html / app entry
├── src/
│   ├── pages/
│   │   ├── Dashboard.*            ← Carbon Dashboard
│   │   ├── Activities.*           ← Activity Log + Log Activity form
│   │   ├── Targets.*              ← Int'l Standards comparison
│   │   ├── Insights.*             ← Sustainability score + recommendations
│   │   └── Reports.*              ← Exportable reports
│   ├── components/
│   │   ├── Sidebar / Navigation
│   │   ├── ComplianceBar
│   │   ├── CategoryPieChart
│   │   ├── EmissionsTrendChart
│   │   └── EcoGuideChat            ← AI Assistant UI
│   ├── lib/
│   │   ├── emissionFactors.*       ← Category emission factor constants + sources
│   │   ├── standards.*             ← IPCC / IEA / EU / EAT-Lancet / UN SDG13 budgets
│   │   ├── scoring.*               ← Sustainability score calculation
│   │   └── gemini.*                ← Gemini API client + fallback insights
│   └── styles/
├── public/
└── package.json
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** >= 18 ([download](https://nodejs.org))
- **npm** >= 9
- A **Google account** (for the Gemini API key used by EcoGuide)
- **Git** installed

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/ecofootprint.git
cd ecofootprint
```

### 2. Install dependencies

```bash
npm install
```

### 3. Add your Gemini API key

Create a `.env` file in the project root:

```bash
GEMINI_API_KEY=YOUR_GEMINI_API_KEY_HERE
```

**Get a free key:**
1. Go to [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)
2. Sign in with your Google account
3. Click **Create API key**
4. Paste it into `.env`

### 4. Run the development server

```bash
npm run dev
```

Open the local URL printed in your terminal (e.g. `http://localhost:3000` or `http://localhost:5000`).

### 5. Build for production

```bash
npm run build
npm run preview
```

---

## 🌐 Deployment

EcoFootprint is currently hosted on **Replit** (`*.replit.app`). It can also be deployed to any static/Node host:

### Replit
The app auto-deploys via the Replit "Deploy" action — no extra config required beyond setting `GEMINI_API_KEY` in Replit Secrets.

### Netlify / Vercel / Firebase
```bash
# Netlify
npm install -g netlify-cli && netlify deploy --prod

# Vercel
npm install -g vercel && vercel --prod

# Firebase Hosting
npm install -g firebase-tools && firebase login && firebase deploy
```

---

## 🤖 AI Integration — EcoGuide (Google Gemini)

EcoGuide is the in-app assistant available from **AI Assistant** in the sidebar.

### How it's used

- Suggested prompts: transportation tips, home energy savings, low-carbon foods, waste reduction, "what's my sustainability score based on?", and a personalised 7-day eco challenge
- Responses are grounded in the user's **actual logged data** (e.g. category totals, exceeded standards) rather than generic advice
- Conversations are saved and listed by date so users can revisit past chats
- If the Gemini API is temporarily unavailable, the assistant should fall back to locally generated, rule-based guidance so the user is never left without an answer

---

## 🔬 Emission Categories & Standards Reference

### Logged categories
| Category | Example entries seen in-app |
|---|---|
| Transportation | Car (km), Train (km) |
| Energy | Electricity (kWh) — home / office |
| Food | Vegetarian, Mixed, Meat-Heavy (per meal) |
| Waste | Recycled (kg), General waste (kg) |

### International standards checked
| Standard | Body | Basis |
|---|---|---|
| IPCC 1.5°C Pathway | Intergovernmental Panel on Climate Change | AR6 (2023) |
| IPCC 2°C Pathway | Intergovernmental Panel on Climate Change | AR6 (2023) |
| IEA Net Zero 2050 (2030 Interim) | International Energy Agency | NZE Roadmap (2023) |
| EU Green Deal — Fit for 55 | European Commission | EU Fit for 55 |
| EAT-Lancet Planetary Health Diet | EAT-Lancet Commission | 2019 report |
| UN SDG 13 — Climate Action | United Nations | SDG 13 |
| Global Average (2024) | Global Carbon Project | 2023 data |

All monthly budgets are derived from official per-capita annual allocations ÷ 12, with category-level splits following IPCC AR6 sectoral methodology.

---

## ♿ Accessibility

- Clear visual status indicators (✓ compliant, ⚠ warning, ✕ exceeded) that don't rely on colour alone
- Legible typography and high-contrast dark mode
- Sidebar navigation usable via keyboard
- Charts paired with numeric labels, not colour-only encoding

---

## 📱 Browser Support

| Browser | Support |
|---|---|
| Chrome / Edge 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Android Chrome | ✅ Responsive (mobile-first design) |
| iOS Safari 14+ | ✅ Responsive |

---

## 🔒 Security

- No API keys committed to the repository — stored as environment variables / Replit Secrets
- AI-generated text sanitized before rendering
- No `eval()` or unsafe HTML injection
- `.env` and `.env.local` excluded via `.gitignore`

---

## 📄 License

MIT License — free to use, modify, and deploy.

---

## 🙏 Credits

| Resource | Source |
|---|---|
| Climate standards | IPCC AR6 (2023), IEA NZE Roadmap (2023), EU Fit for 55, EAT-Lancet Commission (2019), UN SDG 13, Global Carbon Project (2023) |
| AI assistant | Google Gemini |
| Hosting | Replit |

---

## 👤 Author

Built as part of a personal carbon-awareness project.

> *"What gets measured gets managed — especially your carbon footprint."*

---

<p align="center">
  Made with 💚 for the planet
  <br/>
  <a href="#-ecofootprint--track-it-understand-it-cut-it">Back to top ↑</a>
</p>

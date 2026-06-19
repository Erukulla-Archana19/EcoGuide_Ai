# 🌍 EcoGuide AI

A personal carbon-tracking app. Log your daily activities, see exactly how much CO₂ they produce, check that number against real international climate targets, and ask an AI assistant what to do about it.

![Status](https://img.shields.io/badge/Status-Active-2ea043?style=flat-square)
![AI](https://img.shields.io/badge/AI%20Assistant-Gemini-4285F4?style=flat-square&logo=google)
![Platform](https://img.shields.io/badge/Hosted%20on-Replit-orange?style=flat-square)

---

## What it does

EcoGuide AI is split into six screens, reachable from the sidebar menu:

| Screen | What you see |
|---|---|
| **Dashboard** | This month's total CO₂ (kg), this year's total (tonnes), a 0–100 sustainability score with a letter grade, number of activities logged, a 6-month emissions trend line, a category pie chart, and budget bars per category |
| **Activities** | A full log of every entry — type (Car, Train, Electricity, Vegetarian/Mixed/Meat-Heavy meals, Recycled/General waste), quantity, date, note, kg CO₂, with search and category filters and an edit/delete icon per row |
| **Targets / Int'l Standards** | Your monthly footprint plotted against 7 real-world climate benchmarks, each marked Compliant, Warning, or Exceeded |
| **Insights** | A written breakdown of your score, how you compare to the 400 kg/month global average, "what your footprint looks like" in relatable units, your top 3 emission sources, and a list of recommended actions you can turn into a weekly challenge |
| **AI Assistant** | A chat window (EcoGuide) with quick-start prompts and a saved history of past conversations |
| **Reports** | Exportable summary of the above |

There's also a dark mode toggle at the bottom of the sidebar.

---

## International standards it checks against

This is the most distinctive part of the app — instead of just showing "your CO₂ this month," it grades that number against 7 published climate targets:

1. **IPCC 1.5°C Pathway** — Intergovernmental Panel on Climate Change
2. **IPCC 2°C Pathway** — Intergovernmental Panel on Climate Change
3. **IEA Net Zero 2050** (2030 interim target) — International Energy Agency
4. **EU Green Deal — Fit for 55** — European Commission
5. **EAT-Lancet Planetary Health Diet** — EAT-Lancet Commission
6. **UN SDG 13 — Climate Action** — United Nations
7. **Global Average (2024)** — Global Carbon Project

Each budget is a monthly figure derived from the official annual per-capita allocation ÷ 12, with category-level limits split out using IPCC AR6 sectoral methodology. Every standard card shows your footprint vs. its budget as a progress bar, the exact kg over/under, and a status chip (✓ Compliant / ⚠ Warning / ✕ Exceeded). At the top of the page is a 3-way summary: standards met, near limit, and exceeded.

---

## Activity categories tracked

| Category | Logged as |
|---|---|
| Transportation | Car (km), Train (km) |
| Energy | Electricity (kWh) |
| Food | Vegetarian / Mixed / Meat-Heavy (number of meals) |
| Waste | Recycled (kg) / General (kg) |

Each category also has its own monthly budget on the Dashboard (e.g. a Transport Budget and a Food Emissions Limit), shown as a separate compliance bar with Exceeded/Warning/OK status.

---

## Insights page

The Insights screen turns raw numbers into something readable:

- **Sustainability Score** — a letter grade (e.g. "A, 80/100") with a percentage comparison to the global average
- **Global Comparison bar** — your footprint vs. the 400 kg CO₂/month global average, with a one-line verdict ("Well below the global average — excellent work")
- **What does your footprint look like?** — your monthly kg converted into relatable equivalents: trees needed per year to offset it, equivalent km driven, equivalent smartphone charges, equivalent minutes of flying
- **Your biggest emission sources** — ranked list (e.g. Food, Transportation, Energy) with kg and % of total, plus a one-line explanation of why that category matters
- **Recommended actions** — paired cards (e.g. "Try one meat-free day" vs. "Reduce beef and lamb specifically") each tagged with a difficulty (easy/medium), an estimated kg/month saving, and a button to turn it into a weekly Challenge
- **Personalised Action Plan** — a generator that builds a 7-day carbon reduction plan from your recommended actions, showing total potential saving

---

## AI Assistant (EcoGuide)

A chat assistant, powered by Gemini, accessible from the sidebar. On open it offers six quick-start prompts:

- How can I reduce my transportation emissions?
- What's the best way to lower my home energy use?
- Which foods have the lowest carbon footprint?
- How do I reduce my waste emissions?
- What's my sustainability score based on?
- Give me a personalised 7-day eco challenge

Answers are written using the user's real numbers — for example, when asked about energy it referenced the user's actual energy emissions for the month and explained how that contributes to exceeding the IPCC 1.5°C and IEA Net Zero pathways, before giving concrete tips. Past chats are saved and listed by date/time so a conversation can be resumed later, and a "New Chat" button starts a clean session.

---

## Tech notes

- Hosted on Replit (`*.replit.app`)
- AI Assistant runs on Google Gemini
- Designed mobile-first, with a full dark theme

> The exact framework, file structure, and emission-factor source code aren't visible from the app screens — fill in a "Tech Stack" and "Project Structure" section here once you share your repo, and I'll add accurate setup/build instructions instead of guessed ones.

---

## License

Add your preferred license here (MIT, etc.)

---

<p align="center">Made with 💚 for the planet</p>

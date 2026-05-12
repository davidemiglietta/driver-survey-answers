# 🚗 Otoqi Driver Survey — Results Dashboard

Interactive dashboard analyzing **314 responses** collected from Otoqi drivers in Italy 🇮🇹, France 🇫🇷, and Germany 🇩🇪.

👉 **[Open the dashboard](https://your-username.github.io/your-repo-name/)** *(replace with your actual GitHub Pages URL)*

---

## What's inside

The dashboard has **two tabs**:

### 📊 Charts
A visual summary of the survey results, with **14 questions** grouped in three sections:
- **Communication** (message volume, channels, NPS rating, etc.)
- **Experience with Otoqi** (quality indicators, blockers, training ratings, recognition, etc.)
- **Final** (interview availability)

For each question you get **three views**, switchable from the toggle on top of each chart:
- 📊 **Aggregated (EN)** — all 314 responses combined, in English
- 🌐 **By country (EN)** — IT/FR/DE side by side, in English (good for cross-country comparison)
- 🌍 **By country (original language)** — same as above, but with original wording per country

> Note: bars show **percentages** so countries are directly comparable, while absolute counts appear as labels on each bar.

### 💬 Free Text Answers
A searchable table of **1,352 open-ended answers** (comments, "Other" free-text, training gaps, recognition suggestions, etc.) — kept in their original language.

---

## How to use the filters

### On the Charts tab
At the top of the page there's a filter bar. Use it to **narrow the analysis** to specific driver segments:
- **Country** — Italy / France / Germany
- **Level** — Standard / Experts / No level *(from Airtable)*
- **Scoring** — driver's internal scoring bucket: 9-10 (top) / 7-9 / 5-7 / <5
- **Missions** — total missions completed: <10 / 10-49 / 50-199 / 200+
- **Interview** — available for a follow-up interview (Yes / No)
- **Driver name** — search by name or email

Filters apply to **all charts simultaneously**. The counter on the right tells you how many responses match your selection.

Click **Clear filters** to reset.

### On the Free Text tab
Same filters, plus:
- **Question** — filter by the specific question the answer is about
- **Search** — search inside the text of the answers

---

## Useful filter recipes

Some examples of how to slice the data:

- **Top performers' opinions** → Scoring `9-10` + Missions `200+`
- **Critical voices** → Scoring `<5` or `5-7`
- **Recent joiners** → Missions `<10`
- **Pool for interviews** → Interview `Yes`
- **Italy only** → Country `Italy`
- **Comments about fuel** → Free Text tab + Search `carburante` or `fuel`

---

## Data sources

The dashboard reads from **three sources**, all merged into a static snapshot:

1. **Tally form exports** (one per language) — the ground truth for survey responses
2. **Airtable driver database** — for enrichment: scoring, level, total missions, interview availability
3. **English form template** — used to translate all multiple-choice options to canonical English

⚠️ The dashboard is a **static snapshot**. It doesn't refresh automatically when new responses come in — the HTML file must be regenerated and re-uploaded.

---

## Notes & caveats

- **3 test responses excluded** — internal tests by the team (Davide, Mattia, Alex) are filtered out from all charts and stats.
- **German Q6 & Q7 in Section 2** are open answers instead of multiple-choice (a request from the German team about scoring sensitivity). They don't appear in the charts but you'll find them in the Free Text tab.
- **Multi-select questions** — the "Other" count reflects how many drivers selected the "Other" option (via the boolean flag), not the free text they typed. The free text itself goes into the Free Text tab.
- **Response rates** are computed against the number of active drivers per country who received the survey link.

---

## Tech notes

- **Single HTML file** — no backend, no database. All data is embedded as JSON inside the page.
- **Plotly.js** loaded from CDN (needs internet on first load, then cached by the browser).
- **Works on all modern browsers** (Chrome, Firefox, Safari, Edge). On mobile, layout adapts to a single column.

---

## File contents

- `index.html` — the dashboard itself
- `README.md` — this file

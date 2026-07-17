# Course Projects — Quick Overview

# Kursprojekt — Snabb översikt

Five **bilingual step-by-step guides** for **Day 6–7**. Each file has:
1. **Part 1** — build a simple one-page app by hand (little CSS, plain HTML/JS)
2. **Part 2** — improve it with **Cline** using ready-made prompts

All apps are meant for **GitHub Pages** (no frameworks, usually one `index.html`).

Fem **tvåspråkiga steg-för-steg-guider** för **Dag 6–7**. Varje fil har:
1. **Del 1** — bygg en enkel ensidig app för hand (lite CSS, ren HTML/JS)
2. **Del 2** — förbättra den med **Cline** med färdiga prompts

Alla appar är tänkta för **GitHub Pages** (inga ramverk, oftast en `index.html`).

| # | Project | API key? | Difficulty |
|---|---------|----------|------------|
| 1 | [Job Finder](Project_1_Job_Finder_for_Sudanese_Students_in_Sweden.md) | No | ⭐ Easy |
| 2 | [Route Planner](Project_2_Public_Transport_Route_Planner.md) | Yes (Trafiklab) | ⭐⭐ Medium |
| 3 | [Statistics Explorer](Project_3_Sweden_Statistics_Explorer.md) | Yes (Apiverket test token) | ⭐⭐ Medium |
| 4 | [Career Recommender](Project_4_Career_Path_Recommender.md) | No | ⭐⭐ Medium |
| 5 | [City Assistant](Project_5_New_Student_City_Assistant.md) | Yes (multiple) | ⭐⭐⭐ Advanced |
| 6 | [Crypto Price Checker](Project_6_Crypto_Price_Checker.md) | No (CoinGecko) | ⭐ Easy |

You may also bring **your own idea** — same rules: small scope, one API minimum, plan before you code.

Ni får också ta med **en egen idé** — samma regler: litet scope, minst ett API, planera innan ni kodar.

---

## Project 1 — Job Finder for Sudanese Students

**One line:** Search Swedish job ads by keyword and city — built for students looking for part-time or entry-level work.

**Page at a glance:** A clean job-search dashboard. Top: app title + short intro. Center: a **search card** with two input fields (**Keyword**, **City**) and a **Search** button. Below: a **results table or card list** showing job title, employer, city, publish date, and deadline. Optional detail panel when you click one job. Footer line: “X jobs found” + top cities.

**Image prompt hint:** *Modern student job-search web app, light background, blue accents, search bar with “deltid” and “Stockholm”, scrollable job result cards with company names and dates, friendly and simple UI, desktop browser mockup.*

**Full brief:** [Project_1_Job_Finder_for_Sudanese_Students_in_Sweden.md](Project_1_Job_Finder_for_Sudanese_Students_in_Sweden.md)

---

## Project 2 — Public Transport Route Planner

**One line:** Enter a **From** and **To** place — see how to travel by Swedish public transport (times, duration, transfers).

**Page at a glance:** A travel-planner layout. Top: title “Route Planner”. Two side-by-side inputs (**From**, **To**) + **Find route** button. Below: **route option cards** — each shows departure time, arrival time, total duration, number of transfers, and transport icons (bus, train, metro). Optional step-by-step timeline for one chosen route.

**Image prompt hint:** *Swedish public transport route planner web app, “Stockholm Central” to “Malmö Central”, route cards with train and bus icons, departure/arrival times, minimal Scandinavian design, white and green accents, browser mockup.*

**Full brief:** [Project_2_Public_Transport_Route_Planner.md](Project_2_Public_Transport_Route_Planner.md)

---

## Project 3 — Sweden Statistics Explorer

**One line:** Explore and **compare Swedish municipalities** with real population/statistics data — tables and charts.

**Page at a glance:** A small **data dashboard**. Top: title + dataset picker or municipality selector. Middle: a **bar chart or line chart** comparing regions (e.g. Stockholm vs Uppsala). Bottom: a **simple data table** + one sentence **insight** (“Stockholm is much larger, but Uppsala is growing…”). Clean, readable numbers — not cluttered.

**Image prompt hint:** *Statistics dashboard web app about Swedish cities, bar chart comparing municipality populations, simple table below, soft gray background, data-visualization style but beginner-friendly, browser mockup.*

**Full brief:** [Project_3_Sweden_Statistics_Explorer.md](Project_3_Sweden_Statistics_Explorer.md)

---

## Project 4 — Career Path Recommender

**One line:** Enter your **skills** (e.g. Python, Excel) — get **recommended career paths** backed by real job ads.

**Page at a glance:** A skills-first recommender. Top: title “What jobs fit my skills?”. Input area for **3–5 skill tags** + **Recommend** button. Results split into two zones: **Top 3 career paths** (ranked cards with job-title counts) and **Evidence** — a short list of 5 real job ads that support the recommendation. Optional sidebar: top cities for those skills.

**Image prompt hint:** *Career recommendation web app for students, skill tags “Python Excel SQL”, three highlighted career path cards, supporting job listings below, modern card UI, purple and white theme, browser mockup.*

**Full brief:** [Project_4_Career_Path_Recommender.md](Project_4_Career_Path_Recommender.md)

---

## Project 5 — New Student City Assistant *(capstone)*

**One line:** Pick a **Swedish city** — see **jobs**, **transport**, and **basic city stats** in one place. Scope down to one section for Day 6!

**Page at a glance:** An all-in-one **city dashboard**. Top: **city dropdown** (Stockholm, Göteborg, Malmö…). Three stacked sections on one scrollable page:
1. **Jobs** — list of 10 student-friendly jobs in that city
2. **Transport** — main station/stop + one example route card
3. **City facts** — population or stat snippet + plain-language summary

Feels like a “welcome to your city” hub for new students.

**Image prompt hint:** *All-in-one city assistant web app for new students in Sweden, city selector “Stockholm”, three sections Jobs Transport City Facts, job cards transport route timeline population number, warm friendly UI, browser mockup.*

**Full brief:** [Project_5_New_Student_City_Assistant.md](Project_5_New_Student_City_Assistant.md)

---

## Project 6 — Crypto Price Checker (Educational)

**One line:** Search a cryptocurrency and show live price in **SEK** and **USD** plus 24h change (learning only — not investment advice).

**Page at a glance:** Title + strong educational disclaimer. Search box for a coin name + **Check price**. Result card with coin icon, name/symbol, SEK price, USD price, and green/red 24h change.

**Image prompt hint:** *Educational crypto price checker web app, search “bitcoin”, result card with BTC icon SEK and USD prices and red/green 24h percent, clear “not financial advice” banner, clean student UI, browser mockup.*

**Full brief:** [Project_6_Crypto_Price_Checker.md](Project_6_Crypto_Price_Checker.md)

---

## Tips before you start / Tips innan ni börjar

- Read your full brief — it has **exact API URLs** and field names.
- Open the API in the **browser first** (see Day 3 tutorial).
- Build **1–2 core features** today; polish on Day 7.
- Never commit **API keys** to a public repo.
- For the crypto project: keep the **“not financial advice”** disclaimer visible.

---

*Part of [teknikkurs26](../README.md) — Summer coding course for youth.*

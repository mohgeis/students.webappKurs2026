# Vibe Coding Web Apps with Public APIs

A 7-day course for teenagers (ages 14–20)

---

## Course Overview

This course teaches teenagers how to build real, working web apps that pull live data from public APIs — using AI-assisted "vibe coding" while genuinely understanding what they are building.
The goal is not to copy-paste blindly, but to direct an AI assistant with intent, read and judge the code it produces, and ship something they're proud of.

By the end, every student has a deployed web app of their own design that talks to at least one public API.

### Format
- **Duration:** 7 days, 2 hours per day (14 hours total)
- **Audience:** Ages 14–20 with *basic* programming/development skills
- **Approach:** AI-assisted ("vibe") coding + concept-first understanding
- **Theme:** Web-app development consuming public APIs

### Prerequisites
- Comfort with basic programming ideas: variables, loops, conditionals, functions.
- A laptop with a modern browser.
- A GitHub account (free).
- An AI coding tool (e.g. Cursor) and/or an AI chat assistant

### What students will be able to do by the end
1. Explain how a web app, a server, and an API talk to each other.
2. Read an API's documentation and make their first request.
3. Use an AI assistant effectively — prompting, reviewing, and fixing its output.
4. Build a multi-feature web app with HTML, CSS, and JavaScript.
5. Handle real-world data: loading states, errors, and empty results.
6. Deploy a live app to the internet and share the link.

### Guiding principles for instructors
- **Concept before code.** Each day opens with a short "why/what" before any building.
- **AI as a pair, not a crutch.** Students must be able to explain any line their AI wrote.
- **Build something real every single day.** No day ends without a runnable result.
- **Fail safely.** Breaking things and reading error messages is part of the lesson.

---

## Recurring 2-Hour Lesson Rhythm

Each day follows roughly the same shape so students always know what to expect:

| Block | Time | What happens |
|-------|------|--------------|
| Warm-up & recap | 10 min | Quick review + today's goal in one sentence |
| Concept mini-lesson | 25 min | The "why/what" — diagrams, demos, discussion |
| Guided build | 45 min | Build together, step by step, with the AI |
| Independent challenge | 30 min | Students extend it on their own / in pairs |
| Wrap-up & share | 10 min | Show results, name one thing learned, preview tomorrow |

---

## Day 1 — Intro to AI, How the Web Works & Your First Vibe-Coded Page

**Concept goal:** Understand what AI is and the moving parts of the web before
building with the AI.

**Intro to AI (~15 min):**
- **What AI actually is:** software that learns patterns from lots of examples,
  rather than following rules a human wrote by hand.
- **What a large language model (LLM) is:** an AI trained on huge amounts of text
  that predicts the next words — this is what powers chat assistants and AI coding
  tools.
- **What it's great at / bad at:** great at drafting, explaining, and boilerplate;
  can be confidently *wrong* ("hallucinate"), so you must check its output.
- **Why it matters for this course:** the AI is your coding partner — but *you*
  stay in charge, review its work, and own the result.

**Web basics:**
- The big picture: client vs. server, frontend vs. backend, what a "request" is.
- What a web app actually is (HTML = structure, CSS = style, JS = behavior).
- What "vibe coding" means and what it does *not* mean (you still own the code).
- Tour of the AI coding tool: prompting, accepting/rejecting changes, undo.

**Hands-on build:** A personal "About Me" single page.
- Students describe the page to the AI in plain language and build it up.
- Practice: ask the AI to change colors, add a section, then read what changed.

**Independent challenge:** Add a new section the AI didn't suggest and explain
each part of the generated HTML to a partner.

**Concept check:** "Point to the HTML, the CSS, and the JS. What does each do?"

---

## Day 2 — Prompting an AI Well & Reading Its Code

**Concept goal:** Treat the AI like a junior teammate you must direct and review.

- Anatomy of a good prompt: context + goal + constraints + examples.
- Iterating: small steps beat one giant request.
- Reading code you didn't write: how to skim, find the relevant part, and ask
  the AI to *explain* a section.
- Saving your work: get in the habit of keeping snapshots as you go
  (the full Git/GitHub workflow comes on Day 5).

**Hands-on build:** An interactive "Quote / Joke of the day" page (still local,
no API yet) — a button that swaps text from a small built-in list.
- Introduces functions, events (clicks), and updating the page with JS.

**Independent challenge:** Make the button pick a *random* item and disable it
for 2 seconds after a click — using the AI, then explaining the logic.

**Concept check:** "Rewrite this vague prompt into a clear one." (group exercise)

---

## Day 3 — What an API Is & Your First Real Data

**Concept goal:** Demystify APIs — a menu of requests another service answers.

- API as a restaurant menu: endpoints, requests, responses.
- JSON: how data is shaped, how to read it (keys, values, arrays, nesting).
- Reading API docs: base URL, endpoints, parameters, example responses.
- Tools to *see* data first: open an API URL in the browser / a viewer.

**Hands-on build:** Fetch and display data from one simple, no-key public API.
- Suggested beginner APIs (all free, most need no key):
  - [Open-Meteo](https://open-meteo.com/) — weather, no key
  - [Dog CEO](https://dog.ceo/dog-api/) — random dog images, no key
  - [REST Countries](https://restcountries.com/) — country info, no key
  - [Bored API](https://www.boredapi.com/) — activity ideas, no key
- Students `fetch` the data and print it, then show one field on the page.

**Independent challenge:** Display three different fields from the response,
nicely formatted.

**Concept check:** "Trace the journey of the data from the API to the screen."

---

## Day 4 — Building a Real Mini App Around an API

**Concept goal:** Turn raw data into a usable feature with input and output.

- User input → request → response → display (the core app loop).
- Query parameters: how user input changes what the API returns
  (e.g. a city name, a country, a search term).
- Structuring code into small, named functions.

**Hands-on build:** A search-driven app, e.g. a **Weather Lookup** or
**Country Explorer**: type something in, get live results back, render them
in a card.

**Independent challenge:** Add a second piece of info to each result and improve
the layout/styling with the AI's help.

**Concept check:** "Where exactly does the user's input enter the request?"

---

## Day 5 — Git, GitHub & Working Like a Real Developer

**Concept goal:** Understand how developers save, track, and share their code —
and why every serious project lives in version control.

- **Why version control exists:** the pain of `final_v2_REALLY_final.html`;
  snapshots you can return to; never losing work.
- **Git vs. GitHub:** Git = the tool that tracks changes on your computer;
  GitHub = the website that hosts and shares those projects online.
- **The core Git ideas (kept simple):**
  - *repository (repo)* — your project + its full history
  - *commit* — a saved snapshot with a message describing what changed
  - *push / pull* — sending your work to GitHub / getting updates back
  - *history & undo* — going back to an earlier version when you break things
- **Branches (gentle intro):** trying an idea without breaking the main version.
- **Collaboration concepts:** repos, issues, pull requests, and README files —
  how teams build together (and how open source works).
- **AI + Git:** letting the AI help write commit messages and explain a diff,
  while *you* decide what to commit.

**Hands-on build:** Put the Day 4 app under version control, end to end:
1. Create a repo (locally and/or on GitHub).
2. Make several commits with clear messages as they add a small feature.
3. Push the project to GitHub.
4. Add a short README describing the app and the API it uses.
5. Use the history to view (and revert) an earlier version.

**Independent challenge:** Create a branch, make a visible change (e.g. a new
color theme or section) with the AI, commit it, then merge it back into main.

**Concept check:** "Explain the difference between Git and GitHub, and what a
commit is." / "Why would you want a project's full history?"

**Bonus mini-session — Cyber Security & Hacking (~15–20 min):**
Pushing code to a public repo is the perfect moment to talk about staying safe
online. Keep it hands-on and story-driven, not scary.

- **Why it matters *right now*:** a public repo is visible to everyone — including
  bots. The #1 beginner mistake is committing *secrets* (API keys, passwords,
  tokens); automated scanners can find a leaked key within minutes of pushing.
- **Secrets hygiene:** keep keys out of your code, use a `.gitignore` and
  environment variables, and if a key ever leaks, **revoke/rotate it immediately**
  (deleting the commit is not enough — it's already in history).
- **What "hacking" really is:** ethical vs. malicious hackers; most real attacks
  exploit simple mistakes (exposed data, weak/reused passwords, phishing) — not
  movie-style magic.
- **Everyday defenses:** strong unique passwords + a password manager, and turn on
  **two-factor authentication (2FA) for GitHub** together in class.
- **The browser hides nothing:** anything in frontend JavaScript is visible to
  users, so you can't trust the browser with real secrets — that's *why* some APIs
  require a backend.
- **Ethics & the law:** attacking systems you don't own is illegal; channel the
  curiosity into legal playgrounds like Capture The Flag (CTF) games and practice
  sites.

**Demo idea:** show a (fake) API key committed to a repo and how GitHub secret
scanning flags it; then enable 2FA on a GitHub account live.

**Security concept check:** "Name one thing you should never put in a public repo —
and what you'd do if you pushed it by accident."

> Note: This sets up Day 7 — students will *deploy straight from their GitHub
> repo*, so getting their project onto GitHub today makes shipping easy.

---

## Day 6 — Project Day: Design & Build Your Own App

**Concept goal:** Go from idea to plan to working prototype independently.

- Scoping: pick a *small enough* idea (1–2 core features).
- Sketching a plan before prompting: what data, which API, what screens.
- Working iteratively with the AI on a multi-part project.

**Hands-on build:** Students choose a public API and build their own app.
Example project ideas:
- Movie/show finder, recipe browser, currency or unit converter,
  Pokémon explorer, NASA picture-of-the-day gallery, GitHub user card,
  meme generator, country quiz game.

**Public API directories to browse:**
- [public-apis (GitHub list)](https://github.com/public-apis/public-apis)
- [Free Public APIs](https://www.freepublicapis.com/)

**Deliverable by end of day:** A working prototype with at least one API feature.

**Concept check:** Each student states their app's one-sentence purpose and which
API powers it.

---

## Day 7 — Polish, Deploy & Showcase

**Concept goal:** Shipping is a skill: finish, publish, and present.

- "Done enough": polishing UI, fixing the top 1–2 bugs, writing a short README.
- Deploying for free: getting a public link
  (e.g. [GitHub Pages](https://pages.github.com/),
  [Netlify](https://www.netlify.com/), or [Vercel](https://vercel.com/)).
- Talking about your work: what it does, how it works, what was hard.
- Responsible AI use & next steps: how to keep learning after the course.

**Hands-on:** Final polish + deploy each app to a live URL.

**Showcase (final 30–40 min):** Each student demos their app and shares:
1. What it does, 2) the API it uses, 3) one thing the AI got wrong that *they*
fixed, 4) one thing they're proud of.

**Wrap-up:** Where to go next — ideas, communities, and project challenges.

---

## Assessment (light-touch, project-based)

Rather than tests, students are assessed on understanding and shipping:
- **Daily concept checks** (can they explain it, not just run it?).
- **Daily runnable result** (something works at the end of each day).
- **Final project + demo** (an app that uses a public API, deployed live).
- **"Explain your code" rule:** can the student walk through any AI-written
  section in their own words?

---

## Materials & Setup Checklist

**Before Day 1, each student needs:**
- [ ] A laptop + charger and a modern browser
- [ ] A GitHub account
- [ ] The AI coding tool installed (e.g. Cursor) and signed in
- [ ] A code-friendly mindset: it's okay to break things

**Instructor prep:**
- [ ] Test every demo API the week before (APIs change/break).
- [ ] Pre-create free API keys for Day 5/6 backups.
- [ ] Have a deployment account ready to demo on Day 7.
- [ ] Prepare 2–3 "starter" project ideas for students who feel stuck.
- [ ] Slow-wifi / API-down backup plan (cached sample JSON responses).

---

## Differentiation (mixed skill levels, ages 14–20)

- **If a student is ahead:** add a second API, add a feature, refactor with the
  AI, or help a peer (teaching reinforces learning).
- **If a student is behind:** pair them up, provide a partly-built starter, and
  focus on understanding one feature deeply rather than many shallowly.
- **Pairing:** mix confidence levels; rotate who "drives" the keyboard.

---

## A Note on "Vibe Coding" Responsibly

The AI writes a lot of the code — and that's fine. The non-negotiable rule of
this course is: **you must be able to explain what your code does.** If you can't,
ask the AI to explain it, until you can. That's the difference between *using* a
tool and being *used by* it.

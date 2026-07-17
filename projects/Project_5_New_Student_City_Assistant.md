# Project 5 — New Student City Assistant *(capstone)*

# Projekt 5 — Stadsassistent för nya studenter *(capstone)*

> **Day 6–7 project guide / Projektguide Dag 6–7**
> This is the **biggest** project. Build a **one-page** city assistant with plain **HTML/CSS/JS** for **GitHub Pages**.
>
> **Scope down for Day 6:** make **Section A (Jobs)** work first. Add transport and stats only if time remains.
>
> Detta är det **största** projektet. Bygg en **ensidig** stadsassistent med ren **HTML/CSS/JS** för **GitHub Pages**.
>
> **Avgränsa för Dag 6:** få **Sektion A (Jobb)** att fungera först. Lägg till transport och statistik bara om tid finns.

---



## What you'll build / Vad du ska bygga

**English**
Pick a Swedish **city**. On one page, show:

1. **Jobs** near that city (JobSearch — no key)
2. **Transport** — main stop + example route (ResRobot — Trafiklab key in an input)
3. **City facts** — population-style snippet (Apiverket — Bearer token in an input)

**Svenska**
Välj en svensk **stad**. På en sida, visa:

1. **Jobb** nära staden (JobSearch — ingen nyckel)
2. **Transport** — huvudhållplats + exempelrutt (ResRobot — Trafiklab-nyckel i ett fält)
3. **Stadsfakta** — befolkningsutdrag (Apiverket — Bearer-token i ett fält)

**User story / Användarberättelse:**

> As a new student in Sweden, I want to choose a city and see jobs, transport options, and useful city data in one place.
> *Som ny student i Sverige vill jag välja en stad och se jobb, transport och användbar stadsdata på ett ställe.*

**Rules / Regler:** one page · no frameworks · never commit API keys · `index.html`

---



## Illustrations / Illustrationer

City Assistant — layout idea ACity Assistant — layout idea BCity Assistant — layout idea C

---



# Part 1 — Build by hand (section by section) /   
Del 1 — Bygg för hand (sektion för sektion)

---



## Step 1 — Create the page shell /   
Steg 1 — Skapa sidans skal

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>New Student City Assistant</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        max-width: 800px;
        margin: 24px auto;
        padding: 0 16px;
        line-height: 1.4;
      }
      section {
        border-top: 1px solid #ccc;
        margin-top: 20px;
        padding-top: 12px;
      }
      input, select { margin-left: 8px; padding: 4px; }
      button { padding: 6px 12px; }
      .item { padding: 8px 0; border-bottom: 1px solid #eee; }
    </style>
  </head>
  <body>
    <h1>New Student City Assistant</h1>
    <p>One place for jobs, transport, and basic city facts.</p>

    <label>
      City
      <select id="city">
        <option>Stockholm</option>
        <option>Göteborg</option>
        <option>Malmö</option>
        <option>Uppsala</option>
        <option>Linköping</option>
        <option>Örebro</option>
        <option>Västerås</option>
      </select>
    </label>
    <br><br>

    <label>
      Trafiklab API key (optional until Section B)
      <input id="trafiklabKey" type="password" autocomplete="off" placeholder="accessId">
    </label>
    <br><br>

    <label>
      Apiverket token (optional until Section C)
      <input id="apiverketToken" type="password" value="sk_test_demo" autocomplete="off">
    </label>
    <br><br>

    <button id="loadBtn">Load city overview</button>
    <p id="status">Choose a city and load the overview.</p>

    <section id="jobsSection">
      <h2>1. Jobs</h2>
      <div id="jobs"></div>
    </section>

    <section id="transportSection">
      <h2>2. Transport</h2>
      <div id="transport"></div>
    </section>

    <section id="factsSection">
      <h2>3. City facts</h2>
      <div id="facts"></div>
    </section>

    <section>
      <h2>Summary</h2>
      <p id="summary"></p>
    </section>

    <script>
      // We will fill this step by step
    </script>
  </body>
</html>
```

---



## Step 2 — Section A: Jobs (core for Day 6) /   
Steg 2 — Sektion A: Jobb (kärna Dag 6)

**English**
This section alone is enough for a successful Day 6 demo if time is short.

**Svenska**
Denna sektion ensam räcker för en lyckad Dag 6-demo om tiden är knapp.

Replace the empty `<script>` with:

```html
<script>
  const JOB_API = "https://jobsearch.api.jobtechdev.se/search";
  const RESROBOT = "https://api.resrobot.se/v2.1";
  const POP_API = "https://apiverket.se/v1/population";

  function getCity() {
    return document.getElementById("city").value;
  }

  async function loadJobs(city) {
    const query = "student " + city;
    const url = JOB_API + "?q=" + encodeURIComponent(query) + "&limit=10";
    const response = await fetch(url);
    if (!response.ok) throw new Error("Jobs API error: " + response.status);
    const data = await response.json();
    return data.hits || [];
  }

  function showJobs(hits) {
    const el = document.getElementById("jobs");
    if (!hits.length) {
      el.innerHTML = "<p>No jobs found for this city search.</p>";
      return;
    }
    let html = "";
    hits.forEach(function (job) {
      const title = job.headline || "No title";
      const employer = (job.employer && job.employer.name) || "Unknown";
      const deadline = job.application_deadline || "Not available";
      const link = job.webpage_url || "";
      html +=
        '<div class="item">' +
        "<p><strong>" + title + "</strong></p>" +
        "<p>" + employer + " · deadline: " + deadline + "</p>" +
        (link ? '<p><a href="' + link + '" target="_blank" rel="noopener">Open ad</a></p>' : "") +
        "</div>";
    });
    el.innerHTML = html;
  }

  async function loadCityOverview() {
    const city = getCity();
    document.getElementById("status").textContent = "Loading jobs for " + city + "…";
    document.getElementById("jobs").innerHTML = "";
    document.getElementById("transport").innerHTML = "<p><em>Section B not loaded yet.</em></p>";
    document.getElementById("facts").innerHTML = "<p><em>Section C not loaded yet.</em></p>";
    document.getElementById("summary").textContent = "";

    try {
      const hits = await loadJobs(city);
      showJobs(hits);
      document.getElementById("status").textContent = "Jobs loaded for " + city + ".";
      document.getElementById("summary").textContent =
        city + ": showing " + hits.length + " student-related job ads. Add transport and facts when ready.";
    } catch (error) {
      console.error(error);
      document.getElementById("status").textContent = error.message || "Failed to load jobs.";
    }
  }

  document.getElementById("loadBtn").addEventListener("click", loadCityOverview);
</script>
```

> ▶️ Test: choose Linköping / Stockholm → Load → jobs appear.
> *Testa: välj Linköping / Stockholm → Ladda → jobb visas.*

---



## Step 3 — Section B: Transport (optional stretch) / Steg 3 — Sektion B: Transport (valfri stretch)

**English**
Needs a Trafiklab key in the input. Look up the city stop, then plan a sample trip to/from Stockholm Central (`740000001`).

**Svenska**
Behöver Trafiklab-nyckel i fältet. Sök stadens hållplats, planera sedan en exempelresa till/från Stockholm Central (`740000001`).

Add these helpers inside your `<script>` (before `loadCityOverview`), then call them from `loadCityOverview` after jobs:

```html
<script>
  // ... keep JOB_API, loadJobs, showJobs from Step 2 ...

  function extractStops(data) {
    const stops = [];
    if (Array.isArray(data.stopLocationOrCoordLocation)) {
      for (const item of data.stopLocationOrCoordLocation) {
        if (item.StopLocation) stops.push(item.StopLocation);
      }
    } else if (Array.isArray(data.StopLocation)) {
      for (const s of data.StopLocation) stops.push(s);
    }
    return stops;
  }

  async function findStop(name, apiKey) {
    const url =
      RESROBOT +
      "/location.name?input=" + encodeURIComponent(name) +
      "&format=json&accessId=" + encodeURIComponent(apiKey);
    const response = await fetch(url);
    if (!response.ok) throw new Error("Stop lookup failed: " + response.status);
    const data = await response.json();
    const stops = extractStops(data);
    if (!stops.length) throw new Error("No stop found for " + name);
    return { name: stops[0].name, extId: stops[0].extId || stops[0].id };
  }

  async function planTrip(originId, destId, apiKey) {
    const url =
      RESROBOT +
      "/trip?format=json&originId=" + encodeURIComponent(originId) +
      "&destId=" + encodeURIComponent(destId) +
      "&passlist=true&accessId=" + encodeURIComponent(apiKey);
    const response = await fetch(url);
    if (!response.ok) throw new Error("Trip failed: " + response.status);
    return response.json();
  }

  async function loadTransport(city) {
    const apiKey = document.getElementById("trafiklabKey").value.trim();
    const el = document.getElementById("transport");
    if (!apiKey) {
      el.innerHTML = "<p>Paste a Trafiklab key to load transport.</p>";
      return null;
    }

    const stop = await findStop(city, apiKey);
    // Example route: city stop → Stockholm Central (or reverse if city is Stockholm)
    const stockholmId = "740000001";
    const originId = stop.extId === stockholmId ? stop.extId : stop.extId;
    const destId = stop.extId === stockholmId ? "740000003" : stockholmId; // Malmö if already Stockholm
    const tripData = await planTrip(originId, destId, apiKey);

    let trips = tripData.Trip;
    if (!trips) {
      el.innerHTML = "<p>Stop found, but no trip options.</p>";
      return stop;
    }
    if (!Array.isArray(trips)) trips = [trips];
    const trip = trips[0];
    const origin = trip.Origin || {};
    const destination = trip.Destination || {};

    el.innerHTML =
      "<p><strong>Main stop:</strong> " + stop.name + " (extId: " + stop.extId + ")</p>" +
      "<p><strong>Example route:</strong> " + (origin.name || "") + " → " + (destination.name || "") + "</p>" +
      "<p><strong>Departure:</strong> " + (origin.time || "") + " · <strong>Arrival:</strong> " + (destination.time || "") + "</p>" +
      "<p><strong>Duration:</strong> " + (trip.duration || "n/a") + "</p>";

    return stop;
  }
</script>
```

Update `loadCityOverview` to also await `loadTransport(city)` inside try (wrap in its own try/catch so jobs still show if transport fails).

---



## Step 4 — Section C: City facts (optional) /   
Steg 4 — Sektion C: Stadsfakta (valfritt)

```html
<script>
  async function loadFacts(city) {
    const token = document.getElementById("apiverketToken").value.trim();
    const el = document.getElementById("facts");
    if (!token) {
      el.innerHTML = "<p>Paste an Apiverket token to load facts.</p>";
      return;
    }

    const response = await fetch(POP_API, {
      headers: { Authorization: "Bearer " + token }
    });
    if (!response.ok) throw new Error("Facts API error: " + response.status);
    const payload = await response.json();
    console.log("population payload", payload);

    // Flexible match: find a row whose name contains the city
    let rows = payload.data;
    if (!Array.isArray(rows)) rows = [];
    const match = rows.find(function (row) {
      const text = JSON.stringify(row).toLowerCase();
      return text.indexOf(city.toLowerCase()) !== -1;
    });

    if (match) {
      el.innerHTML =
        "<p>Found a data row related to <strong>" + city + "</strong>.</p>" +
        "<pre>" + JSON.stringify(match, null, 2) + "</pre>" +
        "<p>Interpret one number from this row in your summary.</p>";
    } else {
      el.innerHTML =
        "<p>Loaded population dataset, but no obvious row for " + city + ".</p>" +
        "<p>Open the Console, inspect <code>data</code>, and adapt this section (or describe the dataset generally).</p>";
    }
  }
</script>
```

---



## Step 5 — Wire all sections + summary /   
Steg 5 — Koppla alla sektioner + sammanfattning

Final `loadCityOverview` pattern:

```javascript
async function loadCityOverview() {
  const city = getCity();
  document.getElementById("status").textContent = "Loading overview for " + city + "…";
  document.getElementById("jobs").innerHTML = "";
  document.getElementById("transport").innerHTML = "";
  document.getElementById("facts").innerHTML = "";

  let jobCount = 0;
  let transportNote = "not loaded";
  let factsNote = "not loaded";

  try {
    const hits = await loadJobs(city);
    jobCount = hits.length;
    showJobs(hits);
  } catch (e) {
    document.getElementById("jobs").innerHTML = "<p>" + e.message + "</p>";
  }

  try {
    const stop = await loadTransport(city);
    transportNote = stop ? stop.name : "skipped/failed";
  } catch (e) {
    document.getElementById("transport").innerHTML = "<p>" + e.message + "</p>";
    transportNote = "error";
  }

  try {
    await loadFacts(city);
    factsNote = "loaded";
  } catch (e) {
    document.getElementById("facts").innerHTML = "<p>" + e.message + "</p>";
    factsNote = "error";
  }

  document.getElementById("status").textContent = "Overview finished for " + city + ".";
  document.getElementById("summary").textContent =
    city + " overview — jobs: " + jobCount +
    "; transport: " + transportNote +
    "; facts: " + factsNote +
    ". This assistant helps new students explore a Swedish city in one page.";
}
```

---



## Step 6 — Test plan /   
Steg 6 — Testplan


| Goal       | Minimum success                           |
| ---------- | ----------------------------------------- |
| Day 6 core | Jobs section works for 2 cities           |
| Stretch    | Transport works with pasted Trafiklab key |
| Stretch    | Facts section loads Apiverket JSON        |
| Always     | No keys hard-coded in the file you push   |


---



# Part 2 — Improve it with AI (Cline) /   
Del 2 — Förbättra den med AI (Cline)

**English**
Now that the core works, use **Cline** in VS Code to improve the page — **one change at a time**. Prefer improving **one section at a time** (Jobs → Transport → Facts). Keep it a **single static page** suitable for **GitHub Pages** (no React, Vue, Angular, no npm, no backend).

**Svenska**
Nu när kärnan fungerar, använd **Cline** i VS Code för att förbättra sidan — **en ändring i taget**. Förbättra helst **en sektion i taget** (Jobb → Transport → Fakta). Behåll en **ensidig statisk sida** som passar **GitHub Pages** (ingen React, Vue, Angular, inget npm, ingen backend).

**How to work / Så här jobbar du:**

1. Open your `index.html` in VS Code.
2. Open the **Cline** chat (left sidebar).
3. Paste **one** prompt below.
4. **Read** the change → Accept only if you understand it → Test in the browser.
5. If something breaks, Undo and try a clearer prompt.

> 🏅 **Golden rule:** You must be able to explain what the AI changed.
> *Gyllene regel: Du måste kunna förklara vad AI:n ändrade.*
>
> ⚠️ Remind Cline every time: keys stay in input fields only — never hard-code Trafiklab or Apiverket secrets.

---



## Sample prompts — Design & layout /   
Exempel-prompts — Design & layout

```text
Improve the visual design of my New Student City Assistant using only CSS in the
same index.html file. Keep all existing JavaScript behavior. Make it look like a
clear dashboard with a title, city selector, optional key fields, a short summary
area, and three numbered sections (1 Jobs, 2 Transport, 3 City facts) with spacing
and readable fonts.
This app must stay publishable on GitHub Pages as one static HTML file.
Do not add React, Vue, npm, or any framework.
Explain each CSS change with a short comment.
```

```text
Improve the mobile layout: stack the city selector, key inputs, and Load button
vertically on small screens; make inputs and buttons full-width; keep section
cards readable. Use only CSS media queries.
Must remain GitHub Pages–ready — one index.html, no frameworks.
```

```text
Style each of the three sections as a simple bordered block with a clear heading
and padding. Make the summary area stand out slightly more than the sections.
Plain CSS only in index.html for GitHub Pages. No frameworks.
```

```text
Add a soft page background and style the main heading and status/progress message
more clearly. Keep everything in one index.html. No npm or frameworks.
```

---



## Sample prompts — User experience /   
Exempel-prompts — Användarupplevelse

```text
When loading a city overview, update #status step by step:
"1/3 Loading jobs…", then "2/3 Loading transport…", then "3/3 Loading facts…", then "Done" (or stop early if Jobs-only mode is on). Keep plain JavaScript. Do not add frameworks. Must stay publishable on GitHub Pages as one static file.
```

```text
If the Trafiklab accessId input is empty, still load Jobs and Facts successfully, and in the Transport section only show a friendly note: "Add a Trafiklab key to unlock routes (optional)."
Do not break the Jobs section. Never hard-code an API key.
One index.html for GitHub Pages — no frameworks.
```

```text
Add a "Jobs only" button next to Load city that loads only the Jobs section (skips transport and facts) for faster demos. Keep the full Load city button too.
Explain the difference with short comments. Plain HTML/CSS/JS for GitHub Pages — no frameworks.
```

```text
Disable Load city / Jobs only while a load is in progress, and re-enable when finished (success or partial failure). Plain JavaScript only.
GitHub Pages–compatible: one static file, no frameworks.
```

```text
When I change the city in the selector, clear previous results and reset status to "Choose Load city when ready" so old Stockholm data is not mixed with Uppsala.
Keep one index.html for GitHub Pages. No frameworks.
```

---



## Sample prompts — Extra features / Exempel-prompts — Extrafunktioner

```text
In the Jobs section, add a small dropdown for query type with options: student, deltid, IT — and search JobSearch with that word plus the selected city (e.g. "student Stockholm"). Keep limit around 10. Plain JS only.
Must remain one static HTML file for GitHub Pages. No frameworks.
```

```text
In the Transport section, list up to 3 trip options instead of only one. For each option show a short summary (e.g. duration and number of legs if available in the
ResRobot response). If the key is missing, keep the friendly unlock message.
Never hard-code the Trafiklab key. One index.html for GitHub Pages — no frameworks.
Explain the new loop with short comments.
```

```text
In the City facts section, if a matching city/municipality row is found, highlight one main number (e.g. population) in larger text and add one short sentence of
interpretation under it (simple, student-written tone). Keep Apiverket token in the input field only — never hard-code it.
Plain HTML/CSS/JS for GitHub Pages. No frameworks.
```

```text
Add a plain-language "Welcome to {city}" summary near the top that combines:
job count from the Jobs section + stop/route note from Transport (if available) + one fact number (if available). Update it after each successful section load.
Keep one static file publishable on GitHub Pages. No frameworks.
```

```text
Add a "Clear all" button that clears summary + all three sections + status, without reloading the page. Do not clear the key input values unless I ask. Plain JS only — GitHub Pages–ready, no frameworks.
```

---



## Sample prompts — Security & language / Exempel-prompts — Säkerhet & språk

```text
Under the Trafiklab and Apiverket key fields, add a bilingual security reminder (EN + SV): never commit API keys to GitHub; paste them only in the browser inputs.
Do not change fetch logic. Keep one index.html for GitHub Pages. No frameworks.
```

```text
Make section titles bilingual: Jobs / Jobb, Transport / Transport, City facts / Stadsfakta, and Load city / Ladda stad. Keep one HTML file. Must stay GitHub Pages–compatible — no frameworks.
```

```text
Improve accessibility: labels with for/id for city and key inputs, clear button text, and a status area that is easy to find. Plain HTML/CSS/JS for GitHub Pages.
```

```text
Add a short "About this app" paragraph under the title: this is a student City Assistant for new students in Sweden; Jobs use the open JobSearch API; Transport
and Facts are optional and need keys pasted only in inputs; publishable on GitHub Pages as one static file. Do not hard-code secrets. No frameworks.
```

---



## Sample prompts — Code quality / Exempel-prompts — Kodkvalitet

```text
Refactor my script into small named functions:
loadJobs, loadTransport, loadFacts, updateSummary, loadCityOverview. Keep the same behavior. Add short comments above each function. Do not introduce frameworks. Must remain one static index.html for GitHub Pages.
Never hard-code API keys.
```

```text
Strengthen independent failure handling: if Transport fails, Jobs and Facts should still show; if Facts fails, Jobs should still show. Put a clear error message only
inside the failed section. Plain JS only for GitHub Pages. No frameworks.
```

```text
Review my code for simple bugs (missing city, empty keys, mixed old results, broken links) and fix them carefully. Keep one static HTML file for GitHub Pages.
Never hard-code Trafiklab or Apiverket keys into the source.
```

---



## Publish checklist / Publiceringschecklista

**English**

1. Jobs work without any keys.
2. No real Trafiklab/Apiverket secrets in source — only empty inputs or placeholders.
3. Push `index.html` to a **public** GitHub repository.
4. Enable **GitHub Pages** and test the live URL.
5. Demo script: jobs first, then optional sections.

**Svenska**

1. Jobb fungerar utan nycklar.
2. Inga riktiga Trafiklab-/Apiverket-hemligheter i källkoden.
3. Push:a `index.html` till ett **offentligt** GitHub-repo.
4. Slå på **GitHub Pages** och testa live-URL:en.
5. Demo: jobb först, sedan valfria sektioner.



## Demo tips (3 min) / Demotips (3 min)

- Select city → show jobs  
- (If ready) paste Trafiklab key → show one route  
- Explain why the project is scoped in sections  
- One Cline improvement



## API reference

```text
Jobs:      GET https://jobsearch.api.jobtechdev.se/search?q=student+CITY&limit=10
Transport: GET https://api.resrobot.se/v2.1/location.name?...&accessId=KEY
           GET https://api.resrobot.se/v2.1/trip?...&accessId=KEY
Facts:     GET https://apiverket.se/v1/population
           Authorization: Bearer TOKEN
```

---

*Part of teknikkurs26 — Sudanese Association*
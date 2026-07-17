# Project 1 — Job Finder for Sudanese Students in Sweden

# Projekt 1 — Jobbsökare för sudanesiska studenter i Sverige

> **Day 6–7 project guide / Projektguide Dag 6–7**
> Build a **one-page** job search app with plain **HTML, CSS, and JavaScript** — no frameworks (React, Vue, etc.). You will publish it on **GitHub Pages**, so keep everything in one `index.html` file (or a few simple files in the same folder).
>
> Bygg en **ensidig** jobbsökningsapp med ren **HTML, CSS och JavaScript** — inga ramverk (React, Vue, osv.). Du ska publicera den på **GitHub Pages**, så håll allt i en `index.html`-fil (eller några enkla filer i samma mapp).

---

## What you'll build / Vad du ska bygga

**English**
A simple page where a student types a **keyword** (e.g. `deltid`) and a **city** (e.g. `Stockholm`), presses **Search**, and sees a list of real Swedish job ads from Arbetsförmedlingen's open JobSearch API.

**Svenska**
En enkel sida där en student skriver ett **sökord** (t.ex. `deltid`) och en **stad** (t.ex. `Stockholm`), trycker **Sök**, och ser en lista med riktiga svenska jobbannonser från Arbetsförmedlingens öppna JobSearch-API.

**User story / Användarberättelse:**

> As a student in Sweden, I want to search for beginner-friendly jobs in my city, so I can quickly find relevant work opportunities.
> *Som student i Sverige vill jag söka efter nybörjarvänliga jobb i min stad, så att jag snabbt hittar relevanta möjligheter.*

**Rules for GitHub Pages / Regler för GitHub Pages:**

- One-page app / Ensidig app
- Plain HTML/CSS/JS only / Bara ren HTML/CSS/JS
- No build tools, no npm, no frameworks / Inga byggverktyg, inget npm, inga ramverk
- File must be named `index.html` / Filen måste heta `index.html`
- No API key needed for this project / Ingen API-nyckel behövs för detta projekt

**You need / Du behöver:** VS Code + a browser + a GitHub account *(for publishing later)*

---

## Illustrations / Illustrationer

*Example layouts — inspiration only. Build a simple version first!*
*Exempel-layouts — bara inspiration. Bygg en enkel version först!*

Job Finder — layout idea AJob Finder — layout idea BJob Finder — layout idea C

---

# Part 1 — Build a simple version by hand /  
Del 1 — Bygg en enkel version för hand

> Goal: a working search page with **very little CSS**. Understand every line before you ask the AI to improve it.
> Mål: en fungerande söksida med **väldigt lite CSS**. Förstå varje rad innan du ber AI:n förbättra den.

---

## Step 1 — See the API in the browser /   
Steg 1 — Se API:et i webbläsaren

**English**
Before coding, open this URL in your browser and press Enter:

**Svenska**
Innan du kodar, öppna denna URL i webbläsaren och tryck Enter:

```text
https://jobsearch.api.jobtechdev.se/search?q=deltid%20stockholm&limit=5
```

**What you should notice / Vad du ska lägga märke till:**

- The jobs live in an array called `**hits**` — *jobben ligger i en array som heter `**hits**`*
- Useful fields / Användbara fält:
  - `headline` — job title / jobbtitel
  - `employer.name` — company / företag
  - `workplace_address.municipality` — city / stad
  - `publication_date` — when it was published / när den publicerades
  - `application_deadline` — deadline (sometimes missing) / deadline (saknas ibland)
  - `webpage_url` — link to the full ad / länk till hela annonsen
  - `id` — the job id / jobbets id

> Tip: try also `q=python%20stockholm` and `q=sommarjobb%20uppsala`.
> *Tips: prova också `q=python%20stockholm` och `q=sommarjobb%20uppsala`.*

---

## Step 2 — Create the project file / Steg 2 — Skapa projektfilen

**English**

1. In VS Code, create a folder, e.g. `job-finder`.
2. Create a file named `**index.html**` (this name is required for GitHub Pages).
3. Type this skeleton:

**Svenska**

1. I VS Code, skapa en mapp, t.ex. `job-finder`.
2. Skapa en fil som heter `**index.html**` (det namnet krävs för GitHub Pages).
3. Skriv denna grundram:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Job Finder</title>
  </head>
  <body>
    <!-- content goes here -->
  </body>
</html>
```

---

## Step 3 — Add the page structure (HTML) / Steg 3 — Lägg till sidstrukturen (HTML)

**English**
Replace the comment inside `<body>` with this. Keep it simple — no fancy layout yet:

**Svenska**
Ersätt kommentaren inuti `<body>` med detta. Håll det enkelt — ingen fin layout än:

```html
<h1>Job Finder for Students in Sweden</h1>
<p>Search for part-time jobs, summer jobs, and beginner roles.</p>

<label>
  Keyword
  <input id="keyword" type="text" value="deltid" placeholder="e.g. deltid, python, sommarjobb">
</label>
<br><br>

<label>
  City
  <input id="city" type="text" value="stockholm" placeholder="e.g. stockholm, uppsala">
</label>
<br><br>

<button id="searchBtn">Search</button>

<p id="status">Type a keyword and city, then press Search.</p>
<div id="results"></div>
```

> 💾 Save and open with Live Server (or double-click the file). You should see the form — nothing happens yet when you click Search.
> *Spara och öppna med Live Server (eller dubbelklicka). Du ska se formuläret — inget händer än när du klickar Sök.*

---

## Step 4 — Add a tiny bit of CSS / Steg 4 — Lägg till en liten bit CSS

**English**
Add this inside `<head>` — just enough to make the page readable. We improve the design in Part 2.

**Svenska**
Lägg till detta inuti `<head>` — bara så sidan blir läsbar. Vi förbättrar designen i Del 2.

```html
<style>
  body {
    font-family: Arial, sans-serif;
    max-width: 700px;
    margin: 24px auto;
    padding: 0 16px;
    line-height: 1.4;
  }
  input { margin-left: 8px; padding: 4px; }
  button { padding: 6px 12px; }
  .job {
    border-top: 1px solid #ccc;
    padding: 12px 0;
  }
</style>
```

---

## Step 5 — Fetch jobs and log them / Steg 5 — Hämta jobb och logga dem

**English**
Add this `<script>` just before `</body>`. First we only **fetch** and **console.log** — like Day 3.

**Svenska**
Lägg till detta `<script>` precis före `</body>`. Först **hämtar** vi och **console.log**:ar bara — som på Dag 3.

```html
<script>
  const API = "https://jobsearch.api.jobtechdev.se/search";

  async function searchJobs() {
    const keyword = document.getElementById("keyword").value.trim();
    const city = document.getElementById("city").value.trim();
    const query = (keyword + " " + city).trim();

    if (!query) {
      document.getElementById("status").textContent = "Please enter a keyword or a city.";
      return;
    }

    document.getElementById("status").textContent = "Searching…";

    try {
      const url = API + "?q=" + encodeURIComponent(query) + "&limit=10";
      const response = await fetch(url);
      if (!response.ok) {
        throw new Error("API error: " + response.status);
      }
      const data = await response.json();
      console.log(data); // inspect the full response
      document.getElementById("status").textContent =
        "Got " + data.hits.length + " jobs (see Console). Total found: " + data.total.value;
    } catch (error) {
      console.error(error);
      document.getElementById("status").textContent = "Something went wrong. Try again.";
    }
  }

  document.getElementById("searchBtn").addEventListener("click", searchJobs);
</script>
```

**English**
Save, refresh, click **Search**, then open the Console (`F12` → Console). You should see an object with a `hits` array.

**Svenska**
Spara, ladda om, klicka **Search**, öppna sedan Console (`F12` → Console). Du ska se ett objekt med en `hits`-array.

---

## Step 6 — Show the jobs on the page / Steg 6 — Visa jobben på sidan

**English**
Add a function that turns each job into simple HTML, then call it after a successful fetch. Replace the success part of `searchJobs` and add `showJobs`:

**Svenska**
Lägg till en funktion som gör varje jobb till enkel HTML, och anropa den efter en lyckad hämtning. Ersätt success-delen i `searchJobs` och lägg till `showJobs`:

```html
<script>
  const API = "https://jobsearch.api.jobtechdev.se/search";

  function showJobs(hits) {
    const results = document.getElementById("results");
    results.innerHTML = "";

    if (!hits || hits.length === 0) {
      document.getElementById("status").textContent = "No jobs found. Try another keyword or city.";
      return;
    }

    document.getElementById("status").textContent = "Showing " + hits.length + " jobs:";

    for (const job of hits) {
      const title = job.headline || "No title";
      const employer = (job.employer && job.employer.name) || "Unknown employer";
      const city = (job.workplace_address && job.workplace_address.municipality) || "Unknown city";
      const published = job.publication_date || "Not available";
      const deadline = job.application_deadline || "Not available";
      const link = job.webpage_url || "";

      const div = document.createElement("div");
      div.className = "job";
      div.innerHTML =
        "<h2>" + title + "</h2>" +
        "<p><strong>Employer:</strong> " + employer + "</p>" +
        "<p><strong>City:</strong> " + city + "</p>" +
        "<p><strong>Published:</strong> " + published + "</p>" +
        "<p><strong>Deadline:</strong> " + deadline + "</p>" +
        (link ? '<p><a href="' + link + '" target="_blank" rel="noopener">Open job ad</a></p>' : "");

      results.appendChild(div);
    }
  }

  async function searchJobs() {
    const keyword = document.getElementById("keyword").value.trim();
    const city = document.getElementById("city").value.trim();
    const query = (keyword + " " + city).trim();

    if (!query) {
      document.getElementById("status").textContent = "Please enter a keyword or a city.";
      return;
    }

    document.getElementById("status").textContent = "Searching…";
    document.getElementById("results").innerHTML = "";

    try {
      const url = API + "?q=" + encodeURIComponent(query) + "&limit=10";
      const response = await fetch(url);
      if (!response.ok) {
        throw new Error("API error: " + response.status);
      }
      const data = await response.json();
      console.log(data);
      showJobs(data.hits);
    } catch (error) {
      console.error(error);
      document.getElementById("status").textContent = "Something went wrong. Try again.";
    }
  }

  document.getElementById("searchBtn").addEventListener("click", searchJobs);
</script>
```

> ▶️ Save, refresh, search for `deltid` + `stockholm`. Real job ads should appear!
> *Spara, ladda om, sök `deltid` + `stockholm`. Riktiga jobbannonser ska dyka upp!*

---

## Step 7 — Test your core features / Steg 7 — Testa dina kärnfunktioner

**English** — Try these searches and confirm they work:

**Svenska** — Prova dessa sökningar och bekräfta att de fungerar:


| Search / Sökning           | What to check / Vad du ska kolla   |
| -------------------------- | ---------------------------------- |
| `deltid` + `stockholm`     | Several part-time jobs appear      |
| `python` + `stockholm`     | Different titles appear            |
| `sommarjobb` + `uppsala`   | Results for Uppsala                |
| empty keyword + empty city | Friendly “enter something” message |
| nonsense word + city       | “No jobs found” message            |


---

## The complete simple page / Den kompletta enkla sidan

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Job Finder</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        max-width: 700px;
        margin: 24px auto;
        padding: 0 16px;
        line-height: 1.4;
      }
      input { margin-left: 8px; padding: 4px; }
      button { padding: 6px 12px; }
      .job {
        border-top: 1px solid #ccc;
        padding: 12px 0;
      }
    </style>
  </head>
  <body>
    <h1>Job Finder for Students in Sweden</h1>
    <p>Search for part-time jobs, summer jobs, and beginner roles.</p>

    <label>
      Keyword
      <input id="keyword" type="text" value="deltid" placeholder="e.g. deltid, python, sommarjobb">
    </label>
    <br><br>

    <label>
      City
      <input id="city" type="text" value="stockholm" placeholder="e.g. stockholm, uppsala">
    </label>
    <br><br>

    <button id="searchBtn">Search</button>

    <p id="status">Type a keyword and city, then press Search.</p>
    <div id="results"></div>

    <script>
      const API = "https://jobsearch.api.jobtechdev.se/search";

      function showJobs(hits) {
        const results = document.getElementById("results");
        results.innerHTML = "";

        if (!hits || hits.length === 0) {
          document.getElementById("status").textContent = "No jobs found. Try another keyword or city.";
          return;
        }

        document.getElementById("status").textContent = "Showing " + hits.length + " jobs:";

        for (const job of hits) {
          const title = job.headline || "No title";
          const employer = (job.employer && job.employer.name) || "Unknown employer";
          const city = (job.workplace_address && job.workplace_address.municipality) || "Unknown city";
          const published = job.publication_date || "Not available";
          const deadline = job.application_deadline || "Not available";
          const link = job.webpage_url || "";

          const div = document.createElement("div");
          div.className = "job";
          div.innerHTML =
            "<h2>" + title + "</h2>" +
            "<p><strong>Employer:</strong> " + employer + "</p>" +
            "<p><strong>City:</strong> " + city + "</p>" +
            "<p><strong>Published:</strong> " + published + "</p>" +
            "<p><strong>Deadline:</strong> " + deadline + "</p>" +
            (link ? '<p><a href="' + link + '" target="_blank" rel="noopener">Open job ad</a></p>' : "");

          results.appendChild(div);
        }
      }

      async function searchJobs() {
        const keyword = document.getElementById("keyword").value.trim();
        const city = document.getElementById("city").value.trim();
        const query = (keyword + " " + city).trim();

        if (!query) {
          document.getElementById("status").textContent = "Please enter a keyword or a city.";
          return;
        }

        document.getElementById("status").textContent = "Searching…";
        document.getElementById("results").innerHTML = "";

        try {
          const url = API + "?q=" + encodeURIComponent(query) + "&limit=10";
          const response = await fetch(url);
          if (!response.ok) {
            throw new Error("API error: " + response.status);
          }
          const data = await response.json();
          console.log(data);
          showJobs(data.hits);
        } catch (error) {
          console.error(error);
          document.getElementById("status").textContent = "Something went wrong. Try again.";
        }
      }

      document.getElementById("searchBtn").addEventListener("click", searchJobs);
    </script>
  </body>
</html>
```

> ✅ **Part 1 done** when search works, results show, and you can explain your code.
> ***Del 1 klar** när sökningen fungerar, resultaten visas, och du kan förklara din kod.*

---

# Part 2 — Improve it with AI (Cline)

# Del 2 — Förbättra den med AI (Cline)

**English**
Now that the core works, use **Cline** in VS Code to improve the page — **one change at a time**. Keep it a **single static page** suitable for GitHub Pages (no React, no npm, no backend).

**Svenska**
Nu när kärnan fungerar, använd **Cline** i VS Code för att förbättra sidan — **en ändring i taget**. Behåll en **ensidig statisk sida** som passar GitHub Pages (ingen React, inget npm, ingen backend).

**How to work / Så här jobbar du:**

1. Open your `index.html` in VS Code.
2. Open the **Cline** chat (left sidebar).
3. Paste **one** prompt below.
4. **Read** the change → Accept only if you understand it → Test in the browser.
5. If something breaks, Undo and try a clearer prompt.

> 🏅 **Golden rule:** You must be able to explain what the AI changed.
> *Gyllene regel: Du måste kunna förklara vad AI:n ändrade.*
>
> ⚠️ Remind Cline: *"Keep this as one plain HTML/CSS/JS file for GitHub Pages. Do not add frameworks or build tools."*
> *Påminn Cline: "Behåll detta som en ren HTML/CSS/JS-fil för GitHub Pages. Lägg inte till ramverk eller byggverktyg."*

---

## Sample prompts — Design & layout / Exempel-prompts — Design & layout

```text
Improve the visual design of my Job Finder page using only CSS in the same index.html file. Keep all existing JavaScript behavior. Use a clean, simple student-friendly look: clearer spacing, readable fonts, and a max-width layout. Do not add frameworks. Explain each CSS change with a short comment.
```

```text
Turn each job result into a simple card with a light border, padding, and rounded corners. Keep the page as plain HTML/CSS/JS for GitHub Pages.
```

```text
Make the search form look nicer: put keyword, city, and the Search button in one horizontal row on desktop, and stack them on small screens using only CSS (flexbox or simple media queries). No frameworks.
```

```text
Add a soft page background color and style the main heading and status message more clearly. Keep everything in one index.html file.
```

```text
Improve mobile readability: make inputs and the button full-width on small screens, increase tap size, and keep text readable. Plain CSS only.
```

---

## Sample prompts — User experience / Exempel-prompts — Användarupplevelse

```text
When I press Enter in the keyword or city input, run the same search as the Search button. Keep plain HTML/CSS/JS. Explain the change.
```

```text
Disable the Search button while a request is loading, and enable it again when the request finishes (success or error). Plain JavaScript only.
```

```text
Show a clearer loading message, for example "Searching jobs in Stockholm…", using the city the user typed. Do not change the API call.
```

```text
If no jobs are found, show a friendly empty-state message with 2 example searches the user can try (deltid stockholm, sommarjobb uppsala).
```

```text
Format publication_date and application_deadline as short readable dates (YYYY-MM-DD is fine). If a deadline is missing, show "Not available".
```

---

## Sample prompts — Extra features / Exempel-prompts — Extrafunktioner

```text
Add a number input for "Max results" (default 10, min 1, max 30) and pass it as the limit query parameter to the JobSearch API. Keep one index.html file.
```

```text
Above the job list, show a short summary: total jobs returned on this page, and list up to 3 unique cities found in the results.
```

```text
Add a "Clear" button that empties the results area and resets the status message, without reloading the page.
```

```text
Sort the displayed jobs by publication_date (newest first) after fetching.
Explain the sorting code with short comments.
```

```text
Add a checkbox "Only show jobs with a deadline" that filters the current results on the page (client-side filter after fetch). Plain JS only.
```

```text
When the user clicks a job title, expand/collapse a short extra line showing the job id. Do not add a second page or a framework.
```

---

## Sample prompts — Language & accessibility / Exempel-prompts — Språk & tillgänglighet

```text
Make the page bilingual: show labels in English and Swedish
(e.g. Keyword / Sökord, City / Stad, Search / Sök). Keep one HTML file.
```

```text
Improve accessibility: associate labels with inputs using for/id, ensure buttons have clear text, and make sure status messages are easy to find. Plain HTML/CSS/JS only.
```

```text
Add Arabic translations for the main labels and the Search button, while keeping English as well. Do not change the JavaScript search logic.
```

```text
Add a short "About this app" paragraph under the title explaining that data comes from Arbetsförmedlingen's open JobSearch API and that this is a student
project.
```

---

## Sample prompts — Code quality / Exempel-prompts — Kodkvalitet

```text
Refactor my script into small named functions (getSearchQuery, buildUrl, fetchJobs, showJobs, showStatus). Keep the same behavior. Add short comments.
Do not introduce frameworks.
```

```text
Add short comments above each function explaining what it does, so I can explain the code to my teacher. Do not change behavior.
```

```text
Review my code for simple bugs (empty search, missing fields, broken links) and fix them carefully. Keep one static HTML file for GitHub Pages.
```

---

## After improvements — Publish checklist / Efter förbättringar — Publiceringschecklista

**English**

1. Confirm everything still works in the browser.
2. Make sure there is **no API key** in the file (this API needs none).
3. Push `index.html` to a **public** GitHub repository.
4. Turn on **GitHub Pages** (Settings → Pages → branch `main` / root).
5. Open `https://YOUR-USERNAME.github.io/REPO-NAME/` and test search live.

**Svenska**

1. Bekräfta att allt fortfarande fungerar i webbläsaren.
2. Se till att det **inte finns någon API-nyckel** i filen (detta API behöver ingen).
3. Push:a `index.html` till ett **offentligt** GitHub-repository.
4. Slå på **GitHub Pages** (Settings → Pages → branch `main` / root).
5. Öppna `https://DITT-ANVÄNDARNAMN.github.io/REPO-NAMN/` och testa sökningen live.

---

## Demo tips (3 minutes) / Demotips (3 minuter)

**English**

- Show one successful search (`deltid stockholm`).
- Show one empty / error case.
- Open one job link.
- Explain: input → build URL → `fetch` → `hits` → show on page.
- Mention one improvement you made with Cline.

**Svenska**

- Visa en lyckad sökning (`deltid stockholm`).
- Visa ett tomt / felläge.
- Öppna en jobblänk.
- Förklara: inmatning → bygg URL → `fetch` → `hits` → visa på sidan.
- Nämn en förbättring du gjorde med Cline.

---

## API reference (quick) / API-referens (snabb)

```text
GET https://jobsearch.api.jobtechdev.se/search?q=KEYWORD+CITY&limit=10
```

Main fields / Huvudfält: `hits[]`, `headline`, `employer.name`, `workplace_address.municipality`, `publication_date`, `application_deadline`, `webpage_url`, `id`

Optional later / Valfritt senare: `GET /ad/{id}` for full details of one job.

---

*Part of teknikkurs26 — Summer Coding Course for Youth · Sudanese Association*
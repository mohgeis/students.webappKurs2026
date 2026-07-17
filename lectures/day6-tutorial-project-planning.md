# Tutorial — Project Design & Plan (Group Work)

# Handledning — Projektdesign & plan (grupparbete)

> **Day 6 breakout activity (~~20–30 minutes) / Dag 6 grupparbete (~~20–30 minuter)**
> Before you start coding, your group will **design and plan** your app together. Each breakout room has a **teacher** to help you think — not to decide for you. Work through the steps below **in order**. Write your answers on paper or in a shared doc.
>
> **Most students** will pick a project from the `**projects/`** folder — but you are **free to bring your own idea** if you prefer.
>
> Innan ni börjar koda ska gruppen **designa och planera** er app tillsammans. Varje grupprum har en **lärare** som hjälper er tänka — inte bestämmer åt er. Gå igenom stegen nedan **i ordning**. Skriv ner era svar på papper eller i ett delat dokument.
>
> **De flesta elever** väljer ett projekt från mappen `**projects/`** — men ni får **gärna ta med en egen idé** om ni vill.

---

## How this works / Så här fungerar det

**English**

- You are in a **breakout room** with your group + **one teacher**.
- This is **discussion first, coding later** — a good plan saves you hours of confusion.
- **Everyone speaks** — share ideas, disagree politely, decide together.
- One person is the **scribe** (writes the plan). One person is the **spokesperson** (shares in the main room later).
- Target time: **20–30 minutes** for Steps 1–8. If you finish early, refine your build order (Step 7).

**Svenska**

- Ni sitter i ett **grupprum** med ert lag + **en lärare**.
- Det här är **diskussion först, kodning sen** — en bra plan sparar timmar av förvirring.
- **Alla pratar** — dela idéer, var oense artigt, bestäm tillsammans.
- En person är **sekreterare** (skriver planen). En person är **talesperson** (delar i huvudrummet senare).
- Måltid: **20–30 minuter** för steg 1–8. Om ni blir klara tidigt, förbättra er byggordning (steg 7).

---

## Step 1 — Start with an idea (3 min) / Steg 1 — Börja med en idé

**English** — Discuss:

1. **Option A (most common):** Open the `**projects/`** folder and read the briefs. Pick **one** project as your starting point — then **adapt it** (change the focus, drop features, make it smaller).
2. **Option B:** Bring **your own idea** — that's fine too! Describe it in **one sentence**.
3. If several people have ideas, **vote** — or combine the best parts into one **small** app.

**Ready-made project briefs / Färdiga projektbeskrivningar** *(in `projects/`)*:


| #     | Project / Projekt                                                       | In one line / I korthet                                                                                                              |
| ----- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | Job Finder for Sudanese Students / Jobbsökare för sudanesiska studenter | Search part-time jobs by keyword and city / Sök extrajobb med sökord och stad                                                        |
| **2** | Public Transport Route Planner / Kollektivtrafik-ruttplanerare          | Plan a route between two stops/places / Planera rutt mellan två hållplatser                                                          |
| **3** | Sweden Statistics Explorer / Sverigestatistik-utforskare                | Compare municipalities with real Swedish data / Jämför kommuner med riktig svensk data                                               |
| **4** | Career Path Recommender / Karriärvägs-rekommendation                    | Enter skills → see matching job titles / Skriv in färdigheter → se matchande jobbtitlar                                              |
| **5** | New Student City Assistant / Stadsassistent för nya studenter           | Jobs + transport + stats for one city *(capstone — scope down!)* / Jobb + transport + statistik för en stad *(capstone — avgränsa!)* |
| **6** | Crypto Price Checker / Kryptopris-koll                                  | Search a coin → price in SEK/USD + 24h change *(educational only!)* / Sök mynt → pris i SEK/USD + 24h *(bara utbildning!)*           |


> 📄 Each file in `projects/` has the **API links**, user story, and suggested build steps — read yours before Step 4.
> *Varje fil i `projects/` har **API-länkar**, user story och föreslagna byggsteg — läs er fil före steg 4.*
>
> ⚠️ **Project 5** combines three APIs — treat it as a **big** idea and pick **one part** for today's core (e.g. jobs only, or transport only).
> ***Projekt 5** kombinerar tre API:er — behandla det som en **stor** idé och välj **en del** som dagens kärna (t.ex. bara jobb, eller bara transport).*
>
> ⚠️ **Project 6** is for learning APIs only — keep a clear **“not financial advice”** disclaimer on the page.
> ***Projekt 6** är bara för att lära API:er — behåll en tydlig **“inte finansiell rådgivning”**-varning på sidan.*

**Svenska** — Diskutera:

1. **Alternativ A (vanligast):** Öppna mappen `**projects/`** och läs beskrivningarna. Välj **ett** projekt som startpunkt — **anpassa** det sedan (ändra fokus, ta bort funktioner, gör det mindre).
2. **Alternativ B:** Ta med **en egen idé** — det går bra! Beskriv den i **en mening**.
3. Om flera har idéer, **rösta** — eller kombinera det bästa till en **liten** app.

**Write down / Skriv ner:**

```text
Our project (from projects/ or own idea): ___________________________________
Vårt projekt (från projects/ eller egen idé): _______________________________

Our app idea (one sentence): _______________________________________________
Vår app-idé (en mening): _______________________________________________
```

---

## Step 2 — Scope it small (4 min) / Steg 2 — Avgränsa smått

**English** — A **finished small app** beats an unfinished big one. Discuss each point:

**Svenska** — En **klar liten app** slår en oavslutad stor. Diskutera varje punkt:


| Question / Fråga                                                                                                                            | Your answer / Ert svar |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| What are the **1–2 core features**? (the main things it must do) / Vilka är **1–2 kärnfunktioner**? (det viktigaste appen måste göra)       |                        |
| What sounds cool but is **NOT for today**? (nice-to-have list) / Vad låter coolt men är **INTE för idag**? (trevligt-att-ha-lista)          |                        |
| Can you describe the whole app in **one sentence**? If not → scope down! / Kan ni beskriva hela appen i **en mening**? Om inte → avgränsa!  |                        |
| Will you finish the **core** in today's build time (~~1 hour)? Be honest. / Hinner ni **kärnan** på dagens byggtid (~~1 timme)? Var ärliga. |                        |


**Red flags — scope is too big / Varningstecken — för stort scope:**

- More than 2 core features / Mer än 2 kärnfunktioner
- Needs login, accounts, or a database / Kräver inloggning, konton eller databas
- Needs an API key you don't have set up safely / Kräver API-nyckel som inte är säkert uppsatt
- "And also…" more than twice / "Och dessutom…" mer än två gånger

---

## Step 3 — Design: what to consider BEFORE you build (5 min) / Steg 3 — Design: vad ska ni tänka på INNAN ni bygger

**English** — Go through this checklist **as a group**. For each item, say **yes / no / not sure** and note what you'll do about it.

**Svenska** — Gå igenom checklistan **som grupp**. För varje punkt, säg **ja / nej / osäker** och skriv vad ni ska göra.

### A. User & purpose / Användare & syfte

- [ ] **Who** is this app for? (you, friends, family, classmates?) / **Vem** är appen till för? (du, vänner, familj, klasskamrater?)
- [ ] **Why** would someone use it? What's the fun or useful part? / **Varför** skulle någon använda den? Vad är det roliga eller användbara?
- [ ] Can a new user understand what to do **without** you explaining? / Kan en ny användare förstå vad hen ska göra **utan** att du förklarar?

### B. Data & API / Data & API

- [ ] **Which API** will you use? (write the base URL) / **Vilket API** ska ni använda? (skriv bas-URL:en)
- [ ] Have you **opened a sample URL in the browser** and looked at the JSON? / Har ni **öppnat en exempel-URL i webbläsaren** och tittat på JSON:en?
- [ ] Is it **free** and **no key** (or do you have a safe plan for a key)? / Är det **gratis** och **nyckel-fritt** (eller har ni en säker plan för en nyckel)?
- [ ] Which **fields** from the JSON will you show on the page? / Vilka **fält** från JSON:en ska ni visa på sidan?

### C. Page layout / Sidlayout

- [ ] What **parts** does the page need? (e.g. title, input, button, results area, status message) / Vilka **delar** behöver sidan? (t.ex. rubrik, inmatning, knapp, resultatytan, statusmeddelande)
- [ ] Sketch a **rough wireframe** on paper — boxes and labels are enough! / Skissa en **grovt wireframe** på papper — rutor och etiketter räcker!
- [ ] What is the **user flow**? (Step 1: user does ___ → Step 2: ___ → Step 3: ___) / Vad är **användarflödet**? (Steg 1: användaren ___ → Steg 2: ___ → Steg 3: ___)

### D. Real app behavior / Riktigt app-beteende

- [ ] What shows while data is **loading**? / Vad visas medan data **laddas**?
- [ ] What shows if the API **fails** or there's **no internet**? / Vad visas om API:et **misslyckas** eller det **inte finns internet**?
- [ ] What shows if the user searches but gets **no results** (empty state)? / Vad visas om användaren söker men får **inga resultat** (tomt-läge)?

### E. Safety & privacy / Säkerhet & integritet

- [ ] Will the app be **public** later (GitHub Pages)? → No real photos, full names, addresses, or secrets / Blir appen **offentlig** senare (GitHub Pages)? → Inga riktiga foton, fullständiga namn, adresser eller hemligheter
- [ ] Will you put any **API keys or passwords** in the code? (Answer should be **no** for a public repo) / Ska ni lägga **API-nycklar eller lösenord** i koden? (Svaret ska vara **nej** för ett offentligt repo)
- [ ] Is all data from the API **safe to display**? / Är all data från API:et **säker att visa**?

### F. Skills from this week / Färdigheter från veckan

- [ ] You'll use the **app loop**: input → request → response → display / Ni använder **app-loopen**: inmatning → förfrågan → svar → visning
- [ ] You'll use **small named functions** (not one giant block) / Ni använder **små namngivna funktioner** (inte ett enda stort block)
- [ ] You'll **commit often** with clear messages / Ni **commit:ar ofta** med tydliga meddelanden
- [ ] You can **explain every line** the AI writes (golden rule) / Ni kan **förklara varje rad** AI:n skriver (gyllene regeln)

> 💬 **Ask your teacher** if any box is "not sure" — that's what they're here for!
> *Fråga er lärare om någon ruta är "osäker" — det är därför de är här!*

---

## Step 4 — Choose & test your API (4 min) / Steg 4 — Välj & testa ert API

**English**

1. If you picked from `**projects/**`, copy the API details from your project brief — then **test** them in the browser.
2. If you have **your own idea**, find an API (see links below) and open a sample URL in the browser.
3. Confirm it works **right now** — not "probably works."
4. Write down one **example URL** you'll use in code.

**Svenska**

1. Om ni valde från `**projects/**`, kopiera API-detaljerna från er projektbeskrivning — **testa** dem sedan i webbläsaren.
2. Om ni har **en egen idé**, hitta ett API (se länkar nedan) och öppna en exempel-URL i webbläsaren.
3. Bekräfta att det fungerar **just nu** — inte "fungerar nog."
4. Skriv ner en **exempel-URL** ni ska använda i koden.

**Write down / Skriv ner:**

```text
API name / API-namn: _______________________
API base URL / API bas-URL: _______________________
Example URL we tested / Exempel-URL vi testade: _______________________
Fields we will use / Fält vi ska använda: _______________________
```

**If you need to find an API yourself / Om ni behöver hitta ett API själva:**

- [public-apis (GitHub)](https://github.com/public-apis/public-apis)
- [Free Public APIs](https://www.freepublicapis.com/)

**APIs we've already used in class / API:er vi redan använt** *(good for own small ideas / bra för egna små idéer)*:

- Rick and Morty · Dog CEO · Open-Meteo · TheCatAPI · Bored API

---

## Step 5 — Sketch the screen (3 min) / Steg 5 — Skissa skärmen

**English** — Draw one screen on paper. Label each part. Example layout:

**Svenska** — Rita en skärm på papper. Märk varje del. Exempel-layout:

```text
┌────────────────────────────────────┐
│  [ App title / Apprubrik ]         │
│                                    │
│  [ input box / inmatningsruta ]    │
│  [ Search button / Sökknapp ]      │
│                                    │
│  [ status: "Loading…" / "Laddar…"] │
│                                    │
│  ┌────────────────────────────┐    │
│  │  Result card / Resultatkort|    │
│  │  - field 1 / fält 1        │    │
│  │  - field 2 / fält 2        │    │
│  │  - image / bild            │    │
│  └────────────────────────────┘    │
└────────────────────────────────────┘
```

**Discuss:** What appears **before** the user clicks? What appears **after**?
**Diskutera:** Vad syns **innan** användaren klickar? Vad syns **efter**?

---

## Step 6 — Write your implementation plan (5 min) / Steg 6 — Skriv er implementationsplan

**English**

Your build order matters. Plan **small steps** — each step should give you something that **runs**. Don't try to build everything in one giant AI prompt.

**Svenska**

Er byggordning spelar roll. Planera **små steg** — varje steg ska ge er något som **körs**. Försök inte bygga allt i en enda jätte-prompt.

### Recommended build order / Rekommenderad byggordning


| Step / Steg | What you build / Vad ni bygger                                                                                                         | Done? / Klar? |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| **1**       | Create `index.html` + HTML skeleton / Skapa `index.html` + HTML-skelett                                                                | ☐             |
| **2**       | Add page layout (title, input, button, result area, status line) / Lägg till sidlayout (rubrik, inmatning, knapp, resultat, statusrad) | ☐             |
| **3**       | Add basic CSS so it looks readable / Lägg till enkel CSS så det är läsbart                                                             | ☐             |
| **4**       | `fetch` the API + `console.log` the response / `fetch`:a API:et + `console.log`:a svaret                                               | ☐             |
| **5**       | Show **one field** on the page / Visa **ett fält** på sidan                                                                            | ☐             |
| **6**       | Show **all planned fields** (or full result card) / Visa **alla planerade fält** (eller hela resultatkortet)                           | ☐             |
| **7**       | Add **loading**, **error**, and **empty** messages / Lägg till **laddning**, **fel** och **tomt**-meddelanden                          | ☐             |
| **8**       | **Commit** after each working step / **Commit:a** efter varje fungerande steg                                                          | ☐             |
| **9**       | Polish styling (optional if time) / Finjustera stil (valfritt om tid finns)                                                            | ☐             |
| **10**      | Nice-to-haves from Step 2 — **only if core works** / Trevligt-att-ha från steg 2 — **bara om kärnan fungerar**                         | ☐             |


**Write your first AI prompt (draft) / Skriv er första AI-prompt (utkast):**

```text
Using plain HTML/CSS/JS, build step ___ of my app:
[describe ONLY this one step — be specific]
Use the API: [URL]
Explain each line with a short comment.

Med ren HTML/CSS/JS, bygg steg ___ av min app:
[beskriv BARA detta enda steg — var specifik]
Använd API:et: [URL]
Förklara varje rad med en kort kommentar.
```

> 🏅 **Rule:** one feature per prompt, then **review and test** before the next.
> *Regel: en funktion per prompt, sedan **granska och testa** innan nästa.*

---

## Step 7 — Plan for problems (3 min) / Steg 7 — Planera för problem

**English** — Discuss what could go wrong and your backup plan:

**Svenska** — Diskutera vad som kan gå fel och er reservplan:


| What if… / Tänk om…                                                                            | Our plan / Vår plan |
| ---------------------------------------------------------------------------------------------- | ------------------- |
| The API is down during the showcase / API:et ligger nere under uppvisningen                    |                     |
| The AI writes code we don't understand / AI:n skriver kod vi inte förstår                      |                     |
| We run out of time today / Vi får slut på tid idag                                             |                     |
| Our idea is too big after 20 minutes of building / Idén är för stor efter 20 minuters byggande |                     |


**Scope-down examples / Exempel på att avgränsa:**

- Drop the image → show text only first / Slopa bilden → visa bara text först
- One search field instead of filters / Ett sökfält i stället för filter
- Show 3 fields instead of 10 / Visa 3 fält i stället för 10

---

## Step 8 — Final check & handoff (2 min) / Steg 8 — Slutkoll & överlämning

**English** — Before you leave the breakout room, confirm:

- [ ] One-sentence app purpose is written and agreed
- [ ] API is tested in the browser
- [ ] Wireframe sketch exists
- [ ] Build order (Steps 1–8 in the table) is filled in
- [ ] Nice-to-have list is **separate** from must-have
- [ ] Spokesperson knows what to share in the main room

**Svenska** — Innan ni lämnar grupprummet, bekräfta:

- [ ] Syftet i en mening är skrivet och alla är överens
- [ ] API:et är testat i webbläsaren
- [ ] Wireframe-skissen finns
- [ ] Byggordningen (steg 1–8 i tabellen) är ifylld
- [ ] Trevligt-att-ha-listan är **separat** från måste-ha
- [ ] Talespersonen vet vad hen ska dela i huvudrummet

**Share in the main room (30 sec) / Dela i huvudrummet (30 sek):**

1. App name + one-sentence purpose / Appnamn + syfte i en mening
2. Which API / Vilket API
3. One thing you're excited to build / En sak ni ser fram emot att bygga

---

## Your project plan — copy & fill in / Er projektplan — kopiera & fyll i

```text
Team / Lag: _______________________
Date / Datum: _______________________

Project source / Projektkälla:  ☐ projects/ (which #? / vilket #?) ___   ☐ Own idea / Egen idé

1. APP PURPOSE (one sentence) / SYFTE (en mening):
   _________________________________________________________________

2. CORE FEATURES (max 2) / KÄRNFUNKTIONER (max 2):
   • _______________________________________________________________
   • _______________________________________________________________

3. NICE-TO-HAVES (not today) / TREVLIGT-ATT-HA (inte idag):
   • _______________________________________________________________

4. API:
   Name / Namn: _______________  URL tested / URL testad: _______________________________
   Fields to show / Fält att visa: __________________________________________________

5. PAGE PARTS / SIDDELAR:
   • _______________________________________________________________

6. USER FLOW / ANVÄNDARFLÖDE:
   1) User / Användaren _________________  2) App _________________  3) User sees / Användaren ser _________________

7. STATES / LÄGEN:
   Loading / Laddar: _________________  Error / Fel: _________________  Empty / Tomt: _________________

8. BUILD ORDER (first 3 steps today) / BYGGORDNING (första 3 stegen idag):
   1) _________________  2) _________________  3) _________________

9. IF WE GET STUCK / OM VI FASTNAR:
   _________________________________________________________________
```

---

## For teachers in the breakout room / För lärare i grupprummet

**Your role / Er roll:** guide thinking, ask questions, **don't pick the idea for them**. Help groups scope **down**, not **up**.
*Led er tänkande, ställ frågor, **välj inte idén åt dem**. Hjälp grupper att avgränsa **neråt**, inte uppåt.*

**If the group picked from `projects/` / Om gruppen valde från `projects/`:**

- "Which **parts** of the brief are you building **today** vs leaving for later?" / "Vilka **delar** av beskrivningen bygger ni **idag** vs sparar till senare?"
- "Project 5 is huge — what's your **one** core feature for today?" / "Projekt 5 är stort — vad är er **enda** kärnfunktion idag?"

**If the group brought an own idea / Om gruppen har en egen idé:**

- "Can you say the whole app in **one sentence**?" / "Kan ni säga hela appen i **en mening**?"
- "Do you have an API that **works in the browser right now**?" / "Har ni ett API som **fungerar i webbläsaren just nu**?"

**If the group is stuck / Om gruppen fastnar:**

- "Can you say the whole app in **one sentence**?" / "Kan ni säga hela appen i **en mening**?"
- "What's the **smallest version** that still feels cool?" / "Vad är den **minsta versionen** som fortfarande känns cool?"
- "Open the API in the browser — **what fields** do you actually see?" / "Öppna API:et i webbläsaren — **vilka fält** ser ni faktiskt?"
- "What will you build in the **first 15 minutes** of coding?" / "Vad ska ni bygga de **första 15 minuterna** av kodningen?"

**If the scope is too big / Om scopet är för stort:**

- "Which **one** feature matters most? Build that first." / "Vilken **en** funktion betyder mest? Bygg den först."
- "Move the rest to the **nice-to-have** list." / "Flytta resten till **trevligt-att-ha**-listan."
- "Day 7 is for polish — today is **core only**." / "Dag 7 är för finputs — idag är det bara **kärnan**."

**If they're ready to code early / Om de är redo att koda tidigt:**

- Check the **implementation plan** is specific enough. / Kolla att **implementationsplanen** är specifik nog.
- Ask them to draft their **first prompt** out loud before opening Cline. / Be dem formulera sin **första prompt** högt innan de öppnar Cline.

**Time guide / Tidsguide:**


| Step / Steg                                   | Minutes / Minuter                                                                         |
| --------------------------------------------- | ----------------------------------------------------------------------------------------- |
| 1 — Idea / Idé                                | 3                                                                                         |
| 2 — Scope / Avgränsning                       | 4                                                                                         |
| 3 — Design checklist / Design-checklista      | 5                                                                                         |
| 4 — API test / API-test                       | 4                                                                                         |
| 5 — Sketch / Skiss                            | 3                                                                                         |
| 6 — Implementation plan / Implementationsplan | 5                                                                                         |
| 7 — Problems / Problem                        | 3                                                                                         |
| 8 — Final check / Slutkoll                    | 2                                                                                         |
| **Total / Totalt**                            | **~24 min** *(stretch to 30 with extra discussion / sträck till 30 med extra diskussion)* |


---

*Next: start building your prototype — iterate, commit, and explain your code!*
*Nästa: börja bygga er prototyp — iterera, commit:a, och förklara er kod!*
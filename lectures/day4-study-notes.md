# Day 4 — Building a Real Mini App Around an API
# Dag 4 — Bygga en riktig mini-app runt ett API

> **How to use these notes / Så använder du dessa anteckningar**
> Read these after the lecture to recap. Each section is written in **English first**, then **Swedish (Svenska)**. Try to explain each idea out loud in your own words — if you can't, that's the part to re-read.
>
> Läs detta efter föreläsningen för att repetera. Varje avsnitt är skrivet **på engelska först**, sedan **på svenska**. Försök förklara varje idé högt med egna ord — om du inte kan, är det den delen du ska läsa om.

---

## Today's lesson plan / Dagens upplägg

**Total: 2 hours / 2 timmar**

| Block / Moment | Time / Tid | What happens / Vad vi gör |
|----------------|-----------|----------------------------|
| **Warm-up & recap**<br>*Uppvärmning & repetition* | 10 min | Recap `fetch` and JSON from Day 3; today's goal: an interactive app.<br>*Repetera `fetch` och JSON från Dag 3; dagens mål: en interaktiv app.* |
| **Concept mini-lesson**<br>*Konceptgenomgång* | 25 min | The app loop, query parameters, small functions, and loading/error/empty states.<br>*App-loopen, query-parametrar, små funktioner, och laddnings-/fel-/tomt-lägen.* |
| **Guided build**<br>*Guidat bygge* | 45 min | Build a search-driven app (Weather Lookup or Country Explorer).<br>*Bygg en sök-driven app (Väderkoll eller Landutforskaren).* |
| **Independent challenge**<br>*Egen utmaning* | 30 min | Add a second piece of info to each result and improve the styling.<br>*Lägg till en andra bit info i varje resultat och förbättra stilen.* |
| **Wrap-up & share**<br>*Avslutning & dela* | 10 min | Where does the user's input enter the request? Preview tomorrow.<br>*Var kommer användarens inmatning in i förfrågan? En förhandstitt på imorgon.* |

---

## 1. What you'll be able to do after today / Vad du kan efter idag

**English**
- Understand the core app loop: **user input → request → response → display**.
- Use **query parameters** to change what the API returns based on user input.
- Handle **loading**, **errors**, and **empty results** so the app feels real.
- Structure your code into small, **named functions**.
- Build a search-driven app (e.g. Weather Lookup or Country Explorer).

**Svenska**
- Förstå appens kärn-loop: **användarinmatning → förfrågan → svar → visning**.
- Använda **query-parametrar** för att ändra vad API:et returnerar utifrån användarens inmatning.
- Hantera **laddning**, **fel** och **tomma resultat** så att appen känns äkta.
- Strukturera din kod i små, **namngivna funktioner**.
- Bygga en sök-driven app (t.ex. Väderkoll eller Landutforskaren).

---

## 2. The core app loop / Appens kärn-loop

**English**
Almost every data app follows the same four-step loop:

1. **User input** — the user types or picks something (a city, a country, a search term).
2. **Request** — your code builds a URL with that input and `fetch`es it.
3. **Response** — the API sends back JSON.
4. **Display** — you pull out the fields you want and show them on the page.

Yesterday you did steps 2–4 with a fixed URL. Today the **user** decides part of the request, so the app becomes interactive.

**Svenska**
Nästan varje data-app följer samma fyra-stegs-loop:

1. **Användarinmatning** — användaren skriver eller väljer något (en stad, ett land, en sökterm).
2. **Förfrågan** — din kod bygger en URL med den inmatningen och `fetch`:ar den.
3. **Svar** — API:et skickar tillbaka JSON.
4. **Visning** — du plockar ut de fält du vill ha och visar dem på sidan.

Igår gjorde du steg 2–4 med en fast URL. Idag bestämmer **användaren** en del av förfrågan, så appen blir interaktiv.

> **Key idea / Nyckelidé:** input → request → response → display. Everything today fits into that loop. / inmatning → förfrågan → svar → visning. Allt idag passar in i den loopen.

---

## 3. Query parameters: user input changes the request / Query-parametrar: inmatning ändrar förfrågan

**English**
**Query parameters** are the options at the end of a URL (after `?`, joined by `&`). By putting the user's input into a parameter, the same endpoint returns *different* data.

```text
https://api.example.com/search?query=stockholm
                               └──── parameter ────┘
```

In code you build that URL from a variable:

```js
const city = inputBox.value;                 // what the user typed
const url = `https://api.example.com/search?query=${city}`; // insert it into the URL
```

The `${city}` part is a **template literal** — it drops the variable's value into the string. Tip: real user text can contain spaces or special characters, so it's often wrapped with `encodeURIComponent(city)` to stay valid in a URL.

**Svenska**
**Query-parametrar** är valen i slutet av en URL (efter `?`, sammanfogade med `&`). Genom att lägga användarens inmatning i en parameter returnerar samma endpoint *olika* data.

(Samma exempel gäller.) I kod bygger du URL:en från en variabel: `${city}` är en **template literal** — den lägger in variabelns värde i texten. Tips: riktig användartext kan innehålla mellanslag eller specialtecken, så den lindas ofta med `encodeURIComponent(city)` för att vara giltig i en URL.

---

## 4. Structuring code into small functions / Strukturera kod i små funktioner

**English**
As apps grow, one giant block of code gets hard to read. Split it into small **named functions**, each doing one job:

- `getCity()` — read what the user typed.
- `buildUrl(city)` — make the request URL.
- `fetchWeather(url)` — get the data.
- `showResult(data)` — render it on the page.

Benefits: each function is easy to name, test, fix, and **explain** — which is the golden rule of this course.

```js
async function search() {
  const city = getCity();
  const url = buildUrl(city);
  const data = await fetchWeather(url);
  showResult(data);
}
```

**Svenska**
När appar växer blir ett enda stort kodblock svårt att läsa. Dela upp det i små **namngivna funktioner**, där var och en gör ett jobb:

- `getCity()` — läs vad användaren skrev.
- `buildUrl(city)` — skapa förfrågans-URL:en.
- `fetchWeather(url)` — hämta datan.
- `showResult(data)` — visa den på sidan.

Fördelar: varje funktion är lätt att namnge, testa, fixa och **förklara** — vilket är kursens gyllene regel.

> **Remember / Kom ihåg:** One function = one job. Small pieces are easier to understand and explain. / En funktion = ett jobb. Små delar är lättare att förstå och förklara.

---

## 5. Handling real-world data: loading, errors, empty / Hantera verklig data: laddning, fel, tomt

**English**
Real data isn't instant and isn't always there. A good app handles three cases:

- **Loading:** show "Loading…" while you wait, so the user knows something is happening.
- **Error:** the request can fail (no internet, API down, bad input). Catch it and show a friendly message instead of a broken page.
- **Empty results:** the API might return *nothing* (e.g. a city that doesn't exist). Show "No results found" rather than a blank screen.

```js
async function search() {
  showMessage("Loading…");                 // loading state
  try {
    const data = await fetchWeather(buildUrl(getCity()));
    if (!data || data.length === 0) {
      showMessage("No results found.");    // empty state
    } else {
      showResult(data);                    // success
    }
  } catch (error) {
    showMessage("Something went wrong. Try again.");  // error state
  }
}
```

**Svenska**
Riktig data är inte omedelbar och finns inte alltid. En bra app hanterar tre fall:

- **Laddning:** visa "Laddar…" medan du väntar, så användaren vet att något händer.
- **Fel:** förfrågan kan misslyckas (inget internet, API nere, dålig inmatning). Fånga det och visa ett vänligt meddelande i stället för en trasig sida.
- **Tomma resultat:** API:et kan returnera *ingenting* (t.ex. en stad som inte finns). Visa "Inga resultat" i stället för en tom skärm.

(Samma kodexempel gäller: `showMessage("Laddar…")` är laddningsläget, `catch` hanterar fel, och `if`-kontrollen hanterar tomma resultat.)

> **Key idea / Nyckelidé:** Always plan for loading, errors, and empty — that's what separates a demo from a real app. / Planera alltid för laddning, fel och tomt — det skiljer en demo från en riktig app.

---

## 6. Today's build: a search-driven app / Dagens bygge: en sök-driven app

**English**
Build something where the user types input and gets live results in a card. Two good options:

- **Weather Lookup** — type a city, show the current temperature and conditions.
- **Country Explorer** — type a country, show its capital, region, and flag.

Steps:
1. Add an input box and a search button.
2. On click, read the input and build the request URL.
3. Fetch, then render the result in a nicely styled card.
4. Add loading, error, and empty states.

Example prompt:

```text
"Using plain HTML/CSS/JS, make a weather lookup: an input for a city and a search
button. On search, fetch current weather from Open-Meteo and show temperature in a
card. Add a 'Loading…' message, an error message, and a 'not found' message.
Use small named functions and comment each one."
```

**Svenska**
Bygg något där användaren skriver in och får live-resultat i ett kort. Två bra alternativ:

- **Väderkoll** — skriv en stad, visa aktuell temperatur och väder.
- **Landutforskaren** — skriv ett land, visa dess huvudstad, region och flagga.

Steg:
1. Lägg till en inmatningsruta och en sökknapp.
2. Vid klick, läs inmatningen och bygg förfrågans-URL:en.
3. Hämta, visa sedan resultatet i ett snyggt format-kort.
4. Lägg till laddnings-, fel- och tomt-lägen.

(Samma exempel-prompt gäller, översatt till svenska vid behov.)

---

## 7. Independent challenge / Egen utmaning

**English**
Add a **second piece of info** to each result (e.g. wind speed for weather, or population for a country) and improve the layout/styling with the AI's help. Make sure your loading/error/empty states still work.

**Svenska**
Lägg till en **andra bit information** till varje resultat (t.ex. vindhastighet för väder, eller befolkning för ett land) och förbättra layouten/stilen med AI:ns hjälp. Se till att dina laddnings-/fel-/tomt-lägen fortfarande fungerar.

---

## 8. Concept check — can you answer these? / Konceptkoll — kan du svara på dessa?

**English**
1. Name the four steps of the core app loop.
2. **Where exactly does the user's input enter the request?**
3. Why split code into small named functions?
4. Name the three real-world states every data app should handle.

**Svenska**
1. Namnge de fyra stegen i appens kärn-loop.
2. **Var exakt kommer användarens inmatning in i förfrågan?**
3. Varför dela upp kod i små namngivna funktioner?
4. Namnge de tre verkliga lägen som varje data-app bör hantera.

---

## 9. Key vocabulary / Nyckelord

| English | Svenska | Meaning / Betydelse |
|---------|---------|----------------------|
| Input | Inmatning | What the user types/picks / Det användaren skriver/väljer |
| Query parameter | Query-parameter | An option in the URL after `?` / Ett val i URL:en efter `?` |
| Template literal | Template literal | A string that inserts variables (`` `...${x}` ``) / En text som infogar variabler |
| Function | Funktion | A named block doing one job / Ett namngivet block som gör ett jobb |
| Render | Rendera / visa | Show data on the page / Visa data på sidan |
| Loading state | Laddningsläge | UI shown while waiting / Gränssnitt som visas medan man väntar |
| Error handling | Felhantering | Reacting safely when something fails / Att reagera säkert när något misslyckas |
| Empty state | Tomt-läge | UI when there are no results / Gränssnitt när det inte finns resultat |
| `try`/`catch` | `try`/`catch` | Code that catches errors / Kod som fångar fel |

---

*Previously: Day 3 — What an API Is & Your First Real Data.*
*Next up: Day 5 — Git, GitHub & Working Like a Real Developer.*
*Tidigare: Dag 3 — Vad ett API är & din första riktiga data.*
*Nästa: Dag 5 — Git, GitHub & att jobba som en riktig utvecklare.*

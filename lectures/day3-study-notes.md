# Day 3 — What an API Is & Your First Real Data
# Dag 3 — Vad ett API är & din första riktiga data

> **How to use these notes / Så använder du dessa anteckningar**
> Read these after the lecture to recap. Each section is written in **English first**, then **Swedish (Svenska)**. Try to explain each idea out loud in your own words — if you can't, that's the part to re-read.
>
> Läs detta efter föreläsningen för att repetera. Varje avsnitt är skrivet **på engelska först**, sedan **på svenska**. Försök förklara varje idé högt med egna ord — om du inte kan, är det den delen du ska läsa om.

---

## Today's lesson plan / Dagens upplägg

**Total: 2 hours / 2 timmar**

| Block / Moment | Time / Tid | What happens / Vad vi gör |
|----------------|-----------|----------------------------|
| **Warm-up & recap**<br>*Uppvärmning & repetition* | 10 min | Recap functions and events from Day 2; today's goal: real data from an API.<br>*Repetera funktioner och händelser från Dag 2; dagens mål: riktig data från ett API.* |
| **Concept mini-lesson**<br>*Konceptgenomgång* | 25 min | API as a menu, how JSON is shaped, and how to read API docs.<br>*API som en meny, hur JSON är format, och hur man läser API-dokumentation.* |
| **Guided build**<br>*Guidat bygge* | 45 min | Fetch from a no-key public API, log it to the console, and show one field.<br>*Hämta från ett nyckel-fritt publikt API, logga det till konsolen, och visa ett fält.* |
| **Independent challenge**<br>*Egen utmaning* | 30 min | Display three different fields from the response, nicely formatted.<br>*Visa tre olika fält från svaret, snyggt formaterade.* |
| **Wrap-up & share**<br>*Avslutning & dela* | 10 min | Trace the data's journey from API to screen; preview tomorrow.<br>*Spåra datans resa från API till skärm; en förhandstitt på imorgon.* |

---

## 1. What you'll be able to do after today / Vad du kan efter idag

**English**
- Explain what an API is using the "restaurant menu" idea.
- Read JSON data: keys, values, arrays, and nesting.
- Read basic API docs: base URL, endpoints, parameters, example responses.
- Look at raw data *before* coding, by opening an API URL in the browser.
- Use `fetch` to get data from a free, no-key public API and show it on the page.

**Svenska**
- Förklara vad ett API är med idén om en "restaurangmeny".
- Läsa JSON-data: nycklar, värden, listor (arrays) och nästling.
- Läsa grundläggande API-dokumentation: bas-URL, endpoints, parametrar, exempel-svar.
- Titta på rådata *innan* du kodar, genom att öppna en API-URL i webbläsaren.
- Använda `fetch` för att hämta data från ett gratis, nyckel-fritt publikt API och visa det på sidan.

---

## 2. What an API is / Vad ett API är

**English**
**API** stands for **Application Programming Interface**. It's a **menu of requests** that another service agrees to answer. You don't need to know *how* their kitchen works — you just order from the menu and get a response.

- **Restaurant analogy:**
  - **Menu** = the list of things you're allowed to ask for (the **endpoints**).
  - **Your order** = the **request** you send.
  - **The dish** = the **response** you get back (usually data).
- You already used this idea on Day 1: client sends a request, server sends a response. An API is just a **well-defined set of requests** a server promises to answer.
- APIs let your small web page use data and features from huge services (weather, maps, dictionaries, images) without building them yourself.

**Svenska**
**API** står för **Application Programming Interface** (programmeringsgränssnitt). Det är en **meny av förfrågningar** som en annan tjänst går med på att besvara. Du behöver inte veta *hur* deras kök fungerar — du beställer bara från menyn och får ett svar.

- **Restaurang-liknelse:**
  - **Menyn** = listan över saker du får be om (**endpoints**).
  - **Din beställning** = **förfrågan (request)** du skickar.
  - **Rätten** = **svaret (response)** du får tillbaka (oftast data).
- Du använde redan denna idé på Dag 1: klienten skickar en förfrågan, servern skickar ett svar. Ett API är bara en **väldefinierad uppsättning förfrågningar** som en server lovar att besvara.
- API:er låter din lilla webbsida använda data och funktioner från enorma tjänster (väder, kartor, ordböcker, bilder) utan att du bygger dem själv.

> **Key idea / Nyckelidé:** An API is a menu of requests a service promises to answer. / Ett API är en meny av förfrågningar som en tjänst lovar att besvara.

---

## 3. JSON: how data is shaped / JSON: hur data är format

**English**
Most APIs answer in **JSON** (JavaScript Object Notation). It's just **text** organized in a way that's easy for both humans and code to read.

Building blocks:
- **Key–value pair:** a label and its value. `"city": "Stockholm"`
- **Value types:** text (`"Stockholm"`), number (`18`), true/false (`true`), or nothing (`null`).
- **Object `{ }`:** a group of key–value pairs (like one "card" of info).
- **Array `[ ]`:** an ordered list of values (things in a row).
- **Nesting:** objects and arrays can contain other objects and arrays.

```json
{
  "city": "Stockholm",
  "temperature": 18,
  "isDay": true,
  "forecast": [
    { "day": "Mon", "high": 20 },
    { "day": "Tue", "high": 17 }
  ]
}
```

Reading it: `city` is text, `temperature` is a number, `forecast` is an **array** of two **objects**, and `forecast[0].high` is `20`.

**Svenska**
De flesta API:er svarar i **JSON** (JavaScript Object Notation). Det är bara **text** organiserad på ett sätt som är lätt för både människor och kod att läsa.

Byggstenar:
- **Nyckel–värde-par:** en etikett och dess värde. `"city": "Stockholm"`
- **Värdetyper:** text (`"Stockholm"`), tal (`18`), sant/falskt (`true`), eller ingenting (`null`).
- **Objekt `{ }`:** en grupp nyckel–värde-par (som ett "kort" med info).
- **Lista/array `[ ]`:** en ordnad lista av värden (saker på rad).
- **Nästling:** objekt och listor kan innehålla andra objekt och listor.

(Samma JSON-exempel gäller: `city` är text, `temperature` är ett tal, `forecast` är en **array** med två **objekt**, och `forecast[0].high` är `20`.)

> **Remember / Kom ihåg:** `{ }` = one thing with labeled parts (object). `[ ]` = a list of things (array). / `{ }` = en sak med namngivna delar (objekt). `[ ]` = en lista av saker (array).

---

## 4. Reading API docs / Att läsa API-dokumentation

**English**
Every API has **docs** (documentation) telling you how to use it. Four things to look for:

- **Base URL:** the start of every address, e.g. `https://api.open-meteo.com/v1`
- **Endpoint:** the specific "menu item" you add on, e.g. `/forecast`
- **Parameters:** extra options after a `?`, joined by `&`, that customize the request, e.g. `?latitude=59.3&longitude=18.1&current=temperature_2m`
- **Example response:** a sample of the JSON you'll get back — read it so you know what fields exist.

Full example URL:
```text
https://api.open-meteo.com/v1/forecast?latitude=59.3&longitude=18.1&current=temperature_2m
   └── base URL ──────────────┘└ endpoint ┘└──────────── parameters ─────────────┘
```

**Svenska**
Varje API har **dokumentation (docs)** som berättar hur du använder det. Fyra saker att leta efter:

- **Bas-URL:** början på varje adress, t.ex. `https://api.open-meteo.com/v1`
- **Endpoint:** den specifika "menyraden" du lägger till, t.ex. `/forecast`
- **Parametrar:** extra val efter ett `?`, sammanfogade med `&`, som anpassar förfrågan, t.ex. `?latitude=59.3&longitude=18.1&current=temperature_2m`
- **Exempel-svar:** ett exempel på den JSON du får tillbaka — läs det så du vet vilka fält som finns.

(Samma exempel-URL gäller: bas-URL + endpoint + parametrar tillsammans bildar hela adressen.)

---

## 5. See the data first / Se datan först

**English**
Before writing any code, **look at the raw data**. Just paste an API URL into your browser's address bar and press Enter — the browser shows you the JSON.

Why do this first?
- You confirm the API works and isn't down.
- You see exactly which **fields** exist and what they're called.
- You can plan what to display *before* coding.

Tip: a browser JSON viewer/extension makes the data easier to read (nice indentation, collapsible sections).

**Svenska**
Innan du skriver någon kod, **titta på rådatan**. Klistra bara in en API-URL i webbläsarens adressfält och tryck Enter — webbläsaren visar dig JSON:en.

Varför göra detta först?
- Du bekräftar att API:et fungerar och inte ligger nere.
- Du ser exakt vilka **fält** som finns och vad de heter.
- Du kan planera vad du ska visa *innan* du kodar.

Tips: en JSON-visare/tillägg i webbläsaren gör datan lättare att läsa (fin indentering, hopfällbara delar).

---

## 6. Beginner-friendly APIs (all free, no key) / Nybörjarvänliga API:er (gratis, ingen nyckel)

**English**
These are great to start with because they need **no sign-up and no key**:

- [Open-Meteo](https://open-meteo.com/) — weather
- [Dog CEO](https://dog.ceo/dog-api/) — random dog images
- [REST Countries](https://restcountries.com/) — country info
- [Bored API](https://www.boredapi.com/) — activity ideas

An **API key** is a password some APIs require to identify you. Today's APIs don't need one, which keeps things simple. (More on keys and keeping them safe on Day 5.)

**Svenska**
Dessa är bra att börja med eftersom de **inte kräver registrering eller nyckel**:

- [Open-Meteo](https://open-meteo.com/) — väder
- [Dog CEO](https://dog.ceo/dog-api/) — slumpmässiga hundbilder
- [REST Countries](https://restcountries.com/) — landinformation
- [Bored API](https://www.boredapi.com/) — aktivitetsidéer

En **API-nyckel** är ett lösenord som vissa API:er kräver för att identifiera dig. Dagens API:er behöver ingen, vilket håller det enkelt. (Mer om nycklar och att hålla dem säkra på Dag 5.)

---

## 7. `fetch`: getting data with JavaScript / `fetch`: att hämta data med JavaScript

**English**
`fetch` is the JavaScript command that sends a request to a URL and gets the response. Because a response can take a moment to arrive, we **wait** for it using `async`/`await`.

```html
<h1 id="result">Loading…</h1>

<script>
  async function getDogImage() {
    const response = await fetch("https://dog.ceo/api/breeds/image/random"); // send request, wait for response
    const data = await response.json();   // turn the JSON text into usable data
    console.log(data);                    // print the whole response to inspect it
    document.getElementById("result").textContent = data.message; // show one field
  }

  getDogImage();
</script>
```

What each step does:
- `fetch(url)` sends the request; `await` waits for the answer.
- `response.json()` converts the JSON text into a JavaScript object/array you can use.
- `console.log(data)` prints it so you can see the shape (open the browser's **Console**).
- `data.message` reads one **field** out of the response.

**Svenska**
`fetch` är JavaScript-kommandot som skickar en förfrågan till en URL och får svaret. Eftersom ett svar kan ta en stund att komma **väntar** vi på det med `async`/`await`.

(Samma kodexempel gäller.) Vad varje steg gör:
- `fetch(url)` skickar förfrågan; `await` väntar på svaret.
- `response.json()` omvandlar JSON-texten till ett JavaScript-objekt/array du kan använda.
- `console.log(data)` skriver ut det så att du kan se formen (öppna webbläsarens **Console**).
- `data.message` läser ett **fält** ur svaret.

> **Key idea / Nyckelidé:** `fetch` → wait → `.json()` → read a field → show it. / `fetch` → vänta → `.json()` → läs ett fält → visa det.

---

## 8. Today's build: fetch and display real data / Dagens bygge: hämta och visa riktig data

**English**
Pick one no-key API and:
1. `fetch` the data and `console.log` it to inspect the shape.
2. Find one useful **field** in the response.
3. Show that one field on the page.

Example prompt:

```text
"Using plain HTML/CSS/JS, fetch a random dog image from
https://dog.ceo/api/breeds/image/random. Log the full response to the console,
then show the image on the page. Explain each line with a short comment."
```

**Svenska**
Välj ett nyckel-fritt API och:
1. `fetch`:a datan och `console.log`:a den för att inspektera formen.
2. Hitta ett användbart **fält** i svaret.
3. Visa det enda fältet på sidan.

Exempel-prompt:

```text
"Med ren HTML/CSS/JS, hämta en slumpmässig hundbild från
https://dog.ceo/api/breeds/image/random. Logga hela svaret till konsolen,
visa sedan bilden på sidan. Förklara varje rad med en kort kommentar."
```

---

## 9. Independent challenge / Egen utmaning

**English**
Display **three different fields** from the response, nicely formatted on the page. (For a weather API that might be temperature, wind, and time; for countries it might be name, capital, and population.)

Bonus: use `console.log` to explore the JSON and find a field that's **nested** inside an object or array.

**Svenska**
Visa **tre olika fält** från svaret, snyggt formaterade på sidan. (För ett väder-API kan det vara temperatur, vind och tid; för länder kan det vara namn, huvudstad och befolkning.)

Bonus: använd `console.log` för att utforska JSON:en och hitta ett fält som är **nästlat** inuti ett objekt eller en array.

---

## 10. Concept check — can you answer these? / Konceptkoll — kan du svara på dessa?

**English**
1. Explain an API using the restaurant analogy.
2. In JSON, what's the difference between `{ }` and `[ ]`?
3. In an API URL, what are the base URL, the endpoint, and the parameters?
4. **Trace the journey of the data** from the API all the way to the screen. What are the steps?

**Svenska**
1. Förklara ett API med restaurang-liknelsen.
2. I JSON, vad är skillnaden mellan `{ }` och `[ ]`?
3. I en API-URL, vad är bas-URL:en, endpointen och parametrarna?
4. **Spåra datans resa** från API:et hela vägen till skärmen. Vilka är stegen?

---

## 11. Key vocabulary / Nyckelord

| English | Svenska | Meaning / Betydelse |
|---------|---------|----------------------|
| API | API | A menu of requests a service answers / En meny av förfrågningar en tjänst besvarar |
| Endpoint | Endpoint | A specific address/"menu item" of an API / En specifik adress/"menyrad" i ett API |
| Base URL | Bas-URL | The common start of the API's addresses / Den gemensamma början på API:ets adresser |
| Parameter | Parameter | An option in the URL (after `?`) / Ett val i URL:en (efter `?`) |
| JSON | JSON | Text format for data / Textformat för data |
| Key–value | Nyckel–värde | A label and its value / En etikett och dess värde |
| Object `{ }` | Objekt `{ }` | Grouped key–value pairs / Grupperade nyckel–värde-par |
| Array `[ ]` | Array/lista `[ ]` | An ordered list of values / En ordnad lista av värden |
| Nesting | Nästling | Data inside other data / Data inuti annan data |
| Field | Fält | A single piece of data (a value) / En enskild bit data (ett värde) |
| `fetch` | `fetch` | JS command to request a URL / JS-kommando som begär en URL |
| API key | API-nyckel | A password some APIs require / Ett lösenord vissa API:er kräver |
| Console | Konsol | Browser panel that shows logs / Webbläsarpanel som visar loggar |

---

*Previously: Day 2 — Prompting an AI Well & Reading Its Code.*
*Next up: Day 4 — Building a Real Mini App Around an API.*
*Tidigare: Dag 2 — Att prompta en AI bra & läsa dess kod.*
*Nästa: Dag 4 — Bygga en riktig mini-app runt ett API.*

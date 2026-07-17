---
marp: true
theme: default
paginate: true
size: 16:9
title: "Day 3 — What an API Is & Your First Real Data"
---

<!-- _class: lead -->
<!-- _paginate: false -->

# Day 3

## What an API Is & Your First Real Data

*Dag 3 — Vad ett API är & din första riktiga data*

Summer Coding Course for Youth · Sudanese Association
*Sommarkurs i kodning för unga · Sudanesiska föreningen*

---

## Welcome back! 👋 / Välkommen tillbaka!

Quick recap from Day 2: *Snabb repetition från Dag 2:*

- We **prompted an AI** and **read its code** — *Vi promptade en AI och läste dess kod*
- HTML = structure, CSS = style, **JS = behavior** — *HTML = struktur, CSS = stil, JS = beteende*

> Today we get **real data** from the internet! 🌍
> *Idag hämtar vi **riktig data** från internet!*

---

## Today / Idag

1. What an **API** is — *Vad ett API är*
2. **JSON** — how data is shaped — *hur data är format*
3. Reading **API docs** — *Att läsa API-dokumentation*
4. **See the data** in the browser — *Se datan i webbläsaren*
5. **Fetch** data with JavaScript — *Hämta data med JavaScript*

> Goal: fetch from a real API and show it on **your** page. 🚀
> *Mål: hämta från ett riktigt API och visa det på **din** sida.*

---

## Today's goal / Dagens mål

By the end of today, you can:
*I slutet av idag kan du:*

- Explain an API with the **restaurant menu** idea — *förklara ett API med "restaurangmenyn"*
- Read **JSON**: keys, values, arrays, nesting — *läsa JSON*
- Read basic **API docs** — *läsa grundläggande API-dokumentation*
- Open an API URL in the **browser** to see raw data — *öppna en API-URL i webbläsaren*
- Use **`fetch`** to show real data on a page — *använda `fetch` för att visa data*

---

<!-- _class: lead -->

# Part 1 — What is an API?
## Del 1 — Vad är ett API?

🍽️

---

## API = a menu of requests / en meny av förfrågningar

**API** = **A**pplication **P**rogramming **I**nterface

A **menu of requests** another service agrees to answer.
*En **meny av förfrågningar** som en annan tjänst går med på att besvara.*

> You don't need to know *how* their kitchen works — you just **order from the menu** and get a response.
> *Du behöver inte veta *hur* deras kök fungerar — du **beställer från menyn** och får ett svar.*

---

## The restaurant analogy 🍽️ / Restaurang-liknelsen

| Restaurant / Restaurang | API |
|--------------------------|-----|
| The **menu** / Menyn | The **endpoints** (what you can ask for) |
| Your **order** / Din beställning | The **request** you send |
| The **dish** / Rätten | The **response** (usually data) |

> Same idea as Day 1: client **asks**, server **answers**.
> *Samma idé som Dag 1: klienten **frågar**, servern **svarar**.*

---

## Why APIs are awesome / Varför API:er är fantastiska

Your small page can use data from **huge services** — without building them!
*Din lilla sida kan använda data från **enorma tjänster** — utan att bygga dem!*

- ☁️ Weather — *Väder*
- 🗺️ Maps — *Kartor*
- 📖 Dictionaries — *Ordböcker*
- 🐶 Images — *Bilder*

> **Key idea / Nyckelidé:** An API is a menu of requests a service promises to answer.
> *Ett API är en meny av förfrågningar som en tjänst lovar att besvara.*

---

<!-- _class: lead -->

# Part 2 — JSON
## Del 2 — JSON

`{ }` · `[ ]`

---

## JSON: how data is shaped / hur data är format

Most APIs answer in **JSON** — just **text** organized so humans *and* code can read it.
*De flesta API:er svarar i **JSON** — bara **text** organiserad så att människor och kod kan läsa den.*

- **Key–value pair / Nyckel–värde:** `"city": "Stockholm"`
- **Value types / Värdetyper:** text, number, true/false, null
- **Object `{ }`** — a group of key–value pairs — *en grupp nyckel–värde-par*
- **Array `[ ]`** — an ordered list — *en ordnad lista*

---

## Read this JSON / Läs denna JSON

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

- `city` is **text**, `temperature` is a **number** — *text / tal*
- `forecast` is an **array** of two **objects** — *en array med två objekt*
- `forecast[0].high` is `20`

---

## `{ }` vs `[ ]` — remember! / kom ihåg!

- `{ }` = **one thing** with labeled parts (an **object**)
  *en **sak** med namngivna delar (ett **objekt**)*
- `[ ]` = a **list** of things (an **array**)
  *en **lista** av saker (en **array**)*

> 🔎 A field is one value, like `temperature`. You reach it with a **dot**: `data.temperature`.
> *Ett fält är ett värde, t.ex. `temperature`. Du når det med en **punkt**: `data.temperature`.*

---

<!-- _class: lead -->

# Part 3 — Reading API Docs
## Del 3 — Att läsa API-dokumentation

📄

---

## The 4 things to look for / De 4 sakerna att leta efter

- **Base URL / Bas-URL** — the start of every address
  `https://api.open-meteo.com/v1`
- **Endpoint** — the specific "menu item" — `/forecast`
- **Parameters / Parametrar** — options after `?`, joined by `&`
  `?latitude=59.3&longitude=18.1&current=temperature_2m`
- **Example response / Exempel-svar** — a sample of the JSON you'll get

---

## One full URL, three parts / En hel URL, tre delar

```text
https://api.open-meteo.com/v1/forecast?latitude=59.3&longitude=18.1&current=temperature_2m
   └── base URL ──────────────┘└ endpoint ┘└──────────── parameters ─────────────┘
```

> Read the **example response** in the docs first — then you know which **fields** exist.
> *Läs **exempel-svaret** i dokumentationen först — då vet du vilka **fält** som finns.*

---

<!-- _class: lead -->

# Part 4 — See the Data First
## Del 4 — Se datan först

🔎

---

## Look before you code / Titta innan du kodar

Paste an API URL into the browser's address bar → press Enter → **you see the JSON**.
*Klistra in en API-URL i adressfältet → tryck Enter → **du ser JSON:en**.*

Why first? *Varför först?*
- ✅ Confirm the API **works** — *bekräfta att API:et **fungerar***
- 👀 See exactly which **fields** exist — *se vilka **fält** som finns*
- 🗺️ Plan what to show **before** coding — *planera vad du ska visa **innan** du kodar*

> 💡 A JSON viewer extension makes it much easier to read.
> *Ett JSON-visartillägg gör det mycket lättare att läsa.*

---

## Try these in the browser 🌐 / Prova dessa i webbläsaren

All **free, no key, no sign-up** — *Alla gratis, ingen nyckel, ingen registrering:*

- 🐶 Dog CEO — `https://dog.ceo/api/breeds/image/random`
- ☁️ Open-Meteo — weather / väder
- 🌍 REST Countries — country info / landinfo
- 🎲 Bored API — activity ideas / aktivitetsidéer

> An **API key** is a password some APIs require. Today's need **none**. (More on keys, Day 5.)
> *En **API-nyckel** är ett lösenord vissa API:er kräver. Dagens behöver **ingen**. (Mer om nycklar, Dag 5.)*

---

<!-- _class: lead -->

# Part 5 — `fetch`
## Del 5 — `fetch`

Get data with JavaScript / Hämta data med JavaScript

---

## `fetch`: request → wait → read / förfrågan → vänta → läs

`fetch` sends a request to a URL and gets the response.
Because it takes a moment, we **wait** with `async`/`await`.
*`fetch` skickar en förfrågan och får svaret. Det tar en stund, så vi **väntar** med `async`/`await`.*

```html
<h1 id="result">Loading…</h1>
<script>
  async function getDogImage() {
    const response = await fetch("https://dog.ceo/api/breeds/image/random");
    const data = await response.json(); // JSON text → usable data
    console.log(data);                  // inspect the whole response
    document.getElementById("result").textContent = data.message; // one field
  }
  getDogImage();
</script>
```

---

## What each step does / Vad varje steg gör

- `fetch(url)` sends the request; `await` waits — *skickar förfrågan; väntar*
- `response.json()` turns JSON text into usable data — *gör JSON till användbar data*
- `console.log(data)` prints it (open the **Console**) — *skriver ut det (öppna **Console**)*
- `data.message` reads **one field** — *läser **ett fält***

> **Key idea / Nyckelidé:** `fetch` → wait → `.json()` → read a field → show it.
> *`fetch` → vänta → `.json()` → läs ett fält → visa det.*

---

<!-- _class: lead -->

# 🛠️ Exercise: Fetch real data
## Övning: Hämta riktig data

---

## Today's build / Dagens bygge

Pick one no-key API and: *Välj ett nyckel-fritt API och:*

1. `fetch` the data and `console.log` it — *hämta datan och logga den*
2. Find one useful **field** — *hitta ett användbart fält*
3. Show that field on the page — *visa fältet på sidan*

```text
Using plain HTML/CSS/JS, fetch a random dog image from
https://dog.ceo/api/breeds/image/random. Log the full response to the
console, then show the image on the page. Explain each line with a comment.
```

---

## Independent challenge / Egen utmaning

Show **three different fields** from the response, nicely formatted.
*Visa **tre olika fält** från svaret, snyggt formaterade.*

- Weather: temperature, wind, time — *Väder: temperatur, vind, tid*
- Countries: name, capital, population — *Länder: namn, huvudstad, befolkning*

> 🏆 **Bonus:** use `console.log` to find a field **nested** inside an object or array.
> *Bonus: använd `console.log` för att hitta ett **nästlat** fält.*

---

## Recap — can you answer? / Kan du svara?

1. Explain an API with the restaurant analogy — *Förklara ett API med restaurang-liknelsen*
2. `{ }` vs `[ ]` in JSON? — *`{ }` vs `[ ]` i JSON?*
3. Base URL, endpoint, parameters? — *Bas-URL, endpoint, parametrar?*
4. **Trace the data's journey** from API to screen — *Spåra datans resa från API till skärm*

---

<!-- _class: lead -->

## Great work today! 🎉
## Bra jobbat idag!

**Next / Nästa:** Day 4 — Building a Real Mini App Around an API
*Dag 4 — Bygga en riktig mini-app runt ett API*

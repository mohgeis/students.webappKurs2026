# Tutorial — Read a Public API & Show It on a Page

# Handledning — Läs ett publikt API & visa det på en sida

> **Day 3 hands-on / Dag 3 praktiskt**
> First you'll open a real API **in the browser** to see its raw **JSON**. Then you'll build a **very simple web page** that reads that same API and shows its content. Type it yourself — that's how the idea sticks.
>
> Först öppnar du ett riktigt API **i webbläsaren** för att se dess råa **JSON**. Sedan bygger du en **väldigt enkel webbsida** som läser samma API och visar dess innehåll. Skriv det själv — så fastnar idén.

---

## What you'll build / Vad du ska bygga

**English** — A tiny page that, when it loads, asks a free public API for a character and shows their **name**, **number (id)**, and **picture** on the screen.

**Svenska** — En liten sida som, när den laddas, ber ett gratis publikt API om en karaktär och visar deras **namn**, **nummer (id)** och **bild** på skärmen.

**You need / Du behöver:** VS Code + a web browser. *(No account, no API key.)*
*(Inget konto, ingen API-nyckel.)*

**The API we'll use / API:et vi använder:** Rick and Morty API 🛸
`https://rickandmortyapi.com/api/character/1`

---

# Part 1 — Read the API in the browser / Läs API:et i webbläsaren

## Step 1 — Open the API URL / Steg 1 — Öppna API-URL:en

**English**

1. Open your web browser (Chrome, Edge, Firefox…).
2. Click the **address bar** at the top.
3. Type (or paste) this address and press **Enter**:

**Svenska**

1. Öppna din webbläsare (Chrome, Edge, Firefox…).
2. Klicka på **adressfältet** högst upp.
3. Skriv (eller klistra in) denna adress och tryck **Enter**:

```text
https://rickandmortyapi.com/api/character/1
```

> You just sent a **request** to the server — like ordering from a menu. 🍽️
> *Du skickade precis en **förfrågan** till servern — som att beställa från en meny.*

---

## Step 2 — Look at the JSON / Steg 2 — Titta på JSON:en

**English**
The server sends back a **response** in **JSON**. It looks something like this (shortened):

**Svenska**
Servern skickar tillbaka ett **svar** i **JSON**. Det ser ut ungefär så här (förkortat):

```json
{
  "id": 1,
  "name": "Rick Sanchez",
  "status": "Alive",
  "species": "Human",
  "image": "https://rickandmortyapi.com/api/character/avatar/1.jpeg",
  "origin": { "name": "Earth (C-137)" },
  "episode": [ "...", "..." ]
}
```

**The fields we care about / Fälten vi bryr oss om:**

- `name` = the character's name — *karaktärens namn*
- `id` = their number — *deras nummer*
- `image` = a link to their picture — *en länk till deras bild*

> The response has **more fields** than we need (`origin`, `episode`, …). That's normal! We just **pick the ones we want** and ignore the rest.
> *Svaret har **fler fält** än vi behöver (`origin`, `episode`, …). Det är helt normalt! Vi **väljer bara de vi vill ha** och struntar i resten.*

---

## Step 3 — Make the JSON readable (optional) / Steg 3 — Gör JSON:en läsbar (valfritt)

**English**
Raw JSON can look messy. To read it nicely (indentation + colors), install a free **JSON viewer** extension in your browser (search your browser's extension store for "JSON Viewer"). It shows the data in a neat, foldable tree.

**Svenska**
Rå JSON kan se rörig ut. För att läsa den snyggt (indentering + färger), installera ett gratis **JSON Viewer**-tillägg i webbläsaren (sök i webbläsarens tilläggsbutik efter "JSON Viewer"). Det visar datan i ett prydligt, hopfällbart träd.

> 💡 Change the number at the end of the URL to `2`, `3`, `4`… to see a different character each time!
> *Ändra numret i slutet av URL:en till `2`, `3`, `4`… för att se en annan karaktär varje gång!*

---

## Step 4 — Find the fields you want / Steg 4 — Hitta fälten du vill ha

**English**
Before coding, decide **which fields** you want to show. We want three: the **name** (`name`), the **number** (`id`), and the **picture** (`image`). In code we'll reach each one with a dot: `**data.name`**, `**data.id**`, `**data.image**`.

**Svenska**
Innan du kodar, bestäm **vilka fält** du vill visa. Vi vill ha tre: **namnet** (`name`), **numret** (`id`) och **bilden** (`image`). I koden når vi varje fält med en punkt: `**data.name`**, `**data.id**`, `**data.image**`.

---

# Part 2 — Build a page that reads the API / Bygg en sida som läser API:et

## Step 5 — Create the file / Steg 5 — Skapa filen

**English**

1. In VS Code, open (or create) a project folder, e.g. `character-api`.
2. Create a new file called `index.html`.
3. Type in the basic HTML skeleton:

**Svenska**

1. I VS Code, öppna (eller skapa) en projektmapp, t.ex. `character-api`.
2. Skapa en ny fil som heter `index.html`.
3. Skriv in HTML-grundramen:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Character Card</title>
  </head>
  <body>
    <!-- Our content will go here -->
  </body>
</html>
```

---

## Step 6 — Add places to show the result / Steg 6 — Lägg till platser för resultatet

**English**
Inside `<body>` (replace the comment), add a heading, an empty image, and a paragraph for the number. They start empty — JavaScript will fill them in.

**Svenska**
Inuti `<body>` (ersätt kommentaren), lägg till en rubrik, en tom bild och ett stycke för numret. De börjar tomma — JavaScript fyller i dem.

```html
<h1 id="name">Loading… 🛸</h1>
<img id="photo" alt="Character picture" width="300">
<p id="number"></p>
```

**What each part is / Vad varje del är:**

- `id="name"` — a label so JS can find this heading — *en etikett så JS kan hitta rubriken*
- `id="photo"` — a label so JS can find this image — *en etikett så JS kan hitta bilden*
- `id="number"` — a label so JS can find this paragraph — *en etikett så JS kan hitta stycket*

> 💾 Save and open with **Live Server** (or double-click the file). You'll see the heading, but no data yet.
> *Spara och öppna med **Live Server** (eller dubbelklicka på filen). Du ser rubriken, men ingen data än.*

---

## Step 7 — Add the fetch script / Steg 7 — Lägg till fetch-skriptet

**English**
Now the magic. Add this `<script>` **just before** the closing `</body>` tag:

**Svenska**
Nu magin. Lägg till detta `<script>` **precis före** den avslutande `</body>`-taggen:

```html
<script>
  async function getCharacter() {
    const response = await fetch("https://rickandmortyapi.com/api/character/1"); // ask the API
    const data = await response.json();  // turn the JSON text into usable data
    console.log(data);                   // print the whole response to inspect it
  }

  getCharacter();
</script>
```

**English**
Save and refresh. Nothing new appears **on the page yet** — but the data is arriving. Let's check.

**Svenska**
Spara och ladda om. Inget nytt syns **på sidan än** — men datan kommer in. Vi kollar.

---

## Step 8 — Inspect it in the Console / Steg 8 — Inspektera i Console

**English**

1. Right-click the page → **Inspect** (or press `F12`).
2. Click the **Console** tab.
3. You'll see the whole object we logged. Find `name`, `id`, and `image` inside it.

**Svenska**

1. Högerklicka på sidan → **Inspektera** (eller tryck `F12`).
2. Klicka på fliken **Console**.
3. Du ser hela objektet vi loggade. Hitta `name`, `id` och `image` i det.

> 👀 This confirms the data arrived and shows the exact field names — the same ones we saw in the browser in Part 1.
> *Detta bekräftar att datan kom fram och visar de exakta fältnamnen — samma som vi såg i webbläsaren i Del 1.*

---

## Step 9 — Show the content on the page / Steg 9 — Visa innehållet på sidan

**English**
Now use the fields. Add **three lines** inside the function, after the `console.log`:

**Svenska**
Använd nu fälten. Lägg till **tre rader** i funktionen, efter `console.log`:

```html
<script>
  async function getCharacter() {
    const response = await fetch("https://rickandmortyapi.com/api/character/1");
    const data = await response.json();
    console.log(data);

    document.getElementById("name").textContent = data.name;        // show the name
    document.getElementById("photo").src = data.image;              // show the picture
    document.getElementById("number").textContent = "Number: " + data.id; // show the number
  }

  getCharacter();
</script>
```

**What's happening / Vad som händer:**

- `getElementById("name").textContent = data.name` — put the name in the heading — *lägg namnet i rubriken*
- `getElementById("photo").src = data.image` — set the image's `src` to the link — *sätt bildens `src` till länken*
- `getElementById("number").textContent = "Number: " + data.id` — show the number — *visa numret*

> ▶️ Save and refresh — **the character's name, picture, and number appear!** 🎉
> *Spara och ladda om — **karaktärens namn, bild och nummer dyker upp!***

---

## The complete page / Den färdiga sidan

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Character Card</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        text-align: center;
        margin: 40px auto;
        max-width: 500px;
        background-color: #f5f7fb;
        color: #333;
      }
      h1 { color: #2b6cb0; }
      img { border-radius: 12px; margin-top: 20px; }
      #number { font-size: 18px; color: #555; }
    </style>
  </head>
  <body>
    <h1 id="name">Loading… 🛸</h1>
    <img id="photo" alt="Character picture" width="300">
    <p id="number"></p>

    <script>
      async function getCharacter() {
        const response = await fetch("https://rickandmortyapi.com/api/character/1");
        const data = await response.json();
        console.log(data);

        document.getElementById("name").textContent = data.name;
        document.getElementById("photo").src = data.image;
        document.getElementById("number").textContent = "Number: " + data.id;
      }

      getCharacter();
    </script>
  </body>
</html>
```

---

## Now make it yours / Gör den till din

**English**

- **Change the character:** in the fetch URL, change the number at the end (`/character/2`, `/3`, `/10`…). That number is a **parameter** — it tells the API *which* character you want.
- Show **two more fields** you saw in the console, e.g. `data.status` (Alive/Dead) and `data.species` (Human, Alien…).
- Change the colors and the heading text.
- **Try a different API!** Open it in the browser first (Part 1), find a field, then show it:
  - 🐶 Dog CEO — `https://dog.ceo/api/breeds/image/random` (image in `message`)
  - 🐱 TheCatAPI — `https://api.thecatapi.com/v1/images/search` (a list — image in `data[0].url`)
  - 🎲 Bored API — an activity idea — *en aktivitetsidé*

**Svenska**

- **Byt karaktär:** i fetch-URL:en, ändra numret i slutet (`/character/2`, `/3`, `/10`…). Det numret är en **parameter** — det talar om för API:et *vilken* karaktär du vill ha.
- Visa **två fält till** som du såg i konsolen, t.ex. `data.status` (Alive/Dead) och `data.species` (Human, Alien…).
- Ändra färgerna och rubriktexten.
- **Prova ett annat API!** Öppna det i webbläsaren först (Del 1), hitta ett fält, visa det sedan:
  - 🐶 Dog CEO — `https://dog.ceo/api/breeds/image/random` (bild i `message`)
  - 🐱 TheCatAPI — `https://api.thecatapi.com/v1/images/search` (en lista — bild i `data[0].url`)
  - 🎲 Bored API — en aktivitetsidé

---

## Step 10 — Improve it with AI (Cline) / Steg 10 — Förbättra den med AI (Cline)

**English**
Now that you understand every line, let the AI help you make it better. Open the **Cline** chat in VS Code (the Cline icon in the left sidebar), make sure your `index.html` is open, and describe **one change at a time**. Read each change before you accept it.

**Svenska**
Nu när du förstår varje rad, låt AI:n hjälpa dig göra den bättre. Öppna **Cline**-chatten i VS Code (Cline-ikonen i vänstra sidofältet), se till att din `index.html` är öppen, och beskriv **en ändring i taget**. Läs varje ändring innan du accepterar den.

**Example prompts / Exempel-prompts:**

```text
Make my character page look nicer: put the name, image, and number inside a centered card with rounded corners and a soft shadow.
```

```text
Add a button that says "Random character". When clicked, it should fetch a random character (id between 1 and 826) and update the page.
```

```text
Also show the character's status and species under the image.
```

```text
Show a friendly "Loading…" message while the data is being fetched, and a nice error message if the request fails.
```

```text
Explain what each line of the <script> does with a short comment, so I can understand it.
```

> 🏅 **Golden rule / Gyllene regel:** you must be able to **explain** what the AI added. If you can't, ask it: *"Explain this line to me."*
> *Du måste kunna **förklara** vad AI:n lade till. Om du inte kan, fråga den: "Förklara den här raden för mig."*

> 💡 Change **one thing at a time** and refresh after each — that way you always know what changed.
> *Ändra **en sak i taget** och ladda om efter varje — så vet du alltid vad som ändrades.*

---

## Recap / Sammanfattning

**English**

- You opened an API in the **browser** and read its **JSON** — you saw the raw data first.
- You used `**fetch**` to send a request and `**await**` to wait for the response.
- `**response.json()**` turned the text into usable data; `**console.log**` let you inspect it.
- You read **three fields** (`data.name`, `data.id`, `data.image`) and showed them on the page — ignoring the fields you didn't need.

The journey: **your page → request → API/server → JSON response → read the fields → show them.** 🚀

**Svenska**

- Du öppnade ett API i **webbläsaren** och läste dess **JSON** — du såg rådatan först.
- Du använde `**fetch**` för att skicka en förfrågan och `**await**` för att vänta på svaret.
- `**response.json()**` gjorde texten till användbar data; `**console.log**` lät dig inspektera den.
- Du läste **tre fält** (`data.name`, `data.id`, `data.image`) och visade dem på sidan — och struntade i fälten du inte behövde.

Resan: **din sida → förfrågan → API/server → JSON-svar → läs fälten → visa dem.** 🚀
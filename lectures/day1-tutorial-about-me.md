# Tutorial — Build an "About Me" Page by Hand

# Handledning — Bygg en "Om mig"-sida för hand

> **Day 1 hands-on (no AI yet) / Dag 1 praktiskt (ingen AI än)**
> Follow these steps to build a simple personal page with **HTML**, a little **CSS**, and **one** piece of **JavaScript**. Type it yourself — that's how you'll recognize what the AI writes later.
>
> Följ dessa steg för att bygga en enkel personlig sida med **HTML**, lite **CSS**, och **en** bit **JavaScript**. Skriv det själv — så känner du igen det AI:n skriver senare.

---

## What you'll build / Vad du ska bygga

**English** — A single page with your name, a photo, a short intro, a list of hobbies, and a button that reveals a fun fact when clicked.

**Svenska** — En sida med ditt namn, ett foto, en kort intro, en lista med hobbies, och en knapp som visar ett roligt faktum när man klickar.

**You need / Du behöver:** VS Code + a web browser. *(VS Code + en webbläsare.)*

---



## Step 0 — Create the file / Steg 0 — Skapa filen

**English**

1. In VS Code, open a folder for your project (e.g. `about-me`).
2. Create a new file called `**index.html**`.
3. `index.html` is the special name browsers look for first — it's your page's home.

**Svenska**

1. Öppna en mapp för ditt projekt i VS Code (t.ex. `about-me`).
2. Skapa en ny fil som heter `**index.html**`.
3. `index.html` är det speciella namn webbläsare letar efter först — det är sidans startpunkt.

---



## Step 1 — The HTML skeleton / Steg 1 — HTML-skelettet

**English**
Every page starts with the same basic frame. Type this into `index.html`:

**Svenska**
Varje sida börjar med samma grundram. Skriv detta i `index.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>About Me</title>
  </head>
  <body>
    <!-- Our content will go here -->
  </body>
</html>
```

**What each part means / Vad varje del betyder:**

- `<!DOCTYPE html>` — "this is a modern web page." *("detta är en modern webbsida.")*
- `<head>` — hidden info about the page (title, settings). *(dold info om sidan.)*
- `<body>` — everything you actually see goes here. *(allt du faktiskt ser hamnar här.)*

> ▶️ **Open it in your browser (from VS Code):** right-click `index.html` in the Explorer panel on the left → **"Reveal in File Explorer"** (Windows) / **"Reveal in Finder"** (macOS), then double-click the file. It'll look empty for now.
> *Öppna den i webbläsaren (från VS Code): högerklicka på* `index.html` *i Utforskar-panelen till vänster → **"Reveal in File Explorer"** (Windows) / **"Reveal in Finder"** (macOS), och dubbelklicka sedan på filen. Den ser tom ut just nu.*
>
> 💡 **Even easier / Ännu enklare:** install the **Live Server** extension in VS Code, then right-click `index.html` → **"Open with Live Server"**. It opens the page and **auto-refreshes** every time you save.
> *Installera tillägget **Live Server** i VS Code, högerklicka sedan på `index.html` → **"Open with Live Server"**. Den öppnar sidan och **uppdaterar automatiskt** varje gång du sparar.*

---



## Step 2 — Add your content (HTML) / Steg 2 — Lägg till innehåll (HTML)

**English**
Put this **inside** the `<body>` tags (replace the comment). Change the text to be about *you*:

**Svenska**
Lägg detta **inuti** `<body>`-taggarna (ersätt kommentaren). Ändra texten så att den handlar om *dig*:

```html
<h1>Hi, I'm Amir 👋</h1>

<p>I'm 16 years old and I live in Stockholm.
   This summer I'm learning to build websites!</p>

<h2>My hobbies</h2>
<ul>
  <li>⚽ Football</li>
  <li>🎮 Video games</li>
  <li>📚 Reading</li>
</ul>
```

**New tags / Nya taggar:**

- `<h1>` big heading, `<h2>` smaller heading — *stor / mindre rubrik*
- `<p>` a paragraph of text — *ett textstycke*
- `<ul>` + `<li>` an unordered list and its items — *en lista + dess punkter*

> 💾 **Save (**`Ctrl/Cmd + S`**) and refresh the browser** to see your changes. *(With Live Server, it refreshes for you.)*
> *Spara (*`Ctrl/Cmd + S`*) och ladda om webbläsaren för att se ändringarna. (Med Live Server uppdateras den åt dig.)*

---



## Step 3 — Add a photo / Steg 3 — Lägg till ett foto

**English**
Now add an image. Put this right under your `<h1>`:

**Svenska**
Lägg nu till en bild. Placera detta precis under din `<h1>`:

```html
<img src="https://picsum.photos/200" alt="A photo of me" width="200">
```

**What each part means / Vad varje del betyder:**

- `<img>` shows an image — *visar en bild*
- `src` = where the image comes from — *varifrån bilden kommer*
- `alt` = a description (shown if the image can't load) — *en beskrivning (visas om bilden inte laddas)*
- `width` = its size in pixels — *storleken i pixlar*

> `https://picsum.photos/200` gives a random placeholder photo. Later you can use your own file → `src="photo.jpg"`.
> `https://picsum.photos/200` *ger ett slumpmässigt platshållarfoto. Senare kan du använda din egen fil →* `src="photo.jpg"`*.*
>
> 💾 Save and refresh — your photo appears! *(Spara och ladda om — ditt foto dyker upp!)*

---



## Step 4 — Add a table / Steg 4 — Lägg till en tabell

**English**
A **table** is great for showing info in rows and columns. Add this inside `<body>`, after your hobbies list:

**Svenska**
En **tabell** är bra för att visa info i rader och kolumner. Lägg detta inuti `<body>`, efter din hobbylista:

```html
<h2>Languages I speak</h2>
<table>
  <tr>
    <th>Language</th>
    <th>Level</th>
  </tr>
  <tr>
    <td>Arabic</td>
    <td>Native</td>
  </tr>
  <tr>
    <td>Swedish</td>
    <td>Native</td>
  </tr>
  <tr>
    <td>English</td>
    <td>Good</td>
  </tr>
</table>
```

**New tags / Nya taggar:**

- `<table>` the whole table — *hela tabellen*
- `<tr>` a table row (**t**able **r**ow) — *en rad*
- `<th>` a header cell, shown bold — *en rubrikcell (fet stil)*
- `<td>` a normal data cell — *en vanlig datacell*

> Each `<tr>` is one row; the cells inside it are its columns. Right now it looks plain — we'll style it in the CSS step.
> *Varje* `<tr>` *är en rad; cellerna i den är kolumnerna. Just nu ser den enkel ut — vi stylar den i CSS-steget.*

---



## Step 5 — Add your GitHub link / Steg 5 — Lägg till din GitHub-länk

**English**
Let's link to **your GitHub profile** (the account you created during setup). Add this inside `<body>`:

**Svenska**
Nu länkar vi till **din GitHub-profil** (kontot du skapade under förberedelserna). Lägg detta inuti `<body>`:

```html
<p>
  Check out my code on
  <a href="https://github.com/your-username" target="_blank">my GitHub</a>!
</p>
```

**English**

- Replace `your-username` with **your** real GitHub username.
- `<a href="...">` creates a **link**; `target="_blank"` opens it in a **new tab**.

**Svenska**

- Byt ut `your-username` mot **ditt** riktiga GitHub-användarnamn.
- `<a href="...">` skapar en **länk**; `target="_blank"` öppnar den i en **ny flik**.

> 🔗 Links are how pages connect to each other — that's the heart of the "web"!
> *Länkar är hur sidor kopplas ihop — det är själva hjärtat i "webben"!*

---



## Step 6 — Make it look nice (a little CSS) / Steg 6 — Gör den snygg (lite CSS)

**English**
CSS controls how things **look**. Add this `<style>` block **inside** the `<head>`, right before `</head>`:

**Svenska**
CSS styr hur saker **ser ut**. Lägg detta `<style>`-block **inuti** `<head>`, precis före `</head>`:

```html
<style>
  body {
    font-family: Arial, sans-serif;
    max-width: 600px;
    margin: 40px auto;      /* center the page */
    padding: 0 20px;
    text-align: center;
    background-color: #f5f7fb;
    color: #333;
  }
  h1 { color: #2b6cb0; }
  img { border-radius: 50%; } /* make the photo a circle */
  ul { list-style: none; padding: 0; }
  li { font-size: 18px; margin: 6px 0; }
  table { margin: 20px auto; border-collapse: collapse; }
  th, td { border: 1px solid #cbd5e0; padding: 8px 16px; }
  th { background-color: #2b6cb0; color: white; }
</style>
```

**How CSS works / Hur CSS fungerar:**

- You pick an element (like `h1`) and set properties (like `color`).
*Du väljer ett element (som* `h1`*) och sätter egenskaper (som* `color`*).*
- Try changing a color or number and refresh — see what happens!
*Ändra en färg eller siffra och ladda om — se vad som händer!*

---



## Step 7 — Add ONE bit of JavaScript / Steg 7 — Lägg till EN bit JavaScript

**English**
JavaScript makes the page **do things**. We'll add a button that shows a fun fact when clicked.

1. Add this **inside** `<body>`, after your list:

**Svenska**
JavaScript får sidan att **göra saker**. Vi lägger till en knapp som visar ett roligt faktum vid klick.

1. Lägg detta **inuti** `<body>`, efter din lista:

```html
<button onclick="showFunFact()">Show a fun fact about me</button>

<p id="fact"></p>
```

**English**
2. Then add this `<script>` block just before the closing `</body>` tag:

**Svenska**
2. Lägg sedan detta `<script>`-block precis före den avslutande `</body>`-taggen:

```html
<script>
  function showFunFact() {
    document.getElementById("fact").textContent =
      "🎉 Fun fact: I once built a game in a single day!";
  }
</script>
```

**What's happening / Vad som händer:**

- `onclick="showFunFact()"` — when the button is clicked, run this function.
*när knappen klickas, kör den här funktionen.*
- `getElementById("fact")` — find the empty `<p id="fact">`.
*hitta det tomma* `<p id="fact">`*.*
- `.textContent = "..."` — put text inside it.
*lägg text i det.*

> ▶️ Save, refresh, and click the button. Your page now **reacts** to you! 🎉
> *Spara, ladda om, och klicka på knappen. Din sida **reagerar** nu på dig!*

---



## The complete page / Den färdiga sidan

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>About Me</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        max-width: 600px;
        margin: 40px auto;
        padding: 0 20px;
        text-align: center;
        background-color: #f5f7fb;
        color: #333;
      }
      h1 { color: #2b6cb0; }
      img { border-radius: 50%; }
      ul { list-style: none; padding: 0; }
      li { font-size: 18px; margin: 6px 0; }
      table { margin: 20px auto; border-collapse: collapse; }
      th, td { border: 1px solid #cbd5e0; padding: 8px 16px; }
      th { background-color: #2b6cb0; color: white; }
    </style>
  </head>
  <body>
    <h1>Hi, I'm Amir 👋</h1>

    <img src="https://picsum.photos/200" alt="A photo of me" width="200">

    <p>I'm 16 years old and I live in Stockholm.
       This summer I'm learning to build websites!</p>

    <h2>My hobbies</h2>
    <ul>
      <li>⚽ Football</li>
      <li>🎮 Video games</li>
      <li>📚 Reading</li>
    </ul>

    <h2>Languages I speak</h2>
    <table>
      <tr>
        <th>Language</th>
        <th>Level</th>
      </tr>
      <tr>
        <td>Arabic</td>
        <td>Native</td>
      </tr>
      <tr>
        <td>Swedish</td>
        <td>Intermediate</td>
      </tr>
      <tr>
        <td>English</td>
        <td>Good</td>
      </tr>
    </table>

    <p>
      Check out my code on
      <a href="https://github.com/your-username" target="_blank">my GitHub</a>!
    </p>

    <button onclick="showFunFact()">Show a fun fact about me</button>
    <p id="fact"></p>

    <script>
      function showFunFact() {
        document.getElementById("fact").textContent =
          "🎉 Fun fact: I once built a game in a single day!";
      }
    </script>
  </body>
</html>
```

---



## Now make it yours / Gör den till din

> 🔒 **Important — this page will be published on the internet later!**
> Use only your **first name**. **Do NOT** add your real photo, last name, address, phone number, school, or any other personal/sensitive info. **Keep the placeholder picture** (`https://picsum.photos/200`).
> *Viktigt — den här sidan kommer att publiceras på internet senare! Använd bara ditt **förnamn**. Lägg **INTE** till ditt riktiga foto, efternamn, adress, telefonnummer, skola eller annan personlig/känslig info. **Behåll platshållarbilden** (*`https://picsum.photos/200`*).*

**English**

- Change the text, hobbies, and the fun fact to be about you — but use your **first name only**.
- **Keep the placeholder image as it is** — don't use your own photo (this page will be public).
- Update the table with safe, non-sensitive rows (e.g. languages, favorite games), and make the GitHub link point to **your** real username.
- Try new colors in the CSS.
- **Bonus:** add a second `<h2>` section (e.g. "My favorite foods").

**Svenska**

- Ändra texten, hobbies och det roliga faktumet så det handlar om dig — men använd bara ditt **förnamn**.
- **Behåll platshållarbilden som den är** — använd inte ditt eget foto (sidan blir offentlig).
- Uppdatera tabellen med säkra, icke-känsliga rader (t.ex. språk, favoritspel), och låt GitHub-länken peka på **ditt** riktiga användarnamn.
- Prova nya färger i CSS:en.
- **Bonus:** lägg till ett andra `<h2>`-avsnitt (t.ex. "Min favoritmat").

---



## Step 8 — Put your page online (GitHub Pages) / Steg 8 — Lägg din sida online (GitHub Pages)

**English**
Your page only lives on your computer so far. Let's put it on the internet so you can share the link with your family and friends! We'll do it **manually** through the GitHub website — you'll learn the "real" GitHub way with Git on **Day 5**.

**Svenska**
Hittills bor din sida bara på din dator. Nu lägger vi den på internet så att du kan dela länken med familj och vänner! Vi gör det **manuellt** via GitHub-webbsidan — du lär dig det "riktiga" GitHub-sättet med Git på **Dag 5**.

### 8a. Create a new repository / Skapa ett nytt repository

**English**

1. Go to [github.com](https://github.com) and **sign in** (create a free account if you don't have one yet).
2. Click the **+** button in the top-right corner → **New repository**.
3. **Repository name:** type `about-me`.
4. Make sure it is set to **Public** (so the world can see your page).
5. Tick **Add a README file**.
6. Click **Create repository**.

**Svenska**

1. Gå till [github.com](https://github.com) och **logga in** (skapa ett gratis konto om du inte redan har ett).
2. Klicka på **+**-knappen uppe till höger → **New repository**.
3. **Repository name:** skriv `about-me`.
4. Se till att den är inställd på **Public** (så att hela världen kan se din sida).
5. Kryssa i **Add a README file**.
6. Klicka på **Create repository**.



### 8b. Upload your file / Ladda upp din fil

**English**

1. In your new repository, click **Add file** → **Upload files**.
2. Open your project folder on your computer, and **drag** `index.html` into the browser window. *(If you use your own photo file, drag that in too!)*
3. Scroll down and click the green **Commit changes** button.

**Svenska**

1. I ditt nya repository, klicka på **Add file** → **Upload files**.
2. Öppna din projektmapp på datorn och **dra** `index.html` in i webbläsarfönstret. *(Om du använder ditt eget fotografi, dra in det också!)*
3. Skrolla ner och klicka på den gröna knappen **Commit changes**.

> ⚠️ The file **must** be named `index.html` so GitHub Pages knows it's your home page.
> *Filen **måste** heta* `index.html` *så att GitHub Pages vet att det är din startsida.*



### 8c. Turn on GitHub Pages / Slå på GitHub Pages

**English**

1. In your repository, click the **Settings** tab (top of the page).
2. In the left menu, click **Pages**.
3. Under **Branch**, choose **main** and the **/ (root)** folder, then click **Save**.
4. Wait about 1–2 minutes and refresh the page. GitHub shows a link like:
  `https://your-username.github.io/about-me/`
5. Open that link — **your page is live on the internet!** 🎉 Share it in the WhatsApp group!

**Svenska**

1. I ditt repository, klicka på fliken **Settings** (högst upp).
2. I menyn till vänster, klicka på **Pages**.
3. Under **Branch**, välj **main** och mappen **/ (root)**, klicka sedan på **Save**.
4. Vänta ca 1–2 minuter och ladda om sidan. GitHub visar en länk som:
  `https://ditt-användarnamn.github.io/about-me/`
5. Öppna länken — **din sida är live på internet!** 🎉 Dela den i WhatsApp-gruppen!

> 💡 Want to change something later? Upload the new `index.html` the same way (**Add file → Upload files**), commit, and your live page updates automatically after a minute.
> *Vill du ändra något senare? Ladda upp den nya* `index.html` *på samma sätt, committa, så uppdateras din live-sida automatiskt efter en minut.*

---



## Recap / Sammanfattning

**English**

- **HTML** gave your page **structure** (headings, text, image, list, table, link).
- **CSS** gave it **style** (colors, font, layout).
- **JavaScript** gave it **behavior** (the button that reacts).
- **GitHub Pages** put your page **online** for the whole world to see.

You just built a real web page **by hand** and **published it on the internet** — now you'll recognize these parts when the AI writes them! 🚀

**Svenska**

- **HTML** gav sidan **struktur** (rubriker, text, bild, lista, tabell, länk).
- **CSS** gav den **stil** (färger, typsnitt, layout).
- **JavaScript** gav den **beteende** (knappen som reagerar).
- **GitHub Pages** la din sida **online** så att hela världen kan se den.

Du byggde precis en riktig webbsida **för hand** och **publicerade den på internet** — nu känner du igen dessa delar när AI:n skriver dem! 🚀
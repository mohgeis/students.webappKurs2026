---
marp: true
theme: default
paginate: true
size: 16:9
title: "Day 1 — How the Web Works, Your First Web Page & Vibe Coding with AI"
---

<!-- _class: lead -->
<!-- _paginate: false -->

# Day 1

## How the Web Works, Your First Web Page & Vibe Coding with AI

*Dag 1 — Hur webben fungerar, din första webbsida & vibe coding med AI*

Summer Coding Course for Youth · Sudanese Association
*Sommarkurs i kodning för unga · Sudanesiska föreningen*

---

## Welcome! Let's meet each other 👋
## Välkommen! Låt oss lära känna varandra

When it's your turn, tell us: *När det är din tur, berätta:*

- **Your name** — *Ditt namn*
- **Where you are** (city) — *Var du är (stad)*
- **What you'd love to build** or why you joined — *Vad du vill bygga / varför du är här*
- **A fun fact** about you 🎉 — *Ett roligt faktum om dig*

> No coding experience needed — everyone is welcome here.
> *Ingen kodningserfarenhet behövs — alla är välkomna här.*

---

## Today / Idag

1. How the web works — *Hur webben fungerar*
2. The 3 building blocks: HTML, CSS, JS — *De 3 byggstenarna*
3. Build a page **by hand** — *Bygg en sida för hand*
4. What AI is & "vibe coding" — *Vad AI är & "vibe coding"*
5. Build a page **with AI** — *Bygg en sida med AI*

> We start with **building**, not installing. The AI setup comes later today. 🚀
> *Vi börjar med att **bygga**, inte installera. AI-setup kommer senare idag.*

---

## Today's goal / Dagens mål

By the end of today, you can:
*I slutet av idag kan du:*

- Explain the main parts of the web — *förklara webbens huvuddelar*
- Name HTML, CSS, and JS and what each does — *namnge HTML, CSS, JS*
- Write a simple page **by hand** — *skriva en enkel sida för hand*
- Say what AI, an LLM, and "vibe coding" are — *förklara AI, LLM & vibe coding*
- Build an "About Me" page **with AI** — *bygga en "Om mig"-sida med AI*

---

<!-- _class: lead -->

# Part 1 — How the Web Works
## Del 1 — Hur webben fungerar

🌐

---

## Two computers talking / Två datorer som pratar

When you open a website, two computers talk to each other:
*När du öppnar en webbplats pratar två datorer med varandra:*

- **Client / Klient** — your device (the browser). It **asks**.
  *din enhet (webbläsaren). Den **frågar**.*
- **Server** — a computer elsewhere that **stores** the site and **answers**.
  *en dator någon annanstans som **lagrar** sidan och **svarar**.*

---

## Request & Response / Förfrågan & Svar

- **Request / Förfrågan:** the message the client sends
  *"please give me this page"*
- **Response / Svar:** what the server sends back
  *the page, an image, some data*

🍽️ **Restaurant analogy / Restaurang-liknelse**
You (**client**) order from the **menu** → the kitchen (**server**) cooks → the waiter brings your food (**response**).
*Du (**klient**) beställer från **menyn** → köket (**servern**) lagar → servitören kommer med maten (**svaret**).*

---

## Your turn: find the pattern 🔎
## Din tur: hitta mönstret

Discuss in pairs — how is each one like the web?
*Diskutera i par — hur liknar var och en webben?*

- 📚 Asking a **librarian** for a book — *Be en **bibliotekarie** om en bok*
- 🍕 **Ordering pizza** by phone — *Beställa **pizza** på telefon*
- 🏧 Using an **ATM** or a **vending machine** — *Använda en **bankomat** eller **varuautomat***
- 💬 **Texting** a friend a question — *Skicka ett **sms** med en fråga*

> For each one: who is the **client**? who is the **server**? what's the **request** and the **response**?
> *För var och en: vem är **klienten**? vem är **servern**? vad är **förfrågan** och **svaret**?*

---

## Frontend vs. Backend

- **Frontend** — the part you **see and click** in the browser
  *delen du **ser och klickar på** i webbläsaren*
  → HTML, CSS, JS
- **Backend** — the hidden part **on the server** (logic, databases)
  *den dolda delen **på servern** (logik, databaser)*

> This week we mostly work on the **frontend**.
> *Den här veckan jobbar vi mest med **frontend**.*

---

## Web page vs. Web app / Webbsida vs. Webbapp

- **Web page / Webbsida** — mostly shows **information** to read or look at
  *visar mest **information** att läsa eller titta på*
  e.g. an article, an "About Me" page — *t.ex. en artikel, en "Om mig"-sida*
- **Web app / Webbapp** — a page you **interact with**; it **does things**
  *en sida du **interagerar med**; den **gör saker***
  e.g. search, buttons, live data — *t.ex. sök, knappar, livedata*

> The difference is **interactivity**: an app responds to you (often with **JS + data/APIs**).
> *Skillnaden är **interaktivitet**: en app svarar på dig (ofta med **JS + data/API:er**).*
>
> This week: start with a **page**, then build real **web apps**. 🚀
> *Denna vecka: börja med en **sida**, bygg sen riktiga **webbappar**.*

---

<!-- _class: lead -->

# Part 2 — The 3 Building Blocks
## Del 2 — De 3 byggstenarna

`HTML` · `CSS` · `JS`

---

## HTML, CSS, JS — one job each / en uppgift var

| Part | Job / Uppgift | Like a house / Som ett hus |
|------|---------------|----------------------------|
| **HTML** | Structure / **Struktur** | Walls & rooms / Väggar & rum |
| **CSS** | Style / **Stil** | Paint & furniture / Färg & möbler |
| **JS** | Behavior / **Beteende** | Electricity / Elen |

> HTML = structure, CSS = style, JS = behavior.
> *HTML = struktur, CSS = stil, JS = beteende.*

---

## A tiny example / Ett litet exempel

```html
<!-- HTML: structure -->
<h1 id="title">Hello!</h1>
<button onclick="changeTitle()">Click me</button>

<!-- CSS: style -->
<style>
  #title { color: hotpink; font-family: sans-serif; }
</style>

<!-- JS: behavior -->
<script>
  function changeTitle() {
    document.getElementById("title").textContent = "You clicked it!";
  }
</script>
```

---

<!-- _class: lead -->

# 🛠️ Exercise: Build a page by hand
## Övning: Bygg en sida för hand

*(no AI yet / ingen AI än)*

---

## Build it yourself / Bygg den själv

1. Create a file `index.html` — *Skapa filen `index.html`*
2. Add a heading, a paragraph, and a list — *rubrik, stycke, lista*
3. Open it in your browser — *Öppna den i webbläsaren*
4. Add a little CSS (a color, a font) — *Lägg till lite CSS*

> Why by hand? So you **recognize** what the AI writes next — and can check it.
> *Varför för hand? Så att du **känner igen** det AI:n skriver sen — och kan kontrollera det.*

---

<!-- _class: lead -->

# Part 3 — What is AI?
## Del 3 — Vad är AI?

🤖

---

## AI & LLMs / AI & språkmodeller

- **AI** = software that **learns patterns from examples**
  *programvara som **lär sig mönster från exempel***
- **LLM (Large Language Model)** = trained on huge text; its trick is to **predict the next word**
  *tränad på enorm text; tricket är att **förutsäga nästa ord***

> This powers ChatGPT, Claude, and AI coding tools like Cursor / Cline.
> *Detta driver ChatGPT, Claude och AI-kodverktyg som Cursor / Cline.*

---

## Great at / Watch out for
## Bra på / Se upp för

✅ **Great at:** drafting code & text, explaining, boilerplate, a fast start
*utkast av kod & text, förklara, en snabb start*

⚠️ **Watch out:** it can be **confidently wrong** — a **hallucination**
*den kan ha **fel med självförtroende** — en **hallucination***

> Always **check** what it produces. *Kontrollera alltid det den skapar.*

---

## AI is your partner / AI är din partner

- The AI is a **coding partner** — *en **kodpartner***
- **You** stay in charge: review its work, own the result
  ***Du** bestämmer: granska arbetet, äg resultatet*

> An LLM **guesses what's likely** — it doesn't "know" facts like a database.
> *En LLM **gissar vad som är troligt** — den "vet" inte fakta som en databas.*

---

## "Vibe coding" — what it is / vad det är

- Describe what you want in **plain language**, the AI writes much of the code
  *Beskriv vad du vill ha på **vanligt språk**, AI:n skriver mycket av koden*
- **IS:** directing, reading, testing, fixing — *styra, läsa, testa, fixa*
- **IS NOT:** blindly copy-pasting — *inte blint kopiera*

> 🏅 **Golden rule / Gyllene regel:** You must be able to **explain your code**.
> *Du måste kunna **förklara din kod**.*

---

## Tool tour / Verktygsrundtur

The loop you'll use all week: *Loopen du använder hela veckan:*

1. **Prompt** — tell the AI what you want
2. **Review** — read the change before accepting
3. **Accept or reject** — keep good, discard bad
4. **Undo** — if it breaks, undo & try a clearer prompt

> Don't be afraid to break things. *Var inte rädd för att ha sönder saker.*

---

<!-- _class: lead -->

# 🤖 Build with AI: "About Me"
## Bygg med AI: "Om mig"

---

## Now build it with AI / Nu bygger vi med AI

- Describe your page to the AI (name, intro, interests)
  *Beskriv din sida för AI:n (namn, intro, intressen)*
- Ask it to **change colors**, then **add a section** — read each change
  *Be den **ändra färger**, **lägg till ett avsnitt** — läs varje ändring*
- Compare with your hand-made page: spot the HTML, CSS, JS
  *Jämför med din handgjorda sida: hitta HTML, CSS, JS*

```text
Create a simple one-page "About Me" website with my name as a big
heading, a short intro, and a list of three hobbies. Clean, colorful style.
```

---

## Independent challenge / Egen utmaning

Add a **new section the AI didn't suggest**
*Lägg till ett **nytt avsnitt AI:n inte föreslog***

- e.g. a favorite quote, a photo, a "contact me" line
  *t.ex. ett citat, en bild, en "kontakta mig"-rad*
- Then **explain each part of the HTML** to a partner
  *Förklara sedan **varje del av HTML:en** för en kompis*

---

## Recap — can you answer? / Kan du svara?

1. Client vs. server? — *Klient vs. server?*
2. What do HTML, CSS, JS each do? — *Vad gör HTML, CSS, JS?*
3. What is an LLM's core trick? — *En LLM:s grundtrick?*
4. What is "vibe coding" + the golden rule? — *"Vibe coding" + gyllene regeln?*

---

<!-- _class: lead -->

## Great work today! 🎉
## Bra jobbat idag!

**Next / Nästa:** Day 2 — Prompting an AI Well & Reading Its Code
*Dag 2 — Att prompta en AI bra & läsa dess kod*

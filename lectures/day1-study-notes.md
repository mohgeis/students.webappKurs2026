# Day 1 — How the Web Works, Your First Web Page & Vibe Coding with AI
# Dag 1 — Hur webben fungerar, din första webbsida & vibe coding med AI

> **How to use these notes / Så använder du dessa anteckningar**
> Read these after the lecture to recap. Each section is written in **English first**, then **Swedish (Svenska)**. Try to explain each idea out loud in your own words — if you can't, that's the part to re-read.
>
> Läs detta efter föreläsningen för att repetera. Varje avsnitt är skrivet **på engelska först**, sedan **på svenska**. Försök förklara varje idé högt med egna ord — om du inte kan, är det den delen du ska läsa om.

---

## Today's lesson plan / Dagens upplägg

**Total: 4 hours / 4 timmar** (a longer kickoff session, with two short breaks / ett längre startpass, med två korta pauser)

| Block / Moment | Time / Tid | What happens / Vad vi gör |
|----------------|-----------|----------------------------|
| **Welcome & today's goal**<br>*Välkomst & dagens mål* | 10 min | Meet everyone and hear today's goal in one sentence. (No setup yet — we jump straight into building.)<br>*Lär känna varandra och hör dagens mål i en mening. (Ingen installation än — vi hoppar rakt in i byggandet.)* |
| **Concept: How the web works**<br>*Koncept: Hur webben fungerar* | 25 min | Client/server/request/response, frontend vs. backend.<br>*Klient/server/förfrågan/svar, frontend vs. backend.* |
| **Concept: HTML/CSS/JS building blocks**<br>*Koncept: byggstenarna HTML/CSS/JS* | 25 min | The three building blocks of a page and what each one does.<br>*Sidans tre byggstenar och vad var och en gör.* |
| **Hands-on: build a basic page — by hand**<br>*Praktiskt: bygg en enkel sida — för hand* | 30 min | Write a small HTML page yourself (no AI yet) and open it in the browser.<br>*Skriv en liten HTML-sida själv (utan AI än) och öppna den i webbläsaren.* |
| **Break**<br>*Paus* | 10 min | Short rest.<br>*Kort paus.* |
| **Concept: What AI is & what "vibe coding" means**<br>*Koncept: Vad AI är & vad "vibe coding" betyder* | 30 min | What AI/LLMs are, good vs. bad at, and what vibe coding is (and isn't).<br>*Vad AI/LLM är, bra vs. dålig på, och vad vibe coding är (och inte är).* |
| **Setup help: get the AI working**<br>*Setup-hjälp: få igång AI:n* | 30 min | Now that you're excited to use it — make sure the AI tool runs. **Fix any setup** that didn't finish beforehand. Already working? Help a neighbour.<br>*Nu när du vill använda den — se till att AI-verktyget fungerar. **Fixa installationer** som inte blev klara i förväg. Funkar redan? Hjälp en granne.* |
| **Tool tour**<br>*Verktygsrundtur* | 15 min | Prompting, accepting/rejecting changes, and undo.<br>*Att prompta, acceptera/avvisa ändringar, och ångra.* |
| **Guided build: "About Me" page — with AI**<br>*Guidat bygge: "Om mig"-sida — med AI* | 30 min | Rebuild a nicer personal page with the AI, recognizing each part it writes.<br>*Bygg om en snyggare personlig sida med AI:n, och känn igen varje del den skriver.* |
| **Break**<br>*Paus* | 10 min | Short rest.<br>*Kort paus.* |
| **Independent challenge**<br>*Egen utmaning* | 15 min | Add a new section the AI didn't suggest, and explain the HTML to a partner.<br>*Lägg till ett nytt avsnitt AI:n inte föreslog, och förklara HTML:en för en kompis.* |
| **Wrap-up & share**<br>*Avslutning & dela* | 10 min | Show your page, name one thing you learned, and preview tomorrow.<br>*Visa din sida, nämn en sak du lärt dig, och en förhandstitt på imorgon.* |

> **Note / Obs:** Environment setup should be done **before** Day 1 (see `environment_setup/before_day1_setup.md`). The setup-help block comes **after the AI intro and before the AI hands-on**, so the day opens with energy and building — not troubleshooting. If setup runs long, the guided AI build and challenge can spill over into the start of Day 2.
> *Installationen bör göras **före** Dag 1 (se `environment_setup/before_day1_setup.md`). Setup-hjälpen kommer **efter AI-introt och före det praktiska AI-momentet**, så dagen börjar med energi och byggande — inte felsökning. Om installationen drar över kan det guidade AI-bygget och utmaningen fortsätta i början av Dag 2.*

---

## 1. What you'll be able to do after today / Vad du kan efter idag

**English**
- Describe the main parts of the web: client, server, request, response.
- Name the three building blocks of a web page: HTML, CSS, JavaScript.
- Write a simple web page **by hand** (HTML + a little CSS).
- Explain in one sentence what AI and a large language model (LLM) are.
- Understand what "vibe coding" means — and what it does *not* mean.
- Build an "About Me" page **with an AI assistant**, and recognize each part.

**Svenska**
- Beskriva webbens huvuddelar: klient, server, förfrågan (request), svar (response).
- Namnge de tre byggstenarna i en webbsida: HTML, CSS, JavaScript.
- Skriva en enkel webbsida **för hand** (HTML + lite CSS).
- Förklara med en mening vad AI och en stor språkmodell (LLM) är.
- Förstå vad "vibe coding" betyder — och vad det *inte* betyder.
- Bygga en "Om mig"-sida **med en AI-assistent**, och känna igen varje del.

---

## 2. How the web works / Hur webben fungerar

**English**
When you open a website, two computers talk to each other:

- **Client:** your device (the browser, e.g. Chrome/Safari). It **asks** for things.
- **Server:** a computer somewhere else that **stores** the website and **answers**.
- **Request:** the message the client sends ("please give me this page").
- **Response:** what the server sends back (the page, an image, some data).

Think of a restaurant: **you (client)** order from the **menu**, the **kitchen (server)** prepares it, and the **waiter** brings back your food (**response**).

- **Frontend** = the part you see and click in the browser (built with HTML, CSS, JS).
- **Backend** = the part on the server you *don't* see (logic, databases). We'll mostly work on the frontend in this course.

**Svenska**
När du öppnar en webbplats pratar två datorer med varandra:

- **Klient:** din enhet (webbläsaren, t.ex. Chrome/Safari). Den **ber om** saker.
- **Server:** en dator någon annanstans som **lagrar** webbplatsen och **svarar**.
- **Request (förfrågan):** meddelandet klienten skickar ("ge mig den här sidan, tack").
- **Response (svar):** det servern skickar tillbaka (sidan, en bild, lite data).

Tänk på en restaurang: **du (klienten)** beställer från **menyn**, **köket (servern)** lagar maten, och **servitören** kommer med maten (**svaret**).

- **Frontend** = delen du ser och klickar på i webbläsaren (byggd med HTML, CSS, JS).
- **Backend** = delen på servern som du *inte* ser (logik, databaser). I den här kursen jobbar vi mest med frontend.

> **Key idea / Nyckelidé:** The browser (client) asks; a server answers. A web page is just the response. / Webbläsaren (klienten) frågar; en server svarar. En webbsida är bara svaret.

---

## 3. The three building blocks of a web page / Webbsidans tre byggstenar

**English**
Every web page is made of three languages that each have a different job:

| Part | Job | Compare to a house |
|------|-----|--------------------|
| **HTML** | **Structure** — the content and its skeleton (headings, text, buttons, images) | The walls and rooms |
| **CSS** | **Style** — how it looks (colors, fonts, spacing, layout) | The paint and furniture |
| **JavaScript (JS)** | **Behavior** — what happens when you interact (clicks, changes, live data) | The electricity and moving parts |

A tiny example:

```html
<!-- HTML: structure -->
<h1 id="title">Hello!</h1>
<button onclick="changeTitle()">Click me</button>

<!-- CSS: style -->
<style>
  #title { color: hotpink; font-family: sans-serif; }
</style>

<!-- JavaScript: behavior -->
<script>
  function changeTitle() {
    document.getElementById("title").textContent = "You clicked it!";
  }
</script>
```

**Svenska**
Varje webbsida är gjord av tre språk som var och en har olika uppgift:

| Del | Uppgift | Jämför med ett hus |
|-----|---------|--------------------|
| **HTML** | **Struktur** — innehållet och dess skelett (rubriker, text, knappar, bilder) | Väggarna och rummen |
| **CSS** | **Stil** — hur det ser ut (färger, typsnitt, avstånd, layout) | Färgen och möblerna |
| **JavaScript (JS)** | **Beteende** — vad som händer när du interagerar (klick, ändringar, livedata) | Elen och de rörliga delarna |

(Samma kodexempel som ovan gäller på svenska — `<h1>` är strukturen, `#title { color: hotpink }` är stilen, och funktionen `changeTitle()` är beteendet.)

> **Remember / Kom ihåg:** HTML = structure, CSS = style, JS = behavior. / HTML = struktur, CSS = stil, JS = beteende.

---

## 4. Build a basic web page — by hand (no AI yet) / Bygg en enkel webbsida — för hand (utan AI än)

**English**
Before we bring in the AI, let's write a tiny page **ourselves**. This way, when the AI writes HTML for you later, you'll recognize the parts and can judge whether it did what you wanted.

1. Create a file called `index.html`.
2. Type a basic page with a heading, a paragraph, and a list.
3. Open the file in your browser (double-click it) to see the result.
4. Add a little CSS to change a color or font, and refresh.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My First Page</title>
    <style>
      body { font-family: sans-serif; }
      h1 { color: teal; }
    </style>
  </head>
  <body>
    <h1>Hello, world!</h1>
    <p>This is my very first web page, written by hand.</p>
    <ul>
      <li>I like football</li>
      <li>I like coding</li>
      <li>I like tea</li>
    </ul>
  </body>
</html>
```

Notice: you just wrote **structure** (the HTML tags) and **style** (the CSS in `<style>`) with your own hands — no AI involved.

**Svenska**
Innan vi tar in AI:n, låt oss skriva en liten sida **själva**. På så sätt känner du igen delarna när AI:n skriver HTML åt dig senare, och kan bedöma om den gjorde det du ville.

1. Skapa en fil som heter `index.html`.
2. Skriv en enkel sida med en rubrik, ett stycke och en lista.
3. Öppna filen i din webbläsare (dubbelklicka) för att se resultatet.
4. Lägg till lite CSS för att ändra en färg eller ett typsnitt, och ladda om.

(Samma kodexempel gäller.) Lägg märke till: du skrev just **struktur** (HTML-taggarna) och **stil** (CSS:en i `<style>`) med dina egna händer — utan någon AI.

> **Key idea / Nyckelidé:** You now know what HTML and CSS look like *by hand* — so you can recognize (and check) what the AI writes next. / Du vet nu hur HTML och CSS ser ut *för hand* — så du kan känna igen (och kontrollera) det AI:n skriver härnäst.

---

## 5. What AI actually is / Vad AI egentligen är

**English**
AI (Artificial Intelligence) is software that **learns patterns from lots of examples**, instead of following step-by-step rules a human wrote by hand. Show it thousands of examples and it learns to guess good answers for new, unseen cases.

- A **Large Language Model (LLM)** is an AI trained on a huge amount of text. Its core trick is simple: **predict the next word** over and over. That single ability is what powers chat assistants (ChatGPT, Claude) and AI coding tools (like Cursor).
- **Great at:** drafting text and code, explaining things, boilerplate (repetitive setup code), and giving you a fast starting point.
- **Bad at / watch out for:** it can be **confidently wrong**. This is called a **hallucination** — it makes something up that *sounds* right but isn't. So you must always **check its output**.
- **Why this matters for the course:** the AI is your **coding partner**, but *you* stay in charge. You review its work and you own the result.

**Svenska**
AI (artificiell intelligens) är programvara som **lär sig mönster från många exempel**, i stället för att följa steg-för-steg-regler som en människa skrivit för hand. Visa den tusentals exempel så lär den sig att gissa bra svar för nya fall den aldrig sett.

- En **stor språkmodell (LLM)** är en AI tränad på enorma mängder text. Grundtricket är enkelt: **förutsäga nästa ord** om och om igen. Just den förmågan är det som driver chattassistenter (ChatGPT, Claude) och AI-kodverktyg (som Cursor).
- **Bra på:** att skriva utkast av text och kod, förklara saker, "boilerplate" (upprepad grundkod) och ge dig en snabb start.
- **Dålig på / se upp för:** den kan ha **fel med stort självförtroende**. Det kallas en **hallucination** — den hittar på något som *låter* rätt men inte är det. Därför måste du alltid **kontrollera det den skriver**.
- **Varför detta är viktigt i kursen:** AI:n är din **kodpartner**, men *du* bestämmer. Du granskar arbetet och du äger resultatet.

> **Key idea / Nyckelidé:** An LLM predicts the next word. It doesn't "know" facts the way a database does — it guesses what's likely. / En LLM förutsäger nästa ord. Den "vet" inte fakta som en databas — den gissar vad som är troligt.

---

## 6. What "vibe coding" is (and isn't) / Vad "vibe coding" är (och inte är)

**English**
"Vibe coding" means you **describe what you want in plain language** and let the AI write much of the code, while you guide, review, and refine.

- **It IS:** directing the AI with clear intent, reading what it produced, testing it, and fixing or improving it.
- **It is NOT:** blindly copy-pasting code you don't understand. **You still own the code.**
- **The golden rule of this course:** *You must be able to explain what your code does.* If you can't, ask the AI to explain it until you can.

Remember the page you wrote by hand in section 4? Vibe coding just lets the AI type that kind of thing faster — but you still need to recognize and understand it.

**Svenska**
"Vibe coding" betyder att du **beskriver vad du vill ha på vanligt språk** och låter AI:n skriva mycket av koden, medan du styr, granskar och förbättrar.

- **Det ÄR:** att styra AI:n med tydlig avsikt, läsa det den skapat, testa det och fixa eller förbättra det.
- **Det är INTE:** att blint kopiera kod du inte förstår. **Du äger fortfarande koden.**
- **Kursens gyllene regel:** *Du måste kunna förklara vad din kod gör.* Om du inte kan det, be AI:n förklara tills du kan.

Kommer du ihåg sidan du skrev för hand i avsnitt 4? Vibe coding låter bara AI:n skriva den typen av saker snabbare — men du behöver fortfarande känna igen och förstå det.

---

## 7. Your AI coding tool (e.g. Cursor) / Ditt AI-kodverktyg (t.ex. Cursor)

**English**
The basic loop you'll use all week:

1. **Prompt** — tell the AI what you want in a chat message.
2. **Review** — read the change it suggests before accepting.
3. **Accept or reject** — keep good changes, discard bad ones.
4. **Undo** — if something breaks, undo and try a clearer prompt.

Don't be afraid to break things — undo exists for exactly this reason.

**Svenska**
Grundloopen du använder hela veckan:

1. **Prompt (fråga)** — berätta för AI:n vad du vill ha i ett chattmeddelande.
2. **Granska** — läs ändringen den föreslår innan du accepterar.
3. **Acceptera eller avvisa** — behåll bra ändringar, släng dåliga.
4. **Ångra (undo)** — om något går sönder, ångra och försök med en tydligare prompt.

Var inte rädd för att ha sönder saker — ångra-funktionen finns just därför.

---

## 8. Now build it with AI: an "About Me" page / Nu bygger vi med AI: en "Om mig"-sida

**English**
You already built a page by hand — now let's build a nicer personal page **with the AI** and feel the difference in speed, while you still recognize every part.

- Describe the page to the AI in plain language (your name, an intro, your interests).
- Ask it to **change colors**, then **add a section** — and each time, **read what changed**.
- Compare it to your hand-written page: can you spot the HTML (content), the CSS (looks), and any JS (interaction)?

Example first prompt you could use:

```text
Create a simple one-page "About Me" website with my name as a big heading,
a short intro paragraph, and a list of three hobbies. Use a clean, colorful style.
```

**Svenska**
Du har redan byggt en sida för hand — nu bygger vi en snyggare personlig sida **med AI:n** och känner skillnaden i hastighet, medan du fortfarande känner igen varje del.

- Beskriv sidan för AI:n på vanligt språk (ditt namn, en intro, dina intressen).
- Be den **ändra färger**, sedan **lägga till ett avsnitt** — och läs varje gång **vad som ändrades**.
- Jämför med din handskrivna sida: kan du hitta HTML (innehåll), CSS (utseende), och eventuell JS (interaktion)?

Exempel på en första prompt du kan använda:

```text
Skapa en enkel enkelsides-webbplats "Om mig" med mitt namn som en stor rubrik,
ett kort introstycke, och en lista med tre hobbies. Använd en ren, färgglad stil.
```

---

## 9. Independent challenge / Egen utmaning

**English**
Add a **new section the AI did not suggest** (for example: a favorite quote, a small photo gallery, or a "contact me" line). Then explain **each part of the generated HTML** to a partner.

**Svenska**
Lägg till ett **nytt avsnitt som AI:n inte föreslog** (till exempel: ett favoritcitat, ett litet bildgalleri, eller en "kontakta mig"-rad). Förklara sedan **varje del av den genererade HTML-koden** för en kompis.

---

## 10. Concept check — can you answer these? / Konceptkoll — kan du svara på dessa?

**English**
1. What is the difference between a client and a server?
2. Point to the HTML, the CSS, and the JS in a page — what does each one do?
3. In one sentence, what is an LLM's core trick?
4. What does "vibe coding" mean, and what's the golden rule of this course?

**Svenska**
1. Vad är skillnaden mellan en klient och en server?
2. Peka på HTML, CSS och JS i en sida — vad gör var och en?
3. Med en mening, vad är en LLM:s grundtrick?
4. Vad betyder "vibe coding", och vad är kursens gyllene regel?

---

## 11. Key vocabulary / Nyckelord

| English | Svenska | Meaning / Betydelse |
|---------|---------|----------------------|
| Client | Klient | The device that asks (browser) / Enheten som frågar (webbläsaren) |
| Server | Server | The computer that stores & answers / Datorn som lagrar & svarar |
| Request | Förfrågan / request | The message asking for something / Meddelandet som ber om något |
| Response | Svar / response | What the server sends back / Det servern skickar tillbaka |
| Frontend | Frontend | The part you see in the browser / Delen du ser i webbläsaren |
| Backend | Backend | The hidden server-side part / Den dolda server-delen |
| HTML | HTML | Structure of a page / Sidans struktur |
| CSS | CSS | Style of a page / Sidans stil |
| JavaScript (JS) | JavaScript (JS) | Behavior / interaction / Beteende / interaktion |
| AI (Artificial Intelligence) | AI (artificiell intelligens) | Software that learns patterns from examples / Programvara som lär sig mönster från exempel |
| LLM (Large Language Model) | Stor språkmodell | AI that predicts the next word / AI som förutsäger nästa ord |
| Hallucination | Hallucination | When AI confidently makes something up / När AI hittar på något med självförtroende |
| Vibe coding | Vibe coding | Describing intent, AI writes code, you own it / Du beskriver, AI skriver, du äger det |

---

*Next up: Day 2 — Prompting an AI Well & Reading Its Code.*
*Nästa: Dag 2 — Att prompta en AI bra & läsa dess kod.*

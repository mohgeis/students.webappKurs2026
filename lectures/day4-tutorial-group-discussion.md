# Tutorial — Group Discussion: What We've Learned (Days 1–3)

# Handledning — Gruppdiskussion: Vad vi har lärt oss (Dag 1–3)

> **Day 4 breakout activity (~ 30 minutes) / Dag 4 grupparbete (~ 30 minuter)**  
> No coding this time! In your breakout room, talk through these questions and mini-quizzes **together**. The goal is to explain ideas **in your own words** — if your group can explain it out loud, you truly understand it.
>
> Ingen kodning den här gången! I ert grupprum, gå igenom dessa frågor och mini-quiz **tillsammans**. Målet är att förklara idéer **med egna ord** — om er grupp kan förklara det högt, då förstår ni det på riktigt.

---

## How this works / Så här fungerar det

**English**

- You'll be split into small groups in **breakout rooms**.
- Work through the **rounds** below in order. Each round has a suggested time.
- You don't have to answer *every* question — pick the ones that spark discussion.
- Keep short notes: you'll **share one highlight** with everyone at the end.

**Svenska**

- Ni delas in i små grupper i **grupprum (breakout rooms)**.
- Gå igenom **rundorna** nedan i ordning. Varje runda har en föreslagen tid.
- Ni behöver inte svara på *varje* fråga — välj de som skapar diskussion.
- Anteckna kort: ni ska **dela en höjdpunkt** med alla i slutet.

---

## Round 1 — How the web works (Day 1) /

Runda 1 — Hur webben fungerar (~6 min)

**English** — Discuss together:

1. Explain **client** and **server** in your own words. Come up with a **new analogy** (not the restaurant one!).
2. What's the difference between **frontend** and **backend**? Which one did we build this week?
3. **Web page vs. web app** — give one real example of each that you use on your phone.

**Quick quiz / Snabbquiz:** When you **search for a video on YouTube**:

- Who is the **client**? Who is the **server**?
- What is the **request**? What is the **response**?

**Svenska** — Diskutera tillsammans:

1. Förklara **klient** och **server** med egna ord. Hitta på en **ny liknelse** (inte restaurangen!).
2. Vad är skillnaden mellan **frontend** och **backend**? Vilken byggde vi den här veckan?
3. **Webbsida vs. webbapp** — ge ett verkligt exempel på varje som du använder i telefonen.

---

## Round 2 — HTML, CSS & JS (Day 1 + "About Me") /

Runda 2 — HTML, CSS & JS (~6 min)

**English** — Discuss together:

1. In one sentence each: what job does **HTML** do? **CSS**? **JS**? (Try the house analogy.)
2. Think back to the **"About Me" page**: which parts were HTML, which were CSS, and what did the one bit of JavaScript do?
3. Why did we build the page **by hand** *before* using AI?

**Quick quiz — which language?** Say **HTML**, **CSS**, or **JS** for each:

```text
a)  <h1>Hello!</h1>
b)  color: hotpink;
c)  onclick="showFunFact()"
d)  <ul> ... </ul>
e)  background-color: #f5f7fb;
```

**Bonus:** Which HTML tag makes… (an **image**? a **list**? a **link**? a **table**?)

**Svenska** — Diskutera tillsammans:

1. En mening var: vilket jobb gör **HTML**? **CSS**? **JS**? (Prova hus-liknelsen.)
2. Tänk tillbaka på **"Om mig"-sidan**: vilka delar var HTML, vilka var CSS, och vad gjorde den lilla biten JavaScript?
3. Varför byggde vi sidan **för hand** *innan* vi använde AI?

---

## Round 3 — AI & "vibe coding" (Days 1–2) / Runda 3 — AI & "vibe coding" (~8 min)

**English** — Discuss together:

1. An **LLM**'s core trick is to **predict the next word**. So how can it write working code?
2. What is a **hallucination**? Share an example of when AI was **confidently wrong** for you.
3. The **golden rule** of this course is: *you must be able to explain your code.* Why does that matter?

**Quick quiz — better prompts?** Pick **2–3** of these (or do all five if you have time). For each bad prompt, your group writes a **better version** together. What makes it better? *(Be specific: what to build, which tech, what it should look like, and ask for short comments.)*

**Snabbquiz — bättre prompts?** Välj **2–3** av dessa (eller gör alla fem om ni har tid). För varje dålig prompt skriver gruppen en **bättre version** tillsammans. Vad gör den bättre? *(Var specifik: vad som ska byggas, vilken teknik, hur det ska se ut, och be om korta kommentarer.)*

**1) Which is better, and why? / Vilket är bättre, och varför?**

```text
A)  "make a website about me"
B)  "Create a one-page 'About Me' site with my name as a big heading, a short intro, and a list of 3 hobbies. Clean, colorful style."
```

**2) Bad prompt / Dålig prompt:**

```text
"fix my button"
```

→ Your group writes a better prompt: *Er grupp skriver en bättre prompt:*

**3) Bad prompt / Dålig prompt:**

```text
"use an api"
```

→ Your group writes a better prompt: *Er grupp skriver en bättre prompt:*

**4) Bad prompt / Dålig prompt:**

```text
"make it look nicer"
```

→ Your group writes a better prompt: *Er grupp skriver en bättre prompt:*

**5) Bad prompt / Dålig prompt:**

```text
"add search"
```

→ Your group writes a better prompt: *Er grupp skriver en bättre prompt:*

**Svenska** — Diskutera tillsammans:

1. En **LLM**:s grundtrick är att **förutsäga nästa ord**. Hur kan den då skriva fungerande kod?
2. Vad är en **hallucination**? Dela ett exempel på när AI hade **fel med självförtroende** för dig.
3. Kursens **gyllene regel** är: *du måste kunna förklara din kod.* Varför är det viktigt?

> 🗨️ Mini-debate / Mini-debatt (2 min): *"AI will soon replace programmers."* Agree or disagree? Give one reason each.
> *"AI kommer snart att ersätta programmerare." Håller ni med eller inte? Ge ett skäl var.*

---

## Round 4 — APIs, JSON & fetch (Day 3 + API tutorials) / Runda 4 — API:er, JSON & fetch (~8 min)

**English** — Discuss together:

1. Explain what an **API** is with a **new analogy** of your own.
2. In JSON, what's the difference between `{ }` and `[ ]`?
3. **Trace the journey** of data from an API all the way to the screen. Name every step.
4. Why do we **look at the API response data in the browser** *before* writing code?

**Quick quiz — read the JSON.** Look at this response:

```json
{
  "results": [
    {
      "id": 1,
      "name": "Rick Sanchez",
      "status": "Alive",
      "image": "https://.../1.jpeg"
    }
  ]
}
```

- Is `results` an **object** or an **array**?
- How would you get the character's **name** in code? *(hint: starts with* `data.`*)*
- How would you get the **image** of the **first** result?

**Svenska** — Diskutera tillsammans:

1. Förklara vad ett **API** är med en **egen ny liknelse**.
2. I JSON, vad är skillnaden mellan `{ }` och `[ ]`?
3. **Spåra resan** för data från ett API hela vägen till skärmen. Namnge varje steg.
4. Varför **tittar vi på API datan i webbläsaren** *innan* vi skriver kod?

**Facit-tips / Answer hint:** `results` = array · name = `data.results[0].name` · image = `data.results[0].image`

---

## Wrap-up: prepare to share (2 min) / Avslutning: förbered att dela (2 min)

**English** — As a group, agree on:

1. ✅ **One thing** everyone now feels confident explaining.
2. ❓ **One question** you're still unsure about (we'll answer these together).
3. 💡 **One favorite** analogy or "aha!" moment from your discussion.

Your **Reporter** will share these when we're back in the main room.

**Svenska** — Kom överens som grupp om:

1. ✅ **En sak** som alla nu känner sig trygga med att förklara.
2. ❓ **En fråga** ni fortfarande är osäkra på (vi svarar på dem tillsammans).
3. 💡 **En favorit**-liknelse eller ett "aha!"-ögonblick från er diskussion.

Er **Rapportör** delar dessa när vi är tillbaka i huvudrummet.

---

## Facilitator answer key (for reference) /   
Facit för ledaren (referens)

> Use only if your group gets stuck — try to reason it out first!
> *Använd bara om gruppen fastnar — försök resonera först!*

- **Client/Server:** client = your device that **asks**; server = the computer elsewhere that **stores & answers**.
- **Frontend/Backend:** frontend = what you see/click (HTML/CSS/JS); backend = hidden logic/data on the server. This week = **frontend**.
- **HTML/CSS/JS:** structure / style / behavior.
- **LLM:** predicts the next word from patterns; it **guesses what's likely**, so it can be **confidently wrong** (a hallucination).
- `{ }` vs `[ ]`: object (one thing with labeled parts) vs array (an ordered list).
- **Data journey:** input → build URL → `fetch` request → server → JSON response → `.json()` → read field(s) → show on page.

**Round 3 — example better prompts / exempel på bättre prompts:**

- **"fix my button"** → *"On my About Me page, the 'Show a fun fact' button does nothing when clicked. Using plain HTML/CSS/JS, fix the onclick handler so it shows a fun fact in `<p id='fact'>`. Explain each change with a short comment."*
- **"use an api"** → *"Using plain HTML/CSS/JS, fetch a character from `https://rickandmortyapi.com/api/character/1`. Log the full JSON to the console, then show the character's name, id, and image on the page. Add a short comment on each line."*
- **"make it look nicer"** → *"Style my character page: put the name, image, and number inside a centered white card with rounded corners, padding, and a soft shadow. Use a light page background and a blue heading. Keep plain HTML/CSS/JS."*
- **"add search"** → *"Using plain HTML/CSS/JS, add a search box and button. When the user searches, fetch from `https://rickandmortyapi.com/api/character/?name=` plus their search term. Show 'Searching…' while loading, 'No character found' if nothing matches, and display matching characters in cards with name and image."*


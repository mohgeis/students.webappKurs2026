# Day 2 — Prompting an AI Well & Reading Its Code
# Dag 2 — Att prompta en AI bra & läsa dess kod

> **How to use these notes / Så använder du dessa anteckningar**
> Read these after the lecture to recap. Each section is written in **English first**, then **Swedish (Svenska)**. Try to explain each idea out loud in your own words — if you can't, that's the part to re-read.
>
> Läs detta efter föreläsningen för att repetera. Varje avsnitt är skrivet **på engelska först**, sedan **på svenska**. Försök förklara varje idé högt med egna ord — om du inte kan, är det den delen du ska läsa om.

---

## Today's lesson plan / Dagens upplägg

**Total: 2 hours / 2 timmar**

| Block / Moment | Time / Tid | What happens / Vad vi gör |
|----------------|-----------|----------------------------|
| **Warm-up & recap**<br>*Uppvärmning & repetition* | 10 min | Recap HTML/CSS/JS from Day 1, and today's goal in one sentence.<br>*Repetera HTML/CSS/JS från Dag 1, och dagens mål i en mening.* |
| **Concept mini-lesson**<br>*Konceptgenomgång* | 25 min | Anatomy of a good prompt, iterating in small steps, and reading code you didn't write.<br>*En bra prompts anatomi, att iterera i små steg, och att läsa kod du inte skrivit.* |
| **Guided build**<br>*Guidat bygge* | 45 min | Build the "Quote / Joke of the day" page with a button and functions.<br>*Bygg sidan "Dagens citat / skämt" med en knapp och funktioner.* |
| **Independent challenge**<br>*Egen utmaning* | 30 min | Make the button pick randomly and disable for 2 seconds; then explain the logic.<br>*Låt knappen välja slumpmässigt och inaktiveras i 2 sekunder; förklara sedan logiken.* |
| **Wrap-up & share**<br>*Avslutning & dela* | 10 min | Share results, name one thing you learned, and preview tomorrow.<br>*Dela resultat, nämn en sak du lärt dig, och en förhandstitt på imorgon.* |

---

## 1. What you'll be able to do after today / Vad du kan efter idag

**English**
- Treat the AI like a junior teammate you must direct and review.
- Write a good prompt using the pattern: **context + goal + constraints + examples**.
- Improve results by **iterating in small steps** instead of one giant request.
- Skim and read code you didn't write, and ask the AI to **explain** a section.
- Get into the habit of **saving snapshots** of your work as you go.
- Build an interactive "Quote / Joke of the day" page (still local, no API yet).

**Svenska**
- Behandla AI:n som en junior lagkamrat du måste styra och granska.
- Skriva en bra prompt med mönstret: **kontext + mål + begränsningar + exempel**.
- Förbättra resultat genom att **iterera i små steg** i stället för en enda jättefråga.
- Skumma och läsa kod du inte själv skrivit, och be AI:n **förklara** en del.
- Vänja dig vid att **spara ögonblicksbilder** av ditt arbete allt eftersom.
- Bygga en interaktiv "Dagens citat / skämt"-sida (fortfarande lokalt, inget API än).

---

## 2. The mindset: AI is a junior teammate / Tänket: AI är en junior lagkamrat

**English**
Think of the AI as a fast, eager, but **inexperienced teammate**. It can produce a lot quickly, but it needs **clear directions** and its work needs **reviewing**.

- **You are the lead.** You decide what to build and whether the result is good.
- **It follows instructions literally.** Vague input → vague or wrong output.
- **It won't push back much.** If you ask for something odd, it may just do it. That's why *you* must judge the result.

**Svenska**
Se AI:n som en snabb, ivrig men **oerfaren lagkamrat**. Den kan producera mycket snabbt, men den behöver **tydliga instruktioner** och dess arbete behöver **granskas**.

- **Du är ledaren.** Du bestämmer vad som ska byggas och om resultatet är bra.
- **Den följer instruktioner bokstavligt.** Vag input → vagt eller felaktigt resultat.
- **Den säger sällan emot.** Ber du om något konstigt kan den bara göra det. Därför måste *du* bedöma resultatet.

---

## 3. Anatomy of a good prompt / En bra prompts anatomi

**English**
A strong prompt usually has four parts:

1. **Context** — the situation and what already exists. *"I have a one-page site with a heading and a button."*
2. **Goal** — what you want to happen. *"I want the button to show a random quote."*
3. **Constraints** — rules and limits. *"Keep it plain JavaScript, no libraries. Keep my current colors."*
4. **Examples** — show what you mean when possible. *"For example, quotes like 'Stay curious.'"*

Compare:

```text
Bad:  "make a quote thing"

Good: "I have a one-page site with a heading and a button (plain HTML/CSS/JS).
       When I click the button, show a random quote from a list of 5 quotes I provide.
       Keep the existing style. Example quotes: 'Stay curious.', 'Keep building.'"
```

**Svenska**
En stark prompt har oftast fyra delar:

1. **Kontext** — situationen och vad som redan finns. *"Jag har en enkelsida med en rubrik och en knapp."*
2. **Mål** — vad du vill ska hända. *"Jag vill att knappen visar ett slumpmässigt citat."*
3. **Begränsningar** — regler och gränser. *"Håll det i ren JavaScript, inga bibliotek. Behåll mina nuvarande färger."*
4. **Exempel** — visa vad du menar när det går. *"Till exempel citat som 'Var nyfiken.'"*

Jämför:

```text
Dåligt:  "gör en citat-grej"

Bra:     "Jag har en enkelsida med en rubrik och en knapp (ren HTML/CSS/JS).
          När jag klickar på knappen, visa ett slumpmässigt citat från en lista med 5 citat jag ger.
          Behåll den nuvarande stilen. Exempelcitat: 'Var nyfiken.', 'Fortsätt bygga.'"
```

> **Key idea / Nyckelidé:** The more precise your prompt, the less guessing the AI does. / Ju mer precis din prompt är, desto mindre gissar AI:n.

---

## 4. Iterating: small steps beat one giant request / Iterering: små steg slår en jättefråga

**English**
Don't try to describe the whole app in one message. Build it up in small, checkable steps.

- Ask for **one change at a time**, then look at the result.
- If it's wrong, **correct just that** ("almost — make the button pick randomly, not always the first quote").
- Small steps make it easy to see **what changed** and to undo a single step if needed.

Why it works: each small step is easy to review, easy to fix, and easy to explain later.

**Svenska**
Försök inte beskriva hela appen i ett enda meddelande. Bygg upp den i små, kontrollerbara steg.

- Be om **en ändring i taget**, titta sedan på resultatet.
- Om det blev fel, **rätta bara det** ("nästan — låt knappen välja slumpmässigt, inte alltid första citatet").
- Små steg gör det lätt att se **vad som ändrades** och att ångra ett enda steg vid behov.

Varför det funkar: varje litet steg är lätt att granska, lätt att fixa, och lätt att förklara senare.

---

## 5. Reading code you didn't write / Att läsa kod du inte skrivit

**English**
You don't need to understand every character. You need to find the relevant part and understand *that*.

- **Skim first:** look at names (functions, variables) and comments to get the shape.
- **Find the relevant part:** which lines handle the thing you care about (e.g. the click)?
- **Ask the AI to explain:** paste a section and ask *"explain what this does, line by line, simply."*
- **Test your understanding:** predict what a line does, then change it and see if you were right.

Useful questions to ask the AI:
- "What does this function do, in one sentence?"
- "What would happen if I removed this line?"
- "Is there a simpler way to write this?"

**Svenska**
Du behöver inte förstå varje tecken. Du behöver hitta den relevanta delen och förstå *den*.

- **Skumma först:** titta på namn (funktioner, variabler) och kommentarer för att få formen.
- **Hitta den relevanta delen:** vilka rader hanterar det du bryr dig om (t.ex. klicket)?
- **Be AI:n förklara:** klistra in en del och be *"förklara vad detta gör, rad för rad, enkelt."*
- **Testa din förståelse:** gissa vad en rad gör, ändra den sedan och se om du hade rätt.

Bra frågor att ställa till AI:n:
- "Vad gör den här funktionen, med en mening?"
- "Vad skulle hända om jag tog bort den här raden?"
- "Finns det ett enklare sätt att skriva detta?"

---

## 6. New building blocks: functions and events / Nya byggstenar: funktioner och händelser

**English**
Today's page introduces three JavaScript ideas:

- **Function:** a named block of code that does a job when you "call" it. Like a recipe you can reuse.
- **Event:** something that happens in the page, like a **click**. You can *listen* for it and react.
- **Updating the page:** JavaScript can change what's on screen (e.g. swap the text inside a heading).

```html
<h1 id="quote">Click the button for a quote</h1>
<button onclick="showQuote()">New quote</button>

<script>
  const quotes = ["Stay curious.", "Keep building.", "Ask better questions."];

  // function = reusable block of code
  function showQuote() {
    const random = quotes[Math.floor(Math.random() * quotes.length)];
    document.getElementById("quote").textContent = random; // update the page
  }
</script>
```

**Svenska**
Dagens sida introducerar tre JavaScript-idéer:

- **Funktion:** ett namngivet kodblock som gör ett jobb när du "anropar" det. Som ett recept du kan återanvända.
- **Händelse (event):** något som händer på sidan, som ett **klick**. Du kan *lyssna* efter det och reagera.
- **Uppdatera sidan:** JavaScript kan ändra vad som visas på skärmen (t.ex. byta texten i en rubrik).

(Samma kodexempel gäller: `quotes` är listan, `showQuote()` är funktionen, `onclick` är händelsen som lyssnar efter klicket, och raden med `textContent` uppdaterar sidan.)

> **Remember / Kom ihåg:** A function *does* something when called; an event is *when* it runs (like a click). / En funktion *gör* något när den anropas; en händelse är *när* den körs (som ett klick).

---

## 7. Saving your work (snapshots) / Spara ditt arbete (ögonblicksbilder)

**English**
Get into the habit of keeping **snapshots** of your work as you go — a saved copy of a version that works. If a later change breaks things, you can go back.

- For now, this can be as simple as saving/duplicating your working file before a big change.
- The full professional workflow (Git & GitHub) comes on **Day 5** — today is just the habit.

**Svenska**
Vänj dig vid att behålla **ögonblicksbilder** av ditt arbete allt eftersom — en sparad kopia av en version som fungerar. Om en senare ändring har sönder något kan du gå tillbaka.

- Just nu kan det vara så enkelt som att spara/duplicera din fungerande fil före en stor ändring.
- Hela det professionella arbetsflödet (Git & GitHub) kommer på **Dag 5** — idag handlar det bara om vanan.

---

## 8. Today's build: "Quote / Joke of the day" / Dagens bygge: "Dagens citat / skämt"

**English**
Build an interactive page with a button that swaps text from a small built-in list (no API yet).

- Start simple: a button that shows the *first* quote.
- Then iterate: make it show a **random** quote each click.
- Practice reading each line the AI writes and explaining it.

Example prompts (iterating step by step):

```text
1) "Add a button under my heading. When clicked, it shows the first item from a
    list of 5 quotes I define in JavaScript. Plain HTML/CSS/JS."

2) "Now make it pick a random quote each time instead of always the first."
```

**Svenska**
Bygg en interaktiv sida med en knapp som byter text från en liten inbyggd lista (inget API än).

- Börja enkelt: en knapp som visar *första* citatet.
- Iterera sedan: låt den visa ett **slumpmässigt** citat vid varje klick.
- Öva på att läsa varje rad AI:n skriver och förklara den.

Exempel-prompts (iterering steg för steg):

```text
1) "Lägg till en knapp under min rubrik. Vid klick visar den första objektet från en
    lista med 5 citat som jag definierar i JavaScript. Ren HTML/CSS/JS."

2) "Låt den nu välja ett slumpmässigt citat varje gång i stället för alltid det första."
```

---

## 9. Independent challenge / Egen utmaning

**English**
Using the AI, make the button:
1. pick a **random** item, and
2. become **disabled for 2 seconds** after a click (so it can't be spammed).

Then explain the logic in your own words: *how* does it pick randomly, and *how* does it re-enable after 2 seconds?

**Svenska**
Med hjälp av AI:n, få knappen att:
1. välja ett **slumpmässigt** objekt, och
2. bli **inaktiverad i 2 sekunder** efter ett klick (så den inte kan spammas).

Förklara sedan logiken med egna ord: *hur* väljer den slumpmässigt, och *hur* aktiveras den igen efter 2 sekunder?

---

## 10. Concept check — can you answer these? / Konceptkoll — kan du svara på dessa?

**English**
1. Name the four parts of a good prompt.
2. Why are small iterative steps better than one huge request?
3. When reading unfamiliar code, what's a good first move?
4. In your page, what is the function, and what is the event that triggers it?

**Group exercise:** Take this vague prompt — *"make a joke button"* — and rewrite it into a clear one using context + goal + constraints + examples.

**Svenska**
1. Namnge de fyra delarna i en bra prompt.
2. Varför är små iterativa steg bättre än en enda enorm fråga?
3. När du läser okänd kod, vad är ett bra första steg?
4. I din sida, vad är funktionen, och vad är händelsen som utlöser den?

**Gruppövning:** Ta denna vaga prompt — *"gör en skämtknapp"* — och skriv om den till en tydlig med kontext + mål + begränsningar + exempel.

---

## 11. Key vocabulary / Nyckelord

| English | Svenska | Meaning / Betydelse |
|---------|---------|----------------------|
| Prompt | Prompt | The instruction you give the AI / Instruktionen du ger AI:n |
| Context | Kontext | Background info the AI needs / Bakgrundsinfo AI:n behöver |
| Constraint | Begränsning | A rule/limit for the answer / En regel/gräns för svaret |
| Iterate | Iterera | Improve in small repeated steps / Förbättra i små upprepade steg |
| Function | Funktion | Reusable named block of code / Återanvändbart namngivet kodblock |
| Event | Händelse (event) | Something that happens, e.g. a click / Något som händer, t.ex. ett klick |
| Click handler | Klickhanterare | Code that runs on a click / Kod som körs vid ett klick |
| Random | Slumpmässig | Chosen by chance / Vald av slumpen |
| Snapshot | Ögonblicksbild | A saved copy of a working version / En sparad kopia av en fungerande version |
| Disabled | Inaktiverad | Temporarily not clickable / Tillfälligt inte klickbar |

---

*Previously: Day 1 — Intro to AI, How the Web Works & Your First Vibe-Coded Page.*
*Next up: Day 3 — What an API Is & Your First Real Data.*
*Tidigare: Dag 1 — Intro till AI, hur webben fungerar & din första vibe-kodade sida.*
*Nästa: Dag 3 — Vad ett API är & din första riktiga data.*

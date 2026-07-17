# Day 6 — Project Day: Design & Build Your Own App
# Dag 6 — Projektdag: designa & bygg din egen app

> **How to use these notes / Så använder du dessa anteckningar**
> Read these after the lecture to recap. Each section is written in **English first**, then **Swedish (Svenska)**. Try to explain each idea out loud in your own words — if you can't, that's the part to re-read.
>
> Läs detta efter föreläsningen för att repetera. Varje avsnitt är skrivet **på engelska först**, sedan **på svenska**. Försök förklara varje idé högt med egna ord — om du inte kan, är det den delen du ska läsa om.

---

## Today's lesson plan / Dagens upplägg

**Total: 2 hours / 2 timmar** (mostly your own build time / mestadels egen byggtid)

| Block / Moment | Time / Tid | What happens / Vad vi gör |
|----------------|-----------|----------------------------|
| **Warm-up & recap**<br>*Uppvärmning & repetition* | 10 min | How project day works; today's goal: your own app.<br>*Hur projektdagen fungerar; dagens mål: din egen app.* |
| **Concept mini-lesson**<br>*Konceptgenomgång* | 20 min | Scoping small, planning before prompting, and choosing an API.<br>*Att avgränsa smått, planera innan du promptar, och välja ett API.* |
| **Plan & choose your API**<br>*Planera & välj ditt API* | 15 min | Sketch your plan, pick a public API, and confirm it works in the browser.<br>*Skissa din plan, välj ett publikt API, och bekräfta att det fungerar i webbläsaren.* |
| **Build your prototype**<br>*Bygg din prototyp* | 60 min | Build your app's core feature iteratively with the AI, committing as you go.<br>*Bygg appens kärnfunktion iterativt med AI:n, och commita allt eftersom.* |
| **Wrap-up & share**<br>*Avslutning & dela* | 15 min | State your app's one-sentence purpose and which API powers it.<br>*Beskriv din apps syfte i en mening och vilket API som driver den.* |

---

## 1. What you'll be able to do after today / Vad du kan efter idag

**English**
- Go from an **idea** to a **plan** to a **working prototype** on your own.
- **Scope** an idea so it's small enough to finish (1–2 core features).
- Sketch a plan before prompting: what data, which API, what screens.
- Work **iteratively** with the AI on a multi-part project.
- Finish the day with a working prototype that uses at least one API.

**Svenska**
- Gå från en **idé** till en **plan** till en **fungerande prototyp** på egen hand.
- **Avgränsa (scope)** en idé så den är liten nog att bli klar (1–2 kärnfunktioner).
- Skissa en plan innan du promptar: vilken data, vilket API, vilka skärmar.
- Jobba **iterativt** med AI:n på ett projekt med flera delar.
- Avsluta dagen med en fungerande prototyp som använder minst ett API.

---

## 2. Scoping: pick a small enough idea / Avgränsning: välj en tillräckligt liten idé

**English**
The most common mistake on project day is picking something **too big**. A great small project beats an unfinished big one.

- Aim for **1–2 core features**, not ten.
- Describe your app in **one sentence**. If you can't, it's probably too big.
- You can always add more *after* the core works ("nice-to-haves" go on a later list).

Example: *"An app where I type a country and see its flag, capital, and population."* — one input, one API, one card. Perfect scope.

**Svenska**
Det vanligaste misstaget på projektdagen är att välja något **för stort**. Ett bra litet projekt slår ett oavslutat stort.

- Sikta på **1–2 kärnfunktioner**, inte tio.
- Beskriv din app i **en mening**. Kan du inte det är den förmodligen för stor.
- Du kan alltid lägga till mer *efter* att kärnan fungerar ("trevligt-att-ha" hamnar på en senare lista).

Exempel: *"En app där jag skriver ett land och ser dess flagga, huvudstad och befolkning."* — en inmatning, ett API, ett kort. Perfekt avgränsning.

> **Key idea / Nyckelidé:** A finished small app beats an unfinished big one. Scope down. / En klar liten app slår en oavslutad stor. Avgränsa neråt.

---

## 3. Plan before you prompt / Planera innan du promptar

**English**
Spend a few minutes sketching before you ask the AI for anything. Answer these:

- **What data** does my app show? (the core content)
- **Which API** provides that data? (check it works — open its URL in the browser)
- **What screens / parts** does the page have? (input, button, results card, message area)
- **What's the user flow?** (what does the user do first, next, last)

A rough sketch on paper of the screen is enough. This plan becomes your prompting checklist.

**Svenska**
Lägg några minuter på att skissa innan du ber AI:n om något. Svara på detta:

- **Vilken data** visar min app? (kärninnehållet)
- **Vilket API** ger den datan? (kolla att det fungerar — öppna dess URL i webbläsaren)
- **Vilka skärmar / delar** har sidan? (inmatning, knapp, resultatkort, meddelandeyta)
- **Vad är användarflödet?** (vad gör användaren först, sedan, sist)

En grov skiss på papper av skärmen räcker. Den här planen blir din prompt-checklista.

---

## 4. Choosing an API / Att välja ett API

**English**
Browse these directories to find a free API that fits your idea:

- [public-apis (GitHub list)](https://github.com/public-apis/public-apis)
- [Free Public APIs](https://www.freepublicapis.com/)

When picking, check:
- Is it **free** and does it need a **key**? (no-key is easiest today)
- Does it return **JSON** you can understand?
- Open a sample URL in the browser — **does it actually work right now?**

**Svenska**
Bläddra i dessa kataloger för att hitta ett gratis API som passar din idé:

- [public-apis (GitHub-lista)](https://github.com/public-apis/public-apis)
- [Free Public APIs](https://www.freepublicapis.com/)

När du väljer, kolla:
- Är det **gratis** och behövs en **nyckel**? (nyckel-fritt är enklast idag)
- Returnerar det **JSON** som du förstår?
- Öppna en exempel-URL i webbläsaren — **fungerar det faktiskt just nu?**

---

## 5. Project ideas / Projektidéer

**English**
If you're stuck, here are starting points (pick one and make it yours):

- Movie / show finder
- Recipe browser
- Currency or unit converter
- Pokémon explorer
- NASA picture-of-the-day gallery
- GitHub user card
- Meme generator
- Country quiz game

Your course also has ready-made project briefs in the `projects/` folder if you want a guided idea.

**Svenska**
Om du kör fast, här är startpunkter (välj en och gör den till din):

- Film- / serie-sökare
- Receptbläddrare
- Valuta- eller enhetsomvandlare
- Pokémon-utforskare
- NASA:s dagens-bild-galleri
- GitHub-användarkort
- Meme-generator
- Land-quiz-spel

Din kurs har även färdiga projektbeskrivningar i mappen `projects/` om du vill ha en guidad idé.

---

## 6. Working iteratively with the AI / Att jobba iterativt med AI:n

**English**
Bring back everything from the week — this is where it all comes together:

- Build in **small steps** (Day 2): one feature at a time, review each change.
- Reuse the **app loop** (Day 4): input → request → response → display.
- Keep **small named functions** (Day 4) so the growing project stays readable.
- Add **loading / error / empty** states (Day 4) so it feels real.
- **Commit often** (Day 5) so you can always go back to a working version.
- **Explain your code** rule (all week): if you can't explain a line, ask the AI until you can.

**Svenska**
Ta med dig allt från veckan — det är här allt kommer samman:

- Bygg i **små steg** (Dag 2): en funktion i taget, granska varje ändring.
- Återanvänd **app-loopen** (Dag 4): inmatning → förfrågan → svar → visning.
- Behåll **små namngivna funktioner** (Dag 4) så det växande projektet förblir läsbart.
- Lägg till **laddnings- / fel- / tomt**-lägen (Dag 4) så det känns äkta.
- **Commit:a ofta** (Dag 5) så du alltid kan gå tillbaka till en fungerande version.
- **Förklara din kod**-regeln (hela veckan): kan du inte förklara en rad, fråga AI:n tills du kan.

---

## 7. Today's deliverable / Dagens leverabel

**English**
By the end of the day, you should have a **working prototype** with **at least one API feature**. It doesn't need to be polished or deployed yet — that's tomorrow (Day 7). It just needs to **run and do its core thing**.

Checklist:
- [ ] One-sentence purpose is clear.
- [ ] It uses at least one public API.
- [ ] The core feature works (input → result).
- [ ] It's committed to Git.

**Svenska**
I slutet av dagen bör du ha en **fungerande prototyp** med **minst en API-funktion**. Den behöver inte vara polerad eller deployad än — det är imorgon (Dag 7). Den behöver bara **köra och göra sin kärnsak**.

Checklista:
- [ ] En-menings-syftet är tydligt.
- [ ] Den använder minst ett publikt API.
- [ ] Kärnfunktionen fungerar (inmatning → resultat).
- [ ] Den är commit:ad till Git.

---

## 8. Concept check — can you answer these? / Konceptkoll — kan du svara på dessa?

**English**
1. State your app's purpose in **one sentence**.
2. **Which API** powers it, and have you confirmed it works?
3. What are your app's 1–2 core features (and what did you leave out on purpose)?
4. What's your plan if the API is down during the showcase?

**Svenska**
1. Beskriv din apps syfte i **en mening**.
2. **Vilket API** driver den, och har du bekräftat att det fungerar?
3. Vilka är din apps 1–2 kärnfunktioner (och vad valde du medvetet bort)?
4. Vad är din plan om API:et ligger nere under uppvisningen?

---

## 9. Key vocabulary / Nyckelord

| English | Svenska | Meaning / Betydelse |
|---------|---------|----------------------|
| Scope | Scope / avgränsning | How big/small the project is / Hur stort/litet projektet är |
| Core feature | Kärnfunktion | The main thing the app does / Det huvudsakliga appen gör |
| Prototype | Prototyp | An early working version / En tidig fungerande version |
| User flow | Användarflöde | The steps a user takes / Stegen en användare tar |
| Iterate | Iterera | Build/improve in small steps / Bygg/förbättra i små steg |
| Deliverable | Leverabel | What must be done by the end / Det som ska vara klart till slutet |
| Nice-to-have | Trevligt-att-ha | An extra, non-essential feature / En extra, icke-nödvändig funktion |

---

*Previously: Day 5 — Git, GitHub & Working Like a Real Developer.*
*Next up: Day 7 — Polish, Deploy & Showcase.*
*Tidigare: Dag 5 — Git, GitHub & att jobba som en riktig utvecklare.*
*Nästa: Dag 7 — Polera, deploya & visa upp.*

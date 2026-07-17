# Day 5 — Git, GitHub & Working Like a Real Developer
# Dag 5 — Git, GitHub & att jobba som en riktig utvecklare

> **How to use these notes / Så använder du dessa anteckningar**
> Read these after the lecture to recap. Each section is written in **English first**, then **Swedish (Svenska)**. Try to explain each idea out loud in your own words — if you can't, that's the part to re-read.
>
> Läs detta efter föreläsningen för att repetera. Varje avsnitt är skrivet **på engelska först**, sedan **på svenska**. Försök förklara varje idé högt med egna ord — om du inte kan, är det den delen du ska läsa om.

---

## Today's lesson plan / Dagens upplägg

**Total: 2 hours / 2 timmar**

| Block / Moment | Time / Tid | What happens / Vad vi gör |
|----------------|-----------|----------------------------|
| **Warm-up & recap**<br>*Uppvärmning & repetition* | 10 min | Recap the Day 4 app; today's goal: save & share code like a developer.<br>*Repetera Dag 4-appen; dagens mål: spara & dela kod som en utvecklare.* |
| **Concept mini-lesson**<br>*Konceptgenomgång* | 20 min | Git vs GitHub, the core ideas (repo/commit/push/pull), and branches.<br>*Git vs GitHub, kärnidéerna (repo/commit/push/pull), och branches.* |
| **Guided build**<br>*Guidat bygge* | 40 min | Put your app under version control: commit, push to GitHub, and add a README.<br>*Lägg din app under versionshantering: commit, push till GitHub, och lägg till en README.* |
| **Security mini-session**<br>*Säkerhetspass (mini)* | 20 min | Secrets hygiene, never commit keys, turn on 2FA, and what "hacking" really is.<br>*Hantering av hemligheter, commita aldrig nycklar, slå på 2FA, och vad "hacking" egentligen är.* |
| **Independent challenge**<br>*Egen utmaning* | 20 min | Create a branch, make a change, commit it, and merge it back into main.<br>*Skapa en branch, gör en ändring, commita den, och merga tillbaka till main.* |
| **Wrap-up & share**<br>*Avslutning & dela* | 10 min | Explain Git vs GitHub in your own words; preview project day.<br>*Förklara Git vs GitHub med egna ord; en förhandstitt på projektdagen.* |

---

## 1. What you'll be able to do after today / Vad du kan efter idag

**English**
- Explain **why** version control exists and what problem it solves.
- Explain the difference between **Git** and **GitHub**.
- Use the core Git ideas: **repo, commit, push/pull, history/undo**.
- Use a **branch** to try an idea safely.
- Put your Day 4 app on GitHub with a README.
- Understand basic **cyber-security & secrets hygiene** before going public.

**Svenska**
- Förklara **varför** versionshantering finns och vilket problem den löser.
- Förklara skillnaden mellan **Git** och **GitHub**.
- Använda Gits kärnidéer: **repo, commit, push/pull, historik/ångra**.
- Använda en **branch** för att testa en idé säkert.
- Lägga upp din Dag 4-app på GitHub med en README.
- Förstå grundläggande **cybersäkerhet & hantering av hemligheter** innan du blir offentlig.

---

## 2. Why version control exists / Varför versionshantering finns

**English**
Ever ended up with files like `project_final.html`, `project_final_v2.html`, `project_REALLY_final.html`? That's the problem version control solves.

**Version control** keeps a full **history of snapshots** of your project. You can:
- Go back to any earlier working version.
- See exactly what changed, when, and why.
- Never truly lose work.

**Svenska**
Har du någonsin haft filer som `projekt_final.html`, `projekt_final_v2.html`, `projekt_VERKLIGEN_final.html`? Det är problemet som versionshantering löser.

**Versionshantering** håller en full **historik av ögonblicksbilder** av ditt projekt. Du kan:
- Gå tillbaka till vilken tidigare fungerande version som helst.
- Se exakt vad som ändrades, när och varför.
- Aldrig egentligen förlora arbete.

---

## 3. Git vs. GitHub / Git vs. GitHub

**English**
These two are related but **not** the same:

- **Git** = the **tool** that runs on *your computer* and tracks changes to your files.
- **GitHub** = a **website** that hosts your Git projects online, so you can back them up, share them, and work with others.

Analogy: **Git** is like the "save history" feature; **GitHub** is like the cloud drive where you store and share that project.

**Svenska**
Dessa två hänger ihop men är **inte** samma sak:

- **Git** = **verktyget** som körs på *din dator* och spårar ändringar i dina filer.
- **GitHub** = en **webbplats** som lagrar dina Git-projekt online, så att du kan säkerhetskopiera, dela och jobba med andra.

Liknelse: **Git** är som "spara historik"-funktionen; **GitHub** är som molnenheten där du lagrar och delar projektet.

> **Key idea / Nyckelidé:** Git = the tool on your machine. GitHub = the website that hosts it. / Git = verktyget på din dator. GitHub = webbplatsen som lagrar det.

---

## 4. The core Git ideas / Gits kärnidéer

**English**
Keep it simple — four ideas cover most of what you need:

- **Repository (repo):** your project folder **plus its full history**.
- **Commit:** a **saved snapshot** with a short message describing what changed. (Commit often, with clear messages.)
- **Push / Pull:** **push** = send your commits up to GitHub; **pull** = get updates back down.
- **History & undo:** because every commit is saved, you can look back and **return to an earlier version** when you break something.

A typical cycle:
```text
make a change  →  commit (snapshot + message)  →  push (send to GitHub)
```

**Svenska**
Håll det enkelt — fyra idéer täcker det mesta du behöver:

- **Repository (repo):** din projektmapp **plus dess fulla historik**.
- **Commit:** en **sparad ögonblicksbild** med ett kort meddelande som beskriver vad som ändrades. (Commit:a ofta, med tydliga meddelanden.)
- **Push / Pull:** **push** = skicka upp dina commits till GitHub; **pull** = hämta ner uppdateringar.
- **Historik & ångra:** eftersom varje commit sparas kan du blicka bakåt och **återgå till en tidigare version** när du har sönder något.

(Samma cykel gäller: gör en ändring → commit → push.)

---

## 5. Branches: try ideas safely / Branches: testa idéer säkert

**English**
A **branch** is a parallel version of your project where you can try something **without touching the main version**. If the idea works, you **merge** it back into `main`. If it doesn't, you throw the branch away — main was never at risk.

- `main` = your stable, working version.
- a new branch = your experiment (e.g. `dark-theme`).
- **merge** = bring the experiment's changes back into `main`.

**Svenska**
En **branch** är en parallell version av ditt projekt där du kan testa något **utan att röra huvudversionen**. Om idén fungerar **mergar** (slår ihop) du den tillbaka till `main`. Om inte, slänger du branchen — main var aldrig i fara.

- `main` = din stabila, fungerande version.
- en ny branch = ditt experiment (t.ex. `dark-theme`).
- **merge** = ta med experimentets ändringar tillbaka till `main`.

---

## 6. Collaboration & AI + Git / Samarbete & AI + Git

**English**
GitHub is also how teams build together and how **open source** works:

- **Issues:** a to-do list / bug tracker for a project.
- **Pull requests (PRs):** a proposal to merge your changes, where others can review them first.
- **README:** the front-page file explaining what the project is and how to use it.

**AI + Git:** the AI can help write **commit messages** and **explain a diff** (what changed), but *you* decide what to commit and when.

**Svenska**
GitHub är också hur team bygger tillsammans och hur **öppen källkod (open source)** fungerar:

- **Issues:** en att-göra-lista / buggspårare för ett projekt.
- **Pull requests (PR):** ett förslag att slå ihop dina ändringar, där andra kan granska dem först.
- **README:** förstasidan-filen som förklarar vad projektet är och hur man använder det.

**AI + Git:** AI:n kan hjälpa till att skriva **commit-meddelanden** och **förklara en diff** (vad som ändrades), men *du* bestämmer vad som ska commit:as och när.

---

## 7. Today's build: put your app on GitHub / Dagens bygge: lägg din app på GitHub

**English**
Take your Day 4 app and put it under version control, end to end:

1. **Create a repo** (locally and/or on GitHub).
2. **Make several commits** with clear messages as you add a small feature.
3. **Push** the project to GitHub.
4. **Add a short README** describing the app and the API it uses.
5. Use the **history** to view (and revert) an earlier version.

A good commit message says *what* changed and *why*, briefly:
```text
Add wind speed to weather card
Fix crash when city is not found
```

**Svenska**
Ta din Dag 4-app och lägg den under versionshantering, hela vägen:

1. **Skapa ett repo** (lokalt och/eller på GitHub).
2. **Gör flera commits** med tydliga meddelanden medan du lägger till en liten funktion.
3. **Push:a** projektet till GitHub.
4. **Lägg till en kort README** som beskriver appen och API:et den använder.
5. Använd **historiken** för att se (och återställa) en tidigare version.

(Samma exempel på bra commit-meddelanden gäller: säg kort *vad* som ändrades och *varför*.)

---

## 8. Bonus: Cyber-security & staying safe / Bonus: Cybersäkerhet & att vara säker

**English**
Pushing code to a **public** repo is the perfect moment to talk about staying safe online. Keep it practical, not scary.

- **Why it matters right now:** a public repo is visible to everyone — including bots. The #1 beginner mistake is committing **secrets** (API keys, passwords, tokens). Automated scanners can find a leaked key **within minutes**.
- **Secrets hygiene:** keep keys **out of your code**; use a **`.gitignore`** and environment variables. If a key ever leaks, **revoke/rotate it immediately** — deleting the commit isn't enough, it's already in the history.
- **What "hacking" really is:** ethical vs. malicious hackers. Most real attacks exploit **simple mistakes** (exposed data, weak/reused passwords, phishing) — not movie-style magic.
- **Everyday defenses:** strong, unique passwords + a **password manager**, and turn on **two-factor authentication (2FA)** for GitHub.
- **The browser hides nothing:** anything in frontend JavaScript is **visible to users**, so you can't trust the browser with real secrets — that's *why* some APIs need a backend.
- **Ethics & the law:** attacking systems you don't own is **illegal**. Channel the curiosity into legal playgrounds like **Capture The Flag (CTF)** games and practice sites.

**Svenska**
Att push:a kod till ett **offentligt** repo är det perfekta tillfället att prata om att vara säker online. Håll det praktiskt, inte läskigt.

- **Varför det är viktigt just nu:** ett offentligt repo är synligt för alla — inklusive bottar. Nybörjarmisstag nummer 1 är att commit:a **hemligheter** (API-nycklar, lösenord, tokens). Automatiska skannrar kan hitta en läckt nyckel **inom minuter**.
- **Hantering av hemligheter:** håll nycklar **utanför din kod**; använd en **`.gitignore`** och miljövariabler. Om en nyckel läcker, **återkalla/rotera den omedelbart** — att radera commit:en räcker inte, den finns redan i historiken.
- **Vad "hacking" egentligen är:** etiska vs. illvilliga hackare. De flesta riktiga attacker utnyttjar **enkla misstag** (exponerad data, svaga/återanvända lösenord, nätfiske) — inte filmmagi.
- **Vardagsförsvar:** starka, unika lösenord + en **lösenordshanterare**, och slå på **tvåfaktorsautentisering (2FA)** för GitHub.
- **Webbläsaren döljer ingenting:** allt i frontend-JavaScript är **synligt för användare**, så du kan inte anförtro webbläsaren riktiga hemligheter — det är *därför* vissa API:er behöver en backend.
- **Etik & lagen:** att attackera system du inte äger är **olagligt**. Kanalisera nyfikenheten till lagliga lekplatser som **Capture The Flag (CTF)**-spel och övningssajter.

> **Key idea / Nyckelidé:** Never commit secrets to a public repo. If you do, revoke the key immediately. / Commit:a aldrig hemligheter till ett offentligt repo. Om du gör det, återkalla nyckeln omedelbart.

---

## 9. Independent challenge / Egen utmaning

**English**
Create a **branch**, make a visible change with the AI (e.g. a new color theme or a new section), **commit** it, then **merge** it back into `main`. Check the history to confirm your commits are there.

**Svenska**
Skapa en **branch**, gör en synlig ändring med AI:n (t.ex. ett nytt färgtema eller ett nytt avsnitt), **commit:a** den, och **merga** den sedan tillbaka till `main`. Kolla historiken för att bekräfta att dina commits finns där.

---

## 10. Concept check — can you answer these? / Konceptkoll — kan du svara på dessa?

**English**
1. Explain the difference between Git and GitHub.
2. What is a commit, and why would you want a project's full history?
3. What does a branch let you do safely?
4. **Security:** Name one thing you should never put in a public repo — and what you'd do if you pushed it by accident.

**Svenska**
1. Förklara skillnaden mellan Git och GitHub.
2. Vad är en commit, och varför skulle du vilja ha ett projekts fulla historik?
3. Vad låter en branch dig göra säkert?
4. **Säkerhet:** Namnge en sak du aldrig bör lägga i ett offentligt repo — och vad du skulle göra om du push:ade den av misstag.

---

## 11. Key vocabulary / Nyckelord

| English | Svenska | Meaning / Betydelse |
|---------|---------|----------------------|
| Version control | Versionshantering | Tracking a project's history / Att spåra ett projekts historik |
| Git | Git | The tool that tracks changes locally / Verktyget som spårar ändringar lokalt |
| GitHub | GitHub | Website that hosts Git projects / Webbplats som lagrar Git-projekt |
| Repository (repo) | Repository (repo) | Project + its full history / Projekt + dess fulla historik |
| Commit | Commit | A saved snapshot with a message / En sparad ögonblicksbild med meddelande |
| Push / Pull | Push / Pull | Send to / get from GitHub / Skicka till / hämta från GitHub |
| Branch | Branch (gren) | A safe parallel version / En säker parallell version |
| Merge | Merge (slå ihop) | Combine a branch back into main / Slå ihop en branch tillbaka i main |
| Pull request (PR) | Pull request (PR) | A reviewable proposal to merge / Ett granskningsbart förslag att merga |
| README | README | File explaining the project / Fil som förklarar projektet |
| Secret | Hemlighet | A key/password that must stay private / En nyckel/lösenord som måste vara privat |
| `.gitignore` | `.gitignore` | Lists files Git should not track / Listar filer Git inte ska spåra |
| 2FA | 2FA (tvåfaktor) | A second login step for security / Ett andra inloggningssteg för säkerhet |

---

*Previously: Day 4 — Building a Real Mini App Around an API.*
*Next up: Day 6 — Project Day: Design & Build Your Own App.*
*Tidigare: Dag 4 — Bygga en riktig mini-app runt ett API.*
*Nästa: Dag 6 — Projektdag: designa & bygg din egen app.*

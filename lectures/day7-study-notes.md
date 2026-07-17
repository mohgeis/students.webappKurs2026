# Day 7 — Polish, Deploy & Showcase
# Dag 7 — Polera, deploya & visa upp

> **How to use these notes / Så använder du dessa anteckningar**
> Read these after the lecture to recap. Each section is written in **English first**, then **Swedish (Svenska)**. Try to explain each idea out loud in your own words — if you can't, that's the part to re-read.
>
> Läs detta efter föreläsningen för att repetera. Varje avsnitt är skrivet **på engelska först**, sedan **på svenska**. Försök förklara varje idé högt med egna ord — om du inte kan, är det den delen du ska läsa om.

---

## Today's lesson plan / Dagens upplägg

**Total: 2 hours / 2 timmar**

| Block / Moment | Time / Tid | What happens / Vad vi gör |
|----------------|-----------|----------------------------|
| **Warm-up & recap**<br>*Uppvärmning & repetition* | 10 min | Today's goal: finish, deploy, and present.<br>*Dagens mål: bli klar, deploya, och presentera.* |
| **Concept mini-lesson**<br>*Konceptgenomgång* | 15 min | "Done enough", deploying for free, and writing a short README.<br>*"Tillräckligt klart", att deploya gratis, och att skriva en kort README.* |
| **Guided build: polish & deploy**<br>*Guidat bygge: polera & deploya* | 50 min | Final polish, fix your top 1–2 bugs, then deploy to a live public URL.<br>*Sista poleringen, fixa dina 1–2 viktigaste buggar, deploya sedan till en offentlig URL.* |
| **Showcase**<br>*Uppvisning* | 35 min | Each student demos their live app and shares four things.<br>*Varje elev visar sin live-app och delar fyra saker.* |
| **Wrap-up & next steps**<br>*Avslutning & nästa steg* | 10 min | Where to go next and how to keep learning after the course.<br>*Vart man går härnäst och hur man fortsätter lära sig efter kursen.* |

---

## 1. What you'll be able to do after today / Vad du kan efter idag

**English**
- Decide when your project is **"done enough"** and polish the right things.
- Fix your top 1–2 bugs and write a short README.
- **Deploy** your app to a free public URL and share the link.
- Present your work clearly: what it does, how it works, what was hard.
- Know how to keep learning after the course.

**Svenska**
- Avgöra när ditt projekt är **"tillräckligt klart"** och polera rätt saker.
- Fixa dina 1–2 viktigaste buggar och skriva en kort README.
- **Deploya** din app till en gratis offentlig URL och dela länken.
- Presentera ditt arbete tydligt: vad den gör, hur den fungerar, vad som var svårt.
- Veta hur du fortsätter lära dig efter kursen.

---

## 2. "Done enough": polish the right things / "Tillräckligt klart": polera rätt saker

**English**
You'll never fix *everything* — and that's fine. Shipping means finishing the important parts and letting the rest go.

- **Polish the UI a little:** readable text, some spacing, consistent colors. Small touches make a big difference.
- **Fix the top 1–2 bugs**, especially anything that crashes or confuses. Ignore tiny cosmetic issues for now.
- **Write a short README:** what the app does, which API it uses, and how to run it.
- Make sure your **loading / error / empty** states still work (from Day 4).

**Svenska**
Du kommer aldrig fixa *allt* — och det är okej. Att "ship:a" betyder att avsluta de viktiga delarna och släppa resten.

- **Polera gränssnittet lite:** läsbar text, lite luft, konsekventa färger. Små detaljer gör stor skillnad.
- **Fixa de 1–2 viktigaste buggarna**, särskilt sådant som kraschar eller förvirrar. Strunta i pyttesmå kosmetiska problem just nu.
- **Skriv en kort README:** vad appen gör, vilket API den använder, och hur man kör den.
- Se till att dina **laddnings- / fel- / tomt**-lägen fortfarande fungerar (från Dag 4).

> **Key idea / Nyckelidé:** Done and shared beats perfect and hidden. / Klar och delad slår perfekt och gömd.

---

## 3. What deploying means / Vad deploy betyder

**English**
So far your app only runs on **your** computer. **Deploying** puts it on the internet at a **public URL** anyone can open — no code or setup needed on their side.

- Before deploy: `file:///Users/you/project/index.html` (only you can see it).
- After deploy: `https://your-app.netlify.app` (anyone with the link can see it).

Because you put your project on GitHub on Day 5, deploying is now easy — most free hosts can **deploy straight from your GitHub repo**.

**Svenska**
Hittills körs din app bara på **din** dator. **Deploy** lägger den på internet på en **offentlig URL** som vem som helst kan öppna — utan kod eller installation hos dem.

- Före deploy: `file:///Users/du/projekt/index.html` (bara du kan se den).
- Efter deploy: `https://din-app.netlify.app` (vem som helst med länken kan se den).

Eftersom du lade ditt projekt på GitHub på Dag 5 är deploy nu enkelt — de flesta gratis-tjänster kan **deploya direkt från ditt GitHub-repo**.

---

## 4. Free places to deploy / Gratis ställen att deploya

**English**
Any of these can host a simple HTML/CSS/JS site for free:

- [GitHub Pages](https://pages.github.com/) — deploy straight from your repo.
- [Netlify](https://www.netlify.com/) — connect your repo or drag-and-drop your folder.
- [Vercel](https://vercel.com/) — connect your GitHub repo and deploy.

They all give you a public link you can share. Pick one and follow its steps with the AI's help.

**Svenska**
Vilken som helst av dessa kan hosta en enkel HTML/CSS/JS-sida gratis:

- [GitHub Pages](https://pages.github.com/) — deploya direkt från ditt repo.
- [Netlify](https://www.netlify.com/) — koppla ditt repo eller dra-och-släpp din mapp.
- [Vercel](https://vercel.com/) — koppla ditt GitHub-repo och deploya.

De ger dig alla en offentlig länk du kan dela. Välj en och följ dess steg med AI:ns hjälp.

---

## 5. Today's hands-on: polish + deploy / Dagens praktiska: polera + deploya

**English**
1. Do a final **polish** pass (UI, top bugs, README).
2. **Commit** and push your latest version to GitHub.
3. **Deploy** to a free host and get your public URL.
4. **Open the live link** on your phone or a friend's device to confirm it really works for everyone.

Tip: after deploying, test the live URL as if you were a first-time user. Does it load? Does the core feature work? Are errors handled?

**Svenska**
1. Gör en sista **poler**-runda (gränssnitt, viktigaste buggarna, README).
2. **Commit:a** och push:a din senaste version till GitHub.
3. **Deploya** till en gratis-tjänst och få din offentliga URL.
4. **Öppna live-länken** på din telefon eller en kompis enhet för att bekräfta att den verkligen fungerar för alla.

Tips: efter deploy, testa live-URL:en som om du vore en förstagångsanvändare. Laddar den? Fungerar kärnfunktionen? Hanteras fel?

---

## 6. The showcase / Uppvisningen

**English**
Each student demos their app (final 30–40 min). In your demo, share **four things**:

1. **What it does** — the one-sentence purpose.
2. **The API it uses** — where the live data comes from.
3. **One thing the AI got wrong that *you* fixed** — shows you're in charge, not the AI.
4. **One thing you're proud of** — a feature, a design touch, or a problem you solved.

Keep it short and show the **live** app, not slides of it.

**Svenska**
Varje elev visar sin app (sista 30–40 min). I din demo, dela **fyra saker**:

1. **Vad den gör** — en-menings-syftet.
2. **API:et den använder** — var livedatan kommer ifrån.
3. **En sak AI:n gjorde fel som *du* fixade** — visar att du bestämmer, inte AI:n.
4. **En sak du är stolt över** — en funktion, en designdetalj, eller ett problem du löste.

Håll det kort och visa den **live**-app, inte bilder av den.

---

## 7. Responsible AI & next steps / Ansvarsfull AI & nästa steg

**English**
- **Responsible AI use:** the AI is a powerful partner, but the **"explain your code" rule** still holds — understanding beats copy-pasting. Always check what it produces.
- **Keep learning:** add a second feature to your app, try a new API, rebuild something without the AI to test yourself, or help a friend build theirs.
- **Find communities:** open-source projects, coding challenges, and CTF security games (from Day 5) are great next playgrounds.

**Svenska**
- **Ansvarsfull AI-användning:** AI:n är en kraftfull partner, men **"förklara din kod"-regeln** gäller fortfarande — förståelse slår kopiera-klistra. Kontrollera alltid det den skapar.
- **Fortsätt lära:** lägg till en andra funktion i din app, testa ett nytt API, bygg om något utan AI:n för att testa dig själv, eller hjälp en kompis bygga sin.
- **Hitta gemenskaper:** öppen-källkods-projekt, kodutmaningar och CTF-säkerhetsspel (från Dag 5) är utmärkta nästa lekplatser.

---

## 8. Concept check — can you answer these? / Konceptkoll — kan du svara på dessa?

**English**
1. What does it mean to "deploy" an app, and how is a live URL different from a local file?
2. Name one free place to deploy a static site.
3. What four things will you share in your showcase demo?
4. What's the "explain your code" rule, and why does it still matter now?

**Svenska**
1. Vad betyder det att "deploya" en app, och hur skiljer sig en live-URL från en lokal fil?
2. Namnge ett gratis ställe att deploya en statisk sida.
3. Vilka fyra saker ska du dela i din uppvisnings-demo?
4. Vad är "förklara din kod"-regeln, och varför är den fortfarande viktig nu?

---

## 9. Key vocabulary / Nyckelord

| English | Svenska | Meaning / Betydelse |
|---------|---------|----------------------|
| Polish | Polera | Small final improvements / Små sista förbättringar |
| Deploy | Deploya | Put the app online publicly / Lägg appen online offentligt |
| Public URL | Offentlig URL | A link anyone can open / En länk vem som helst kan öppna |
| Static site | Statisk sida | A site of just HTML/CSS/JS files / En sida av bara HTML/CSS/JS-filer |
| Host | Host / värdtjänst | A service that serves your site / En tjänst som serverar din sida |
| Showcase / demo | Uppvisning / demo | Presenting your working app / Att presentera din fungerande app |
| Ship | Ship:a / leverera | Finish and release something / Avsluta och släppa något |

---

## 10. Course wrap-up / Kurssammanfattning

**English**
Look how far you came in 7 days: from "what is AI?" to a **live web app of your own design that talks to a real API** — built with the AI as your partner, and fully understood by you. That's exactly what the course set out to do.

Keep building, keep asking *why*, and keep owning your code.

**Svenska**
Se hur långt du kom på 7 dagar: från "vad är AI?" till en **live-webbapp av din egen design som pratar med ett riktigt API** — byggd med AI:n som din partner, och helt förstådd av dig. Det är precis vad kursen ville uppnå.

Fortsätt bygga, fortsätt fråga *varför*, och fortsätt äga din kod.

---

*Previously: Day 6 — Project Day: Design & Build Your Own App.*
*Tidigare: Dag 6 — Projektdag: designa & bygg din egen app.*

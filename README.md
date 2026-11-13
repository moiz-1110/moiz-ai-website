# Website: Prive AI platform

Dit document beschrijft wat de website is, wat erop moet staan, hoe hij eruit ziet en hoe hij live gaat. Gebruik het als opdracht voor jezelf, een webdesigner of een AI-bouwtool.

## 1. Doel van de site

Eén pagina die een operationeel B2B-bedrijf in een paar seconden laat snappen wat we doen, met één actie: **een demo van 30 minuten plannen**.

De site is simpel en duidelijk. Korte blokken, weinig tekst, één boodschap per blok.

## 2. De kern

> Wij maken je bedrijf klaar voor AI: eerst je data en systemen op orde en gekoppeld, daarna bouwen en beheren wij de flows en agents die je tijd opleveren.

- Alle applicaties van het bedrijf worden aangesloten op één platform.
- Data wordt centraal beheerd (PIM, CRM, DAM).
- Daarbovenop bouwen en beheren wij flows, apps, agents en een dashboard.
- Het bedrijf bespaart uren, kosten en fouten, krijgt betere kwaliteit en meer inzicht. Alles op één plek en controleerbaar.
- Onderscheid: de klant kan veel zelf, maar wij beginnen bij data-begrip en beheren het daarna. Daardoor is de kwaliteit beter en blijft het werken.
- Uitleg in één beeld: "De IT-partner regelde je netwerk. Wij regelen je AI." (Managed AI Service Provider)
- Doelgroep: operationele B2B-bedrijven. Eén focus, geen aparte pagina's per branche.

## 3. Regels voor de teksten

- Geen cijfers. Wel: "we besparen uren, kosten en fouten".
- Geen prijzen. Alleen drie niveaus zonder bedragen. Prijs komt in het demo-gesprek.
- Geen concurrenten noemen.
- Geen referentie met naam. Het voorbeeld is anoniem.
- Geen jargon. PIM, CRM en DAM zijn "waar we je data neerzetten", niet drie losse producten.
- Eén knop op de hele site: "Plan een demo".
- Alle teksten, logo's en beeld zijn eigen werk. Nooit iets van een andere site overnemen.

## 4. Data, EU en privacy

Dit is een sterk vertrouwenspunt en moet kloppen met wat we echt doen.

Wat we mogen zeggen:

- De interne data van het bedrijf staat in de EU.
- De AI verwerkt die data in een EU-context.
- Data van elk bedrijf is strikt gescheiden van die van andere bedrijven.
- Een mens keurt altijd goed. De AI maakt een concept, de medewerker klikt op goedkeuren.

Voorgestelde tekst:

> Je bedrijfsdata blijft in Europa. Het platform en de AI waarmee we je data verwerken draaien in de EU, en de data van elk bedrijf is strikt gescheiden.

WorkOS regelt alleen inloggen en toegang en bevat geen interne bedrijfsdata. Het hoeft daarom niet in de EU-belofte en niet op de site genoemd te worden.

De EU-belofte gaat over het platform, niet over de marketingsite zelf. Op de site staat geen bedrijfsdata.

Controleer vóór livegang:

- [ ] Draait de AI-verwerking van klantdata echt via een EU-regio?
- [ ] Gaat er geen klantdata via een dienst die buiten de EU verwerkt? Nango Cloud heeft geen EU-regio.
- [ ] Verwerkersovereenkomst en lijst met subverwerkers kunnen op verzoek gedeeld worden.
- [ ] Een jurist of AVG-adviseur heeft de formulering gezien.

Klopt een van deze punten niet, schrijf dan "ons platform draait in de EU" en laat "alle data en AI in de EU" weg.

## 5. Opbouw van de pagina

1. **Hero**: kop "Maak je bedrijf klaar voor AI.", één zin subkop, knop "Plan een demo".
2. **Het probleem**: systemen praten niet met elkaar, data is niet klaar voor AI, medewerkers typen over. Drie korte punten met icoon.
3. **Hoe het werkt in drie stappen**: data op orde, systemen koppelen, flows en agents doen het werk.
4. **Eén concreet voorbeeld (anoniem)**: mail binnen, AI leest hem, concept-order in het ERP, medewerker klikt op goedkeuren. Als screenshot of korte animatie.
5. **Wat je krijgt**: flows, apps, dashboard, beheer. Vier blokken met één zin elk.
6. **Vertrouwen**: mens keurt altijd goed, data per bedrijf gescheiden, data en AI in de EU (zie sectie 4).
7. **Abonnementen**: Starter, Groei, Pro (namen voorlopig), zonder bedragen, elk met de knop "Plan een demo".
8. **Veelgestelde vragen**: "Kunnen we dit niet zelf?", "Wat als de AI een fout maakt?", "Waar staat mijn data?", "Hoe lang duurt het voor we starten?"
9. **Afsluiting**: korte zin en nog een keer "Plan een demo".

Footer: bedrijfsnaam, contact, privacyverklaring, cookie-instellingen.

## 6. Stijl

- Gevoel: rustig, helder, betrouwbaar, modern. Geen AI-hype (geen robots, geen neonpaars, geen sterretjes).
- Kleur: één hoofdkleur, neutrale tinten (wit, lichtgrijs, donkergrijs) en één accentkleur voor de knop.
- Lettertype: één schreefloos lettertype, bijvoorbeeld Inter. Grote, duidelijke koppen.
- Veel witruimte.
- Beeld: echte schermen van het platform (anoniem) en eenvoudige schema's. Geen stockfoto's.
- Toon: gewone taal, "je" en "jouw", korte zinnen.
- Mobiel: werkt net zo goed op een telefoon, de knop is altijd snel te bereiken.

## 7. Techniek

- Statische site met Astro (of gewone HTML met Tailwind). Geen backend.
- Eén repo voor de site, los van de platformcode.
- Snel en licht, goede laadtijd.
- Demo plannen via een boekingstool die in de EU verwerkt (bijvoorbeeld Cal.com met EU-regio). Zo slaan we zelf geen persoonsgegevens op.
- Analytics zonder cookies (Cloudflare Web Analytics). Cookiebanner alleen als er andere niet-noodzakelijke cookies zijn.
- Privacyverklaring op de site.
- Geen geheimen in de repo. Alleen publieke content en publieke sleutels.

Voorgestelde mapstructuur:

```
website/
├── src/
│   ├── pages/index.astro
│   ├── components/      (Hero, Probleem, Stappen, Voorbeeld, Vertrouwen, Abonnementen, FAQ)
│   └── styles/
├── public/              (logo, afbeeldingen, favicon)
├── astro.config.mjs
└── package.json
```

## 8. Deployment: GitHub en Cloudflare Pages

1. Zet de site in een eigen GitHub-repo.
2. Maak in Cloudflare een Pages-project en koppel de repo.
3. Build command: `npm run build`. Output directory: `dist`.
4. Elke push naar `main` gaat automatisch live.
5. Elke andere branch krijgt een eigen preview-link om wijzigingen te bekijken voor ze live gaan.
6. Koppel het domein in Cloudflare. HTTPS is automatisch.
7. Zet Cloudflare Web Analytics aan.

Werkwijze voor wijzigingen: nieuwe branch, push, preview bekijken, mergen naar `main`.

## 9. Definition of done

- [ ] Eén pagina, negen blokken, één knop.
- [ ] Alle teksten volgen de regels in sectie 3.
- [ ] De EU-tekst is gecontroleerd tegen de lijst in sectie 4.
- [ ] Voorbeeldflow staat erop, anoniem.
- [ ] Demo-aanvraag werkt en komt binnen.
- [ ] Privacyverklaring staat erop.
- [ ] Werkt op telefoon en laptop.
- [ ] Live via GitHub en Cloudflare Pages op het eigen domein.
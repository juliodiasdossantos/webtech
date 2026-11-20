# Labo 1 - Je werkplek en je eerste pagina's: modeloplossing

Dit is een mogelijke oplossing van labo 1, niet de enige. Vergelijk ze met je eigen werk: niet om over te nemen, maar om te zien waar jouw pagina's afwijken en of dat erg is. Een andere tekst of een andere foto is nooit fout; een andere boom soms wel. De map `labo-01/` is wat er op het einde van het labo in je repository `webtech` staat. Open ze met Live Server om de links te volgen. De verwijzingen (1.8, F1.5) zijn naar de syllabus.

## 1. Je werkplek

De map `webtech` is je workspace (*File - Open Folder*), met daarin de submap `labo-01`. Elk bestand begint met het skelet van syllabus 1.5, uit het hoofd getypt: `<!doctype html>`, `html` met `lang="nl"`, `head` met `charset`, `viewport` en `title`, en een `body`. Bestandsnamen staan in kleine letters, zonder spaties (F1.6).

Veelgemaakte fouten: een los bestand openen in plaats van de map, waardoor Live Server niets doet of de verkeerde map opent; de map in OneDrive of iCloud zetten, wat vanaf labo 2 botst met de repository; het skelet kopiëren in plaats van typen, wat je merkt zodra je het in oefening 3 zonder voorbeeld moet schrijven.

## 2. Kijken naar de pagina

Haal je `</p>` weg, dan staat de sluittag in de Elements-tab tóch: de browser herstelt je HTML stil (syllabus 1.6 en het motorkap-kader). Dat is het punt van deze oefening. De Elements-tab toont de boom die de browser bouwde, niet het bestand dat jij schreef, en "de pagina werkt" bewijst dus niets (F1.10). Vanaf nu controleer je de boom, niet alleen het uitzicht.

## 3. Over mij

Zie `over-mij.html`. Eén kop met de naam, twee of drie paragrafen, een kop "Wat ik graag doe" met een `ul`, een kop "Mijn ochtend" met een `ol`, en in een paragraaf één `em` en één `strong`. In de modeloplossing zijn de tussenkoppen `h3`, omdat de `h1` van de site in de header staat (oefening 5) en de naam de `h2` van de pagina is. Had jij `h2`-tussenkoppen onder een `h1`-naam, dan is dat even goed: niveaus mogen niet springen, meer niet (F1.2).

Veelgemaakte fouten: tekst rechtstreeks in `body` of `main`, zonder `p` (F1.1); tekst of een `p` als rechtstreeks kind van een `ul` (F1.4), zichtbaar in de Elements-tab als een tekstknoop vóór het eerste `li`; `em` en `strong` kiezen om het uitzicht ("ik wil dit vet"), terwijl klemtoon `em` is en belang `strong`; `<br>` als witruimte tussen paragrafen.

## 4. Tags opzoeken

De acht commentaarregels bovenaan `over-mij.html` zijn een antwoord in eigen woorden. De kern per element: `main` is uniek per pagina en komt één keer voor; `header` en `footer` keren op elke pagina terug; `nav` is een blok links; `article` staat op zichzelf; `aside` staat ernaast; `a` heeft een `href`; `img` heeft een `src` en een `alt`. Een zin van MDN overschrijven is niet fout, maar kan je ze in je eigen woorden herhalen?

## 5. De structuur van een pagina

Zie `hobby.html`. Het grondplan: `header`, `main` en `footer` als de drie kinderen van `body` (syllabus 1.8). De `nav` bevat een `ul` met vier links. De `img` heeft een relatief pad `afbeeldingen/naam.jpg` en een `alt` die zegt wat er op de foto te zien is. De externe link heeft een volledig adres met `https://`. Dezelfde header en footer staan in alle pagina's.

Veelgemaakte fouten: de `nav` in `main` of de `h1` in de `footer` (F1.8); `alt="foto"` of geen `alt` (F1.5), en ook "een foto van mij" is zwak, want het zegt niet wat er te zien is; een bestandsnaam met hoofdletter of spatie (`Schelde 1.JPG`) die lokaal werkt en na publicatie breekt (F1.6); de navigatie kopiëren naar de andere pagina's maar één link vergeten; `href="#"` als tijdelijke link terwijl de pagina's bestaan.

## 6. Boodschappenlijst

Zie `boodschappen.html`. Een `ul` met uitsluitend `li`-kinderen; wat online gekocht wordt, heeft een `a` ín het `li`, niet eromheen. De pagina staat in elke navigatie. Een `<a>` rond een `<li>` is de klassieke fout hier: de validator meldt ze, de browser herstelt ze stil.

## 7. Je pagina's online

De repository heet `webtech`, is public en heeft een README. De map `labo-01` is als geheel geüpload (niet de losse bestanden, anders ontbreekt `afbeeldingen/`). Pages staat op `main` en `/ (root)`; het adres is `https://gebruikersnaam.github.io/webtech/labo-01/index.html`, met de gebruikersnaam in kleine letters.

Veelgemaakte fouten: losse bestanden slepen, waardoor de afbeelding online ontbreekt; de repository privé zetten, waardoor Pages niet werkt op een gratis account; een afbeelding die lokaal werkt en online kapot is, bijna altijd F1.6; opnieuw uploaden terwijl Pages gewoon nog even bezig is.

## Klaar?

De validator meldt op de vier pagina's van de modeloplossing niets. Meldt hij bij jou een ontbrekende `title`, tekst rechtstreeks in een `ul`, gekruiste tags of een ontbrekende `alt`, dan zijn dat precies de fouten die de browser stil herstelde en die je dus nooit zag.

De boom van `hobby.html`, zoals je ze op papier tekent:

```
body
  header
    h1
    nav
      ul
        li  a
        li  a
        li  a
        li  a
  main
    h2
    p
    img
    p
      a
  footer
    p
```

Tekende je `a` als broer van `li` in plaats van als kind, dan klopt de nesting van je lijst niet. Hing je `img` onder `p` terwijl het ernaast staat, vergelijk dan nog eens met de Elements-tab.

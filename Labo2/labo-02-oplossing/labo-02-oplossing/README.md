# Labo 2 - Wie wint? Selectors, cascade en je eerste nabouw: modeloplossing

Dit is een mogelijke oplossing van labo 2, niet de enige. Vergelijk ze met je eigen werk: niet om over te nemen, maar om te zien waar jouw CSS afwijkt en of dat erg is. Een andere weg naar hetzelfde screenshot is niet fout; een weg die de regels breekt (een gewijzigde `index.html`, id-selectors, `!important`, px voor tekst, letterlijke kleuren waar tokens horen) wel. De HTML-bestanden zijn identiek aan de starter. De verwijzingen (2.7, F2.4) zijn naar de syllabus.

## 1. Van uploaden naar Commit & Sync

Geen modeloplossing: dit is een handeling, geen bestand. Het resultaat is een gekloonde map `webtech` op je schijf, met `labo-01` en `labo-02` erin, en een repository op github.com die na elke *Commit & Sync* hetzelfde toont. Liep het mis, dan was het bijna altijd één van de vier storingen uit de opgave: Git niet geïnstalleerd of VS Code niet herstart, `user.name` en `user.email` niet gezet, niet aangemeld bij GitHub, of gekloond in OneDrive.

## 2. Selectors schrijven en lezen

Zie `selectors/css/stijl.css`: per opdracht de selector, en in commentaar de typische fout. De lat is precisie, niet uitzicht. `nav a` en `header nav ul li a` geven hetzelfde beeld, maar het tweede sleept vier schakels mee die niets doen en elke latere override zwaarder maken (2.4, en het AI-kader van hoofdstuk 2). Bij opdracht 3 is `.rassen li` de klassieker: het verschil met `.rassen > li` zie je alleen in de binnenlijsten. Bij opdracht 8 hoort `:focus` naast `:hover`; wie alleen hover stylet, laat wie met de tab-toets navigeert in het donker (F2.11).

De vijf leesselectors, in één zin elk:

- a. `header nav ul li a`: elke link in de navigatie, dezelfde drie als bij opdracht 1, met vier schakels te veel
- b. `article > p`: elke paragraaf die een direct kind is van `article`; de slogan niet, die zit in de header
- c. `.uren li:nth-child(3)`: het derde item van de openingsuren, woensdag
- d. `h2 ~ p`: elke `p` die na een `h2` komt binnen dezelfde ouder; hier alle paragrafen in `article`
- e. `.rassen li:first-child`: elk `li` dat het eerste kind van zijn ouder is, ergens in `.rassen`: "Honden", maar ook het eerste item van elke binnenlijst

## 3. Voorspel, daarna kijk je na

| vraag | kleur | trede | waarom |
|---|---|---|---|
| 1 | groen | herkomst | jouw regel verslaat de blauwe link van de user agent stylesheet |
| 2 | blauw | volgorde | dezelfde selector twee keer; de laatste wint |
| 3 | rood | specificiteit | een class (0,1,0) verslaat een element (0,0,1), ook al staat het element later |
| 4 | rood | de selector raakt niet | `.v4 > a` raakt niets: de `a` is geen direct kind van de section; alleen `.v4 a` raakt |
| 5 | blauw | specificiteit | één id verslaat drie classes |
| 6 | blauw | overerving verliest | `.v6-tekst` raakt de `p` zelf; de rode kleur op de section is alleen geërfd |
| 7 | rood | overerving | geen enkele regel raakt `blockquote`; hij erft van `.v7` |
| 8 | blauw | inline style | het style-attribuut wint van elke selector in de stylesheet (2.3) |
| 9 | rood | `!important` | springt boven de normale orde uit; de class verliest (2.7) |
| 10 | groen, normale grootte | vergeten puntkomma (F2.3) | `font-size: 1.5rem color: blue` is één onbegrijpelijke declaratie; de browser laat ze vallen en `color: green` blijft |

Zat je fout bij 4, 8 of 10, dan ben je in goed gezelschap. Bij 4 denken velen "groen, want `>` is specifieker": nee, `>` verandert niets aan de specificiteit, de regel raakt gewoon niet (F2.4). Bij 10 toont het Styles-paneel een waarschuwingsteken; dat is het signaal dat je vanaf nu na elke werksessie zoekt.

## 4. De nabouw

Zie `nabouw/css/stijl.css`. De opbouw is die van de tip in de opgave: eerst het tokenblok met de vijf kleuren en de twee lettertypes, dan de basis op `body` (achtergrond, kleur, lettertype, regelhoogte) zodat alles erft (2.6), dan alleen de uitzonderingen: de koppen in Georgia en níét vet (`font-weight: normal`, want koppen in Georgia zijn standaard vet en in het screenshot niet), de navigatie en de links in `main` apart (`nav a` en `main a`, niet één `a`-regel, anders worden ook de footer-links accentkleur), het zebrapatroon met `.kaart li:nth-child(odd)` (het eerste item is gekleurd, dus oneven), en overal `:focus` naast `:hover`.

Veelgemaakte fouten: `font-size: 48px` in plaats van `3rem` (F2.9), want "16 px basis" in de opgave is de hint, niet de eenheid; kleuren letterlijk in de regels in plaats van via `var()` (F2.10), wat werkt maar het punt mist; `font-weight: normal` op de koppen vergeten; `line-height: 1.6rem` in plaats van `1.6` (2.8), waardoor de intro op 1.25rem te weinig regelhoogte krijgt; `:nth-child(even)` waar `odd` moest, kijk naar het screenshot; `css/stijl.css` naast `index.html` gezet in plaats van in `css/` (F2.1).

Het Zen-moment: `css/zen.css` gebruikt `text-transform` en `letter-spacing` uit hoofdstuk 7 en `list-style: none`. Kijken mag, nadoen hoeft nog niet.

## 6. Je site

Geen modeloplossing: je site is van jou. Waar je zelf op controleert: `site/` staat naast `labo-01/`; één `site/css/stijl.css`, gelinkt vanuit alle vier de pagina's met `css/stijl.css`; een tokenblok met rolnamen (`--color-accent`, niet `--color-blauw`); de basis op `body`; `nav a` met `:hover` én `:focus`; nergens `#`, `!important` of `style=""`; en de stijl staat ook live op `https://JOUWGEBRUIKERSNAAM.github.io/webtech/site/`.

Veelgemaakte fouten: de stylesheet in `labo-01` gezet en `site` vergeten; `href="stijl.css"` zonder `css/`; een token gedeclareerd maar nergens gebruikt; `a:hover` zonder `:focus`.

## Thuis: R2.3

Een antwoordmodel bestaat niet, want elk model geeft andere output. De meetlat wel: elke bevinding verwijst naar een sectie of een foutnummer. Wat je vrijwel zeker vond: px voor lettergroottes (F2.9), kettingen als `header nav ul li a` (AI-kader), `!important` waar het model de user agent-stijl "moest" overschrijven (F2.6), letterlijke kleuren ondanks de meegegeven tokens (F2.10), en de geneste spelling van 2.5.

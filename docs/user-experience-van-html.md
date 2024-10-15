# All Human - Accessible Website

## User Experience van HTML

Als frontender heb je de verantwoordelijkheid om een goede gebruikerservaring voor eindgebruikers neer te zetten. Goede HTML helpt bij die goede _User Experience (UX)_. En slechte HTML zorgt voor een slechte gebruikerservaring. Dat klinkt logisch, maar het Internet (en ook ChatGPT) staat vol met voorbeelden van slechte HTML.

Voordat je kunt bepalen wat goede HTML is, moet je vooral leren wat HTML zoal kan. En welke functionaliteiten je van de browser gratis krijgt, als je de juiste HTML elementen schrijft.

Je hebt maandag gezien dat Mensen (waar deze sprint om draait) veel verschillende browsers en apparaten gebruiken. Al die browsers kunnen overweg met HTML, de standaard waar het hele Web op draait.

### Links

De allereerste browser ooit, zo'n 30 jaar geleden, kon al met links (`<a href="...">`) overweg. Sindsdien is er alleen maar leuk spul bijgekomen in HTML.

Maak een blanco HTML pagina in je editor, noem deze `ux.html` en sla deze op op je Bureaublad. Begin met een `<h1>UX in HTML</h1>` en maak een eerste subkop, `<h2>Links</h2>`. Schrijf daaronder een simpele `<a href="ux.html">UX in HTML<a>` link (naar zichzelf dus), en open de pagina in een willekeurige browser.

Onderzoek met je tafel welke functionaliteiten _verschillende browsers_ je geven bij zo'n link. Gebruik je rechtermuisknop, doe een _long tap_ op je telefoon, gebruik de Shift-, Control-, Command-, Option-, Alt- of een combinatie van die toetsen bij het klikken op die link.

Voeg het `download` attribuut toe, en onderzoek wat er met de functionaliteit in de browser verandert.

Verander het `download` attribuut naar `target="_blank"`, en onderzoek wat er met de functionaliteit in de browser verandert, als je op de link klikt.

Voeg meerdere links toe aan je HTML, en probeer met alleen je toetsenbord de links te bereiken en te volgen. Wat is de standaard tabvolgorde?

Met zoiets simpels als een link kun je al alle kanten op. <!-- Hrhr --> Wil je de eindgebruiker dus de mogelijkheid geven om ergens _heen_ te gaan, gebruik dan een `<a>` (_anchor_). En dus geen `<button>`, want daarbij krijg je niet die functionaliteit van een browser.

#### Bronnen

- [`<a>`: The Anchor element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
- [Het `href` attribuut](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#href)
- [Het `download` attribuut](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#download)
- [Het `target` attribuut](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#target)


### Afbeeldingen

Door foto's, logo's en andere visuele afbeeldingen toe te voegen in HTML, maken we het meteen ingewikkeld. Niet iedere browser kan namelijk de afbeeldingen downloaden, en niet ieder mens kan überhaupt _zien_. In HTML willen we met die gebruikerservaring ook rekening houden.

Voeg in jouw `ux.html` de volgende subkop toe, `<h2>Afbeeldingen</h2>`. We hebben nog geen afbeeldingen, maar de HTML kunnen we wel alvast schrijven. Zet de volgende HTML onder je kop: `<a href="ux.html"><img width="200" height="100"></a>`, en bekijk het resultaat in je browser.

De afbeelding kan nog niet gedownload worden, dus de browser tekent hier ook geen pixels.

Voeg `alt="UX in HTML"` toe aan de `<img>` tag, en bekijk het in je browser. Welke UX vind je beter als de afbeelding niet getoond kan worden?

We gaan nu tekst én een icoon toevoegen aan onze link, ook al hebben we de afbeelding voor het icoontje nog niet. En we hebben net geleerd dat een `alt` attribuut “beter” is voor de UX, dus die zetten we er ook meteen in. We willen immers het juiste doen. Gebruik de volgende HTML: `<a href="ux.html"><img alt="UX in HTML">UX in HTML</a>`, en bekijk het in je browser. Hm, is dit nou echt beter? Wat als je van dat `alt` attribuut `alt="Icoon"`, of `alt="Download icoon"` maakt? En wat als je gewoon `alt=""` doet in dit geval? Welke UX vind jij beter?

Onderzoek en bespreek met je tafel op welke verschillende manieren je afbeeldingen kunt gebruiken, en wat voor soort `alt` attribuut daarbij hoort.

Nu weet je waarom je altijd na moet denken over de inhoud van je `alt` attributen, en waarom dat bijvoorbeeld in Lighthouse en de WCAG richtlijnen langskomt. De context van een afbeelding is relevant bij het schrijven van een `alt` attribuut.

#### Bronnen

- [`<img>`: The Image Embed element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)
- [Het `alt` attribuut](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/alt#usage_notes)
- [Requirements for providing text to act as an alternative for images @ de HTML specificatie (geavanceerd)](https://html.spec.whatwg.org/multipage/images.html#alt)


### Labels voor invoervelden

Bij het maken van formulieren, voor bijvoorbeeld filters of zoekvelden, kun je verschillende invoervelden gebruiken. Denk aan een lijst met checkboxes of radios. Voor formulieren hangt een goede UX onder andere af van goede labels.

Maak een nieuwe subkop aan, `<h2>Labels voor invoervelden</h2>`, plak de volgene HTML eronder, en test het in je browser door verschillende docenten aan te klikken.

```html
<fieldset>
  <legend>Docenten</legend>
  <ul>
    <li><input type="checkbox"> Charley</li>
    <li><input type="checkbox"> Cyd</li>
    <li><input type="checkbox"> Dion</li>
    <li><input type="checkbox"> Dorien</li>
    <li><input type="checkbox"> Joost</li>
    <li><input type="checkbox"> Justus</li>
    <li><input type="checkbox"> Koop</li>
    <li><input type="checkbox"> Krijn</li>
    <li><input type="checkbox"> Sanne</li>
    <li><input type="checkbox"> Suus</li>
  </ul>
</fieldset>
```

De UX is verschrikkelijk. Lighthouse klaagt er ook over. WCAG audit niet gehaald. Helaas.

Wat nou als je om elke `<input>` én elke docent een `<label>...</label>` zet? (💡 Pro-tip: zoek uit hoe _multi-cursor editing_ in je editor werkt, want daar ga je veel plezier van hebben.) Test je wijzigingen.

Een paar vliegen in één klap: je hebt de UX voor _alle_ gebruikers verbeterd, Lighthouse klaagt wat minder, en die WCAG checklist is zo ook wel te doen. Leer jezelf aan om bij elke `<input>` een `<label>` te koppelen. Niet alleen bij checkboxjes, maar bij _alle_ invoervelden.

Test dit maar in je browser:

```html
<fieldset>
  <legend>Adresgegevens</legend>
  <p><input type="text"></p>
  <p><input type="text"></p>
  <p><input type="text"></p>
  <p><input type="text"></p>
</fieldset>
```

Zonder labels is het voor _iedereen_ ontoegankelijk en onbruikbaar, omdat je geen idee hebt wat je waar moet invullen.

Plak het volgende voorbeeld onder je code, zodat je het kunt vergelijken.

```html
<fieldset>
  <legend>Adresgegevens</legend>
  <p>Straat: <input type="text"></p>
  <p>Huisnummer: <input type="text"></p>
  <p>Postcode: <input type="text"></p>
  <p>Plaats: <input type="text"></p>
</fieldset>
```

Als we wél de tekstuele labels toevoegen, maar _niet_ de `<label>` elementen, blijft het voor een deel van je eindgebruikers ontoegankelijk en onbruikbaar. En HTML schrijf je voor _iedereen_.

Je wilt het dus als volgt doen. Plak dit onder je code, zodat je beide versies kunt vergelijken.

```html
<fieldset>
  <legend>Adresgegevens</legend>
  <p><label>Straat: <input type="text"></label></p>
  <p><label>Huisnummer: <input type="text"></label></p>
  <p><label>Postcode: <input type="text"></label></p>
  <p><label>Plaats: <input type="text"></label></p>
</fieldset>
```

Bijkomend voordeel is dat je nu ook op het label kunt klikken, en dat je met CSS meer kunt doen. Omdat je een goed HTML fundament hebt geschreven. Plak deze HTML/CSS onderaan in je `ux.html` om het te testen.

```html
<style>
input:hover {
  outline: 2px solid blue;
}
</style>
```

(💡 Pro-tip: voeg `contenteditable style="display:block;white-space:pre;font-family:monospace;border:1px solid;padding:1em;"` toe aan het `<style>` element, en bewerk de CSS live in je browser!)

#### Bronnen

- [`<label>`: The Label element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)
- [`<fieldset>`: The Field Set element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset)
- [Pro-tip: Multiple selections (multi-cursor) @ VS Code](https://code.visualstudio.com/docs/editor/codebasics#_multiple-selections-multicursor)
- [Geavanceerd: Het `contenteditable` attribuut](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contenteditable)


### Details

#### Bronnen

- [`<details>`: The Details disclosure element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details)
- [Het `open` attribuut](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details#open)
- [Het `name` attribuut](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details#name)


### Dialog & popover

#### Bronnen

- [`<dialog>`: The Dialog element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)
- [Het `popover` attribuut](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/popover)


### Headings

En door je content een goede heading structuur te geven, zorg je dat bijvoorbeeld Inhoudsopgaves automatisch gemaakt kunnen worden. Sommige browsers bieden deze functionaliteit.

Onderzoek met je tafel hoe je de screen reader die je geïnstalleerd hebt de heading structuur van je UX pagina kunt laten voorlezen.

#### Bronnen

- [`<h1>`–`<h6>`: The HTML Section Heading elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
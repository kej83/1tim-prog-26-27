# Oppgavesett: HTML, CSS & Boksmodellen (`height`, `width`, `padding`)

### Repetisjon: Hva vi har lært så langt

* **HTML-struktur:** Grunnleggende koder som `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`, og semantiske elementer som `<h1>`-`<h6>`, `<p>`, `<div>` og `<span>`.
* **CSS-grunnleggende:** Syntaks, selektorer (element, klasse `.`, ID `#`), farger (`color`, `background-color`) og tekstformatering (`font-family`, `font-size`, `text-align`).
* **Boksmodellen:**
* **`width` og `height`:** Setter den innvendige bredden og høyden på et element.
* **`padding`:** Den innvendige avstanden fra innholdet ut til kanten/rammen på elementet.



---

## Oppgave 1: Enkel knappe-styling (Svært enkel)

**Mål:** Bruke `padding` og `background-color` for å skape en fin knapp.

**Nivå:** Nybegynner

### Instruksjoner

1. Opprett et HTML-dokument og legg til en lenke/knapp: `<a href="#" class="min-knapp">Klikk her</a>`.
2. Lag en CSS-regel for klassen `.min-knapp`:
* Sett bakgrunnsfargen til en valgfri farge (f.eks. `#3498db`).
* Sett tekstfargen til hvit (`#ffffff`).
* Legg til **12px padding oppe/nede** og **24px padding til høyre/venstre**.
* *Tips:* Husk å sette `display: inline-block;` på lenken slik at `width`, `height` og `padding` fungerer optimalt.



---

## Oppgave 2: Fast størrelse på et bildekort (Enkel)

**Mål:** Kombinere fast `width`, `height` og `padding` for å ramme inn innhold.

**Nivå:** Lett

### Instruksjoner

1. Lag et `<div>`-element i HTML med klassen `profil-kort`.
2. Inni kortet legger du til en overskrift (`<h2>`) og et kort avsnitt (`<p>`).
3. Lag en CSS-regel for `.profil-kort`:
* Sett bredden (`width`) til **300px**.
* Sett høyden (`height`) til **200px**.
* Sett bakgrunnsfargen til lys grå (`#f4f4f4`).
* Legg til **20px padding** på alle sider.
* Legg til en tynn ramme (`border: 1px solid #ccc`).



---

## Oppgave 3: Hero-seksjon med prosent-bredde og innvendig luft (Middels)

**Mål:** Bruke prosentbasert `width` sammen med `padding` for å lage et responserivt element.

**Nivå:** Middels

### Instruksjoner

1. Lag en `<header>` eller `<div class="hero">` som inneholder en hovedoverskrift (`<h1>`) og en undertekst (`<p>`).
2. I CSS skal du style `.hero`:
* Sett `width` til **80%** (slik at den tilpasser seg skjermbredden).
* Sett `min-height` til **250px** (minimumshøyde).
* Sett `padding` til **40px 20px** (40px oppe/nede, 20px på sidene).
* Midtstill elementet på siden ved å bruke `margin: 0 auto;`.
* Velg en mørk bakgrunnsfarge og lys tekstfarge.



---

## Oppgave 4: Boksmodell-fellen – `box-sizing: border-box` (Litt krevende)

**Mål:** Forstå hvordan `padding` påvirker den totale bredden på elementer, og hvordan du løser det.

**Nivå:** Viderekommende

### Beskrivelse

Når du setter `width: 300px` og legger til `padding: 20px`, vil elementet i utgangspunktet bli totalt **340px** bredt i nettleseren. Dette kan ødelegge oppsettet ditt!

### Instruksjoner

1. Lag to bokser i HTML med klassene `boks-1` og `boks-2`. Legg til litt tekst i begge.
2. I CSS gir du **begge** boksene:
* `width: 300px;`
* `padding: 30px;`
* Hver sin bakgrunnsfarge og en tynn kantlinje (`border`).


3. På `boks-2` legger du i tillegg til følgende linje:
```css
box-sizing: border-box;

```


4. Åpne siden i nettleseren eller bruk inspeksjonsverktøyet (F12).
* **Spørsmål:** Hvorfor er `boks-2` smalere enn `boks-1` selv om begge har `width: 300px`?



---

## Oppgave 5: Komplett infokort med alle elementer (Sammensatt)

**Mål:** Kombinere HTML-struktur, tekstformatering, klasser, `width`, `height`, `padding` og `box-sizing` i et komplett komponent design.

**Nivå:** Utfordrende / Sammensatt

```
+------------------------------------------+
|  Overtskrift (h3)                        |
|  --------------------------------------- |
|  Innholdstekst og detaljer om emnet.     |
|                                          |
|  [ Knapp ]                               |
+------------------------------------------+

```

### Instruksjoner

1. Lag en HTML-struktur for et produktkort eller en nyhetsartikkel:
* En ytre `div` med klassen `kort-container`.
* En overskrift `<h3>`.
* Et avsnitt `<p>` med brødtekst.
* En lenke med klassen `les-mer-knapp`.


2. Style elementene i CSS etter følgende spesifikasjoner:
* **Nullstill bokser:** Legg til `* { box-sizing: border-box; }` øverst i CSS-filen din.
* **`kort-container`:**
* `width: 100%;`
* `max-width: 400px;` (Gjør at kortet ikke blir bredere enn 400px, men krymper på små skjermer).
* `padding: 25px;`
* `background-color: #ffffff;`
* `border: 1px solid #e0e0e0;`
* `border-radius: 8px;` (valgfritt, for avrundede hjørner).


* **Tekst og knapp:**
* Endre skrifttype (`font-family: Arial, sans-serif;`).
* Gi knappen passende `padding` (f.eks. `8px 16px`), bakgrunnsfarge og fjern understreking (`text-decoration: none;`).






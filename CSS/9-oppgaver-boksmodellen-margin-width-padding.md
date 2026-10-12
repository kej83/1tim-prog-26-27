## Oppgave 1: Luft inni og utenfor boksen

### STEG 1: Lag filen og innholdet

Lag `oppgave1.html`. Bruk vanlig HTML-struktur med `<style>` i `<head>`. Legg dette i `<body>`:

```html
<h1>En viktig beskjed</h1>
<div class="beskjed">
    <h2>Husk!</h2>
    <p>Lagre filen før du oppdaterer nettleseren.</p>
</div>
```

### STEG 2: Gi boksen størrelse og farge

Lag en CSS-regel for `.beskjed`. Sett disse verdiene:

- `width: 240px;`
- `padding: 0px;`
- `margin: 0px;`
- `background-color: lightyellow;`
- `border: 2px solid black;`

Lagre filen og åpne den i nettleseren.

### STEG 3: Lag luft inni boksen

Endre bare `padding` til **20px**. Lagre og oppdater nettleseren. Se at det blir mer luft mellom teksten og rammen.

### STEG 4: Lag luft utenfor boksen

Legg til `margin-left: 40px;`. Behold padding på **20px**. Lagre og oppdater. Se at hele boksen flyttes mot høyre.

### STEG 5: Endre overskriften

Gi `h1` mørkeblå tekst med `color: navy;`. Behold boksens bredde på **240px**.

---

## Oppgave 2: Få boksen til å beholde bredden

### STEG 1: Lag filen og innholdet

Lag `oppgave2.html` i samme mappe som oppgave 1. Legg dette i `<body>`:

```html
<h1>En boks med faste mål</h1>
<div class="regneboks">
    <p>Mer padding gir mindre plass til teksten
       hvis hele boksen skal beholde bredden.</p>
</div>
```

### STEG 2: Gi boksen disse stilene

Lag en CSS-regel for `.regneboks`:

- `width: 180px;`
- `padding: 15px;`
- `border: 3px solid darkgreen;`
- `margin-left: 20px;`
- `margin-right: 30px;`
- `background-color: lightgreen;`

Lagre og åpne filen i nettleseren. Ikke bruk `box-sizing: border-box` i denne oppgaven.

### STEG 3: Regn ut bredden

Regn ut bredden med ramme: **180 + 15 + 15 + 3 + 3**.

Regn også med sidemargene: Legg til **20 + 30**. Margin ligger utenfor rammen.

### STEG 4: Øk padding

Endre `padding` til **25px**. Behold `width: 180px;`. Lagre og oppdater. Se at boksen blir bredere.

### STEG 5: Rett innholdsbredden

Boksen skal igjen være **216px bred med ramme**. Behold padding på **25px** og rammen på **3px**.

Regn **216 - 25 - 25 - 3 - 3**. Bruk svaret som ny `width` i px. Lagre og oppdater. Behold begge sidemargene.

---

## Oppgave 3: Rett kortet som er for bredt

### STEG 1: Lag filen og kopier HTML

Lag `oppgave3.html` i samme mappe. Legg dette i `<body>`:

```html
<h1>Spillkveld</h1>
<div class="omrade">
    <div class="kort">
        <h2>Ta med et spill!</h2>
        <p>Vi spiller sammen etter skolen.</p>
    </div>
</div>
```

### STEG 2: Kopier CSS og se feilen

Legg dette i `<style>`. Lagre og åpne siden. Det blå kortet stikker utenfor det grå området.

```css
.omrade {
    width: 400px;
    background-color: lightgray;
}
.kort {
    width: 360px;
    padding: 30px;
    border: 4px solid navy;
    margin-left: 40px;
    margin-right: 40px;
    background-color: lightblue;
}
```

### STEG 3: Rett sidemargene

Endre `margin-left` og `margin-right` på `.kort` til **20px** hver.

### STEG 4: Rett bredden

Kortet skal være **360px bredt med ramme**. Behold padding på **30px** og rammen på **4px**.

Regn **360 - 30 - 30 - 4 - 4**. Bruk svaret som ny `width` på `.kort`. Ikke bruk `box-sizing: border-box`.

### STEG 5: Kontroller resultatet

Gi `h2` mørkeblå tekst. Lagre og oppdater. Kortet skal nå passe i det grå området, med **20px luft på hver side**.

---

## Oppgave 4: Lag et bildegalleri

### STEG 1: Lag filen og tre bilder

Lag `oppgave4.html` i samme mappe. Legg dette i `<body>`:

```html
<h1>Mitt bildegalleri</h1>
<p>Tre bilder med ramme og luft rundt.</p>
<img src="https://picsum.photos/seed/en/240/180"
     alt="Første motiv">
<img src="https://picsum.photos/seed/to/240/180"
     alt="Andre motiv">
<img src="https://picsum.photos/seed/tre/240/180"
     alt="Tredje motiv">
```

### STEG 2: Gi alle bildene samme stil

Lag en CSS-regel for `img`:

- `width: 120px;` og `height: 90px;`
- `padding: 10px;`
- `margin: 12px;`
- `border: 3px dotted blue;`
- `background-color: lightyellow;`

Lagre og åpne siden i nettleseren.

### STEG 3: Øk avstanden mellom bildene

Endre bare `margin` til **24px**. Lagre og oppdater. Se at det blir større avstand utenfor bilderammene.

### STEG 4: Øk luften inni bilderammene

Sett `margin` tilbake til **12px**. Endre `padding` til **20px**. Lagre og oppdater. Se at den gule flaten blir større. Sett deretter padding tilbake til **10px**.

### STEG 5: Gjør det første bildet til en lenke

Legg `<a href="oppgave1.html">` rett før det første bildet. Legg `</a>` rett etter det samme bildet.

Lagre og oppdater. Klikk på bildet. Det skal åpne oppgave 1.

### STEG 6: Legg til en liste og prøv vindusstørrelsen

Lag en nummerert liste (`ol`) under bildene med tre listepunkter (`li`): «Første motiv», «Andre motiv» og «Tredje motiv».

Gjør nettleservinduet smalere og bredere. Se hvordan bildene flytter seg til en ny linje når det blir lite plass.

---

## Oppgave 5: Lag en invitasjon

### STEG 1: Lag filen og samle innholdet

Lag `oppgave5.html` i samme mappe. Lag et `div` med `class="invitasjon"` i `<body>`. Alt innholdet fra steg 2 og 3 skal ligge inni denne boksen.

### STEG 2: Skriv invitasjonen

Legg inn følgende HTML-elementer:

- `h1`: «Velkommen til aktivitetsdagen».
- `p`: En kort tekst om hvor og når dere møtes.
- `h2`: «Ta med».
- `ul`: Tre ting deltakerne skal ta med. Bruk `li` for hvert punkt.
- `img`: Bruk en bildeadresse fra oppgave 4. Legg til beskrivende `alt`-tekst.

### STEG 3: Lag programmet og en lenke

Legg til `h2` med teksten «Program».

Lag en tabell med kolonnene «Tid» og «Aktivitet». Bruk `th` i overskriftsraden og `td` i to rader med aktiviteter.

Legg til en lenke til `oppgave4.html` med teksten «Se bildegalleriet».

### STEG 4: Gi invitasjonsboksen stil

Lag en CSS-regel for `.invitasjon`:

- `width: 70%;`
- `padding: 20px;`
- `margin: 20px auto;`
- `border: 3px solid navy;`
- `background-color: lightyellow;`

`auto` gir like sidemarger og sentrerer boksen når det er plass.

### STEG 5: Gi innholdet stil

- `h1`: Sett `color: navy;`.
- `h2`: Sett `padding: 8px;` og `margin-top: 20px;`.
- `img`: Sett `width: 160px;`, `height: 120px;`, `padding: 8px;`, `margin: 10px;` og `border: 2px solid navy;`.
- `ul`: Sett `padding: 30px;`, `margin: 15px;` og `background-color: lightblue;`.
- `th` og `td`: Sett `padding: 8px;` og `border: 1px solid black;`.
- `th`: Sett `background-color: navy;` og `color: white;`.

### STEG 6: Kontroller siden

Lagre og åpne siden. Kontroller at bildet vises og at lenken åpner galleriet. Gjør nettleservinduet smalere og bredere. Se at invitasjonsboksen endrer bredde og ligger midt på siden.

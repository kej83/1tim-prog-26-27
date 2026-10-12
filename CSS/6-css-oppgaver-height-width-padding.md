# CSS-oppgaver: height, width og padding

Fem oppgaver med stigende vanskegrad, fra en enkel overskrift til en liten nettside.

## Før du begynner

Du har brukt overskrifter (`h1`, `h2`), avsnitt (`p`), bilder (`img`), lister (`ul`, `ol`, `li`), tabeller (`table`, `tr`, `th`, `td`) og lenker (`a`). I CSS har du brukt tekstfarge, bakgrunnsfarge og rammer. Nå skal du kombinere dette med **bredde, høyde og innvendig luft**.

Lag en mappe som heter `storrelsesoppgaver`. Lag én HTML-fil per oppgave i denne mappen. Skriv CSS i `<style>` i `<head>`. Lagre og oppdater nettleseren etter hver endring.

### Startmal

Bruk denne malen til hver oppgave. Bytt sidetittel i `<title>` og innhold i `<body>`. Skriv nye CSS-regler for hver oppgave.

```html
<!DOCTYPE html>
<html lang="nb">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Oppgave 1</title>
    <style>
        /* Skriv CSS her. */
    </style>
</head>
<body>
    <h1>Hei, CSS!</h1>
    <p>Jeg lærer å endre størrelsen på elementer.</p>
</body>
</html>
```

### Husk

- `width` er bredde. `height` er høyde. `px` betyr piksler.
- `width: 50%;` gir halvparten av bredden til elementet som ligger rundt. For en overskrift rett i `<body>` er det den tilgjengelige bredden i `<body>`.
- `padding` er luft mellom innholdet og rammen. `padding: 20px;` gir luft på alle fire sider. `padding-left` og `padding-top` gjelder én side hver.
- Med vanlige standardinnstillinger gjelder `width` og `height` innholdet. Padding og ramme kommer i tillegg. La tekstbokser få høyde automatisk hvis oppgaven ikke ber om en bestemt høyde.

---

## Oppgave 1: En overskrift med størrelse

**Nivå: Svært enkelt.** Lagre som `oppgave1.html`.

Bruk startmalen med teksten «Hei, CSS!» og avsnittet under.

### Gjør dette

1. Gi `h1` en lyseblå bakgrunn med `background-color: lightblue;`.
2. Gi `h1` en bredde på **200px** og en høyde på **80px**.
3. Lagre og åpne filen i nettleseren. Den lyseblå bakgrunnen gjør størrelsen synlig.
4. Endre bare bredden til **300px**. Se hva som skjer, og sett den tilbake til **200px**.
5. Endre bare høyden til **120px**. Se hva som skjer, og sett den tilbake til **80px**.

### Hjelp

Skriv en regel for `h1` inne i `<style>`. Start slik, og legg til egenskapene for bredde og høyde:

```css
h1 {
    background-color: lightblue;
}
```

### Sjekk og forklar

- Overskriften har lyseblå bakgrunn, `width: 200px;` og `height: 80px;`.
- Avsnittet er fortsatt synlig under overskriften.
- Hva endret seg da du endret `width`? Hva endret seg da du endret `height`?

**Svar:** ___________________________________________________________

____________________________________________________________________

---

## Oppgave 2: Luft inni en tekstboks

**Nivå: Enkelt.** Lagre som `oppgave2.html`.

Bruk startmalen. Bytt overskriften til «Beskjed» og avsnittet til «Husk å lagre filen før du oppdaterer nettleseren.»

### Gjør dette

1. Gi `p` en bredde på **250px** og en lysegul bakgrunn (`lightyellow`).
2. Gi `p` en heltrukket, mørkeblå ramme (`navy`) med tykkelse **2px**.
3. Sett `padding` på `p` til **0px**. Se hvor nær teksten ligger rammen.
4. Endre `padding` til **20px**. Behold bredden på **250px** og rammen på **2px**.
5. Gi overskriften en valgfri tekstfarge. La avsnittets høyde tilpasse seg teksten automatisk.

### Hjelp

Du trenger egenskapene `width`, `background-color`, `border-style`, `border-width`, `border-color` og `padding`. Rammen kan også skrives slik:

```css
border: 2px solid navy;
```

### Sjekk og forklar

- Teksten har luft til rammen på alle fire sider.
- CSS-bredden er fortsatt **250px**, selv om boksen tar mer plass med padding.
- Hva er forskjellen på å øke `width` og å øke `padding`?
- Hvor bred er boksen fra ytterkant til ytterkant av rammen til slutt? Regn **250 + 20 + 20 + 2 + 2**.

**Svar:** ___________________________________________________________

____________________________________________________________________

---

## Oppgave 3: Bilde og hobbyliste

**Nivå: Middels.** Lagre som `oppgave3.html`.

Bruk startmalen, men skriv innholdet i `<body>` selv. Lag en hovedoverskrift, et kort avsnitt om en hobby, et bilde og en underoverskrift med en punktliste over tre ting du trenger til hobbyen.

### Gjør dette

1. Bruk `h1`, `p`, `img`, `h2`, `ul` og `li` til innholdet. Bildet skal ha en beskrivende `alt`-tekst.
2. Gi bildet en bredde på **200px** og en høyde på **150px** med CSS.
3. Gi bildet en heltrukket ramme med tykkelse **2px** og valgfri farge.
4. Gi bildet **25px padding på venstre side** og **15px padding på toppen**. La høyre side og bunnen være uten padding.
5. Gi hele punktlisten (`ul`) en bredde på **250px**, **30px padding på alle sider** og en lys bakgrunnsfarge.
6. Gi `h2` en tekstfarge som passer til siden.

### Hjelp

Du kan bruke dette bildet. Det har samme forhold mellom bredde og høyde som størrelsen du skal bruke:

```html
<img src="https://picsum.photos/400/300"
     alt="Et tilfeldig bilde til hobbylisten">
```

Bruk `padding-left` og `padding-top` på bildet. Bruk `padding` på listen. Skriv størrelsen i CSS; ikke legg `width`- eller `height`-attributter på bildet i HTML.

### Sjekk og forklar

- Listen viser tre punkter, og bildet vises med `width: 200px;` og `height: 150px;`.
- Luften innenfor bilderammen er størst på venstre side. Det er også luft på toppen.
- Hvorfor bruker du `padding-left` på bildet, men `padding` på listen?

**Svar:** ___________________________________________________________

____________________________________________________________________

---

## Oppgave 4: Aktivitetsplan med prosentbredde

**Nivå: Litt mer krevende.** Lagre som `oppgave4.html`.

Bruk startmalen. Skriv selv HTML til en aktivitetsplan med en hovedoverskrift, en kort forklaring og en tabell.

### Gjør dette

1. Tabellen skal ha **to kolonner**: «Dag» og «Aktivitet». Bruk `th` til overskriftene og `td` til innholdet. Legg inn **tre rader med aktiviteter**, i tillegg til overskriftsraden.
2. Gi `h1` en bredde på **80%**, en lys bakgrunn og **10px padding**.
3. Gi tabellen en bredde på **70%** og en heltrukket ramme på **2px**.
4. Gi både `th` og `td` **12px padding** og en heltrukket ramme på **1px**.
5. Gi `th` en mørk bakgrunn og lys tekst. Velg farger som er lette å lese.
6. Prøv et smalt og et bredt nettleservindu. Se hvordan prosentbreddene endrer seg.
7. Endre padding i cellene til **4px**, og sammenlign. Sett den deretter tilbake til **12px**.

### Hjelp

Du har brukt en felles regel for `h1, h2` tidligere. På samme måte kan `th, td` få en felles regel for padding og ramme. Lag deretter en egen regel for fargene til `th`.

### Sjekk og forklar

- Tabellen har fire rader totalt og to kolonner.
- Alle cellene har luft mellom teksten og rammen.
- Overskriften og tabellen endrer bredde når du endrer bredden på vinduet.
- Hvordan oppfører `width: 70%;` seg sammenlignet med `width: 250px;`?

**Svar:** ___________________________________________________________

____________________________________________________________________

---

## Oppgave 5: Lag en liten infoside

**Nivå: Mer sammensatt.** Lagre som `oppgave5.html`.

Lag en infoside om en hobby, et spill eller en aktivitet. Bruk startmalen, og skriv HTML og CSS selv. Du kan se på tidligere eksempler når du trenger hjelp.

### Innhold i HTML

- Én hovedoverskrift, minst to underoverskrifter og to korte avsnitt.
- Ett bilde med beskrivende `alt`-tekst. Bruk gjerne bildeadressen fra oppgave 3.
- En punktliste med tre ting man trenger, og en nummerert liste med tre trinn for å komme i gang.
- En tabell med to kolonner og minst tre rader med innhold, i tillegg til en overskriftsrad.
- En lenke til en relevant nettside, og en lenke tilbake til `oppgave1.html`. Gi lenkene tydelig lenketekst.

### Krav til CSS

1. `h1`: **80% bredde**, **15px padding**, bakgrunnsfarge og tekstfarge.
2. `h2`: **50px høyde**, **10px padding** og en lys bakgrunnsfarge. Bruk korte overskrifter som får plass.
3. `p`: **300px bredde**, **15px padding** og en heltrukket ramme på **2px**. La høyden tilpasse seg teksten.
4. `img`: **200px bredde**, **150px høyde**, **10px padding** og en ramme med valgfri stil og farge.
5. `ul` og `ol`: **250px bredde** og **30px padding**.
6. `table`: **70% bredde**. `th` og `td`: **8px padding** og synlig ramme. Gi `th` egen bakgrunnsfarge og tekstfarge.

### Sjekk og forklar

- Alt innholdet er med, begge lenkene virker, og siden er lett å lese.
- Du har brukt `width` i både `px` og `%`, samt `height` og `padding`.
- Prøv siden i et smalt og et bredt vindu. Sjekk at tekst ikke stikker utenfor rammene.
- Velg ett element: Forklar hva `width`, eventuell `height` og `padding` gjør med akkurat dette elementet.

**Svar:** ___________________________________________________________

____________________________________________________________________

____________________________________________________________________

# CSS-oppgaver: Rammer og farger

I disse oppgavene er HTML-koden ferdig skrevet. Din jobb er å kopiere HTML-koden inn i en ny `.html`-fil og legge til CSS i `<style>`-feltet øverst for å løse oppgavene.

## Oppgave 1: "Min Profilside"

I denne oppgaven skal du bruke rammer og farger til å pynte på en enkel profilside.

### HTML-kode (Startpunkt)

Kopier koden under inn i en fil som heter `oppgave1.html`:

```html
<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Min Profilside</title>
    <style>
        /* Skriv din CSS her! */
        
    </style>
</head>
<body>
    <h1>Velkommen til min profil</h1>
    
    <h2>Om meg</h2>
    <p>Jeg lærer HTML og CSS!</p>
    
    <img src="https://picsum.photos/200" alt="Profilbilde">
</body>
</html>
```

### Hva du skal gjøre (CSS):

1. Gi `h1` en bakgrunnsfarge (`background-color: lightgreen`), tekstfarge (`color: darkgreen`) og en stiplet ramme (`border-style: dashed; border-color: darkgreen`).

2. Gi `h2` en ramme som kun er på venstre side (`border-left-style: solid`), med en tykkelse på `5px` (`border-left-width: 5px`).

3. Gi bildet (`img`) en prikkete ramme (`border-style: dotted`), en rammetykkelse på `8px` (`border-width: 8px`) og en valgfri rammefarge (`border-color`).

---

## Oppgave 2: "Handleliste"

Her skal du bruke det du har lært om rammer på lister (`ul` og `li`).

### HTML-kode (Startpunkt)

Kopier koden under inn i en fil som heter `oppgave2.html`:

```html
<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Handleliste</title>
    <style>
        /* Skriv din CSS her! */
        
    </style>
</head>
<body>
    <h1>Min Handleliste</h1>

    <h2>Varer å kjøpe:</h2>
    <ul>
        <li>Melk</li>
        <li>Brød</li>
        <li>Ost</li>
        <li>Epler</li>
    </ul>
</body>
</html>
```

### Hva du skal gjøre (CSS):

1. Gi `h1` en lyseblå bakgrunnsfarge (`background-color: lightblue`), mørkeblå tekst (`color: navy`), og en heltrukket ramme (`border-style: solid; border-color: navy`).

2. Gi hele listen (`ul`) en ramme:
   * Heltrukket ramme (`border-style: solid`)
   * Tykkelse på `2px` (`border-width: 2px`)
   * Rammefarge etter eget ønske (`border-color`)

3. Gi hvert enkelt punkt i listen (`li`) en stiplet ramme *kun på undersiden*:
   * `border-bottom-style: dashed;`
   * `border-bottom-color: gray;`

---

## Oppgave 3: "Fotballtabell"

I denne oppgaven skal du style en hel tabell med rammestiler og bakgrunnsfarger.

### HTML-kode (Startpunkt)

Kopier koden under inn i en fil som heter `oppgave3.html`:

```html
<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fotballtabell</title>
    <style>
        /* Skriv din CSS her! */
        
    </style>
</head>
<body>
    <h1>Eliteserien - Topp 3</h1>

    <table>
        <tr>
            <th>Lag</th>
            <th>Poeng</th>
        </tr>
        <tr>
            <td>Bodø/Glimt</td>
            <td>45</td>
        </tr>
        <tr>
            <td>Brann</td>
            <td>42</td>
        </tr>
        <tr>
            <td>Viking</td>
            <td>40</td>
        </tr>
    </table>
</body>
</html>
```

### Hva du skal gjøre (CSS):

1. Gi hele tabellen (`table`):
   * Bakgrunnsfarge: `lightyellow`
   * Heltrukket ramme (`border-style: solid`) med tykkelse `3px`

2. Gi overskriftene i tabellen (`th`):
   * Bakgrunnsfarge: `orange`
   * En tykk venstreramme (`border-left-style: solid; border-left-width: 8px; border-left-color: darkorange;`)

3. Gi selve datacellene (`td`):
   * En prikkete ramme rundt det hele (`border-style: dotted; border-color: gray;`)

---

## Oppgave 4: Finaleoppgave – "Meny og Tabell"

I denne oppgaven får du **ingen CSS-koder** oppgitt! Du må selv huske eller slå opp hvilke CSS-egenskaper og verdier du skal bruke for å oppfylle kravene.

### HTML-kode (Startpunkt)

Kopier koden under inn i en fil som heter `oppgave4.html`:

```html
<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kafé Meny</title>
    <style>
        /* Skriv all CSS her helt selv! */
        
    </style>
</head>
<body>

    <h1>Velkommen til Kafé Koden</h1>

    <h2>Dagens Spesialiteter</h2>
    <ul>
        <li>Kaffe Latte</li>
        <li>Kanelbolle</li>
        <li>Gulrotkake</li>
    </ul>

    <h2>Prisliste</h2>
    <table>
        <tr>
            <th>Vare</th>
            <th>Pris</th>
        </tr>
        <tr>
            <td>Kaffe Latte</td>
            <td>45 kr</td>
        </tr>
        <tr>
            <td>Kanelbolle</td>
            <td>35 kr</td>
        </tr>
        <tr>
            <td>Gulrotkake</td>
            <td>55 kr</td>
        </tr>
    </table>

    <br>
    <img src="https://picsum.photos/300/150" alt="Kafebilde">

</body>
</html>
```

### Kravene du skal løse i CSS:

1. **Hovedoverskriften (`h1`):**
   * Mørkerød bakgrunnsfarge
   * Hvit tekstfarge
   * En tykk, heltrukket ramme (5px) med rødbrun farge

2. **Underoverskriftene (`h2`):**
   * En tykk ramme som kun er på **venstre side** (10px tykkelse, heltrukket stil, mørkerød farge)

3. **Punktlisten (`ul`):**
   * Hele listen skal ha en stiplet ramme (2px tykk) rundt seg med fargen grå
   * Bakgrunnsfargen på hele listen skal være lysegul

4. **Listeleddene (`li`):**
   * Hvert enkelt punkt i listen skal ha en prikkete ramme som **kun er i bunnen**

5. **Tabellen (`table`):**
   * Tabellen skal ha en heltrukket rammestil rundt seg (3px tykk)
   * Bakgrunnsfargen skal være hvit

6. **Tabelloverskriftene (`th`):**
   * Bakgrunnsfargen skal være mørkerød
   * Tekstfargen skal være hvit

7. **Tabellcellene (`td`):**
   * Skal ha en heltrukket grå ramme (1px tykk) rundt hver enkelt celle

8. **Bildet (`img`):**
   * Bildet skal ha en stiplet ramme på 6px tykkelse rundt seg, med en mørkerød farge
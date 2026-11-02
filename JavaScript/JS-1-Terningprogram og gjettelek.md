# Programmeringshefte: Rollespillterningen (D20)

I rollespill som *Dungeons & Dragons* bruker man en terning med 20 sider, en D20. Får du 20, er det et **kritisk treff**. Får du 1, er det en **kritisk bom**. Vi lager en slik terning på nettsiden.

### Steg 1: Lag nettsiden

Lag en ny fil som heter `terning.html`, og skriv av denne koden:

```html
<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rollespillterning</title>
</head>
<body>
    <h1>Rollespillterningen (D20)</h1>
    <button onclick="kastD20()">Kast terningen</button>
    <p id="txtUt"></p>

    <script>

    </script>
</body>
</html>
```

**Slik virker det:**

- `onclick="kastD20()"` betyr at funksjonen `kastD20` skal kjøre når noen trykker på knappen.
- `id="txtUt"` gir avsnittet et navn. Da kan JavaScript skrive tekst i det.
- All JavaScript-koden skal stå mellom `<script>` og `</script>`.

**Test:** Åpne filen i nettleseren. Du skal se overskriften og knappen. Knappen gjør ingenting ennå.

### Steg 2: Kast terningen

Skriv denne funksjonen mellom `<script>` og `</script>`:

```js
function kastD20() {
    let kast = Math.ceil(Math.random() * 20);
    txtUt.textContent = `Du fikk ${kast}.`;
}
```

**Slik virker det:**

- `Math.random()` gir et tilfeldig desimaltall fra 0 til litt under 1, for eksempel 0,374.
- `* 20` gjør det til et tall fra 0 til litt under 20, for eksempel 7,48.
- `Math.ceil()` runder **opp** til nærmeste heltall. Da får vi et tall fra 1 til 20.
- `txtUt.textContent = ...` skriver tekst i avsnittet med `id="txtUt"`.
- Teksten står mellom backticks (`` ` ``). Da kan vi sette inn variabler med `${kast}`.

**Test:** Trykk på knappen mange ganger. Du skal få tall mellom 1 og 20.

### Steg 3: Kritisk treff

Nå skal programmet juble når du får 20. Bytt ut linjen med `txtUt.textContent` med en `if`-setning, slik at funksjonen ser slik ut:

```js
function kastD20() {
    let kast = Math.ceil(Math.random() * 20);

    if (kast == 20) {
        txtUt.textContent = "KRITISK TREFF! Du fikk 20!";
    } else {
        txtUt.textContent = `Du fikk ${kast}.`;
    }
}
```

**Slik virker det:**

- `if (kast == 20)` sjekker om kastet ble 20. Hvis ja, kjøres koden i den første klammeparentesen `{ }`.
- `else` betyr «ellers». Koden der kjøres hvis kastet **ikke** ble 20.
- Husk: `==` **sammenligner** to verdier. Ett likhetstegn `=` **gir** en variabel en verdi.

### Steg 4: Kritisk bom

Vi legger til en sjekk for 1 med `else if` («ellers hvis»). Hele funksjonen ser nå slik ut:

```js
function kastD20() {
    let kast = Math.ceil(Math.random() * 20);

    if (kast == 20) {
        txtUt.textContent = "KRITISK TREFF! Du fikk 20!";
    } else if (kast == 1) {
        txtUt.textContent = "Kritisk bom ... Du fikk 1.";
    } else {
        txtUt.textContent = `Du fikk ${kast}.`;
    }
}
```

**Test:** Hvor mange ganger må du trykke før du får 20? Sammenlign med sidemannen.

**Lurt triks:** Det kan ta lang tid å få 20 ved et uhell. For å teste kan du midlertidig skrive `let kast = 20;` i stedet for den tilfeldige linjen. Husk å sette den tilbake etterpå!

## Del 1: Gjør endringer

Nå skal du endre programmet selv. Test etter hver endring.

### Endring 1: Gjør siden til din egen

Endre teksten i `<h1>`, i `<title>` og på knappen. Kall gjerne terningen noe eget, for eksempel «Dragens terning».

### Endring 2: Nye meldinger

Skriv om de tre meldingene i `if`-setningen. Den vanlige meldingen skal også si om kastet ble høyt eller lavt, for eksempel `Du fikk en ${kast}-er. Helten svinger sverdet ...`

### Endring 3: Bra kast

Legg til en ny `else if` som skriver «Bra kast!» når kastet er 15 eller mer. Her er koden du trenger:

```js
} else if (kast >= 15) {
    txtUt.textContent = `Bra kast! Du fikk ${kast}.`;
```

**Prøv deg fram:** Sett den nye sjekken **først** i `if`-setningen og få et kast på 20 (bruk trikset fra steg 4). Hva skjer? Flytt den så til riktig plass.

> **Hvorfor?** Datamaskinen sjekker betingelsene ovenfra og ned, og stopper ved den første som er sann. 20 er også større enn 15!

### Endring 4: Lag en D12

Gjør terningen om til en 12-sidet terning. Finn **alle** stedene i koden som må endres. Husk også overskriften og grensen for «bra kast».

**Spørsmål:** Hva skjer hvis du endrer `Math.random() * 20` til `* 12`, men glemmer `kast == 20`?

### Endring 5: Én variabel for antall sider

Det er tungvint å endre tallet mange steder. Lag en variabel helt øverst i `<script>`, **over** funksjonen:

```js
let sider = 20;
```

Bytt så ut tallet 20 inne i funksjonen med `sider`, både i `Math.random() * sider` og i `kast == sider`. Bruk `${sider}` i teksten om kritisk treff. Sett grensen for «bra kast» tilbake til 15.

**Test:** Endre `sider` til 6, 12 og 100. Virker terningen hver gang?

## Del 1: Utvid programmet

Nå skal du bygge videre på terningen. Du får hint, men må skrive det meste av koden selv.

### Utvidelse 1: Kast med fordel

I rollespill kan man noen ganger kaste **med fordel**. Da kaster man to terninger og bruker den høyeste.

Lag en ny knapp under den første:

```html
<button onclick="kastMedFordel()">Kast med fordel</button>
```

Lag så en ny funksjon. Begynnelsen får du her:

```js
function kastMedFordel() {
    let kast1 = Math.ceil(Math.random() * sider);
    let kast2 = Math.ceil(Math.random() * sider);

    // Skriv ut hva begge terningene viste,
    // og hvilket av kastene som var høyest.
}
```

Eksempel på utskrift: `Du fikk 7 og 15. Du bruker 15.`

**Hint:** Bruk `if (kast1 > kast2)` for å finne det høyeste kastet. Lagre det i en ny variabel, for eksempel `let beste`.

### Utvidelse 2: To like

Hvis begge terningene viser det samme, skal programmet skrive `Hurra! To like!` i tillegg til tallene.

**Hint:** Sjekk `kast1 == kast2` i en egen `if`-setning. Du kan legge til tekst på slutten med `txtUt.textContent += " Hurra! To like!";`

### Utvidelse 3: Kast med ulempe

Lag en tredje knapp, «Kast med ulempe». Den skal også kaste to terninger, men bruke den **laveste**.

**Hint:** Du kan kopiere funksjonen fra utvidelse 1. Hva må du endre? Gi funksjonen et nytt navn!

### Utvidelse 4: Tell kastene

Programmet skal holde styr på hvor mange ganger du har kastet. Utskriften skal for eksempel bli `Kast nr. 5: Du fikk 12.`

**Hint:**

- Lag variabelen `let antallKast = 0;` øverst i `<script>`, ved siden av `sider`.
- Inne i hver funksjon øker du den med 1: `antallKast = antallKast + 1;`
- Bruk `${antallKast}` i teksten.

**Spørsmål:** Hvorfor må `antallKast` stå **utenfor** funksjonene? Prøv å flytte den inn i funksjonen og se hva som skjer.

### Bonus: Velg terning selv

La brukeren skrive inn hvor mange sider terningen skal ha.

**Hint:** Lag et inndatafelt `<input id="inpSider" type="number" value="20">`. Les det inn øverst i funksjonene med `sider = Number(inpSider.value);`

### Bonus: Statistikk

Tell hvor mange kritiske treff og kritiske bom du har fått, og skriv det ut under kastet. Bruk et nytt avsnitt, for eksempel `<p id="txtStatistikk"></p>`.


### Rollespillterningen, ferdig program

```html
<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dragens terning</title>
</head>
<body>
    <h1>Dragens terning</h1>
    <button onclick="kastD20()">Kast terningen</button>
    <button onclick="kastMedFordel()">Kast med fordel</button>
    <button onclick="kastMedUlempe()">Kast med ulempe</button>
    <p id="txtUt"></p>

    <script>
        let sider = 20;
        let antallKast = 0;

        function kastD20() {
            antallKast = antallKast + 1;
            let kast = Math.ceil(Math.random() * sider);

            if (kast == sider) {
                txtUt.textContent = `Kast nr. ${antallKast}: KRITISK TREFF! Du fikk ${sider}!`;
            } else if (kast == 1) {
                txtUt.textContent = `Kast nr. ${antallKast}: Kritisk bom ... Du fikk 1.`;
            } else if (kast >= 15) {
                txtUt.textContent = `Kast nr. ${antallKast}: Bra kast! Du fikk ${kast}.`;
            } else {
                txtUt.textContent = `Kast nr. ${antallKast}: Du fikk en ${kast}-er. Helten svinger sverdet ...`;
            }
        }

        function kastMedFordel() {
            antallKast = antallKast + 1;
            let kast1 = Math.ceil(Math.random() * sider);
            let kast2 = Math.ceil(Math.random() * sider);

            let beste;
            if (kast1 > kast2) {
                beste = kast1;
            } else {
                beste = kast2;
            }

            txtUt.textContent = `Kast nr. ${antallKast}: Du fikk ${kast1} og ${kast2}. Du bruker ${beste}.`;

            if (kast1 == kast2) {
                txtUt.textContent += " Hurra! To like!";
            }
        }

        function kastMedUlempe() {
            antallKast = antallKast + 1;
            let kast1 = Math.ceil(Math.random() * sider);
            let kast2 = Math.ceil(Math.random() * sider);

            let verste;
            if (kast1 < kast2) {
                verste = kast1;
            } else {
                verste = kast2;
            }

            txtUt.textContent = `Kast nr. ${antallKast}: Du fikk ${kast1} og ${kast2}. Du må bruke ${verste}.`;

            if (kast1 == kast2) {
                txtUt.textContent += " Hurra! To like!";
            }
        }
    </script>
</body>
</html>
```
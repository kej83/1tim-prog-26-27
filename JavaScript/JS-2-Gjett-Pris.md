# Gjett prisen

Datamaskinen finner på en hemmelig pris på et skateboard, mellom 1 og 1000 kr. Du gjetter, og programmet sier om du gjettet for høyt eller for lavt.

### Steg 1: Lag nettsiden

Lag en ny fil som heter `gjettprisen.html`, og skriv av denne koden:

```html
<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gjett prisen</title>
</head>
<body>
    <h1>Gjett prisen!</h1>
    <p>Hva koster skateboardet? Det koster mellom 1 og 1000 kr.</p>
    <input id="inpGjett" type="number" min="1" max="1000">
    <button onclick="sjekkGjett()">Gjett</button>
    <p id="txtUt"></p>

    <script>

    </script>
</body>
</html>
```

**Slik virker det:**

- `<input>` er et felt der brukeren kan skrive. `type="number"` betyr at feltet er laget for tall.
- `id="inpGjett"` gjør at JavaScript kan lese det brukeren har skrevet.

**Test:** Åpne filen i nettleseren. Du skal se overskriften, et tekstfelt og en knapp.

### Steg 2: Lag en hemmelig pris

Skriv denne koden mellom `<script>` og `</script>`:

```js
let pris = Math.ceil(Math.random() * 1000);

function sjekkGjett() {
    let gjett = Number(inpGjett.value);
    txtUt.textContent = `Du gjettet ${gjett} kr.`;
}
```

**Slik virker det:**

- `pris` blir et tilfeldig tall fra 1 til 1000, på samme måte som terningen i del 1.
- `pris` står **utenfor** funksjonen. Da lages prisen bare én gang, når siden lastes. Står den inni, får du ny pris hver gang du gjetter!
- `inpGjett.value` er det brukeren har skrevet i feltet. Det er alltid **tekst**.
- `Number()` gjør teksten om til et tall, slik at vi kan sammenligne det med prisen.

**Test:** Skriv et tall i feltet og trykk «Gjett». Programmet skal skrive tallet ditt.

### Steg 3: Sammenlign med prisen

Bytt ut linjen med `txtUt.textContent` med en `if`-setning, slik at funksjonen ser slik ut:

```js
function sjekkGjett() {
    let gjett = Number(inpGjett.value);

    if (gjett == pris) {
        txtUt.textContent = `Riktig! Skateboardet koster ${pris} kr.`;
    } else if (gjett < pris) {
        txtUt.textContent = "For lavt! Prøv en høyere pris.";
    } else {
        txtUt.textContent = "For høyt! Prøv en lavere pris.";
    }
}
```

**Slik virker det:**

- Først sjekker vi om gjettet er riktig, så om det er for lavt.
- Er det verken riktig eller for lavt, må det være for høyt. Derfor holder det med `else` til slutt.

### Steg 4: Test smart

Det er vanskelig å teste programmet når du ikke vet prisen. Legg til denne linjen rett under `let pris = ...`:

```js
console.log(pris);
```

Trykk F12 og åpne fanen *Console*. Der står den hemmelige prisen! Test at programmet svarer riktig på et for lavt, et for høyt og et riktig gjett. Ta bort linjen når du er ferdig.

**Spørsmål:** Hva er den beste strategien for å finne prisen raskt? Hvor mange gjett trenger du på det meste?

## Del 2: Gjør endringer

Nå skal du endre gjetteleken selv. Test etter hver endring.

### Endring 1: Ny vare og ny pris

Bytt skateboardet ut med noe annet, for eksempel en mobil som koster mellom 1 og 5000 kr. Finn **alle** stedene som må endres:

- teksten i `<h1>` og i avsnittet under
- `max` i `<input>`
- tallet i `Math.random() * 1000`
- meldingen når du gjetter riktig

### Endring 2: Vis gjettet i meldingen

Nå sier programmet bare «For lavt!». Endre meldingene så de tar med tallet du gjettet, for eksempel `350 kr er for lavt! Prøv en høyere pris.`

**Hint:** Bruk backticks og `${gjett}`, slik du gjorde med `${kast}` i del 1.

### Endring 3: Tøm feltet

Det er irriterende å måtte slette det gamle tallet før du gjetter på nytt. Legg til denne linjen **nederst** i funksjonen:

```js
inpGjett.value = "";
```

**Spørsmål:** Hva skjer hvis du setter linjen **øverst** i funksjonen i stedet? Prøv, og forklar hvorfor.

### Endring 4: Ugyldig gjett

Hvis noen gjetter 0, -5 eller 99999, skal programmet si fra. Legg til en ny sjekk **først** i `if`-setningen. Bruk ditt eget makstall fra endring 1:

```js
if (gjett < 1 || gjett > 5000) {
    txtUt.textContent = "Prisen er mellom 1 og 5000 kr!";
} else if (gjett == pris) {
```

**Slik virker det:** `||` betyr «eller». Betingelsen er sann hvis gjettet er under 1 **eller** over 5000.

**Husk:** Den gamle `if (gjett == pris)` må nå bli til `else if`.

## Del 2: Utvid programmet

Nå skal du gjøre gjetteleken til et ordentlig spill. Du får hint, men må skrive det meste av koden selv.

### Utvidelse 1: Tell forsøkene

Når du gjetter riktig, skal programmet si hvor mange forsøk du brukte, for eksempel `Riktig! Mobilen koster 2317 kr. Du brukte 9 forsøk.`

**Hint:**

- Lag variabelen `let antallForsok = 0;` ved siden av `pris`, utenfor funksjonen. (Vi skriver uten ø i variabelnavn.)
- Øk den med 1 hver gang noen gjetter: `antallForsok = antallForsok + 1;`
- Du gjorde nesten det samme med `antallKast` i del 1!

**Spørsmål:** Skal et ugyldig gjett (fra endring 4) telle som et forsøk? Bestem selv, og få programmet til å gjøre det du bestemte.

### Utvidelse 2: Begrens antall forsøk

Spilleren skal bare få 10 forsøk. Etter hvert gjett skal programmet vise hvor mange forsøk som er igjen. Er forsøkene brukt opp, skal det stå `Game over! Prisen var 2317 kr.`

**Hint:**

- Forsøk igjen kan du regne ut med `10 - antallForsok`.
- Sjekk om spillet er tapt med `if (antallForsok >= 10 && gjett != pris)`.
- `&&` betyr «og». Begge delene må være sanne. `!=` betyr «ikke lik».

### Utvidelse 3: Nytt spill

Lag en knapp «Nytt spill» som starter spillet på nytt uten at du må laste siden på nytt.

```html
<button onclick="nyttSpill()">Nytt spill</button>
```

**Hint:** Funksjonen `nyttSpill()` må gjøre tre ting:

1. Lage en ny tilfeldig pris: `pris = Math.ceil(Math.random() * 5000);`
2. Sette `antallForsok` tilbake til 0.
3. Skrive en melding i `txtUt`, for eksempel «Ny vare! Gjett prisen.»

**Legg merke til:** Vi skriver `pris = ...` uten `let`. Variabelen finnes allerede, vi gir den bare en ny verdi.

### Utvidelse 4: Varmt eller kaldt

Gi spilleren et ekstra hint når gjettet er nær prisen, for eksempel `For lavt, men du er veldig nær!`

**Hint:** `Math.abs(gjett - pris)` gir avstanden mellom gjettet og prisen, uten minustegn. Er avstanden 100 eller mindre, er du «varm».

### Bonus: Rekord

Programmet skal huske det laveste antallet forsøk du har brukt på å vinne, og vise det som `Rekord: 8 forsøk`.

**Hint:** Lag `let rekord = 999;` utenfor funksjonene. Når du vinner, sjekk om `antallForsok < rekord`. Da har du ny rekord!

### Bonus: Kombiner programmene

Lag et nytt spill der du gjetter hva en D20 kommer til å vise. Du har tre forsøk. Bruk det du har lært i begge delene av heftet.

## Huskeliste

Her er kodebitene du har brukt i heftet. Bruk dem når du lager egne programmer.

| Hva vil du gjøre? | Kode |
| --- | --- |
| Lage et tilfeldig tall fra 1 til N | `Math.ceil(Math.random() * N)` |
| Lese et tall fra et inndatafelt | `Number(inpGjett.value)` |
| Skrive tekst på siden | `txtUt.textContent = "Hei!";` |
| Legge til tekst på slutten | `txtUt.textContent += " Mer tekst";` |
| Sette en variabel inn i tekst | `` `Du fikk ${kast}.` `` (med backticks rundt teksten) |
| Øke en variabel med 1 | `antall = antall + 1;` |
| Tømme et inndatafelt | `inpGjett.value = "";` |
| Vise en verdi i Console (F12) | `console.log(pris);` |
| Finne avstanden mellom to tall | `Math.abs(a - b)` |

**Sammenligninger:**

| Tegn | Betyr | Eksempel |
| --- | --- | --- |
| `==` | lik | `kast == 20` |
| `!=` | ikke lik | `gjett != pris` |
| `<` | mindre enn | `gjett < pris` |
| `>` | større enn | `kast1 > kast2` |
| `<=` | mindre enn eller lik | `avstand <= 100` |
| `>=` | større enn eller lik | `kast >= 15` |

**Kombinere betingelser:** `&&` betyr «og» (begge må være sanne). `||` betyr «eller» (minst én må være sann).

**En `if`-setning med flere valg:**

```js
if (betingelse1) {
    // kjøres hvis betingelse1 er sann
} else if (betingelse2) {
    // kjøres hvis betingelse1 er usann og betingelse2 er sann
} else {
    // kjøres hvis ingen av dem er sanne
}
```

**Variabler utenfor eller inni funksjonen?** En variabel som skal **huske** noe mellom hvert trykk (pris, antall kast, rekord), må stå utenfor funksjonen. En variabel som bare brukes i étt trykk (kast, gjett), kan stå inni.

## Løsningsforslag


### Svar på spørsmålene

| Hvor | Svar |
| --- | --- |
| Del 1, steg 4 | I snitt må man kaste 20 ganger for å få 20, men det varierer mye. |
| Del 1, endring 3 | Står `kast >= 15` først, gir 20 «Bra kast!» og aldri kritisk treff. Den første sanne betingelsen vinner. |
| Del 1, endring 4 | Glemmer man `kast == 20`, kan kritisk treff aldri skje, fordi terningen aldri viser 20. |
| Del 1, utvidelse 4 | Står `antallKast` inni funksjonen, settes den til 0 ved hvert trykk. Da blir det alltid «Kast nr. 1». |
| Del 2, steg 4 | Beste strategi er å halvere: start på 500, så 250 eller 750 osv. Med 1–1000 trengs maks 10 gjett. |
| Del 2, endring 3 | Står linjen øverst, tømmes feltet før det leses. `Number("")` blir 0, så gjettet blir alltid 0. |

**Verdt å merke seg:**

- Med prisområdet 1–5000 trengs opptil 13 gjett med halveringsstrategien. 10 forsøk gjør derfor spillet vanskelig, noe hintet om «varmt» hjelper litt på. Elevene kan selv justere grensen.
- I løsningen kan man fortsatt gjette etter at spillet er vunnet eller tapt. Det kan løses med en variabel `spilletErFerdig`, med `return`, eller ved å deaktivere knappen. Det passer som en ekstra utfordring.


### Del 2: Gjett prisen, ferdig program

```html
<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gjett prisen</title>
</head>
<body>
    <h1>Gjett prisen!</h1>
    <p>Hva koster mobilen? Den koster mellom 1 og 5000 kr. Du har 10 forsøk.</p>
    <input id="inpGjett" type="number" min="1" max="5000">
    <button onclick="sjekkGjett()">Gjett</button>
    <button onclick="nyttSpill()">Nytt spill</button>
    <p id="txtUt"></p>

    <script>
        let pris = Math.ceil(Math.random() * 5000);
        let antallForsok = 0;

        function sjekkGjett() {
            let gjett = Number(inpGjett.value);

            if (gjett < 1 || gjett > 5000) {
                // Ugyldige gjett teller ikke som forsøk
                txtUt.textContent = "Prisen er mellom 1 og 5000 kr!";
            } else {
                antallForsok = antallForsok + 1;
                let igjen = 10 - antallForsok;
                let avstand = Math.abs(gjett - pris);

                if (gjett == pris) {
                    txtUt.textContent = `Riktig! Mobilen koster ${pris} kr. Du brukte ${antallForsok} forsøk.`;
                } else if (antallForsok >= 10) {
                    txtUt.textContent = `Game over! Prisen var ${pris} kr.`;
                } else if (gjett < pris && avstand <= 100) {
                    txtUt.textContent = `${gjett} kr er for lavt, men du er veldig nær! ${igjen} forsøk igjen.`;
                } else if (gjett < pris) {
                    txtUt.textContent = `${gjett} kr er for lavt! Prøv en høyere pris. ${igjen} forsøk igjen.`;
                } else if (avstand <= 100) {
                    txtUt.textContent = `${gjett} kr er for høyt, men du er veldig nær! ${igjen} forsøk igjen.`;
                } else {
                    txtUt.textContent = `${gjett} kr er for høyt! Prøv en lavere pris. ${igjen} forsøk igjen.`;
                }
            }

            inpGjett.value = "";
        }

        function nyttSpill() {
            pris = Math.ceil(Math.random() * 5000);
            antallForsok = 0;
            txtUt.textContent = "Ny mobil! Gjett prisen.";
        }
    </script>
</body>
</html>
```

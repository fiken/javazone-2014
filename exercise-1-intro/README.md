# Oppgave 1 - intro

## a)

I denne oppgaven skal du lage en kontroller og binde data fra denne i DOMen.

### Steg

Lag en funksjon som heter `MyCtrl`. Putt denne listen med navn inn i en variabel som heter `names`:

  * Arne
  * Bjarte
  * Conrad

Bruk funksjonen som kontroller i HTML-siden.

Putt `ng-app` i `index.html`.

Vis alle navnene som en liste i HTML-siden.

## b)

Nå utvider vi oppgaven med å kunne legge til data i controlleren fra en form.

### Steg

Lag et `form`-element med en `input` og en `button`. Bind verdien fra `input`-feltet til en variabel med `ng-model`.

I kontrolleren, lag og bind en funksjon som tar inn en parameter og legger den til listen med navn:

    ctrl.names.push(parameter);

Bind funksjonen til knappen og send med verdien fra `input`-feltet som et argument til funksjonen.

Sjekk at du kan legge til nye navn i applikasjonen.

## c) Bonusoppgave!

Hvis du prøver å legge til to strenger med samme verdi så vil du få en exception når `ng-repeat` kjøres.

Dette er fordi Angular bruker objektidentitet til å holde styr på DOM-elementer internt. Siden vi itererer over en liste
med like strenger så vil strengene ha samme identitet.

`ng-repeat` støtter en feature som heter `track by` som sier hvordan Angular skal holde styr på elementene. I vårt
tilfelle så kan man bruke `track by $index`. Oppdater siden så den fungerer med duplikate navn.

## d) Bonusoppgave!

Endre slik at hvis man taster inn et duplikat navn, så oppdatererer du lista til å bytte om navnet i lista til
"<antall> X <navn>". Eksempel: Om man taster inn Arne, Bjarte, Arne, Arne skal lista se slik ut:

* 3 X Arne
* Bjarte



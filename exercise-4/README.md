# Oppgave 4

## a)

Lag en side som viser "Antall klikk: <antall>", samt en `<button>` med en `ng-click`. Hver gang knappen trykkes på skal
telleren øke med 1.

## b)

Få koden til å fungere ved å bruke onclick, istedenfor ng-click.

## c)

Legg til denne teksten på siden: "Antall klikk x2: <dobbeltantall>". Dobbeltantall skal være en variabel som blir satt
ved å watche antall-variabelen.

## c) Bonusoppgave!

`performance.now()` kan brukes til ytelsestesting for å se hvor mange millisekunder siden nettsiden begynte å laste. Vis
`performance.now()` et sted på siden din. Lag en knapp "Kjør!" ved siden av. Når man klikker på denne knappen skal 
verdien av `performance.now()` på siden oppdateres med et intervall på 100 ms.


## Dokumentasjon:

* https://docs.angularjs.org/api/ngTouch/directive/ngClick
* https://docs.angularjs.org/guide/scope#integration-with-the-browser-event-loop
* https://docs.angularjs.org/api/ng/function/angular.element
* https://docs.angularjs.org/api/ng/type/$rootScope.Scope#$apply
* https://developer.mozilla.org/en-US/docs/Web/API/Performance.now

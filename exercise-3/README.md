# Oppgave 3 - Snacks

TODO: fjern c og d - pass på at e fortsatt er mulig

## a)

Lag en tabell med alle kommunene i Norge. Denne tabellen skal ha to kolonner:

* Navn på kommune
* Innbyggertall

Annenhver rad skal få css-klassen `text-info`. Bruk `ng-class` og `$even`.

## b)

Legg til følgende to kolonner til tabellen:

* Knapp for å skjule raden (skal være disabled på første rad)
* Knapp for å fjerne raden (skal være disabled på rad nummer 3)

Legg merke til effektene med den stripede tabellen, og at annenhver rad skulle ha klassen text-info, og hvilke knapper
som skal være disabled når du fjerner rader med ng-if og ng-show. Hvorfor virker det på den måten?

## c)

I a) la du sikkert merke til at du ikke fikk css-klassen text-info til å være på annenhver rad etter at en rad ble skjult
med ng-show/ng-if. Dette skal du fikse opp i ved å løse oppgaven på en annen måte. Lag en ny knapp som fjerner raden fra 
en annen måte som gjør at tabellen hele tiden følger reglene i a) etter at du fjerner rader med den ny knappen.

Hint: Du må fjerne elementene fra selve arrayen.


## d) Bonusoppgave!

Istedenfor å fjerne radene skal du nå flytte de til en annen tabell. Her skal det være en knapp for å flytte raden
tilbake til den originale tabellen igjen (som nederste rad).

Har du fortsatt tid kan du gjøre så knappen som skal få raden tilbake dytter den på samme posisjon som den originalt
var.


## Dokumentasjon:

* https://docs.angularjs.org/api/ng/directive/ngHide
* https://docs.angularjs.org/api/ng/directive/ngShow
* https://docs.angularjs.org/api/ng/directive/ngIf
* https://docs.angularjs.org/api/ng/directive/ngRepeat
* https://docs.angularjs.org/api/ng/directive/ngClass
* https://docs.angularjs.org/api/ng/type/$rootScope.Scope#$watch



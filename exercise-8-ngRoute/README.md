# Exercise: Single Page Applications with ngRoute

I denne oppgaven skal vi lage en SPA med to sider, en som lister opp alle personene og en som viser detaljer for en
person.

Du har fått utlevert en ferdig Angular-service i funksjonen `PersonService` som snakker med en Mongodb-database over
HTTP med `$http`-tjenesten.

## a) Oppvarming

Lag en module som er avhengig av `ngRoute`. Bruk denne som `ng-app` i applikasjonen.

Registrer `MongoLab`- og `PersonService`-tjenestene i modulen.

Sjekk at du ikke får noen feilmeldinger når du laster applikasjonen.

## b) Oppsett av routing

Lag to controllere; `listCtrl` og `detailCtrl` og registrer disse i modulen. Legg til en linje i hver controller som
skriver ut navnet på controlleren til konsollet:

    console.log('listCtrl');

Sett opp routing for disse til disse to controllerene, med følgende stier-typer:

* `/` skal bruke `listCtrl`
* `/5409fb39e4b0f26affce02b0` skal bruke `detailCtrl`. Stiargumentet skal bindes til `personId`.

Se dokumentasjonen for hvordan `path`-argumentet til `when` for hvordan de blir ut i fra sti-typene.

Lag to templates som stiene skal bruke. Du selv om de skal være inne i `index.html`, eksterne filer eller inne i
`config`-metoden. De trenger bare minimalt innhold for nå.

Hvis du nå åpner `index.html`-filen så vil du se at du automatisk får lagt til en `#/` på slutten av filnavnet i
adresselinjen i nettleseren. Dette betyr at ngRoute har startet. I konsollet så vil du se at `listCtrl` har blitt kjørt.

## c) `listCtrl`

Endre `listCtrl` slik at den bruker `PersonService.list()` for å hente data. Bind resultatet til controlleren og vis
listen i templaten.

For hver person i svaret, lag en link til detaljsiden for personen. Når du klikker på linken i nettleseren vil i
konsollet du se at `detailCtrl` har kjørt.

## c) `detailCtrl`

Endre `detailCtrl` slik at den bruker `PersonService.get(id)` for å hente personen. Bind resultatet til controlleren og vis
listen i templaten. `id` må hentes fra routen som er valgt.

Lag en link tilbake til listesiden.

## d) Bonusoppgave!

Endre `MongoLab`-tjenesten slik at `shared`-feltet blir satt til `false`. Dette gjør at du får din egen tomme collection
med et tilfeldig navn.

* Lag en form og knapp for å legge til personer.
* Lag en knapp for å slette personer på listesiden. Oppdater listen med personer etter at slettingen er gjennomført.
* Lag en knapp for å slette personer på detaljsiden. Etter at personen er slettet, send brukeren tilbake til
  listesiden.

For å slette en person så må `PersonService` utvides litt. For å slette en person så må man gjøre en HTTP `DELETE` mot
URLen til dokumentet som skal slettes. `MongoLab`-tjenestens `url`-metode vil lage korrekt url når man sender inn
dokument-iden.

## Dokumentasjon

* https://docs.angularjs.org/api/ngRoute/provider/$routeProvider

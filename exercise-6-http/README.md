# Oppgave 7: $http

I denne oppgaven så skal du lage en Angular-applikasjon som bruker `$http` for å prate med en database med brukere.

TODO: noe om at denne oppgaven prøver å lage angular-idiomatisk kode.

Tjenesten du skal bruke er MongoLab sitt API for å dytte data inn og ut av en Mongodb-collection (tabell i SQL-sjargong).
Vi har laget en ferdig service for dere som heter `MongoLab` med en funksjon som heter `url` som kan bruke for å lage
URLer på formen som oppgaven trenger.

URLen som genereres av `url()` støtter disse HTTP-verbene:

* `GET`: returnerer en array med alle dokumentene (radene i SQL-sjargong) i collectionen
* `POST`: lagrer et nytt dokument i collectionen. Returnerer et objekt med et `_id`-felt

URLen som genereres av `url('5409fb39e4b0f26affce02b0')` støtter disse HTTP-verbene:

* `GET`: returnerer objektet hvis id ble gitt inn
* `PUT`: oppdaterer dokumentet med den nye versjonen. Returnerer et objektet hvis id ble gitt inn

## Tips

  * Objektene du får fra MongoLabs ser slik ut:

        {
          "_id": {
            "$oid": "5409fb39e4b0f26affce02b0"
          },
          "name": "Ola Normann"
        }

  * Collectionen inneholder allerede noe data som deles mellom alle.

## a)

Lag en `PersonService` med en `list`-metode som henter alle personene i databasen. Servicen må registreres i Angular og
ha en avhengighet på `$http`.

TODO: lag en run() som gjør PersonService.list() og viser verdiene i console.

## b)

Lag en controller som er avhengig av `PersonService`. Når controlleren kjører så må den gjøre et kall til `list()` og
registrere et callback på returverdien slik at man kan få tak i dataene.

Vis alle navnene og objekt-idene til personene i en tabell.

## c)

Endre `MongoLab`-tjenesten slik at `shared`-feltet blir satt til `false`. Dette gjør at du får din egen tomme collection
med et tilfeldig navn.

## d)

Legg til `store`-funksjon i `PersonService` for å lagre et nytt dokument i collectionen.

Lag en `<form>` med en tekst-felt og en 'legg til'-knapp. Bind verdien av feltet til `ctrl.name` og bind `nc-click` til
en funksjon i controlleren. Bruk den nye metoden i `PersonService` for å lagre personen.

For å se den nye personen så må du laste siden på nytt.

## e) Bonusoppgave!

Du vil legge merke til at listen med personer ikke oppdateres automatisk når dataene sendes til Mongodb.

Legg til et callback som håndterer resultatet av `store` og oppdaterer den listen med personer.

## f) Bonusoppgave!

MongoLab-tjenesten bruker litt tid på å ta i mot og lagre dataene så det går litt tid mellom at brukeren trykker på
knappen og at svaret kommer tilbake fra MongoLab.

Lag en advarsel til brukeren ved siden av knappen som vises når brukeren trykker på knappen og helt til man har fått et
svar tilbake.

Tips: `ng-show`

## Dokumentasjon:

  * https://docs.angularjs.org/api/ng/service/$http
  * http://docs.mongolab.com/restapi/

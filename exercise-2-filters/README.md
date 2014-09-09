# Oppgave 2 - filters

## a)
Lag en side uten noe mer JavaScript enn de tre linjene i prekoden. Siden skal vise en listen over kommunene i Norge,
sortert etter navn. Se gjerne dokumentasjon for orderBy.


## b)

Legg til et inputfelt på siden som skal brukes til å søke etter kommune (basert på navn). Legg til filteret som er
nødvendig for at denne skal virke.


## c)

Lag et nytt filter som heter "gt". Dette filteret skal filtrere vekk kommuner som har færre antall innbyggere enn det 
som blir gitt som parameter. Som parameter skal du lage et inputfelt med binding til `ctrl.minSize`. Filteret skal 
benyttes på siden slik at kun de kommunene med flere innbyggere enn det som blir skrevet i "minSize" vises: 
`ctrl.munis | gt:ctrl.minSize`  

I tillegg skal kun de 10 minste kommunene som passer kriteriet skal vises. Disse kommunene skal være sortert på navn. 
Forventent resultat når man taster inn 1337:

* Aremark - 1408
* Dønna - 1420
* Engerdal - 1345
* Etnedal - 1408
* Evenes - 1391
* Flakstad - 1368
* Hyllestad - 1391
* Lebesby - 1341
* Lierne - 1385
* Rollag - 1369

Endre siden så `ctrl.minSize` default er satt til 1000.

## d) Bonusoppgave!

Endre c) med følgende elementer:

* La det være mulig å taste inn hvor mange kommuner som skal vises (default 10).
* La det være mulig å bestemme om sorteringen skal være stigende eller synkende (med en checkbox).
* La det være mulig å bestemme om listen skal sorteres etter navn eller etter innbyggertall (med to radio buttons).

## Dokumentasjon:

* https://docs.angularjs.org/api/ng/filter/orderBy
* https://docs.angularjs.org/api/ng/filter/filter
* https://docs.angularjs.org/api/ng/filter/limitTo
* https://docs.angularjs.org/guide/filter#creating-custom-filters

# Oppgave 5

I JavaScript regnes det som lite gunstig å forurense det globale `window` med verdier. En vanlig måte å forhindre dette 
er på er ved å legge koden i en "immediately-invoked function expression" eller IIFE. De ser typisk slik ut: 
`(function(){/* kode */}());`

## a)

Opprett angular-modulen 'MyJzApp' i siden. Registrer en konstant i denne modulen med navn 'title' - la verdien være en
string, feks "Mr. Manager". I tillegg skal du registrere en controller med navn 'myCtrl' i modulen. I 'myCtrl' skal du 
injecte 'title', slik at du kan vise den i en `<h1>`-tagg på siden.


## b)

Lag en factory med navn 'namesFactory'. Denne skal opprette en service som har en function - 'random()'. 'random()'
skal returnere et tilfeldig navn fra listen 'adNames'.

Registrer 'namesFactory' i 'MyJzApp'-modulen med navnet 'names'. La controlleren få 'names' som dependency. Bruk 
`names.random()` i controlleren slik at siden viser et tilfeldig navn fra 'names'-servicen.


## c)

Nå skal vi stykke opp koden over enda mer - funksjonaliteten skal være den samme.

* Lag to nye separate IIFE-er
* I den første oppretter du en modul 'jzConstants'. Der registrerer du først 'title'-konstanten
* I den andre IIFE-en skal definerer en ny konstant i 'jzConstants': 'adNames'.
* I den andre IIFE-en skal du også opprette en ny modul: 'jzServices'. 'jzServices' skal ha en avhengighet til 
'jzConstants'. Her skal du registrere 'namesFactory'. 'namesFactory' skal ha 'adNames' som dependency.
* Endre 'MyJzApp' til å få en dependency til 'jzServices'. Test at alt virker som før.

## d) Bonusoppgave!

Løs oppgave 4c, men denne gangen med å injecte servicen '$timeout' og bruk den istedenfor.


## Dokumentasjon:

* https://docs.angularjs.org/api/ng/type/angular.Module

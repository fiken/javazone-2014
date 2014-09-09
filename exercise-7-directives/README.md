# Oppgave 6


## a)
I denne oppgaven skal du lage et enkelt direktiv for enkelt å kunne utføre en handling ved en form reset-event.
Reset er en event som oppstår fra `<form>`-elementet når det trykkes på en `<button type="reset">Reset</button>`-knapp.
Oppgaven er laget slik at den kan løses uten bruk av noen controller utenom den i direktivet.

  * Start med å opprette en modul med navn 'MyJzApp'. Registrer et direktiv kalt 'jzReset' i modulen.
  * Direktivet er et attribute-direktiv til `<form>`-elementet. Det er avhengig av `$parse` for å fungere. Det skal kun 
    kun bestå av en controller


      function direktivFn(evtAvhengigheter){ 
        return { controller:controllerFn} }
      }


  * Controlleren trenger `$scope` og `$element`. `$attrs` er også praktisk
  * Angular inneholder et lite subset av jQuerys funksjonalitet kalt jqLite. `$element` er et jqLite-element, ikke et 
    rent DOM-element. Du kan bruke `$element.bind('reset', onResetFn)` for å lytte til reset-event fra form-en
  * Husk at Angular må få beskjed når du gjør en endring i modellen som trigget av en DOM-event
  * Verdien av `jz-reset` skal være et angular-expression som setter variabelen 'status' til 'reset' og 'name' til '' (blank)
  * Bruk `$parse(expression)` til å parse en string som et Angular expression. Resultatet gir en funksjon som tar et scope
    som parameter
  * `<input>`-feltet skal ha toveis-binding mot 'name'


## b)

Nå skal vi utvide siden med et enkelt element-direktiv - `<jz-label>`. Direktivet skal ha et eget isolert scope med
binding til 'status'.

  * Registrer direktivet 'jzLabel' i 'MyJzApp'. Ettersom dette er et element må `restrict:'E'` være med i konfigurasjonen
  * Isolert scope med toveis-binding gjør du med '='
  * Template skal være en `<span class="label label-default">` med innhold fra 'jzText'


      function direktiv() { return {
        restrict:'E',
        scope:{jzText:'='},
        template:'<span class="label label-default"> ...</span>' }
      }
      
        
  * 'jz-text' i 'jz-label' skal bindes til 'status'

## c) Bonusoppgave!

### jzReset

  * 'status' skal få verdien 'pristine' når siden initieres. Ta en titt på `ng-init`!
  * Når det skjer en endring i `<input>`-feltet så skal 'status' få verdien 'dirty'
  * Bruk en post-link-funksjon i stedet for en controller i direktivet 


      function direktivFn(evtAvhengigheter){ 
        return { link:linkFn } 
      }


### jzLabel

  * Endre template slik at label får klassen 'label-success' istedenfor 'label-default' dersom 'jzText' er lik 'dirty'
  * Skjul direktivet dersom 'name' har mer enn tre tegn

## Dokumentasjon

  * https://docs.angularjs.org/api/ng/directive/ngInit
  * https://docs.angularjs.org/api/ng/directive/ngChange
  * https://docs.angularjs.org/api/ng/service/$parse
  * https://docs.angularjs.org/api/ng/function/angular.element
  * https://docs.angularjs.org/guide/directive
  * https://docs.angularjs.org/api/ng/service/$compile

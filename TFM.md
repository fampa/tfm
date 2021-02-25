---
title: "Aplicació Web Progressiva (PWA) de gestió d'una AMPA"
abstract: "El present **Treball Final de Màster** planteja el desenvolupament d'una PWA que facilitarà la gestió de les AMPA a més a més de fomentar la participació dels propis pares, propiciar la sol·licitud de serveis de manera online, així com facilitar la comunicació al sí de l'associació."
author: 'Josep V. Monjo'
date: '24/02/2021'
lang: ca
include-before:
- '`\newpage{}`{=latex}'
toc: true
numbersections: true
bibliography: ["bibliography.bib"]
fontfamily: lmodern
linkcolor: blue
urlcolor: blue
header-includes: |
    \usepackage{fancyhdr}
    \pagestyle{fancy}
    \fancyhf{}
    \rhead{TFM}
    \lhead{Josep V. Monjo}
    \cfoot{\thepage}
    \usepackage{setspace}
    \doublespacing
---

\newpage{}

# Introducció

## Context i justificació del Treball

La gestió de les Associacions de Mares i Pares d'Alumnes inclou bases de dades de pares, d'alumnes, de pagament de quotes, de serveis, etc... Aquesta tasca s'ha realitzat tradicionalment de manera offline (MS Excel, MS Access,...). El canvi a una eina online facilitarà no només aquesta gestió si no que propiciarà la participació dels propis pares i mares en la gestió i actualització de les seues dades així com en la sol·licitud de serveis que ofereix la seua AMPA de manera online, evitant l'ús de formularis en paper i minimitzant el contacte físic, aspecte aquest molt important en aquests temps de pandèmia mundial.

A més a més facilitarà la comunicació dels membres de la Junta de govern del AMPA amb els seus afiliats, ajudant a gestionar els continguts del blog, notícies, axí com l'enviament de notificacions push.

## Objectius del Treball

Els objectius del treball són:

- El plantejament de les necessitats de les AMPA que puguen ser assolides mitjançant una aplicació web i que plasmarem en forma de requeriments.
- La modernització en la gestió de les AMPA, integrant el catàleg d'eines i aplicacions de gestió obsoletes en una única aplicació centralitzada i allotjada a un servidor web.
- Substituir les eines privatives que poguéssin estar usant en l'actualitat per una aplicació web de codi obert que puga ser usada i adaptada per totes les AMPA de manera lliure.
- Evitar l'ús de formularis en paper i minimitzar el contacte personal.

## Enfocament i tecnologies

L'aplicació segueix un enfocament basat en el model d'aplicació web progressiva (PWA[^pwa]) en el _frontend_ i una API basada en GraphQL per al _backend_.

[^pwa]: De les segles en anglés Progressive Web App.

### PWA

El model d'aplicació web progressiva està basat en estàndards web i no en cap _framework_ o empresa. Per a que una aplicació web siga considerada PWA, ha de complir una sèrie de requisits que podríem dividir en tres grans àrees [@richard_what_2020]:

- Capaç: Gràcies a les cada vegada més extenses API web, combinades amb l'ús de _web assembly_, hi ha poques coses que una web app no siga capaç de realitzar (xat en temps real, notificacions push, geolocalització, etc...)
- Confiable: una PWA s'ha de sentir ràpida, tant en la càrrega com en la interacció de l'usuari. A més a més ha de permetre certa usabilitat amb una connexió a la xarxa dèbil o inexistent. Açò és possible gràcies als _service workers_.
- Instal·lable: una PWA s'executa en la seua pròpia finestra i ha de poder ser llançada des de l'escriptori de l'usuari.

### GraphQL

GraphQL és un llenguatge query per a APIs i temps d'execució que proporciona de manera automàtica descripció de les dades que figuren a la API i permet obtenir només aquells camps que ens interessen des d'un únic _endpoint_.

## Metodologia

S'emprarà una metodologia de tipus _waterfall_. Per tant es presentarà el document de requeriments al client per a que el valide, i una vegada fet procedirem a executar les tasques necessàries de manera seqüencial.

Les etapes per les que passarem seran les que detallarem al següent apartat de planificació del treball.

## Planificació del Treball

### Requeriments

Elaboració i aprovació per part del client del document de requeriments de l'aplicació. Una vegada tancat aquest document iniciarem la següent fase.

## Disseny

Elaboració del disseny de l'aplicació. S'elaborarà un _wireframe_ de baixa fidelitat i una vegada validat per part del client s'elaborarà un _mockup_ del disseny final.

Una vegada aprovat el disseny final passarem a la següent fase.

## Desenvolupament

### Backend

Instal·larem el l'eina [Hasura](https://hasura.io/) a un servidor VPS contractat pel client. Això ens facilitarà tindre en funcionament una base de dades postgreSQL i un servidor graphQL de manera ràpida.

Dissenyarem les taules i les relacions necessàries, partint dels continguts de la base de dades que usen actualment, MS Access.

Configurarem el sistema d'autenticació amb [Firebase](https://firebase.google.com/) i el d'autorització amb _Hasura_.

### Frontend

Instal·larem localment el framework [Quasar](https://quasar.dev/), basat en VueJS.

Elaborarem les rutes necessàries per a la nostra app així com el sistema d'autenticació i autorització.

Adaptarem la nostra app per que complisca els requisits d'una PWA i ens assegurarem que hem acomplit tots els requeriments.

## Proves

Escriurem els tests unitaris que necessitem i farem les proves d'integració i funcionals que calguen.

## Llançament

Actualitzarem les DNS del domini del client per a que apunte a la versió de producció de l'aplicació.

# Test

# Bibliografia

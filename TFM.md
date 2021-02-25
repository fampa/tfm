---
title: "Aplicació Web Progressiva (PWA) de gestió de les AMPA"
abstract: "El present treball final de màster planteja el desenvolupament d'una PWA que facilitarà la gestió de les AMPA a més a més de fomentar la participació dels propis pares en la gestió i actualització de les seues dades així com en la sol·licitud de serveis que ofereix la pròpia AMPA, així com facilitar la comunicació."
author: 'Josep V. Monjo'
date: '24/02/2021'
lang: ca
toc: true
numbersections: true
bibliography: bibliography.bib
# fontfamily: FiraSans
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

# Introducció

## Context i justificació del Treball

La gestió de les Associacions de Mares i Pares d'Alumnes inclou bases de dades de pares, d'alumnes, de pagament de quotes, de serveis, etc... Aquesta tasca s'ha realitzat tradicionalment de manera offline (MS Excel, MS Access,...). El canvi a una eina online facilitarà no només aquesta gestió si no que propiciarà la participació dels propis pares i mares en la gestió i actualització de les seues dades així com en la sol·licitud de serveis que ofereix la seua AMPA, així com facilitar la comunicació amb els afiliats.

## Objectius del Treball

Els objectius del treball són:

- El plantejament de les necessitats de les AMPA que puguen ser assolides mitjançant una aplicació web i que plasmarem en forma de requeriments.
- La modernització en la gestió de les AMPA, integrant el catàleg d'eines i aplicacions de gestió obsoletes en una única aplicació centralitzada i allotjada a un servidor web.
- Substituir les eines privatives que poguéssin estar usant en l'actualitat per una aplicació web de codi obert que puga ser usada i adaptada per totes les AMPA de manera lliure.

## Enfocament i mètode

L'aplicació segueix un enfocament basat en el model d'aplicació web progressiva (PWA[^pwa]) en el _frontend_ i una API basada en GraphQL per al _backend_.

[^pwa]: De les segles en anglés Progressive Web App.

### PWA

El model d'aplicació web progressiva està basat en estàndards web i no en cap _framework_ o empresa. Per a que una aplicació web siga considerada PWA, ha de complir una sèrie de requisits. Segons Sam Richard [©richard_what_2020], ha de ser:

- Capaç: Gràcies a les cada vegada més extenses API web, combinades amb l'ús de _web assembly_, hi ha poques coses que una web app no siga capaç de realitzar (xat en temps real, notificacions push, geolocalització, etc...)
- Confiable: una PWA s'ha de sentir ràpida, tant en la càrrega com en la interacció de l'usuari. A més a més ha de permetre certa usabilitat amb una connexió a la xarxa dèbil o inexistent. Açò és possible gràcies als _service workers_.
- Instal·lable: una PWA s'executa en la seua pròpia finestra i ha de poder ser llançada des de l'escriptori de l'usuari.

### GraphQL

GraphQL és un llenguatge query per a APIs i temps d'execució que proporciona de manera automàtica descripció de les dades que figuren a la API i permet obtenir només aquells camps que ens interessen des d'un únic _endpoint_ [@noauthor_graphql_nodate].

## Planificació del Treball

# Bibliografia

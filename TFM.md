---
title: "Desenvolupament d'una _Progressive Web App_ (PWA) de gestió d'una AMPA"
abstract: > 
    El present **Treball Final de Màster** planteja el desenvolupament d'una PWA que facilitarà la gestió de les AMPA a més a més de fomentar la participació dels propis pares, propiciar la sol·licitud de serveis de manera online, així com facilitar la comunicació al sí de l'associació mitjançant notificacions push.
    
    \newline{}

    \newline{}

    Paraules clau: PWA, AMPA, GraphQL, VueJS, NodeJS

    \newline{}

    \newline{}

    **Abstract**

    \newline{}

    \newline{}

    _This **Final Master's Thesis** proposes the development of a PWA that will facilitate the management of Parents Associations in addition to encouraging the participation of parents themselves, promote the request for services online, as well as facilitate communication within the association through push notifications._

    _keywords: PWA, AMPA, GraphQL, VueJS, NodeJS_
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

## Context

No cal recordar que el context actual de pandèmia mundial facilita que cada vegada més la gent estiga a sa casa i realitze totes les seues gestions de manera telemàtica, posant de relleu la importància de les eines digitals i de telegestió com ara videoconferències, administració electrònica, teletreball, etc...

És en aquest context que sorgeix la necessitat de modernitzar la gestió del AMPA.

## Justificació del Treball

La gestió de les Associacions de Mares i Pares d'Alumnes inclou bases de dades de pares, d'alumnes, de pagament de quotes, de serveis, etc... Aquesta tasca s'ha realitzat tradicionalment de manera offline (MS Excel, MS Access,...). El canvi a una eina online facilitarà no només aquesta gestió si no que propiciarà la participació dels propis pares i mares en la gestió i actualització de les seues dades així com en la sol·licitud de serveis que ofereix la seua AMPA de manera online, evitant l'ús de formularis en paper i minimitzant el contacte físic, aspecte aquest molt important en aquests temps de pandèmia mundial.

A més a més facilitarà la comunicació dels membres de la Junta de govern del AMPA amb els seus afiliats, ajudant a gestionar els continguts del blog, notícies, axí com l'enviament de notificacions push.

# Descripció

En un primer moment es va plantejar la possibilitat d'elaborar un model _SaaS_[^sass]. En aquest cas l'aplicació podria contenir la gestió de diferents AMPA i cadascuna d'elles podria tindre el seu propi subdomini. No obstant aquesta possibilitat es va descartar per falta de temps, ja que aquest model incrementaria la complexitat.

[^sass]: De les segles en anglès _Software as a Service_.

Per això s'ha decidit finalment decantar-nos per un enfocament basat en el model d'aplicació web progressiva (PWA[^pwa]) en el _frontend_ i una API basada en GraphQL per al _backend_.

[^pwa]: De les segles en anglès _Progressive Web App_.

El model d'aplicació web progressiva està basat en estàndards web i no en cap _framework_ o empresa. Per a que una aplicació web siga considerada **PWA**, ha de complir una sèrie de requisits que podríem dividir en tres grans àrees [@richard_what_2020]:

- Capaç: Gràcies a les cada vegada més extenses API web, hi ha poques coses que una web app no siga capaç de realitzar avui en dia (xat en temps real, notificacions push, geolocalització, etc...).
- Confiable: una PWA s'ha de sentir ràpida, tant en la càrrega com en la interacció amb l'usuari. A més a més ha de permetre certa usabilitat amb una connexió a la xarxa dèbil o inexistent. Açò és possible gràcies als _service workers_.
- Instal·lable: una PWA s'executa en la seua pròpia finestra i ha de poder ser llançada des de l'escriptori de l'usuari.

Pel que fa a **GraphQL** és un llenguatge query per a APIs que proporciona de manera automàtica una documentació de les dades que poden ser extretes de la API, autocompletat de les _queries_ i a més a més permet obtenir només aquells camps que ens interessen des d'un únic _endpoint_.

El projecte constarà de les següents fases.

## Investigació/Requeriments

Investigació de les característiques que haurà de tenir l'aplicació en base a les necessitats d'una AMPA, seguit de l'elaboració d'un document de requeriments que haurà de ser aprovat per part del client. Una vegada tancat aquest document iniciarem la següent fase.

## Disseny

Elaboració del disseny de l'aplicació. S'elaborarà un _wireframe_ de baixa fidelitat i/o un _mockup_ d'alta fidelitat del disseny final.

Una vegada aprovat el disseny final passarem a la fase de desenvolupament.

## Desenvolupament

### Backend

Instal·larem l'eina [Hasura](https://hasura.io/) a un servidor VPS contractat pel client. Això ens facilitarà tindre en funcionament una base de dades postgreSQL i un servidor graphQL de manera ràpida.

Dissenyarem les taules i les relacions necessàries, segons el full de requeriments.

Configurarem el sistema d'autenticació amb [Firebase](https://firebase.google.com/) i el d'autorització amb _Hasura_.

Addicionalment posarem en marxa un petit servidor _NodeJS_ per gestionar transaccions amb dades sensibles com per exemple certes claus API, i els mecanismes per autoritzar a un administrador, i d'altres com ara l'enviament de missatges per correu electrònic i de notificacions push.

### Frontend

Instal·larem localment el framework [Quasar](https://quasar.dev/), basat en VueJS.

Elaborarem les rutes necessàries per a la nostra app així com el sistema d'autenticació i autorització.

Adaptarem la nostra app per que complisca els requisits d'una PWA i ens assegurarem que hem acomplit tots els requeriments.

## Proves

Escriurem els tests unitaris que necessitem i farem les proves d'integració i funcionals que calguen.

## Llançament

Actualitzarem les DNS del domini del client per a que apunte a la versió de producció de l'aplicació.

# Objectius

## Objectiu principal

- La modernització en la gestió de les AMPA, integrant el catàleg d'eines i aplicacions de gestió obsoletes en una única aplicació centralitzada i allotjada a un servidor web.

## Objectius secundaris

- El plantejament de les necessitats de les AMPA que puguen ser assolides mitjançant una aplicació web i que plasmarem en forma de requeriments.
- Substituir les eines privatives que poguéssin estar usant en l'actualitat per una aplicació web de codi obert que puga ser usada i adaptada per totes les AMPA de manera lliure.
- Evitar l'ús de formularis en paper i minimitzar el contacte personal.
- Afavorir la immediatesa en les gestions i comunicacions amb l'AMPA.

# Continguts

Pendent

# Metodologia

S'emprarà una metodologia de tipus _waterfall_ amb retroalimentació. Per tant es presentarà el document de requeriments al client per a que el valide, i una vegada fet procedirem a executar cadascuna de les tasques necessàries de manera seqüencial, tornant enrere a alguna d'elles si fos necessari per reajustar algun requeriment.

# Arquitectura de l'aplicació

Pendent

# Plataforma de desenvolupament

L'aplicació constarà de les següents parts:

- Una base de dades postgreSQL gestionada per una API GraphQL, mitjançant el _framework_ _Hasura_.
- Un servidor NodeJS
- Un _frontend_ VueJS mitjançant el framework _Quasar_.
- Un servei d'autenticació mitjançant _Firebase_.
  
El desenvolupament tindrà lloc principalment en dues màquines amb Sistema Operatiu Linux, i el IDE _Visual Studio Code_.

El present treball està redactat en llenguatge _Markdown_ i convertit a PDF amb [Pandoc](https://pandoc.org/).

# Planificació del treball

PAC | Activitat | Inici | Fi
--- | --- | ---| ---
1 | **Plantejament del projecte** | 17/02/2021 | 02/03/2021
" | Document de requeriments | " | "
" | Context i Justificació | " | "
2 | **Desenvolupament i documentació I** | 03/03/2021 | 31/03/2021
" | Desenvolupament i docs Backend | " | "
" | Desenvolupament i docs Frontend | " | "
2 | **Desenvolupament i documentació II** | 01/04/2021 | 09/05/2021
" | Desenvolupament i docs Backend | " | "
" | Desenvolupament i docs Frontend | " | "
" | MVP i primeres proves (vídeo) | " | "
3 | **Desenvolupament i documentació III** | 10/05/2021 | 07/06/2021
" | Finalitzar Desenvolupament i docs | " | "
" | Finalitzar Memòria TFM | " | "
" | Elaborar presentació | " | "
" | Presentació en vídeo | " | "
" | Elaborar autoinforme d'avaluació | " | "

(...)

# Procés de treball/desenvolupament

Pendent

# Bibliografia

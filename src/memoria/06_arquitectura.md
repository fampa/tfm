# Arquitectura de l'aplicació

L'aplicació segueix un model MVVM[^mvvm]. Es tracta d'un model de desenvolupament que separa el _business logic_ de la capa de presentació, el que propícia la separació i la modularització del nostre codi, afavorint l'elaboració de tests unitaris i col·laborant a tindre un codi més net i més fàcil de mantenir [@britz_enterprise_2017]. A diferència del model MVC[^mvc], el MVVM utilitza llenguatge de marcat per a la capa d'unió entre la capa lògica i la capa de presentació. Aquest és el cas del _framework VueJS_ tal i com podem veure a la @fig:mvvm. A més a més e el model MVC el controlador és el punt d'entrada de l'aplicació mentre que en el MVVM la vista és el punt d'entrada [@rungta_mvc_nodate].

[^mvvm]: _Model View View-Model_
[^mvc]: _Model View Controller_

![Model MVVM. Font: https://vuejs.org](img/mvvm-vue.png){#fig:mvvm}

El diagrama de flux de la nostra aplicació el podem observar a la @fig:diagramaFlux.

WIP

![Diagrama de flux](img/diagrama-flux.svg){#fig:diagramaFlux}

## Repositoris

- Frontend i NodeServer: <https://github.com/fampa/ampa-pwa>
- Backend: <https://github.com/fampa/ampa-graphql>

## URL de l'aplicació

<https://fampa-pwa.web.app/>

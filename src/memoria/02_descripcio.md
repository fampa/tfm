# Descripció

S'ha decidit finalment aplicar un enfocament basat en el model d'aplicació web progressiva (PWA[^pwa]) en el _frontend_ en combinació amb una API GraphQL per al _backend_.

[^pwa]: De les segles en anglès _Progressive Web App_.

El model d'aplicació web progressiva està basat en estàndards web i no en cap _framework_ o empresa. Per a que una aplicació web siga considerada **PWA**, ha de complir una sèrie de requisits que podríem dividir en tres grans àrees [@richard_what_2020]:

- Capaç: Gràcies a les cada vegada més extenses API web, hi ha poques coses que una web app no siga capaç de realitzar avui en dia (xat en temps real, notificacions push, geolocalització, etc...).
- Confiable: una PWA s'ha de sentir ràpida, tant en la càrrega com en la interacció amb l'usuari. A més a més ha de permetre certa usabilitat amb una connexió a la xarxa dèbil o inexistent. Açò és possible gràcies als _service workers_.
- Instal·lable: una PWA s'executa en la seua pròpia finestra i ha de poder ser llançada des de l'escriptori de l'usuari.

Pel que fa a **GraphQL** és un llenguatge query per a APIs que proporciona de manera automàtica una documentació de les dades que poden ser extretes de la API, autocompletat de les _queries_ i a més a més permet obtenir només aquells camps que ens interessen des d'un únic _endpoint_.

El projecte constarà de les fases que detallarem a continuació.

## Investigació/Requeriments

Investigació de les característiques que haurà de tenir l'aplicació en base a les necessitats d'una AMPA, seguit de l'elaboració d'un document de requeriments que haurà de ser aprovat per part del client. Una vegada tancat aquest document iniciarem la següent fase.

## Disseny

Elaboració del disseny de l'aplicació. S'elaborarà un _wireframe_ de baixa fidelitat i/o un _mockup_ d'alta fidelitat del disseny final.

Una vegada aprovat el disseny final passarem a la fase de desenvolupament.

## Desenvolupament

### Backend

Instal·larem l'eina [Hasura](https://hasura.io/) (a un servidor VPS contractat pel client, o a un servei al núvol). Això ens facilitarà tindre en funcionament una base de dades postgreSQL i un servidor graphQL de manera ràpida.

Dissenyarem les taules i les relacions necessàries, segons el full de requeriments.

Configurarem el sistema d'autenticació amb [Firebase](https://firebase.google.com/) i el d'autorització amb _Hasura_.

Addicionalment posarem en marxa un petit servidor _NodeJS_ per gestionar transaccions amb dades sensibles com per exemple certes claus API que necessiten residir al costat del servidor, i els mecanismes per autoritzar a un administrador, així com d'altres com ara l'enviament de missatges per correu electrònic o de notificacions push.

### Frontend

Instal·larem localment el framework [Quasar](https://quasar.dev/), basat en VueJS.

Elaborarem les rutes necessàries per a la nostra app així com el sistema d'autenticació i autorització.

Adaptarem la nostra app per que complisca els requisits d'una PWA i ens assegurarem que hem acomplit tots els requeriments.

## Proves

Escriurem els tests unitaris que necessitem i farem les proves d'integració i funcionals que calguen.

## Llançament

Actualitzarem les DNS del domini del client per a que apunte a la versió de producció de l'aplicació.

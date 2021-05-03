# Introducció

## Context

No cal recordar que el context actual de pandèmia mundial propícia que cada vegada més les persones romanguen a sa casa i realitzen totes les seues gestions de manera telemàtica, posant de relleu la importància de les eines digitals i de telegestió com ara videoconferències, aprenentatge online, administració electrònica, teletreball, etc...

És en aquest context que sorgeix la necessitat de modernitzar la gestió de l'Associació de Mares i Pares d'Alumnes (AMPA).

### Estudi de mercat

Fent un estudi de mercat, en un primer moment es va plantejar la possibilitat d'elaborar un model _SaaS_[^sass]. En aquest cas l'aplicació podria contenir la gestió de diferents AMPA i cadascuna d'elles podria tindre el seu propi subdomini. Aquest és el model més freqüent al mercat per a quest tipus d'aplicacions web.

No obstant això, aquesta possibilitat es va descartar perquè la finalitat inicial no era muntar un negoci _SaaS_ si no desenvolupar internament una eina per a l'autogestió de la AMPA de la que forme part com a membre de la Junta, fent-la el més oberta i transparent possible per a que puga ser implementada a altres AMPA o associacions que no vulguen un model de subscripció si no un d'autogestionat.

[^sass]: De les segles en anglès _Software as a Service_.

No obstant això, aquesta aplicació és relativament fàcil de reconvertir a un model de SaaS si en el futur es volgués usar per aquesta finalitat, ja que no totes les AMPA disposen de personal qualificat per posar en marxa una aplicació web a partir del seu repositori públic.

A continuació detallaré un **estudi de la competència** en aquest sector.

#### Mi ampa

- Url: <https://miampa.com/>
- Model de negoci: SaaS
- Descripció: ofereix inscripció online de socis, comptabilitat, multiidioma, gestió d'esdeveniments, extraescolars, tenda, galeria d'imatges, menus, carnet virtual, enquestes, web, personalització.
- Preu: s/d

#### playoff gestión de asociaciones

- Url: <https://playoffinformatica.com/gestion-de-asociaciones>
- Model de negoci: SaaS
- Descripció: Versàtil per a qualsevol tipus d'associació. Gestió de pagaments online i rebuts SEPA, gestió d'activitats, comunicacions per correu i mòbil, carnet virtual.
- Preu: entre 25€ i 65€ mensuals

#### AmpaSoft

- Url: <https://ampasoft.es/>
- Model de negoci: SaaS
- Descripció: gestió d'alumnes/pares, gestió econòmica (generació de remeses bancàries), missatgeria.
- Preu: s/d

#### AmpaNet

- Url: <https://www.ampanet.es/>
- Model de negoci: SaaS
- Descripció: gestió d'alumnes/pares, extraescolars, menjador, acampades, activitats, rebuts SEPA, web, tenda.
- Preu: s/d

#### EduTeca

- Url: <https://edutecaservicios.es/software-especializado/>
- Model de negoci: SaaS
- Descripció: Gestió altes/baixes, tallers/activitats, comunicacions, actes de junta i assemblea, web, memòria d'activitat i control de pressupost, matinera, menjador, comptabilitat, remeses bancàries.

#### GesAmpa

- Url: <https://gesampa.com/joomla/>
- Model de negoci: Llicència d'ús de Software + suport.
- Descripció: Gestió de membres i domiciliacions bancàries.
- Preu: des de 15€/mes o 100€/any

## Justificació del Treball

La gestió de les Associacions de Mares i Pares d'Alumnes inclou bases de dades amb dades de pares, d'alumnes, de pagament de quotes, de serveis, etc... Aquesta tasca s'ha realitzat tradicionalment de manera offline (MS Excel, MS Access, formularis en paper,...) i amb poca o cap automatització. El canvi a una eina online facilitarà no només aquesta gestió si no que propiciarà la participació dels propis pares i mares en la gestió i actualització de les seues dades, així com en la sol·licitud de serveis que ofereix la seua AMPA de manera online, evitant l'ús de formularis en paper i minimitzant el contacte físic, aspecte aquest molt important en aquests temps de pandèmia mundial.

A més a més facilitarà la comunicació dels membres de la Junta de govern del AMPA amb els seus afiliats, ajudant a gestionar els continguts coma ara notícies, activitats, juntes, etc... axí com l'enviament de notificacions push.

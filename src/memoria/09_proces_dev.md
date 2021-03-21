# Procés de treball/desenvolupament

## Disseny dels mockup

Hem dissenyat l'aplicació amb l'eina online [Figma](https://www.figma.com/) usant un acostament _mobile first_, ja que s'espera que la majoria de trànsit vinga des de dispositius mòbils.

WIP

## Desenvolupament del _backend_

WIP

## Desenvolupament del _frontend_

En primer lloc instal·lem quasar:

`yarn global add @quasar/cli`

I creem el projecte:

`quasar create <folder_name>`

Si volem usar Quasar V2.0 necessitarem un pas extra ja que a la data d'escriure aquesta documentació aquesta versió no es troba a la branca principal.

`yarn upgrade quasar@next`

Finalment executem `yarn` per instal·lar totes les dependències.

Afegim suport per dotenv: `yarn add --dev dotenv`, i editem el fitxer `/quasar.conf.js`:

```javascript
build: {
  env: require('dotenv').config().parsed
}
```

Seguint les recomanacions a la web oficial de Quasar, he instal·lat la versió 2, malgrat que encara es troba en beta. Això ha requerit certs _workarounds_ com ara els proposats a aquest _issue_ de github per fer funcionar la _store_ de Vuex:
[https://github.com/quasarframework/quasar/issues/8500]

## Components

Creem els components que necessitarem:

- src/components/NewsCard.vue

Per a que totes les targetes de notícies tinguen la mateixa independentment de la mida del titular he optat per una solució via css per fer elipsis del titular quan sobrepassa 2 línies:

```css
.titular {
  display: inline-block;
  height: 65px;
  overflow: hidden;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;
  text-overflow: ellipsis;
}
```

## GraphQl

Afegim support per a _GraphQl_ amb _Apollo client_.

`yarn add @vue/apollo-composable`

Per a poder usar queries en fitxers independents en format `.gql` necessitem afegir aquest codi a `src/shims-vue.d.ts`:

```js
declare module '*.gql' {
  import { DocumentNode } from 'graphql'

  const content: DocumentNode
  export default content
}
```

I a `quasar.conf.js`:

```js
chainWebpack (chain /** { isServer, isClient } **/) {
  // ...
  chain.module.rule('gql')
          .test(/\.(graphql|gql)$/)
          .use('graphql-tag/loader')
          .loader('graphql-tag/loader')
  // ...
}
```

## Vuex

Per a manejar l'estat de la nostra aplicació usem Vuex, instal·lat durant la configuració inicial de Quasar. Per a que l'estat persisteixi usarem `vuex-persistedstate`:

`yarn add vuex-persistedstate`

I afegirem ho configurem a Vuex al fitxer `src/store/index.ts`:

```js
import createPersistedState from 'vuex-persistedstate'

const store = createStore({
  // ...
  plugins: [createPersistedState()]
});
```

## Autenticació i autorització

Usarem Firebase per tasques d'autorització i autenticació.

El primer pas és crear un projecte a (<https://console.firebase.google.com/u/0/?pli=1>).

També usarem Firebase Hosting per a allotjar la nostra app posteriorment, així com Cloud Functions per a usar com a servidor nodejs, Firebase Storage per allotjar imatges pujades pels usuaris, i Firebase RealTime Database per gestionar tokens.

Afegim Firebase a la nostra app:

`yarn add firebase`

També necessitarem el cli de Firebase al nostre sistema:

`npm install -g firebase-tools`

Configurarem les credencials de Firebase amb variables ambientals, de manera que els desenvolupadors només hauran d'omplir les dades del fitxer `.env`.

Per al _flow_ d'autenticació usarem la llibreria FirebaseUi:

`yarn add firebaseui`

## PWA

Afegim suport per a PWA.

`quasar mode add pwa`

Això crearà una carpeta `src-pwa` amb el codi font del _service worker_, i les icones necessàries a la carpeta `public`.

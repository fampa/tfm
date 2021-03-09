# Procés de treball/desenvolupament

## Disseny dels mockup

Hem dissenyat l'aplicació amb l'eina online [figma](https://www.figma.com/), enfocant-nos en el disseny per a mòbils ja que hem seguit un enfocament _mobile first_.

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

Creem els components que necessitarem:

- src/components/NewsCard.vue

Afegim support per a _GraphQl_ amb _Apollo client_.

`yarn add @vue/apollo-composable`

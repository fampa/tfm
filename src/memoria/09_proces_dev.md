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

Afegim support per a _GraphQl_ amb _Apollo client_.

`yarn add @vue/apollo-composable`

Afegim suport per a PWA.

`quasar mode add pwa`

Això crearà una carpeta `src-pwa` amb el codi fint del _service worker_.

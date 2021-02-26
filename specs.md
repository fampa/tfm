---
title: "Annexe 1. Document d'especificacions de la PWA de gestió de les AMPA"
author: 'Josep V. Monjo'
date: '24/02/2021'
lang: ca
numbersections: true
fontfamily: lmodern
linkcolor: blue
urlcolor: blue
header-includes: |
    \usepackage{fancyhdr}
    \pagestyle{fancy}
    \fancyhf{}
    \rhead{Annexe 1}
    \lhead{Josep V. Monjo}
    \cfoot{\thepage}
    \usepackage{setspace}
    \doublespacing
---

# Especificacions

- Disseny _responsive_
- Dos tipus d'usuari (administrador, afiliat)
- Multiidioma (català, castellà)

Un afiliat ha de poder:

- Donar-se d'alta amb correu electrònic
- Donar-se d'alta amb Google
- Validar el número de IBAN
- Editar les seues dades
- Inscriure's en activitats del AMPA

Un administrador ha de poder:

- Gestionar els continguts del blog
- Veure i editar el llistat d'afiliats
- Generar un fitxer de remesa bancària per a les domiciliacions
- Enviar notificacions push

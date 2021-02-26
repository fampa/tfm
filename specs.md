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

La base de dades ha d'arreplegar les següents dades:

- members (
    id text NOT NULL,
    firstname text,
    lastname text,
    email text NOT NULL,
    family_id integer,
    created_at timestamp with time zone DEFAULT now(),
    updated_at timestamp with time zone DEFAULT now(),
    isadmin boolean DEFAULT false
)
- children (
    id integer NOT NULL,
    firstname text,
    lastname text,
    birthyear integer,
    family_id integer,
    created_at timestamp with time zone DEFAULT now(),
    updated_at timestamp with time zone DEFAULT now()
)
- families (
    id integer NOT NULL,
    name text,
    created_at timestamp with time zone DEFAULT now(),
    updated_at timestamp with time zone DEFAULT now()
)

I, opcionalment, per poder gestionar el blog:

- articles (
    id integer NOT NULL,
    created_at timestamp with time zone DEFAULT now(),
    updated_at timestamp with time zone DEFAULT now(),
    status text DEFAULT 'DRAFT'::text NOT NULL,
    image text,
    author_id text
)

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

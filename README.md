# TFM

Treball Final del Màster en Desenvolupament d'Aplicacions i Llocs Web de la Universitat Oberta de Catalunya.

El present treball està redactat en [markdown](https://github.com/fampa/tfm/blob/main/TFM.md) i posteriorment generat en PDF amb [Pandoc](https://pandoc.org/).

A més d'instal·lar Pandoc:

`sudo apt-get install pandoc`

Cal instal·lar latex:

`sudo apt-get install texlive-latex-base`

I és recomanable també:

Fonts extra

`sudo apt-get install texlive-fonts-recommended`

`sudo apt-get install texlive-fonts-extra`

Paquets extra

`sudo apt-get install texlive-latex-extra`

Idiomes extra

`sudo apt-get install texlive-lang-spanish`

Per a footnotes:

`texlive-mdwtools`

Manipulació d'imatges i svg:

`sudo apt install librsvg2-bin`

Comando per a Fedora:

Es recomanen els binaris de [pandoc](https://github.com/jgm/pandoc/releases) i [pandoc-crossref](https://github.com/lierdakil/pandoc-crossref/releases/)

I les llibreries de latex

`sudo dnf install texlive librsvg2-tools texlive-mdwtools texlive-collection-langspanish texlive-framed`

També cal tenir en compte que el _output_ de pandoc necessita les següents opcions:

`-f markdown+implicit_figures *.md --standalone --highlight-style=zenburn --filter pandoc-crossref --citeproc`

El treball s'ha seqüenciat en diferents entregues (PAC) que figuren com a [releases](https://github.com/fampa/tfm/releases).

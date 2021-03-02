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

Gestió de la bibliografia

`sudo apt install pandoc-citeproc`

Per a footnotes:

`texlive-mdwtools`

També cal tenir en compte que el _output_ de pandoc necessita les següents opcions:

`-f markdown+implicit_figures --highlight-style=zenburn --filter pandoc-crossref --citeproc`

El treball s'ha seqüenciat en diferents entregues (PAC) que figuren com a [releases](https://github.com/fampa/tfm/releases).

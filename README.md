# PyryTex

<!-- Luotu 2022-09-06 -->

PyryTex on LaTeX-paketti, jonka tarkoitus on helpottaa yliopistomatikan tehtävien ratkomista.


## Asennus

**Huono ratkaisu:** Kopioi `pyry.sty` aina samaan kansioon `main.tex`:n kanssa. Toimii vain niissä kansioissa, joissa sty-tiedosto on.

**Parempi ratkaisu:** Aseta tiedosto `pyry.sty` paikkaan `~/Library/texmf/tex/latex/pyry/pyry.sty`. Toimii kaikkialla yhdellä kertaa.

Jos compiler valittaa, ettei jotain pakettia löydy, sen voi asentaa näin: `sudo tlmgr install PAKETTI`


## Käyttö

Paketin voi käyttää näin:

**main.tex**

```LaTeX
\documentclass{article}
\usepackage{pyry}
\title{Pääotsikko}
\date{Päivämäärä}
\author{Alaotsikko}
\begin{document}

\maketitle

\section*{Harjoitus 1}
\subfile{teht1}		% tiedoston nimi ilman .tex-päätettä

% ...

\end{document}
```

**teht1.tex**

```LaTeX
\documentclass[main.tex]{subfiles}
\begin{document}

% ...

\end{document}
```
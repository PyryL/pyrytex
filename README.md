# PyryTex

<!-- Created on 2022-09-06 -->

PyryTex is a LaTeX package which is intended to ease writing mathematical documents for university courses.


## Installation

### Debian

1. Create directory `/usr/share/texmf/tex/latex/pyrytex`.
2. Copy `pyry.sty` into that folder.
3. Run `texhash` to update caches.

### macOS

1. Place the file `pyry.sty` into `~/Library/texmf/tex/latex/pyry/pyry.sty`.
2. If your LaTeX compiler warns about missing packages, install them with command `sudo tlmgr install <PACKAGE>`

If you cannot follow the instructions above for some reason, you can also copy the `pyry.sty` file into every directory in which you want to use it. This is obviously a lot worse option.

## Usage

Below is an example of how you can use PyryTex.

**main.tex**

```LaTeX
\documentclass{article}
% \usepackage[finnish]{babel}
\usepackage{pyrytex}
\addbibresource{references.bib}
\title{Main title}
\author{Your name}
\date{Deadline date}
\begin{document}

\maketitle

\subfile{exercise1}

You \cite{EXMPL} can cite references like this.

% ...

\printbibliography

\end{document}
```

**exercise1.tex**

```LaTeX
\documentclass[main.tex]{subfiles}
\begin{document}

\section*{Exercise 1}
% ...

\end{document}
```

**references.bib**

Place your references here in BibTeX format.

```
@book{EXMPL,
	author = {John Doe},
	title = {Example title},
	publisher = {Publisher Inc.},
	isbn = {12349876},
	year = {2023}
}
```

# Some tricks

## Author Style
- Use the package authblk
- The code is

```latex
\usepackage{authblk}

\author[1]{Srijan R. Shetty \thanks{srijans@iitk.ac.in}}
\affil[1]{Department of Computer Science and Engineering, Indian Institute of Technology, Kanpur}
```

## The margins of the document
```latex
\topmargin -0.5in
\advance \topmargin by -\headheight
\advance \topmargin by -\headsep
\textheight 9.9in
\oddsidemargin 0pt
\evensidemargin \oddsidemargin
\marginparwidth 0.5in
\textwidth 6.5in

\parindent 0in
\parskip 1.5ex
```

## Color the document

```latex
\usepackage{color}
\textcolor{green}{SOme text}
```

## Hyperlinks

```latex
\usepackage[hidelinks,colorlinks]{hyperref}
```

## Code

```latex
\usepackage{listings}
\lstset{                                                                                                                                           
basicstyle=\footnotesize\sffamily\color{black},
commentstyle=\color{mygray},
frame=single,
numbers=left,
numbersep=10pt,
numberstyle=\tiny\color{mygray},
keywordstyle=\color{mygreen},
showspaces=false,
showstringspaces=false,
stringstyle=\color{myorange},
tabsize=2,
language=C++
}

\lstinputlisting{filname}
```

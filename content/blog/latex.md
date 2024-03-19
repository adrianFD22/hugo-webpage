+++
title = "Pijaditas de LaTeX"
date = "2024-03-19T21:59:03+01:00"

#
# description is optional
#
# description = "An optional description for SEO. If not provided, an automatically created summary will be used."

tags = []
+++

Recopilatorio personal de algunas cosas guays de LaTeX, algunas de ellas útiles.

- Quitar la barra inferior de navegación inútil del beamer.
```tex
\setbeamertemplate{navigation symbols}{}
```

- Hacer que la l se reemplace por \ell en modo matemático.
```tex
\mathcode`l="8000
\begingroup
\makeatletter
\lccode`\~=`\l
\DeclareMathSymbol{\lsb@l}{\mathalpha}{letters}{`l}
\lowercase{\gdef~{\ifnum\the\mathgroup=\m@ne \ell \else \lsb@l \fi}}%
\endgroup
```

- Comentar: hay varias formas de hacerlo. Una opción es usar el package comment, pero este no se comporta muy allá con beamer. También se puede usar el environment comment de verbatim. Otra alternativa sin dependencias extrañas y sin que se rompa nada es:
```tex
\newcommand{\comment}[1]{}
...

\comment{
    This is a comment.
}
```

- ¡Si escribes algo después del \end{document} será ignorado por el compilador! Esto es bastante inútil pero no deja de ser una forma graciosa para comentar texto o esconder texto (esteganografía).

- El package rotating para rotar cosas.

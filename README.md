# template-contest
LaTeX Template para creación de _statements_ para competencias de programación organizadas por Programación Competitiva UChile.

## Tabla de contenidos

* [Ambiente problem](#ambiente-problem)
* [Ambiente problemexamples](#ambiente-problemexamples)
* [Macros](#macros)
* [Estructura de archivos](#estructura-de-archivos)
* [Ejemplo](#ejemplo)
* [TODO](#todo)

## Ambiente problem
El ambiente _problem_ recibe dos parámetros:
```latex
\begin{problem}{time-limit}{memory-limit}

\end{problem}
```

## Ambiente problemexamples
El ambiente _problemexamples_ es usado para colocar casos de prueba de ejemplo. Dentro de él, se usa el comando `\testcase{i}` para hacer input de el caso de prueba número `i`. Este macro buscará los archivos `testcases/X/i.in` y `testcases/X/i.out`, donde `X` es la letra del problema en el que se usa.

## Macros
- `\probleminputformat`: Crea una subsección para la descripción del input
- `\problemoutputformat`: Crea una subsección para la descripción del output
- `\testcase` para colocar un caso de prueba en el ambiente `problemexamples`. Recibe como parámetro el número del caso de prueba.

## Estructura de archivos
```bash
.
├── README.md
├── config.tex
├── logo.png
├── main.tex
├── preamble.sty
├── testcases
│   ├── A
│   │   ├── 1.in
│   │   ├── 1.out
│   │   ├── 2.in
│   │   └── 2.out
│   ├── B
│   ├── C
│   ├── D
│   ├── E
│   ├── F
│   ├── G
│   ├── H
│   ├── I
│   ├── J
│   ├── K
│   ├── L
│   └── M
└── tree
```

## Ejemplo
```latex
\begin{problem}{Problema de ejemplo}{2}{64}
    Primer párrafo del problema de ejemplo.

    Segundo párrafo del problema de ejemplo.
\probleminputformat
    La primer línea contiene el número $n$ ($1 \leq n \leq 10^6$).
\problemoutputformat
    Imprime \texttt{SI} si $n$ es par, e imprime \texttt{NO} en el caso contrario.
    
    \begin{problemexamples}
        \testcase{1}
        \testcase{2}
    \end{problemexamples}
\end{problem}
```
Nótese que deben existir los archivos `testcases/A/1.in`, `testcases/A/1.out`, `testcases/A/2.in` y `testcases/A/2.out`, asumiendo que es el problema A.

Este ejemplo es el que se encuentra en el `main.tex` por defecto.

## TODO
* Automatizar ambiente problemexamples (input automático de archivos existentes dentro del directorio del problema)
# contest-template
LaTeX Template para creación de _statements_ para competencias de programación organizadas por Programación Competitiva UChile.

## Tabla de contenidos

* [Ambiente problem](#ambiente-problem)
* [Macros](#macros)
* [Estructura de archivos](#estructura-de-archivos)
* [Ejemplo](#ejemplo)

## Ambiente problem
El ambiente _problem_ recibe dos parámetros:
```latex
\begin{problem}{problem title}{time limit}{memory limit}

\end{problem}
```

## Macros
- `\probleminputformat`: Crea una subsección para la descripción del input
- `\problemoutputformat`: Crea una subsección para la descripción del output
- `\problemexample` Crea la subsección de ejemplos y automaticamente crea una tabla de los testcases (ver [Estructura de archivos](#estructura-de-archivos))

## Estructura de archivos
```bash
.
├── README.md
├── config.tex
├── logo.png
├── main.tex
├── preamble.sty
└── testcases
    ├── A
    │   ├── 1in.txt
    │   ├── 1out.txt
    │   ├── 2in.txt
    │   └── 2out.txt
    ├── B
    ├── C
    ├── D
    ├── E
    ├── F
    .
    .
    .
```
- `config.tex` posee algunas configuraciones básicas del documento.
- `logo.png` es el logo a usar en el template.
- `main.tex` es el archivo principal, donde se tipean los problemas.
- `preamble.sty` es el cuerpo del template.
- En `testcases` se crea un subdirectorio para cada problema. Estos deben tener de nombre una letra mayúscula. Dentro de cada uno de estos, se crean los archivos `ink.txt` e `outk.txt` para cada caso de prueba k que se usará de ejemplo.


## Ejemplo
```latex
\begin{problem}{Problema de ejemplo}{2}{64}
    Primer párrafo del problema de ejemplo.

    Segundo párrafo del problema de ejemplo.
\probleminputformat
    La primer línea contiene el número $n$ ($1 \leq n \leq 10^6$).
\problemoutputformat
    Imprime \texttt{SI} si $n$ es par, e imprime \texttt{NO} en el caso contrario.
\problemexample

\end{problem}
```
Nótese que deben existir, por lo menos, los archivos `testcases/A/in1.txt`, `testcases/A/out1.txt`, asumiendo que es el problema A, sino la tabla aparecerá en blanco

Este ejemplo es el que se encuentra en el `main.tex` por defecto.

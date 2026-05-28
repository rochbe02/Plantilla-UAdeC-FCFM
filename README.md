# Plantilla Beamer — FCFM UAdeC

Tema de [Beamer](https://ctan.org/pkg/beamer) **no oficial** para presentaciones de la Facultad de Ciencias Físico-Matemáticas (FCFM) de la Universidad Autónoma de Coahuila (UAdeC).

Incluye una portada de diseño hecha con TikZ, paleta de colores institucional, tipografía Montserrat, bloques personalizados, resaltado de código con `listings` y bibliografía a juego con el tema.

> **Nota:** Esta es una plantilla creada de forma independiente. No es un producto oficial de la UAdeC ni de la FCFM.

## Vista previa

<!-- Reemplaza esta línea con una captura de tu presentación -->
![Vista previa de la plantilla](img/preview.png)

## Características

- Formato panorámico 16:9 (`aspectratio=169`).
- Portada personalizada con banda superior y elementos decorativos en TikZ.
- Paleta de colores institucional configurable.
- Tipografía Montserrat.
- Bloques `block`, `alertblock` y `exampleblock` con estilo propio.
- Estilo de código `listings` con soporte para acentos y la ñ.
- Estilo de bibliografía coordinado con los colores del tema.
- Logos de universidad y facultad configurables mediante comandos.

## Requisitos

- Una distribución de LaTeX reciente (TeX Live, MiKTeX) o una cuenta de [Overleaf](https://www.overleaf.com).
- Compilar con **pdfLaTeX**.
- Usar **Biber** como motor de bibliografía (solo si utilizas `biblatex`).
- Paquetes: `beamer`, `montserrat`, `tikz`, `listings`, `biblatex` (todos incluidos en TeX Live y Overleaf).

## Instalación

1. Descarga o clona este repositorio:
   ```bash
   git clone https://github.com/rochbe02/Plantilla-UAdeC-FCFM.git
   ```
2. Copia `beamerthemeFCFM.sty` a la raíz de tu proyecto (al mismo nivel que tu archivo `.tex`).
3. Coloca los logos en una carpeta `img/`:
   - `img/FCFM` — logo de la facultad.
   - `img/UAdeC` — logo de la universidad.

En Overleaf basta con subir el `.sty`, las imágenes y tu `.tex` al proyecto.

## Uso básico

```latex
\documentclass[aspectratio=169]{beamer}
\usepackage[utf8]{inputenc}
\usetheme{FCFM}

\title[Título corto]{Título de la presentación}
\subtitle{Subtítulo}
\date{\today}
\author[Autor corto]{Nombre del Autor}
\institute[UAdeC]{Universidad Autónoma de Coahuila}

\begin{document}

\begin{frame}
    \titlepage
\end{frame}

\begin{frame}{Mi primera diapositiva}
    Contenido aquí.
\end{frame}

\end{document}
```

### Código fuente

Los frames con código necesitan la opción `[fragile]`:

```latex
\begin{frame}[fragile]{Ejemplo}
\begin{lstlisting}[language=Python]
def saludo():
    print("Hola, mundo")
\end{lstlisting}
\end{frame}
```

### Bibliografía

En el preámbulo:

```latex
\usepackage[backend=biber, style=numeric, sortcites]{biblatex}
\addbibresource{referencias.bib}
```

Al final del documento:

```latex
\begin{frame}[allowframebreaks]{Referencias}
    \printbibliography
\end{frame}
```

## Personalización

### Cambiar los logos

```latex
\setlogofacultad{ruta/a/logo-facultad}
\setlogouniversidad{ruta/a/logo-universidad}
```

### Cambiar los colores

Edita las definiciones de color en `beamerthemeFCFM.sty`:

```latex
\definecolor{facPrimario}{RGB}{50, 81, 172}
\definecolor{facSecundario}{RGB}{191, 155, 76}
\definecolor{facClaro}{RGB}{140, 156, 156}
\definecolor{facTexto}{RGB}{30, 30, 30}
```

## Estructura de archivos

```
.
├── beamerthemeFCFM.sty   # El tema
├── PlantillaPresentación.tex              # Documento de ejemplo
├── referencias.bib       # Bibliografía de ejemplo
└── img/
    ├── FCFM.png          # Logo de la facultad
    └── UAdeC.png         # Logo de la universidad
```

## Licencia

El código de esta plantilla se distribuye bajo la licencia [MIT](LICENSE).

Esta licencia cubre **únicamente** el código del tema. **No** se extiende a:

- Los **logos** de la UAdeC y la FCFM, que son marca registrada de la institución y deben usarse conforme a sus normas de identidad gráfica.
- La fuente **Montserrat**, distribuida bajo la [SIL Open Font License](https://openfontlicense.org/).

## Créditos

Plantilla desarrollada por Roberto Chávez Berlanga.

Las contribuciones son bienvenidas mediante *issues* y *pull requests*.

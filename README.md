# SOC9035 - Análisis Avanzado de Datos II

Repositorio del sitio web del curso **SOC9035 - Análisis Avanzado de Datos II**,
dictado por Gabriel Sotomayor en la Universidad Diego Portales durante el primer
semestre de 2026.

El sitio está construido con [Quarto](https://quarto.org/) y organiza clases
expositivas, talleres aplicados, datos y materiales de apoyo para un curso de
análisis multivariante aplicado a ciencias sociales. El foco del curso está en
la preparación de datos, el análisis reproducible en R y la interpretación de
modelos estadísticos usados en investigación social.

## Contenidos del Curso

El curso combina fundamentos metodológicos, trabajo computacional y lectura
crítica de resultados. Los principales ejes son:

- Investigación reproducible, ciencia abierta, proyectos en R y documentos Quarto.
- Gestión, limpieza y visualización de datos sociales.
- Análisis de encuestas complejas con ponderadores, estratos y conglomerados.
- Regresión lineal múltiple e inferencia con diseños muestrales complejos.
- Análisis Factorial Exploratorio (AFE): preparación, supuestos, extracción,
  rotación e interpretación.
- Análisis Factorial Confirmatorio (AFC) con `{lavaan}`, incluyendo ajuste
  global, ajuste local, residuos de correlación e índices de modificación.
- Tratamiento de variables ordinales/categóricas, correlaciones policóricas y
  estimadores como WLSMV/DWLS.
- Análisis de Senderos y descomposición de efectos directos, indirectos y totales.
- Modelos de Ecuaciones Estructurales (SEM), integrando modelo de medición y
  modelo estructural.

## Materiales Disponibles

Los materiales del año 2026 están en `2026/`. La carpeta `2026/weeks/` contiene
las semanas disponibles a la fecha:

| Semana | Tema principal |
|:---|:---|
| `week00` | Nivelación en R |
| `week01` | Introducción al curso, gestión de datos y visualización |
| `week02` | Investigación reproducible y ciencia abierta |
| `week03` | Fundamentos de diseños muestrales complejos |
| `week04` | Análisis de encuestas complejas con `{srvyr}` |
| `week05` | Modelos multivariados y regresión lineal múltiple |
| `week06` | AFE I: preparación y supuestos |
| `week07` | AFE II: extracción, rotación e interpretación |
| `week08` | AFC con `{lavaan}` y datos complejos |
| `week09` | Análisis de Senderos I |
| `week10` | Análisis de Senderos II |
| `week11` | Modelos de Ecuaciones Estructurales (SEM) |

Cada semana puede incluir:

- `page.qmd`: página de entrada de la semana.
- `slides.qmd`: presentación Quarto/revealjs.
- `lab.qmd` o `lab2.qmd`: taller aplicado.
- `img/` u otros recursos locales cuando corresponde.

## Estructura del Repositorio

```text
aadii/
|-- 2026/
|   |-- index.qmd          # Página de inicio del curso 2026
|   |-- syllabus.qmd       # Programa del curso
|   |-- ai-policy.qmd      # Política de uso de IA
|   |-- data/              # Datos usados en talleres
|   `-- weeks/             # Materiales organizados por semana
|-- css/
|   |-- custom.scss        # Estilos del sitio HTML
|   `-- slides.scss        # Estilos de presentaciones revealjs
|-- figures/               # Imágenes generales del sitio
|-- helpers/               # Fragmentos HTML reutilizables
|-- references/            # Bibliografía y CSL
|-- renv/                  # Configuración de entorno R reproducible
|-- _quarto.yml            # Configuración principal del sitio
|-- renv.lock              # Versiones de paquetes R
`-- README.md
```

## Desarrollo Local

### Requisitos

- [R](https://www.r-project.org/) 4.5.x, consistente con el workflow de GitHub
  Actions.
- [Quarto](https://quarto.org/docs/get-started/).
- Paquete R `{renv}`.

### Restaurar dependencias

```r
install.packages("renv")
renv::restore()
```

### Previsualizar el sitio

```bash
quarto preview . --render all --no-browser
```

### Renderizar el sitio completo

```bash
quarto render
```

El resultado se escribe en `_output/`, según la configuración de `_quarto.yml`.

### Renderizar una clase específica

```bash
quarto render 2026/weeks/week10/slides.qmd
quarto render 2026/weeks/week10/lab.qmd
```

### Agregar paquetes R

```r
install.packages("nombre_paquete")
renv::snapshot()
```

## Publicación

El sitio se publica en GitHub Pages mediante el workflow
`.github/workflows/publish.yml`. El workflow:

1. instala Quarto y R,
2. restaura dependencias con `renv`,
3. ejecuta `quarto render`,
4. sube `_output/` como artefacto de Pages.

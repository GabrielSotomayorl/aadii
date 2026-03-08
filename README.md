# SOC9035 · Análisis Avanzado de Datos II

Repositorio del sitio web del curso **SOC9035 — Análisis Avanzado de Datos II** de la [Universidad Diego Portales](https://www.udp.cl/), dictado por Gabriel Sotomayor.

El sitio está construido con [Quarto](https://quarto.org/) e incluye clases expositivas (revealjs), talleres prácticos y materiales de apoyo organizados por semana.

---

## Estructura del repositorio

```
aadii/
├── 2026/
│   ├── index.qmd              # Página de inicio del curso
│   └── weeks/
│       ├── week00/            # Semana 00: Nivelación
│       ├── week01/            # Semana 01
│       ├── week02/            # Semana 02
│       │   ├── page.qmd       # Página de la semana
│       │   ├── slides.qmd     # Presentación revealjs
│       │   ├── lab.qmd        # Taller práctico
│       │   ├── IPO-R/         # Proyecto ejemplo reproducible
│       │   └── IPO-R.zip      # Descargable para estudiantes
│       └── ...
├── _quarto.yml                # Configuración del sitio
├── custom.scss                # Estilos del curso
└── renv.lock                  # Dependencias R
```

---

## Desarrollo local

### Requisitos

- [R](https://www.r-project.org/) ≥ 4.2
- [Quarto](https://quarto.org/docs/get-started/) ≥ 1.4
- Paquete `renv`

### Setup

```r
install.packages("renv")
renv::restore()   # instala todos los paquetes del proyecto
```

### Previsualizar el sitio

```bash
quarto preview . --render all --no-browser
```

### Agregar un paquete R nuevo

```r
install.packages("nombre-paquete")
renv::snapshot()   # actualiza renv.lock
```

---

## Publicación

El sitio se publica automáticamente en GitHub Pages mediante GitHub Actions al hacer push a `main`. La configuración está en `.github/workflows/publish.yml`.

# ISR401-PFC-ERS-EquipoB

**Repositorio para la práctica experimental de la unidad 4**

## Sistema del PFC

**MundiPets** — plataforma para fomentar la cruza responsable de mascotas, facilitar la
gestión de adopciones y fortalecer la interacción entre propietarios, adoptantes, médicos
veterinarios y refugios de animales.

- **Titular del PFC:** Andy Johel Mendoza Párraga
- **Tablero CASE (Jira):** [https://mundipetspe4.atlassian.net/jira/software/projects/KAN/summary](https://mundipetspe4.atlassian.net/jira/software/projects/KAN/summary)

## Integrantes y roles (PE4 — Inspección Fagan y CCB)

| Integrante | CI | Correo | Rol en la inspección | Rol en el CCB |
|---|---|---|---|---|
| Cedeño Avila Winston Damian | 0942833492 | [wcedenoa2@uteq.edu.ec](mailto:wcedenoa2@uteq.edu.ec) | Inspector 1 | Analista de requisitos |
| Cordova Carreño Mayra Lucila | 0750286775 | [mcordovac2@uteq.edu.ec](mailto:mcordovac2@uteq.edu.ec) | Inspector 2 | Representante del cliente / Desarrolladora |
| Mendoza Párraga Andy Johel | 1251401590 | [amendozap9@uteq.edu.ec](mailto:amendozap9@uteq.edu.ec) | Moderador y Lector | Presidente del CCB |

> **Nota sobre roles:** debido a que el equipo está conformado por 3 integrantes, Andy
> Mendoza asume dos roles (Moderador y Lector) durante la reunión de inspección, mientras
> que Winston Cedeño y Mayra Cordova actúan como Inspector 1 e Inspector 2,
> respectivamente. Esta asignación queda registrada también en el Anexo A (listas de
> verificación individuales) y en el acta de la reunión de inspección.

## Estructura del repositorio

```text
ISR401-PFC-ERS-EquipoB/
│   README.md
│   CHANGELOG.md
│
├───01_ERS/                        ERS/SRS versionado del PFC
│   │   ERS_SRS_2A_v1.0.pdf
│   │   ERS_SRS_2A_v1.1.pdf
│   │
│   └───fuentes_tex/
│       ├───ERS_SRS_2A_v1.0/
│       │   │   ERS_SRS_2A_v1.0.tex
│       │   │   referencias.bib
│       │   │   .gitignore
│       │   └───figuras/           diagramas UML, mockups y capturas del ERS
│       │
│       └───ERS_SRS_2A_v1.1/       fuentes de la versión corregida (post-CCB)
│           │   ERS_SRS_2A_v1_1.tex
│           │   referencias.bib
│           └───figuras/
│
├───02_Inspeccion/                 Inspección formal Fagan (PE4)
│   │   AnexoB_registro_defectos.xlsx
│   │   metricas.xlsx
│   │   Planificacion_Roles_Inspeccion.pdf
│   │
│   └───AnexoA_checklists/         listas de verificación firmadas, una por inspector
│
├───03_CCB/                        Gestión del cambio (PE4)
│       RFC-01.pdf
│       RFC-02.pdf
│       RFC-03.pdf
│       Acta_CCB.pdf
│
├───04_Trazabilidad/               Trazabilidad en herramienta CASE (PE4)
│   │   matriz_trazabilidad.xlsx
│   │   backlog_export.csv
│   │
│   └───capturas/                  tablero, issues, panel de estadísticas (Jira)
│
├───05_Informe/                    Informe LaTeX de la PE4
│   │   PE4_U4_CEDENOAVILA_CORDOVA_MENDOZAPARRAGA.tex
│   │   referencias.bib
│   │   PE4_U4_CEDENOAVILA_CORDOVA_MENDOZAPARRAGA.pdf
│   │
│   └───figuras/
│
├───06_Evidencias/                 Evidencia de baseline y de la sesión
│   ├───capturas_git/              git log --oneline --graph --decorate, git tag -n,
│   │                              vista de commits en GitHub
│   │
│   ├───fotos_sesion/              evidencia de la reunión de inspección y del CCB
│   │                              vista de commits en GitHub
│   │
│   └───declaracion_IA.pdf         declaración de uso de IA, firmada por los 3 integrantes
│
└───07_Borradores/                 Carpeta de trabajo interno (NO evaluable)
    ├───CedenoAvila/
    ├───CordovaCarreno/
    └───MendozaParraga/
```

> **`07_Borradores/`** es una carpeta de trabajo interno, no forma parte de la estructura
> oficial exigida por la guía de la PE4. Se usa para que cada integrante suba sus avances
> individuales.

## Instrucciones de compilación

El informe y el ERS se compilan con **LaTeX (distribución MiKTeX o TeX Live)** usando
`pdflatex` + `biber` para la bibliografía en formato IEEE (paquete `biblatex`).

### Requisitos previos

- Distribución LaTeX completa: [MiKTeX](https://miktex.org/) o [TeX Live](https://www.tug.org/texlive/)
- `biber` (incluido en ambas distribuciones; verificar con `biber --version`)
- Paquetes: `IEEEtran`, `babel` (spanish), `csquotes`, `booktabs`, `tabularx`, `array`,
  `multirow`, `longtable`, `graphicx`, `float`, `xcolor`, `geometry`, `fancyhdr`,
  `parskip`, `enumitem`, `caption`, `titlesec`, `amsmath`, `amssymb`, `biblatex`
  (backend biber, estilo ieee), `hyperref`

### Compilar el ERS (`01_ERS/`)

```bash
cd 01_ERS/fuentes_tex/ERS_SRS_2A_v1.0
pdflatex ERS_SRS_2A_v1.0.tex
biber ERS_SRS_2A_v1.0
pdflatex ERS_SRS_2A_v1.0.tex
pdflatex ERS_SRS_2A_v1.0.tex
```

### Compilar el informe de la PE4 (`05_Informe/`)

```bash
cd 05_Informe
pdflatex PE4_U4_CEDENOAVILA_CORDOVA_MENDOZAPARRAGA.tex
biber PE4_U4_CEDENOAVILA_CORDOVA_MENDOZAPARRAGA
pdflatex PE4_U4_CEDENOAVILA_CORDOVA_MENDOZAPARRAGA.tex
pdflatex PE4_U4_CEDENOAVILA_CORDOVA_MENDOZAPARRAGA.tex
```

> Se ejecuta `pdflatex` dos veces después de `biber` para resolver correctamente las
> referencias cruzadas, el índice y la bibliografía. El archivo principal en ambos casos
> es el `.tex` de primer nivel indicado arriba; las figuras deben estar en la subcarpeta
> `figuras/` relativa a cada archivo `.tex`.

### Compilación alternativa (VS Code)

Con la extensión **LaTeX Workshop** y el backend `biber` configurado, basta con abrir el
`.tex` principal y ejecutar la receta por defecto (`pdflatex ➞ biber ➞ pdflatex ➞ pdflatex`).

## Convenciones de commits

Se usan mensajes semánticos, por ejemplo:

```text
docs(ers): v1.1 - acotar RNF-02, agregar criterio de verificacion a las RD y corregir matriz de trazabilidad (40->59 filas)
docs(pe4): completar seccion 4 - correcciones aplicadas a defectos criticos y mayores
docs(ccb): agregar formularios RFC y acta del CCB firmados
docs(inspeccion): consolidar Anexo B - 18 defectos detectados en reunion
```

## Línea base (baseline)

La versión aprobada por el CCB quedó marcada con un tag anotado publicado:

```bash
git tag -a baseline-v1.1 -m "Baseline aprobada por CCB"
git push origin baseline-v1.1
```

Evidencia del historial completo (`git log --oneline --graph --decorate` y `git tag -n`)
disponible en `06_Evidencias/capturas_git/` y en la Sección 7 / Anexo E del informe.

Ver detalle de versiones en [`CHANGELOG.md`](./CHANGELOG.md).

## Declaración de uso de Inteligencia Artificial

Ver [`declaracion_IA.pdf`](./06_Evidencias/declaracion_IA.pdf), firmada por los tres integrantes, con el
detalle de las tareas en las que se empleó asistencia de IA y la verificación crítica
realizada por el equipo sobre cada resultado incluido en el informe.

## Docente

Ing. Guerrero Ulloa Gleiston Cicerón — Ingeniería de Requerimientos, UTEQ,
2026-2027 PPA.
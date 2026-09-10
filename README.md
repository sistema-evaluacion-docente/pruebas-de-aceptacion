# Pruebas de Aceptación

Evidencia de la ejecución de las **pruebas de aceptación end-to-end** (Cypress) del sistema de evaluaciones docente. El repositorio no contiene el código de las pruebas, sino sus **resultados**: un reporte HTML navegable y las grabaciones en video de cada ejecución, usados como evidencia.

## Contenido

- **`index.html`** — Reporte generado con [Mochawesome](https://github.com/adamgruber/mochawesome) a partir de la corrida de Cypress. Es autocontenido (estilos y datos embebidos): basta abrirlo en un navegador para explorarlo, sin necesidad de servidor.
- **`videos/`** — Grabación en `.mp4` de cada spec de Cypress, organizada por módulo. El reporte (`index.html`) enlaza cada prueba con su video correspondiente.

```
videos/
├── admin/         # Gestión administrativa (facultades, programas, departamentos, usuarios...)
├── auth/          # Autenticación y sesión
├── evaluations/   # Carga y análisis de evaluaciones docentes
└── security/      # Control de acceso y aislamiento de datos entre departamentos
```

## Resultado de la última corrida

| Suites | Tests | Aprobados | Fallidos | Duración |
|---|---|---|---|---|
| 24 | 94 | 94 (100%) | 0 | ~5 min |

## Módulos cubiertos

- **`admin/`** — CRUD de facultades, programas, departamentos, grupos académicos, directores, usuarios y consulta del historial de auditoría.
- **`auth/`** — Inicio de sesión, selección de rol y manejo del token de sesión (expirado, ausente, renovación).
- **`evaluations/`** — Carga de evaluaciones (y sus distintas modalidades), extracción y descarga de PDF, estado de procesamiento, análisis con IA, clasificación y visualización de comentarios, alertas, y renombrado de cursos.
- **`security/`** — Control de acceso por rol, aislamiento de información entre departamentos y restricciones de acceso a evaluaciones ajenas.

## Cómo consultar la evidencia

1. Abre `index.html` en cualquier navegador o en [https://pruebas-de-aceptacion.netlify.app/](https://pruebas-de-aceptacion.netlify.app/).
2. Filtra o navega por suite/spec en el panel del reporte.
3. Al expandir una prueba, el reporte muestra el paso a paso ejecutado y un enlace al video (`videos/<módulo>/<spec>.cy.ts.mp4`) con la grabación de esa corrida.

# Guía de contribución — PeaceApp

Este repositorio contiene el **Informe de Trabajo Final** del curso *1ASI0548 - Agile Software Factories* (NRC 17433) y, progresivamente, los artefactos del producto **PeaceApp**.

## Estrategia de ramas

| Rama | Propósito |
| :--- | :--- |
| `main` | Solo versiones entregables y etiquetadas. Protegida. |
| `develop` | Integración del trabajo en curso. Protegida. |
| `feature/<ID>-<slug>` | Una rama por User Story o Technical Story. Nace de `develop`. |
| `docs/<slug>` | Cambios exclusivos de documentación e informe. Nace de `develop`. |
| `hotfix/<slug>` | Corrección urgente sobre una versión entregada. Nace de `main`. |

Nadie hace push directo a `main` ni a `develop`. Toda integración pasa por Pull Request con al menos una revisión aprobada.

## Convención de commits

Se aplica [Conventional Commits](https://www.conventionalcommits.org/):

```
<tipo>(<alcance>): <descripción en imperativo>

[cuerpo opcional]

Refs: #<número de issue>
```

Tipos permitidos: `feat`, `fix`, `docs`, `test`, `refactor`, `chore`, `ci`.

**Regla del equipo:** un commit por cada sección o título completado. No se hace un único commit grande por capítulo.

Ejemplos:

```
docs(capitulo-1): agregar To-Be Scenario Mapping
docs(backlog): estimar y priorizar el Product Backlog inicial
feat(incident): registrar reporte con ubicación y evidencia
```

## Flujo de trabajo

1. Toma un work-item del tablero y muévelo a *In Progress*.
2. Crea tu rama desde `develop`: `git checkout -b feature/US-06-registro-rapido-incidente develop`.
3. Trabaja con commits pequeños, uno por sección o unidad terminada.
4. Abre un Pull Request hacia `develop` enlazando el Issue.
5. Espera al menos una aprobación y a que todos los *checks* estén en verde.
6. Integra y elimina la rama.

## Definition of Done

Ver la sección **1.4.3** del `README.md`.

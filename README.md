<p align="center">
  <img src="assets/upc-logo.png" alt="Logo UPC" width="120">
</p>

<h1 align="center">Universidad Peruana de Ciencias Aplicadas</h1>

<p align="center">
  <b>Facultad de Ingeniería</b><br>
  <b>Carrera de Ingeniería de Software</b>
</p>

<h3 align="center">Informe de Trabajo Final</h3>

<div align="center">

<br>

**Ciclo:** 2026-20

**Curso:** 1ASI0548 - Agile Software Factories

**NRC:** 17433

**Profesor:** Vásquez Medina, José Luis

<br>

**Startup:** PeaceApp

**Producto:** PeaceApp

<br>

**Integrantes:**

| Código | Apellidos y Nombres |
| :---: | :--- |
| `[Código 1]` | `[Apellidos, Nombres 1]` |
| `[Código 2]` | `[Apellidos, Nombres 2]` |
| `[Código 3]` | `[Apellidos, Nombres 3]` |
| `[Código 4]` | `[Apellidos, Nombres 4]` |
| `[Código 5]` | `[Apellidos, Nombres 5]` |
| `[Código 6]` | `[Apellidos, Nombres 6]` |
| `[Código 7]` | `[Apellidos, Nombres 7]` |
| `[Código 8]` | `[Apellidos, Nombres 8]` |

<br>

**Septiembre, 2026**

</div>

---

# Registro de Versiones del Informe

| Versión | Fecha | Autor | Descripción de la modificación |
| :---: | :---: | :--- | :--- |
| 1.0 | 12/09/2026 | Equipo PeaceApp | Primer Avance (Semana 03): descripción del producto, problema y necesidad, Product Vision, objetivos, alcance inicial, As-Is, To-Be, User Stories iniciales, Product Backlog inicial, estrategia Agile, organización del equipo, estrategia inicial de Software Factory y herramientas seleccionadas. |
| 1.1 | `[DD/MM/YYYY]` | `[Autor]` | `[Segundo Avance]` |
| 1.2 | `[DD/MM/YYYY]` | `[Autor]` | `[Trabajo Parcial - TB2]` |
| 1.3 | `[DD/MM/YYYY]` | `[Autor]` | `[Trabajo Final - TB4]` |

---

# Project Report Collaboration Insights

**Repositorio del informe:** `[URL del repositorio]`

**Estrategia de colaboración:** el informe se versiona en GitHub bajo el flujo **GitFlow simplificado** definido en la sección 1.6.3. La rama `main` contiene únicamente las versiones entregables del informe; la rama `develop` integra el trabajo en curso, y cada integrante trabaja sobre una rama `feature/<seccion>` que se integra vía Pull Request con revisión de al menos un compañero.

**Convención de commits:** se aplica *Conventional Commits*, con un commit por cada sección o título completado (no un commit único por capítulo), de modo que la trazabilidad del aporte individual sea verificable en el historial.

| Entrega | Estado | Evidencia |
| :--- | :---: | :--- |
| Primer Avance - Semana 03 | Completado | Commits e historial de la rama `develop` integrados a `main` vía Pull Request. |
| Segundo Avance | Pendiente | `[Por completar]` |
| Trabajo Parcial (TB2) | Pendiente | `[Por completar]` |
| Trabajo Final (TB4) | Pendiente | `[Por completar]` |

---

# Tabla de contenidos

- [Registro de Versiones del Informe](#registro-de-versiones-del-informe)
- [Project Report Collaboration Insights](#project-report-collaboration-insights)
- [Tabla de contenidos](#tabla-de-contenidos)
- [Student Outcome](#student-outcome)
- [Perfiles de los Integrantes del Equipo](#perfiles-de-los-integrantes-del-equipo)
- [Capítulo I: Product \& Agile Foundation](#capítulo-i-product--agile-foundation)
  - [1.1. Descripción del producto](#11-descripción-del-producto)
    - [1.1.1. Nombre del producto](#111-nombre-del-producto)
    - [1.1.2. Problema y necesidad](#112-problema-y-necesidad)
    - [1.1.3. Usuarios objetivo](#113-usuarios-objetivo)
    - [1.1.4. Propuesta de solución](#114-propuesta-de-solución)
    - [1.1.5. Objetivos del producto](#115-objetivos-del-producto)
    - [1.1.6. Alcance inicial](#116-alcance-inicial)
    - [1.1.7. Restricciones](#117-restricciones)
  - [1.2. Product Vision](#12-product-vision)
  - [1.3. Requirements Specification](#13-requirements-specification)
    - [1.3.1. As-Is Scenario Mapping](#131-as-is-scenario-mapping)
    - [1.3.2. To-Be Scenario Mapping](#132-to-be-scenario-mapping)
    - [1.3.3. Epics](#133-epics)
    - [1.3.4. User Stories](#134-user-stories)
    - [1.3.5. Product Backlog inicial](#135-product-backlog-inicial)
  - [1.4. Estrategia Agile](#14-estrategia-agile)
    - [1.4.1. Marco de trabajo seleccionado](#141-marco-de-trabajo-seleccionado)
    - [1.4.2. Cadencia y ceremonias](#142-cadencia-y-ceremonias)
    - [1.4.3. Definition of Ready y Definition of Done](#143-definition-of-ready-y-definition-of-done)
    - [1.4.4. Estimación y priorización](#144-estimación-y-priorización)
    - [1.4.5. Métricas de proceso](#145-métricas-de-proceso)
  - [1.5. Organización del equipo](#15-organización-del-equipo)
    - [1.5.1. Roles y responsabilidades](#151-roles-y-responsabilidades)
    - [1.5.2. Matriz RACI](#152-matriz-raci)
    - [1.5.3. Canales de comunicación](#153-canales-de-comunicación)
  - [1.6. Estrategia inicial de Software Factory](#16-estrategia-inicial-de-software-factory)
    - [1.6.1. Flujo Plan → Code → Build → Test → Release → Deploy → Operate](#161-flujo-plan--code--build--test--release--deploy--operate)
    - [1.6.2. Herramientas seleccionadas](#162-herramientas-seleccionadas)
    - [1.6.3. Source Code Management y estrategia de ramas](#163-source-code-management-y-estrategia-de-ramas)
    - [1.6.4. Arquitectura objetivo y candidatos a microservicios](#164-arquitectura-objetivo-y-candidatos-a-microservicios)
    - [1.6.5. Prácticas de seguridad iniciales (DevSecOps)](#165-prácticas-de-seguridad-iniciales-devsecops)
- [Conclusiones y recomendaciones](#conclusiones-y-recomendaciones)
- [Bibliografía](#bibliografía)
- [Anexos](#anexos)

---

# Student Outcome

El curso **1ASI0548 - Agile Software Factories** contribuye al desarrollo del siguiente *Student Outcome* de ABET:

> **ABET - EAC - Student Outcome 5:** *La capacidad de funcionar efectivamente en un equipo cuyos miembros juntos proporcionan liderazgo, crean un entorno de colaboración e inclusión, establecen metas, planifican tareas y cumplen objetivos.*

| Criterio específico | Acciones realizadas | Conclusiones |
| :--- | :--- | :--- |
| **5.1.** Reconoce la contribución individual dentro de un equipo. | `[Apellidos, Nombres 1]`<br>`[Describir las acciones realizadas por el integrante durante el Primer Avance.]` | `[Conclusión individual del integrante 1.]` |
| | `[Apellidos, Nombres 2]`<br>`[Describir las acciones realizadas por el integrante durante el Primer Avance.]` | `[Conclusión individual del integrante 2.]` |
| | `[Apellidos, Nombres 3]`<br>`[Describir las acciones realizadas por el integrante durante el Primer Avance.]` | `[Conclusión individual del integrante 3.]` |
| | `[Apellidos, Nombres 4]`<br>`[Describir las acciones realizadas por el integrante durante el Primer Avance.]` | `[Conclusión individual del integrante 4.]` |
| | `[Apellidos, Nombres 5]`<br>`[Describir las acciones realizadas por el integrante durante el Primer Avance.]` | `[Conclusión individual del integrante 5.]` |
| | `[Apellidos, Nombres 6]`<br>`[Describir las acciones realizadas por el integrante durante el Primer Avance.]` | `[Conclusión individual del integrante 6.]` |
| | `[Apellidos, Nombres 7]`<br>`[Describir las acciones realizadas por el integrante durante el Primer Avance.]` | `[Conclusión individual del integrante 7.]` |
| | `[Apellidos, Nombres 8]`<br>`[Describir las acciones realizadas por el integrante durante el Primer Avance.]` | `[Conclusión individual del integrante 8.]` |
| **5.2.** Crea un entorno colaborativo e inclusivo, establece metas, planifica tareas y cumple objetivos. | El equipo definió la estrategia Agile (Scrum con sprints de dos semanas), distribuyó roles formales, construyó el Product Backlog inicial y acordó la estrategia de Software Factory documentada en la sección 1.6. | La organización formal del equipo y la trazabilidad *Product Backlog → User Stories → Sprint Backlog* permitieron cerrar el Primer Avance con entregables verificables en el repositorio. |

---

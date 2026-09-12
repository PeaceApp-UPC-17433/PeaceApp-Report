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

# Perfiles de los Integrantes del Equipo

**Startup:** PeaceApp

PeaceApp nace como respuesta a la inseguridad ciudadana en el Perú. Nuestra misión es que cualquier persona pueda desplazarse por la ciudad con información confiable, actualizada y verificada sobre los riesgos de su ruta. Nuestra visión es consolidarnos como la plataforma de referencia en inteligencia colaborativa de seguridad ciudadana en Latinoamérica, convirtiendo el reporte ciudadano en prevención basada en datos.

El equipo está conformado por ocho estudiantes de la carrera de Ingeniería de Software, con perfiles complementarios en desarrollo backend, desarrollo frontend y móvil, calidad de software, arquitectura, datos y prácticas DevOps.

<table>
<tr>
<td width="70%">
<b>Nombre:</b> [Apellidos, Nombres 1] (<code>[Código 1]</code>)<br><br>
<b>Rol en el equipo:</b> [Rol]<br><br>
<b>Conocimientos técnicos / habilidades:</b> [Describir carrera, ciclo, lenguajes, frameworks, herramientas y aporte esperado al equipo.]
</td>
<td width="30%" align="center">
<img src="assets/integrante1.png" alt="[Apellidos, Nombres 1]" width="150">
</td>
</tr>
<tr>
<td width="70%">
<b>Nombre:</b> [Apellidos, Nombres 2] (<code>[Código 2]</code>)<br><br>
<b>Rol en el equipo:</b> [Rol]<br><br>
<b>Conocimientos técnicos / habilidades:</b> [Describir carrera, ciclo, lenguajes, frameworks, herramientas y aporte esperado al equipo.]
</td>
<td width="30%" align="center">
<img src="assets/integrante2.png" alt="[Apellidos, Nombres 2]" width="150">
</td>
</tr>
<tr>
<td width="70%">
<b>Nombre:</b> [Apellidos, Nombres 3] (<code>[Código 3]</code>)<br><br>
<b>Rol en el equipo:</b> [Rol]<br><br>
<b>Conocimientos técnicos / habilidades:</b> [Describir carrera, ciclo, lenguajes, frameworks, herramientas y aporte esperado al equipo.]
</td>
<td width="30%" align="center">
<img src="assets/integrante3.png" alt="[Apellidos, Nombres 3]" width="150">
</td>
</tr>
<tr>
<td width="70%">
<b>Nombre:</b> [Apellidos, Nombres 4] (<code>[Código 4]</code>)<br><br>
<b>Rol en el equipo:</b> [Rol]<br><br>
<b>Conocimientos técnicos / habilidades:</b> [Describir carrera, ciclo, lenguajes, frameworks, herramientas y aporte esperado al equipo.]
</td>
<td width="30%" align="center">
<img src="assets/integrante4.png" alt="[Apellidos, Nombres 4]" width="150">
</td>
</tr>
<tr>
<td width="70%">
<b>Nombre:</b> [Apellidos, Nombres 5] (<code>[Código 5]</code>)<br><br>
<b>Rol en el equipo:</b> [Rol]<br><br>
<b>Conocimientos técnicos / habilidades:</b> [Describir carrera, ciclo, lenguajes, frameworks, herramientas y aporte esperado al equipo.]
</td>
<td width="30%" align="center">
<img src="assets/integrante5.png" alt="[Apellidos, Nombres 5]" width="150">
</td>
</tr>
<tr>
<td width="70%">
<b>Nombre:</b> [Apellidos, Nombres 6] (<code>[Código 6]</code>)<br><br>
<b>Rol en el equipo:</b> [Rol]<br><br>
<b>Conocimientos técnicos / habilidades:</b> [Describir carrera, ciclo, lenguajes, frameworks, herramientas y aporte esperado al equipo.]
</td>
<td width="30%" align="center">
<img src="assets/integrante6.png" alt="[Apellidos, Nombres 6]" width="150">
</td>
</tr>
<tr>
<td width="70%">
<b>Nombre:</b> [Apellidos, Nombres 7] (<code>[Código 7]</code>)<br><br>
<b>Rol en el equipo:</b> [Rol]<br><br>
<b>Conocimientos técnicos / habilidades:</b> [Describir carrera, ciclo, lenguajes, frameworks, herramientas y aporte esperado al equipo.]
</td>
<td width="30%" align="center">
<img src="assets/integrante7.png" alt="[Apellidos, Nombres 7]" width="150">
</td>
</tr>
<tr>
<td width="70%">
<b>Nombre:</b> [Apellidos, Nombres 8] (<code>[Código 8]</code>)<br><br>
<b>Rol en el equipo:</b> [Rol]<br><br>
<b>Conocimientos técnicos / habilidades:</b> [Describir carrera, ciclo, lenguajes, frameworks, herramientas y aporte esperado al equipo.]
</td>
<td width="30%" align="center">
<img src="assets/integrante8.png" alt="[Apellidos, Nombres 8]" width="150">
</td>
</tr>
</table>

---

# Capítulo I: Product & Agile Foundation

## 1.1. Descripción del producto

### 1.1.1. Nombre del producto

**PeaceApp** — Plataforma colaborativa de mapeo y prevención de incidentes de seguridad ciudadana con validación comunitaria e inteligencia predictiva.

PeaceApp es una plataforma móvil y web que construye, a partir de reportes ciudadanos georreferenciados, un mapa colaborativo de robos, accidentes y siniestros en la vía pública. Incorpora validación comunitaria, reputación de usuarios, detección de reportes falsos o duplicados, mapas de calor por horario, sugerencia de rutas de menor riesgo y un panel analítico para autoridades locales.

### 1.1.2. Problema y necesidad

**Problema.** Los ciudadanos se desplazan diariamente sin información confiable ni actualizada sobre dónde ocurren robos, accidentes y otros siniestros. Las denuncias formales están subregistradas, se publican con meses de retraso y no se georreferencian. Esto impide anticipar zonas de riesgo, elegir rutas más seguras y que las autoridades prioricen la intervención en los puntos críticos reales.

**Descomposición del problema (5W2H).**

| Dimensión | Descripción |
| :--- | :--- |
| **What (Qué)** | No existe una fuente de información de incidentes de seguridad ciudadana que sea simultáneamente oportuna, georreferenciada y verificable. La estadística oficial llega tarde, agregada por distrito y sin coordenadas. |
| **When (Cuándo)** | El problema se manifiesta en cada desplazamiento diario, con mayor intensidad en horarios de alta exposición (madrugada, hora punta de salida laboral y fines de semana por la noche). |
| **Where (Dónde)** | Zonas urbanas del Perú, con foco inicial en Lima Metropolitana, especialmente en corredores peatonales, paraderos de transporte público y vías de reparto de última milla. |
| **Who (Quién)** | Ciudadanos que se desplazan a pie o en transporte público, conductores y repartidores de última milla, juntas vecinales, serenazgos municipales, comisarías y gobiernos locales. |
| **Why (Por qué)** | Porque la ausencia de información oportuna convierte la seguridad en una decisión basada en percepción y rumor, y obliga a las autoridades a intervenir de manera reactiva en lugar de preventiva. |
| **How (Cómo)** | Mediante el reporte ciudadano desde el celular con ubicación, tipo de siniestro y evidencia, validado por la comunidad cercana y consolidado en mapas de calor y analítica por zona, horario y tipo de incidente. |
| **How much (Cuánto)** | El producto será gratuito para el ciudadano; la sostenibilidad se apoyará en licenciamiento del panel analítico a municipalidades y convenios institucionales. |

**Necesidad.** Los segmentos objetivo necesitan **decidir con evidencia**: el ciudadano necesita saber si su ruta y horario habituales son riesgosos antes de salir; la junta vecinal y el serenazgo necesitan identificar puntos críticos para priorizar patrullaje; y la comisaría o el gobierno local necesita complementar la estadística oficial con señales ciudadanas en tiempo real. Ninguna de estas necesidades está cubierta hoy por las herramientas disponibles.

**Evidencia del contexto.** Según el INEI (2024), el 89,9 % de la población de Lima Metropolitana de 15 años a más percibe que será víctima de algún hecho delictivo en los próximos doce meses, mientras que la tasa de denuncia efectiva se mantiene muy por debajo de la tasa de victimización, lo que confirma el subregistro que motiva este producto.

### 1.1.3. Usuarios objetivo

| # | Segmento | Descripción | Necesidad principal |
| :---: | :--- | :--- | :--- |
| 1 | **Ciudadano en tránsito** | Personas que se desplazan a pie o en transporte público por zonas urbanas, de 18 a 65 años, usuarias habituales de aplicaciones de mapas y mensajería. | Evaluar el riesgo de sus rutas y horarios habituales antes y durante el trayecto. |
| 2 | **Juntas vecinales y serenazgos municipales** | Organizaciones vecinales y personal de seguridad ciudadana municipal responsables de vigilancia en el territorio. | Identificar puntos críticos y priorizar patrullaje con evidencia georreferenciada. |
| 3 | **Conductores, repartidores y trabajadores de última milla** | Personas cuya jornada transcurre en la vía pública y que están expuestas de forma permanente a robos y accidentes. | Anticipar zonas y horarios de alta incidencia y reportar rápidamente desde el vehículo. |
| 4 | **Comisarías y gobiernos locales** | Autoridades que gestionan la estadística delictiva y la planificación de intervenciones. | Complementar la estadística oficial con reportes ciudadanos en tiempo real y analítica por zona y horario. |

**Contexto de uso.** El usuario reporta un incidente desde su celular en la vía pública o poco después del hecho, adjuntando ubicación, tipo de siniestro y evidencia (foto, video o descripción). Otros usuarios cercanos validan o descartan el reporte, y la plataforma muestra el mapa de calor actualizado que cualquier persona consulta antes de salir o durante su trayecto. Los municipios y juntas vecinales acceden a un panel web con la data consolidada por zona, horario y tipo de incidente.

### 1.1.4. Propuesta de solución

PeaceApp es una plataforma móvil y web que construye un mapa colaborativo de robos, accidentes y siniestros reportados por los propios ciudadanos con evidencia georreferenciada. Incorpora un sistema de validación comunitaria y reputación de usuarios, junto a un modelo de detección de reportes falsos o duplicados, para garantizar la confiabilidad de la información. A partir del histórico genera mapas de calor por horario y sugiere rutas alternativas de menor riesgo, además de un panel analítico para autoridades locales que permite pasar del reporte reactivo a la prevención basada en datos.

**Capacidades diferenciales.**

| Capacidad | Descripción | Valor entregado |
| :--- | :--- | :--- |
| Reporte georreferenciado con evidencia | Registro del incidente con coordenadas, tipo, hora y adjuntos multimedia en menos de 60 segundos. | Cierra la brecha de oportunidad frente a la denuncia formal. |
| Validación comunitaria | Usuarios cercanos confirman o descartan el reporte dentro de una ventana de tiempo y radio definidos. | Eleva la confiabilidad sin requerir verificación institucional previa. |
| Reputación de usuarios | Puntaje dinámico según el historial de reportes confirmados y descartados. | Desincentiva el reporte malicioso y pondera la señal. |
| Detección de reportes falsos y duplicados | Reglas y modelo de clasificación sobre proximidad espacio-temporal, similitud de contenido y reputación del emisor. | Evita la contaminación del mapa y la doble contabilización. |
| Mapa de calor por horario | Agregación del histórico por celda geográfica y franja horaria. | Permite decidir ruta y horario con evidencia. |
| Sugerencia de rutas de menor riesgo | Ponderación del grafo de rutas con el índice de riesgo de cada tramo. | Convierte la información en una decisión accionable. |
| Panel analítico para autoridades | Tablero web con indicadores por zona, horario, tipo de incidente y evolución temporal. | Habilita la priorización de patrullaje e intervención preventiva. |

### 1.1.5. Objetivos del producto

**Objetivo general.** Reducir la exposición al riesgo de los ciudadanos en sus desplazamientos urbanos mediante una plataforma colaborativa que convierta el reporte ciudadano georreferenciado en información confiable, oportuna y accionable para personas y autoridades.

**Objetivos específicos.**

| ID | Objetivo específico | Indicador de logro |
| :---: | :--- | :--- |
| OE-01 | Habilitar el registro de incidentes georreferenciados con evidencia desde dispositivos móviles. | Tiempo mediano de registro de un reporte completo menor o igual a 60 segundos. |
| OE-02 | Garantizar la confiabilidad de la información publicada mediante validación comunitaria y reputación. | Al menos el 80 % de los reportes publicados cuentan con una validación comunitaria dentro de las 2 horas. |
| OE-03 | Reducir la proporción de reportes falsos o duplicados visibles en el mapa. | Menos del 5 % de los reportes visibles clasificados como falsos o duplicados en auditoría manual. |
| OE-04 | Ofrecer mapas de calor y rutas alternativas de menor riesgo. | Disponibilidad del mapa de calor por franja horaria para el 100 % de las zonas con cobertura de reportes. |
| OE-05 | Proveer a autoridades locales un panel analítico con datos consolidados. | Panel con indicadores por zona, horario y tipo de incidente, actualizado al menos cada hora. |
| OE-06 | Construir el producto bajo una Software Factory automatizada y una arquitectura de microservicios contenedorizada. | Pipeline de CI/CD ejecutándose en cada Pull Request y despliegue automatizado en entorno cloud. |

**Objetivos de proceso (curso).**

| ID | Objetivo de proceso | Indicador de logro |
| :---: | :--- | :--- |
| OP-01 | Mantener trazabilidad completa *Product Backlog → User Stories → Sprint Backlog → Código → Pruebas → Despliegue*. | 100 % de los work-items enlazados a una User Story y a un commit o Pull Request. |
| OP-02 | Automatizar progresivamente build, pruebas y despliegue. | Incremento del porcentaje de etapas automatizadas en cada entrega. |
| OP-03 | Distribuir la carga de trabajo de forma equilibrada entre los ocho integrantes. | Variación menor al 20 % entre los story points completados por integrante en cada sprint. |

### 1.1.6. Alcance inicial

**Dentro del alcance del Primer Avance (Semana 03).**

- Definición del producto, del problema y de la necesidad.
- Product Vision.
- Objetivos generales y específicos.
- Delimitación del alcance del producto y sus restricciones.
- As-Is Scenario Mapping y To-Be Scenario Mapping.
- Epics y User Stories iniciales.
- Product Backlog inicial priorizado y estimado.
- Estrategia Agile y organización del equipo.
- Estrategia inicial de Software Factory y herramientas seleccionadas.
- Configuración del repositorio con estrategia de ramas `main` / `develop`.

**Dentro del alcance del producto (semestre).**

| Módulo | Incluye |
| :--- | :--- |
| Identidad y cuentas | Registro, autenticación, perfil, reputación y reporte anónimo. |
| Reporte de incidentes | Creación, edición, adjuntos multimedia, categorización y geolocalización. |
| Validación comunitaria | Confirmación y descarte por usuarios cercanos, ventana temporal y radio de validación. |
| Confiabilidad | Detección de duplicados y de reportes falsos, moderación y apelación. |
| Consulta y visualización | Mapa en tiempo real, mapa de calor por franja horaria y filtros por tipo de incidente. |
| Rutas | Cálculo de ruta alternativa ponderada por índice de riesgo. |
| Notificaciones | Alertas de proximidad y resumen por zona de interés. |
| Analítica institucional | Panel web con indicadores, exportación y comparativo temporal por zona. |
| Plataforma | Microservicios contenedorizados, API Gateway, CI/CD, observabilidad y seguridad. |

**Fuera del alcance.**

- Integración con los sistemas internos de la Policía Nacional del Perú o del Ministerio del Interior para la generación de denuncias formales con valor legal.
- Botón de pánico con despacho automático de unidades policiales o de bomberos.
- Videovigilancia, reconocimiento facial o cualquier tratamiento biométrico.
- Cobertura nacional completa en la primera versión; el despliegue inicial se limita a Lima Metropolitana.
- Aplicaciones nativas publicadas en tiendas comerciales (se contempla distribución de builds para evaluación).

### 1.1.7. Restricciones

| Tipo | Restricción | Implicancia |
| :--- | :--- | :--- |
| **Temporal** | El producto debe evolucionar mediante entregas incrementales durante el ciclo 2026-20, con hitos en las semanas 03, Segundo Avance, TB2 y TB4. | El Product Backlog se prioriza para asegurar un incremento verificable en cada hito. |
| **Técnica** | Arquitectura obligatoria orientada a microservicios, con contenedorización y una plataforma de administración de cargas de trabajo y servicios. | Se descarta el monolito; se define un conjunto acotado de servicios por dominio (sección 1.6.4). |
| **Técnica** | Despliegue en un entorno cloud o infraestructura equivalente. | Se prioriza el uso de niveles gratuitos o créditos académicos de los proveedores cloud. |
| **Presupuestal** | Proyecto académico sin presupuesto asignado. | Uso de herramientas gratuitas, de código abierto o con licencia educativa (GitHub Actions, Docker Hub, SonarCloud, etc.). |
| **De equipo** | Ocho integrantes con disponibilidad parcial y carga académica simultánea. | Sprints de dos semanas y límites de trabajo en curso por integrante. |
| **Regulatoria** | Tratamiento de datos personales y de geolocalización sujeto a la Ley N.° 29733 de Protección de Datos Personales y su reglamento. | Consentimiento explícito, minimización de datos, anonimización del reporte y política de retención documentada. |
| **De contenido** | Los reportes son generados por usuarios y pueden contener contenido sensible o difamatorio. | Moderación, términos de uso, reputación y mecanismo de apelación desde el primer incremento. |
| **De datos** | La calidad del mapa depende de la densidad de reportes en cada zona. | Se define un umbral mínimo de reportes por celda antes de publicar índices de riesgo. |

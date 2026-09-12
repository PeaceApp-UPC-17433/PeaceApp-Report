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

## 1.2. Product Vision

**Declaración de visión (Moore's Product Vision Statement).**

> **Para** ciudadanos, juntas vecinales, trabajadores de última milla y autoridades locales del Perú
> **que** necesitan información oportuna, georreferenciada y confiable sobre robos, accidentes y siniestros en la vía pública,
> **PeaceApp es** una plataforma colaborativa de mapeo y prevención de incidentes de seguridad ciudadana
> **que** convierte el reporte ciudadano validado por la comunidad en mapas de calor, rutas de menor riesgo y analítica accionable.
> **A diferencia de** la estadística oficial —publicada con meses de retraso y sin georreferenciación— y de los grupos de mensajería vecinales —sin verificación, sin estructura ni memoria histórica—,
> **nuestro producto** garantiza la confiabilidad mediante validación comunitaria, reputación de usuarios y detección automatizada de reportes falsos o duplicados, y entrega a las autoridades evidencia consolidada para priorizar la intervención preventiva.

**Valor entregado por segmento.**

| Segmento | Valor entregado |
| :--- | :--- |
| Ciudadano en tránsito | Decidir ruta y horario con evidencia en lugar de percepción, reduciendo su exposición al riesgo. |
| Juntas vecinales y serenazgos | Priorizar patrullaje sobre puntos críticos reales y medir el efecto de la intervención. |
| Conductores y repartidores | Anticipar tramos y franjas horarias de alta incidencia en su jornada. |
| Comisarías y gobiernos locales | Complementar la estadística oficial con señales ciudadanas en tiempo real y sustentar decisiones presupuestales. |

**Product Vision Board.**

| Bloque | Contenido |
| :--- | :--- |
| **Visión** | Que ninguna persona tenga que elegir su ruta a ciegas. |
| **Grupo objetivo** | Ciudadanos en tránsito, trabajadores de última milla, juntas vecinales, serenazgos y gobiernos locales en zonas urbanas del Perú. |
| **Necesidades** | Información de incidentes oportuna, georreferenciada y verificable; capacidad de reportar en segundos; evidencia consolidada para priorizar intervención. |
| **Producto** | Aplicación móvil de reporte y consulta, aplicación web de consulta, panel analítico institucional y backend de microservicios con validación comunitaria e inteligencia sobre reportes. |
| **Objetivos de negocio** | Alcanzar una densidad de reportes suficiente para publicar índices de riesgo confiables en las zonas piloto y validar el panel analítico con al menos una organización vecinal o municipal. |

---

## 1.3. Requirements Specification

### 1.3.1. As-Is Scenario Mapping

Escenario actual del ciudadano que necesita desplazarse por la ciudad y del vecino o autoridad que necesita actuar sobre los puntos críticos.

| Fases | 1. Buscar información sobre la seguridad de la zona | 2. Planificar el desplazamiento | 3. Ocurrencia del incidente | 4. Reportar o compartir lo ocurrido | 5. Actuar sobre los puntos críticos |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Doing** | Revisa noticias, pregunta en grupos de WhatsApp del barrio y consulta comentarios sueltos en redes sociales. | Abre una app de mapas y elige la ruta más corta o más rápida; el criterio de seguridad no existe como variable. | Sufre o presencia un robo, un accidente o un siniestro en la vía pública. | Comenta el hecho en el grupo vecinal; en pocos casos acude a la comisaría a denunciar. | La junta vecinal o el serenazgo organiza rondas según reclamos verbales y percepción. |
| **Thinking** | "No sé si esta información es de hoy o de hace un año." | "Esta ruta es más corta, pero no sé si es segura a esta hora." | "Me pudo pasar en cualquier cuadra, nadie lo va a saber." | "Denunciar me va a tomar horas y no va a cambiar nada." | "Sabemos que hay zonas malas, pero no tenemos con qué sustentarlo." |
| **Feeling** | Desconfianza e incertidumbre. | Inseguridad al decidir. | Miedo, vulnerabilidad e impotencia. | Frustración y desánimo. | Impotencia frente a la falta de evidencia. |
| **Pain points** | Información dispersa, desactualizada, no georreferenciada y sin verificación. | Ninguna app de rutas incorpora el riesgo como variable de decisión. | No existe un canal inmediato para dejar registro del hecho. | La denuncia formal es lenta, el subregistro es alto y el aporte en grupos de mensajería se pierde. | La estadística oficial llega agregada y con meses de retraso; no permite priorizar cuadras ni horarios. |

### 1.3.2. To-Be Scenario Mapping

Escenario objetivo con PeaceApp operando.

| Fases | 1. Consultar el riesgo de la zona | 2. Planificar el desplazamiento | 3. Ocurrencia del incidente | 4. Reportar y validar | 5. Actuar sobre los puntos críticos |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Doing** | Abre PeaceApp y consulta el mapa de calor filtrado por su zona, franja horaria y tipo de incidente. | Solicita la ruta hacia su destino y recibe alternativas ordenadas por índice de riesgo, no solo por tiempo. | Sufre o presencia un incidente y abre el formulario rápido de reporte. | Registra ubicación, tipo y evidencia en menos de un minuto; usuarios cercanos confirman o descartan y la plataforma filtra duplicados y reportes falsos. | La junta vecinal, el serenazgo o el gobierno local revisa el panel analítico por zona, horario y tipo, y programa el patrullaje sobre los puntos críticos. |
| **Thinking** | "Esta información es de hoy y otras personas ya la validaron." | "Tomo cinco minutos más y evito el tramo con más incidencias a esta hora." | "Reportar me toma menos de un minuto y sirve a los demás." | "Mi reporte tiene peso porque mi historial es confiable." | "Tenemos evidencia georreferenciada para sustentar dónde intervenir." |
| **Feeling** | Confianza y control. | Tranquilidad al decidir. | Capacidad de reacción. | Sentido de contribución a la comunidad. | Respaldo para tomar decisiones y rendir cuentas. |
| **Gains** | Información oportuna, georreferenciada y validada por la comunidad. | El riesgo se vuelve una variable explícita de la decisión de ruta y horario. | Canal inmediato y accesible desde el celular, con opción de reporte anónimo. | Confiabilidad sostenida por validación comunitaria, reputación y detección de falsos y duplicados. | Priorización preventiva basada en datos y medición del efecto de la intervención. |

### 1.3.3. Epics

| ID | Epic | Descripción | Objetivo relacionado |
| :---: | :--- | :--- | :---: |
| **EP-01** | Gestión de identidad y perfil | Registro, autenticación, gestión de perfil, reputación y modo de reporte anónimo. | OE-02 |
| **EP-02** | Reporte de incidentes georreferenciados | Creación, categorización, adjuntos de evidencia y edición de reportes con ubicación. | OE-01 |
| **EP-03** | Validación comunitaria y reputación | Confirmación y descarte de reportes por usuarios cercanos y cálculo del puntaje de reputación. | OE-02 |
| **EP-04** | Confiabilidad de la información | Detección de reportes duplicados y falsos, moderación y apelación. | OE-03 |
| **EP-05** | Visualización y mapa de calor | Mapa en tiempo real, mapa de calor por franja horaria y filtros de consulta. | OE-04 |
| **EP-06** | Rutas de menor riesgo | Cálculo y presentación de rutas alternativas ponderadas por índice de riesgo. | OE-04 |
| **EP-07** | Notificaciones y alertas | Alertas de proximidad y resúmenes por zona de interés. | OE-04 |
| **EP-08** | Panel analítico institucional | Tablero web con indicadores por zona, horario y tipo de incidente, y exportación de datos. | OE-05 |
| **EP-09** | Plataforma, arquitectura y Software Factory | Microservicios, contenedorización, API Gateway, CI/CD, observabilidad y seguridad. | OE-06 |

### 1.3.4. User Stories

Las historias siguen el formato *Como \<rol\>, quiero \<funcionalidad\>, para \<beneficio\>*, con criterios de aceptación expresados en formato Gherkin (*Given–When–Then*). Las historias con prefijo **TS** corresponden a *Technical Stories*.

#### EP-01 — Gestión de identidad y perfil

| ID | Título | Descripción | Criterios de aceptación |
| :---: | :--- | :--- | :--- |
| **US-01** | Registro de usuario | Como ciudadano, quiero registrarme con mi correo y una contraseña, para acceder a las funciones de reporte y validación. | **Escenario: registro exitoso**<br>**Dado** que ingreso un correo válido no registrado y una contraseña que cumple la política de seguridad,<br>**Cuando** confirmo el formulario de registro,<br>**Entonces** el sistema crea mi cuenta, envía un correo de verificación y me redirige a la pantalla de inicio de sesión.<br><br>**Escenario: correo ya registrado**<br>**Dado** que ingreso un correo ya registrado,<br>**Cuando** confirmo el formulario,<br>**Entonces** el sistema muestra el mensaje "El correo ya se encuentra registrado" y no crea una cuenta duplicada. |
| **US-02** | Inicio de sesión | Como usuario registrado, quiero iniciar sesión de forma segura, para usar la aplicación con mi identidad y mi reputación. | **Escenario: credenciales válidas**<br>**Dado** que mi cuenta está verificada,<br>**Cuando** ingreso credenciales correctas,<br>**Entonces** el sistema me autentica, emite un token de sesión y muestra el mapa principal.<br><br>**Escenario: credenciales inválidas**<br>**Dado** que ingreso una contraseña incorrecta,<br>**Cuando** intento iniciar sesión,<br>**Entonces** el sistema muestra un mensaje de error genérico y bloquea el acceso tras cinco intentos fallidos consecutivos. |
| **US-03** | Gestión de perfil | Como usuario registrado, quiero editar mis datos de perfil y mis zonas de interés, para recibir información relevante a mis desplazamientos. | **Escenario: actualización de zonas de interés**<br>**Dado** que estoy autenticado,<br>**Cuando** agrego una zona de interés en mi perfil y guardo los cambios,<br>**Entonces** el sistema persiste la zona y la utiliza para filtrar el resumen de incidentes de mi pantalla principal. |
| **US-04** | Reporte anónimo | Como ciudadano que teme represalias, quiero enviar un reporte sin exponer mi identidad pública, para contribuir sin ponerme en riesgo. | **Escenario: reporte anónimo**<br>**Dado** que estoy autenticado y activo la opción "Reportar de forma anónima",<br>**Cuando** envío el reporte,<br>**Entonces** el reporte se publica sin mostrar mi nombre de usuario, aunque el sistema conserva internamente la trazabilidad para el cálculo de reputación y la moderación. |
| **US-05** | Consulta de reputación | Como usuario registrado, quiero ver mi puntaje de reputación y su historial, para entender cómo mis reportes afectan mi credibilidad. | **Escenario: visualización de reputación**<br>**Dado** que tengo al menos un reporte publicado,<br>**Cuando** abro la sección "Mi reputación",<br>**Entonces** el sistema muestra mi puntaje actual, el número de reportes confirmados y descartados, y la variación de los últimos treinta días. |

#### EP-02 — Reporte de incidentes georreferenciados

| ID | Título | Descripción | Criterios de aceptación |
| :---: | :--- | :--- | :--- |
| **US-06** | Registro rápido de incidente | Como ciudadano, quiero registrar un incidente con ubicación y tipo en menos de un minuto, para dejar constancia inmediata del hecho. | **Escenario: registro con ubicación automática**<br>**Dado** que concedí permiso de ubicación a la aplicación,<br>**Cuando** selecciono el tipo de incidente y confirmo el envío,<br>**Entonces** el sistema registra el reporte con mis coordenadas y la marca de tiempo, y lo muestra en el mapa en estado "Pendiente de validación".<br><br>**Escenario: sin permiso de ubicación**<br>**Dado** que no concedí permiso de ubicación,<br>**Cuando** intento registrar un incidente,<br>**Entonces** el sistema me permite seleccionar la ubicación manualmente sobre el mapa antes de enviar. |
| **US-07** | Categorización del incidente | Como ciudadano, quiero clasificar el incidente por tipo y gravedad, para que la información sea útil al filtrar el mapa. | **Escenario: selección de categoría**<br>**Dado** que estoy en el formulario de reporte,<br>**Cuando** despliego el selector de tipo,<br>**Entonces** el sistema muestra las categorías disponibles (robo, hurto, accidente de tránsito, agresión, vandalismo, otro) y exige seleccionar una antes de habilitar el envío. |
| **US-08** | Adjuntar evidencia multimedia | Como ciudadano, quiero adjuntar una foto, un video corto o una descripción al reporte, para dar respaldo a lo que reporto. | **Escenario: adjunto válido**<br>**Dado** que selecciono un archivo de imagen o video menor a 25 MB,<br>**Cuando** confirmo el envío del reporte,<br>**Entonces** el sistema almacena la evidencia, la asocia al reporte y elimina los metadatos de ubicación del archivo original.<br><br>**Escenario: archivo excede el límite**<br>**Dado** que selecciono un archivo mayor a 25 MB,<br>**Cuando** intento adjuntarlo,<br>**Entonces** el sistema rechaza el archivo y muestra el límite permitido. |
| **US-09** | Edición y eliminación de reporte propio | Como autor de un reporte, quiero corregirlo o eliminarlo dentro de una ventana de tiempo, para enmendar errores de registro. | **Escenario: edición dentro de la ventana**<br>**Dado** que mi reporte tiene menos de 30 minutos y no ha recibido validaciones,<br>**Cuando** edito el tipo o la descripción,<br>**Entonces** el sistema actualiza el reporte y registra la modificación en la bitácora de auditoría.<br><br>**Escenario: edición fuera de la ventana**<br>**Dado** que mi reporte ya fue validado por otros usuarios,<br>**Cuando** intento editarlo,<br>**Entonces** el sistema bloquea la edición y ofrece la opción de solicitar corrección a moderación. |
| **US-10** | Historial de reportes propios | Como usuario registrado, quiero ver la lista de los reportes que he enviado y su estado, para dar seguimiento a mi aporte. | **Escenario: consulta de historial**<br>**Dado** que estoy autenticado,<br>**Cuando** abro la sección "Mis reportes",<br>**Entonces** el sistema lista mis reportes ordenados por fecha, con su estado (pendiente, validado, descartado o en moderación) y el número de validaciones recibidas. |

#### EP-03 — Validación comunitaria y reputación

| ID | Título | Descripción | Criterios de aceptación |
| :---: | :--- | :--- | :--- |
| **US-11** | Validar o descartar un reporte cercano | Como usuario ubicado cerca de un incidente reportado, quiero confirmarlo o descartarlo, para elevar la confiabilidad del mapa. | **Escenario: validación dentro del radio**<br>**Dado** que me encuentro dentro del radio de validación de 500 metros y el reporte tiene menos de 6 horas,<br>**Cuando** selecciono "Confirmo" o "No ocurrió",<br>**Entonces** el sistema registra mi voto, actualiza el contador de validaciones y no me permite votar nuevamente sobre el mismo reporte.<br><br>**Escenario: fuera del radio**<br>**Dado** que me encuentro fuera del radio de validación,<br>**Cuando** abro el detalle del reporte,<br>**Entonces** el sistema muestra la información pero deshabilita los botones de validación. |
| **US-12** | Publicación por umbral de validación | Como plataforma, quiero publicar un reporte como validado al alcanzar un umbral de confirmaciones ponderadas por reputación, para mostrar solo información respaldada. | **Escenario: umbral alcanzado**<br>**Dado** que un reporte acumula un puntaje de validación ponderado mayor o igual al umbral configurado,<br>**Cuando** se registra la validación que alcanza dicho umbral,<br>**Entonces** el sistema cambia el estado del reporte a "Validado" y lo incorpora al cálculo del mapa de calor. |
| **US-13** | Cálculo de reputación | Como plataforma, quiero recalcular la reputación del autor según el resultado de la validación, para ponderar futuros reportes. | **Escenario: reporte confirmado**<br>**Dado** que un reporte del usuario alcanza el estado "Validado",<br>**Cuando** se cierra su ventana de validación,<br>**Entonces** el sistema incrementa la reputación del autor según la fórmula definida y registra el evento en su historial.<br><br>**Escenario: reporte descartado**<br>**Dado** que un reporte del usuario es descartado por la comunidad,<br>**Cuando** se cierra su ventana de validación,<br>**Entonces** el sistema reduce la reputación del autor y, si cae por debajo del mínimo, limita su capacidad de publicar sin moderación previa. |

#### EP-04 — Confiabilidad de la información

| ID | Título | Descripción | Criterios de aceptación |
| :---: | :--- | :--- | :--- |
| **US-14** | Detección de reportes duplicados | Como plataforma, quiero agrupar reportes del mismo hecho, para evitar la doble contabilización en el mapa. | **Escenario: duplicado por proximidad espacio-temporal**<br>**Dado** que se recibe un reporte del mismo tipo a menos de 100 metros y dentro de los 30 minutos de otro existente,<br>**Cuando** se procesa el nuevo reporte,<br>**Entonces** el sistema lo vincula como evidencia adicional del incidente agrupado en lugar de crear una entrada independiente en el mapa. |
| **US-15** | Detección de reportes falsos | Como plataforma, quiero identificar reportes con alta probabilidad de ser falsos, para retenerlos antes de su publicación. | **Escenario: reporte de alto riesgo**<br>**Dado** que el modelo de clasificación asigna a un reporte una probabilidad de falsedad mayor al umbral configurado,<br>**Cuando** se procesa el reporte,<br>**Entonces** el sistema lo envía a la cola de moderación, no lo publica en el mapa y notifica al autor que su reporte está en revisión. |
| **US-16** | Moderación de reportes | Como moderador, quiero revisar la cola de reportes retenidos y aprobar o rechazar cada uno, para mantener la calidad del contenido. | **Escenario: aprobación**<br>**Dado** que existe un reporte en la cola de moderación,<br>**Cuando** lo apruebo,<br>**Entonces** el sistema lo publica en el mapa y registra la decisión junto con mi identificador y la marca de tiempo. |
| **US-17** | Apelación del autor | Como autor de un reporte rechazado, quiero apelar la decisión, para que se revise nuevamente mi caso. | **Escenario: apelación registrada**<br>**Dado** que mi reporte fue rechazado hace menos de 7 días,<br>**Cuando** envío una apelación con una justificación,<br>**Entonces** el sistema reabre el caso en la cola de moderación con prioridad y me notifica el resultado de la revisión. |

#### EP-05 — Visualización y mapa de calor

| ID | Título | Descripción | Criterios de aceptación |
| :---: | :--- | :--- | :--- |
| **US-18** | Mapa de incidentes en tiempo real | Como ciudadano, quiero ver en un mapa los incidentes validados cerca de mí, para conocer la situación actual de mi entorno. | **Escenario: carga del mapa**<br>**Dado** que abro la aplicación con permiso de ubicación,<br>**Cuando** se carga la pantalla principal,<br>**Entonces** el sistema centra el mapa en mi posición y muestra los incidentes validados de las últimas 24 horas dentro de un radio de 2 kilómetros en menos de 3 segundos. |
| **US-19** | Filtros de consulta | Como ciudadano, quiero filtrar el mapa por tipo de incidente y rango de fechas, para enfocar la consulta en lo que me interesa. | **Escenario: aplicación de filtros**<br>**Dado** que estoy en el mapa principal,<br>**Cuando** selecciono uno o más tipos de incidente y un rango de fechas,<br>**Entonces** el sistema actualiza el mapa mostrando únicamente los incidentes que cumplen los criterios seleccionados. |
| **US-20** | Mapa de calor por franja horaria | Como ciudadano, quiero ver el mapa de calor de una zona según la franja horaria, para saber si mi horario habitual es riesgoso. | **Escenario: consulta por franja horaria**<br>**Dado** que selecciono una franja horaria y una zona con cobertura de reportes suficiente,<br>**Cuando** activo la vista de mapa de calor,<br>**Entonces** el sistema muestra la intensidad de incidencia por celda geográfica para esa franja, calculada sobre el histórico de reportes validados.<br><br>**Escenario: cobertura insuficiente**<br>**Dado** que la zona no alcanza el umbral mínimo de reportes,<br>**Cuando** activo la vista de mapa de calor,<br>**Entonces** el sistema muestra la leyenda "Datos insuficientes para esta zona" en lugar de un índice de riesgo. |
| **US-21** | Detalle del incidente | Como ciudadano, quiero abrir el detalle de un incidente del mapa, para conocer el tipo, la hora, la evidencia y el nivel de validación. | **Escenario: apertura del detalle**<br>**Dado** que selecciono un marcador en el mapa,<br>**Cuando** se abre el panel de detalle,<br>**Entonces** el sistema muestra el tipo, la fecha y hora, la descripción, la evidencia adjunta, el número de validaciones y el estado del reporte. |

#### EP-06 — Rutas de menor riesgo

| ID | Título | Descripción | Criterios de aceptación |
| :---: | :--- | :--- | :--- |
| **US-22** | Sugerencia de ruta de menor riesgo | Como ciudadano, quiero recibir rutas alternativas ordenadas por riesgo además de por tiempo, para elegir con criterio de seguridad. | **Escenario: cálculo de alternativas**<br>**Dado** que ingreso un origen y un destino,<br>**Cuando** solicito la ruta,<br>**Entonces** el sistema muestra al menos dos alternativas indicando para cada una el tiempo estimado y su índice de riesgo relativo según el histórico de la franja horaria actual. |
| **US-23** | Comparación de rutas por horario | Como ciudadano, quiero comparar el riesgo de una misma ruta en distintos horarios, para decidir cuándo desplazarme. | **Escenario: comparación horaria**<br>**Dado** que tengo una ruta calculada,<br>**Cuando** selecciono la opción "Comparar por horario",<br>**Entonces** el sistema muestra el índice de riesgo de esa ruta para cada franja horaria del día. |

#### EP-07 — Notificaciones y alertas

| ID | Título | Descripción | Criterios de aceptación |
| :---: | :--- | :--- | :--- |
| **US-24** | Alerta de proximidad | Como ciudadano en tránsito, quiero recibir una alerta cuando me aproximo a una zona con incidencia alta reciente, para tomar precauciones. | **Escenario: ingreso a zona de alta incidencia**<br>**Dado** que tengo activadas las alertas de proximidad,<br>**Cuando** ingreso a una celda con índice de riesgo alto en la franja horaria actual,<br>**Entonces** el sistema emite una notificación indicando el tipo de incidente predominante, sin repetir la alerta para la misma celda dentro de la siguiente hora. |
| **US-25** | Resumen por zona de interés | Como usuario registrado, quiero recibir un resumen periódico de mis zonas de interés, para mantenerme informado sin abrir la aplicación. | **Escenario: envío del resumen**<br>**Dado** que tengo al menos una zona de interés configurada y el resumen activado,<br>**Cuando** se cumple la periodicidad seleccionada,<br>**Entonces** el sistema envía una notificación con el número de incidentes validados y el tipo más frecuente en el periodo. |

#### EP-08 — Panel analítico institucional

| ID | Título | Descripción | Criterios de aceptación |
| :---: | :--- | :--- | :--- |
| **US-26** | Acceso institucional al panel | Como representante de una municipalidad o junta vecinal, quiero acceder al panel web con credenciales institucionales, para consultar la data consolidada de mi jurisdicción. | **Escenario: acceso autorizado**<br>**Dado** que mi cuenta institucional está habilitada para una jurisdicción,<br>**Cuando** inicio sesión en el panel web,<br>**Entonces** el sistema me muestra únicamente los datos de las zonas asignadas a mi jurisdicción. |
| **US-27** | Indicadores por zona, horario y tipo | Como autoridad local, quiero ver indicadores de incidencia por zona, horario y tipo de incidente, para priorizar el patrullaje. | **Escenario: consulta de indicadores**<br>**Dado** que estoy autenticado en el panel,<br>**Cuando** selecciono una zona y un periodo,<br>**Entonces** el sistema muestra el total de incidentes validados, su distribución por tipo, su distribución horaria y el ranking de los diez puntos críticos de la zona. |
| **US-28** | Evolución temporal y efecto de la intervención | Como autoridad local, quiero comparar la incidencia antes y después de una intervención, para evaluar su efecto. | **Escenario: comparativo de periodos**<br>**Dado** que selecciono dos periodos y una zona,<br>**Cuando** solicito el comparativo,<br>**Entonces** el sistema muestra la variación porcentual de incidentes validados por tipo entre ambos periodos. |
| **US-29** | Exportación de datos | Como analista municipal, quiero exportar los datos consolidados de mi jurisdicción, para integrarlos a mis propios informes. | **Escenario: exportación**<br>**Dado** que tengo un conjunto de datos filtrado en el panel,<br>**Cuando** selecciono "Exportar",<br>**Entonces** el sistema genera un archivo CSV con los datos agregados y sin información que permita identificar a los usuarios autores. |

#### EP-09 — Plataforma, arquitectura y Software Factory (Technical Stories)

| ID | Título | Descripción | Criterios de aceptación |
| :---: | :--- | :--- | :--- |
| **TS-01** | Configuración del repositorio y estrategia de ramas | Como equipo de desarrollo, quiero un repositorio con ramas `main` y `develop` y reglas de protección, para asegurar la trazabilidad y la calidad de las integraciones. | **Escenario: protección de ramas**<br>**Dado** que el repositorio está creado,<br>**Cuando** intento hacer push directo a `main`,<br>**Entonces** el servidor lo rechaza y exige un Pull Request con al menos una revisión aprobada y el pipeline en verde. |
| **TS-02** | Pipeline de integración continua | Como equipo de desarrollo, quiero un pipeline que compile y ejecute las pruebas en cada Pull Request, para detectar defectos antes de integrar. | **Escenario: ejecución del pipeline**<br>**Dado** que se abre o actualiza un Pull Request hacia `develop`,<br>**Cuando** el pipeline se ejecuta,<br>**Entonces** compila el servicio, ejecuta las pruebas unitarias y publica el resultado como *check* obligatorio del Pull Request. |
| **TS-03** | Contenedorización de los servicios | Como equipo de desarrollo, quiero empaquetar cada servicio en una imagen de contenedor, para garantizar la paridad entre entornos. | **Escenario: build de imagen**<br>**Dado** que un servicio cuenta con su `Dockerfile`,<br>**Cuando** el pipeline ejecuta la etapa de build,<br>**Entonces** genera la imagen etiquetada con la versión semántica y el hash del commit, y la publica en el registro de artefactos. |
| **TS-04** | API Gateway y enrutamiento | Como equipo de desarrollo, quiero exponer los microservicios a través de un API Gateway, para centralizar autenticación, enrutamiento y límites de tasa. | **Escenario: enrutamiento**<br>**Dado** que un cliente invoca un endpoint público,<br>**Cuando** la petición llega al Gateway,<br>**Entonces** este valida el token, aplica el límite de tasa y enruta al microservicio correspondiente. |
| **TS-05** | Análisis estático de código y calidad | Como equipo de desarrollo, quiero ejecutar análisis estático en cada Pull Request, para sostener estándares de calidad y seguridad. | **Escenario: quality gate**<br>**Dado** que el pipeline ejecuta el análisis estático,<br>**Cuando** el resultado no cumple el *quality gate* definido,<br>**Entonces** el Pull Request queda bloqueado hasta la corrección de los hallazgos bloqueantes. |
| **TS-06** | Despliegue automatizado en entorno cloud | Como equipo de desarrollo, quiero desplegar automáticamente el incremento en el entorno de pruebas, para validar cada integración. | **Escenario: despliegue continuo**<br>**Dado** que un merge se integra a `develop` y el pipeline finaliza correctamente,<br>**Cuando** se ejecuta la etapa de despliegue,<br>**Entonces** la nueva versión queda desplegada en el entorno de pruebas y el equipo recibe la notificación con la URL del incremento. |
| **TS-07** | Observabilidad básica | Como equipo de desarrollo, quiero centralizar métricas y logs de los servicios, para diagnosticar incidencias en operación. | **Escenario: consulta de métricas**<br>**Dado** que los servicios exponen sus métricas,<br>**Cuando** consulto el tablero de observabilidad,<br>**Entonces** visualizo latencia, tasa de error y disponibilidad por servicio en el periodo seleccionado. |
| **TS-08** | Gestión de secretos y configuración | Como equipo de desarrollo, quiero gestionar credenciales y configuración fuera del código fuente, para evitar la exposición de secretos. | **Escenario: ausencia de secretos en el repositorio**<br>**Dado** que el pipeline ejecuta el escaneo de secretos,<br>**Cuando** detecta una credencial en el código,<br>**Entonces** falla la ejecución e impide la integración del cambio. |

### 1.3.5. Product Backlog inicial

Estimación en *story points* con la serie de Fibonacci (1, 2, 3, 5, 8, 13) mediante *Planning Poker*. Priorización según **MoSCoW** y ordenamiento por valor de negocio frente a esfuerzo.

| # Orden | ID | Epic | Título | Prioridad (MoSCoW) | Story Points | Sprint tentativo |
| :---: | :---: | :---: | :--- | :---: | :---: | :---: |
| 1 | TS-01 | EP-09 | Configuración del repositorio y estrategia de ramas | Must | 2 | Sprint 1 |
| 2 | TS-02 | EP-09 | Pipeline de integración continua | Must | 5 | Sprint 1 |
| 3 | TS-03 | EP-09 | Contenedorización de los servicios | Must | 5 | Sprint 1 |
| 4 | US-01 | EP-01 | Registro de usuario | Must | 3 | Sprint 1 |
| 5 | US-02 | EP-01 | Inicio de sesión | Must | 3 | Sprint 1 |
| 6 | TS-04 | EP-09 | API Gateway y enrutamiento | Must | 5 | Sprint 1 |
| 7 | US-06 | EP-02 | Registro rápido de incidente | Must | 8 | Sprint 2 |
| 8 | US-07 | EP-02 | Categorización del incidente | Must | 2 | Sprint 2 |
| 9 | US-18 | EP-05 | Mapa de incidentes en tiempo real | Must | 8 | Sprint 2 |
| 10 | US-08 | EP-02 | Adjuntar evidencia multimedia | Must | 5 | Sprint 2 |
| 11 | US-11 | EP-03 | Validar o descartar un reporte cercano | Must | 5 | Sprint 2 |
| 12 | US-12 | EP-03 | Publicación por umbral de validación | Must | 5 | Sprint 2 |
| 13 | TS-06 | EP-09 | Despliegue automatizado en entorno cloud | Must | 8 | Sprint 2 |
| 14 | US-21 | EP-05 | Detalle del incidente | Must | 3 | Sprint 3 |
| 15 | US-19 | EP-05 | Filtros de consulta | Should | 3 | Sprint 3 |
| 16 | US-13 | EP-03 | Cálculo de reputación | Should | 5 | Sprint 3 |
| 17 | US-14 | EP-04 | Detección de reportes duplicados | Should | 8 | Sprint 3 |
| 18 | US-10 | EP-02 | Historial de reportes propios | Should | 3 | Sprint 3 |
| 19 | TS-05 | EP-09 | Análisis estático de código y calidad | Should | 3 | Sprint 3 |
| 20 | US-20 | EP-05 | Mapa de calor por franja horaria | Must | 13 | Sprint 4 |
| 21 | US-15 | EP-04 | Detección de reportes falsos | Should | 13 | Sprint 4 |
| 22 | US-16 | EP-04 | Moderación de reportes | Should | 5 | Sprint 4 |
| 23 | US-04 | EP-01 | Reporte anónimo | Should | 3 | Sprint 4 |
| 24 | US-09 | EP-02 | Edición y eliminación de reporte propio | Should | 3 | Sprint 4 |
| 25 | TS-08 | EP-09 | Gestión de secretos y configuración | Should | 3 | Sprint 4 |
| 26 | US-22 | EP-06 | Sugerencia de ruta de menor riesgo | Must | 13 | Sprint 5 |
| 27 | US-26 | EP-08 | Acceso institucional al panel | Must | 5 | Sprint 5 |
| 28 | US-27 | EP-08 | Indicadores por zona, horario y tipo | Must | 8 | Sprint 5 |
| 29 | US-24 | EP-07 | Alerta de proximidad | Should | 5 | Sprint 5 |
| 30 | TS-07 | EP-09 | Observabilidad básica | Should | 5 | Sprint 5 |
| 31 | US-03 | EP-01 | Gestión de perfil | Could | 3 | Sprint 6 |
| 32 | US-05 | EP-01 | Consulta de reputación | Could | 2 | Sprint 6 |
| 33 | US-28 | EP-08 | Evolución temporal y efecto de la intervención | Could | 5 | Sprint 6 |
| 34 | US-29 | EP-08 | Exportación de datos | Could | 3 | Sprint 6 |
| 35 | US-23 | EP-06 | Comparación de rutas por horario | Could | 5 | Sprint 6 |
| 36 | US-25 | EP-07 | Resumen por zona de interés | Could | 3 | Sprint 6 |
| 37 | US-17 | EP-04 | Apelación del autor | Won't (este ciclo) | 3 | Backlog |

**Resumen de la estimación.**

| Indicador | Valor |
| :--- | :---: |
| Total de ítems del backlog inicial | 37 |
| Total de story points estimados | 189 |
| Ítems *Must have* | 18 |
| Ítems *Should have* | 12 |
| Ítems *Could have* | 6 |
| Ítems *Won't have* en este ciclo | 1 |
| Technical Stories | 8 |

---

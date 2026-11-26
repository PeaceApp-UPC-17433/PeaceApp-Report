# Evidencias de la sección 4.4

Salidas de las ejecuciones citadas en 4.4.1 a 4.4.5, copiadas sin editar. La única excepción son los resúmenes JSON de k6: se les quitó `setup_data`, que traía los JWT de los usuarios de prueba.

Todas las corridas son locales, del 26 de noviembre de 2026 (hora de Lima), contra el stack de Docker Compose de `peaceapp-platform` con `docker-compose.ci.yml`. Docker Desktop tenía 12 CPU lógicas. Cuando `advanced-tests.yml` corra en GitHub Actions, el artefacto `advanced-tests` de cada ejecución trae los mismos archivos.

## Versiones probadas

| Repositorio | Rama | Commit |
|---|---|---|
| `identity-service` | `develop` | `27e96fc` |
| `incident-service` | `tests/pruebas-avanzadas` | `4247a99` |
| `trust-service` | `develop` | `e7c43d6` |
| `alerts-service` | `develop` | `76c4f8a` |
| `community-service` | `develop` | `2ca363b` |
| `notification-service` | `tests/pruebas-avanzadas` | `af54dd7` |
| `api-gateway` | `develop` | `3060df3` |
| `PeaceApp-AppWeb` | `tests/pruebas-avanzadas` | `5f7e913` (accesibilidad) y `c7eda8b` (cabeceras de seguridad) |
| `peaceapp-platform` | `tests/pruebas-avanzadas` | suite `tests/` |

## Contenido

| Carpeta | Archivo | Qué es |
|---|---|---|
| `4.4.1` | `humo-api.txt` | Humo de API (`scripts/e2e.sh`): 92 verificaciones, incluidos los 4 controles de acceso por objeto |
| | `junit.xml`, `results.json` | Resultado de Playwright en Chromium y Firefox |
| | `playwright-report.html` | Reporte HTML de Playwright (se abre en el navegador) |
| `4.4.2` | `TEST-*ResendProviderIntegrationTest.xml`, `resend-red.txt`, `resend-green.txt` | Resend con WireMock: la prueba en rojo antes de corregir los reintentos y en verde después |
| | `TEST-*EvidenceStorageAzuriteTest.xml`, `azurite-mutacion.txt` | Azure Blob con Azurite y la mutación manual que la prueba detecta |
| `4.4.3` | `load-*` | Carga de 20 req/s: resumen de k6, dashboard HTML, CPU por contenedor y colas de RabbitMQ |
| | `stress-*` | Estrés por escalones: lo mismo, más `stress-analysis.md` (tabla por escalón) y `stress-drain.csv` (drenado de colas) |
| | `diagnostico-350rps.txt` | Ráfaga a 350 req/s con muestreo de consultas activas en PostgreSQL |
| `4.4.4` | `prod-headers-antes.txt`, `prod-actuator.txt` | Cabeceras y endpoints de gestión de producción antes de la corrección (solo lectura con `curl`) |
| | `zap-baseline-antes/` | ZAP baseline contra la web con la configuración de nginx de `develop` |
| | `zap-baseline/` | ZAP baseline contra la web corregida |
| | `zap-api-antes/` | ZAP API scan autenticado de los 5 servicios, a través del gateway, antes de las correcciones de `identity-service` e `incident-service` |
| | `zap-api/` | El mismo API scan con las correcciones y el falso positivo revisado (`false-positives.tsv`) |
| | `dlq-correos-invalidos.txt`, `dlq-despues.txt` | Mensajes en las DLQ de RabbitMQ después del API scan, antes y después de la corrección del correo |
| | `zap-full/` | ZAP full scan (activo) de la web. Pendiente: la corrida local se interrumpió por fallas de Docker Desktop |
| | `lighthouse-con-csp-summary.json` | Lighthouse con la CSP activa, en las 7 pantallas |
| `4.4.5` | `antes/axe/`, `despues/axe/` | Violaciones de axe por pantalla y navegador, antes y después de las correcciones |
| | `antes/lighthouse-*`, `despues/lighthouse-*` | Puntajes de Lighthouse por pantalla y el reporte HTML de la pantalla de reportes, la de puntaje más bajo al inicio |

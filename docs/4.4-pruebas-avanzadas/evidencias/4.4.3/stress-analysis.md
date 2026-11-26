Inicio del escenario: estimado (último muestreo - duración del escenario).

| Escalón (req/s) | Logrado (req/s) | p50 (ms) | p95 (ms) | p99 (ms) | Errores | CPU más alta (promedio de la meseta) | Mensajes en cola (máx.) |
|---|---|---|---|---|---|---|---|
| 25 | 25.0 | 5.5 | 9.7 | 13.4 | 0.00 % | rabbitmq 33 %, incident-service 9 %, api-gateway 9 % | 0 |
| 50 | 50.0 | 4.7 | 8.9 | 11.0 | 0.00 % | rabbitmq 90 %, api-gateway 17 %, incident-service 16 % | 0 |
| 100 | 100.0 | 4.9 | 10.1 | 14.0 | 0.00 % | rabbitmq 55 %, incident-service 30 %, api-gateway 21 % | 0 |
| 200 | 200.0 | 6.6 | 17.1 | 26.6 | 0.00 % | postgres 67 %, incident-service 64 %, api-gateway 49 % | 0 |
| 300 | 300.0 | 10.8 | 42.9 | 101.6 | 0.00 % | postgres 179 %, incident-service 110 %, api-gateway 72 % | 10 |
| 400 | 331.0 | 948.4 | 5372.6 | 7167.9 | 0.00 % | postgres 468 %, incident-service 184 %, api-gateway 129 % | 51 |
| 600 | 338.6 | 3107.0 | 4559.7 | 5450.3 | 0.00 % | postgres 517 %, incident-service 181 %, api-gateway 104 % | 49 |

Mensajes pendientes al terminar la carga: sin muestras; las colas no se vaciaron durante el muestreo.

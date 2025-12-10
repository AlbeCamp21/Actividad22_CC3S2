## Captura de pantalla

![img1](/img/img_1.png)

## Explicación

**1.** `job="otel-collector"`

Este label almacena el nombre del servicio que prometheus está "scrapeando". Esto es definido en la configuración del `.yml` y sirve para agrupar targets similares bajo un mismo nombre. En este ocasión el job agrupa todo lo relacionado con lo que genera OTEL.

**2.** `instance="otel-collector:8889"`

Este label nos indica la dirección específica del target (comunmente `host:puerto`). En esta ocasión nos muestra que prometheus está obteniendo métricas desde el contenedor `otel-collector` en el puerto `8889`.

## Consultas PromQL

**1.** `up`

- Tipo gauge
- Representa el estado de cada target screapado, 1 para UP y 0 para DOWN

**2.** `up{job="otel-collector"}`

- Tipo gauge
- Representa el estado del target del job `otel-collector`

**3.** `http_server_requests_duration_seconds_count`

- Tipo: counter
- Representa la cantidad total de solicitudes HTTP que se registraron por la aplicación

## Mejores prácticas

- Primero, usar counters para medir los errores (en vez de gauges).
- Mantener los nombres de las métricas constantes, para que sea fácil identificar.
- Añadir labels descriptivos.
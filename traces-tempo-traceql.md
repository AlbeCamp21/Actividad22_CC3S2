## Captura de pantalla

![img_3](/img/img_3.png)

## Consultas TraceQL

- `{resource.service.name="demo-app"}`
- `{resource.service.name="demo-app", http.target="/api/v1/error"}`

## Spans

- Primero, un span principal, raiz, que corresponde a la petición HTTP principal (`GET /api/v1/items`, por ejemplo).
- Luego, diversos spans internos generados por librerias como OTEL, por ejemplo: manejo de solicitudes, operaciones, etc.
- Por último, para ciertos casos (como `api/v1/error`), aparece un span marcado como error y atributos donde se indica el código de estado, el método HTTP y el mensaje de fallo.

## Relación con logs y métricas

**1.** Métricas (Prometheus)

Nos permite ver cuantas veces se llama a cada endpoint, además de la tasa de error y la latencia.

**2.** Logs (Loki)

Nos muestra mensajes muy detallados del procesamiento, incluyendo errores o advertencias.

**3.** Trazas (Tempo)

Nos permite ver el recorrido completo de una petición y relacionarlo con los logs y métricas que estén asociadas al mismo trazo.

## Protocolos y tracing

**1.** OpenTelemetry (OTEL)

Es un estándar que define cómo se va a generar, procesar y exportar las trazas, métricas y logs.

**2.** Propagación de contexto

Es un mecanismo que transmite el `trace_id` y el `span_id` entre los servicios, esto nos permite vincular todos los spans de una misma operación.
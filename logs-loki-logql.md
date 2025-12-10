## Captura de pantalla

![img_2](/img/img_2.png)

## Expresiones LogQL usadas

- `{job="demo-app"}`
- `{job="demo-app"} |= "ERROR"`
- `{job="demo-app"} |= "WARNING"`
- `{job="demo-app"} |= "/api/v1/error"`

## Contexto DevSecOps

- Serviría para detectar patrones de fallos que sean repetidos (errores 5XX por ejemplo)
- Para identificar comportameintos sospechosos, por ejemplo: múltiples intentos fallidos o intentar accessos a rutas no autorizadas
- Relacionar logs con las alertas de seguridad y métricas con el fin de responder más rápidamente a incidentes.
- Para la realización de auditorias y trazabilidad
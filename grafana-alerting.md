## Captura de pantalla

![img_4](/img/img_4.png)

## Metrica usada

Para la alerta utilicé consulta TraceQL desde Tempo que identifica respuestas con error 5xx en la aplicación:

```
{resource.service.name="demo-app" && .http.status_code >= 500} | rate()
```

## Condición y duración

- **Condición:** error_rate_5xx > 0.3  
- **Duración:** 5 minutos continuos  
- **Motivo:** El umbral de 0.3 nos indica una frecuencia significativa de errores. Los 5 minutos nos ayuda a evitar falsos positivos por fallos aislados.

## Encaje en equipos

### DevOps/DevSecOps

Esta alerta nos permite detectar rápidamente fallos críticos en el sistema, facilitando así la relación con logs (Loki) y trazas (Tempo). También se integra fácilmente con flujos de CI/CD para lanzar acciones como rollback o análisis luego de ciertos incidentes.

### Blue Team / SRE

Un aumento en los errores 5xx nos puede indicar un mal funcionamiento, fallos en dependencias o inclusive actividad sospechosa como fuzzing o ataques DoS. Entonces, esta alerta actúa como mecanismo de detección temprana, contribuyendo así al monitoreo continuo y manteniendo la estabilidad del sistema.
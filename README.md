# Actividad22_CC3S2

## Descripción de la actividad
Esta actividad consiste en levantar un stack de observabilidad basado en Grafana, Prometheus, Loki, Tempo y un servidor MCP. Se deben generar métricas, logs y trazas, crear paneles y reglas de alerta, y documentar los resultados obtenidos.

## Instrucciones para reproducir

### Levantar el stack

```
make up
```

### Generar tráfico hacia la demo-app

```
make demo-traffic
```

## URLs de acceso
- Aplicación: http://localhost:8000/docs  
- Grafana: http://localhost:3000  
- Prometheus: http://localhost:9090  
- MCP: http://localhost:8080/docs  

## Evidencias
Los archivos generados se encuentran en:
- metrics-prometheus.md  
- logs-loki-logql.md  
- traces-tempo-traceql.md  
- grafana-alerting.md  
- devsecops-observabilidad.md  
- dashboard-actividad22.json  
- observabilidad-telematria.md

Cada uno contiene capturas o descripciones según la actividad.
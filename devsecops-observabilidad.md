## Observabilidad en el ciclo DevSecOps

La observabilidad forma parte de todas las fases del ciclo DevSecOps y nos permite comprender el comportamiento del sistema de forma continua.

Ahora, en la fase de planificación y diseño, se definen los requisitos de monitoreo, los datos que deben recolectarse y las métricas importantes. En esta etapa también se decide qué información se debe exponer desde la aplicación, cómo se formará el código y qué herramientas formarán parte del stack de observabilidad.

Luego, durante la construcción y las pruebas (CI), la observabilidad permite validar que la aplicación genera métricas, logs y trazas de forma correcta.
Esto nos ayuda a detectar fallos en la organización del sistema antes de llegar a entornos avanzados.

En la etapa de despliegue (CD), la observabilidad nos ayuda a tomar decisiones informadas. Si los datos no cumplen con ciertos valores esperados, el despliegue puede detenerse, reduciendo riesgos y evitando que fallos lleguen a producción.

En la fase de operación y respuesta a incidentes, la observabilidad es fundamental. Las métricas nos permiten detectar degradaciones, los logs nos muestran detalles de los fallos y las trazas nos ayudan a localizar los lugares exactos donde ocurre un problema. Además, los paneles nos permiten revisar el estado del sistema en tiempo real.

Por último, la mejora continua consiste en analizar los datos históricos recolectados y, a partir de tendencias de errores, latencias, trazas o eventos inusuales, se pueda aplicar ajustes en la arquitectura del sistema. La observabilidad también nos permite evaluar el impacto que tienen los cambios recientes y validar si las soluciones aplicadas resolvieron problemas previos.

## Gates DevSecOps basados en observabilidad

**1.** Gate previo al despliegue

El despliegue solo va a continuar si el entorno de staging muestra disponibilidad correcta y métricas sin errores.

**2.** Gate post-deploy

Después del despliegue, se monitorea durante varios minutos el panel de métricas. Si el "error rate" supera el umbral definido o la latencia aumenta de forma sostenida, el pipeline puede activar un rollback automático.

**3.** Gate de seguridad

Se bloquea la siguiente fase si en los logs aparecen patrones sospechosos, como intentos repetidos de acceso a rutas no válidas, o si en las trazas se observan tiempos extraños que podrían indicar fallos o ataques.
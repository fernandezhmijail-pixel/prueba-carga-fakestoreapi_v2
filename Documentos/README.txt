PRUEBA DE PERFORMANCE - FAKESTOREAPI

1. OBJETIVO

Ejecutar pruebas de rendimiento sobre el servicio fakestoreapi mediante Apache JMeter, evaluando métricas clave como TPS, tiempos de respuesta y tasa de error bajo diferentes niveles de carga.

2. TECNOLOGÍAS UTILIZADAS
Apache JMeter: 5.6.3
Java JDK: 8 o superior
Sistema operativo: Windows 10/11
Formato de resultados: JTL (CSV)
Herramientas de análisis: JMeter Summary Report / Aggregate Report

3. ESTRUCTURA DEL PROYECTO
Test Plan: fakestoreapi.jmx
Escenarios:
Línea base
Carga media
Carga alta
Archivos de salida:
baseline.jtl
media.jtl
alta.jtl

4. CONFIGURACIÓN DE ESCENARIOS
Escenario	Threads (VUs)	Ramp-up	Loop
Línea base	20	20 seg	10
Carga media	80	80 seg	10
Carga alta	140	140 seg	10

5. PASOS DE EJECUCIÓN
Abrir Apache JMeter.
Cargar el archivo:
fakestoreapi.jmx
Validar configuración:
URL del endpoint
Headers HTTP
CSV Data Set (si aplica)
Configurar listeners:
Summary Report
Aggregate Report
View Results Tree (solo para debugging)
Ejecutar cada escenario de forma independiente:
Ajustar número de Threads según escenario
Ejecutar prueba
Guardar resultados:
Exportar archivo .jtl por escenario

6. CÁLCULO DE TPS (Transactions per Second)

Fórmula utilizada:

TPS = Total de transacciones / Duración total (segundos)

Resultados obtenidos:

Línea base: 2.05 TPS
Carga media: 7.34 TPS
Carga alta: 4.57 TPS

7. CONSIDERACIONES IMPORTANTES
Durante las ejecuciones se presentó error 523 (Origin Unreachable)
Esto afecta directamente:
TPS
Tasa de error
Tiempos de respuesta
Se recomienda validar disponibilidad del API antes de ejecutar pruebas

8. RECOMENDACIONES DE EJECUCIÓN
Validar endpoint activo antes de pruebas
Configurar ramp-up progresivo
Evitar ejecutar con listeners pesados en pruebas grandes
Ejecutar en modo non-GUI para pruebas de alta carga

Comando sugerido:

jmeter -n -t fakestoreapi.jmx -l resultados.jtl

9. RESULTADOS DE REFERENCIA (EJERCICIO)
Success rate: 97.55%
Tiempo promedio: 191 ms
Error rate: 2.44%
p95: 1.28 s

Estos valores representan el comportamiento esperado del sistema en condiciones normales.
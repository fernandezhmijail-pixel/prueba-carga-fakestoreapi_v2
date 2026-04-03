INSTRUCCIONES DE EJECUCIÓN DE LA PRUEBA DE CARGA

1. Requerimientos:
   - Java JDK 8 o superior
   - Apache JMeter 5.6.3
   - Sistema operativo: Windows 10 / 11 (recomendado)
   - Navegador web para abrir el dashboard HTML (Chrome, Edge, Firefox)
   - Carpeta de trabajo: C:\Users\susan\OneDrive\Desktop\Trabajo Ayesa\Performance

2. Archivos necesarios:
   - Test Plan: Test Plan fakestoreapi.jmx
   - Resultados: resultados.jtl (si ya se generaron)
   - Carpeta de dashboard: reporte (o se generará)

3. Paso a paso para ejecutar la prueba:

   A) Abrir CMD y navegar a la carpeta de JMeter:
      cd C:\Users\susan\OneDrive\Desktop\Trabajo Ayesa\Performance\apache-jmeter-5.6.3\bin

   B) Ejecutar prueba en modo no GUI:
      jmeter.bat -n -t "C:\Users\susan\OneDrive\Desktop\Trabajo Ayesa\Performance\Test Plan fakestoreapi.jmx" -l "C:\Users\susan\OneDrive\Desktop\Trabajo Ayesa\Performance\resultados.jtl"

   C) Generar el dashboard HTML:
      - Si la carpeta 'reporte' ya existe, vaciarla o eliminarla.
      - Ejecutar:
        jmeter.bat -g "C:\Users\susan\OneDrive\Desktop\Trabajo Ayesa\Performance\resultados.jtl" -o "C:\Users\susan\OneDrive\Desktop\Trabajo Ayesa\Performance\reporte"

   D) Abrir el dashboard:
      - Ir a la carpeta 'reporte'
      - Abrir el archivo index.html con un navegador
      - Revisar los gráficos:
          * Active Threads Over Time → Usuarios virtuales (VUs)
          * Transactions per Second → Requests por segundo
          * Response Times Over Time → Latencias de respuesta

4. Notas adicionales:
   - El dashboard utiliza estilos CSS (dashboard.css), no modificar manualmente.
   - Todos los datos de la prueba se guardan en resultados.jtl.
   - Para ejecutar de nuevo, borrar la carpeta 'reporte' para evitar errores.
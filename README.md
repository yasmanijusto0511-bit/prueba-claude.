# prueba-claude.

## Indicador "Los 4 Fantásticos" de Oliver Vélez

- `fab4_velez.pine`: indicador de **TradingView (Pine Script v6)**.
- `notas_4_fantasticos_velez.md`: notas de estudio del video de Vélez, con los tiempos de cada regla.

**Uso:** abre el Editor de Pine en TradingView, pega el contenido de `fab4_velez.pine` y pulsa "Añadir al gráfico". Úsalo en un gráfico de **2 minutos**, como indica Vélez.

**Qué dibuja:**
- La **caja** de los 4 Fantásticos: SMA 20, SMA 200, cierre previo y máximo/mínimo de los últimos ~45 minutos de la sesión previa. Va del elemento más alto al más bajo.
- La **ubicación**: si el día abre por encima de la caja (solo largos) o por debajo (solo cortos).
- El **gatillo** (línea amarilla) y el **stop** (línea roja) del "juego del color".

**Reglas del gatillo** (ejemplo bajista; el alcista es el espejo):
- La referencia es la primera barra del día.
- Entra en corto cuando una barra posterior rompe el bajo de la referencia. El stop va por encima de su alto.
- Si aparece una barra verde, pasa a ser la nueva referencia hasta que una barra rompa su bajo.
- Cada nueva barra de color opuesto con rotura da otra entrada (hasta 5 por defecto).

**Parámetros configurables:** zona horaria y sesión regular, longitudes de las SMA, minutos finales (45), máximo de entradas y ventana de operación.

**Límites:**
- El video no define objetivos ni salidas, así que el indicador solo marca ubicación, gatillo y stop.
- Cada entrada se evalúa por separado y la tabla muestra el stop de la última.
- No resuelve el orden dentro de una misma barra.
- No ha sido compilado ni probado en TradingView.
- Es solo educativo, no asesoría financiera.

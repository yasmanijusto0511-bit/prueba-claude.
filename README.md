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

**Salida R1** (regla propia del usuario, no es de Vélez):
- Al ganar 1 cabeza (+1R, lo mismo que arriesgaba de la entrada al stop) marca "R1 ½": se vende la mitad y el stop de la otra mitad pasa al precio de entrada.
- Después el stop se lleva vela a vela. Solo cuentan las velas de tu color de tendencia que no sean "mini": en largo, el stop sube al bajo de cada vela verde; en corto, baja al alto de cada vela roja. Nunca se afloja.
- Sigue hasta que el precio toque el stop móvil, aunque pase la primera hora.
- "Mini" = rango menor a 0.5 veces el rango promedio de las últimas 10 velas. Es un valor por defecto mío y es ajustable.
- Solo se sigue la última entrada del día.

**Filtro de entradas:** por defecto una vela mini no puede ser la referencia del gatillo, para no entrar en cualquier vela. Se puede apagar en "No entrar con una vela mini como referencia".

**Ventana:** solo se opera la **primera hora** del mercado (60 minutos desde la apertura). Se puede cambiar en los parámetros.

**Parámetros configurables:** zona horaria y sesión regular, longitudes de las SMA, minutos finales (45), máximo de entradas y ventana de operación (60).

**Límites:**
- El video no define objetivos ni salidas; la salida R1 es la del usuario.
- El indicador sigue solo la última entrada (stop, R1 y stop móvil).
- No resuelve el orden dentro de una misma barra.
- No ha sido compilado ni probado en TradingView.
- Es solo educativo, no asesoría financiera.

# prueba-claude.

## Indicador "Velas de los motores y Muñeco" (`velas_munecos.pine`)

Segundo indicador de TradingView (Pine Script v6). Marca las señales de entrada de las técnicas de los bots de Yasmani, con los números del documento de traspaso. Activa solo las técnicas del marco de tiempo del gráfico:

| Gráfico | Técnicas |
|---|---|
| **5 min** | 1A Muñeco A (envolvente), 1B Muñeco B (cola de piso en la SMA20), 2 Rebote 4 velas, 4 Toro en la SMA20, M3 vela toro dominante |
| **2 min** | 3 Toro 180, 5 Cola de techo (corto), 6 Roja grandota (corto), 7 Cola de piso lejos |

Para cada señal dibuja la flecha, el precio de entrada, el **stop inicial** y el nivel **R1** (una cabeza: entrada ± riesgo). Incluye tabla de la última señal y alertas.

**No incluye todavía:** las salidas del bot (2.ª y 3.ª verde, seguimiento 2 velas atrás, mitad en vela gigante), la agregada, la espera tras vela gigante, la regla de días de gap ni la variante "si antes sale una verde" de las colas. La Roja grandota se marca al cierre de la vela, no en vivo. No ha sido compilado ni probado en TradingView.

Nota: en los documentos de los bots, el "Filtro Fab 4 de Velez" figura como probado y descartado en las compras del Muñeco.

## Indicador "Los 4 Fantásticos" de Oliver Vélez (`fab4_velez.pine`)

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

**Ubicaciones (zonas 1, 2 y 3):** la apertura se clasifica por su distancia a la caja, en velas promedio de 50. Zona 1: justo fuera. Zona 2: un poco más lejos. Zona 3: sobreextendido, desde 4 velas (el valor que usan tus bots). Según el video "La magia de las ubicaciones de trading" y tu documento de traspaso: en zona 1 y 2 se opera a favor (más fuerte en la 1); en zona 3 no se opera a favor, y por defecto el indicador **no opera la zona 3**. También hay una opción "En contra" (corto arriba, largo abajo), experimental. Los límites de zona 1 y 2 (2 velas) son un valor mío por defecto. En pruebas con 4 acciones y 3 meses, dejar de operar la zona 3 pasó de −0.02 a +0.06 R por entrada, una mejora modesta que aún cae dentro del margen de error.

**Estado estrecho (medias comprimidas):** siguiendo a Vélez, solo se opera el día si la SMA 20 y la SMA 200 estaban relativamente cerca una de la otra al cierre previo. Por defecto el umbral es 3 velas promedio (rango promedio de 50 velas), ajustable en "Los 4 Fantásticos". Si las medias están abiertas, la etiqueta de apertura lo dice y ese día no hay entradas. Vélez no da un número; el 3 es un valor por defecto mío.

**Salida R1** (regla propia del usuario, no es de Vélez):
- Al ganar 1 cabeza (+1R, lo mismo que arriesgaba de la entrada al stop) marca "R1 ½": se vende la mitad y el stop de la otra mitad pasa al precio de entrada.
- Después el stop se lleva vela a vela. Solo cuentan las velas de tu color de tendencia que no sean "mini": en largo, el stop sube al bajo de cada vela verde; en corto, baja al alto de cada vela roja. Nunca se afloja.
- Sigue hasta que el precio toque el stop móvil, aunque pase la primera hora.
- "Mini" = rango menor a 0.5 veces el rango promedio de las últimas 10 velas. Es un valor por defecto mío y es ajustable.
- Solo se sigue la última entrada del día.

**Filtro de entradas:** por defecto una vela mini no puede ser la referencia del gatillo, para no entrar en cualquier vela. Se puede apagar en "No entrar con una vela mini como referencia".

**Stop del otro lado de la media:** si el precio de entrada está muy cerca de la SMA 20 o de la SMA 200 (a una vela promedio de 20 o menos, ajustable), el stop va encima de esa media en cortos o debajo en largos, y no en el extremo de la vela de referencia. Si están cerca las dos, va del otro lado de la más lejana. Se puede apagar en "Stop del otro lado de la SMA20/SMA200…".

**Entrada anticipada por tamaño:** además de entrar al superar la vela de color opuesto, entra en cuanto la vela en formación recorre desde su apertura el tamaño de una vela grande (cuerpo ≥ 2.5 veces el promedio de 20 velas y ≥ 1.5 veces el ATR de 14, como en "Los 3 motores"). Se puede apagar. En pruebas con AAPL casi no cambia el resultado.

**Ventana:** solo se opera la **primera hora** del mercado (60 minutos desde la apertura). Se puede cambiar en los parámetros.

**Parámetros configurables:** zona horaria y sesión regular, longitudes de las SMA, minutos finales (45), máximo de entradas y ventana de operación (60).

**Límites:**
- El video no define objetivos ni salidas; la salida R1 es la del usuario.
- El indicador sigue solo la última entrada (stop, R1 y stop móvil).
- No resuelve el orden dentro de una misma barra.
- No ha sido compilado ni probado en TradingView.
- Es solo educativo, no asesoría financiera.

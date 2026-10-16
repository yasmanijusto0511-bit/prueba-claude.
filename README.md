# prueba-claude.

## Indicador "Los 4 Fantásticos" de Oliver Vélez

`fab4_velez.pine` es un indicador de **TradingView (Pine Script v6)**.

**Uso:** abre el Editor de Pine en TradingView, pega el contenido del archivo y pulsa "Añadir al gráfico". Úsalo en un gráfico intradía (ideal 2 minutos).

**Qué dibuja:** una zona (caja) construida con los 4 elementos de la sesión anterior:
SMA 200, SMA 20, cierre previo y máximo/mínimo del tramo final de la sesión.

| Apertura | Lectura |
|---|---|
| Por encima de la zona | Sesgo alcista (largos) |
| Por debajo de la zona | Sesgo bajista (cortos) |
| Dentro de la zona | Zona trampa, no operar |

El sesgo se confirma con N cierres consecutivos fuera de la caja (por defecto 2) durante la primera hora, y se invalida si el precio vuelve a cerrar dentro. Incluye tabla de resumen y alertas.

**Parámetros configurables:** zona horaria y sesión regular, longitudes de las SMA, minutos finales de la sesión previa (30–60 según la fuente), cierres de confirmación y duración de la ventana.

**Aviso:** está basado en interpretaciones públicas del método, no en material original de Vélez. No ha sido compilado ni probado en TradingView. Es solo educativo, no asesoría financiera.

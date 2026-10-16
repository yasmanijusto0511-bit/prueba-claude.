# Los 4 Fantásticos de Oliver Vélez – notas de estudio

Fuente: transcripción automática en español de un video de Oliver Velez Trading En Español (28:03, "Estrategia de Trading Poderosa…", miniatura "30 minutos de trading").
La transcripción se leyó desde grabaciones de pantalla. Es autogenerada y tiene errores: "tata" = data, "baba" = BABA (Alibaba), "stock de protección" = stop, "barra toros" = barra alcista, "Elite número 2" = ítem número 2.
Quedaron cinco huecos cortos (10–35 s) sin leer: 18:55–19:10, 19:41–19:50, 21:22–21:44, 22:17–22:50 y 26:18–26:41. Parecen ejemplos, pero no los leí.
Los tiempos entre paréntesis son los del video.

## 1. Los "5 cosas que necesitamos" (diapositiva, 0:00)
1. Cuenta de 50k–100k+ USD (requisito de day trading, no entra en el indicador).
2. SMA 20.
3. SMA 200.
4. Cierre previo.
5. Rango de precio del final del día anterior.

Los **4 Fantásticos son los ítems 2 a 5**.

## 2. Cómo se construye la caja (0:00–5:00, 14:12–15:03)
- **Ítem 1 (SMA 20)** y **ítem 2 (SMA 200)**: sus valores al cierre del día anterior. Se hace *antes* de que abra el mercado.
- **Ítem 3**: precio de cierre del día anterior.
- **Ítem 4**: máximo y mínimo de los últimos **~45 minutos** de la sesión previa (2:19–2:36). Dice: "no quiero una hora, no quiero dos horas… los últimos 45 minutos aproximadamente".
- **Caja**: del elemento **más alto** de los cuatro al **más bajo** (4:04, 14:39), incluidos el máximo y el mínimo del tramo final. Se extiende hacia el futuro, es decir, el día de hoy.
- La caja actúa como **techo o resistencia** si el precio está debajo (18:00).
- Ejemplos de la caja en el video: la SMA 200 es el piso en AAPL (4:04) y en MSFT/BABA (14:46, 17:51).

## 3. Ubicación (5:00–6:30, 8:19)
- Abre **por encima** de la caja: sesgo alcista. Las probabilidades de continuación alcista son mayores que las bajistas.
- Abre **por debajo** de la caja: sesgo bajista.
- Aclara que no es que lo contrario sea imposible, sino que es lo que ocurre **más a menudo** (5:36).
- La ubicación sola **no basta**: hace falta un gatillo de entrada (6:32, 8:42).
- No dice nada explícito sobre abrir *dentro* de la caja en este video. La "zona trampa" viene de scripts de terceros.

## 4. El "juego del color" (6:40–12:34)
- Gráfico de **2 minutos** (6:56), pensado para el trading de corto plazo en la apertura.
- Color de la primera barra vs. ubicación:
  - Debajo de la caja = territorio **rojo**. Arriba = territorio **verde** (7:28–7:36).
  - Coincidencia (rojo abajo, verde arriba) = **confirmación** (7:13–8:09).
  - Si no coincide, hay **conflicto**.

### Entrada 1 – método de confirmación (8:42–10:00)
Ejemplo bajista, abierto debajo de la caja con primera barra roja:
- **Entrada:** corto cuando cualquier barra siguiente **rompe el bajo de la primera barra**.
- **Stop:** por encima del **alto de la primera barra**. "Arriesgamos una sola barra."
- Caso alcista: el espejo.

### Entrada 2 – método del color opuesto (10:09–12:34)
Abre debajo de la caja pero la primera barra es **verde** (conflicto, "toros en territorio negativo").
- Se **marca el bajo de la barra verde**.
- Cuando **una barra roja rompe el bajo de la barra verde**, se entra en esa barra roja. Se entra **en el instante** en que se rompe el bajo, sin esperar al cierre de la barra (18:47–18:55).
- **Stop:** por encima del alto de la barra verde.
- Si aparece otra barra verde que no rompe, se **marca su bajo**. Se sigue marcando el bajo de las barras verdes hasta que una barra rompa el bajo de la última (19:57–20:26).
- Si no hay coincidencia ("verde en territorio rojo"), no se entra de inmediato. Hay que esperar el gatillo (18:24–18:47).

### Entradas adicionales y reintentos (12:34–12:59, 15:52–16:17, 24:16–25:36)
- Cada vez que aparece una barra de color opuesto cuyo bajo es roto, hay **otra entrada** (entrada 2, 3, 4…).
- En una tendencia larga hay entre **2 y 5** oportunidades de entrada. Muchas veces son 2–3 (22:55–23:18).
- Tras un stop-out hay que dar **un segundo intento**, sobre todo si ocurre casi de inmediato (24:53–25:18).

## 5. Gestión de riesgo (9:14–9:22, 19:00–19:34, 22:09)
- Se arriesga **una sola barra**. Dice que casi siempre se pierde una barra cuando falla.
- La recompensa puede ser de 3, 8, 12 o 14 barras: "arriesgar una barra, ganar ocho barras" (19:10–19:26).
- En barras pequeñas se puede ignorar la cola. Algunos traders usan el cuerpo y otros la cola o mecha (21:44–22:09).
- No define objetivos ni salidas en este video.

## 6. Cuándo bajan las probabilidades (13:00–13:41, 16:25–16:57, 20:35–20:51)
- Cuanto más lejos de la caja, más baja la probabilidad de continuación.
- Al inicio de la jugada hay la mayor probabilidad. En el medio es decente. Varias piernas adentro, las probabilidades empiezan a cambiar y es más común un giro.
- Cuando la SMA 20 se separa mucho de la SMA 200 ("amplitud"), la confiabilidad de seguir la tendencia baja.

## 7. Dónde lo aplica
- Acciones muy líquidas y populares: AAPL, MSFT, BABA, FB/META, NVDA.
- Los ejemplos son principalmente bajistas, y cierra con un ejemplo alcista (26:41–27:20).

## 8. Diferencias con lo que había supuesto antes
| Antes (fuentes de terceros) | Ahora (Vélez en el video) |
|---|---|
| Confirmar con N cierres fuera de la caja | Color de la primera barra de 2 min coincide con la ubicación; entrada al romper el bajo (o el alto) |
| Invalidar si cierra dentro de la caja | No lo menciona; el stop es el alto/bajo de la barra de referencia |
| Ventana de 1 hora | No fija ventana; habla de oportunidades durante el día |
| Zona trampa dentro de la caja | No se menciona en este video |

# 🗺️Validación Geográfica de la Señal de Reversión (RSI)

## 📌Descripción del Proyecto

Este proyecto analiza la efectividad de la señal de sobrecompra (RSI > 70) como indicador de reversión bajista, segmentando los resultados por país de origen del activo.
El objetivo es identificar diferencias estructurales en la eficiencia del mercado y en el comportamiento de los traders según la geografía.

La hipótesis central es que no todos los mercados reaccionan igual ante señales técnicas clásicas, y que en algunos países la señal de RSI puede anticipar caídas de precio de forma más consistente que en otros.

## 📊Insight Clave

¿En qué país la señal de sobrecompra (RSI > 70) genera, en promedio, la mayor caída de precio en los 5 días posteriores?

Un mayor rendimiento negativo post-señal indica:
- Mayor eficiencia de la señal técnica
- Traders más reactivos o mercados menos tolerantes al exceso de momentum
- Mejor entorno para estrategias sistemáticas de reversión

## 🧩Metodología

- Identificación de la señal
- Se detectan todas las instancias donde RSI_14 > 70, interpretadas como señal de sobrecompra.
- Cálculo del rendimiento post-señal
- Se mide la variación porcentual del precio de cierre 5 días después de la señal.
- Se utiliza LEAD() para obtener el precio futuro sin lookahead bias.
- Segmentación geográfica
- Los resultados se agrupan por bolsa_mercado (país de origen del ticker).
- Filtro estadístico
- Se exige un mínimo de 5 señales por país para garantizar robustez en los promedios.
- Ranking
- Los países se ordenan por mayor caída promedio, validando dónde la señal de RSI funciona mejor como indicador de venta.
- Estructura de Datos Utilizada
- tickers
- Identificación del activo
- País / mercado de origen (bolsa_mercado)
- indicadores_tecnicos
- RSI de 14 períodos (rsi_14)
- Fecha del indicador
- precios_diarios
- Precio de cierre diario
- Base para calcular rendimientos futuros

## ✒️Output Esperado

- País / Mercado	Nº de Señales	Rendimiento Promedio 5D
- País A	12	-4.3%
- País B	9	-2.1%
- País C	7	-0.8%

📉 Valores más negativos indican una señal de venta más efectiva.

## 💼Valor de Negocio

- Optimiza estrategias cuantitativas de reversión filtrando por geografía.
- Permite ajustar modelos técnicos por país, evitando asumir eficiencia homogénea.
- Mejora la asignación internacional de capital en estrategias sistemáticas.
- Reduce ruido en señales RSI en mercados donde históricamente no funcionan bien.

## 📈Casos de Uso

- Hedge funds cuantitativos
- Trading sistemático internacional
- Research de microestructura de mercado
- Evaluación de eficiencia técnica por región

## 📝Notas Técnicas

- El análisis asume días naturales consecutivos (no ajusta por feriados).
- No se incluyen costos de transacción ni slippage.
- La señal RSI se evalúa como evento discreto, no como estado persistente.

## 👤Autora
Flavia Hepp Proyecto de SQL aplicó un análisis de riesgo basado en eventos.

****
🌍📉 **¿El RSI funciona igual en todos los mercados?**

El RSI > 70 es una de las señales más clásicas de sobrecompra.
Pero hay una pregunta clave que pocas veces se hace:

👉 ¿Funciona igual en todos los países?

💡 **Insight clave:**
La efectividad de la señal de reversión (RSI > 70) **varía significativamente según el mercado**.
En algunos países, estas señales están seguidas por caídas más pronunciadas en los días posteriores.

---

📊 **¿Qué medí?**

* Señales de sobrecompra (RSI > 70)
* Rendimiento a 5 días post-señal
* Segmentación por **bolsa / país de origen**
* Filtro mínimo de señales para robustez estadística

---

🧠 **¿Cómo interpretarlo?**

* Caídas más fuertes → señal más efectiva (mejor reversión)
* Caídas débiles o inexistentes → señal menos confiable
* Diferencias geográficas → comportamiento distinto de los traders

---

⚡ **¿Por qué importa?**

Porque rompe una suposición común:

👉 Los indicadores técnicos **no son universales**.

Esto permite:

* Adaptar estrategias según el mercado
* Detectar ineficiencias geográficas
* Mejorar modelos cuantitativos con contexto real

---

📌 Pregunta para la comunidad:
¿Aplican las mismas estrategias técnicas en todos los mercados… o las adaptan según el contexto?

#QuantFinance #Trading #DataScience #StockMarket #RSI #GlobalMarkets #Alpha #Analytics

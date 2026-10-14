# 🟡 Intermedio 01 — Completá las tablas y marcá las citas

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-2, RA-4

## 🧱 Estado inicial

Abrí [`paquetes-y-opiniones.html`](../recursos/portafolio-inicial/paquetes-y-opiniones.html) de la carpeta
`portafolio-inicial`. La página de Mateo tiene:

- Una tabla de **paquetes** (tres columnas) escrita sin título ni partes, con una aclaración suelta debajo.
- Los **horarios** de los sábados escritos en una oración.
- Dos **opiniones** de clientes y una **recomendación** de lectura, escritas como párrafos comunes.

## 🛠️ Proceso esperado

**Parte A — La tabla de paquetes.**

1. Agregar el título «Paquetes de fotos».
2. Agrupar la fila de encabezados en `thead` y las tres filas de datos en `tbody`.
3. Mover la aclaración «Los precios no incluyen el álbum impreso» a un pie de tabla, en **una sola celda que ocupe las tres
   columnas**.

**Parte B — Los horarios.**

1. Armar una segunda tabla con el título «Horarios de atención» donde «Sábados» **ocupe dos filas**: a su derecha, «Mañana»
   con «10 a 13 h» y, debajo, «Tarde» con «15 a 19 h».

**Parte C — Las citas.**

1. Marcar la opinión larga de Laura Díaz como **cita extensa**, con la dirección de la fuente
   `https://mateo-ruiz.example/opiniones/laura`, y dejar «— Laura Díaz, novia» **fuera** de la cita.
2. Marcar la frase «se nota el cuidado en cada foto» como **cita corta** dentro de su oración, con la fuente
   `https://mateo-ruiz.example/opiniones/diego`.
3. Marcar «Guía para preparar una sesión» como **título de una obra**.

## ✅ Resultado esperado

- ☑️ La tabla de paquetes con `caption`, `thead`, `tbody` y `tfoot`; el pie con `colspan="3"`.
- ☑️ La tabla de horarios con un `th` con `rowspan="2"` y una segunda fila de **solo dos celdas**.
- ☑️ Un `blockquote` con `cite`, la atribución fuera de él, un `q` con `cite` y un `cite` con el título de la guía.
- ☑️ Todas las etiquetas cerradas y bien anidadas.

## 🚧 Restricciones

- 🚫 No cambies los datos de las tablas ni los textos de las citas.
- 🚫 No pongas el nombre de la persona entre `<cite>`: esa etiqueta es para títulos de obras.
- 🚫 No escribas comillas a mano alrededor del `q`: las agrega el navegador.
- 🚫 No agregues CSS.

## 🎓 Resultados de aprendizaje

- RA-2: Presentar datos en una tabla, agrupando sus partes y combinando celdas.
- RA-4: Marcar citas y referencias y atribuir su fuente.

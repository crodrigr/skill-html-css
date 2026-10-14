# 📘 Ejemplo 02 — Tablas

## 🧱 Situación inicial

Lucía tiene sus tarifas en un cuadro: tres servicios, cada uno con su cantidad de páginas y su precio, más una aclaración que
vale para todos. Quiere publicarlo como una tabla, y también mostrar sus horarios de atención: lunes y martes, con un
horario de mañana y otro de tarde.

| Servicio | Páginas | Precio en USD |
|---|---|---|
| Sitio personal | 3 | 150 |
| Sitio para negocio | 5 | 300 |
| Blog | 4 | 200 |

Aclaración: todos los precios incluyen una revisión.

## 💻 Código

La tabla de tarifas (de `servicios.html`):

```html
<table>
  <caption>Tarifas 2026</caption>
  <thead>
    <tr>
      <th>Servicio</th>
      <th>Páginas</th>
      <th>Precio en USD</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Sitio personal</td>
      <td>3</td>
      <td>150</td>
    </tr>
    <tr>
      <td>Sitio para negocio</td>
      <td>5</td>
      <td>300</td>
    </tr>
    <tr>
      <td>Blog</td>
      <td>4</td>
      <td>200</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="3">Todos los precios incluyen una revisión</td>
    </tr>
  </tfoot>
</table>
```

La tabla de horarios, con una celda que ocupa dos filas:

```html
<h3>Horarios de atención</h3>
<table>
  <caption>Horarios de atención</caption>
  <tbody>
    <tr>
      <th rowspan="2">Lunes y martes</th>
      <td>Mañana</td>
      <td>9 a 12 h</td>
    </tr>
    <tr>
      <td>Tarde</td>
      <td>14 a 18 h</td>
    </tr>
  </tbody>
</table>
```

## 🔍 Análisis paso a paso

1. **Una tabla para datos.** Hay filas y columnas de datos que se comparan: es un caso típico de tabla.
2. **El título.** `<caption>` va primero dentro de `<table>` y describe qué contiene: «Tarifas 2026».
3. **Los encabezados.** La primera fila va dentro de `<thead>` y cada celda es un `<th>`: «Servicio», «Páginas» y «Precio en
   USD».
4. **Los datos.** Las tres filas van dentro de `<tbody>`. Cada fila es un `<tr>` y cada dato, un `<td>`. Todas las filas
   tienen **tres celdas**, porque la tabla tiene tres columnas.
5. **El pie.** La aclaración vale para todos los precios: va en `<tfoot>`, en **una sola celda** con
   `colspan="3"`, que **ocupa las tres columnas**.
6. **Combinar filas.** En la tabla de horarios, «Lunes y martes» corresponde a dos horarios. Lucía usa `rowspan="2"` en
   su `<th>` para que ocupe **dos filas**. La segunda fila **tiene una celda menos** (solo «Tarde» y «14 a 18 h»), porque
   la primera celda ya está ocupada por el `rowspan`.
7. **Una advertencia.** Las celdas combinadas hacen la tabla más compleja de interpretar para las tecnologías de apoyo;
   por eso Lucía las usa solo donde hacen falta.
8. **Qué no hacer.** Lucía no usa una tabla para ubicar su menú a la izquierda y su texto a la derecha: una tabla es para
   datos.

## ✅ Resultado esperado

- El título «Tarifas 2026» arriba de la tabla.
- Una fila de **encabezados** (en negrita) con tres columnas, tres filas de datos y, abajo, **una celda que ocupa todo el
  ancho** con «Todos los precios incluyen una revisión».
- Una segunda tabla donde «Lunes y martes» **ocupa dos filas**: a su derecha, «Mañana» con «9 a 12 h» y, debajo, «Tarde»
  con «14 a 18 h».
- Sin CSS, la tabla se ve **sin bordes**: el aspecto lo vas a definir con CSS más adelante.

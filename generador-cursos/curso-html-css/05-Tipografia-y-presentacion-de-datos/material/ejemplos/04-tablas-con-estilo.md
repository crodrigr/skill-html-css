# 📘 Ejemplo 04 — Tablas con estilo

> 🕐 **Sesión 1** · 🎓 **Resultados de aprendizaje:** RA-5

## 🧱 Situación inicial

En la Clase 02 Lucía escribió la tabla de tipos de sitio de su artículo con `table`, `caption`, `thead`, `tbody`, `tr`, `th` y `td`. Ahora quiere que los datos se lean con
claridad: bordes, espacio dentro de las celdas, alineación y filas alternas. Prueba dos versiones de la misma tabla en `tablas.html`: una con los bordes **separados** (el
comportamiento por defecto) y otra con los bordes **unidos**.

## 💻 Código

El contenido de `tablas.html` (dentro de `<main>`):

```html
<h2>Bordes separados (el comportamiento por defecto)</h2>
<table class="separada">
        <caption>Tipos de sitio y su costo mensual estimado (datos de ejemplo)</caption>
        <thead>
          <tr>
            <th>Tipo de sitio</th>
            <th>Para qué sirve</th>
            <th class="numero">Costo (USD/mes)</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>Blog</td><td>Publicar artículos</td><td class="numero">5</td></tr>
          <tr><td>Portafolio</td><td>Mostrar trabajos</td><td class="numero">8</td></tr>
          <tr><td>Tienda en línea</td><td>Vender productos</td><td class="numero">29</td></tr>
          <tr><td>Página de aterrizaje</td><td>Presentar una sola oferta</td><td class="numero">12</td></tr>
          <tr><td>Sitio institucional</td><td>Presentar una organización</td><td class="numero">15</td></tr>
        </tbody>
      </table>

<h2>Bordes unidos, con filas alternas</h2>
<table class="unida">
        <caption>Tipos de sitio y su costo mensual estimado (datos de ejemplo)</caption>
        <thead>
          <tr>
            <th>Tipo de sitio</th>
            <th>Para qué sirve</th>
            <th class="numero">Costo (USD/mes)</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>Blog</td><td>Publicar artículos</td><td class="numero">5</td></tr>
          <tr><td>Portafolio</td><td>Mostrar trabajos</td><td class="numero">8</td></tr>
          <tr><td>Tienda en línea</td><td>Vender productos</td><td class="numero">29</td></tr>
          <tr><td>Página de aterrizaje</td><td>Presentar una sola oferta</td><td class="numero">12</td></tr>
          <tr><td>Sitio institucional</td><td>Presentar una organización</td><td class="numero">15</td></tr>
        </tbody>
      </table>
```

La hoja `css/tablas.css`:

```css
/* Bordes, relleno y alineación de las celdas */
th, td {
  border: 1px solid #2563eb;
  padding: 8px 12px;
  text-align: left;
}

th {
  color: #ffffff;
  background-color: #1e3a8a;
}

.numero {
  text-align: right;
}

/* Sin border-collapse, cada celda dibuja su propio borde y se ve doble */
.separada {
  border-spacing: 8px;
}

/* Con collapse, las celdas comparten el borde */
.unida {
  border-collapse: collapse;
  width: 100%;
}

/* El título de la tabla, debajo */
.unida caption {
  caption-side: bottom;
  font-style: italic;
}

/* Filas alternas */
.unida tbody tr:nth-child(even) {
  background-color: #dbeafe;
}
```

## 🔍 Análisis paso a paso

1. **Bordes en las celdas.** `th, td { border: 1px solid #2563eb; }` dibuja el borde en cada celda. Por defecto cada celda tiene **su propio** borde y entre dos celdas
   se ven **dos líneas**, con un espacio entre ellas.
2. **`border-collapse`.** Su valor inicial es `separate` (celdas con bordes propios). Con `collapse`, las celdas **comparten** el borde y se ve una sola línea. Es lo que
   hace `.unida`.
3. **`border-spacing`.** Fija la distancia entre las celdas **separadas**: `.separada` la pone en `8px`. Con `collapse` no se usa: no hay espacio entre bordes que unir.
4. **`padding` en las celdas.** `8px 12px` deja 8px arriba y abajo y 12px a los costados. Sin relleno, el texto toca el borde y se lee mal.
5. **Alineación.** `text-align: left` alinea el texto de las celdas a la izquierda; los números van mejor **a la derecha**, para que las unidades queden una debajo de otra
   (clase `.numero`).
6. **El título de la tabla.** `caption-side: bottom` pasa el `caption` debajo de la tabla.
7. **Filas alternas.** `.unida tbody tr:nth-child(even)` pinta las filas **pares** del cuerpo de la tabla. De las 5 filas, elige 2 (la segunda y la cuarta), y no toca la
   fila de encabezado, que está en el `thead`.
8. **Ancho.** `width: 100%` hace que la tabla ocupe todo el ancho disponible.

## ✅ Resultado esperado

| Elemento | Propiedad | Valor calculado |
|---|---|---|
| `.separada` | `border-collapse` / `border-spacing` | `separate` / `8px` |
| `.unida` | `border-collapse` | `collapse` |
| `.unida td` | `border-top-width` | `1px` |
| `.unida td` | `padding-top` / `padding-left` | `8px` / `12px` |
| `.unida caption` | `caption-side` | `bottom` |
| `.unida th` | `background-color` | `rgb(30, 58, 138)` |
| `.unida .numero` | `text-align` | `right` |

- `.unida tbody tr:nth-child(even)` elige **2** de las **5** filas y las pinta de celeste (`rgb(219, 234, 254)`); la primera fila del cuerpo queda sin fondo.
- La tabla `.separada` se ve con un doble borde y un espacio de 8px entre las celdas; la `.unida`, con una sola línea y a todo el ancho.
- El título aparece debajo de la tabla `.unida`.

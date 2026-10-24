# 📘 Ejemplo 01 — `display: grid` y sus partes

> 🎓 **Resultados de aprendizaje:** RA-1
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere ordenar seis tarjetas de su portafolio en filas y columnas. En `grid-basico.html` prueba la misma regla de columnas en dos contenedores: uno **sin** `display: grid` y otro **con** `display: grid`, para ver qué hace cada parte.

## 💻 Código

El contenido de `grid-basico.html` (dentro de `<main>`):

```html
<h2>Sin display: grid</h2>
<section class="sin-grid">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</section>

<h2>Con display: grid</h2>
<section class="con-grid">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</section>
```

La hoja `css/grid-basico.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

/* Sin margen en el cuerpo: las cuadrículas ocupan todo el ancho de la ventana */
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

/* Cada elemento tiene la misma altura y un fondo claro */
.item {
  height: 60px;
  line-height: 60px;
  text-align: center;
  background-color: #dbeafe;
}

.item:nth-child(even) {
  background-color: #ccfbf1;
}

/* Sin display: grid, esta regla no tiene ningún efecto */
.sin-grid {
  grid-template-columns: 200px 200px 200px;
}

/* Con display: grid, las tres columnas de 200px sí se crean */
.con-grid {
  display: grid;
  grid-template-columns: 200px 200px 200px;
}
```

## 🔍 Análisis paso a paso

1. **Qué es Grid.** Es un sistema de disposición en **dos dimensiones**: ordena los elementos en filas **y** columnas a la vez. Se activa en el **contenedor** (el elemento que los encierra) con `display: grid`.
2. **Sin `display: grid`.** `.sin-grid` tiene `grid-template-columns: 200px 200px 200px`, pero esa propiedad solo funciona en un contenedor de cuadrícula. Los seis `div` se comportan como bloques normales: cada uno ocupa **todo el ancho** (`1200px`) y se apilan.
3. **Con `display: grid`.** `.con-grid` activa la cuadrícula. Sus **hijos directos** (los seis `div`) pasan a ser los **elementos** de la cuadrícula. Los nietos, si los hubiera, no son elementos de la cuadrícula.
4. **Las pistas.** Las tres medidas de `grid-template-columns` crean **tres columnas** de `200px`. Cada columna (y cada fila) es una **pista**. Como hay seis elementos y tres columnas, el navegador crea **dos filas** solo, del alto de sus elementos (`60px`).
5. **Las líneas.** Entre las pistas hay **líneas** numeradas desde `1`: tres columnas tienen **cuatro** líneas verticales (1 a 4) y dos filas tienen **tres** líneas horizontales (1 a 3). Las vas a usar en el Ejemplo 06.
6. **La celda.** El cruce de una fila y una columna es una **celda**. Cada elemento ocupa una celda; varias celdas juntas forman un **área** (diagrama de la explicación).
7. **Cuidado.** Si ves que `grid-template-columns` «no hace nada», revisá primero que el contenedor tenga `display: grid`.

## ✅ Resultado esperado

| Medida | Valor |
|---|---|
| `.sin-grid .item`, ancho | `1200px` (la regla de columnas no tuvo efecto) |
| `.con-grid`, columnas calculadas | `200px 200px 200px` |
| `.con-grid`, filas calculadas | `60px 60px` |
| `.con-grid .item`, ancho | `200px` |
| `.con-grid`, alto total | `120px` |

- En el primer contenedor los seis elementos se apilan, uno debajo del otro, cada uno a lo ancho.
- En el segundo se ven tres columnas y dos filas, y quedan libres los `600px` de la derecha (la cuadrícula no se estira).

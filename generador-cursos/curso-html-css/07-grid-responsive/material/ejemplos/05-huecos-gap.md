# 📘 Ejemplo 05 — Huecos con `gap`

> 🎓 **Resultados de aprendizaje:** RA-3
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere separar sus tarjetas. Primero lo hace con márgenes y después descubre `gap`. En `huecos.html` compara cuatro contenedores de tres columnas con seis elementos, con la ventana en `1200px`.

## 💻 Código

El contenido de `huecos.html` (dentro de `<main>`):

```html
<h2>Sin hueco</h2>
<section class="sin-hueco">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</section>

<h2>gap: 16px</h2>
<section class="con-gap">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</section>

<h2>row-gap: 1rem; column-gap: 2rem</h2>
<section class="dos-huecos">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</section>

<h2>Margen en lugar de hueco</h2>
<section class="con-margen">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</section>
```

La hoja `css/huecos.css`:

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

.item {
  height: 60px;
  line-height: 60px;
  text-align: center;
  background-color: #dbeafe;
}

.item:nth-child(even) {
  background-color: #ccfbf1;
}

.sin-hueco,
.con-gap,
.dos-huecos,
.con-margen {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

/* gap: el mismo hueco entre filas y entre columnas */
.con-gap {
  gap: 16px;
}

/* row-gap separa las filas; column-gap separa las columnas */
.dos-huecos {
  row-gap: 1rem;
  column-gap: 2rem;
}

/* El margen también separa, pero rodea a cada elemento, borde exterior incluido */
.con-margen .item {
  margin: 8px;
}
```

## 🔍 Análisis paso a paso

1. **`gap`** pone un espacio **entre las pistas** de la cuadrícula. `gap: 16px` separa las filas y las columnas con `16px`. Es el atajo de `row-gap` (entre filas) y `column-gap` (entre columnas).
2. **Dos valores distintos.** `row-gap: 1rem; column-gap: 2rem` da `16px` entre filas y `32px` entre columnas (con la base de `16px`). Con `gap` también se pueden escribir dos valores: el primero es el de las filas y el segundo el de las columnas.
3. **El hueco se descuenta del espacio.** Con `repeat(3, 1fr)` y `gap: 16px`, los dos huecos suman `32px` y las columnas se reparten `1200 − 32 = 1168px`: `389.33px` cada una. Con `column-gap: 2rem` son `64px` de huecos: `378.66px` cada columna.
4. **Solo entre pistas.** No hay hueco antes de la primera columna ni después de la última: el primer elemento empieza en `0` (`offsetLeft` `0`).
5. **El margen no es lo mismo.** Con `margin: 8px` en cada elemento, el espacio rodea a **cada elemento**, también en el borde exterior: el primer elemento empieza en `8px` y cada uno mide `384px` (`400 − 16`). Además, los márgenes de dos elementos vecinos se suman (`8 + 8 = 16px`) y los de arriba y abajo hacen la cuadrícula más alta: `152px` frente a `136px`.
6. **Cuál elegir.** Para separar elementos de una cuadrícula, usá `gap`: lo escribís una vez, en el contenedor, y no ensucia el borde exterior.

## ✅ Resultado esperado

| Contenedor | Regla | Columnas calculadas (`1200px`) | Alto |
|---|---|---|---|
| `.sin-hueco` | — | `400px 400px 400px` | `120px` |
| `.con-gap` | `gap: 16px` | `389.33px` ×3 | `136px` (`120 + 16`) |
| `.dos-huecos` | `row-gap: 1rem; column-gap: 2rem` | `378.66px` ×3 | `136px` (`row-gap` `16px`, `column-gap` `32px`) |
| `.con-margen` | `margin: 8px` en cada elemento | `400px` ×3 (elementos de `384px`) | `152px` |

- En `.con-gap` el primer elemento empieza pegado al borde (`offsetLeft` `0`); en `.con-margen` empieza a `8px`.

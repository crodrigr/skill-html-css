# 📘 Ejemplo 03 — `repeat()` y `minmax()`

> 🎓 **Resultados de aprendizaje:** RA-2
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere doce columnas iguales sin escribir `1fr` doce veces, y una galería cuyas columnas **nunca** se achiquen por debajo de `200px`. En `repeat.html` prueba `repeat()` y `minmax()`, con la ventana en `1200px` y en `500px`.

## 💻 Código

El contenido de `repeat.html` (dentro de `<main>`):

```html
<h2>repeat(3, 1fr)</h2>
<section class="tres">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</section>

<h2>repeat(2, 100px 1fr)</h2>
<section class="patron">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
</section>

<h2>repeat(3, minmax(200px, 1fr))</h2>
<section class="minimo">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</section>
```

La hoja `css/repeat.css`:

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

/* repeat(3, 1fr) es lo mismo que escribir 1fr 1fr 1fr */
.tres {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

/* repeat también repite un patrón de varias pistas: 100px 1fr 100px 1fr */
.patron {
  display: grid;
  grid-template-columns: repeat(2, 100px 1fr);
}

/* minmax(200px, 1fr): nunca menos de 200px; si hay espacio, crece hasta 1fr */
.minimo {
  display: grid;
  grid-template-columns: repeat(3, minmax(200px, 1fr));
}
```

## 🔍 Análisis paso a paso

1. **`repeat(veces, pista)`** repite una pista. `repeat(3, 1fr)` es exactamente lo mismo que `1fr 1fr 1fr`: tres columnas iguales de `400px` en una ventana de `1200px`.
2. **Repetir un patrón.** `repeat()` también repite **varias pistas**: `repeat(2, 100px 1fr)` equivale a `100px 1fr 100px 1fr`. Con `1200px`, las dos pistas `1fr` se reparten los `1000px` que sobran: `100px 500px 100px 500px`.
3. **`minmax(mínimo, máximo)`** define una pista que **nunca baja del mínimo ni pasa del máximo**. `minmax(200px, 1fr)` significa «al menos `200px`; si hay espacio, crece hasta `1fr`».
4. **Con espacio de sobra** (`1200px`), `repeat(3, minmax(200px, 1fr))` se comporta como `repeat(3, 1fr)`: cada columna mide `400px`.
5. **Con poco espacio** (`500px`), tres columnas de `1fr` medirían `166.66px`, pero el mínimo es `200px`: la cuadrícula mide `600px` y **sobresale** de la ventana (aparece desplazamiento horizontal). `minmax()` protege el contenido, pero no resuelve el desborde.
6. **Idea clave.** Para que una cuadrícula cambie el número de columnas según el ancho, `minmax()` solo no alcanza: hace falta una consulta de medios o `auto-fit` (Ejemplos 10 y 11).

## ✅ Resultado esperado

| Contenedor | Columnas escritas | Ventana de `1200px` | Ventana de `500px` |
|---|---|---|---|
| `.tres` | `repeat(3, 1fr)` | `400px 400px 400px` | `166.66px` cada una |
| `.patron` | `repeat(2, 100px 1fr)` | `100px 500px 100px 500px` | — |
| `.minimo` | `repeat(3, minmax(200px, 1fr))` | `400px 400px 400px` | `200px 200px 200px` |

- Con la ventana en `500px`, `.minimo` mide `600px` de ancho total (la página tiene desplazamiento horizontal) y `.tres` cabe justo.

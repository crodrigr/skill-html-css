# 📘 Ejemplo 04 — Filas y `auto`

> 🎓 **Resultados de aprendizaje:** RA-2
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía define tres filas con alturas distintas y descubre que, cuando hay más elementos que celdas, aparecen filas nuevas. En `filas.html` las controla con `grid-template-rows` y `grid-auto-rows`.

## 💻 Código

El contenido de `filas.html` (dentro de `<main>`):

```html
<h2>Tres filas definidas: 60px auto 1fr</h2>
<section class="filas">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
  <div class="item">7</div>
  <div class="item">8</div>
  <div class="item">9</div>
</section>

<h2>Sin grid-auto-rows</h2>
<section class="sin-auto">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
  <div class="item">7</div>
  <div class="item">8</div>
</section>

<h2>Con grid-auto-rows: 80px</h2>
<section class="con-auto">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
  <div class="item">7</div>
  <div class="item">8</div>
</section>
```

La hoja `css/filas.css`:

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
  text-align: center;
  background-color: #dbeafe;
}

.item:nth-child(even) {
  background-color: #ccfbf1;
}

/* La fila 2 es auto (se ajusta a su contenido); la fila 3 toma todo lo que sobra */
.filas {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 60px auto 1fr;
  height: 300px;
}

/* Dos filas definidas, pero hay ocho elementos: la tercera fila se crea sola */
.sin-auto {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 50px 50px;
}

/* grid-auto-rows da la altura de las filas que se crean solas */
.con-auto {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 50px 50px;
  grid-auto-rows: 80px;
}
```

## 🔍 Análisis paso a paso

1. **`grid-template-rows`** define las filas igual que `grid-template-columns` define las columnas: con medidas fijas, `fr`, `auto`, `repeat()` y `minmax()`.
2. **Tres filas distintas.** En `.filas`, la primera es fija (`60px`), la segunda es `auto` y la tercera es `1fr`. El contenedor mide `300px` de alto.
3. **`auto`** significa «lo que necesite su contenido»: la fila 2 mide `18px`, la altura de una línea de texto de `16px` con Arial.
4. **`1fr` en filas** necesita un **alto definido** en el contenedor para repartir algo: como `.filas` mide `300px`, la tercera fila toma lo que sobra: `300 − 60 − 18 = 222px`. Sin un alto en el contenedor, `1fr` no tiene espacio libre que repartir: en una prueba aparte, la tercera fila midió `18px`, lo que pide su contenido.
5. **Filas implícitas.** En `.sin-auto` hay dos filas definidas (`50px 50px`) pero **ocho elementos** en tres columnas: caben seis, y los otros dos necesitan una **tercera fila**. El navegador la crea solo (es **implícita**) y la fila mide lo que su contenido (`18px`).
6. **`grid-auto-rows`** da la altura de las filas implícitas. En `.con-auto`, con `grid-auto-rows: 80px`, la tercera fila mide `80px`.
7. **Para qué sirve.** Es la forma de que las filas que aparecen cuando se agregan más elementos tengan una altura uniforme y predecible.

## ✅ Resultado esperado

| Contenedor | Filas escritas | Filas calculadas | Alto total |
|---|---|---|---|
| `.filas` | `60px auto 1fr` (alto del contenedor `300px`) | `60px 18px 222px` | `300px` |
| `.sin-auto` | `50px 50px` (ocho elementos) | `50px 50px 18px` | `118px` |
| `.con-auto` | `50px 50px` y `grid-auto-rows: 80px` | `50px 50px 80px` | `180px` |

- La tercera fila de `.sin-auto` es muy baja; la de `.con-auto` mide `80px`.

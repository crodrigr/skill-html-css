# 📘 Ejemplo 08 — Unidades de ventana

> 🎓 **Resultados de aprendizaje:** RA-7

## 🧱 Situación inicial

Lucía quiere una sección que ocupe la mitad de la altura de la ventana y una caja que mida un porcentaje del ancho de la ventana. Usa las **unidades de ventana** (`vw`, `vh`, `vmin`, `vmax`) y `rlh`, solo como **medidas**:
no arma un diseño adaptable. Las prueba en `ventana.html`, con la ventana fijada en `1000 × 600`.

## 💻 Código

El contenido de `ventana.html` (dentro de `<main>`):

```html
<h2>Un porcentaje de la ventana</h2>
<div class="caja caja--vw">10vw</div>
<div class="caja caja--vh">50vh</div>
<div class="caja caja--vmin">10vmin</div>
<div class="caja caja--vmax">10vmax</div>

<h2>La altura de línea de la raíz</h2>
<div class="caja caja--rlh">2rlh</div>
```

La hoja `css/ventana.css`:

```css
/* Tamaño base: 16px y una altura de línea de 1.5 en la raíz (la que mide rlh) */
html {
  font-size: 16px;
  line-height: 1.5;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.caja {
  margin-bottom: 8px;
  background-color: #dbeafe;
}

/* vw y vh: 1% del ancho y 1% del alto de la ventana */
.caja--vw {
  width: 10vw;
}

.caja--vh {
  height: 50vh;
}

/* vmin y vmax: 1% de la menor y de la mayor de las dos medidas */
.caja--vmin {
  width: 10vmin;
}

.caja--vmax {
  width: 10vmax;
}

/* rlh: la altura de línea de la raíz */
.caja--rlh {
  height: 2rlh;
}
```

## 🔍 Análisis paso a paso

1. **La ventana de visualización.** Es el área de la página que se ve en el navegador (en inglés, *viewport*). Con la ventana de `1000 × 600`, el ancho es `1000px` y el alto es `600px`.
2. **`vw` y `vh`.** `1vw` es el `1%` del **ancho** de la ventana y `1vh`, el `1%` del **alto**: `10vw` son `100px` y `50vh` son `300px`.
3. **`vmin` y `vmax`.** `1vmin` es el `1%` de la **menor** de las dos medidas (ancho o alto) y `1vmax`, el `1%` de la **mayor**. Con `1000 × 600`: `10vmin` son `60px` y `10vmax`, `100px`.
4. **Qué pasa si la ventana cambia.** Con una ventana de `600 × 1000` (en vertical), `10vw` pasan a ser `60px`, `10vmin` siguen en `60px` y `10vmax` siguen en `100px`: `vmin` y `vmax` no dependen de la orientación.
5. **`rlh`.** Es la altura de línea del **elemento raíz** (`html`). Con `font-size: 16px` y `line-height: 1.5` en la raíz, la altura de línea es `24px` y `2rlh` son `48px`.
6. **La diferencia con `%`.** El porcentaje se mide contra el **contenedor**; las unidades de ventana, contra la **ventana**, sin importar en qué contenedor estén.
7. **Alcance.** En esta clase solo se usan como medida. Los diseños que cambian según el ancho de la ventana (diseño adaptable) son otro tema.
8. **Compatibilidad.** `rlh` es reciente y las unidades de ventana tienen variantes más nuevas: comprobá su compatibilidad en MDN antes de usarlas; en este ejemplo se verificaron en Chrome.

## ✅ Resultado esperado

| Clase | Escrito | Ventana de `1000 × 600` | Ventana de `600 × 1000` |
|---|---|---|---|
| `.caja--vw` | `width: 10vw` | `100px` | `60px` |
| `.caja--vh` | `height: 50vh` | `300px` | — |
| `.caja--vmin` | `width: 10vmin` | `60px` | `60px` |
| `.caja--vmax` | `width: 10vmax` | `100px` | `100px` |
| `.caja--rlh` | `height: 2rlh` (raíz con `line-height: 1.5`) | `48px` | — |

- Las medidas siguen a la ventana, no al contenedor.

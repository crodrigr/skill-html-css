# 📘 Ejemplo 09 — Estrategias de diseño

> 🎓 **Resultados de aprendizaje:** RA-6
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere que su galería tenga una columna en el teléfono, dos en la tableta y tres en el computador. En `estrategias.html` escribe el mismo diseño de dos maneras: **móvil primero** y **escritorio primero**.

## 💻 Código

El contenido de `estrategias.html` (dentro de `<main>`):

```html
<h2>Móvil primero</h2>
<section class="movil-primero">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</section>

<h2>Escritorio primero</h2>
<section class="escritorio-primero">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</section>
```

La hoja `css/estrategias.css`:

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

/* Que el ancho incluya el relleno y el borde (se explica en el Ejemplo 08) */
* {
  box-sizing: border-box;
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

/* MÓVIL PRIMERO: se escribe el diseño pequeño y se agrega con min-width lo que crece */
.movil-primero {
  display: grid;
  grid-template-columns: 1fr;
  gap: 16px;
}

@media (min-width: 600px) {
  .movil-primero {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 900px) {
  .movil-primero {
    grid-template-columns: repeat(3, 1fr);
  }
}

/* ESCRITORIO PRIMERO: se escribe el diseño grande y se quita con max-width lo que no cabe */
.escritorio-primero {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}

@media (max-width: 899px) {
  .escritorio-primero {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 599px) {
  .escritorio-primero {
    grid-template-columns: 1fr;
  }
}
```

## 🔍 Análisis paso a paso

1. **Una cuadrícula fluida.** Una cuadrícula con `fr` ya es flexible: sus columnas siguen el ancho de la ventana. Lo que cambia con las consultas es **cuántas columnas** hay.
2. **Móvil primero** (*mobile first*). Se escribe **primero el diseño más pequeño** (una columna) y se va **agregando** lo que crece con `min-width`: «a partir de `600px`, dos columnas; a partir de `900px`, tres». Los estilos base son los del teléfono.
3. **Escritorio primero** (*desktop first*). Se escribe primero el diseño grande (tres columnas) y se va **quitando** con `max-width`: «hasta `899px`, dos columnas; hasta `599px`, una».
4. **Qué es un punto de ruptura** (*breakpoint*). Es el ancho en el que cambia la disposición. En este curso usamos `600px` y `900px`. MDN recomienda definirlos en unidades relativas (como `em`) en lugar de ajustarlos a un dispositivo concreto.
5. **Mismo resultado.** Medido en tres ventanas, las dos estrategias dan exactamente las mismas columnas: una de `500px`, dos de `392px` y tres de `389.33px`.
6. **Por qué suele preferirse móvil primero.** El teléfono tiene el diseño más simple (una columna, sin reglas extra): se parte de lo esencial y se va añadiendo. Además, un solo tipo de condición (`min-width`) hace las reglas más fáciles de leer.
7. **Antes de leer el código.** Las `@media` se explican en detalle desde el Ejemplo 11; por ahora leelas como «a partir de este ancho de ventana» (`min-width`) o «hasta este ancho» (`max-width`).

## ✅ Resultado esperado

| Ventana | `.movil-primero` | `.escritorio-primero` |
|---|---|---|
| `500px` | `500px` (una columna) | `500px` (una columna) |
| `800px` | `392px 392px` (dos columnas) | `392px 392px` (dos columnas) |
| `1200px` | `389.33px` ×3 (tres columnas) | `389.33px` ×3 (tres columnas) |

- Las dos estrategias terminan igual; cambia el camino por el que se escribe cada una.

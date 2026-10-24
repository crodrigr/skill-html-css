# 📘 Ejemplo 06 — Ocupar varias pistas

> 🎓 **Resultados de aprendizaje:** RA-1, RA-3
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía arma la maqueta de una página: una cabecera que ocupa todo el ancho, un menú, el contenido y un pie. Además, un mosaico con una tarjeta grande. En `abarcar.html` usa las **líneas** de la cuadrícula y la palabra `span`.

## 💻 Código

El contenido de `abarcar.html` (dentro de `<main>`):

```html
<h2>Una maqueta de página</h2>
<section class="pagina">
  <div class="cabecera">Cabecera</div>
  <div class="menu">Menú</div>
  <div class="contenido">Contenido</div>
  <div class="pie">Pie</div>
</section>

<h2>Un mosaico</h2>
<section class="mosaico">
  <div class="grande">Grande</div>
  <div class="chico">1</div>
  <div class="chico">2</div>
  <div class="chico">3</div>
  <div class="chico">4</div>
  <div class="chico">5</div>
</section>
```

La hoja `css/abarcar.css`:

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

/* Maqueta de dos columnas: un menú de 200px y el contenido, con 16px entre ellos */
.pagina {
  display: grid;
  grid-template-columns: 200px 1fr;
  gap: 16px;
}

.pagina > div {
  padding: 1rem;
  background-color: #dbeafe;
}

/* De la línea 1 a la línea 3: abarca las dos columnas */
.cabecera {
  grid-column: 1 / 3;
  background-color: #fef3c7;
}

/* span 2: abarca dos columnas desde donde le toque */
.pie {
  grid-column: span 2;
  background-color: #fef3c7;
}

/* Mosaico de tres columnas con filas de 60px */
.mosaico {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 60px;
  gap: 16px;
}

.mosaico > div {
  background-color: #ccfbf1;
  text-align: center;
}

/* Ocupa dos columnas y dos filas */
.mosaico .grande {
  grid-column: span 2;
  grid-row: span 2;
  background-color: #fee2e2;
}
```

## 🔍 Análisis paso a paso

1. **Colocar con líneas.** Cada elemento ocupa por defecto una celda. `grid-column: 1 / 3` significa «desde la línea de columna `1` hasta la línea `3`»: abarca las **dos** columnas. `grid-row` hace lo mismo con las filas.
2. **La maqueta.** `.pagina` tiene dos columnas (`200px 1fr`) y un `gap` de `16px`. La segunda columna mide `1200 − 200 − 16 = 984px`.
3. **`span`.** `grid-column: span 2` significa «abarcá dos pistas desde donde te toque». `.pie` lo usa y mide `1200px`, igual que `.cabecera`, que usa `1 / 3`. La diferencia: con números fijás **dónde** empieza; con `span` solo fijás **cuántas** pistas ocupa.
4. **El mosaico.** `.mosaico` tiene tres columnas, filas de `60px` (`grid-auto-rows`) y `gap: 16px`. La tarjeta `.grande` usa `span 2` en columnas **y** en filas: ocupa dos columnas y dos filas.
5. **Las medidas.** `.grande` mide `2 × 389.33 + 16 = 795px` de ancho (dos columnas **más** el hueco que hay entre ellas) y `2 × 60 + 16 = 136px` de alto.
6. **Líneas negativas.** `-1` cuenta desde el final: `grid-column: 1 / -1` abarca **todas** las columnas, sin importar cuántas sean. Lo vas a usar en el Ejemplo 13.
7. **Mención.** También existe `grid-template-areas`, que da **nombres** a las áreas y las coloca con ellos. Es otra forma de lograr lo mismo y queda para un estudio posterior.

## ✅ Resultado esperado

| Elemento | Regla | Medida (ventana de `1200px`) |
|---|---|---|
| `.pagina` | `200px 1fr` y `gap: 16px` | columnas `200px 984px` |
| `.cabecera` | `grid-column: 1 / 3` | ancho `1200px` |
| `.menu` | (una celda) | ancho `200px` |
| `.contenido` | (una celda) | ancho `984px` |
| `.pie` | `grid-column: span 2` | ancho `1200px` |
| `.mosaico` | `repeat(3, 1fr)` y `gap: 16px` | columnas `389.33px` ×3 |
| `.grande` | `grid-column: span 2; grid-row: span 2` | `795px` de ancho y `136px` de alto |

- La cabecera y el pie cruzan toda la página; el menú y el contenido van lado a lado en la fila del medio.

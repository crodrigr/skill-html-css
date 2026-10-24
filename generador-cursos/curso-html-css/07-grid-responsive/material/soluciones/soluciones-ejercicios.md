# 🔑 Soluciones — Ejercicios de la Clase 07 (material docente)

No compartir este archivo con los estudiantes. Cada hoja se probó en Chrome sobre la página de partida del ejercicio: pasa `validar_css.py` y cumple los valores de su tabla o de sus casos de prueba, con la ventana del ancho indicado y sin barra de desplazamiento vertical.

---

## 🟢 Básico 01 — Tus primeras cuadrículas

**Hoja.**

```css
/* Tamaño base */
html {
  font-size: 16px;
}

/* Sin margen en el cuerpo: las cuadrículas ocupan todo el ancho de la ventana */
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

.caja {
  height: 60px;
  line-height: 60px;
  text-align: center;
  background-color: #fef3c7;
}

/* 1. Galería: tres columnas iguales con repeat() */
.galeria {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

/* 2. Maqueta: una columna fija y dos que se reparten lo que sobra */
.maqueta {
  display: grid;
  grid-template-columns: 200px 1fr 1fr;
}

/* 3. Proporción: 1 a 2 a 1 */
.proporcion {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
}
```

**Parte B.**

1. Sin `display: grid`, las cajas son bloques normales y cada una ocupa todo el ancho de su contenedor (`1200px`).
2. `fr` reparte solo lo que **sobra**: de `1200px` se descuenta la columna fija de `200px` y quedan `1000px` para dos columnas: `500px` cada una.
3. Tres columnas tienen **cuatro** líneas verticales y dos filas (seis cajas en tres columnas) tienen **tres** líneas horizontales.

---

## 🟢 Básico 02 — Huecos y pistas

**Hoja.**

```css
/* Tamaño base */
html {
  font-size: 16px;
}

/* Sin margen en el cuerpo: las cuadrículas ocupan todo el ancho de la ventana */
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

/* 1. Huecos: 1rem entre filas y 2rem entre columnas */
.rejilla {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 60px;
  row-gap: 1rem;
  column-gap: 2rem;
}

.rejilla > div {
  background-color: #fef3c7;
  text-align: center;
}

/* 2. La cabecera abarca de la primera a la última línea de columna */
.cabecera {
  grid-column: 1 / -1;
}

/* 3. La destacada ocupa dos columnas y dos filas */
.destacada {
  grid-column: span 2;
  grid-row: span 2;
  background-color: #16a34a;
}
```

**Medidas comprobadas (ventana de `1200px`).** Columnas `378.66px ×3`, `row-gap` `16px`, `column-gap` `32px`; `.cabecera` `1200 × 60`; `.destacada` `789 × 136`; `.rejilla` de `288px` de alto. Sin la solución, la rejilla mide `120px` de alto y la cabecera, `400px` de ancho.

**Parte B.**

1. Ocupa dos columnas **más el hueco** que hay entre ellas: `2 × 378.66 + 32 = 789.33px`.
2. Hay cuatro filas de `60px` (la cabecera, las dos de la destacada y la de abajo) y tres huecos de `16px`: `4 × 60 + 3 × 16 = 288px`.
3. Con un margen de `16px` el espacio rodearía a cada elemento, también en el borde exterior, y cada elemento sería más chico; además la rejilla quedaría más alta (los márgenes de arriba y de abajo se suman). `gap` solo separa **entre** las pistas.

---

## 🟡 Intermedio 01 — Prepará la página

**Hoja.**

```css
/* Tamaño base */
html {
  font-size: 16px;
}

/* Sin margen en el cuerpo: las cuadrículas ocupan todo el ancho de la ventana */
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

/* 1. El ancho incluye el relleno y el borde en todos los elementos */
* {
  box-sizing: border-box;
}

/* 2. Ancho flexible: ocupa lo que haya, hasta 960px */
.contenedor {
  max-width: 960px;
  padding: 20px;
  border: 4px solid #111827;
}

.tarjeta {
  width: 100%;
  padding: 16px;
  border: 2px solid #16a34a;
  background-color: #fef3c7;
}

/* 3. Imagen flexible: nunca pasa del ancho de su contenedor */
img {
  max-width: 100%;
  height: auto;
}
```

**Medidas comprobadas.** En `500px`: contenedor `500`, tarjeta `452`, imagen `452 × 113`, página `500`. En `800px`: `800`, `752`, `752 × 188`, `800`. En `1200px`: `960`, `912`, `912 × 228`, `1200`. Con la hoja de partida, la página mide `1224px` en una ventana de `500px`.

**Parte B.**

1. La tarjeta está dentro del contenedor, que tiene `20px` de relleno y `4px` de borde por lado: `500 − 2 × 20 − 2 × 4 = 452px`. Su `width: 100%` es el `100%` del **contenido** del contenedor.
2. `<meta name="viewport" content="width=device-width, initial-scale=1">`. En un teléfono evita que el navegador dibuje la página en una ventana virtual más ancha y la reduzca. Su efecto solo existe en navegadores de teléfono y tableta: en el escritorio la ventana siempre tiene su ancho real, así que no se puede medir ahí.

---

## 🟡 Intermedio 02 — Dos consultas de medios

**Hoja.**

```css
/* Tamaño base */
html {
  font-size: 16px;
}

/* Sin margen en el cuerpo: las cuadrículas ocupan todo el ancho de la ventana */
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

* {
  box-sizing: border-box;
}

/* Estilos base (teléfono): una columna */
.titulo {
  font-size: 1.25rem;
}

.galeria {
  display: grid;
  grid-template-columns: 1fr;
  gap: 24px;
}

.foto {
  height: 60px;
  line-height: 60px;
  text-align: center;
  background-color: #fef3c7;
}

/* Tableta: dos columnas desde 600px */
@media (min-width: 600px) {
  .titulo {
    font-size: 1.75rem;
  }

  .galeria {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Computador: cuatro columnas desde 900px (va después: gana en las ventanas anchas) */
@media (min-width: 900px) {
  .titulo {
    font-size: 2.25rem;
  }

  .galeria {
    grid-template-columns: repeat(4, 1fr);
  }
}
```

**Medidas comprobadas.** `500px`: `500px` y `20px`; `599px`: `599px` y `20px`; `600px`: `288px 288px` y `28px`; `899px`: `437.5px 437.5px` y `28px`; `900px`: `207px ×4` y `36px`; `1200px`: `282px ×4` y `36px`.

**Parte B.**

1. En una ventana de `900px` o más se cumplen las dos consultas; como tienen la misma especificidad, **gana la que aparece después**. Si la de `900px` va después, gana en las ventanas anchas.
2. Con el orden invertido, en `1200px` se cumplen las dos y gana la de `600px`: dos columnas de `588px` y título de `28px` (comprobado).
3. `repeat(auto-fit, minmax(…, 1fr))` ajusta la cantidad de columnas según el ancho sin consultas. No alcanzaría si hiciera falta **otra disposición** (por ejemplo, cambiar el título de tamaño o mover un bloque).

---

## 🔴 Desafío 01 — El portafolio adaptable de Mateo

**Hoja.**

```css
/* Base: tamaño, cuerpo y preparación previa */
html {
  font-size: 16px;
}

body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

* {
  box-sizing: border-box;
}

img {
  max-width: 100%;
  height: auto;
}

/* Colores de los bloques */
.cabecera,
.pie {
  padding: 1rem;
  background-color: #111827;
  color: #fef3c7;
}

.menu {
  padding: 1rem;
  background-color: #fef3c7;
}

.contenido {
  padding: 1rem;
}

/* Teléfono (móvil primero): una columna, los bloques se apilan */
.pagina {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

/* Galería: tantas columnas de al menos 250px como quepan, sin consultas de medios */
.galeria {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
}

/* La cabecera y el pie abarcan todas las columnas desde 600px */
@media (min-width: 600px) {
  .cabecera,
  .pie {
    grid-column: 1 / -1;
  }
}

/* Tableta: dos columnas iguales entre 600px y 899px */
@media (min-width: 600px) and (max-width: 899px) {
  .pagina {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Computador: menú fijo de 220px y contenido flexible desde 900px */
@media (min-width: 900px) {
  .pagina {
    grid-template-columns: 220px 1fr;
  }
}
```

**Medidas comprobadas.**

| Ventana | `.pagina` | `.contenido` | `.galeria` | Foto |
|---|---|---|---|---|
| `500px` | `500px` | `500px` | `468px` | `468 × 293` |
| `599px` | `599px` | — | — | — |
| `600px` | `292px 292px` (cabecera `600`) | — | — | — |
| `800px` | `392px 392px` | `392px` | `360px` | — |
| `899px` | `441.5px 441.5px` | — | — | — |
| `900px` | `220px 664px` | — | — | — |
| `1200px` | `220px 964px` | `964px` | `300px 300px 300px` | alto `188` |

La página mide exactamente el ancho de la ventana en `500px`, `800px` y `1200px` (sin desplazamiento horizontal). Sin la hoja, mide `648px` en una ventana de `500px`.

**Notas de corrección.**

- La condición de la tableta usa `and`: `(min-width: 600px) and (max-width: 899px)`.
- `grid-column: 1 / -1` funciona con **cualquier** cantidad de columnas: por eso la cabecera y el pie abarcan todo en la tableta y en el computador.
- `.galeria` no lleva consulta de medios: `repeat(auto-fit, minmax(250px, 1fr))` da `1`, `1` y `3` columnas porque el contenido tiene `16px` de relleno por lado y su ancho útil cambia (`468px`, `360px` y `932px`).
- Se acepta una hoja con los mismos valores medidos aunque ordene los bloques de otra manera, mientras tenga comentarios, no repita reglas y no use `!important`.

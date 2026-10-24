# 📘 Ejemplo 12 — Condiciones y orden de las reglas

> 🎓 **Resultados de aprendizaje:** RA-7
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía necesita consultas más finas: un tramo con dos límites, una condición con «o», la forma de la ventana y entender qué pasa cuando dos consultas coinciden. En `condiciones.html` prueba cada caso en ventanas de `500px`, `800px` y `1200px` (con `800px` de alto).

## 💻 Código

El contenido de `condiciones.html` (dentro de `<main>`):

```html
<h2>Rangos con and</h2>
<div class="rango">Rojo: menos de 600px · Amarillo: de 600px a 899px · Verde: 900px o más</div>

<h2>Dos condiciones con coma</h2>
<div class="coma">Con borde si mide menos de 600px o 900px o más</div>

<h2>Orientación</h2>
<div class="orientacion">Rojo en vertical · Verde en horizontal</div>

<h2>Rangos que no se tocan</h2>
<div class="sin-cubrir">Rojo hasta 500px · Verde desde 700px · Gris entre los dos</div>

<h2>El orden de las reglas</h2>
<div class="orden">La regla de 700px va después</div>
<div class="orden-inverso">La regla de 700px va antes</div>
```

La hoja `css/condiciones.css`:

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

div {
  padding: 1rem;
  margin-bottom: 1rem;
}

/* Tres tramos, cada uno con su rango */
.rango {
  background-color: #fee2e2;
}

@media (min-width: 600px) and (max-width: 899px) {
  .rango {
    background-color: #fef3c7;
  }
}

@media (min-width: 900px) {
  .rango {
    background-color: #dcfce7;
  }
}

/* La coma funciona como «o»: basta con que se cumpla una condición */
.coma {
  border: 0 solid #111827;
}

@media (max-width: 599px), (min-width: 900px) {
  .coma {
    border-width: 4px;
  }
}

/* Dos rangos que no se tocan: entre 501px y 699px no se aplica ninguno y queda el estilo base */
.sin-cubrir {
  background-color: #e5e7eb;
}

@media (max-width: 500px) {
  .sin-cubrir {
    background-color: #fee2e2;
  }
}

@media (min-width: 700px) {
  .sin-cubrir {
    background-color: #dcfce7;
  }
}

/* La orientación depende de la forma de la ventana, no de su ancho */
.orientacion {
  background-color: #fee2e2;
}

@media (orientation: landscape) {
  .orientacion {
    background-color: #dcfce7;
  }
}

/* Con dos consultas que coinciden, gana la que aparece DESPUÉS */
.orden {
  color: #111827;
}

@media (min-width: 600px) {
  .orden {
    color: #dc2626;
  }
}

@media (min-width: 700px) {
  .orden {
    color: #2563eb;
  }
}

/* Mismas dos reglas con el orden invertido: ahora gana la de 600px */
.orden-inverso {
  color: #111827;
}

@media (min-width: 700px) {
  .orden-inverso {
    color: #2563eb;
  }
}

@media (min-width: 600px) {
  .orden-inverso {
    color: #dc2626;
  }
}
```

## 🔍 Análisis paso a paso

1. **Un rango con `and`.** `(min-width: 600px) and (max-width: 899px)` exige que se cumplan **las dos** condiciones: la ventana mide entre `600px` y `899px`. `.rango` es rojo por defecto, amarillo en ese tramo y verde desde `900px`.
2. **Una lista con coma.** `(max-width: 599px), (min-width: 900px)` se lee con «**o**»: basta con que se cumpla **una**. `.coma` recibe un borde de `4px` en `500px` y en `1200px`, y ninguno (`0px`) en `800px`.
3. **La orientación.** `(orientation: landscape)` depende de la **forma** de la ventana, no de su ancho. Es `landscape` (horizontal) si el ancho es **mayor** que el alto, y `portrait` (vertical) si el alto es mayor o **igual** al ancho. Por eso `.orientacion` es roja en `500×800` y en `800×800` (alto igual al ancho: vertical) y verde en `1200×800`. MDN aclara que no tiene que ver con la orientación física del dispositivo.
4. **Rangos que no se tocan.** `.sin-cubrir` tiene `max-width: 500px` (rojo) y `min-width: 700px` (verde). Entre `501px` y `699px` **no se cumple ninguna** y queda el estilo base (gris): con una ventana de `600px` se ve gris. Revisá siempre que los rangos de tus consultas se **toquen** (`599px` y `600px`, no `500px` y `700px`).
5. **El orden importa.** Si dos consultas coinciden y afectan lo mismo, **gana la que aparece después** (misma especificidad). En `800px` coinciden `min-width: 600px` y `min-width: 700px`. En `.orden` la de `700px` va **después**: el texto es azul. En `.orden-inverso` la de `600px` va después: el texto es rojo, aunque la condición de `700px` sea más estricta. La **posición** decide, no el valor.
6. **Regla práctica.** Con **móvil primero**, escribí las consultas de `min-width` de **menor a mayor**: así la más grande va después y gana en las ventanas anchas, como se espera.

## ✅ Resultado esperado

| Elemento | `500px` (alto `800`) | `800px` (alto `800`) | `1200px` (alto `800`) |
|---|---|---|---|
| `.rango`, fondo | rojo `rgb(254, 226, 226)` | amarillo `rgb(254, 243, 199)` | verde `rgb(220, 252, 231)` |
| `.coma`, borde | `4px` | `0px` | `4px` |
| `.orientacion`, fondo | rojo (vertical) | rojo (vertical) | verde (horizontal) |
| `.orden`, color | negro base `rgb(17, 24, 39)` | azul `rgb(37, 99, 235)` | azul |
| `.orden-inverso`, color | negro base | rojo `rgb(220, 38, 38)` | rojo |

- `.sin-cubrir`: rojo en `500px`, **gris** `rgb(229, 231, 235)` en `600px`, verde en `800px` y `1200px`.

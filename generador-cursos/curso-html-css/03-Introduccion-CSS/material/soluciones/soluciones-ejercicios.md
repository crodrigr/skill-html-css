# 🔑 Soluciones — Ejercicios de la Clase 03 (material docente)

No compartir este archivo con los estudiantes.

Todo el CSS de estas soluciones pasó la revisión de estructura del curso y sus resultados se comprobaron en Chrome leyendo los
estilos calculados. Los ejercicios **cerrados** tienen una sola respuesta defendible.

---

## 🟢 Básico 01 — Enlazá una hoja de estilos y escribí tres reglas

### ✅ Respuesta o criterio

En `basico-01.html`, dentro de `<head>`:

```html
<link rel="stylesheet" href="css/basico-01.css">
```

En `css/basico-01.css`:

```css
/* Hoja de estilos de Mateo Ruiz (ejercicio Básico 01) */
h1 {
  color: #16a34a;
}

.destacado {
  color: #111827;
  background-color: #fef3c7;
}

#aviso {
  color: #b45309;
}
```

**Preguntas.** CSS significa *Cascading Style Sheets* (hojas de estilo en cascada). Se usa una hoja externa porque un solo archivo da
estilo a todas las páginas del sitio y mantiene el HTML limpio; el estilo en línea obliga a repetir y se considera una mala práctica.

### 🔍 Justificación

La forma adecuada para un sitio de varias páginas es el archivo externo. Cada regla usa un tipo de selector distinto: elemento (`h1`), clase
(`.destacado`) e identificador (`#aviso`).

### 🔎 Verificación

Colores calculados: `h1` `rgb(22, 163, 74)`; `.destacado` texto `rgb(17, 24, 39)` sobre fondo `rgb(254, 243, 199)`; `#aviso`
`rgb(180, 83, 9)`. La hoja pasa `validar_css.py` sin errores.

---

## 🟢 Básico 02 — ¿Qué regla gana?

### ✅ Respuesta o criterio

| Caso | Color | Por qué |
|---|---|---|
| A. `<p>` común | `#111827` → `rgb(17, 24, 39)` | Solo lo alcanza `p` |
| B. `<h2 class="oferta">` | `#b45309` → `rgb(180, 83, 9)` | La clase `.oferta` (10) gana a `h2` (1) |
| C. `<p id="especial" class="oferta">` | `#7c3aed` → `rgb(124, 58, 237)` | El identificador (100) gana a la clase (10) y al elemento (1) |
| D. `<p class="aviso">` | `#be123c` → `rgb(190, 18, 60)` | Las dos reglas `.aviso` pesan igual: gana la última |
| E. `<p class="urgente" id="especial-dos">` | `#dc2626` → `rgb(220, 38, 38)` | `!important` anula la especificidad: gana `.urgente` aunque `#especial-dos` sea más específico |
| F. `<em>` dentro de `<p class="oferta">` | `#b45309` → `rgb(180, 83, 9)` | El `em` no tiene regla propia y **hereda** el color de su padre |

**Edición en vivo.** El archivo `basico-02.css` **no cambia**: lo que se edita en las herramientas es una prueba en pantalla.

### 🔍 Justificación

Se aplican, en orden, el origen y la importancia, la especificidad y el orden de aparición. Todas las reglas son del autor; solo el caso E
usa `!important`.

### 🔎 Verificación

Los seis colores coinciden con los estilos calculados en Chrome.

---

## 🟡 Intermedio 01 — Variables y formas de escribir un color

### ✅ Respuesta o criterio

```css
/* Hoja de Mateo con variables (ejercicio Intermedio 01) */
:root {
  --color-oscuro: #111827;
  --color-verde: #16a34a;
  --color-crema: #fef3c7;
}

body {
  color: var(--color-oscuro);
  background-color: var(--color-crema);
}

h1 {
  color: var(--color-crema);
  background-color: var(--color-oscuro);
}

h2 {
  color: var(--color-verde);
}

a {
  color: var(--color-verde);
}

.destacado {
  color: var(--color-oscuro);
  background-color: #ffffff;
  border-style: solid;
  border-width: 2px;
  border-color: var(--color-verde);
}

.cita {
  background-color: rgb(22 163 74 / 0.2);
}
```

**Parte B — el verde `#16a34a` de cuatro formas** (valores calculados en Chrome):

| Forma | Se escribe | Color calculado |
|---|---|---|
| Hexadecimal | `#16a34a` | `rgb(22, 163, 74)` |
| RGB | `rgb(22, 163, 74)` | `rgb(22, 163, 74)` |
| HSL | `hsl(142, 76%, 36%)` | `rgb(22, 162, 73)` (casi igual: el HSL redondeado pierde un punto en dos canales) |
| RGB con 50% de transparencia | `rgb(22 163 74 / 0.5)` (también valen `#16a34a80` y `hsl(142 76% 36% / 50%)`) | `rgba(22, 163, 74, 0.5)` |

### 🔍 Justificación

Cada color de la paleta se define una sola vez en `:root` y se usa con `var()`. El color con transparencia de la cita se escribe con
canal alfa (`rgb(22 163 74 / 0.2)`), porque una variable de hexadecimal no admite alfa de esta forma. No se usa `opacity`: afectaría
también al texto de la cita.

### 🔎 Verificación

Colores calculados: `body` `rgb(17, 24, 39)` sobre `rgb(254, 243, 199)`; `h1` con fondo `rgb(17, 24, 39)`; `h2` y enlaces
`rgb(22, 163, 74)`; borde de `.destacado` `rgb(22, 163, 74)`; `.cita` `rgba(22, 163, 74, 0.2)`. La hoja pasa `validar_css.py` sin errores (todas
las variables están definidas).

---

## 🟡 Intermedio 02 — Gradientes, imágenes y opacidad

### ✅ Respuesta o criterio

```css
/* Una caja de práctica (ejercicio Intermedio 02) */
.caja {
  width: 400px;
  height: 80px;
  color: #ffffff;
  background-color: #111827;
}

.lineal {
  background-image: linear-gradient(90deg, #111827, #16a34a);
}

.radial {
  background-image: radial-gradient(circle, #fef3c7, #16a34a);
}

.mosaico {
  color: #111827;
  background-image: url("../imagenes/patron.png");
  background-repeat: repeat;
}

.portada {
  color: #111827;
  background-image: url("../imagenes/portada.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.tenue {
  opacity: 0.6;
}

.vidrio {
  background-color: rgb(22 163 74 / 0.5);
}
```

**Respuestas.** `.tenue` atenúa el texto porque `opacity` afecta al elemento completo, con su contenido; `.vidrio` solo atenúa el fondo
porque el canal alfa pertenece al color de fondo, no al elemento. La ruta de `url()` se cuenta **desde el archivo CSS** (por eso
`../imagenes/…` desde `css/`).

### 🔍 Justificación

Los gradientes son imágenes: van en `background-image`. El mosaico usa `repeat`; la portada, `no-repeat`, `cover` y `center`.

### 🔎 Verificación

Valores calculados: `.lineal` `linear-gradient(90deg, rgb(17, 24, 39), rgb(22, 163, 74))`; `.radial`
`radial-gradient(circle, rgb(254, 243, 199), rgb(22, 163, 74))`; `.mosaico` `repeat`; `.portada` `cover` y `50% 50%`; `.tenue` opacidad `0.6`;
`.vidrio` fondo `rgba(22, 163, 74, 0.5)` y texto `rgb(255, 255, 255)`. Las dos imágenes se ven (captura).

---

## 🔴 Desafío 01 — Dale estilo a la página de Mateo

### ✅ Respuesta o criterio

```css
/* Hoja de estilos de Mateo Ruiz (Desafío 01) */

/* Variables: cada color se define una sola vez */
:root {
  --color-oscuro: #111827;
  --color-verde: #16a34a;
  --color-crema: #fef3c7;
}

/* Estilos generales */
body {
  color: var(--color-oscuro);
  background-color: var(--color-crema);
}

/* Títulos: el h1 lleva un gradiente lineal */
h1 {
  color: var(--color-crema);
  background-color: var(--color-oscuro);
  background-image: linear-gradient(90deg, var(--color-oscuro), var(--color-verde));
}

h2 {
  color: var(--color-oscuro);
}

a {
  color: var(--color-verde);
}

/* Una clase y un identificador */
.destacado {
  color: var(--color-verde);
  background-color: #ffffff;
}

#portada {
  background-color: var(--color-crema);
  background-image: url("../imagenes/portada.png");
  background-repeat: no-repeat;
  background-size: cover;
}

/* Citas: un color con transparencia (canal alfa) */
blockquote {
  background-color: rgb(22 163 74 / 0.2);
}

/* Pie: imagen que se repite */
footer {
  background-color: var(--color-crema);
  background-image: url("../imagenes/patron.png");
  background-repeat: repeat;
}

small {
  opacity: 0.7;
}
```

### 🔍 Justificación

Las variables concentran la paleta. El `h1` usa el gradiente con las variables; la portada y el pie usan imágenes de fondo con un color de
respaldo; la cita usa un color con alfa; y la letra chica, `opacity`. No hace falta `!important` porque ninguna regla compite con otra de la
misma especificidad.

### 🔎 Verificación

Se cumplen los 13 casos de prueba:

| # | Resultado |
|---|---|
| 1 | `:root` define las tres variables |
| 2 | `body`: `rgb(17, 24, 39)` y fondo `rgb(254, 243, 199)` |
| 3 | `h1`: `rgb(254, 243, 199)` y `linear-gradient(90deg, rgb(17, 24, 39), rgb(22, 163, 74))` |
| 4 | `h2`: `rgb(17, 24, 39)` |
| 5 | Enlaces: `rgb(22, 163, 74)` |
| 6 | `.destacado`: `rgb(22, 163, 74)` |
| 7 | `#portada`: imagen, `no-repeat` y `cover` |
| 8 | `blockquote`: `rgba(22, 163, 74, 0.2)` |
| 9 | `footer`: imagen con `repeat` |
| 10 | `small`: opacidad `0.7` |
| 11 | Los colores de la paleta aparecen una sola vez, en `:root` (salvo el verde con alfa del `blockquote`) |
| 12 | No hay `!important`, `style` ni `<style>` |
| 13 | `validar_css.py` da 0 errores |

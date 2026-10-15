# 🔑 Soluciones — Ejercicios de la Clase 04 (material docente)

No compartir este archivo con los estudiantes.

Todo el CSS de estas soluciones pasó la revisión de estructura del curso (`validar_css.py`), los conteos de elementos se comprobaron con
`probar_selectores.py` y los estilos, con `probar_estilos.py` (con estados simulados donde corresponde). Los ejercicios **cerrados** tienen una sola
respuesta defendible; en cada selector se aceptan equivalentes que eligen exactamente lo mismo.

---

## 🟢 Básico 01 — Elegí los elementos justos

### ✅ Respuesta o criterio

```css
/* Hoja de estilos de Mateo Ruiz (ejercicio Básico 01) */
h2 {
  background-color: #fef3c7;
}

#reserva {
  color: #16a34a;
}

.precio {
  color: #111827;
}

a[href^="https"] {
  color: #16a34a;
}

a[href$=".pdf"] {
  font-weight: bold;
}

input[type="email"] {
  background-color: #fef3c7;
}

a[target="_blank"] {
  background-color: #fef3c7;
}
```

| # | Elegir | Selector | Elementos |
|---|---|---|---|
| 1 | Títulos de segundo nivel | `h2` | 3 |
| 2 | El elemento con `id="reserva"` | `#reserva` | 1 |
| 3 | Párrafos de clase `precio` | `.precio` (o `p.precio`) | 3 |
| 4 | Enlaces que empiezan con `https` | `a[href^="https"]` | 2 |
| 5 | Enlaces que terminan en `.pdf` | `a[href$=".pdf"]` | 1 |
| 6 | Campos de tipo correo | `input[type="email"]` | 1 |
| 7 | Enlaces en pestaña nueva | `a[target="_blank"]` | 1 |

**Preguntas.** `a[href^="https"]` exige que el valor **empiece** con `https`; `a[href*="https"]` basta con que lo **contenga** en cualquier lugar. `.precio` elige cualquier
elemento con esa clase; `p.precio`, solo los párrafos con esa clase (más específico).

### 🔍 Justificación

Cada selector usa la forma que corresponde: elemento, identificador, clase y los operadores de atributo `^=`, `$=` y `=`.

### 🔎 Verificación

Los siete conteos coinciden con la tabla y la hoja pasa `validar_css.py` sin errores.

---

## 🟢 Básico 02 — Renombrá las clases con BEM

### ✅ Respuesta o criterio

| Clase actual | Nombre BEM |
|---|---|
| `caja` | `foto` (bloque) |
| `destacada` | `foto--destacada` (modificador del bloque) |
| `img` | `foto__imagen` (elemento) |
| `t` | `foto__titulo` (elemento) |
| `autor` | `foto__autor` (elemento) |
| `btn` | `foto__boton` (elemento) |
| `btn-grande` | `foto__boton--grande` (modificador del elemento) |

En el HTML, los modificadores van junto a la clase de su bloque o elemento: `class="foto foto--destacada"` y `class="foto__boton foto__boton--grande"`.

El HTML actualizado (`basico-02.html`):

```html
<h1>Foto del mes</h1>

<div class="foto foto--destacada">
  <img class="foto__imagen" src="imagenes/paisaje.png" alt="Montañas al atardecer" width="240">
  <h2 class="foto__titulo">Montañas al atardecer</h2>
  <p class="foto__autor">Foto de Mateo Ruiz</p>
  <a class="foto__boton foto__boton--grande" href="galeria.html">Ver la galería</a>
</div>

<div class="foto">
  <img class="foto__imagen" src="imagenes/retrato.png" alt="Retrato de una persona con un buzo violeta" width="240">
  <h2 class="foto__titulo">Retrato en el estudio</h2>
  <p class="foto__autor">Foto de Mateo Ruiz</p>
  <a class="foto__boton" href="galeria.html">Ver la galería</a>
</div>
```

La hoja actualizada (`css/basico-02.css`):

```css
/* Hoja de Mateo con nombres BEM (ejercicio Básico 02) */
.foto {
  background-color: #ffffff;
  border-style: solid;
  border-width: 1px;
  border-color: #cbd5e1;
}

.foto--destacada {
  background-color: #fef3c7;
  border-color: #16a34a;
}

.foto__imagen {
  border-style: solid;
  border-width: 2px;
  border-color: #16a34a;
}

.foto__titulo {
  color: #111827;
}

.foto__autor {
  color: #1f2937;
}

.foto__boton {
  color: #16a34a;
}

.foto__boton--grande {
  font-size: 24px;
}
```

**Preguntas.** `foto__boton` y no `foto__enlace__boton` porque en BEM **no hay elementos de elementos**: el botón es una parte de la foto, aunque en el HTML esté dentro de
otra etiqueta. En la convención oficial de bem.info, el modificador se une con **un guion bajo** (`foto_destacada`, `foto__boton_grande`); los dos guiones son una variante habitual.

### 🔍 Justificación

El bloque es el componente independiente; los elementos son sus partes y se unen con `__`; los modificadores son variantes y se unen con `--`.

### 🔎 Verificación

Conteos: `.foto` 2, `.foto--destacada` 1, `.foto__imagen` 2, `.foto__titulo` 2, `.foto__autor` 2, `.foto__boton` 2 y `.foto__boton--grande` 1. Los estilos calculados son idénticos a los de la
hoja original (fondo `rgb(254, 243, 199)`, borde `rgb(22, 163, 74)`, botón grande de `24px`).

---

## 🟡 Intermedio 01 — Combinadores y selectores lógicos

### ✅ Respuesta o criterio

```css
/* Hoja de estilos de Mateo Ruiz (ejercicio Intermedio 01) */
nav a {
  color: #16a34a;
}

ul.menu > li {
  background-color: #fef3c7;
}

h2 + p {
  color: #16a34a;
}

h2 ~ p {
  background-color: #fef3c7;
}

:is(h1, h2, h3) {
  color: #111827;
}

a:not([href^="https"]) {
  background-color: #dbeafe;
}

article:has(img) {
  border-style: solid;
  border-width: 2px;
  border-color: #16a34a;
}
```

| # | Elegir | Selector | Elementos |
|---|---|---|---|
| a | Enlaces dentro del `nav` | `nav a` | 3 |
| b | `li` hijos directos de `ul.menu` | `ul.menu > li` (o `.menu > li`) | 3 |
| c | Párrafo inmediatamente después de un `h2` | `h2 + p` | 1 |
| d | Párrafos hermanos que siguen a un `h2` | `h2 ~ p` | 3 |
| e | Títulos de primer, segundo y tercer nivel | `:is(h1, h2, h3)` | 8 |
| f | Enlaces no externos | `a:not([href^="https"])` | 4 |
| g | Tarjetas con imagen | `article:has(img)` | 2 |

**Parte B.**

```css
h3 {
  color: #16a34a;
}

:where(h2, h3) {
  color: #111827;
}
```

1. Con `:where()`, el `h3` se ve **verde** (`rgb(22, 163, 74)`): `:where()` vale **cero**, y la regla `h3` vale `0-0-1`, así que gana aunque venga antes.
2. Con `:is()` en lugar de `:where()`, el `h3` se ve **gris oscuro** (`rgb(17, 24, 39)`): `:is(h2, h3)` toma la especificidad de su argumento más específico (`0-0-1`), igual que la
   regla `h3`, y entonces gana la **última**.

### 🔍 Justificación

Los combinadores relacionan elementos por su posición; los selectores lógicos agrupan, excluyen y miran el contenido. La diferencia entre `:where()` y `:is()` está en la especificidad.

### 🔎 Verificación

Los siete conteos coinciden con la tabla. En la Parte B, los colores calculados del `h3` son los indicados. La hoja pasa `validar_css.py` sin errores.

---

## 🟡 Intermedio 02 — Estilos según el estado y la posición

### ✅ Respuesta o criterio

```css
/* Hoja de estilos de Mateo Ruiz (ejercicio Intermedio 02) */
/* Orden de los estados de enlace: normal, cursor, foco */
nav a:hover {
  color: #16a34a;
}

a:focus {
  background-color: #fef3c7;
}

.boton:active {
  background-color: #16a34a;
}

input:checked + label {
  color: #16a34a;
}

input:disabled {
  background-color: #e5e7eb;
}

tbody tr:nth-child(even) {
  background-color: #fef3c7;
}

li:first-child {
  font-weight: bold;
}

li:last-child {
  font-weight: bold;
}

li:nth-child(3) {
  color: #16a34a;
}

li:only-child {
  background-color: #fef3c7;
}
```

**Conteos y resultados.** `tbody tr:nth-child(even)` elige **3** filas; `li:first-child`, **2**; `li:last-child`, **2**; `li:nth-child(3)`, **1**; `li:only-child`, **1**. Con el estado simulado,
el enlace del menú se ve verde (`rgb(22, 163, 74)`) con el cursor, y con fondo crema (`rgb(254, 243, 199)`) con el foco; el botón presionado tiene fondo `rgb(22, 163, 74)`. La etiqueta de la
casilla marcada se ve verde, la de la desmarcada sigue negra, y el campo deshabilitado tiene fondo `rgb(229, 231, 235)`.

**Sobre `:visited`.** No se puede comprobar con una prueba automática: por privacidad, el navegador limita lo que se puede cambiar con `:visited` y hace que las herramientas de lectura de
estilos informen el color de un enlace **sin visitar**.

### 🔍 Justificación

Cada estado y cada posición se eligen con la pseudoclase que corresponde. Los estados de enlace van en orden (cursor y después foco) y no se quita el indicador de foco.

### 🔎 Verificación

Los conteos y los estilos coinciden con lo indicado y la hoja pasa `validar_css.py` sin errores.

---

## 🔴 Desafío 01 — Dale estilo a la página de Mateo con selectores precisos

### ✅ Respuesta o criterio

```css
/* Hoja de estilos de Mateo Ruiz (Desafío 01) */

/* Base: texto, fondo y títulos */
body {
  color: #111827;
  background-color: #fef3c7;
}

:is(h2, h3) {
  color: #111827;
}

/* Menú: enlaces del nav y enlace activo */
nav a {
  color: #16a34a;
}

.menu__enlace--activo {
  font-weight: bold;
}

/* Enlaces según su dirección */
a[href^="https"] {
  background-color: #fef3c7;
}

a[href$=".pdf"] {
  font-weight: bold;
}

a:not([href^="https"]) {
  text-decoration-color: #16a34a;
}

/* Componente foto (BEM) */
.foto {
  background-color: #ffffff;
  border-style: solid;
  border-width: 1px;
  border-color: #cbd5e1;
}

.foto--destacada {
  background-color: #fef3c7;
}

.foto__titulo--grande {
  font-size: 28px;
}

/* :has() con la clase del bloque, para que su especificidad supere a la de .foto */
.foto:has(img) {
  border-color: #16a34a;
}

/* Estados */
a:hover {
  color: #16a34a;
}

a:focus {
  background-color: #fef3c7;
}

.boton:active {
  background-color: #16a34a;
}

input:disabled {
  background-color: #e5e7eb;
}

input:checked + label {
  color: #16a34a;
}

/* Posición */
tbody tr:nth-child(even) {
  background-color: #fef3c7;
}

h2 + p {
  color: #16a34a;
}
```

**Un punto clave.** La regla del bloque `foto` fija el color del borde (`0-1-0`). Un `article:has(img)` valdría solo `0-0-2` y **perdería**; por eso la regla usa `.foto:has(img)`
(`0-1-1`), que sí gana.

### 🔍 Justificación

Cada requisito usa el selector que le corresponde: atributos para los enlaces, BEM para el componente, `:has()` para las tarjetas con imagen, `:not()` para los enlaces no externos, pseudoclases para los estados y la
posición, y la hoja queda ordenada por temas y comentada, sin repetir reglas ni usar `!important`.

### 🔎 Verificación

Se cumplen los 18 casos de prueba (comprobados en Chrome, con los estados simulados):

| # | Resultado |
|---|---|
| 1 | `body`: `rgb(17, 24, 39)` sobre `rgb(254, 243, 199)` |
| 2 | `h2` y `h3`: `rgb(17, 24, 39)` |
| 3 | `nav a`: `rgb(22, 163, 74)` (4 enlaces) |
| 4 | `.menu__enlace--activo`: `700` |
| 5 | `a[href^="https"]` (2): fondo `rgb(254, 243, 199)` |
| 6 | `a[href$=".pdf"]`: `700` |
| 7 | `.foto--destacada`: fondo `rgb(254, 243, 199)` |
| 8 | `.foto__titulo--grande`: `28px` |
| 9 | Las dos tarjetas con imagen: borde `rgb(22, 163, 74)` |
| 10 | La tarjeta sin imagen: borde `rgb(203, 213, 225)` |
| 11 | Enlace con el cursor: `rgb(22, 163, 74)` |
| 12 | Enlace con el foco: fondo `rgb(254, 243, 199)` |
| 13 | `.boton` presionado: fondo `rgb(22, 163, 74)` |
| 14 | `input:disabled`: fondo `rgb(229, 231, 235)`; etiqueta de la casilla marcada: `rgb(22, 163, 74)` |
| 15 | Filas pares del cuerpo (2): fondo `rgb(254, 243, 199)` |
| 16 | `h2 + p` (1): `rgb(22, 163, 74)` |
| 17 | Enlaces no externos (6): `text-decoration-color` `rgb(22, 163, 74)` |
| 18 | Sin `!important`, sin reglas repetidas, con comentarios; `validar_css.py` da 0 errores |

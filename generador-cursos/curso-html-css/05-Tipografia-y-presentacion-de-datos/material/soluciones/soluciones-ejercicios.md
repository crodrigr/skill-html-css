# 🔑 Soluciones — Ejercicios de la Clase 05 (material docente)

No compartir este archivo con los estudiantes. Cada hoja se probó en Chrome sobre la página de partida del ejercicio: pasa `validar_css.py` y cumple todos los valores calculados y las medidas de
su tabla. Las medidas de `scrollWidth` y de los márgenes automáticos dependen de la ventana y del sistema; los casos de prueba piden solo lo que no depende de ellos.

---

## 🟢 Básico 01 — Dale forma al texto de una entrada

```css
/* Tipografía base de la página */
body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
}

/* Títulos con serifa */
h1, h2 {
  font-family: Georgia, "Times New Roman", serif;
}

.titulo {
  text-align: center;
}

/* Entradilla y fecha */
.intro {
  font-size: 1.25rem;
  font-style: italic;
}

.fecha {
  font-size: 0.875rem;
  text-transform: uppercase;
  letter-spacing: 1px;
}

/* Párrafos del cuerpo del artículo */
.cuerpo p {
  text-indent: 1.5rem;
  text-align: justify;
}
```

**Parte B.**

1. Porque no hay garantía de que ninguna de las tipografías nombradas esté instalada. La familia genérica final (`sans-serif` o `serif`) deja que el navegador elija una de ese tipo como último recurso.
2. Dentro de un contenedor de `1.25rem` (`20px`), `1.25em` se mide contra el contenedor y da `25px`; `1.25rem` se mide siempre contra la raíz y da `20px`.
3. Un número sin unidad se multiplica por el tamaño de la propia letra de cada elemento. Con `160%`, el valor se calcula una vez en el padre y los hijos heredan los píxeles ya calculados, que pueden quedar chicos o grandes para sus letras.

**Comprobación.** `h1, h2` elige 3 elementos; `.cuerpo p`, 3. Valores calculados: `body` `16px` y `25.6px`; `.intro` `20px` e `italic`; `.fecha` `14px`, `uppercase` y `1px`; `.cuerpo p` `24px` y `justify`.

---

## 🟢 Básico 02 — Presentá los precios con una tabla y una lista

```css
/* Tabla: bordes unidos, a todo el ancho */
table {
  border-collapse: collapse;
  width: 100%;
}

th, td {
  border: 1px solid #111827;
  padding: 8px 12px;
  text-align: left;
}

th {
  color: #fef3c7;
  background-color: #111827;
}

/* Las cifras, a la derecha */
.horas, .precio {
  text-align: right;
}

caption {
  caption-side: bottom;
}

/* Filas alternas */
tbody tr:nth-child(even) {
  background-color: #fef3c7;
}

/* Listas */
.incluye {
  list-style-type: square;
  list-style-position: inside;
}

.pasos {
  list-style-type: upper-roman;
}

.pasos li {
  margin-bottom: 0.5rem;
}
```

**Parte B.** Sin `border-collapse: collapse`, cada celda dibuja su **propio borde** (el valor inicial es `separate`) y entre dos celdas se ven **dos líneas** con un espacio entre ellas. La distancia la controla
`border-spacing`.

**Comprobación.** `.horas` y `.precio` eligen 6 elementos cada uno (12 en total); `tbody tr:nth-child(even)` elige 2; `.pasos li`, 3. La clase `.horas, .precio` pesa más que `th, td`, por eso las cifras
quedan a la derecha aunque `th, td` pida la izquierda.

---

## 🟡 Intermedio 01 — Un informe con texto, datos y decoraciones

```css
/* Base */
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.6;
  color: #111827;
}

h1 {
  font-family: Georgia, "Times New Roman", serif;
  text-shadow: 2px 2px 4px #16a34a;
}

/* Aviso */
.aviso {
  text-transform: uppercase;
  letter-spacing: 2px;
  font-weight: 700;
}

/* Precio anterior y precio nuevo */
.antes {
  text-decoration: line-through #dc2626;
}

.nuevo {
  font-weight: 700;
  color: #16a34a;
}

/* Menú: sin subrayado, que aparece al pasar el cursor */
nav a {
  text-decoration: none;
}

nav a:hover {
  text-decoration: underline;
}

.volver {
  text-decoration: underline wavy #16a34a;
}

/* Tabla */
table {
  border-collapse: collapse;
}

th, td {
  border: 1px solid #111827;
  padding: 8px 12px;
}

.cantidad {
  text-align: right;
}

/* Lista */
.pendientes {
  list-style-type: square;
}
```

**Parte B.** Respuesta de ejemplo: al quitar el subrayado, el menú se distingue por estar en un bloque aparte, en un color distinto del texto y porque aparece el subrayado al pasar el cursor. Importa porque mucha gente reconoce
los enlaces por su subrayado (MDN lo advierte); si desaparece, hay que dejar otra señal clara, como un color con buen contraste o un fondo.

**Criterios.** Cualquier respuesta que (a) nombre al menos una señal alternativa (color, negrita, fondo, subrayado al pasar el cursor) y (b) explique que sirve para reconocerlos como enlaces.

**Comprobación.** `nav a` elige 2 enlaces; `.cantidad`, 4 celdas. Con el estado `hover` simulado, `nav a` calcula `underline`.

---

## 🟡 Intermedio 02 — Bordes por lado y esquinas

```css
/* Aspecto común: el relleno separa el texto del borde */
div {
  padding: 8px;
  margin-bottom: 12px;
}

.nota {
  border: 2px solid #111827;
}

/* Una barra solo a la izquierda */
.aviso {
  border-left: 6px solid #16a34a;
}

/* Un borde distinto por lado */
.recuadro {
  border-top: 4px solid #111827;
  border-right: 1px solid #111827;
  border-bottom: 4px double #111827;
  border-left: 1px solid #111827;
}

/* Dos valores: arriba y abajo / izquierda y derecha */
.etiqueta {
  border-style: solid;
  border-width: 1px 4px;
  border-color: #111827 #16a34a;
}

.redonda {
  border: 1px solid #111827;
  border-radius: 12px;
}

/* Un círculo: caja cuadrada y radio del 50% */
.circulo {
  width: 80px;
  height: 80px;
  border: 2px solid #16a34a;
  border-radius: 50%;
}

/* Solo las dos esquinas de arriba */
.pestana {
  border: 1px solid #111827;
  border-radius: 16px 16px 0 0;
}

.esquina {
  border: 1px solid #111827;
  border-bottom-right-radius: 24px;
}
```

**Parte B.**

1. No: sin estilo el borde no se dibuja. El estilo inicial es `none` y el grosor calculado es `0px`, aunque se haya escrito `3px`.
2. Porque el `width` de `80px` es solo el del **contenido**: se suman `8px` de relleno por lado (la regla `div`) y `2px` de borde por lado, y la caja mide `80 + 16 + 4 = 100px`. Como el alto suma lo mismo, sigue siendo
   un cuadrado y, con `50%`, un círculo.

**Comprobación.** `.circulo`: `offsetWidth` y `offsetHeight` de `100`. `.recuadro`: `4px solid`, `1px solid`, `4px double`, `1px solid`. `.pestana`: `16px`, `16px`, `0px`, `0px`.

---

## 🟡 Intermedio 03 — Medí las cajas

**Parte A.**

| Caja | Cálculo | Ancho de borde a borde | Con márgenes |
|---|---|---|---|
| `.c1` | `300 + 10 + 10 + 2 + 2` (por defecto) | **324** | `324 + 8 + 8` = **340** |
| `.c2` | `150 + 30 + 30 + 4 + 4` (por defecto; el relleno horizontal es `30px`) | **218** | sin margen: 218 |
| `.c3` | `border-box`: el `width` ya incluye todo | **250** (el contenido queda en `250 − 40 − 10` = 200) | sin margen: 250 |

**Partes B, C y D.** La hoja completa (las reglas de `.c1`, `.c2` y `.c3` ya venían escritas; se agregan las de `.c4`, `.c5`, `.visor`, `.p1`, `.p2` y `.centrada`):

```css
/* Tres cajas ya escritas: calculá su tamaño antes de medirlas */
.c1 {
  width: 300px;
  padding: 10px;
  border: 2px solid #111827;
  margin: 8px;
}

.c2 {
  width: 150px;
  padding: 15px 30px;
  border: 4px solid #111827;
}

.c3 {
  box-sizing: border-box;
  width: 250px;
  padding: 20px;
  border: 5px solid #111827;
}

/* Un fondo para ver las demás cajas */
.c4, .c5, .p1, .p2, .centrada {
  background-color: #fef3c7;
}

.tira {
  width: 400px;
  height: 60px;
  background-color: #fef3c7;
}

.p1, .p2 {
  height: 40px;
}

/* c4: 320px de borde a borde con el cálculo por defecto: 320 - 20 - 20 - 5 - 5 = 270 */
.c4 {
  width: 270px;
  padding: 20px;
  border: 5px solid #111827;
}

/* c5: la misma medida con border-box: el ancho ya incluye relleno y borde */
.c5 {
  box-sizing: border-box;
  width: 320px;
  padding: 20px;
  border: 5px solid #111827;
}

/* Visor: el contenido ancho se recorre con una barra horizontal */
.visor {
  width: 200px;
  height: 100px;
  overflow-x: auto;
  overflow-y: hidden;
}

/* Márgenes verticales: colapsan en 24px, el mayor */
.p1 {
  margin-bottom: 24px;
}

.p2 {
  margin-top: 16px;
}

/* Centrada con márgenes automáticos */
.centrada {
  width: 300px;
  margin: 0 auto;
}
```

**Comprobación.** `.c4` y `.c5` miden `offsetWidth` `320`; `.visor` calcula `auto` y `hidden` y su `scrollWidth` es `400`; `.p2` empieza 24px después de que termina `.p1` (no 40); `.centrada` mide `300` y sus márgenes izquierdo
y derecho son iguales.

---

## 🔴 Desafío 01 — La tarjeta de Mateo

```css
/* Base */
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.6;
  color: #111827;
}

h2 {
  font-family: Georgia, "Times New Roman", serif;
  font-size: 1.5rem;
}

/* Tarjeta: 320px de borde a borde, borde distinto por lado, dos esquinas redondeadas */
.tarjeta {
  box-sizing: border-box;
  width: 320px;
  border-top: 4px solid #111827;
  border-right: 1px solid #111827;
  border-bottom: 4px double #16a34a;
  border-left: 1px solid #111827;
  border-radius: 16px 0;
  padding: 20px 24px;
  margin: 16px auto;
}

.tarjeta--destacada {
  background-color: #fef3c7;
}

.tarjeta__titulo {
  margin-top: 0;
}

/* El texto no crece: si no entra, se desplaza en vertical */
.tarjeta__texto {
  height: 80px;
  overflow-x: hidden;
  overflow-y: auto;
}
```

**Notas.**

- `box-sizing: border-box` con `width: 320px` logra los `320px` de borde a borde con una sola declaración de ancho; con el cálculo por defecto habría que restar relleno y borde (`320 − 48 − 2 = 270`).
- El contenido de `.tarjeta__texto` mide `270px` de ancho (`320 − 24 − 24 − 1 − 1`) y `80px` de alto.
- Las dos tarjetas quedan separadas por `16px`: el margen inferior de la primera (`16px`) colapsa con el superior de la segunda (`16px`), no se suman.
- `.tarjeta__texto` desplaza en vertical porque su contenido (el texto, de unos `237px` con este ancho, que varían con la tipografía) no entra en `80px`; `overflow-x: hidden` recorta lo que sobre en horizontal.

**Comprobación (11 casos de prueba).** Todos se cumplen sobre la página de partida con esta hoja: `offsetWidth` `320` en ambas tarjetas; bordes `4px solid rgb(17, 24, 39)`, `1px solid`, `4px double rgb(22, 163, 74)`, `1px solid`; esquinas
`16px`, `0px`, `16px`, `0px`; relleno `20px`, `24px`, `24px`; separación entre tarjetas `16`; fondo de la destacada `rgb(254, 243, 199)`; título con `Georgia, "Times New Roman", serif`, `24px` y margen superior `0px`; texto con
`offsetWidth` `270`, `offsetHeight` `80`, `overflow-y` `auto`, `overflow-x` `hidden`, y `scrollHeight` mayor que `clientHeight`.

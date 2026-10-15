# 📚 Explicación conceptual — Tipografía y presentación de datos

En las clases anteriores diste color y fondo a tus páginas y aprendiste a elegir con precisión qué elementos reciben cada regla. Ahora vas a darle **forma** al contenido:
cómo se ve el texto, cómo se presentan las tablas y las listas, y cómo se miden y se separan las cajas. Seguimos con el sitio de **Lucía Fernández**, con un artículo
(`articulo.html`) y una página de práctica por cada tema. Se recomienda haber hecho las Clases 01 a 04.

La clase se dicta en **dos sesiones**:

- 🕐 **Sesión 1 — Texto y datos** (bloques 1 a 5): tipografía, tipografías en CSS, textos y alineaciones, decoraciones y representación de datos.
- 🕑 **Sesión 2 — Cajas** (bloques 6 a 9): bordes, bordes redondeados, modelo de cajas y márgenes y rellenos.

Resultados de aprendizaje de la clase:

- **RA-1**: explicar qué es la tipografía y reconocer las familias tipográficas más comunes.
- **RA-2**: aplicar tipografías en CSS: familia con alternativas, tamaño, peso, estilo y altura de línea.
- **RA-3**: alinear y espaciar el texto.
- **RA-4**: aplicar decoraciones y sombras al texto.
- **RA-5**: dar estilo a tablas y listas para presentar datos.
- **RA-6**: crear bordes, incluidos bordes distintos en cada lado, y redondear sus esquinas.
- **RA-7**: explicar el modelo de cajas y controlar el desborde del contenido.
- **RA-8**: controlar márgenes y rellenos, incluidas sus abreviaturas.

## 🗒️ Glosario

| Término | Equivalente |
|---|---|
| *typography* | tipografía (el diseño de las letras) |
| *font family* | familia tipográfica |
| *serif* / *sans-serif* / *monospace* | con serifa / sin serifa / de ancho fijo |
| *line height* | altura de línea (interlineado) |
| *box model* | modelo de cajas |
| *padding* | relleno (espacio entre el contenido y el borde) |
| *margin* | margen (espacio fuera del borde) |
| *overflow* | desborde (contenido que no entra en su caja) |
| *margin collapsing* | colapso de márgenes |

> 📌 **Origen de la información.** Las descripciones están contrastadas con **MDN Web Docs**. Los valores calculados y las medidas de los ejemplos se comprobaron en un
> navegador. Las tipografías dependen de lo que tenga instalado cada equipo, por eso se describen de forma genérica.

---

## 🔤 Tipografía

_Sesión 1 · Resultados de aprendizaje: RA-1_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 01 — Tipografías en CSS](01-tipografias-en-css.md): las tres familias en uso, con el artículo de Lucía.

![Tres familias genéricas con una muestra de cada una: serif, con remates en los extremos de las letras; sans-serif, con extremos lisos; y monospace, donde todas las letras ocupan el mismo ancho.](../imagenes/familias-tipograficas.svg)

### 🌍 Contexto

Casi todo lo que hay en una página es texto. La forma de las letras cambia cómo se **lee** y qué **personalidad** transmite el sitio: no se ve igual un cuento infantil que
un contrato.

### 💡 Concepto

La **tipografía** es el diseño de las letras de un texto. Una **familia tipográfica** es un conjunto de letras con el mismo diseño (por ejemplo, Arial o Georgia), con sus
variantes de peso (fina, normal, negrita) y de estilo (normal, cursiva).

### 📖 Explicación

Las familias se agrupan según la forma de sus letras:

| Familia | Cómo son las letras | Se usa para | Ejemplos de tipografías |
|---|---|---|---|
| Con serifa (*serif*) | Los trazos terminan en pequeños remates | Títulos y textos largos impresos | Georgia, Times New Roman |
| Sin serifa (*sans-serif*) | Los trazos terminan lisos | Texto en pantalla, menús | Arial, Helvetica |
| De ancho fijo (*monospace*) | Todas las letras miden lo mismo | Código, datos alineados | Courier New |

**Qué hace legible a un texto.** Un tamaño cómodo, un buen contraste con el fondo, un espacio entre líneas suficiente y **pocas tipografías distintas** en la misma página
(dos o tres como máximo).

> 💡 Ni la tipografía ni el tamaño «correcto» son únicos: dependen del público y del soporte. Probá siempre con un texto real, no con «lorem ipsum».
>
> ⚠️ En esta clase usás solo **tipografías del sistema**, las que ya están instaladas en el equipo de quien visita la página. No hace falta descargar nada.

---

## 🅰️ Tipografías en CSS

_Sesión 1 · Resultados de aprendizaje: RA-2_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 01 — Tipografías en CSS](01-tipografias-en-css.md): pila de alternativas, tamaño y unidades, peso, estilo y altura de línea, con sus valores calculados.

### 🌍 Contexto

No sabés qué tipografías tiene instalada cada persona que visita tu sitio. Tenés que dar **alternativas** para que el texto se vea bien en cualquier equipo.

### 💡 Concepto

`font-family` recibe una **lista de tipografías** (una **pila**) en orden de preferencia: el navegador usa la primera que está instalada. Otras propiedades controlan el
tamaño (`font-size`), el peso (`font-weight`), el estilo (`font-style`) y la altura de línea (`line-height`).

### 📖 Explicación

**Familia con alternativas.**

```css
body {
  font-family: Arial, Helvetica, sans-serif;
}

h1 {
  font-family: Georgia, "Times New Roman", serif;
}
```

- Las alternativas se separan con **comas**, de la más a la menos preferida.
- Los nombres con espacios van **entre comillas**.
- La lista **termina siempre con una familia genérica** (`serif`, `sans-serif` o `monospace`): si ninguna de las anteriores está instalada, el navegador elige una de ese tipo.

**Tamaño y unidades.**

| Unidad | Se mide contra… | Con base `16px` |
|---|---|---|
| `px` | Un tamaño fijo en píxeles | `20px` = 20px |
| `em` | El tamaño de letra del elemento (en `font-size`, el del padre) | `1.25em` = 20px |
| `rem` | El tamaño de letra de la raíz (`html`) | `1.25rem` = 20px |
| `%` | El tamaño del padre | `125%` = 20px |

`em` se **acumula** al anidar elementos: un `1.25em` dentro de otro `1.25em` da `1,5625` veces el tamaño base. `rem` no se acumula. Además, las unidades relativas respetan el
tamaño que cada persona eligió en su navegador; por eso se recomiendan para el texto.

**Peso, estilo y altura de línea.**

| Propiedad | Valores | Qué hace |
|---|---|---|
| `font-weight` | `normal`, `bold`, o un número de 100 a 900 | Grosor de las letras (`700` = `bold`) |
| `font-style` | `normal`, `italic` | Cursiva |
| `line-height` | Un número sin unidad (`1.6`), una longitud o `normal` | Espacio de cada línea |

Con un número sin unidad, la altura de línea se multiplica por el tamaño de la propia letra (`1.6 × 16px = 25.6px`). Es la forma recomendada, porque con `em` o `%` el valor
calculado se hereda tal cual y puede dar resultados inesperados. Para el texto principal se recomienda **al menos `1.5`**.

> ⚠️ Un tamaño muy chico o una altura de línea de `1` vuelven el texto incómodo de leer.

---

## ✍️ Textos y alineaciones

_Sesión 1 · Resultados de aprendizaje: RA-3_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 02 — Textos y alineaciones](02-textos-y-alineaciones.md): alineación, sangría, espaciado entre letras y palabras, y mayúsculas.

### 🌍 Contexto

Un párrafo bien alineado y con un espaciado cómodo se lee casi sin esfuerzo; uno apretado o mal alineado cansa.

### 💡 Concepto

Estas propiedades controlan cómo se acomoda el texto dentro de su caja: `text-align` (alineación), `text-indent` (sangría), `letter-spacing` (espacio entre letras),
`word-spacing` (espacio entre palabras) y `text-transform` (mayúsculas y minúsculas).

### 📖 Explicación

| Propiedad | Valores | Qué hace |
|---|---|---|
| `text-align` | `left`, `center`, `right`, `justify` | Alinea el texto dentro de su caja |
| `text-indent` | Una longitud (`2rem`) o un porcentaje | Sangría de la **primera línea** |
| `letter-spacing` | `normal` o una longitud (`2px`) | Espacio **extra** entre letras |
| `word-spacing` | `normal` o una longitud (`10px`) | Espacio **extra** entre palabras |
| `text-transform` | `none`, `uppercase`, `lowercase`, `capitalize` | Cambia las mayúsculas **al mostrar** |

```css
.sangria {
  text-indent: 2rem;
}

.mayusculas {
  text-transform: uppercase;
}
```

- `justify` estira los espacios para que cada línea llegue de borde a borde; en columnas angostas deja «ríos» de espacio.
- Los valores de `letter-spacing` y `word-spacing` se **suman** al espacio normal y pueden ser negativos; si son muy grandes, el texto se vuelve ilegible.
- `text-transform` no cambia el HTML: lo que lee un lector de pantalla es el texto original.

---

## 🖍️ Decoraciones de texto

_Sesión 1 · Resultados de aprendizaje: RA-4_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 03 — Decoraciones de texto](03-decoraciones-de-texto.md): subrayado, tachado, línea superior, estilos y colores de línea, y sombras.

### 🌍 Contexto

A veces querés marcar una parte del texto: un dato tachado, un título con relieve, un enlace sin subrayado.

### 💡 Concepto

`text-decoration` dibuja una línea (debajo, encima o a través del texto) y permite elegir su estilo y su color. `text-shadow` agrega una o varias sombras al texto.

### 📖 Explicación

**`text-decoration`** es una abreviatura de `text-decoration-line`, `text-decoration-style`, `text-decoration-color` y `text-decoration-thickness`.

| Parte | Valores |
|---|---|
| Línea | `none`, `underline`, `overline`, `line-through` |
| Estilo | `solid` (inicial), `double`, `dotted`, `dashed`, `wavy` |
| Color | Cualquier color; por defecto, el del texto |

```css
.ondulado {
  text-decoration: underline wavy #dc2626;
}
```

> ⚠️ Los enlaces ya van subrayados y mucha gente depende de esa señal para reconocerlos. Si quitás el subrayado con `none`, dejá otra señal clara (color o fondo).

**`text-shadow`** recibe `desplazamiento-x desplazamiento-y desenfoque color`. Solo los dos desplazamientos son obligatorios; pueden ser negativos. El desenfoque no puede
serlo. Se pueden dar varias sombras separadas por comas.

```css
.sombra {
  text-shadow: 2px 2px 4px #94a3b8;
}
```

---

## 📊 Representación de datos

_Sesión 1 · Resultados de aprendizaje: RA-5_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 04 — Tablas con estilo](04-tablas-con-estilo.md): bordes unidos, relleno, alineación, título y filas alternas.
> - [Ejemplo 05 — Listas con estilo](05-listas-con-estilo.md): tipo de viñeta o numeración, posición y espaciado.

### 🌍 Contexto

Una tabla o una lista sin estilo muestra los datos, pero cuesta leerlos. Con unas pocas propiedades se vuelven claros. La estructura (`table`, `ul`, `li`…) ya la escribiste en la
Clase 02; ahora te ocupás de su **apariencia**.

### 💡 Concepto

Dar estilo a una tabla es controlar los **bordes**, el **espacio** de las celdas, la **alineación** y las **filas alternas**. Dar estilo a una lista es elegir la **viñeta o
la numeración**, su **posición** y el **espacio** entre los elementos.

### 📖 Explicación

**5.1 Tablas.**

| Propiedad | Para qué sirve |
|---|---|
| `border` en `th, td` | Dibuja el borde de cada celda |
| `border-collapse: collapse` | **Une** los bordes de celdas vecinas (por defecto es `separate` y se ve doble) |
| `border-spacing` | Distancia entre celdas separadas |
| `padding` | Espacio entre el texto y el borde de la celda |
| `text-align` | Alinea el contenido; los números, a la derecha |
| `caption-side: bottom` | Pasa el título de la tabla debajo |
| `tbody tr:nth-child(even)` | Pinta las filas pares (filas alternas, ya vista en la Clase 04) |

**5.2 Listas.**

| Propiedad | Valores | Para qué sirve |
|---|---|---|
| `list-style-type` | `disc`, `circle`, `square`, `none`; `decimal`, `upper-roman`, `lower-alpha` | Tipo de viñeta o numeración |
| `list-style-position` | `outside` (inicial), `inside` | Viñeta fuera o dentro de la caja del elemento |
| `margin-bottom` en `li` | Una longitud | Espacio entre elementos |

> 💡 Para una lista sin viñetas (por ejemplo, un menú), usá `list-style-type: none` y `padding-left: 0`: `none` quita la viñeta, pero no la sangría de 40px que trae la lista.

---

## 🖼️ Bordes

_Sesión 2 · Resultados de aprendizaje: RA-6_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 06 — Bordes](06-bordes.md): estilos, abreviatura, propiedades por separado y un borde distinto por lado.

### 🌍 Contexto

Un borde delimita un bloque y le da presencia: una nota, una tarjeta, un recuadro. Además es la primera de las capas del modelo de cajas que vas a medir.

### 💡 Concepto

Un **borde** es una línea alrededor de un elemento, con tres características: **grosor**, **estilo** y **color**.

### 📖 Explicación

**6.1 Propiedades de bordes.**

| Propiedad | Qué fija | Valores |
|---|---|---|
| `border-width` | Grosor | Una longitud (`3px`), `thin`, `medium`, `thick` |
| `border-style` | Estilo | `solid`, `dotted`, `dashed`, `double`, `none` (inicial) |
| `border-color` | Color | Cualquier color |
| `border` | Las tres, en una abreviatura | `3px solid #2563eb` |

> ⚠️ **Sin estilo no hay borde.** El estilo inicial es `none`: `border: 3px #2563eb;` no dibuja nada y su grosor calculado es `0`. Escribí siempre el estilo.

**6.2 Bordes múltiples (diferentes).**

| Propiedad | Qué fija |
|---|---|
| `border-top`, `border-right`, `border-bottom`, `border-left` | Grosor, estilo y color de **un** lado |
| `border-width`, `border-style`, `border-color` con dos a cuatro valores | Un valor por lado, con la notación abreviada (ver «Márgenes y rellenos») |

```css
.tarjeta {
  border-top: 4px solid #1e3a8a;
  border-right: 1px solid #94a3b8;
  border-bottom: 4px double #1e3a8a;
  border-left: 1px solid #94a3b8;
}
```

---

## ⭕ Bordes redondeados

_Sesión 2 · Resultados de aprendizaje: RA-6_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 07 — Bordes redondeados](07-bordes-redondeados.md): las cuatro esquinas, dos y cuatro valores, una esquina específica y un círculo.

![Tres cuadros con border-radius: uno con 16px que redondea las cuatro esquinas; uno con 16px 0, que redondea la esquina de arriba a la izquierda y la de abajo a la derecha; y uno con cuatro valores, numerados 1 a 4 en el sentido de las agujas del reloj desde arriba a la izquierda.](../imagenes/esquinas-redondeadas.svg)

### 🌍 Contexto

Las esquinas rectas se ven duras. Un pequeño radio suaviza la caja y da un aspecto más amable, y con un radio grande se hacen círculos y cápsulas.

### 💡 Concepto

`border-radius` redondea las esquinas de un elemento. El valor es el **radio** de la curva: cuanto mayor, más redonda la esquina.

### 📖 Explicación

**7.1 La propiedad `border-radius`.**

| Valores | Qué esquinas recibe cada uno |
|---|---|
| 1 | Las cuatro |
| 2 | 1.º: arriba a la izquierda y abajo a la derecha · 2.º: arriba a la derecha y abajo a la izquierda |
| 3 | 1.º: arriba a la izquierda · 2.º: arriba a la derecha y abajo a la izquierda · 3.º: abajo a la derecha |
| 4 | Arriba a la izquierda, arriba a la derecha, abajo a la derecha y abajo a la izquierda (**sentido horario**) |

Un valor en **porcentaje** se mide contra la caja: `50%` en una caja cuadrada da un **círculo**.

**7.2 Esquinas específicas.**

| Propiedad | Esquina |
|---|---|
| `border-top-left-radius` | Arriba a la izquierda |
| `border-top-right-radius` | Arriba a la derecha |
| `border-bottom-right-radius` | Abajo a la derecha |
| `border-bottom-left-radius` | Abajo a la izquierda |

```css
.caja--una-esquina {
  border-top-left-radius: 24px;
}
```

---

## 📦 Modelo de cajas

_Sesión 2 · Resultados de aprendizaje: RA-7_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 08 — Modelo de cajas](08-modelo-de-cajas.md): dos cajas con las mismas medidas y tamaños distintos, con `content-box` y `border-box`.
> - [Ejemplo 09 — Desborde del contenido](09-overflow.md): los valores de `overflow` y los ejes por separado.

![Una caja con sus cuatro capas de afuera hacia adentro: margen, borde, relleno y contenido. A la derecha, el cálculo del ancho total de la caja A de 200 píxeles de ancho, 20 de relleno y 5 de borde: 250 con content-box y 200 con border-box.](../imagenes/modelo-de-cajas.svg)

### 🌍 Contexto

Cuando decís «esta caja mide 200 píxeles», ¿mide 200 con relleno y borde o sin ellos? Si no lo sabés, tus páginas se desarman. El modelo de cajas lo responde.

### 💡 Concepto

Para el navegador, **todo elemento es una caja** con cuatro capas, de adentro hacia afuera: **contenido**, **relleno** (`padding`), **borde** (`border`) y **margen** (`margin`).
`box-sizing` decide qué incluye el `width` de la caja.

### 📖 Explicación

**8.1 ¿Qué es el modelo de cajas?**

| `box-sizing` | `width` incluye… | Ancho de borde a borde con `width: 200px`, relleno `20px` y borde `5px` |
|---|---|---|
| `content-box` (por defecto) | Solo el contenido | `200 + 20 + 20 + 5 + 5` = **250px** |
| `border-box` | Contenido, relleno y borde | **200px** (el contenido queda en 150px) |

El **margen nunca se incluye** en `width` ni en `height`; se suma aparte al espacio que la caja ocupa en la página. Por eso muchos sitios usan `border-box`: si pedís 200px,
mide 200px aunque le agregues relleno o borde.

**8.2 La propiedad `overflow`.** Cuando el contenido no entra en la caja, `overflow` decide qué pasa:

| Valor | Qué hace |
|---|---|
| `visible` (inicial) | El contenido **sobresale** de la caja |
| `hidden` | Se **recorta** lo que no entra, sin barras |
| `scroll` | Recorta y **siempre** muestra barras de desplazamiento |
| `auto` | Recorta y muestra barras **solo si hace falta** |

`overflow-x` y `overflow-y` fijan el valor del eje horizontal y del vertical por separado; `overflow: scroll hidden` es la forma abreviada (primero `x`, luego `y`).

> ⚠️ Si un eje es `visible` y el otro no, el `visible` se comporta como `auto`.

---

## 📏 Márgenes y rellenos

_Sesión 2 · Resultados de aprendizaje: RA-8_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 10 — Márgenes y rellenos](10-margenes-y-rellenos.md): la notación de uno a cuatro valores, el centrado con `auto`, el colapso de márgenes y una tarjeta completa.

![Cuatro cuadros que muestran qué lado recibe cada valor en margin o padding: un valor para los cuatro lados; dos valores, vertical y horizontal; tres valores, arriba, horizontal y abajo; cuatro valores, arriba, derecha, abajo e izquierda en el sentido de las agujas del reloj.](../imagenes/notacion-abreviada.svg)

### 🌍 Contexto

Un diseño con aire se ve ordenado; uno sin aire, amontonado. El **margen** separa una caja de las demás y el **relleno** separa su contenido de su borde.

### 💡 Concepto

`margin` es el espacio **fuera** del borde; `padding`, el espacio **dentro**. Las dos propiedades se pueden escribir con uno, dos, tres o cuatro valores.

### 📖 Explicación

**9.1 La propiedad `margin`.** **9.2 La propiedad `padding`.** Los dos usan la misma notación:

| Valores | Qué lado recibe cada uno | Ejemplo |
|---|---|---|
| 1 | Los cuatro | `margin: 10px` |
| 2 | Arriba y abajo · izquierda y derecha | `margin: 10px 20px` |
| 3 | Arriba · izquierda y derecha · abajo | `margin: 5px 10px 15px` |
| 4 | Arriba, derecha, abajo, izquierda (**sentido horario**) | `margin: 5px 10px 15px 20px` |

- Un `margin` puede tener valores **negativos** (acerca el elemento a sus vecinos) o `auto`; con `margin: 0 auto` y un `width` fijo, la caja queda **centrada**. Un `padding`
  **no admite** valores negativos.
- Los porcentajes del relleno y del margen se miden contra el **ancho** de la caja que contiene al elemento.

**Colapso de márgenes.** Los márgenes **verticales** contiguos de elementos hermanos **no se suman**: se combinan en uno solo, del tamaño del mayor. Un margen inferior de `30px`
sobre un margen superior de `20px` deja **30px** entre las cajas. Solo ocurre en vertical.

**9.3 Atajo: modelo de cajas.** Dos atajos hacen más corta la hoja y más fácil el cálculo:

| Atajo | Qué resume |
|---|---|
| `margin` y `padding` con uno a cuatro valores | Cuatro lados en una declaración |
| `box-sizing: border-box` | El ancho de la caja incluye el relleno y el borde |

> 💡 Una tarjeta típica junta todo: `border`, `border-radius`, `padding`, `margin` y `box-sizing: border-box`. Está completa en el
> [Ejemplo 10](10-margenes-y-rellenos.md).

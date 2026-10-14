# 📚 Explicación conceptual — Introducción a CSS

Hasta ahora escribiste páginas con HTML: contenido y estructura, sin estilo. En esta clase le vas a dar **aspecto** al sitio de
**Lucía Fernández** usando CSS, sin cambiar su contenido. Se recomienda haber hecho las Clases 01 y 02. No necesitás saber
programar.

Resultados de aprendizaje de la clase:

- **RA-1**: explicar qué es CSS, qué significa y por qué se usa.
- **RA-2**: enlazar CSS a una página HTML de las distintas formas y elegir la más adecuada.
- **RA-3**: escribir reglas con la sintaxis correcta y organizarlas en un documento CSS.
- **RA-4**: usar el navegador para probar y revisar los estilos.
- **RA-5**: explicar la herencia y cómo la cascada decide qué estilo se aplica.
- **RA-6**: definir y usar variables CSS.
- **RA-7**: dar color con las propiedades de color, las formas de escribir un color y la transparencia.
- **RA-8**: crear gradientes, usar imágenes de fondo y controlar la opacidad.

## 🗒️ Glosario

| Término | Equivalente |
|---|---|
| *stylesheet* | hoja de estilos |
| *selector* | selector (a qué elementos se aplica) |
| *property* / *value* | propiedad / valor |
| *declaration* | declaración |
| *cascade* | cascada |
| *specificity* | especificidad |
| *custom property* | variable CSS |
| *alpha channel* | canal alfa (transparencia) |
| *developer tools* | herramientas para desarrolladores |

> 📌 **Origen de la información.** Las descripciones están contrastadas con **MDN Web Docs**. Los resultados que ves en los
> ejemplos se comprobaron en un navegador leyendo los estilos que realmente se aplican.

---

## 🎨 ¿Qué es CSS?

_Resultados de aprendizaje: RA-1, RA-2_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 01 — Qué es CSS y cómo enlazarlo](01-que-es-css-y-como-enlazarlo.md): las tres formas de enlazar CSS y cuál elegir para el sitio de Lucía.

### 🌍 Contexto

Una página solo con HTML se ve «seca»: fondo blanco, letra negra, enlaces azules. Para cambiar su aspecto sin tocar el contenido
hace falta otro lenguaje.

### 💡 Concepto

**CSS** significa *Cascading Style Sheets*, en español **hojas de estilo en cascada**. Es un lenguaje **basado en reglas**: en cada
regla se dice qué estilos se aplican a qué elementos de la página.

### 📖 Explicación

**¿Por qué se usa?** Porque separa el **contenido** (HTML) de la **presentación** (CSS). Esa separación permite:

| Ventaja | Qué significa |
|---|---|
| Cambiar el aspecto en un solo lugar | Un archivo CSS puede dar estilo a todas las páginas del sitio |
| Mantener el HTML limpio | El HTML dice **qué es** cada cosa; el CSS, **cómo se ve** |
| Reutilizar | Una misma regla se aplica a muchos elementos |

**Formas de enlazar CSS.** Hay tres:

| Forma | Cómo se escribe | Cuándo |
|---|---|---|
| **Archivo externo** | `<link rel="stylesheet" href="css/estilos.css">` dentro de `<head>` | Es la mejor opción para un sitio: una sola hoja para todas las páginas |
| **Bloque interno** | `<style> … </style>` dentro de `<head>` | Una sola página con estilos propios |
| **Estilo en línea** | `<p style="color: red;">` | Un solo elemento; **conviene evitarlo**: MDN lo considera una mala práctica |

> 💡 Para un sitio de varias páginas como el de Lucía, elegí el **archivo externo**: cada página lo enlaza y cualquier cambio
> llega a todas.

---

## ✍️ Sintaxis y documento CSS

_Resultados de aprendizaje: RA-3_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 02 — Sintaxis y documento CSS](02-sintaxis-y-documento-css.md): la regla, los selectores y la hoja de estilos de Lucía.

![Una regla CSS tiene un selector, un bloque entre llaves con una o más declaraciones, y cada declaración está formada por una propiedad, dos puntos, un valor y un punto y coma.](../imagenes/anatomia-de-una-regla.svg)

### 🌍 Contexto

Para que el navegador entienda tus estilos tenés que escribirlos con una forma precisa. Un punto y coma olvidado cambia el
resultado.

### 💡 Concepto

Una **regla CSS** tiene un **selector** (a qué elementos se aplica) y, entre llaves, una o más **declaraciones**. Cada declaración
es un par **propiedad: valor;**. Las reglas se guardan en un **documento CSS**: un archivo de texto con extensión `.css`.

### 📖 Explicación

```css
h1 {
  color: red;
  opacity: 0.9;
}
```

**Los selectores esenciales.**

| Selector | Se escribe | A qué se aplica |
|---|---|---|
| Elemento | `h1` | A todos los elementos de esa etiqueta |
| Clase | `.destacado` | A los elementos con `class="destacado"` (se puede usar muchas veces) |
| Identificador | `#portada` | Al elemento con `id="portada"` (un solo elemento por página) |
| Grupo | `h1, h2` | A todos los selectores de la lista, separados por comas |
| Universal | `*` | A todos los elementos |

> ⚠️ En un grupo con comas, si **un solo selector** está mal escrito, **toda la regla se ignora**.

**El documento CSS.** Es un archivo (por ejemplo, `css/estilos.css`) con reglas una debajo de otra. Los **comentarios** se escriben
entre `/*` y `*/` y el navegador los ignora:

```css
/* Títulos del sitio */
h2 {
  color: #1e3a8a;
}
```

> 💡 Si una declaración está mal escrita (por ejemplo, sin dos puntos o con una propiedad inexistente), el navegador la **ignora**
> y sigue con la siguiente. Si no ves un estilo, empezá por revisar la escritura.

---

## 🔍 Uso de navegadores

_Resultados de aprendizaje: RA-4_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 03 — Las herramientas del navegador](03-herramientas-del-navegador.md): inspeccionar un elemento y cambiar estilos en vivo.

### 🌍 Contexto

Cuando un estilo «no funciona», adivinar lleva tiempo. El navegador te muestra exactamente qué reglas se aplican a cada elemento.

### 💡 Concepto

Todos los navegadores modernos incluyen **herramientas para desarrolladores**. La más útil para CSS es el **Inspector** (en algunos
navegadores se llama *Elements*): muestra el HTML de la página y las reglas CSS que se aplican a cada elemento.

### 📖 Explicación

**Cómo abrirlas.** Con **F12** o **Ctrl + Shift + I** (en Mac, **⌘ + ⌥ + I**), o con clic derecho sobre un elemento y
**Inspeccionar**.

**Qué podés hacer.**

| Acción | Para qué sirve |
|---|---|
| Inspeccionar un elemento | Ver qué reglas se le aplican, de la más específica a la menos específica |
| Desmarcar una declaración | Ver qué pasaría si no estuviera |
| Cambiar un valor | Probar un color o un tamaño con vista previa inmediata |
| Agregar una declaración | Probar una propiedad nueva |

> ⚠️ **Lo que cambies en las herramientas no modifica tu archivo CSS.** Es una prueba: cuando algo te guste, **copialo a tu
> archivo** y guardalo.

**Compatibilidad.** Los navegadores no incorporan las funciones nuevas al mismo tiempo. Si una declaración no se entiende, el
navegador la ignora. Por eso se puede escribir primero un **valor de respaldo** y después el valor moderno:

```css
.caja {
  background-color: #2563eb;
  background-color: rgb(37 99 235 / 0.9);
}
```

Un navegador que no entienda la segunda línea se queda con la primera.

---

## 🌳 Herencia

_Resultados de aprendizaje: RA-5_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 04 — Herencia](04-herencia.md): qué propiedades llegan a los elementos internos y cuáles no.

![El elemento main define color verde y un borde; sus hijos p y em heredan el color verde pero no el borde; el enlace a no hereda el color porque el navegador le da el suyo, salvo que se use inherit.](../imagenes/herencia-del-arbol.svg)

### 🌍 Contexto

No hace falta escribir una regla para cada párrafo, cada énfasis y cada lista: lo que definís en un contenedor llega, en parte, a
lo que tiene adentro.

### 💡 Concepto

La **herencia** es el mecanismo por el cual un elemento recibe el valor de algunas propiedades de su elemento padre. No todas
las propiedades se heredan.

### 📖 Explicación

| Se hereda | No se hereda |
|---|---|
| `color`, `font-family`, `font-size`, `line-height`, `text-align`, `visibility` | `border`, `background`, `margin`, `padding`, `width`, `height`, `opacity` |

**Un ejemplo.** Si `main { color: green; border-style: solid; }`, los párrafos y los énfasis de `main` **heredan el color verde**,
pero **no el borde**: el borde es solo de `main`.

**Controlar la herencia.**

| Valor | Qué hace |
|---|---|
| `inherit` | Fuerza a tomar el valor del padre |
| `initial` | Vuelve al valor inicial de la propiedad |
| `unset` | Se comporta como `inherit` si la propiedad se hereda y como `initial` si no |

> 💡 Los **enlaces** son un caso típico: el navegador les da su propio color, así que no heredan el del contenedor, salvo que
> uses `color: inherit`.

---

## 🌊 Modelo en cascada

_Resultados de aprendizaje: RA-5_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 05 — La cascada](05-cascada.md): qué regla gana cuando dos reglas se aplican al mismo elemento.

![La cascada decide qué declaración se aplica comparando primero el origen y la importancia, luego la especificidad (identificador vale 100, clase 10, elemento 1) y por último el orden de aparición, donde gana la última.](../imagenes/orden-de-la-cascada.svg)

### 🌍 Contexto

Un mismo elemento puede recibir **varias reglas** que dicen cosas distintas sobre la misma propiedad: una para el elemento, otra
para su clase, otra del navegador. Hace falta una forma de decidir cuál gana.

### 💡 Concepto

La **cascada** es el conjunto de criterios con los que el navegador decide qué declaración se aplica. Mira, en este orden: el
**origen y la importancia**, la **especificidad** y el **orden de aparición**.

### 📖 Explicación

**1. Origen.** Los estilos pueden venir de tres lugares:

| Origen | Qué es |
|---|---|
| Navegador | Los estilos por defecto (por eso los enlaces son azules y subrayados) |
| Usuario | Preferencias de quien lee la página |
| Autor | Tu hoja de estilos |

Los estilos del **autor** ganan a los del navegador.

**2. Importancia.** Una declaración puede llevar `!important`: así anula todo lo anterior, incluso los estilos en línea. Con
`!important` el orden de los orígenes se **invierte**. MDN recomienda **no usarlo** salvo que sea imprescindible.

```css
p {
  color: red !important;
}
```

**3. Especificidad.** Si dos reglas del mismo origen se aplican al mismo elemento, gana la de **selector más específico**:

| Selector | Valor |
|---|---|
| Elemento (`p`) | 1 |
| Clase (`.destacado`) | 10 |
| Identificador (`#aviso`) | 100 |

Un identificador vale más que cualquier cantidad de clases.

**4. Orden de aparición.** Si dos reglas tienen **la misma especificidad**, gana la que viene **última** en la hoja.

> 💡 Si un estilo no se aplica, el Inspector te muestra qué regla lo está pisando y por qué.

---

## 🧩 Variables CSS

_Resultados de aprendizaje: RA-6_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 06 — Variables CSS](06-variables-css.md): los colores de Lucía definidos una sola vez.

### 🌍 Contexto

En la hoja de Lucía el azul principal aparece en seis reglas. Si decide cambiarlo, tiene que encontrar y cambiar cada una.

### 💡 Concepto

Una **variable CSS** (o *propiedad personalizada*) es un valor con nombre que se define una vez y se reutiliza. Su nombre empieza
con dos guiones, como `--color-principal`, y se usa con `var()`.

### 📖 Explicación

```css
:root {
  --color-principal: #2563eb;
}

a {
  color: var(--color-principal);
}
```

- **Dónde se definen.** Habitualmente en `:root`, que representa a toda la página: así se pueden usar en cualquier regla.
- **Cómo se usan.** Con `var(--nombre)`.
- **Valor de respaldo.** `var(--color-extra, red)` usa `red` si `--color-extra` no existe.
- **Mayúsculas.** Los nombres distinguen mayúsculas: `--color` y `--Color` son variables distintas.
- **Ventaja.** Cambiás el valor en un solo lugar y cambia en todas las reglas que lo usan.

---

## 🌈 Manejo de colores

_Resultados de aprendizaje: RA-7_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 07 — Colores y transparencia](07-colores-y-transparencia.md): el azul principal de Lucía escrito de distintas formas y con transparencia.

![El mismo azul principal se escribe en hexadecimal 2563eb, en rgb con 37, 99 y 235 y en hsl con 221 grados, 83 por ciento y 53 por ciento; con un canal alfa de 0,5 se escribe rgb con barra 0,5 o hexadecimal con 80 al final.](../imagenes/formas-de-escribir-un-color.svg)

### 🌍 Contexto

El color es lo primero que se nota de una página. CSS ofrece varias propiedades para aplicarlo y varias formas de escribir un
mismo color.

### 💡 Concepto

Las **propiedades de color** más usadas son `color` (el texto), `background-color` (el fondo) y `border-color` (el borde). Un color
se puede escribir por **nombre**, en **hexadecimal**, en **RGB** o en **HSL**, y puede llevar **transparencia** con el **canal alfa**.

### 📖 Explicación

**Propiedades de color.**

| Propiedad | Colorea |
|---|---|
| `color` | El texto |
| `background-color` | El fondo |
| `border-color` | El borde (hace falta que el borde exista: `border-style` y `border-width`) |

**Formas de escribir un color.**

| Forma | Ejemplo |
|---|---|
| Nombre | `royalblue` |
| Hexadecimal | `#2563eb` (rojo, verde y azul en base 16) |
| RGB | `rgb(37, 99, 235)` (cantidad de rojo, verde y azul, de 0 a 255) |
| HSL | `hsl(221, 83%, 53%)` (tono en grados, saturación y luminosidad) |

> 💡 El hexadecimal y el RGB del ejemplo son **exactamente** el mismo color. El HSL escrito con números redondeados da un color
> **casi** igual: el navegador lo calcula como `rgb(36, 99, 235)`, un punto menos en un canal, que no se nota.

**Canal alfa (transparencia).** Un cuarto valor, entre 0 (invisible) y 1 (sólido), indica cuánto se ve el fondo a través del
color. Se escribe después de una barra: `rgb(37 99 235 / 0.5)`, `hsl(221 83% 53% / 50%)`. En hexadecimal se agregan dos dígitos al
final: `#2563eb80`.

> ⚠️ **Contraste.** Si el texto y el fondo se parecen mucho, o si la transparencia deja pasar demasiado fondo, el texto se vuelve
> difícil de leer. Comprobalo siempre.

---

## 🌅 Gradientes, imágenes y opacidad

_Resultados de aprendizaje: RA-8_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 08 — Gradientes, imágenes y opacidad](08-gradientes-imagenes-y-opacidad.md): la cabecera con gradiente, un fondo con imagen y la opacidad.

### 🌍 Contexto

Además de un color liso, un fondo puede ser una transición de colores (gradiente) o una imagen. Y se puede hacer más o menos
transparente a un elemento.

### 💡 Concepto

Un **gradiente** es una transición progresiva entre dos o más colores. Es una **imagen**, por eso se escribe en `background-image`
(no en `background-color`). Una **imagen de fondo** se configura con `background-image`, `background-repeat`, `background-size` y
`background-position`. La **opacidad** (`opacity`) hace transparente a un elemento entero.

### 📖 Explicación

**Gradiente lineal.** Avanza en línea recta, con una dirección o un ángulo:

```css
background-image: linear-gradient(90deg, #1e3a8a, #2563eb);
```

`to right` equivale a `90deg`; por defecto va `to bottom`. Se pueden poner **más de dos colores**, con paradas en porcentajes
(`#1e3a8a 0%, #2563eb 60%, #f59e0b 100%`).

**Gradiente radial.** Los colores salen desde un centro, con forma de círculo o de elipse:

```css
background-image: radial-gradient(circle, #f59e0b, #1e3a8a);
```

**Imágenes de fondo.**

| Propiedad | Valores habituales | Qué hace |
|---|---|---|
| `background-image` | `url("../imagenes/patron.png")` | Elige la imagen |
| `background-repeat` | `repeat` (por defecto), `no-repeat`, `repeat-x`, `repeat-y` | Cuánto se repite |
| `background-size` | `auto` (por defecto), `cover`, `contain` | Tamaño: `cover` rellena y recorta; `contain` entra completa |
| `background-position` | `center`, `top left` | Dónde se ubica |

> 💡 La ruta de `url()` se cuenta **desde el archivo CSS**, no desde la página HTML. Por eso, si el CSS está en `css/` y la imagen
> en `imagenes/`, la ruta es `../imagenes/…`. Conviene indicar también un `background-color` por si la imagen no carga.

**Opacidad.** `opacity` va de 0 (invisible) a 1 (sólido) y afecta al **elemento completo, texto incluido**. No se hereda, pero los
hijos se dibujan dentro del elemento ya atenuado.

**Opacidad frente a color con alfa.**

| | `opacity: 0.5` | `background-color: rgb(30 58 138 / 0.5)` |
|---|---|---|
| Qué atenúa | Todo el elemento, con su texto | Solo el fondo |
| El texto | Queda más tenue | Queda del mismo color |

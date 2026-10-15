# 📚 Explicación conceptual — Unidades relativas

En las clases anteriores escribiste `16px`, `1.5rem`, `50%` o `2em` casi sin detenerte en qué significa cada sufijo. Ahora vas a entender **qué es una unidad**, qué unidades hay y **respecto de qué se
calcula cada una**, para elegir con criterio. Seguimos con el sitio de **Lucía Fernández**, con una página de práctica por tema. Se recomienda haber hecho las Clases 01 a 05.

Resultados de aprendizaje de la clase:

- **RA-1**: explicar qué es una unidad de medida en CSS y distinguir las absolutas de las relativas.
- **RA-2**: usar `px` y explicar la densidad de píxeles.
- **RA-3**: reconocer las otras unidades absolutas.
- **RA-4**: usar el porcentaje y explicar respecto de qué se calcula.
- **RA-5**: usar `em` y `rem` y explicar su diferencia.
- **RA-6**: usar `ex`, `ch` y `lh`.
- **RA-7**: reconocer las otras unidades relativas y elegir la unidad adecuada.

## 🗒️ Glosario

| Término | Equivalente |
|---|---|
| *unit* | unidad (el sufijo que da sentido a un número) |
| *absolute unit* / *relative unit* | unidad absoluta / relativa |
| *reference value* | valor de referencia (aquello contra lo que se calcula una unidad relativa) |
| *pixel density* | densidad de píxeles |
| *viewport* | ventana de visualización |
| *root element* | elemento raíz (`html`) |
| *line height* | altura de línea |

> 📌 **Origen de la información.** Los valores calculados de todos los ejemplos se comprobaron en un navegador, con una ventana de `1000 × 600` y la densidad de pantalla indicada. Las descripciones de
> las unidades siguen la terminología de MDN Web Docs; la compatibilidad de las unidades recientes (`lh`, `rlh` y las de ventana) debe comprobarse en MDN antes de usarlas en un sitio real.

---

## 📏 Unidades

### 🧭 1.1 Tipos de unidades

_Resultados de aprendizaje: RA-1_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 01 — Tipos de unidades](01-tipos-de-unidades.md): cajas con cinco unidades distintas, un número sin unidad y el cero.

![Árbol de las unidades de CSS: las absolutas (px, cm, mm, Q, in, pt, pc), con un tamaño fijo, y las relativas, que se calculan a partir de otro valor: el porcentaje, que depende del contenedor; em, ex, ch y lh, que dependen de la letra; rem y rlh, que dependen de la raíz; y vw, vh, vmin y vmax, que dependen de la ventana.](../imagenes/tipos-de-unidades.svg)

#### 🌍 Contexto

Todo valor de longitud en CSS (un ancho, un tamaño de letra, un margen) lleva una **unidad**. Elegir bien la unidad decide si la página se adapta al contenedor, a la letra o a la ventana, o si queda fija.

#### 💡 Concepto

Una **unidad** es el sufijo que dice en qué se mide un número: `px`, `cm`, `%`, `em`… Se dividen en dos tipos: las **absolutas**, con un tamaño fijo, y las **relativas**, que se calculan a partir de otro
valor, el **valor de referencia**.

#### 📖 Explicación

| Tipo | Qué significa | Ejemplos |
|---|---|---|
| Absoluta | Tiene un tamaño fijo; no depende de ningún otro elemento | `px`, `cm`, `mm`, `Q`, `in`, `pt`, `pc` |
| Relativa | Se calcula a partir de otro valor | `%`, `em`, `rem`, `ex`, `ch`, `lh`, `rlh`, `vw`, `vh`, `vmin`, `vmax` |

- Un número distinto de cero **necesita** unidad: `width: 200;` no es válido y el navegador lo ignora. El `0` es la única excepción (`margin: 0`).
- Entre el número y la unidad **no va un espacio**: `200px`, no `200 px`.
- Dos medidas que hoy calculan lo mismo (`200px` y `50%` de un contenedor de `400px`) se comportan distinto cuando algo cambia.

---

## 📐 Unidades absolutas

### 🔲 2.1 La unidad `px` (píxel)

_Resultados de aprendizaje: RA-2_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 02 — La unidad px](02-la-unidad-px.md): una caja de 200 píxeles, medida en una pantalla común y en una de doble densidad.

#### 🌍 Contexto

`px` es la unidad que más viste hasta ahora y la que parece más sencilla: «un punto de la pantalla». No es exactamente así.

#### 💡 Concepto

El **píxel de CSS** (`px`) es la unidad absoluta de uso habitual en pantalla. Es un tamaño **de referencia** que el navegador convierte a puntos físicos de la pantalla.

#### 📖 Explicación

- `200px` mide siempre doscientos píxeles **de CSS**, sin importar el contenedor ni el tamaño de la letra.
- Sirve para lo que debe ser **fijo y pequeño**: bordes finos, sombras, detalles.
- No respeta la preferencia de tamaño de letra de quien visita la página; para el texto se prefiere `rem`.

### 🔬 2.2 Densidad de píxeles

_Resultados de aprendizaje: RA-2_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 02 — La unidad px](02-la-unidad-px.md): `devicePixelRatio` en 1 y en 2, con la misma caja de 200 píxeles.

![Una caja de 200 píxeles de CSS en dos pantallas: en una pantalla común cada píxel de CSS es un punto físico y la caja usa 200 puntos; en una pantalla de alta densidad con una relación de 2, cada píxel de CSS son 2 por 2 puntos físicos y la caja usa 400 puntos, pero ocupa el mismo tamaño aparente.](../imagenes/densidad-de-pixeles.svg)

#### 🌍 Contexto

Los celulares y muchos portátiles tienen pantallas con muchísimos más puntos que una pantalla antigua del mismo tamaño. Si `px` fuera un punto físico, las páginas se verían minúsculas en ellas.

#### 💡 Concepto

La **densidad de píxeles** es cuántos puntos físicos de la pantalla ocupa un píxel de CSS. El navegador la informa como una relación, `window.devicePixelRatio`: `1` en una pantalla clásica de 96 DPI y `2` en una pantalla de alta densidad (HiDPI o Retina).

#### 📖 Explicación

| Pantalla | Relación | Un píxel de CSS ocupa… | Una caja de `200px` usa… |
|---|---|---|---|
| Común | `1` | 1 punto físico | 200 puntos de ancho |
| Alta densidad | `2` | 2 × 2 = 4 puntos físicos | 400 puntos de ancho |

- La caja se ve **del mismo tamaño aparente** en las dos pantallas; en la de alta densidad se ve más nítida.
- Las medidas que lee el navegador (`offsetWidth`, los valores calculados) siguen en píxeles **de CSS**.
- Por eso `px` es «absoluta» pero no «un punto físico»: es fija en CSS, no en la pantalla.

### 📎 2.3 Otras unidades absolutas

_Resultados de aprendizaje: RA-3_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 03 — Otras unidades absolutas](03-otras-unidades-absolutas.md): siete formas de escribir `96px`.

#### 🌍 Contexto

Vas a encontrar `cm`, `pt` o `in` en hojas heredadas o pensadas para imprimir. Conviene reconocerlas y saber cuánto valen.

#### 💡 Concepto

CSS tiene unidades heredadas de la impresión: centímetro (`cm`), milímetro (`mm`), cuarto de milímetro (`Q`), pulgada (`in`), punto (`pt`) y pica (`pc`). El navegador las convierte a píxeles de CSS con
relaciones fijas.

#### 📖 Explicación

| Unidad | Equivale a… |
|---|---|
| `1in` | `96px` = `2.54cm` = `25.4mm` = `101.6Q` = `72pt` = `6pc` |
| `1cm` | ≈ `37.8px` |
| `1mm` | ≈ `3.78px` |
| `1pt` | ≈ `1.33px` (1/72 de pulgada) |
| `1pc` | `16px` (12 puntos) |

> ⚠️ En una impresora, `1cm` coincide con un centímetro real; en una pantalla, el navegador usa la equivalencia fija `1in = 96px` y el tamaño físico depende de la pantalla. Para pantalla usá `px` y las unidades
> relativas; estas unidades sirven sobre todo para hojas de estilo para imprimir.

---

## 🔀 Unidades relativas

![Tabla visual con la referencia de cada unidad relativa: el porcentaje depende del ancho del contenedor en width y padding, de la letra del padre en font-size y de la altura definida del contenedor en height; em, de la letra del propio elemento; rem, de la letra de la raíz; ex y ch, de la x y del cero de la tipografía; lh y rlh, de la altura de línea; y vw, vh, vmin y vmax, de la ventana.](../imagenes/referencias-de-unidades.svg)

### 💯 3.1 La unidad de porcentaje `%`

_Resultados de aprendizaje: RA-4_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 04 — Porcentajes](04-porcentajes.md): ancho, tamaño de letra, alto y relleno en `%`.

#### 🌍 Contexto

El porcentaje parece simple («la mitad de»), pero **«de qué»** cambia según la propiedad. Es el origen de muchos errores.

#### 💡 Concepto

El **porcentaje** (`%`) es una unidad relativa: expresa «tanto por ciento de otro valor». El valor de referencia depende de la propiedad.

#### 📖 Explicación

| Propiedad | El porcentaje se calcula sobre… | Ejemplo (marco de `400px`, letra de `16px`) |
|---|---|---|
| `width` | El ancho del contenedor | `50%` = `200px` |
| `font-size` | El tamaño de letra del padre | `150%` = `24px` |
| `height` | El alto del contenedor, **si está definido** | `50%` de `200px` = `100px` |
| `padding` y `margin` | El **ancho** del contenedor (también arriba y abajo) | `10%` = `40px` |

> ⚠️ Un `height` en `%` dentro de un contenedor **sin alto definido** no se puede calcular: el elemento queda con su alto automático y no avisa de ningún error.

### 🔤 3.2 Unidad `em`

_Resultados de aprendizaje: RA-5_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 05 — La unidad em](05-la-unidad-em.md): el efecto acumulativo en tres niveles y `em` en ancho y relleno.

![Tres niveles anidados, cada uno con font-size de 1.25em: el primero mide 20 píxeles porque su padre mide 16; el segundo, 25 porque su padre mide 20; y el tercero, 31.25 porque su padre mide 25. A la derecha, los mismos niveles con 1.25rem miden 20 píxeles los tres.](../imagenes/em-acumulativo.svg)

#### 🌍 Contexto

Querés que un botón crezca cuando agrandás su texto, o que un título sea «un poco más grande» que el texto que lo rodea.

#### 💡 Concepto

`em` es una unidad relativa a la **letra**: `1em` es el tamaño de letra del elemento. En `font-size`, como la letra del propio elemento todavía no está calculada, `em` se mide contra la del **padre**.

#### 📖 Explicación

- `font-size: 1.25em` dentro de un padre de `16px` → `20px`.
- **Se acumula** al anidar: `1.25em` dentro de `1.25em` dentro de `1.25em` → `20px`, `25px`, `31.25px`.
- En `width`, `padding` y `margin`, `em` se mide contra la letra del **propio elemento**: con `font-size: 20px`, `10em` = `200px` y `1em` = `20px`.
- Usalo en componentes pequeños (botones, etiquetas) para que las medidas acompañen a la letra.

### 🌱 3.3 Unidad `rem` (root em)

_Resultados de aprendizaje: RA-5_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 06 — La unidad rem](06-la-unidad-rem.md): `rem` frente a `em` y el efecto de cambiar el tamaño de la raíz.

#### 🌍 Contexto

Con `em`, el tamaño de un elemento depende de cuántos niveles tenga encima. Con `rem`, no.

#### 💡 Concepto

`rem` (*root em*) es una unidad relativa al tamaño de letra del **elemento raíz** (`html`). Siempre se mide contra el mismo valor, esté donde esté el elemento.

#### 📖 Explicación

| Unidad | Referencia | Tres niveles de `1.25` (raíz de `16px`) | Raíz de `20px` |
|---|---|---|---|
| `em` | El padre | `20px`, `25px`, `31.25px` | `25px`, `31.25px`, `39.0625px` |
| `rem` | La raíz | `20px`, `20px`, `20px` | `25px`, `25px`, `25px` |

- `rem` **no se acumula**: es predecible.
- Si la raíz no fija un tamaño en `px`, `rem` respeta el tamaño de letra que cada persona eligió en su navegador. Por eso se recomienda `rem` para el texto y los espacios generales.
- En esta clase fijamos `html { font-size: 16px; }` solo para que los cálculos den lo mismo en cualquier equipo.

### 🔡 3.4 Unidad `ex`

_Resultados de aprendizaje: RA-6_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 07 — ex, ch y lh](07-ex-ch-y-lh.md): `10ex` frente a `10em`.

#### 🌍 Contexto

A veces querés una medida ligada al **tamaño de las letras minúsculas**, no al de la «eme».

#### 💡 Concepto

`ex` es una unidad relativa a la altura de la letra «x» minúscula de la tipografía del elemento.

#### 📖 Explicación

- Es **menor que `1em`**: la «x» es más baja que la altura total de la letra; en las pruebas, `1ex` midió cerca de la mitad de `1em`.
- **Depende de la tipografía**: con otra tipografía, `ex` cambia. Por eso se usa poco y no se fija en píxeles.

### 🔢 3.5 Unidad `ch`

_Resultados de aprendizaje: RA-6_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 07 — ex, ch y lh](07-ex-ch-y-lh.md): un campo de 20 caracteres de ancho.
> - [Ejemplo 09 — Elegir la unidad](09-elegir-la-unidad.md): un párrafo con `max-width: 65ch`.

#### 🌍 Contexto

Querés dar a un campo o a un párrafo un ancho en **caracteres**: «unos 65 por línea» para que se lea bien.

#### 💡 Concepto

`ch` es una unidad relativa al ancho del carácter «0» (cero) de la tipografía del elemento.

#### 📖 Explicación

- `20ch` son veinte veces el ancho del «0».
- Con `monospace`, todos los caracteres miden lo mismo y `20ch` son exactamente veinte caracteres; con otras tipografías es una **aproximación**.
- Es la unidad natural para el **ancho de lectura** (`max-width: 65ch`).

### 📐 3.6 Unidad `lh`

_Resultados de aprendizaje: RA-6_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 07 — ex, ch y lh](07-ex-ch-y-lh.md): un bloque de tres líneas de alto.
> - [Ejemplo 09 — Elegir la unidad](09-elegir-la-unidad.md): un bloque de cuatro líneas.

#### 🌍 Contexto

Querés que un bloque muestre exactamente tres líneas de texto, aunque cambie el tamaño de la letra.

#### 💡 Concepto

`lh` es una unidad relativa a la **altura de línea** (`line-height`) del elemento.

#### 📖 Explicación

- Con `line-height: 1.6` y letra de `16px`, una línea mide `25.6px`: `3lh` son unos `76.8px`.
- La altura **acompaña** a la altura de línea: si cambia, el bloque sigue mostrando tres líneas.

> ⚠️ `lh` es una unidad reciente: antes de usarla en un sitio real, comprobá su compatibilidad en MDN. Un navegador que no la reconozca ignora la declaración.

### 🧩 3.7 Otras unidades

_Resultados de aprendizaje: RA-7_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 08 — Unidades de ventana](08-unidades-de-ventana.md): `vw`, `vh`, `vmin`, `vmax` y `rlh` con la ventana fijada.
> - [Ejemplo 09 — Elegir la unidad](09-elegir-la-unidad.md): la tabla de criterios aplicada a una hoja y la mención de `calc()`.

#### 🌍 Contexto

Querés una sección que ocupe la mitad de la altura de la pantalla, o una medida que siga a la ventana, no al contenedor.

#### 💡 Concepto

Las **unidades de ventana** se miden contra la ventana de visualización (el área visible del navegador). `rlh` se mide contra la altura de línea del elemento raíz.

#### 📖 Explicación

| Unidad | Qué es | Ventana `1000 × 600` |
|---|---|---|
| `vw` | 1% del ancho de la ventana | `10vw` = `100px` |
| `vh` | 1% del alto de la ventana | `50vh` = `300px` |
| `vmin` | 1% del lado **menor** | `10vmin` = `60px` |
| `vmax` | 1% del lado **mayor** | `10vmax` = `100px` |
| `rlh` | La altura de línea de la raíz | `2rlh` = `48px` (con raíz de `line-height: 1.5` y `16px`) |

- En esta clase se usan **solo como medida**; los diseños que cambian según el ancho de la ventana son otro tema.
- Compatibilidad: comprobala en MDN antes de usar `rlh` o las variantes más nuevas de las unidades de ventana.

**Cómo elegir la unidad.**

| Situación | Unidad |
|---|---|
| Tamaño del texto | `rem` |
| Medidas que acompañan a la letra de un componente | `em` |
| Bordes finos | `px` |
| Ancho que acompaña al contenedor | `%` |
| Ancho de lectura | `ch` |
| Alto de un bloque de texto | `lh` |
| Una sección según la ventana | `vh`, `vw` |

> 💡 Para mezclar unidades (por ejemplo, «`100%` menos `20px`») CSS tiene la función `calc()`. No se practica en esta clase; solo se menciona para que sepas que existe.

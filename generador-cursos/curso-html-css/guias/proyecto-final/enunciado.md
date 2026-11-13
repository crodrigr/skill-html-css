# 🏁 Proyecto final — Sitio web adaptable para una cafetería

> 🎓 **Evaluación de las Unidades 01 a 07.** Vas a construir un sitio web de cuatro páginas que se vea bien en un **teléfono**, una **tableta** y un **computador**. Se evalúa tu capacidad de **maquetar** (estructura y estilo) y de **hacer diseño adaptable** (*responsive*).

## 🧭 Resumen

| | |
|---|---|
| **Proyecto** | Sitio de **Café Altiplano**: inicio, carta, sedes y reservas |
| **Unidades que evalúa** | 01 Fundamentos HTML · 02 HTML para presentación · 03 Introducción a CSS · 04 Selectores y reglas · 05 Tipografía y datos · 06 Unidades relativas · 07 Grid y diseño adaptable |
| **Tiempo en clase** | **4 sesiones de 3 horas** (12 h) |
| **Trabajo fuera de clase** | **Permitido.** Podés avanzar en tu casa; en la última sesión se hace la revisión y la entrega |
| **Modalidad** | Individual |
| **Herramientas** | Editor de código (VS Code), navegador con sus herramientas para desarrolladores. **Solo HTML y CSS** |
| **Material de partida** | [`codigo/material-inicial/`](codigo/material-inicial/): [contenido.md](codigo/material-inicial/contenido.md) (textos y datos) e `imagenes/` |

## 🏪 El problema

**Café Altiplano** es una cafetería de especialidad con tres sedes. Hoy no tiene sitio web. Pide uno que:

- muestre **qué ofrece** (inicio y carta con precios),
- diga **dónde y cuándo** encontrarla (sedes),
- permita **reservar una mesa** (formulario),
- y se lea **cómodamente desde el teléfono**, que es donde la mayoría de sus clientes mira el sitio.

El contenido (textos, precios, direcciones) ya está en [contenido.md](codigo/material-inicial/contenido.md). **Tu trabajo es la estructura, el estilo y la adaptación.** Todos los datos son inventados.

## 📋 Requerimientos

Cada requerimiento indica la **unidad** que evalúa. En la [rúbrica](rubrica.md) ves cuántos puntos vale cada uno.

### 🧱 Unidad 01 — Estructura de las páginas

| Código | Requerimiento |
|---|---|
| **RF-01.1** | Cuatro páginas: `index.html`, `carta.html`, `sedes.html` y `reservas.html`, cada una con `<!DOCTYPE html>`, `lang="es"`, `charset` y un `<title>` propio. |
| **RF-01.2** | Estructura semántica: `header`, `nav`, `main`, `section`, `aside` y `footer` donde corresponda. Un solo `h1` por página y títulos en orden. |
| **RF-01.3** | Menú de navegación **igual en las cuatro páginas**, con enlaces relativos que funcionan. |
| **RF-01.4** | En la carta, un **índice con anclas internas** (`href="#bebidas"`, etc.) que lleva a cada sección. |
| **RF-01.5** | Imágenes con `alt` útil; en las sedes, `figure` con `figcaption`. Al menos un enlace externo con `target="_blank"` y `rel="noopener noreferrer"`. |
| **RF-01.6** | Comentarios HTML que separan las partes principales de cada página. |

### 📝 Unidad 02 — HTML para presentar datos

| Código | Requerimiento |
|---|---|
| **RF-02.1** | **Tablas** de precios en la carta: `caption`, `thead`, `tbody`, `th` con `scope`. |
| **RF-02.2** | Al menos una lista **sin orden** (`ul`), una **ordenada** (`ol`) y una **de definición** (`dl`). |
| **RF-02.3** | Una cita con `blockquote` y `cite`. |
| **RF-02.4** | **Formulario de reserva** con `fieldset` y `legend`, cada campo con su `label for`, al menos un `select`, un grupo de `radio`, un `checkbox`, un `textarea`, campos `required` y `placeholder`. |

### 🎨 Unidad 03 — Introducción a CSS

| Código | Requerimiento |
|---|---|
| **RF-03.1** | Todo el estilo en **hojas externas** enlazadas con `<link>`, ordenadas por tema (por ejemplo `base.css`, `tipografia.css`, `cajas.css`, `componentes.css`, `layout.css`). |
| **RF-03.2** | **Paleta definida una sola vez** en `:root` con variables. Ningún color suelto fuera de `:root`. |
| **RF-03.3** | Un **gradiente** (por ejemplo en la cabecera), una **imagen de fondo** y un color con **transparencia** (`rgba`) o `opacity`. |
| **RF-03.4** | Aprovechar la **herencia**: el color de letra se declara en pocos elementos y se hereda; no se repite en cada regla. |

### 🎯 Unidad 04 — Selectores y reglas

| Código | Requerimiento |
|---|---|
| **RF-04.1** | Clases con nombres **BEM** (`bloque__elemento--modificador`). |
| **RF-04.2** | Al menos **un** selector de atributo, **un** combinador (`>`, `+` o espacio) y **un** selector lógico (`:is()`, `:not()` o `:has()`). |
| **RF-04.3** | Estados con `:hover` y `:focus` en menú, botones y campos. El estilo de `:focus` debe verse. |
| **RF-04.4** | **Filas alternas** en las tablas con `:nth-child()`. La **página actual** se distingue en el menú. |
| **RF-04.5** | Reglas **ordenadas y comentadas**, sin `!important` y sin `id` para dar estilo. |

### 🔤 Unidad 05 — Tipografía, datos y cajas

| Código | Requerimiento |
|---|---|
| **RF-05.1** | Familia tipográfica con **alternativas** (`font-family` con varias opciones), jerarquía clara entre `h1`, `h2`, `h3` y texto, y `line-height` cómodo. |
| **RF-05.2** | Tablas y listas **legibles**: bordes colapsados, relleno, alineación (precios a la derecha) y listas sin viñetas donde corresponda. |
| **RF-05.3** | Tarjetas con **borde**, **esquinas redondeadas**, **relleno y margen** coherentes. |
| **RF-05.4** | `box-sizing: border-box` en todos los elementos y **página centrada** con ancho máximo (`max-width` y `margin: 0 auto`). |
| **RF-05.5** | Las tablas que no caben **no rompen la página**: se desplazan dentro de un contenedor con `overflow`. |

### 📏 Unidad 06 — Unidades relativas

| Código | Requerimiento |
|---|---|
| **RF-06.1** | `html { font-size: 100% }` y **todos los tamaños de letra en `rem`** (ninguno en `px`). |
| **RF-06.2** | Espacios (rellenos, márgenes, `gap`) y anchos máximos en `rem`; `px` **solo** para bordes finos. |
| **RF-06.3** | Ancho de lectura con `ch` en los párrafos (unos 65 caracteres). |
| **RF-06.4** | Al menos **una medida en `%`** y **una en unidad de ventana** (`vh`, por ejemplo en la altura mínima de la portada). |
| **RF-06.5** | En el `README` de tu entrega, **justificá por qué elegiste la unidad** en cinco medidas distintas. |

### 🧩 Unidad 07 — Grid y diseño adaptable

| Código | Requerimiento |
|---|---|
| **RF-07.1** | `<meta name="viewport" content="width=device-width, initial-scale=1.0">` en las cuatro páginas e **imágenes flexibles** (`max-width: 100%; height: auto`). |
| **RF-07.2** | **Enfoque móvil primero**: la hoja base es el teléfono (**una columna**); lo demás se agrega con `@media (min-width: …)`. |
| **RF-07.3** | **Dos puntos de ruptura: 600 px y 900 px.** Una columna por debajo de 600, **dos** desde 600 y **tres** desde 900 en el contenedor principal. Consultas escritas **de menor a mayor**. |
| **RF-07.4** | La cabecera, la portada y el pie ocupan **todo el ancho** en cualquier tamaño (`grid-column: 1 / -1`). Al menos un bloque ocupa **dos columnas** (`span 2`). |
| **RF-07.5** | Una **galería** (tarjetas de productos) que se acomoda **sola**, sin consultas, con `repeat(auto-fit, minmax(…, 1fr))`. |
| **RF-07.6** | Los espacios entre bloques se hacen con **`gap`**, no con márgenes sueltos. |
| **RF-07.7** | **Sin desplazamiento horizontal** a 500 px, 800 px y 1200 px (que son los tres tamaños de prueba). |

### 🚫 Restricciones

| Código | Restricción |
|---|---|
| **RNF-01** | Solo **HTML y CSS**. Sin JavaScript, sin frameworks (Bootstrap, Tailwind…) y sin plantillas copiadas. |
| **RNF-02** | **Sin Flexbox** y sin animaciones: no se vieron en estas unidades. La disposición es con **Grid**. |
| **RNF-03** | Nada de `style=""` ni `<style>` en las páginas. Sin `!important`. |
| **RNF-04** | Solo datos inventados. Ninguna información personal real. |
| **RNF-05** | Podés consultar tus apuntes, las guías y la documentación (MDN). **No** podés copiar código de otra persona ni de una IA sin entenderlo: en la sustentación te pediremos explicar y modificar tu código. |

## 🗓️ Plan sugerido de las 4 sesiones

> El plan es una **guía**. Podés adelantar trabajo fuera de clase, pero cada sesión termina con un **hito** que el docente revisa.

| Sesión | Foco | Qué hacés | ✅ Hito al terminar |
|---|---|---|---|
| **1** | Unidades 01 y 02 | Creás las cuatro páginas con su estructura semántica, el menú, las tablas, las listas, la cita y el formulario. Todavía **sin CSS**. | Las cuatro páginas se ven como documento sin estilo, con los enlaces funcionando y pasando la validación. |
| **2** | Unidades 03, 04 y 05 | Definís la paleta, el gradiente y el fondo (`base.css`); armás los componentes y estados (`componentes.css`); das forma a letra, tablas y cajas (`tipografia.css`, `cajas.css`). | El sitio **se ve completo y con identidad** en una ventana ancha, aunque todavía apilado. |
| **3** | Unidades 06 y 07 | Pasás todo a `rem`, agregás `ch`, `%` y `vh`; maquetás con Grid, la galería con `auto-fit` y la maqueta de **una columna** (móvil). | La página se ve bien a 500 px y no tiene scroll horizontal. |
| **4** | Unidad 07 y cierre | Agregás los puntos de ruptura de 600 y 900 px, probás en los **tres tamaños**, corregís desbordes, escribís el `README` y **entregás**. En la última hora: sustentación breve. | Entrega completa y sustentación. |

## 📦 Qué entregás

Una carpeta comprimida `apellido-nombre-proyecto-final.zip` con:

```text
apellido-nombre-proyecto-final/
├── index.html
├── carta.html
├── sedes.html
├── reservas.html
├── css/
│   ├── base.css
│   ├── tipografia.css
│   ├── cajas.css
│   ├── componentes.css
│   └── layout.css
├── imagenes/
└── README.md
```

El **`README.md`** contiene (no más de una página):

1. **Mapa del sitio**: las cuatro páginas y qué hay en cada una.
2. **Tabla de medidas.** Para cada página y cada tamaño de prueba, cuántas columnas tiene el contenedor principal y si hay desplazamiento horizontal:

   | Página | 500 px | 800 px | 1200 px |
   |---|---|---|---|
   | index | 1 columna, sin scroll | 2 columnas, sin scroll | 3 columnas, sin scroll |
   | carta | … | … | … |
   | sedes | … | … | … |
   | reservas | … | … | … |

3. **Justificación de cinco unidades** (RF-06.5): para cinco medidas, cuál usaste y por qué.
4. **Decisiones**: por qué elegiste móvil primero y por qué esos puntos de ruptura.
5. **Dificultades**: una cosa que te costó y cómo la resolviste.

## 🎤 Sustentación (en la sesión 4)

Cinco minutos con el docente, sobre **tu** proyecto:

- Abrir la página y mostrar los tres tamaños con las herramientas del navegador.
- Responder una pregunta de cada bloque (estructura, estilo, unidades, Grid).
- Hacer **un cambio en vivo** (por ejemplo, pasar el punto de ruptura de 900 a 1000 px o agregar una cuarta columna a la galería).

## ✅ Antes de entregar: lista de control

- [ ] Las cuatro páginas abren y todos los enlaces del menú funcionan.
- [ ] Probé a **500, 800 y 1200 px** y no hay desplazamiento horizontal.
- [ ] No hay `style=""`, `<style>`, `!important`, Flexbox ni JavaScript.
- [ ] Ningún tamaño de letra está en `px`.
- [ ] Los colores salen solo de las variables de `:root`.
- [ ] Probé el formulario con el teclado (`Tab`): el foco se ve siempre.
- [ ] El `README.md` tiene las cinco partes.
- [ ] El zip se llama `apellido-nombre-proyecto-final.zip`.

## 💡 Consejos

- **Primero el contenido, después el estilo, al final la adaptación.** No mezcles las tres cosas.
- Probá a **500 px desde la sesión 3**, no solo al final: un desborde se corrige mejor cuando es pequeño.
- Si algo se sale de la pantalla, el culpable suele ser una imagen, una tabla o un ancho fijo. Buscalo con las herramientas del navegador.
- Guardá versiones: copiá la carpeta al terminar cada sesión.

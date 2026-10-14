# 📚 Explicación conceptual — Fundamentos HTML

En esta clase vas a construir, paso a paso, el **sitio personal de Lucía Fernández**, una desarrolladora web junior
ficticia. Cada concepto se muestra en las páginas de ese sitio. No necesitás saber programar: solo curiosidad y una
computadora con un navegador.

Resultados de aprendizaje de la clase:

- **RA-1**: explicar qué es HTML5 y qué papel cumple en una página web.
- **RA-2**: preparar un entorno de desarrollo con VS Code, crear un archivo HTML y verlo en el navegador.
- **RA-3**: escribir un documento con estructura válida, sintaxis y anidación, y explicar el DOM.
- **RA-4**: marcar un texto con etiquetas de texto y de formato, y documentarlo con comentarios.
- **RA-5**: crear hipervínculos e identificar las partes de una dirección web.
- **RA-6**: incorporar imágenes, video y contenido incrustado con `iframe`.
- **RA-7**: organizar una página con etiquetas semánticas y decidir cuándo usar `div`.

## 🗒️ Glosario

Usamos los términos técnicos en su forma habitual, con su equivalente en español la primera vez.

| Término | Equivalente |
|---|---|
| *tag* | etiqueta |
| *element* | elemento |
| *attribute* | atributo |
| *link* / *hyperlink* | enlace / hipervínculo |
| *path* | ruta |
| *query string* | parámetros de la dirección |
| *anchor* | ancla |
| *browser* | navegador |
| *DOM* | modelo de objetos del documento |

> 📌 **Origen de la información.** Las descripciones de las etiquetas están contrastadas con **MDN Web Docs**, la
> referencia más usada para HTML. Los **fragmentos de texto** de los enlaces no son parte de HTML sino una función del
> navegador: te lo avisamos cuando lleguemos.

---

## 🌐 ¿Qué es HTML5?

_Resultados de aprendizaje: RA-1_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 01 — Tu primera página](01-primera-pagina.md): una página mínima que se abre en el navegador.

### 🌍 Contexto

Todas las páginas web que visitás —un diario, una tienda, una red social— llegan a tu navegador como texto escrito en
un lenguaje. Para construir una, primero hay que saber cuál es y qué hace.

### 💡 Concepto

**HTML** (*HyperText Markup Language*, lenguaje de marcado de hipertexto) es el lenguaje con el que se **marca la
estructura y el significado del contenido** de una página: qué es un título, qué es un párrafo, qué es un enlace y
qué es una imagen. **HTML5** es la versión moderna de ese lenguaje.

### 📖 Explicación

**Es un lenguaje de marcado, no de programación.** HTML no calcula ni toma decisiones: **describe** el contenido. Por
eso se puede aprender sin saber programar.

**Cómo se ve.** Un documento HTML es un archivo de texto con extensión `.html`. El contenido se rodea de
**etiquetas** que le dan significado:

```html
<h1>Lucía Fernández</h1>
<p>Desarrolladora web junior</p>
```

**Quién lo lee.** El **navegador** (Chrome, Firefox, Safari, Edge) lee el archivo y lo muestra como una página. Cada
persona ve la misma estructura aunque use otro navegador.

**Qué no hace.** HTML da la estructura; el **aspecto** (colores, tipografías, ubicación) lo define CSS, el próximo
módulo del curso.

---

## 🧰 Entorno de desarrollo y VS Code

_Resultados de aprendizaje: RA-2_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 01 — Tu primera página](01-primera-pagina.md): crear la carpeta y el archivo en VS Code y abrirlo en el navegador.

### 🌍 Contexto

Podrías escribir HTML en el Bloc de notas, pero un editor pensado para código te ayuda a escribir más rápido y a
cometer menos errores.

### 💡 Concepto

Un **entorno de desarrollo** es el conjunto de herramientas con las que escribís, probás y organizás tu proyecto. Para
HTML alcanza con **dos**: un **editor de código** y un **navegador**. **Visual Studio Code** (VS Code) es un editor de
código gratuito, muy usado.

### 📖 Explicación

**Qué te da el editor.** Colorea el código para distinguir etiquetas de texto, te muestra los archivos de tu proyecto
en un panel lateral y te avisa de algunos errores.

**Cómo se trabaja.**

1. Creás una **carpeta** para el proyecto (por ejemplo, `portafolio`).
2. La abrís en VS Code (*Archivo → Abrir carpeta*).
3. Creás un archivo con extensión `.html` (por ejemplo, `index.html`).
4. Escribís el código y lo **guardás**.
5. Abrís el archivo en el navegador (doble clic en el archivo, o *clic derecho → Abrir con*) y, cuando cambies algo,
   guardás y **recargás** la página.

**¿Y el nombre `index.html`?** Es el nombre tradicional de la página principal de un sitio.

> 💡 **Si no podés instalar VS Code**, podés usar un **editor en línea** gratuito que muestre el HTML y su resultado
> lado a lado. Los ejemplos de la clase funcionan igual.

---

## 🏗️ Estructura de un proyecto de HTML

_Resultados de aprendizaje: RA-3_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 02 — Estructura, sintaxis y DOM](02-estructura-y-dom.md): la estructura mínima, la sintaxis, la anidación y el árbol DOM.

![Un elemento HTML se forma con una etiqueta de apertura que puede llevar atributos, el contenido y una etiqueta de cierre con una barra; juntos forman el elemento.](../imagenes/anatomia-de-una-etiqueta.svg)

![El navegador convierte el documento en un árbol: html contiene head y body; head contiene meta y title; body contiene header, main y footer; main contiene un título h2 y un párrafo.](../imagenes/arbol-dom.svg)

### 🌍 Contexto

Todas las páginas empiezan igual. Antes de agregar contenido, tenés que armar el «esqueleto» del documento, y escribir
las etiquetas de forma que el navegador las entienda.

### 💡 Concepto

Un documento HTML tiene una **estructura mínima**, se escribe con una **sintaxis** precisa (etiquetas y atributos) y
sus etiquetas se **anidan** unas dentro de otras. El navegador representa esa anidación como un árbol llamado **DOM**.

### 📖 Explicación

**La estructura mínima.**

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Lucía Fernández | Desarrolladora web</title>
  </head>
  <body>
    <p>Hola</p>
  </body>
</html>
```

| Parte | Para qué sirve |
|---|---|
| `<!doctype html>` | Indica que es un documento HTML5; evita que el navegador use un modo antiguo |
| `<html lang="es">` | Contiene todo el documento y declara que el idioma es español |
| `<head>` | Datos **sobre** la página que no se muestran en ella |
| `<meta charset="utf-8">` | Codificación de caracteres: permite escribir tildes y la «ñ» |
| `<title>` | Título del documento: aparece en la pestaña del navegador |
| `<body>` | Todo lo que se **ve** en la página |

**La sintaxis.** Un **elemento** tiene una **etiqueta de apertura**, un **contenido** y una **etiqueta de cierre**
(con una barra). La apertura puede llevar **atributos** con la forma `nombre="valor"`: siempre entre comillas.

```html
<a href="proyectos.html" target="_blank">Ver proyectos</a>
```

Algunos elementos son **vacíos**: no tienen contenido ni etiqueta de cierre. Por ejemplo `<br>` (salto de línea),
`<hr>` (línea horizontal) e `<img>` (imagen).

**La anidación.** Las etiquetas se colocan unas **dentro** de otras y se cierran en orden inverso al que se abrieron:

```html
<p>Mi nombre es <strong>Lucía</strong>.</p>
```

El caso incorrecto es **solaparlas**: `<p>Mi nombre es <strong>Lucía.</p></strong>`. El navegador tiene que «adivinar»
lo que quisiste decir y el resultado puede ser inesperado. **Olvidar el cierre** de una etiqueta es el error más
común de quien empieza.

**El DOM.** Cuando abrís el archivo, el navegador arma un **árbol**: `html` es la raíz, `head` y `body` son sus
**hijos**, y cada etiqueta anidada cuelga de su **padre**. Ese árbol se llama **DOM** (*Document Object Model*,
modelo de objetos del documento) y es lo que el navegador usa para mostrar y, más adelante, modificar la página.

---

## ✍️ Tipos de etiquetas: texto y formato

_Resultados de aprendizaje: RA-4_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 03 — Texto, formato y comentarios](03-texto-formato-y-comentarios.md): la página «Sobre mí» de Lucía con títulos, párrafos, listas y formato.

### 🌍 Contexto

Un texto sin marcar es una sola masa de palabras. Con etiquetas el navegador sabe dónde hay un título, dónde termina
un párrafo y qué palabra es importante.

### 💡 Concepto

Las **etiquetas de texto** estructuran el contenido (títulos, párrafos, listas) y las **etiquetas de formato** dan
énfasis o significado a una parte del texto.

### 📖 Explicación

**Etiquetas de texto esenciales.**

| Etiqueta | Qué marca |
|---|---|
| `<h1>` a `<h6>` | Títulos en seis niveles: `h1` el más importante |
| `<p>` | Un párrafo |
| `<br>` | Un salto de línea (vacía) |
| `<hr>` | Una línea horizontal que separa temas (vacía) |
| `<ul>` y `<ol>` con `<li>` | Lista **no ordenada** (viñetas) y lista **ordenada** (números); cada ítem va en un `<li>` |

> 💡 Usá **un solo `h1` por página** y **no saltes niveles** (de `h1` a `h3`, por ejemplo). Y no uses un título
> «para que se vea más grande»: para eso está CSS.

**Etiquetas de formato esenciales.**

| Etiqueta | Significado | Se ve habitualmente como |
|---|---|---|
| `<strong>` | Importancia, seriedad o urgencia | negrita |
| `<em>` | Énfasis | cursiva |
| `<mark>` | Texto resaltado por su relevancia | resaltado |
| `<small>` | Letra pequeña (aclaraciones) | texto más chico |
| `<sub>` / `<sup>` | Subíndice / superíndice | texto más bajo / más alto |
| `<del>` / `<ins>` | Texto eliminado / texto agregado | tachado / subrayado |
| `<code>` | Fragmento de código | letra de ancho fijo |

Las etiquetas de formato **describen** un significado; que se vean en negrita o en cursiva es solo la apariencia que
suele darles el navegador.

---

## 💬 Comentarios en HTML

_Resultados de aprendizaje: RA-4_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 03 — Texto, formato y comentarios](03-texto-formato-y-comentarios.md): comentarios en la página «Sobre mí» y en la cabecera.

### 🌍 Contexto

A veces querés dejar una nota para vos o para otra persona que lea el código, sin que aparezca en la página.

### 💡 Concepto

Un **comentario** es un texto del código que el navegador **ignora**: no se ve en la página.

### 📖 Explicación

Se escribe entre `<!--` y `-->`:

```html
<!-- Presentación breve: un párrafo por idea -->
<p>Me llamo Lucía.</p>
```

Sirve para **explicar** el código, para **organizarlo** en bloques y para **desactivar** temporalmente una parte sin
borrarla. Los comentarios los puede leer cualquiera que vea el código de la página, así que **no escribas ahí datos
privados**.

---

## 🔗 ¿Qué son los hipervínculos?

_Resultados de aprendizaje: RA-5_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 04 — Enlaces y direcciones](04-enlaces-y-direcciones.md): enlaces externos, a otro archivo y las partes de una dirección.
> - [Ejemplo 05 — Anclas y fragmentos de texto](05-anclas-y-fragmentos.md): saltar a una sección de la misma página y enlazar a un texto.

![La dirección https://lucia-fernandez.example:443/proyectos/panaderia.html?categoria=web&orden=reciente#resultados se divide en protocolo, dominio, puerto, ruta, parámetros y ancla.](../imagenes/partes-de-una-direccion.svg)

### 🌍 Contexto

Lo que hace «web» a la web son los enlaces: permiten ir de una página a otra. Para escribirlos bien tenés que
entender cómo está formada una dirección.

### 💡 Concepto

Un **hipervínculo** (o **enlace**) es un elemento que lleva a otro lugar al hacer clic. Se crea con la etiqueta
`<a>` y su atributo `href`, que contiene la **dirección** de destino.

```html
<a href="https://developer.mozilla.org/es/" target="_blank" rel="noopener">MDN en español</a>
```

### 📖 Explicación

**Las partes de una dirección.** Tomemos
`https://lucia-fernandez.example:443/proyectos/panaderia.html?categoria=web&orden=reciente#resultados`:

| Parte | En el ejemplo | Qué es |
|---|---|---|
| **Protocolo** | `https://` | La forma de comunicarse; `https` es la versión segura de `http` |
| **Dominio** | `lucia-fernandez.example` | El nombre del sitio |
| **Puerto** | `:443` | Opcional; casi siempre se omite (443 es el habitual de `https`) |
| **Ruta o path** | `/proyectos/panaderia.html` | Dónde está el archivo dentro del sitio |
| **Parámetros o query strings** | `?categoria=web&orden=reciente` | Datos que se envían; empiezan con `?` y se separan con `&` |
| **Ancla** | `#resultados` | Un punto concreto de la página; empieza con `#` |

> 💡 El dominio `.example` está reservado para ejemplos: no existe en internet, y por eso lo usamos en esta clase.

**Rutas absolutas y relativas.** Una dirección completa (con protocolo y dominio) es **absoluta**. Para enlazar a otro
archivo **de tu propio sitio** usás una ruta **relativa**, que se cuenta desde el archivo actual:

| Ruta | Significa |
|---|---|
| `sobre-mi.html` | Un archivo en la misma carpeta |
| `imagenes/foto-lucia.png` | Un archivo dentro de la subcarpeta `imagenes` |
| `../index.html` | Un archivo en la carpeta de arriba |

**Anclas.** Para saltar a una parte de la **misma página**, le ponés un `id` al elemento de destino y enlazás con
`#` y ese `id`:

```html
<a href="#panaderia">Sitio de una panadería</a>
...
<article id="panaderia"> ... </article>
```

**Fragmentos de texto.** Un enlace puede incluir `#:~:text=` y un texto para que el navegador **resalte esa frase**
al abrir la página: `sobre-mi.html#:~:text=Mi%20lema`.

> 📌 **Recurso opcional del navegador.** Los fragmentos de texto **no son parte de HTML**: son una función del
> navegador (disponible en Chrome desde la versión 80, Safari 16.1 y Firefox 131). Si el navegador no la admite, o el
> texto no existe en la página, **el enlace funciona igual** y te lleva a la página desde arriba. Por eso conviene
> usarlos como un extra, nunca como lo único que hace funcionar un enlace.

**Abrir en otra pestaña.** `target="_blank"` abre el enlace en una pestaña nueva. Agregarle `rel="noopener"` es una
buena costumbre por seguridad al enlazar a otros sitios.

---

## 🖼️ Manejo de multimedia

_Resultados de aprendizaje: RA-6_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 06 — Imágenes, video e iframe](06-imagenes-video-e-iframe.md): la foto de Lucía, su video de presentación, un mapa y un error de ruta corregido.

### 🌍 Contexto

Una página solo con texto es poco atractiva. Las imágenes, el video y el contenido de otros sitios hacen la página más
rica, siempre que sepas dónde está cada archivo.

### 💡 Concepto

HTML incorpora archivos multimedia con **etiquetas propias**: `<img>` para imágenes, `<video>` para video e
`<iframe>` para mostrar **otra página dentro de la tuya**.

### 📖 Explicación

**Imágenes.** `<img>` es una etiqueta **vacía**. Necesita `src` (la ruta del archivo) y `alt` (un texto que
**describe** la imagen para quien no puede verla):

```html
<img src="imagenes/foto-lucia.png" alt="Retrato ilustrado de Lucía, una joven de pelo castaño con un buzo azul" width="200">
```

El `alt` debe describir **qué muestra** la imagen, no decir «imagen de…» ni repetir el nombre del archivo.

**Video.** `<video>` con el atributo `controls` muestra los botones de reproducción. Lo que escribas dentro se ve solo
si el navegador no admite video:

```html
<video controls width="480">
  <source src="video/presentacion.mp4" type="video/mp4">
  <p>Tu navegador no reproduce video.</p>
</video>
```

**iframe.** `<iframe>` incrusta otro documento dentro de tu página, por ejemplo un mapa. Siempre conviene darle un
`title` que describa su contenido:

```html
<iframe title="Mapa de OpenStreetMap con el centro de Buenos Aires" width="480" height="320"
  src="https://www.openstreetmap.org/export/embed.html?bbox=-58.42%2C-34.63%2C-58.36%2C-34.59&amp;layer=mapnik"></iframe>
```

> ⚠️ **No todos los sitios se dejan incrustar.** Algunos lo bloquean por seguridad y el recuadro queda vacío. Elegí
> contenido que lo permita (como el mapa de OpenStreetMap).

**Cuando no se ve.** Casi siempre es un problema de **ruta**: revisá que el archivo exista en la carpeta indicada, que
el nombre y la **extensión** estén escritos igual (`foto.png` no es `foto.jpg`) y que la ruta relativa cuente bien las
carpetas.

---

## 🧭 Semántica

_Resultados de aprendizaje: RA-7_

> 🔗 **Ejemplos de este concepto**
>
> - [Ejemplo 07 — Semántica y `div`](07-semantica-y-div.md): de una página hecha solo con `div` a una con etiquetas que describen su estructura.

![Una página semántica tiene header arriba con nav, un main en el centro con secciones y artículos, un aside lateral y un footer al pie.](../imagenes/estructura-semantica.svg)

### 🌍 Contexto

Una página puede verse bien y estar mal armada por dentro. Un lector de pantalla, un buscador o vos misma dentro de un
año necesitan saber **qué es cada parte**.

### 💡 Concepto

La **semántica** es usar la etiqueta que **describe el significado** de cada parte, no solo su apariencia. Las
**etiquetas semánticas** nombran el papel de una parte de la página.

### 📖 Explicación

| Etiqueta | Qué representa |
|---|---|
| `<header>` | Contenido introductorio de la página (o de una sección) |
| `<nav>` | La navegación principal: enlaces a las partes del sitio |
| `<main>` | El contenido **propio de esta página**; se usa **una sola vez** por página |
| `<section>` | Una parte con un tema propio; conviene empezarla con un título |
| `<article>` | Un bloque que se entiende **por sí solo** (por ejemplo, un proyecto o una entrada de blog) |
| `<aside>` | Contenido relacionado pero secundario |
| `<footer>` | El pie: contenido final de la página |

**¿Y `div`?** `<div>` es un contenedor **genérico, sin significado**. No cambia nada de lo que se ve hasta que se le da
estilo con CSS.

> 💡 **Regla práctica.** Usá `div` **solo cuando ninguna etiqueta semántica describa** lo que querés agrupar. Si hay
> una etiqueta que dice qué es (`nav`, `article`, `footer`…), usala: tu página será más clara para todos.

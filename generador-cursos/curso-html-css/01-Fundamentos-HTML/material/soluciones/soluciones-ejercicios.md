# 🔑 Soluciones — Ejercicios de la Clase 01 (material docente)

No compartir este archivo con los estudiantes.

Todo el código de estas soluciones se validó con la revisión de estructura del curso y se abrió en Chrome. Los ejercicios
**cerrados** tienen una sola respuesta defendible; los **abiertos** se evalúan con los criterios indicados.

---

## 🟢 Básico 01 — Corregí la estructura de un documento

### ✅ Respuesta o criterio

**Parte A — los cinco errores**

| # | Error | Corrección |
|---|---|---|
| 1 | Falta `<!doctype html>` al inicio | Agregarlo como primera línea |
| 2 | `<html>` sin el idioma | `<html lang="es">` |
| 3 | `<title>` sin cerrar | Agregar `</title>` |
| 4 | Etiquetas solapadas: `<em>Rosario</p></em>` | `<em>Rosario</em></p>` |
| 5 | La etiqueta vacía `<img>` lleva cierre | Quitar `</img>` |

Documento corregido:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Mateo Ruiz | Fotógrafo</title>
  </head>
  <body>
    <h1>Mateo Ruiz</h1>
    <p>Fotógrafo de <em>Rosario</em></p>
    <img src="imagenes/retrato.png" alt="Retrato de Mateo">
  </body>
</html>
```

**Parte B**

| Elemento | Dónde va |
|---|---|
| `title` | `head` |
| `meta` | `head` |
| `h1` | `body` |
| `p` | `body` |
| `img` | `body` |

**Parte C**

1. HTML es un lenguaje de **marcado**: describe la estructura y el significado del contenido, no calcula ni decide.
2. El padre de `em` es `p`.
3. Con la extensión `.html`.

### 🔍 Justificación

Los cinco errores corresponden a la estructura mínima (doctype, `lang`), a la sintaxis (cierre de `title`, etiqueta
vacía) y a la anidación (etiquetas solapadas). El `head` guarda datos de la página; el `body`, lo que se ve.

### 🔎 Verificación

Cinco errores con su corrección, cinco clasificaciones correctas y tres respuestas correctas. El documento corregido
pasa la revisión de estructura sin errores.

---

## 🟢 Básico 02 — Marcá un texto y comentalo

### ✅ Respuesta o criterio

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Sobre mí | Mateo Ruiz</title>
  </head>
  <body>
    <!-- Página «Sobre mí» de Mateo Ruiz -->
    <h1>Sobre mí</h1>

    <p>Soy <strong>Mateo Ruiz</strong>, fotógrafo de Rosario. Fotografío bodas, paisajes y retratos.</p>

    <p>Trabajo con <em>luz natural</em> siempre que puedo.</p>

    <h2>Lo que ofrezco</h2>

    <!-- Lista de servicios -->
    <ul>
      <li>Sesiones de retratos</li>
      <li>Fotografía de eventos</li>
      <li>Álbumes impresos</li>
    </ul>

    <p>Mi precio por sesión era <del>80 USD</del> y ahora es <ins>70 USD</ins>.</p>

    <p>Las fotos se entregan en alta resolución.</p>
  </body>
</html>
```

Son válidas otras ubicaciones razonables de los comentarios. No son aceptables `<b>` e `<i>` en lugar de `strong` y `em`,
porque el ejercicio pide importancia y énfasis.

### 🔍 Justificación

Un título principal y uno de sección, cuatro párrafos, una lista con viñetas, `strong` para la importancia, `em` para el
énfasis y `del`/`ins` para el cambio de precio. Los comentarios no se ven.

### 🔎 Verificación

Recuento: `h1` = 1, `h2` = 1, `p` = 4, `ul` = 1, `li` = 3, `strong` ≥ 1, `em` ≥ 1, `del` = 1, `ins` = 1 y al menos dos
comentarios. La revisión de estructura pasa sin errores y en el navegador no se ve ningún comentario.

---

## 🟡 Intermedio 01 — Conectá las páginas de Mateo

### ✅ Respuesta o criterio

**Parte A** — `index.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Mateo Ruiz | Fotógrafo</title>
  </head>
  <body>
    <h1>Mateo Ruiz</h1>
    <p>Fotógrafo de Rosario</p>

    <p>
      <a href="index.html">Inicio</a> |
      <a href="galeria.html">Galería</a> |
      <a href="sobre-mi.html">Sobre mí</a> |
      <a href="#servicios">Servicios</a> |
      <a href="#contacto">Contacto</a>
    </p>

    <h2 id="servicios">Servicios</h2>
    <p>Retratos, eventos y álbumes impresos.</p>

    <h2 id="contacto">Contacto</h2>
    <p>Escribime y coordinamos una sesión.</p>

    <p>Para aprender más sobre fotografía: <a href="https://es.wikipedia.org/wiki/Fotograf%C3%ADa" target="_blank" rel="noopener">Wikipedia, artículo «Fotografía»</a>.</p>
  </body>
</html>
```

**Parte B**

| Parte | Valor |
|---|---|
| Protocolo | `https://` |
| Dominio | `mateo-ruiz.example` |
| Puerto | No tiene (se usa el habitual) |
| Ruta | `/galeria/bodas.html` |
| Parámetros | `anio` = `2025` y `tipo` = `color` (`?anio=2025&tipo=color`) |
| Ancla | `#album-3` |

**Parte C**

- Desde `galeria.html` (misma carpeta que `index.html`): `href="index.html"`.
- Desde una página dentro de `fotos/`: `href="../index.html"`.

### 🔍 Justificación

Las páginas del mismo sitio se enlazan con rutas relativas. Las anclas usan `#` y el `id` del destino. El enlace
externo usa la dirección absoluta y `target="_blank"` con `rel="noopener"`. Los parámetros empiezan con `?` y se separan
con `&`; el ancla va siempre al final.

### 🔎 Verificación

Cinco enlaces internos que funcionan, uno externo con `target="_blank"` y `rel="noopener"`, la dirección dividida en sus
partes sin errores y las dos rutas relativas correctas. La revisión de estructura pasa sin errores.

---

## 🟡 Intermedio 02 — Arreglá la galería de Mateo

### ✅ Respuesta o criterio

**Los tres errores**

| # | Qué pasa | Corrección |
|---|---|---|
| 1 | `src="imagen/boda.png"`: la carpeta se llama `imagenes` | `src="imagenes/boda.png"` |
| 2 | `src="imagenes/paisaje.jpg"`: el archivo es `.png` | `src="imagenes/paisaje.png"` |
| 3 | La imagen del retrato no tiene `alt` | Agregar un `alt` descriptivo |

Galería corregida:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Galería | Mateo Ruiz</title>
  </head>
  <body>
    <h1>Galería</h1>

    <h2>Fotos</h2>
    <img src="imagenes/boda.png" alt="Pareja de novios caminando por un parque" width="240">
    <img src="imagenes/paisaje.png" alt="Montañas al atardecer" width="240">
    <img src="imagenes/retrato.png" alt="Retrato de una persona con un buzo violeta" width="240">

    <h2>Video</h2>
    <video controls width="480">
      <source src="video/demo.mp4" type="video/mp4">
      <p>Tu navegador no reproduce video. Podés <a href="video/demo.mp4">descargarlo acá</a>.</p>
    </video>

    <h2>Dónde trabajo</h2>
    <p>Trabajo en Rosario y alrededores.</p>
    <iframe title="Mapa de OpenStreetMap con la zona de Rosario" width="480" height="320"
      src="https://www.openstreetmap.org/export/embed.html?bbox=-60.75%2C-33.0%2C-60.6%2C-32.9&amp;layer=mapnik"></iframe>
  </body>
</html>
```

### 🔍 Justificación

Los dos primeros son errores de ruta (carpeta y extensión) y el tercero es de accesibilidad. El `alt` del retrato debe
describir lo que se ve, no decir «imagen». El video necesita `controls` para mostrar los botones; el `iframe` lleva
`title` y el `&` de la dirección se escribe `&amp;`.

### 🔎 Verificación

Tres errores identificados y corregidos, las tres fotos se ven, el video tiene `controls` y `source`, el `iframe` tiene
`title`. La revisión de estructura pasa sin errores (sin rutas rotas ni imágenes sin `alt`).

---

## 🔴 Desafío 01 — De `div` a una página semántica

### ✅ Respuesta o criterio

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Mateo Ruiz | Fotógrafo</title>
  </head>
  <body>
    <!-- Cabecera: nombre y navegación -->
    <header id="arriba">
      <h1>Mateo Ruiz</h1>
      <p>Fotógrafo de Rosario</p>
      <nav>
        <a href="index.html">Inicio</a> |
        <a href="galeria.html">Galería</a> |
        <a href="sobre-mi.html">Sobre mí</a> |
        <a href="#contacto">Contacto</a>
      </nav>
    </header>

    <!-- Contenido principal: una sección por tema -->
    <main>
      <section>
        <h2>Trabajos destacados</h2>
        <!-- Se mantiene este div: solo agrupa las dos fotos para darles estilo después y no tiene significado propio -->
        <div>
          <img src="imagenes/boda.png" alt="Pareja de novios caminando por un parque" width="240">
          <img src="imagenes/paisaje.png" alt="Montañas al atardecer" width="240">
        </div>
        <p>Una selección de mis sesiones de bodas y paisajes.</p>
      </section>

      <section>
        <h2>Servicios</h2>
        <p>Retratos, eventos y álbumes impresos.</p>
      </section>

      <section id="contacto">
        <h2>Contacto</h2>
        <p><em>Escribime</em> y coordinamos una sesión.</p>
        <iframe title="Mapa de OpenStreetMap con la zona de Rosario" width="480" height="320"
          src="https://www.openstreetmap.org/export/embed.html?bbox=-60.75%2C-33.0%2C-60.6%2C-32.9&amp;layer=mapnik"></iframe>
      </section>
    </main>

    <!-- Pie de la página -->
    <footer>
      <p>© 2026 Mateo Ruiz. Sitio de ejemplo del curso.</p>
      <p><a href="#arriba">Volver arriba</a></p>
    </footer>
  </body>
</html>
```

**El `div` que se mantiene:** el que agrupa las dos fotos, porque solo sirve para darles estilo más adelante y no tiene
significado propio (no es una sección ni un artículo).

### 🔍 Justificación

El primer `div` es `header`, el de enlaces es `nav`, el contenido va en un único `main` con una `section` por tema, y el
último bloque es `footer`. El `id="arriba"` en la cabecera permite el enlace «Volver arriba».

### 🔎 Verificación

Se cumplen los 11 casos de prueba:

| # | Resultado |
|---|---|
| 1 | Un `<main>` |
| 2 | Un `<h1>`, dentro de `<header>` |
| 3 | `<nav>` dentro de `<header>` con cuatro enlaces |
| 4 | Tres `<section>`, cada una con `<h2>` |
| 5 | `<footer>` con «Volver arriba» |
| 6 | Un solo `<div>`, con su comentario |
| 7 | «Contacto» baja a `#contacto` |
| 8 | «Volver arriba» vuelve a `#arriba` |
| 9 | Todas las imágenes con `alt` y visibles |
| 10 | `iframe` con `title` |
| 11 | La revisión de estructura da 0 errores |

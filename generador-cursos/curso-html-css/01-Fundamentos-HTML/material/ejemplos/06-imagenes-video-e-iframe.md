# 📘 Ejemplo 06 — Imágenes, video e iframe

## 🧱 Situación inicial

Lucía quiere que su página de inicio tenga su foto, un video corto de presentación y un mapa de su zona. En la carpeta
`portafolio` ya están los archivos:

```text
portafolio/
├── index.html
├── imagenes/
│   └── foto-lucia.png
└── video/
    └── presentacion.mp4
```

## 💻 Código

La página completa `index.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Lucía Fernández | Desarrolladora web</title>
  </head>
  <body>
    <!-- Cabecera con el nombre y la navegación -->
    <header>
      <h1>Lucía Fernández</h1>
      <p>Desarrolladora web junior</p>
      <nav>
        <a href="index.html">Inicio</a> |
        <a href="sobre-mi.html">Sobre mí</a> |
        <a href="proyectos.html">Proyectos</a> |
        <a href="#contacto">Contacto</a>
      </nav>
    </header>

    <main>
      <section>
        <h2>Hola, soy Lucía</h2>
        <img src="imagenes/foto-lucia.png" alt="Retrato ilustrado de Lucía, una joven de pelo castaño con un buzo azul" width="200">
        <p>Construyo páginas web claras y fáciles de usar. Acá vas a encontrar mis proyectos y cómo trabajo.</p>
      </section>

      <section>
        <h2>Mi presentación en video</h2>
        <video controls width="480">
          <source src="video/presentacion.mp4" type="video/mp4">
          <p>Tu navegador no reproduce video. Podés <a href="video/presentacion.mp4">descargarlo acá</a>.</p>
        </video>
      </section>

      <section id="contacto">
        <h2>Contacto</h2>
        <p>Trabajo desde Buenos Aires. Este es el mapa de mi zona:</p>
        <iframe title="Mapa de OpenStreetMap con el centro de Buenos Aires" width="480" height="320"
          src="https://www.openstreetmap.org/export/embed.html?bbox=-58.42%2C-34.63%2C-58.36%2C-34.59&amp;layer=mapnik"></iframe>
      </section>
    </main>

    <footer>
      <p><small>© 2026 Lucía Fernández. Sitio de ejemplo del curso.</small></p>
    </footer>
  </body>
</html>
```

## 🔍 Análisis paso a paso

1. **La imagen.** `<img>` es una etiqueta vacía. `src="imagenes/foto-lucia.png"` es una ruta **relativa**: entra a la
   subcarpeta `imagenes`. `alt` describe lo que se ve, y `width="200"` fija el ancho.
2. **El video.** `<video controls>` muestra los botones de reproducción. Dentro, `<source>` indica el archivo y su tipo
   (`video/mp4`), y el párrafo se muestra solo si el navegador no admite video.
3. **El iframe.** `<iframe>` incrusta el mapa de OpenStreetMap. Lleva un `title` que describe el contenido y un tamaño. En
   la dirección, `&amp;` es la forma de escribir `&` dentro de HTML.
4. **Un error de ruta.** Si Lucía escribe `src="imagen/foto-lucia.png"` (le falta la «s») o `foto-lucia.jpg` (otra
   extensión), la imagen no carga y el navegador muestra el texto de `alt` (o un ícono de imagen rota).
5. **Cómo corregirlo.** Revisa que la carpeta se llame igual (`imagenes`), que el archivo exista con ese nombre exacto y
   que la extensión coincida. Corrige y recarga con `F5`.
6. **Un sitio que no se deja incrustar.** Si intenta incrustar una página que bloquea los iframes, el recuadro queda en
   blanco: el sitio lo impide. Por eso eligió el mapa de OpenStreetMap, que sí lo permite.

## ✅ Resultado esperado

- Una **foto ilustrada** de Lucía (una joven de pelo castaño con un buzo azul) de 200 píxeles de ancho.
- Un **reproductor** con los controles del navegador; al reproducirlo se ven, durante unos 6 segundos, tres pantallas de
  proyectos.
- Un **mapa** de Buenos Aires dentro de un recuadro de 480 × 320 píxeles (necesita conexión a internet).
- Con la ruta mal escrita, la foto **no aparece** y se ve su texto alternativo; con la ruta corregida, aparece.

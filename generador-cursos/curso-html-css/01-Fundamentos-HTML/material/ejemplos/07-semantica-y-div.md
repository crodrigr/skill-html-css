# 📘 Ejemplo 07 — Semántica y `div`

## 🧱 Situación inicial

La primera versión de la página de inicio de Lucía usa solo `div` para todo. Funciona, pero nada dice qué es cada parte:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Lucía Fernández | Desarrolladora web</title>
  </head>
  <body>
    <div>
      <h1>Lucía Fernández</h1>
      <p>Desarrolladora web junior</p>
      <div>
        <a href="index.html">Inicio</a> |
        <a href="sobre-mi.html">Sobre mí</a> |
        <a href="proyectos.html">Proyectos</a>
      </div>
    </div>
    <div>
      <h2>Hola, soy Lucía</h2>
      <p>Construyo páginas web claras y fáciles de usar.</p>
    </div>
    <div>
      <p>© 2026 Lucía Fernández.</p>
    </div>
  </body>
</html>
```

## 💻 Código

La versión semántica es la página `index.html` completa (la misma del ejemplo 06):

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

1. **La cabecera.** El primer `div`, que contiene el título y la navegación, pasa a ser `<header>`.
2. **La navegación.** El `div` con los enlaces a las otras páginas pasa a ser `<nav>`, dentro del `header`.
3. **El contenido principal.** Lo propio de esta página va dentro de un único `<main>`.
4. **Las secciones.** Cada tema («Hola, soy Lucía», «Mi presentación en video», «Contacto») es una `<section>` con su
   título `h2`.
5. **El pie.** El último `div` pasa a ser `<footer>`, con la letra chica en `<small>`.
6. **¿Qué pasa con `div`?** En la página final ya no queda ninguno: cada grupo tiene una etiqueta que dice lo que es.
7. **Cuándo sí usar `div`.** Si Lucía necesitara agrupar la foto y un texto solo para darles estilo más adelante, sin que
   ese grupo signifique algo (no es una sección ni un artículo), ahí sí usaría `<div>`.
8. **Comprobar.** Se ve igual en el navegador que la versión con `div`: la diferencia está en la estructura.

## ✅ Resultado esperado

- Visualmente, la página se ve **casi igual** que la de `div`: la semántica no cambia el aspecto, cambia el **significado**.
- Podés señalar en el código qué es la cabecera, la navegación, el contenido principal, cada sección y el pie.
- En la estructura hay **un solo** `<main>`.
- Podés dar un caso en el que se mantiene un `<div>`: un grupo sin significado propio, solo para dar estilo.

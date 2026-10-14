# 📘 Ejemplo 05 — Anclas y fragmentos de texto

## 🧱 Situación inicial

La página `proyectos.html` de Lucía tiene tres proyectos y es larga. Quiere un índice al principio que lleve a cada
proyecto, un enlace «Volver arriba» al final de cada uno y, además, un enlace que lleve a una frase de «Sobre mí».

## 💻 Código

La página completa `proyectos.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Proyectos | Lucía Fernández</title>
  </head>
  <body>
    <header id="arriba">
      <h1>Mis proyectos</h1>
      <nav>
        <a href="index.html">Inicio</a> |
        <a href="sobre-mi.html">Sobre mí</a> |
        <a href="proyectos.html">Proyectos</a>
      </nav>
    </header>

    <main>
      <p>Estos son tres proyectos que armé mientras aprendía:</p>
      <ul>
        <li><a href="#panaderia">Sitio de una panadería</a></li>
        <li><a href="#agenda">Agenda de turnos</a></li>
        <li><a href="#recetas">Blog de recetas</a></li>
      </ul>

      <article id="panaderia">
        <h2>Sitio de una panadería</h2>
        <img src="imagenes/panaderia.png" alt="Pantalla de inicio de la panadería La Espiga con dos panes dorados" width="320">
        <p>Una página para mostrar el pan del día y los horarios del local.</p>
        <p><a href="#arriba">Volver arriba</a></p>
      </article>

      <article id="agenda">
        <h2>Agenda de turnos</h2>
        <img src="imagenes/agenda.png" alt="Calendario con ocho turnos, dos de ellos ocupados" width="320">
        <p>Un calendario sencillo para reservar turnos en un consultorio.</p>
        <p><a href="#arriba">Volver arriba</a></p>
      </article>

      <article id="recetas">
        <h2>Blog de recetas</h2>
        <img src="imagenes/recetas.png" alt="Dos tarjetas de recetas: una ensalada fresca y una tarta de frutillas" width="320">
        <p>Un blog con recetas fáciles, cada una en su propia tarjeta.</p>
        <p><a href="#arriba">Volver arriba</a></p>
      </article>

      <p>Para saber cómo trabajo, leé <a href="sobre-mi.html#:~:text=Mi%20lema">mi lema en «Sobre mí»</a>.
        Si querés ver más recursos, visitá <a href="https://developer.mozilla.org/es/" target="_blank" rel="noopener">MDN en español</a>.</p>
    </main>

    <footer>
      <p><small>© 2026 Lucía Fernández. Sitio de ejemplo del curso.</small></p>
    </footer>
  </body>
</html>
```

## 🔍 Análisis paso a paso

1. **Poner un `id` a cada destino.** Cada proyecto es un `<article>` con un `id` único: `panaderia`, `agenda` y
   `recetas`. El `id` es el nombre del «ancla».
2. **Enlazar al ancla.** El índice usa `href="#panaderia"` (el `#` seguido del `id`). El navegador baja hasta ese elemento.
3. **Volver arriba.** El `header` lleva `id="arriba"` y cada proyecto tiene `<a href="#arriba">Volver arriba</a>`.
4. **Anclas hacia otra página.** Un enlace puede combinar archivo y ancla: `proyectos.html#recetas` abre la página de
   proyectos directamente en el blog de recetas.
5. **Fragmento de texto.** El enlace `sobre-mi.html#:~:text=Mi%20lema` pide al navegador que resalte la frase «Mi lema»
   al abrir «Sobre mí». El texto va **codificado** (el espacio es `%20`).
6. **Qué pasa si no se admite.** Los fragmentos de texto son una función del navegador, no de HTML. Si el navegador no
   la tiene (o el texto no existe), **el enlace funciona igual** y abre «Sobre mí» desde arriba.

> 📌 **Soporte.** Chrome 80, Firefox 131 y Safari 16.1 o posteriores.

## ✅ Resultado esperado

- Al hacer clic en «Agenda de turnos» del índice, la página **baja** hasta el proyecto de la agenda; «Volver arriba»
  regresa al principio.
- El enlace «mi lema en “Sobre mí”» abre `sobre-mi.html`; en un navegador compatible, la frase «Mi lema» aparece
  **resaltada**, y en uno que no lo admite se abre la página sin resaltar nada, **sin error**.
- Cada `id` aparece **una sola vez** en la página.

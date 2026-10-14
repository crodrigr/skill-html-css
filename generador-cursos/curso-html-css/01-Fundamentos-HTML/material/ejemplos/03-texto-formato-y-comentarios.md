# 📘 Ejemplo 03 — Texto, formato y comentarios

## 🧱 Situación inicial

Lucía escribió el texto de su página «Sobre mí» en un documento sin formato: nombre, quién es, lo que sabe hacer, cómo
trabaja y algunos detalles. Quiere marcarlo con HTML para que el navegador entienda su estructura.

## 💻 Código

La página completa `sobre-mi.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Sobre mí | Lucía Fernández</title>
  </head>
  <body>
    <header>
      <h1>Sobre mí</h1>
      <nav>
        <a href="index.html">Inicio</a> |
        <a href="sobre-mi.html">Sobre mí</a> |
        <a href="proyectos.html">Proyectos</a>
      </nav>
    </header>

    <main>
      <section>
        <h2>Quién soy</h2>
        <!-- Presentación breve: un párrafo por idea -->
        <p>Me llamo <strong>Lucía Fernández</strong> y soy desarrolladora web junior. Me gusta que cada página sea <em>clara</em>, rápida y útil para quien la visita.</p>
        <p>Aprendí HTML en un curso en línea y lo practiqué armando sitios para negocios de mi barrio.<br>
        Hoy sigo estudiando todos los días.</p>
        <p>Mi lema es <mark>escribir primero el contenido y después el estilo</mark>.</p>
      </section>

      <hr>

      <section>
        <h2>Lo que sé hacer</h2>
        <h3>Habilidades</h3>
        <ul>
          <li>Escribir documentos HTML bien estructurados</li>
          <li>Enlazar páginas entre sí</li>
          <li>Agregar imágenes y video</li>
        </ul>
        <h3>Cómo trabajo</h3>
        <ol>
          <li>Hablo con la persona que necesita el sitio.</li>
          <li>Escribo el contenido de cada página.</li>
          <li>Lo marco con HTML y lo reviso en el navegador.</li>
        </ol>
      </section>

      <section>
        <h2>Detalles</h2>
        <p>Mi sitio anterior tenía el precio <del>$5000</del> <ins>$4500</ins> por página.</p>
        <p>La fórmula del agua se escribe H<sub>2</sub>O y el cuadrado de 3 es 3<sup>2</sup>.</p>
        <p>Para marcar el título de una página uso la etiqueta <code>&lt;h1&gt;</code>.</p>
        <p><small>Última actualización: octubre de 2026.</small></p>
      </section>
    </main>

    <footer>
      <p><small>© 2026 Lucía Fernández. Sitio de ejemplo del curso.</small></p>
    </footer>
  </body>
</html>
```

## 🔍 Análisis paso a paso

1. **Un título principal.** `<h1>Sobre mí</h1>` en la cabecera: es el único `h1` de la página.
2. **Títulos de sección.** Cada tema lleva un `h2` («Quién soy», «Lo que sé hacer», «Detalles») y, dentro de «Lo que sé
   hacer», dos `h3`. No se salta ningún nivel.
3. **Párrafos.** Cada idea va en su propio `<p>`. En el segundo párrafo, `<br>` parte la línea sin abrir un párrafo nuevo.
4. **Formato con significado.** `<strong>` para su nombre (importante), `<em>` para «clara» (énfasis) y `<mark>` para
   resaltar su lema.
5. **Listas.** Las habilidades no tienen orden: `<ul>` con un `<li>` por ítem. Los pasos de su trabajo sí lo tienen:
   `<ol>`.
6. **Separador.** `<hr>` marca un cambio de tema entre «Quién soy» y «Lo que sé hacer».
7. **Detalles de formato.** `<del>` y `<ins>` muestran un precio tachado y el nuevo; `<sub>` y `<sup>` escriben H₂O y
   3²; `<code>` muestra una etiqueta; y `<small>` marca la letra chica. Para que `<h1>` se vea como texto y no se
   interprete, se escribe `&lt;h1&gt;`.
8. **Comentarios.** `<!-- Presentación breve: un párrafo por idea -->` deja una nota para quien lea el código; el
   navegador no la muestra.

## ✅ Resultado esperado

- Un título grande «Sobre mí», y debajo la navegación con tres enlaces.
- El nombre «Lucía Fernández» en **negrita**, «clara» en *cursiva* y la frase «escribir primero el contenido y después el
  estilo» **resaltada**.
- Una línea horizontal entre «Quién soy» y «Lo que sé hacer».
- Una lista con viñetas (tres habilidades) y una lista **numerada** (tres pasos).
- El precio `$5000` tachado seguido de `$4500`, «H₂O» con el 2 más abajo y «3²» con el 2 más arriba, y la palabra
  `<h1>` en letra de ancho fijo.
- **No se ve ningún comentario** en la página.

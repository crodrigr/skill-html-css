# 📘 Ejemplo 06 — El formulario de contacto

## 🧱 Situación inicial

Lucía junta todo lo aprendido en la **página de contacto** de su sitio. Quiere pedir: el nombre, el correo, la cantidad de
páginas que necesita (con un valor sugerido de 3), el tipo de sitio (personal, negocio o blog) y si quiere recibir novedades.
Todo con **datos de prueba**: el formulario no se envía a ningún servidor.

## 💻 Código

La página completa `contacto.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Contacto | Lucía Fernández</title>
  </head>
  <body>
    <header>
      <h1>Contacto</h1>
      <nav>
        <a href="index.html">Inicio</a> |
        <a href="sobre-mi.html">Sobre mí</a> |
        <a href="proyectos.html">Proyectos</a> |
        <a href="servicios.html">Servicios</a> |
        <a href="contacto.html">Contacto</a>
      </nav>
    </header>

    <main>
      <p>Completá el formulario para contarme qué sitio necesitás. Usá datos de prueba: este formulario no se envía a ningún servidor.</p>

      <!-- method="get" y sin action: al enviar, la página se recarga y los datos aparecen en la dirección -->
      <form method="get">
        <p>
          <label for="nombre">Nombre</label>
          <input type="text" id="nombre" name="nombre">
        </p>
        <p>
          <label for="correo">Correo</label>
          <input type="email" id="correo" name="correo">
        </p>
        <p>
          <label for="paginas">Cantidad de páginas</label>
          <input type="number" id="paginas" name="paginas" value="3">
        </p>
        <p>Tipo de sitio:</p>
        <p>
          <input type="radio" id="tipo-personal" name="tipo" value="personal">
          <label for="tipo-personal">Personal</label>
          <input type="radio" id="tipo-negocio" name="tipo" value="negocio">
          <label for="tipo-negocio">Negocio</label>
          <input type="radio" id="tipo-blog" name="tipo" value="blog">
          <label for="tipo-blog">Blog</label>
        </p>
        <p>
          <input type="checkbox" id="novedades" name="novedades" value="si">
          <label for="novedades">Quiero recibir novedades</label>
        </p>
        <p>
          <input type="submit" value="Enviar">
        </p>
      </form>
    </main>

    <footer>
      <p><small>© 2026 Lucía Fernández. Sitio de ejemplo del curso.</small></p>
    </footer>
  </body>
</html>
```

## 🔍 Análisis paso a paso

1. **Elegir un tipo para cada dato.** Nombre → `text`; correo → `email`; cantidad de páginas → `number`; tipo de sitio →
   `radio` (una sola opción entre tres); novedades → `checkbox` (sí o no).
2. **Un `name` para cada dato.** `nombre`, `correo`, `paginas`, `tipo` y `novedades`. Los tres `radio` comparten `name="tipo"`.
3. **Un valor inicial.** `value="3"` en el número: el campo aparece con un 3.
4. **El `value` de las opciones y la casilla.** Son lo que **se envía** si están marcadas: `personal`, `negocio`, `blog` y `si`.
5. **Una etiqueta para cada campo.** Cada `<label for="…">` apunta al `id` de su campo. En las opciones y la casilla, la etiqueta
   va **después** del campo.
6. **El botón.** `<input type="submit" value="Enviar">`.
7. **Un comentario.** Lucía deja una nota que recuerda que el formulario usa `method="get"` y no tiene `action`.
8. **Probar.** Escribe «Ana Pérez» y `ana@example.com`, cambia las páginas a 5, elige «Negocio», marca «Quiero recibir
   novedades» y envía.
9. **Mirar la dirección.** Queda así: `contacto.html?nombre=Ana+P%C3%A9rez&correo=ana%40example.com&paginas=5&tipo=negocio&novedades=si`.
   El espacio se envía como `+` y la «é», como `%C3%A9`.
10. **Probar sin marcar.** Si no elige ningún tipo ni marca la casilla y deja las páginas en 3, la dirección termina en
    `?nombre=Ana&correo=ana%40example.com&paginas=3`: **`tipo` y `novedades` no viajan**.

## ✅ Resultado esperado

- Una página con el título «Contacto», un texto de ayuda y un formulario con: nombre, correo, cantidad de páginas (con un 3),
  tres opciones («Personal», «Negocio», «Blog»), una casilla «Quiero recibir novedades» y un botón «Enviar».
- Al hacer clic en el texto de una opción o de la casilla, **se marca** el campo.
- Al enviar con los datos del paso 8, la dirección termina en
  `?nombre=Ana+P%C3%A9rez&correo=ana%40example.com&paginas=5&tipo=negocio&novedades=si`.
- Con un correo sin forma de correo, el navegador **no envía** el formulario.
- Ningún dato sale de tu computadora.

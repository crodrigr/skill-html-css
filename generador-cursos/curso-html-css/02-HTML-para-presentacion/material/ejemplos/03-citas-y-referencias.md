# 📘 Ejemplo 03 — Citas y referencias

## 🧱 Situación inicial

Lucía recibió dos comentarios de clientas y quiere publicarlos en su página de servicios. Uno es largo, de Marta Gómez, de
la panadería La Espiga. El otro es una frase corta de otra clienta, Inés, que quiere incluir dentro de una oración suya.
Además, quiere recomendar un artículo llamado «Cómo elegir un sitio web».

## 💻 Código

La sección de testimonios (de `servicios.html`):

```html
<section>
  <h2>Testimonios</h2>
  <blockquote cite="https://lucia-fernandez.example/testimonios/marta">
    <p>Lucía armó el sitio de mi panadería en una semana y quedó mejor de lo que imaginaba.</p>
  </blockquote>
  <p>— Marta Gómez, panadería La Espiga</p>

  <p>Otra clienta contó que Lucía <q cite="https://lucia-fernandez.example/testimonios/ines">explica todo con paciencia</q>.</p>

  <p>Para elegir bien el tipo de sitio, leé <cite>Cómo elegir un sitio web</cite>.</p>
</section>
```

## 🔍 Análisis paso a paso

1. **Cita extensa.** El comentario de Marta es largo y va aparte: usa `<blockquote>` con un párrafo adentro. El navegador
   lo muestra con **sangría**.
2. **La fuente.** Al `<blockquote>` le agrega `cite="https://lucia-fernandez.example/testimonios/marta"`: la dirección de
   donde sale la cita. **No se ve** en la página; es información para quien lea el código.
3. **La atribución visible.** El nombre de quien lo dijo va **fuera** del `<blockquote>`, en un párrafo siguiente:
   «— Marta Gómez, panadería La Espiga».
4. **Cita corta.** La frase de Inés va **dentro de una oración**: usa `<q>`. **No escribe las comillas**: el navegador las
   agrega solo. También lleva su atributo `cite`.
5. **Una referencia.** El artículo «Cómo elegir un sitio web» es una **obra con título**: va entre `<cite>`, que el
   navegador muestra en cursiva.
6. **Qué no va en `<cite>`.** El nombre de Marta **no** va entre `<cite>`: esa etiqueta es para títulos de obras, no para
   personas.

## ✅ Resultado esperado

- Un párrafo **con sangría** que dice «Lucía armó el sitio de mi panadería en una semana y quedó mejor de lo que imaginaba.»
- Debajo, en una línea común, «— Marta Gómez, panadería La Espiga».
- Una oración con la frase «explica todo con paciencia» **entre comillas** (puestas por el navegador).
- El título «Cómo elegir un sitio web» **en cursiva**.
- Las direcciones de `cite` **no se ven** en la página.

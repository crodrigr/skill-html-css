# 📘 Ejemplo 05 — Listas con estilo

> 🕐 **Sesión 1** · 🎓 **Resultados de aprendizaje:** RA-5

## 🧱 Situación inicial

La lista de comprobación del artículo de Lucía se ve con las viñetas habituales. Ella quiere cambiar el tipo de viñeta o de numeración, decidir si la viñeta queda dentro o
fuera del texto, quitarlas para un menú y separar los elementos. Lo prueba en `listas.html`.

## 💻 Código

El contenido de `listas.html` (dentro de `<main>`):

```html
<h2>Tipo de viñeta</h2>
<ul class="cuadrados">
  <li>Cuadrados</li>
  <li>En lugar de círculos</li>
</ul>
<ul class="circulos">
  <li>Círculos vacíos</li>
  <li>Para un segundo nivel</li>
</ul>
<ul class="sin-vinetas">
  <li>Sin viñetas</li>
  <li>Ideal para un menú</li>
</ul>

<h2>Tipo de numeración</h2>
<ol class="romanos">
  <li>Primero</li>
  <li>Segundo</li>
  <li>Tercero</li>
</ol>
<ol class="letras">
  <li>Primero</li>
  <li>Segundo</li>
  <li>Tercero</li>
</ol>

<h2>Posición de la viñeta</h2>
<ul class="afuera">
  <li>La viñeta queda afuera, y el texto largo de este elemento sigue alineado al volver de renglón en una pantalla angosta.</li>
</ul>
<ul class="adentro">
  <li>La viñeta queda adentro, y el texto largo de este elemento vuelve de renglón por debajo de la viñeta en una pantalla angosta.</li>
</ul>

<h2>Espaciado</h2>
<ul class="espaciada">
  <li>Un elemento</li>
  <li>Otro elemento</li>
  <li>Un tercero</li>
</ul>
```

La hoja `css/listas.css`:

```css
/* Tipo de viñeta */
.cuadrados {
  list-style-type: square;
}

.circulos {
  list-style-type: circle;
}

/* Sin viñetas: también se quita la sangría que trae la lista */
.sin-vinetas {
  list-style-type: none;
  padding-left: 0;
}

/* Tipo de numeración */
.romanos {
  list-style-type: upper-roman;
}

.letras {
  list-style-type: lower-alpha;
}

/* Posición de la viñeta: afuera es el valor por defecto */
.afuera {
  list-style-position: outside;
}

.adentro {
  list-style-position: inside;
}

/* Espacio entre elementos */
.espaciada li {
  margin-bottom: 0.5rem;
}
```

## 🔍 Análisis paso a paso

1. **`list-style-type`.** Elige la viñeta o la numeración. En listas no ordenadas: `disc` (círculo lleno, el valor habitual), `circle` (círculo vacío), `square`
   (cuadrado) y `none` (sin viñeta). En listas ordenadas: `decimal` (1, 2, 3), `upper-roman` (I, II, III), `lower-alpha` (a, b, c), entre otras.
2. **Sin viñetas.** `none` quita la viñeta, pero la lista conserva su sangría izquierda. Por eso `.sin-vinetas` también pone `padding-left: 0`: el navegador da a `ul` y `ol` un
   relleno izquierdo de **40px** por defecto.
3. **`list-style-position`.** Con `outside` (el valor inicial) la viñeta queda **fuera** de la caja del elemento, y si el texto ocupa varios renglones, todos se alinean. Con
   `inside` la viñeta forma parte del contenido: el segundo renglón empieza **debajo de la viñeta**.
4. **Espaciado.** `.espaciada li { margin-bottom: 0.5rem; }` separa los elementos con `8px` (la mitad del tamaño de la letra base, `16px`).
5. **Abreviatura.** `list-style` junta tipo, posición (y una imagen) en una sola declaración, por ejemplo `list-style: square inside;`. En esta clase usamos las propiedades
   por separado para que cada una se entienda.
6. **Qué no cambia.** `list-style-type` cambia solo la viñeta o la numeración; la estructura (`ul`, `ol`, `li`) sigue siendo la de la Clase 02.

## ✅ Resultado esperado

| Clase | Propiedad | Valor calculado |
|---|---|---|
| `.cuadrados` | `list-style-type` | `square` |
| `.circulos` | `list-style-type` | `circle` |
| `.sin-vinetas` | `list-style-type` / `padding-left` | `none` / `0px` |
| `.romanos` | `list-style-type` | `upper-roman` (I., II., III.) |
| `.letras` | `list-style-type` | `lower-alpha` (a., b., c.) |
| `.afuera` / `.adentro` | `list-style-position` | `outside` / `inside` |
| `.espaciada li` | `margin-bottom` | `8px` |
| `.cuadrados` (sin cambios) | `padding-left` | `40px` |

- La lista `.sin-vinetas` se ve sin viñetas y pegada al borde izquierdo.
- En `.adentro`, cuando el texto vuelve de renglón, queda debajo de la viñeta; en `.afuera`, alineado con el texto del primer renglón.

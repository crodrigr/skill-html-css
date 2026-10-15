# 📘 Ejemplo 04 — Combinadores

## 🧱 Situación inicial

Lucía quiere dar estilo a elementos según **dónde están**: los enlaces del menú, los elementos de una lista, el párrafo que presenta
cada sección y los párrafos que siguen a un título. No quiere agregar una clase a cada uno. Usa **combinadores** en la página
`laboratorio-combinadores.html`.

## 💻 Código

El menú y el comienzo de la página (de `laboratorio.html`):

```html
<nav>
  <a href="index.html">Inicio</a> |
  <a href="sobre-mi.html">Sobre mí</a> |
  <a href="proyectos.html" class="menu__enlace menu__enlace--activo">Proyectos</a> |
  <a href="servicios.html">Servicios</a> |
  <a href="contacto.html">Contacto</a>
</nav>
```

```html
<h2>Enlaces</h2>
<p class="destacado">Esta página reúne todo lo que vamos a seleccionar.</p>
<p>Los enlaces de ejemplo:</p>
<ul class="enlaces">
  <li><a href="https://developer.mozilla.org/es/" target="_blank" rel="noopener">MDN en español</a></li>
  <li><a href="https://lucia-fernandez.example/cv.pdf">Mi currículum (PDF)</a></li>
  <li><a href="proyectos.html">Mis proyectos</a></li>
  <li><a href="#contacto">Ir al contacto</a></li>
</ul>
```

La hoja `css/combinadores.css`:

```css
/* Descendiente (espacio): los enlaces que están dentro de nav, a cualquier profundidad */
nav a {
  color: #1e3a8a;
}

/* Hijo directo (>): los li que son hijos directos de una lista no ordenada */
ul > li {
  background-color: #dbeafe;
}

/* Hermano adyacente (+): el párrafo que va inmediatamente después de un h2 */
h2 + p {
  color: #16a34a;
}

/* Hermano general (~): todos los párrafos que siguen a un h2 con el mismo padre */
h2 ~ p {
  background-color: #fef3c7;
}
```

## 🔍 Análisis paso a paso

1. **Descendiente (espacio).** `nav a` elige los enlaces que están **dentro** de `nav`, a cualquier profundidad: son **5**, los del menú.
   Los demás enlaces de la página (en la lista y en las tarjetas) no están dentro de un `nav` y no se eligen.
2. **Hijo directo (`>`).** `ul > li` elige los `li` que son **hijos directos** de un `ul`: son **5** (4 de la lista de enlaces y 1 de la nota).
   Los `li` de la lista numerada (`ol`) no se eligen, aunque sean listas: el padre es un `ol`, no un `ul`.
3. **Hermano adyacente (`+`).** `h2 + p` elige el párrafo que va **inmediatamente después** de un `h2`, si comparten padre: es **1**, el párrafo
   de presentación (`.destacado`). El segundo párrafo ya no va justo después del `h2`.
4. **Hermano general (`~`).** `h2 ~ p` elige **todos** los párrafos hermanos que vienen después de un `h2`, aunque no sean inmediatos: son **2**
   (el de presentación y «Los enlaces de ejemplo:»). Los párrafos del formulario no se eligen: su padre es el `form`, no `main`.
5. **Elegir bien.** Para el menú, `nav a` es suficiente. Para evitar que llegue a enlaces más profundos, se podría usar `nav > a`.
6. **Cuidado con la longitud.** Cada selector que se une suma especificidad: `nav a` vale `0-0-2`, más que `a` solo.

## ✅ Resultado esperado

| Selector | Elementos que elige |
|---|---|
| `nav a` | 5 |
| `ul > li` | 5 |
| `h2 + p` | 1 |
| `h2 ~ p` | 2 |

- Los cinco enlaces del menú se ven en **azul oscuro** (`rgb(30, 58, 138)`).
- Los cinco `li` de listas no ordenadas tienen fondo **celeste**; los de la lista numerada, no.
- El párrafo de presentación se ve en **verde** (`rgb(22, 163, 74)`) y con fondo **crema**; el segundo párrafo tiene fondo crema, pero su texto no cambia.

# 📘 Ejemplo 05 — Selectores lógicos

## 🧱 Situación inicial

Lucía repite selectores: «los títulos de primer, segundo y tercer nivel», «los elementos de cualquier lista», «los enlaces que no son
externos» y «las tarjetas que tienen una imagen». Quiere escribirlos de forma más corta y entender cómo afectan a la especificidad. Lo
prueba en `laboratorio-logicos.html` con los **selectores lógicos**.

## 💻 Código

Los enlaces, las listas y las tarjetas (de `laboratorio.html`):

```html
<ul class="enlaces">
  <li><a href="https://developer.mozilla.org/es/" target="_blank" rel="noopener">MDN en español</a></li>
  <li><a href="https://lucia-fernandez.example/cv.pdf">Mi currículum (PDF)</a></li>
  <li><a href="proyectos.html">Mis proyectos</a></li>
  <li><a href="#contacto">Ir al contacto</a></li>
</ul>
```

```html
<article class="tarjeta tarjeta--destacada">
  <img class="tarjeta__imagen" src="imagenes/panaderia.png" alt="Pantalla de inicio de la panadería La Espiga" width="160">
  <h3 class="tarjeta__titulo tarjeta__titulo--grande">Sitio de una panadería</h3>
  <p class="tarjeta__texto">Una página para mostrar el pan del día.</p>
  <a class="tarjeta__enlace" href="proyectos.html#panaderia">Ver proyecto</a>
</article>
<article class="tarjeta">
  <img class="tarjeta__imagen" src="imagenes/agenda.png" alt="Calendario con ocho turnos, dos de ellos ocupados" width="160">
  <h3 class="tarjeta__titulo">Agenda de turnos</h3>
  <p class="tarjeta__texto">Un calendario para reservar turnos.</p>
  <a class="tarjeta__enlace" href="proyectos.html#agenda">Ver proyecto</a>
</article>
<article class="tarjeta">
  <h3 class="tarjeta__titulo">Blog de recetas</h3>
  <p class="tarjeta__texto">Un blog con recetas fáciles.</p>
  <a class="tarjeta__enlace" href="proyectos.html#recetas">Ver proyecto</a>
</article>
```

La hoja `css/logicos.css`:

```css
/* :is(): una sola regla para varios selectores */
:is(h1, h2, h3) {
  color: #1e3a8a;
}

/* :is() suma la especificidad de su argumento más específico: vale más que li */
:is(ul, ol) li {
  background-color: #dbeafe;
}

li {
  background-color: #fef3c7;
}

/* :where() siempre vale cero: li, que viene después, lo anula */
:where(ul, ol) li {
  color: #16a34a;
}

li {
  color: #dc2626;
}

/* :not(): todos los enlaces menos los que empiezan con https */
a:not([href^="https"]) {
  background-color: #e0f2fe;
}

/* :has(): los artículos que contienen una imagen */
article:has(img) {
  border-style: solid;
  border-width: 2px;
  border-color: #16a34a;
}
```

## 🔍 Análisis paso a paso

1. **`:is()` agrupa.** `:is(h1, h2, h3)` reemplaza a `h1, h2, h3`: elige **9** títulos (1 `h1`, 5 `h2` y 3 `h3`), todos en azul oscuro.
2. **`:is()` suma especificidad.** `:is(ul, ol) li` vale como su argumento más específico (una etiqueta) más la etiqueta `li`: `0-0-2`. Por eso su
   fondo celeste le gana a `li { background-color: ... }`, que vale `0-0-1`, **aunque `li` venga después**.
3. **`:where()` no suma nada.** `:where(ul, ol) li` vale solo `0-0-1`, la del `li`: es igual a la regla `li` posterior, y gana la **última**.
   Por eso el verde de `:where(...)` pierde frente al rojo de `li`.
4. **Elegir entre los dos.** Con `:is()` la regla gana con más fuerza; con `:where()` queda como un estilo «de base», fácil de anular.
5. **`:not()` excluye.** `a:not([href^="https"])` elige los enlaces cuyo `href` **no** empieza con `https`: **11** de los 13 (todos menos los dos externos).
6. **`:has()` mira el contenido.** `article:has(img)` elige los `article` que **contienen** una imagen: **2** de las 3 tarjetas (la del blog no
   tiene imagen).
7. **Compatibilidad.** `:has()` es reciente (Chrome y Edge 105, Firefox 121 y Safari 15.4, y disponible en todos desde diciembre de 2023). Si
   hubiera que dar soporte a navegadores más antiguos, la alternativa es agregar una clase en el HTML (por ejemplo, `tarjeta--con-imagen`).

## ✅ Resultado esperado

| Selector | Elementos que elige |
|---|---|
| `:is(h1, h2, h3)` | 9 |
| `:where(ul, ol) li` | 8 (4 + 3 + 1) |
| `a:not([href^="https"])` | 11 |
| `article:has(img)` | 2 |

- Todos los títulos se ven en **azul oscuro** (`rgb(30, 58, 138)`).
- Todos los `li` tienen fondo **celeste** (`rgb(219, 234, 254)`: gana `:is()`) y texto **rojo** (`rgb(220, 38, 38)`: gana la regla `li`, posterior).
- Los 11 enlaces que no son externos tienen fondo celeste claro (`rgb(224, 242, 254)`); los dos externos, no.
- Las dos tarjetas con imagen tienen un borde **verde** (`rgb(22, 163, 74)`); la tarjeta del blog no tiene borde.

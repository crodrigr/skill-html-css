# 📘 Ejemplo 08 — Escribir y organizar reglas

## 🧱 Situación inicial

La hoja de estilos de Lucía creció a los tropezones: tiene reglas repetidas, sin comentarios ni orden, y un selector larguísimo que no logra
sobrescribir. Quiere **reorganizarla** sin que la página cambie de aspecto. Compara las dos versiones, en `laboratorio-reglas-antes.html` y
`laboratorio-reglas-despues.html`.

## 💻 Código

La tarjeta de la página (de `laboratorio.html`):

```html
<article class="tarjeta tarjeta--destacada">
  <img class="tarjeta__imagen" src="imagenes/panaderia.png" alt="Pantalla de inicio de la panadería La Espiga" width="160">
  <h3 class="tarjeta__titulo tarjeta__titulo--grande">Sitio de una panadería</h3>
  <p class="tarjeta__texto">Una página para mostrar el pan del día.</p>
  <a class="tarjeta__enlace" href="proyectos.html#panaderia">Ver proyecto</a>
</article>
```

La hoja desordenada, `css/reglas-desordenadas.css`:

```css
main article.tarjeta h3.tarjeta__titulo {
  color: #1e3a8a;
}
a {
  color: #2563eb;
}
.tarjeta__titulo {
  color: #dc2626;
}
h2 {
  color: #1e3a8a;
}
.destacado {
  background-color: #fef3c7;
}
h2 {
  background-color: #eff6ff;
}
ul > li {
  color: #1f2937;
}
li {
  color: #1f2937;
}
```

La misma hoja reorganizada, `css/reglas.css`:

```css
/* Enlaces */
a {
  color: #2563eb;
}

/* Títulos: una sola regla para las dos propiedades */
h2 {
  color: #1e3a8a;
  background-color: #eff6ff;
}

/* Listas */
li {
  color: #1f2937;
}

/* Clases y componentes: selectores simples, con la especificidad justa */
.destacado {
  background-color: #fef3c7;
}

.tarjeta__titulo {
  color: #1e3a8a;
}
```

## 🔍 Análisis paso a paso

1. **Encontrar los problemas.** La hoja desordenada tiene: dos reglas para `h2`; dos reglas casi iguales para los `li`; sin comentarios; y un selector
   larguísimo, `main article.tarjeta h3.tarjeta__titulo`, que además se contradice con `.tarjeta__titulo`.
2. **La contradicción.** El título tiene dos reglas de color: la larga (azul oscuro) y `.tarjeta__titulo` (rojo, más abajo). La larga vale `0-2-3` y la
   corta, `0-1-0`: **gana la larga**, aunque la corta venga después. Por eso el título se ve azul oscuro, no rojo.
3. **Elegir qué se quiere.** Lucía quiere el azul oscuro. Entonces borra la regla roja, que nunca se aplicaba, y deja la clase simple.
4. **Simplificar el selector.** `main article.tarjeta h3.tarjeta__titulo` pasa a ser `.tarjeta__titulo`: un solo selector de clase (BEM), que vale `0-1-0`.
5. **Agrupar.** Las dos reglas de `h2` se juntan en una sola, con sus dos declaraciones.
6. **Quitar lo repetido.** La regla `ul > li` repetía lo mismo que `li`: alcanza con `li`.
7. **Ordenar y comentar.** La hoja nueva empieza por lo general (enlaces, títulos, listas) y termina con las clases y los componentes. Cada bloque tiene su comentario.
8. **Comprobar.** Lucía lee los estilos calculados de los mismos elementos en las dos páginas.

## ✅ Resultado esperado

Los estilos calculados son **los mismos** con la hoja desordenada y con la reorganizada:

| Elemento | Estilo |
|---|---|
| Enlaces (`a`) | Texto azul (`rgb(37, 99, 235)`) |
| Títulos (`h2`) | Texto azul oscuro (`rgb(30, 58, 138)`) y fondo muy claro (`rgb(239, 246, 255)`) |
| `.destacado` | Fondo crema (`rgb(254, 243, 199)`) |
| Título de tarjeta (`h3.tarjeta__titulo`) | Texto azul oscuro (`rgb(30, 58, 138)`) |
| Elementos de lista (`li`) | Texto gris oscuro (`rgb(31, 41, 55)`) |

- La hoja reorganizada tiene **menos reglas** (5 en lugar de 8), sin selectores largos, con comentarios y sin contradicciones.
- La página **se ve igual** que antes.

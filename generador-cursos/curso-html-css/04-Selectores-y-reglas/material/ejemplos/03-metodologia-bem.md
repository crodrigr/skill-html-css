# 📘 Ejemplo 03 — La metodología BEM

## 🧱 Situación inicial

La página de proyectos de Lucía tiene tres **tarjetas**: cada una con una imagen (la tercera no), un título, un texto y un enlace. Una de
ellas es la destacada, y su título es más grande. Lucía quiere nombrar las clases de forma ordenada, para saber siempre a qué componente
pertenece cada una y poder modificar una sin tocar las otras. Usa **BEM**, con la variante de dos guiones para los modificadores.

## 💻 Código

Las tres tarjetas (de `laboratorio.html`):

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

La hoja `css/bem.css`:

```css
/* Bloque: el componente completo */
.tarjeta {
  background-color: #ffffff;
  border-style: solid;
  border-width: 1px;
  border-color: #cbd5e1;
}

/* Elementos: las partes del bloque */
.tarjeta__imagen {
  border-style: solid;
  border-width: 2px;
  border-color: #bfdbfe;
}

.tarjeta__titulo {
  color: #1e3a8a;
}

.tarjeta__texto {
  color: #1f2937;
}

.tarjeta__enlace {
  color: #2563eb;
}

/* Modificador del bloque: una variante de toda la tarjeta */
.tarjeta--destacada {
  background-color: #fef3c7;
  border-color: #f59e0b;
}

/* Modificador de un elemento: una variante de una sola parte */
.tarjeta__titulo--grande {
  font-size: 28px;
}
```

## 🔍 Análisis paso a paso

1. **Encontrar el bloque.** La tarjeta es un componente que tiene sentido solo: es el **bloque**. Se llama `tarjeta`.
2. **Nombrar los elementos.** Cada parte lleva el nombre del bloque, **dos guiones bajos** y su propio nombre: `tarjeta__imagen`,
   `tarjeta__titulo`, `tarjeta__texto` y `tarjeta__enlace`. No hay elementos de elementos: aunque el título estuviera dentro de otra etiqueta,
   seguiría siendo `tarjeta__titulo`.
3. **Escribir los modificadores.** La tarjeta destacada lleva `tarjeta--destacada` (modifica al **bloque**) y su título lleva
   `tarjeta__titulo--grande` (modifica a un **elemento**). Los dos nombres usan dos guiones.
4. **Las dos clases a la vez.** En el HTML, la tarjeta destacada tiene `class="tarjeta tarjeta--destacada"`: la clase del bloque (que da lo
   común) y la del modificador (que cambia lo que hace falta).
5. **Una clase, un selector.** Todas las reglas de `bem.css` usan **un solo selector de clase**. Por eso todas valen lo mismo y es fácil
   predecir cuál gana.
6. **El modificador va después del bloque.** `.tarjeta--destacada` está debajo de `.tarjeta` en la hoja: al valer lo mismo, gana la última y
   cambia el fondo y el color del borde.
7. **Un detalle sobre la convención.** La documentación oficial de BEM escribe los modificadores con **un guion bajo**
   (`tarjeta_destacada`, `tarjeta__titulo_grande`). Lo importante es usar **una** forma, siempre igual, en todo el proyecto.
8. **Comprobar.** Lucía cuenta los elementos de cada clase y mira los estilos calculados.

## ✅ Resultado esperado

| Clase | Elementos |
|---|---|
| `.tarjeta` | 3 |
| `.tarjeta__titulo` | 3 |
| `.tarjeta__imagen` | 2 (la tercera tarjeta no tiene imagen) |
| `.tarjeta--destacada` | 1 |
| `.tarjeta__titulo--grande` | 1 |

- La tarjeta destacada tiene fondo **crema** (`rgb(254, 243, 199)`) y borde **naranja** (`rgb(245, 158, 11)`); las otras dos tienen fondo blanco y
  borde gris celeste (`rgb(203, 213, 225)`).
- El título de la tarjeta destacada se ve **más grande** (`28px`); los otros títulos mantienen el tamaño habitual de un `h3` (`18.72px`).
- Todos los títulos se ven en azul oscuro (`rgb(30, 58, 138)`).

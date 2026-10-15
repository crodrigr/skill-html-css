# 📘 Ejemplo 09 — Elegir la unidad

> 🎓 **Resultados de aprendizaje:** RA-7

## 🧱 Situación inicial

Lucía ya conoce todas las unidades y tiene que escribir la hoja de una página. En lugar de elegir una al azar, usa una **tabla de criterios**. La aplica en `elegir.html`, con la ventana fijada en `1000 × 600`.

## 💻 Código

El contenido de `elegir.html` (dentro de `<main>`):

```html
<section class="portada">
  <h2>Portada</h2>
  <p>Una sección que ocupa la mitad de la ventana.</p>
</section>

<section class="contenedor">
  <h2>Contenedor</h2>
  <p class="parrafo">Un párrafo cómodo de leer no pasa de unos 65 caracteres por línea: así el ojo no se pierde al volver al comienzo del renglón siguiente.</p>
  <p class="nota">Una nota con un borde fino y un relleno que acompaña a la letra.</p>
  <div class="bloque">Un bloque que muestra cuatro líneas de texto de alto, tenga el texto que tenga, sin recortar la última línea.</div>
</section>
```

La hoja `css/elegir.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* El texto: rem, para respetar el tamaño que cada persona elige en su navegador */
body {
  font-size: 1rem;
  line-height: 1.6;
}

/* Una sección que ocupa la mitad de la ventana: vh */
.portada {
  min-height: 50vh;
  background-color: #eff6ff;
}

/* Un contenedor flexible, con un tope razonable: % y rem */
.contenedor {
  width: 80%;
  max-width: 40rem;
}

/* Un ancho de lectura: ch */
.parrafo {
  max-width: 65ch;
}

/* Un borde fino fijo en px; el relleno acompaña a la letra con em */
.nota {
  border: 1px solid #1e3a8a;
  padding: 1em;
}

/* Un alto en líneas de texto: lh */
.bloque {
  height: 4lh;
  overflow: hidden;
  background-color: #dbeafe;
}
```

## 🔍 Análisis paso a paso

La tabla de criterios que sigue Lucía:

| Situación | Unidad | Por qué |
|---|---|---|
| Tamaño del texto | `rem` | Respeta el tamaño que cada persona elige en su navegador |
| Espacio que acompaña a la letra de un componente | `em` | Crece con el texto del componente |
| Un borde fino | `px` | Debe ser fijo: `1px` es `1px` |
| Ancho de un contenedor flexible | `%` | Acompaña al contenedor |
| Un tope razonable para ese ancho | `rem` o `ch` | No crece sin límite |
| Ancho de lectura de un párrafo | `ch` | Se mide en caracteres |
| Alto de un bloque de texto | `lh` | Muestra un número exacto de líneas |
| Una sección según la ventana | `vh` o `vw` | Sigue a la ventana |

1. **Texto.** `body` usa `font-size: 1rem` y `line-height: 1.6` (sin unidad).
2. **Sección según la ventana.** `.portada` pide `min-height: 50vh`: con la ventana de `600px` de alto, mide `300px`.
3. **Contenedor flexible con tope.** `.contenedor` pide `width: 80%` y `max-width: 40rem`. El `80%` del ancho disponible (`969px`: la ventana de `1000px` menos los márgenes del `body` y la barra de desplazamiento de la página) sería `775.2px`, pero el tope de `40rem` (`640px`) gana: mide `640px`.
4. **Ancho de lectura.** `.parrafo` pide `max-width: 65ch`: no pasa de unos 65 caracteres por línea (`578.4px` con la tipografía de la prueba).
5. **Borde y relleno.** `.nota` usa `1px` para el borde (fijo) y `1em` para el relleno (acompaña a la letra): `16px`.
6. **Alto en líneas.** `.bloque` pide `height: 4lh`: cuatro líneas de `25.6px`, unos `102.4px`, y `overflow: hidden` recorta lo que sobre.
7. **Combinar unidades.** A veces hace falta mezclar, por ejemplo «el `100%` del ancho menos `20px`». CSS tiene la función `calc()` para eso: se menciona para que sepas que existe, pero no se practica en esta clase.
8. **Regla práctica.** Fijo y pequeño: `px`. Texto y espacios generales: `rem`. Acompañar a la letra de un componente: `em`. Acompañar al contenedor: `%`. Seguir a la ventana: `vw` y `vh`.

## ✅ Resultado esperado

| Clase | Escrito | Valor calculado (ventana `1000 × 600`) |
|---|---|---|
| `body` | `font-size: 1rem`, `line-height: 1.6` | `16px` y `25.6px` |
| `.portada` | `min-height: 50vh` | `300px` |
| `.contenedor` | `width: 80%`, `max-width: 40rem` | `640px` (gana el tope; el `80%` sería `775.2px`) |
| `.parrafo` | `max-width: 65ch` | `578.4px` (65 veces el ancho del «0») |
| `.nota` | `padding: 1em` | `16px` |
| `.bloque` | `height: 4lh` | `102.4px` (4 × `25.6px`) |

- El párrafo se ve más angosto que el contenedor, y la portada ocupa la mitad de la altura de la ventana.

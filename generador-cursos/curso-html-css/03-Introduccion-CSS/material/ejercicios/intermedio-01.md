# 🟡 Intermedio 01 — Variables y formas de escribir un color

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-6, RA-7

## 🧱 Estado inicial

Abrí [`intermedio-01.html`](../recursos/portafolio-inicial/intermedio-01.html) y su hoja
[`intermedio-01.css`](../recursos/portafolio-inicial/css/intermedio-01.css). La hoja de Mateo **repite** tres colores:

| Color | Dónde se repite |
|---|---|
| `#111827` (gris oscuro) | texto del `body`, fondo del `h1` y texto de `.destacado` |
| `#16a34a` (verde) | `h2`, enlaces, borde de `.destacado` y fondo de `.cita` |
| `#fef3c7` (crema) | fondo del `body` y texto del `h1` |

El fondo de `.cita` es un verde **sólido**, y Mateo lo quiere semitransparente.

## 🛠️ Proceso esperado

**Parte A — Variables.**

1. Definí en `:root` tres variables: `--color-oscuro`, `--color-verde` y `--color-crema`, con los colores de la tabla.
2. Reemplazá **todos** los colores repetidos por `var(--…)`. El blanco `#ffffff` queda como está.

**Parte B — Formas de escribir un color.**

1. Escribí el verde `#16a34a` de **cuatro formas**: hexadecimal, `rgb()`, `hsl()` y `rgb()` con un 50% de transparencia.
2. Comprobá en el navegador (con las herramientas, probando en vivo) el color calculado de cada forma y anotalo.

**Parte C — Transparencia.**

1. Cambiá el fondo de `.cita` por el verde con una transparencia del 20%.

## ✅ Resultado esperado

- ☑️ Un bloque `:root` con tres variables y **ningún** color repetido fuera de él (salvo `#ffffff` y el verde con transparencia de la cita).
- ☑️ La página se ve igual que antes, salvo la cita, que ahora tiene un fondo verde muy suave.
- ☑️ Las cuatro formas del verde escritas y sus colores calculados anotados.

## 🚧 Restricciones

- 🚫 No uses `!important`.
- 🚫 No cambies el HTML.
- 🚫 Los nombres de las variables empiezan con dos guiones y se escriben en minúsculas.
- 🚫 La transparencia va en el canal alfa del color, no en `opacity`.

## 🎓 Resultados de aprendizaje

- RA-6: Definir y usar variables CSS.
- RA-7: Dar color con las propiedades de color, las formas de escribir un color y la transparencia.

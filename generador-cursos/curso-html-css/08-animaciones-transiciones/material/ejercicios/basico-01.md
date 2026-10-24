# 🟢 Básico 01 — Tus primeras transiciones

> 🟢 **Nivel:** Básico · 🎓 **Resultados de aprendizaje:** RA-1, RA-2 · 🗓️ **Sesión 1**

## 🧱 Estado inicial

Abrí [`basico-01.html`](../recursos/portafolio-inicial/basico-01.html) y su hoja [`css/basico-01.css`](../recursos/portafolio-inicial/css/basico-01.css), de la carpeta `portafolio-inicial`. La hoja define el aspecto de `.boton` (fondo verde `#16a34a`) y su estado `:hover` (fondo gris oscuro `#111827` y opacidad `0.6`). Hay tres botones: `.boton-a`, `.boton-b` y `.boton-c`. **Hoy el cambio al pasar el cursor es instantáneo**: ningún botón tiene transición.

## 🛠️ Proceso esperado

Escribí en `basico-01.css` las reglas de la tabla y comprobá cada valor calculado.

| # | Elegí… | Pedido | Valor calculado esperado |
|---|---|---|---|
| 1 | `.boton-a` | Una transición del fondo con las **cuatro propiedades por separado**: `0.4s`, función `ease-in` y retardo de `0.2s` | `transition-property` `background-color`, `transition-duration` `0.4s`, `transition-timing-function` `ease-in`, `transition-delay` `0.2s` |
| 2 | `.boton-b` | **Lo mismo** que el botón A, con el atajo `transition` | los mismos cuatro valores calculados |
| 3 | `.boton-c` | **Dos transiciones en una sola declaración**: el fondo en `0.3s` y la opacidad en `1s` con `ease-out` y retardo de `0.2s` | propiedades `background-color, opacity`; duraciones `0.3s, 1s`; funciones `ease, ease-out`; retardos `0s, 0.2s` |

Comprobá además el color de fondo del botón A con el cursor encima: a los `100 ms` debe ser `rgb(22, 163, 74)` (todavía en el retardo), a los `400 ms`, `rgb(20, 119, 63)` y a los `600 ms`, `rgb(17, 24, 39)`.

**Parte B.** Respondé:

1. En el atajo `0.4s ease-in 0.2s`, ¿cómo sabe el navegador cuál tiempo es la duración y cuál el retardo?
2. ¿Qué pasa con el botón si borrás la duración de una transición?
3. En el botón C, ¿cuál de las dos propiedades termina primero y por qué?

## ✅ Resultado esperado

- ☑️ Tres reglas con los valores calculados de la tabla.
- ☑️ Los tres colores del botón A en los instantes pedidos.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 No cambies las reglas `.boton` y `.boton:hover` de la hoja de partida.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-1: Explicar qué es una transición y usar sus cuatro propiedades.
- RA-2: Escribir transiciones con el atajo `transition`.

# 🔴 Desafío 01 — La hoja de Mateo, con la unidad adecuada

> 🔴 **Nivel:** Desafío · 🎓 **Resultados de aprendizaje:** RA-4, RA-5, RA-6, RA-7

## 🧱 Estado inicial

Abrí [`desafio.html`](../recursos/portafolio-inicial/desafio.html) de la carpeta `portafolio-inicial` y su hoja vacía [`css/desafio.css`](../recursos/portafolio-inicial/css/desafio.css). La página de Mateo tiene una
portada (`.portada`), un contenedor (`.contenedor`) con un resumen (`.resumen`), un «0» de referencia (`.cero`), una tarjeta (`.tarjeta`), un bloque (`.bloque`) y una cinta (`.cinta`). La paleta de Mateo es gris oscuro
`#111827` y crema `#fef3c7`. **Probá con la ventana del navegador en `1000 × 600`.**

## 🛠️ Proceso esperado

Escribí en `desafio.css` una hoja **ordenada y comentada** que cumpla todo lo siguiente, con la **unidad adecuada** en cada caso.

1. **Base.** Declará el tamaño base de `16px` en `html`. El texto, con tipografía sin serifa con alternativas, tamaño `1rem` y altura de línea `1.6`.
2. **Portada.** Una altura mínima de la mitad de la altura de la ventana.
3. **Contenedor.** Un ancho del `80%` con un tope de `40rem`.
4. **Resumen.** Un ancho máximo de `40` caracteres. `.cero` debe mostrarse como `inline-block` para poder medirlo.
5. **Tarjeta.** Letra de `20px`; ancho de `20rem`; relleno de `1.5em` en los cuatro lados; borde de `1px` continuo gris oscuro y fondo crema.
6. **Bloque.** Un alto de tres líneas de texto, con lo que sobre recortado.
7. **Cinta.** La mitad del ancho de la ventana, el `10%` del alto de la ventana y fondo crema.
8. **Reglas claras.** Ordená la hoja por temas, con un comentario antes de cada bloque, sin reglas repetidas y sin `!important`.

## ✅ Resultado esperado

- ☑️ Una hoja con todas las reglas de la lista, ordenada y comentada.
- ☑️ El HTML sin cambios.
- ☑️ La hoja pasa la revisión de estructura sin errores.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni sus clases.
- 🚫 No uses `!important`, ni `style`, ni un bloque `<style>`.
- 🚫 No uses `px` salvo donde se pida (la base, la letra de la tarjeta y el borde).
- 🚫 No uses `calc()`, `clamp()` ni `min()`.

## 🎓 Resultados de aprendizaje

- RA-4: Porcentajes y su referencia.
- RA-5: `rem` y `em`.
- RA-6: `ch` y `lh`.
- RA-7: Unidades de ventana y elección de la unidad.

## 🧪 Casos de prueba

| # | Comprobación (ventana `1000 × 600`) | Resultado esperado |
|---|---|---|
| 1 | `html` | `font-size` `16px` |
| 2 | `body` | `16px` de letra, altura de línea `25.6px`, familia con `sans-serif` al final |
| 3 | `.portada` | Alto mínimo `300px` |
| 4 | `.contenedor` | Ancho `640px` (gana el tope de `40rem`) |
| 5 | `.resumen` | Ancho igual a `40` veces el ancho de `.cero` (con una diferencia de hasta `1px`) |
| 6 | `.tarjeta` letra, ancho y relleno | `20px`, `320px` y `30px` en los cuatro lados |
| 7 | `.tarjeta` borde | `1px` continuo `rgb(17, 24, 39)` |
| 8 | `.bloque` | Alto igual a tres veces la altura de línea (`76.8px`, con una diferencia de hasta `1px`) |
| 9 | `.cinta` | Ancho `500px` y alto `60px` |
| 10 | Con la raíz en `20px` (estado simulado con una regla extra) | `body` `20px`; `.tarjeta` ancho `400px`; relleno `30px` (la letra de la tarjeta sigue fija) |
| 11 | La hoja | Sin `!important`, sin reglas repetidas y con comentarios; pasa `validar_css.py` |

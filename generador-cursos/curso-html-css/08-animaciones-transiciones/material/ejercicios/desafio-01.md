# 🔴 Desafío 01 — Una tarjeta con vida

> 🔴 **Nivel:** Desafío · 🎓 **Resultados de aprendizaje:** RA-7, RA-8, RA-9 · 🗓️ **Sesión 2**

## 🧱 Estado inicial

Abrí [`desafio.html`](../recursos/portafolio-inicial/desafio.html) de la carpeta `portafolio-inicial` y su hoja vacía [`css/desafio.css`](../recursos/portafolio-inicial/css/desafio.css). La página de Mateo tiene una `.tarjeta` con un `.icono`, un título, un texto y un `.boton`. La paleta de Mateo es verde `#16a34a`, gris oscuro `#111827` y crema `#fef3c7`.

## 🛠️ Proceso esperado

Escribí en `desafio.css` una hoja **ordenada y comentada** que cumpla todo lo siguiente.

1. **Base y aspecto.** Tamaño base de `16px` y tipografía sin serifa. `.tarjeta` de `300px` de ancho, relleno de `1rem` y fondo crema; `.icono` de `40px × 40px` con fondo verde y un margen inferior de `1rem`; `.boton` como un enlace con aspecto de botón (relleno `0.75rem 1.5rem`, texto blanco, fondo verde y sin subrayado).
2. **Entrada de la tarjeta.** Una secuencia `aparecer` (de invisible y `20px` más abajo a visible y en su lugar) que dura `0.8s` con `ease-out` y conserva los estados antes y después.
3. **Rebote del icono.** Una secuencia `rebote` con **cinco pasos porcentuales**: `0%` en `0`, `25%` en `-30px`, `50%` en `0`, `75%` en `-15px` y `100%` en `0`. Dura `2s`, a velocidad constante, **sin fin** y **empieza cuando termina la entrada** de la tarjeta.
4. **El botón.** Al pasar el cursor, el fondo cambia a gris oscuro. La **entrada** dura `0.2s` con `ease-out` y la **salida**, `0.6s` con `ease-in`.
5. **Movimiento reducido.** Si la persona prefiere menos movimiento, la tarjeta y el icono **no se animan** y el botón cambia de color al instante.
6. **Reglas claras.** Hoja ordenada por temas, con un comentario antes de cada bloque, sin reglas repetidas y sin `!important`.

## ✅ Resultado esperado

- ☑️ Una hoja con todas las reglas de la lista, ordenada y comentada.
- ☑️ El HTML sin cambios.
- ☑️ La hoja pasa la revisión de estructura sin errores.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni sus clases.
- 🚫 No uses `!important`, ni `style`, ni un bloque `<style>`.
- 🚫 Animá solo `opacity` y `transform` en las secuencias, y el fondo en la transición.
- 🚫 Sin JavaScript.

## 🎓 Resultados de aprendizaje

- RA-7: Propiedades de animación y atajo `animation`.
- RA-8: Secuencias con `from`/`to` y con porcentajes.
- RA-9: Respetar la preferencia de movimiento reducido.

## 🧪 Casos de prueba

| # | Comprobación | Resultado esperado |
|---|---|---|
| 1 | `.tarjeta` a los `0 ms` | `opacity` `0` y `translateY(20px)` |
| 2 | `.tarjeta` a los `400 ms` | `opacity` `0.68` y `translateY(6.31px)` |
| 3 | `.tarjeta` a los `800 ms` y a los `1200 ms` | `opacity` `1` y sin desplazamiento (conserva el estado final) |
| 4 | `.icono` a los `0` y `400 ms` | sin movimiento (todavía en el retardo) |
| 5 | `.icono` a los `1300 ms` | `translateY(-30px)` |
| 6 | `.icono` a los `1800 ms` y a los `2800 ms` | `0px` |
| 7 | `.icono` a los `2300 ms` | `translateY(-15px)` |
| 8 | `.icono` a los `3300 ms` | `translateY(-30px)` (la animación se repite) |
| 9 | `.boton` con el cursor, a los `100 ms` / `200 ms` | `rgb(19, 68, 50)` / `rgb(17, 24, 39)` |
| 10 | `.boton` al salir el cursor, a los `300 ms` / `600 ms` | `rgb(19, 68, 50)` / `rgb(22, 163, 74)` |
| 11 | Con movimiento reducido | ninguna animación activa; `animation-name` `none` en `.tarjeta` e `.icono`; `.boton` con `transition-duration` `0s`; la tarjeta visible (`opacity` `1`) |
| 12 | La hoja | Sin `!important`, sin reglas repetidas y con comentarios; pasa `validar_css.py` |

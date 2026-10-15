# 🔴 Desafío 01 — La tarjeta de Mateo

> 🔴 **Nivel:** Desafío · 🕑 **Sesión 2** · 🎓 **Resultados de aprendizaje:** RA-6, RA-7, RA-8

## 🧱 Estado inicial

Abrí [`desafio.html`](../recursos/portafolio-inicial/desafio.html) de la carpeta `portafolio-inicial` y su hoja vacía [`css/desafio.css`](../recursos/portafolio-inicial/css/desafio.css). La
página de Mateo tiene dos tarjetas de sus sesiones (`tarjeta`, una de ellas con el modificador `tarjeta--destacada`), con una imagen, un título (`tarjeta__titulo`), un texto largo
(`tarjeta__texto`) y un enlace. La paleta de Mateo es gris oscuro `#111827`, verde `#16a34a` y crema `#fef3c7`.

## 🛠️ Proceso esperado

Escribí en `desafio.css` una hoja **ordenada y comentada** que cumpla todo lo siguiente.

1. **Base.** Texto sin serifa con alternativas, altura de línea `1.6` y color gris oscuro. Los `h2` con serifa con alternativas y `1.5rem` de tamaño.
2. **Tamaño.** Cada tarjeta mide **320px de borde a borde**, sin importar el relleno y el borde. Elegí el modo de cálculo que lo logra con una sola declaración de ancho.
3. **Bordes.** Arriba, `4px` continuo gris oscuro; a la derecha y a la izquierda, `1px` continuo gris oscuro; abajo, `4px` doble verde.
4. **Esquinas.** Redondeadas con `16px` **solo** arriba a la izquierda y abajo a la derecha (con una sola declaración de dos valores).
5. **Espacios.** Relleno de `20px` arriba y abajo y `24px` a los costados; margen de `16px` arriba y abajo y automático a los costados, para centrar la tarjeta.
6. **Destacada.** `tarjeta--destacada` con fondo crema.
7. **Título.** `tarjeta__titulo` sin margen superior.
8. **Texto.** `tarjeta__texto` con `80px` de alto y, si el texto no entra, una barra de desplazamiento **vertical solo cuando haga falta**; nada de barra horizontal (recortá lo que sobre en ese eje).
9. **Reglas claras.** Ordená la hoja por temas, con un comentario antes de cada bloque, sin reglas repetidas y sin `!important`.

## ✅ Resultado esperado

- ☑️ Una hoja con todas las reglas de la lista, ordenada y comentada.
- ☑️ El HTML sin cambios.
- ☑️ La hoja pasa la revisión de estructura sin errores.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni sus clases.
- 🚫 No uses `!important`, ni `style`, ni un bloque `<style>`.
- 🚫 Cada color de la paleta se escribe como valor hexadecimal.
- 🚫 No uses disposición (flexbox, grid) ni posicionamiento.

## 🎓 Resultados de aprendizaje

- RA-6: Bordes distintos por lado y esquinas.
- RA-7: Cálculo del tamaño de la caja y desborde.
- RA-8: Márgenes y rellenos con sus abreviaturas.

## 🧪 Casos de prueba

| # | Comprobación | Resultado esperado |
|---|---|---|
| 1 | `body` | Familia `Arial, Helvetica, sans-serif` y altura de línea `25.6px` |
| 2 | `.tarjeta` (`offsetWidth`, las dos tarjetas) | `320` |
| 3 | `.tarjeta` bordes (arriba, derecha, abajo, izquierda) | `4px solid rgb(17, 24, 39)`, `1px solid`, `4px double rgb(22, 163, 74)`, `1px solid` |
| 4 | `.tarjeta` esquinas (arriba-izquierda, arriba-derecha, abajo-derecha, abajo-izquierda) | `16px`, `0px`, `16px`, `0px` |
| 5 | `.tarjeta` relleno (arriba, derecha, izquierda) | `20px`, `24px`, `24px` |
| 6 | `.tarjeta` márgenes | Arriba y abajo `16px`; izquierdo y derecho iguales entre sí y mayores que `0` |
| 7 | Separación entre las dos tarjetas | `16` (los márgenes colapsan) |
| 8 | `.tarjeta--destacada` | Fondo `rgb(254, 243, 199)` |
| 9 | `.tarjeta__titulo` | Familia `Georgia, "Times New Roman", serif`, tamaño `24px` y margen superior `0px` |
| 10 | `.tarjeta__texto` | `offsetWidth` `270`, `offsetHeight` `80`, `overflow-y` `auto`, `overflow-x` `hidden` y `scrollHeight` mayor que `clientHeight` |
| 11 | La hoja | Sin `!important`, sin reglas repetidas y con comentarios; pasa `validar_css.py` |

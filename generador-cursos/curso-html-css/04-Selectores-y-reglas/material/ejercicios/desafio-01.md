# 🔴 Desafío 01 — Dale estilo a la página de Mateo con selectores precisos

> 🔴 **Nivel:** Desafío · 🎓 **Resultados de aprendizaje:** RA-1, RA-2, RA-3, RA-4, RA-5, RA-6, RA-7

## 🧱 Estado inicial

Abrí [`desafio.html`](../recursos/portafolio-inicial/desafio.html) de la carpeta `portafolio-inicial` y su hoja vacía
[`css/desafio.css`](../recursos/portafolio-inicial/css/desafio.css). La página de Mateo ya tiene sus clases con nombres **BEM**: el bloque
`foto` (con `foto__imagen`, `foto__titulo`, `foto__autor` y `foto__enlace`, y los modificadores `foto--destacada` y `foto__titulo--grande`) y el
bloque `menu` (con `menu__enlace` y `menu__enlace--activo`). La paleta de Mateo es gris oscuro `#111827`, verde `#16a34a` y crema `#fef3c7`.

## 🛠️ Proceso esperado

Escribí en `desafio.css` una hoja **ordenada y comentada** que cumpla todo lo siguiente.

1. **Base.** Texto gris oscuro en toda la página; fondo crema; títulos `h2` y `h3` en gris oscuro (con `:is()`).
2. **Menú (combinador).** Los enlaces del `nav` en verde. El enlace activo (`menu__enlace--activo`) en negrita.
3. **Atributos.** Los enlaces que empiezan con `https` con fondo crema y los que terminan en `.pdf` en negrita.
4. **BEM.** El bloque `foto` con fondo blanco y borde; el modificador `foto--destacada` con fondo crema; el título grande con tamaño `28px`.
5. **`:has()`.** Las tarjetas que tienen imagen con borde verde. Cuidado: la regla del bloque `foto` también fija el color del borde; pensá la especificidad para que gane el verde.
6. **Estados.** Los enlaces en verde al pasar el cursor y con fondo crema al recibir el foco; el botón con fondo verde mientras se presiona; el campo
   deshabilitado con fondo gris (`#e5e7eb`); la etiqueta de una casilla marcada en verde.
7. **Posición.** Las filas pares del cuerpo de la tabla con fondo crema; el primer párrafo después de un `h2`, en verde.
8. **`:not()`.** Los enlaces que no son externos con subrayado de color verde (`text-decoration-color`).
9. **Reglas claras.** Ordená la hoja por temas, con un comentario antes de cada bloque, sin reglas repetidas, sin selectores de más de tres
   partes y sin `!important`.

## ✅ Resultado esperado

- ☑️ Una hoja con todas las reglas de la lista, ordenada y comentada.
- ☑️ El HTML sin cambios.
- ☑️ La hoja pasa la revisión de estructura sin errores.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni sus clases.
- 🚫 No uses `!important`, ni `style`, ni un bloque `<style>`.
- 🚫 Cada color de la paleta se escribe como valor hexadecimal.
- 🚫 No agregues propiedades de tipografía (salvo el tamaño y el peso indicados) ni de disposición.

## 🎓 Resultados de aprendizaje

- RA-1 y RA-2: Selectores básicos y de atributos.
- RA-3: Selectores basados en los nombres BEM.
- RA-4: Combinadores.
- RA-5: Selectores lógicos.
- RA-6: Pseudoclases de estado y de estructura.
- RA-7: Reglas ordenadas, comentadas y sin repetir.

## 🧪 Casos de prueba

| # | Comprobación | Resultado esperado |
|---|---|---|
| 1 | `body` | Texto `rgb(17, 24, 39)` y fondo `rgb(254, 243, 199)` |
| 2 | `h2` y `h3` | Texto `rgb(17, 24, 39)` |
| 3 | `nav a` (cuatro enlaces) | Texto `rgb(22, 163, 74)` |
| 4 | `.menu__enlace--activo` | Negrita (`700`) |
| 5 | `a[href^="https"]` (dos enlaces) | Fondo `rgb(254, 243, 199)` |
| 6 | `a[href$=".pdf"]` | Negrita (`700`) |
| 7 | `.foto--destacada` | Fondo `rgb(254, 243, 199)` |
| 8 | `.foto__titulo--grande` | Tamaño `28px` |
| 9 | Las tarjetas con imagen (dos) | Borde de color `rgb(22, 163, 74)` |
| 10 | La tarjeta sin imagen | Sin ese borde verde |
| 11 | Enlace con el cursor encima (estado simulado) | Texto `rgb(22, 163, 74)` |
| 12 | Enlace con el foco (estado simulado) | Fondo `rgb(254, 243, 199)` |
| 13 | `.boton` presionado (estado simulado) | Fondo `rgb(22, 163, 74)` |
| 14 | `input:disabled` y `input:checked + label` | Fondo `rgb(229, 231, 235)` y texto `rgb(22, 163, 74)` |
| 15 | Filas pares del cuerpo de la tabla (dos) | Fondo `rgb(254, 243, 199)` |
| 16 | `h2 + p` (uno) | Texto `rgb(22, 163, 74)` |
| 17 | Enlaces que no son externos (seis) | `text-decoration-color` `rgb(22, 163, 74)` |
| 18 | La hoja | Sin `!important`, sin reglas repetidas y con comentarios; pasa `validar_css.py` |

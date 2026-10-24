# 🟢 Básico 01 — Tus primeras cuadrículas

> 🟢 **Nivel:** Básico · 🎓 **Resultados de aprendizaje:** RA-1, RA-2 · 🗓️ **Sesión 1**

## 🧱 Estado inicial

Abrí [`basico-01.html`](../recursos/portafolio-inicial/basico-01.html) y su hoja [`css/basico-01.css`](../recursos/portafolio-inicial/css/basico-01.css), de la carpeta `portafolio-inicial`. La hoja declara el tamaño base de `16px`, saca el margen del cuerpo y le da a `.caja` una altura de `60px`. La página tiene tres secciones con cajas: `.galeria` (seis cajas), `.maqueta` (tres) y `.proporcion` (tres). Todavía no hay ninguna cuadrícula: cada caja ocupa todo el ancho. **Probá con la ventana del navegador en `1200px` de ancho**, sin barra de desplazamiento vertical.

## 🛠️ Proceso esperado

Escribí en `basico-01.css` las reglas de la tabla y comprobá las columnas calculadas.

| # | Elegí… | Pedido | Valor calculado esperado |
|---|---|---|---|
| 1 | `.galeria` | Una cuadrícula de tres columnas iguales, con `repeat()` y `fr` | columnas `400px 400px 400px` y filas `60px 60px` |
| 2 | `.maqueta` | Una cuadrícula con una columna fija de `200px` y dos columnas que se reparten lo que sobra | columnas `200px 500px 500px` |
| 3 | `.proporcion` | Una cuadrícula de tres columnas en proporción 1 a 2 a 1, con `fr` | columnas `300px 600px 300px` |

**Parte B.** Respondé:

1. Antes de escribir `display: grid`, ¿por qué cada caja de la galería medía `1200px` de ancho?
2. En `.maqueta`, ¿por qué las columnas `1fr` miden `500px` y no `600px`?
3. ¿Cuántas líneas verticales y cuántas horizontales tiene `.galeria` con tus reglas?

## ✅ Resultado esperado

- ☑️ Tres reglas con los valores calculados de la tabla.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 En la fila 2, usá `px` solo para la columna fija; en las filas 1 y 3, solo `fr`.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-1: Explicar qué es Grid y reconocer sus partes.
- RA-2: Crear una cuadrícula y definir sus columnas.

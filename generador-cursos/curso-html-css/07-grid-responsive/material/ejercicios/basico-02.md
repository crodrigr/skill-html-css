# 🟢 Básico 02 — Huecos y pistas

> 🟢 **Nivel:** Básico · 🎓 **Resultados de aprendizaje:** RA-3 · 🗓️ **Sesión 1**

## 🧱 Estado inicial

Abrí [`basico-02.html`](../recursos/portafolio-inicial/basico-02.html) y su hoja [`css/basico-02.css`](../recursos/portafolio-inicial/css/basico-02.css), de la carpeta `portafolio-inicial`. La hoja ya convierte `.rejilla` en una cuadrícula de tres columnas iguales y filas de `60px` (`grid-auto-rows`). Dentro hay una `.cabecera`, una `.destacada` (en verde) y cuatro `.foto`. Todavía no hay huecos y cada elemento ocupa una sola celda. **Probá con la ventana en `1200px` de ancho.**

## 🛠️ Proceso esperado

Escribí en `basico-02.css` las reglas de la tabla y comprobá cada medida.

| # | Elegí… | Pedido | Valor calculado esperado |
|---|---|---|---|
| 1 | `.rejilla` | `1rem` entre las filas y `2rem` entre las columnas, con `row-gap` y `column-gap` | `row-gap` `16px`, `column-gap` `32px` y columnas de `378.66px` |
| 2 | `.cabecera` | Que abarque todas las columnas, con números de línea (de la primera a la última) | ancho `1200px` |
| 3 | `.destacada` | Que ocupe dos columnas y dos filas, con `span` | ancho `789px` y alto `136px` |

**Parte B.** Respondé:

1. ¿Por qué `.destacada` mide `789px` y no `757px` (el doble de una columna)?
2. ¿Cuánto mide en total la altura de `.rejilla` y cómo se calcula?
3. ¿Qué cambiaría si en lugar de `gap` pusieras un margen de `16px` a cada elemento?

## ✅ Resultado esperado

- ☑️ Tres reglas (o grupos de reglas) con los valores calculados de la tabla.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 No cambies las columnas ni `grid-auto-rows` de la hoja de partida.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-3: Separar las pistas con huecos y ocupar varias pistas.

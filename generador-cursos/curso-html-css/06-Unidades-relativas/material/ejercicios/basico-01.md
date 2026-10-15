# 🟢 Básico 01 — Clasificá y convertí las unidades absolutas

> 🟢 **Nivel:** Básico · 🎓 **Resultados de aprendizaje:** RA-1, RA-2, RA-3

## 🧱 Estado inicial

Abrí [`basico-01.html`](../recursos/portafolio-inicial/basico-01.html) de la carpeta `portafolio-inicial`: es una página de Mateo Ruiz con cuatro cajas (`.pulgada`, `.pica`, `.punto` y `.centimetro`). Ya está
enlazada a [`css/basico-01.css`](../recursos/portafolio-inicial/css/basico-01.css), que declara el tamaño base de `16px` y el aspecto común de las cajas.

## 🛠️ Proceso esperado

**Parte A. Clasificá.** Escribí si cada valor es una unidad **absoluta** o **relativa**: `12pt`, `50%`, `2em`, `3cm`, `1.5rem`, `10vw`, `96px`, `8ch`, `2in`, `0`.

**Parte B. Convertí.** Sin usar el navegador, escribí cuántos píxeles de CSS son: `1in`, `2.54cm`, `72pt`, `3pc`, `0.5in`.

**Parte C. Escribí la hoja.** En `basico-01.css`, dale a las cuatro cajas **exactamente `192px` de ancho**, cada una con una unidad distinta:

| # | Caja | Unidad que debe usar |
|---|---|---|
| 1 | `.pulgada` | `in` |
| 2 | `.pica` | `pc` |
| 3 | `.punto` | `pt` |
| 4 | `.centimetro` | `cm` |

Comprobá que cada ancho calculado sea `192px` con las herramientas del navegador.

**Parte D. Densidad.** En una pantalla de doble densidad (`devicePixelRatio` de `2`), ¿cuántos puntos físicos de ancho ocupa una caja de `150px`? ¿Y cuántos de alto si mide `100px`?

## ✅ Resultado esperado

- ☑️ La clasificación de los diez valores.
- ☑️ Las cinco conversiones.
- ☑️ Cuatro reglas con un ancho calculado de `192px` cada una.
- ☑️ Dos respuestas numéricas para la Parte D.

## 🚧 Restricciones

- 🚫 No cambies el HTML.
- 🚫 No uses `px` en las cuatro cajas de la Parte C.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-1: Explicar qué es una unidad de medida en CSS y distinguir las absolutas de las relativas.
- RA-2: Usar `px` y explicar la densidad de píxeles.
- RA-3: Reconocer las otras unidades absolutas.

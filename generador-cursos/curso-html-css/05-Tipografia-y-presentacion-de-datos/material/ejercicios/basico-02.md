# 🟢 Básico 02 — Presentá los precios con una tabla y una lista

> 🟢 **Nivel:** Básico · 🕐 **Sesión 1** · 🎓 **Resultados de aprendizaje:** RA-5

## 🧱 Estado inicial

Abrí [`basico-02.html`](../recursos/portafolio-inicial/basico-02.html) de la carpeta `portafolio-inicial`: es la página de precios de Mateo, con una tabla de cinco servicios (con título,
encabezado y cuerpo), una lista de lo que incluye cada sesión y una lista numerada con los pasos para reservar. Ya está enlazada a
[`css/basico-02.css`](../recursos/portafolio-inicial/css/basico-02.css), que está vacía. La paleta de Mateo es gris oscuro `#111827` y crema `#fef3c7`.

## 🛠️ Proceso esperado

Escribí en `basico-02.css` las reglas de la tabla. Después comprobá cada valor calculado con las herramientas del navegador.

| # | Elegí… | Pedido | Valor calculado esperado |
|---|---|---|---|
| 1 | `table` | Bordes de celdas unidos y ancho completo | `collapse` y `100%` del ancho disponible |
| 2 | `th` y `td` | Borde de `1px` continuo gris oscuro y relleno de `8px` arriba y abajo y `12px` a los costados | `1px solid rgb(17, 24, 39)`; relleno `8px` y `12px` |
| 3 | `th` | Fondo gris oscuro y texto crema | `rgb(17, 24, 39)` y `rgb(254, 243, 199)` |
| 4 | Las celdas de clase `horas` y `precio` (12 elementos) | Texto a la derecha | `right` |
| 5 | `caption` | El título debajo de la tabla | `bottom` |
| 6 | Las filas pares del cuerpo (2 elementos) | Fondo crema | `rgb(254, 243, 199)` |
| 7 | `.incluye` | Viñeta cuadrada, dentro del texto | `square` e `inside` |
| 8 | `.pasos` y sus `li` | Numeración romana en mayúsculas y `0.5rem` de espacio debajo de cada elemento | `upper-roman` y `8px` |

**Parte B.** Respondé: si no escribieras `border-collapse: collapse`, ¿cómo se verían los bordes de las celdas y qué propiedad controlaría la distancia entre ellas?

## ✅ Resultado esperado

- ☑️ Ocho reglas con los valores calculados de la tabla.
- ☑️ Una respuesta de una o dos frases a la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 Cada color de la paleta se escribe como valor hexadecimal.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-5: Dar estilo a tablas y listas para presentar datos.

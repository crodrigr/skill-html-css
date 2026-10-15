# 🟡 Intermedio 03 — Medí las cajas

> 🟡 **Nivel:** Intermedio · 🕑 **Sesión 2** · 🎓 **Resultados de aprendizaje:** RA-7, RA-8

## 🧱 Estado inicial

Abrí [`intermedio-03.html`](../recursos/portafolio-inicial/intermedio-03.html) y su hoja [`css/intermedio-03.css`](../recursos/portafolio-inicial/css/intermedio-03.css), de la carpeta
`portafolio-inicial`. La hoja ya tiene tres cajas escritas (`.c1`, `.c2` y `.c3`) y un fondo para las demás.

## 🛠️ Proceso esperado

**Parte A. Calculá antes de medir.** Sin abrir la página, calculá para cada caja el ancho **de borde a borde** (sin margen) y anotalo en una tabla. Después medilo en la consola con
`document.querySelector(".c1").offsetWidth` y comprobá si acertaste.

| Caja | Cálculo por defecto o `border-box` | Tu cálculo | Medida real |
|---|---|---|---|
| `.c1` | _a completar_ | | |
| `.c2` | _a completar_ | | |
| `.c3` | _a completar_ | | |

Para `.c1`, calculá también cuánto espacio horizontal ocupa **con sus márgenes**.

**Parte B. Escribí dos cajas.** En `intermedio-03.css`, agregá reglas para:

| # | Caja | Pedido | Medida esperada |
|---|---|---|---|
| 1 | `.c4` | Relleno de `20px`, borde de `5px` continuo gris oscuro `#111827` y el cálculo **por defecto**; elegí el `width` para que mida **320px** de borde a borde | `offsetWidth` `320` |
| 2 | `.c5` | Los mismos relleno y borde, pero con `box-sizing: border-box`; elegí el `width` para que mida **320px** de borde a borde | `offsetWidth` `320` |

**Parte C. Desborde.** `.visor` mide `200px` por `100px` y su contenido (`.tira`) mide `400px` de ancho. Escribí la regla para que aparezca una barra de desplazamiento **horizontal solo si hace falta** y que
lo que sobre en vertical se recorte.

**Parte D. Márgenes.** Escribí las reglas para que:

1. `.p1` y `.p2` queden separadas por exactamente `24px`, usando un margen inferior en `.p1` y un margen superior de `16px` en `.p2`.
2. `.centrada` mida `300px` de ancho y quede centrada horizontalmente, con la abreviatura de `margin` de dos valores.

## ✅ Resultado esperado

- ☑️ La tabla de la Parte A completa, con el cálculo y la medida de cada caja.
- ☑️ Las reglas de las Partes B, C y D con las medidas esperadas.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni modifiques las reglas de `.c1`, `.c2` y `.c3`.
- 🚫 No uses `!important` ni el atributo `style`.
- 🚫 Cada color se escribe como valor hexadecimal.
- 🚫 No uses valores de `overflow` fuera de `visible`, `hidden`, `scroll` y `auto`.

## 🎓 Resultados de aprendizaje

- RA-7: Explicar el modelo de cajas y controlar el desborde del contenido.
- RA-8: Controlar el espacio exterior (márgenes) e interior (rellenos) de un elemento.

## 🧪 Casos de prueba

| # | Comprobación | Resultado esperado |
|---|---|---|
| 1 | `.c4` (`offsetWidth`) | `320` |
| 2 | `.c5` (`offsetWidth` y `box-sizing`) | `320` y `border-box` |
| 3 | `.visor` (`overflow-x` y `overflow-y`) | `auto` y `hidden` |
| 4 | `.visor` (`scrollWidth`) | `400` |
| 5 | Separación entre `.p1` y `.p2` (inicio de `.p2` menos el final de `.p1`) | `24` |
| 6 | `.centrada` (`offsetWidth`) | `300` |
| 7 | `.centrada` (márgenes izquierdo y derecho) | Iguales entre sí y mayores que `0` |

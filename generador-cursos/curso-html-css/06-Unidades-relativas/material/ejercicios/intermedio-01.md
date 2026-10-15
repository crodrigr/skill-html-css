# 🟡 Intermedio 01 — De `em` a `rem`

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-5

## 🧱 Estado inicial

Abrí [`intermedio-01.html`](../recursos/portafolio-inicial/intermedio-01.html) y su hoja [`css/intermedio-01.css`](../recursos/portafolio-inicial/css/intermedio-01.css), de la carpeta `portafolio-inicial`. La página de Mateo
tiene tres niveles anidados (`.nivel-1`, `.nivel-2` y `.nivel-3`) y un botón (`.boton`). La hoja ya declara el tamaño base y una regla `.nivel` con `font-size: 1.5em`, que **se acumula**, y un `.boton` con letra de `18px`.

## 🛠️ Proceso esperado

1. **Medí** los tres niveles con las herramientas del navegador y anotá sus tamaños. Explicá por qué no son iguales.
2. **Reescribí** la regla de `.nivel` para que los **tres niveles midan `24px`**, sin cambiar el HTML.
3. **El botón.** Sin tocar su `font-size`, dale un ancho de `12em` y un relleno de `0.5em` arriba y abajo y `1em` a los costados.
4. **La raíz.** Probá cambiar en la hoja `html { font-size: 20px; }` y anotá cuánto miden ahora los tres niveles y el ancho del botón. Después devolvé la raíz a `16px`.

| # | Elemento | Valor calculado esperado (raíz de `16px`) |
|---|---|---|
| 1 | `.nivel-1`, `.nivel-2` y `.nivel-3` | `24px` los tres |
| 2 | `.boton` ancho | `216px` |
| 3 | `.boton` relleno (arriba y abajo / izquierda y derecha) | `9px` / `18px` |
| 4 | Con la raíz de `20px`: los tres niveles | `30px` los tres |
| 5 | Con la raíz de `20px`: el ancho del botón | `216px` (no cambia) |

**Parte B.** Respondé: ¿por qué el botón **no** cambia con la raíz de `20px`, mientras que los niveles sí?

## ✅ Resultado esperado

- ☑️ Las anotaciones del paso 1 y del paso 4.
- ☑️ Las reglas de los pasos 2 y 3 con los valores de la tabla.
- ☑️ Una respuesta de una o dos frases a la Parte B.

## 🚧 Restricciones

- 🚫 No cambies el HTML.
- 🚫 No uses `px` en la regla de `.nivel` ni en el ancho ni en el relleno del botón.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-5: Usar `em` y `rem` y explicar su diferencia, incluido el efecto acumulativo de `em` al anidar.

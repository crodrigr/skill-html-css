# 🟢 Básico 02 — Porcentajes, `em` y `rem`

> 🟢 **Nivel:** Básico · 🎓 **Resultados de aprendizaje:** RA-4, RA-5

## 🧱 Estado inicial

Abrí [`basico-02.html`](../recursos/portafolio-inicial/basico-02.html) y su hoja [`css/basico-02.css`](../recursos/portafolio-inicial/css/basico-02.css), de la carpeta `portafolio-inicial`. La hoja declara el tamaño base
de `16px` y un marco (`.marco`) de `600px` de ancho. La página tiene, dentro del marco, `.mitad`, `.letra` y `.relleno`; y fuera, un `.boton`, un `.titulo-rem` y tres niveles anidados (`.nivel-1`, `.nivel-2` y `.nivel-3`).

## 🛠️ Proceso esperado

Escribí en `basico-02.css` las reglas de la tabla y comprobá cada valor calculado.

| # | Elegí… | Pedido | Valor calculado esperado |
|---|---|---|---|
| 1 | `.mitad` | La mitad del ancho del marco, con `%` | `300px` de ancho |
| 2 | `.letra` | Un tamaño de letra del `125%` | `20px` |
| 3 | `.relleno` | Un relleno del `5%` en los cuatro lados | `30px` en cada lado |
| 4 | `.boton` | Letra de `20px`, ancho de `15em` y relleno de `0.5em` | ancho `300px` y relleno `10px` |
| 5 | `.titulo-rem` | Un tamaño de `1.5rem` | `24px` |
| 6 | `.nivel` (los tres) | Un tamaño de `1.5em` en la clase `.nivel` | `24px`, `36px` y `54px` |

**Parte B.** Respondé:

1. ¿Por qué el `5%` de relleno da `30px` también arriba y abajo, si el marco es más bajo que ancho?
2. ¿Por qué `.nivel-3` no mide `24px` si los tres piden lo mismo?
3. ¿Qué cambiaría en la tabla si `html` tuviera `font-size: 20px`? Respondé para las filas 5 y 6.

## ✅ Resultado esperado

- ☑️ Seis reglas con los valores calculados de la tabla.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 Usá en cada fila solo la unidad pedida.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-4: Usar el porcentaje y explicar respecto de qué se calcula.
- RA-5: Usar `em` y `rem` y explicar su diferencia.

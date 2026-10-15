# 🟡 Intermedio 02 — `ch`, `lh` y las unidades de ventana

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-6, RA-7

## 🧱 Estado inicial

Abrí [`intermedio-02.html`](../recursos/portafolio-inicial/intermedio-02.html) y su hoja [`css/intermedio-02.css`](../recursos/portafolio-inicial/css/intermedio-02.css), de la carpeta `portafolio-inicial`. La hoja declara el
tamaño base de `16px`, una altura de línea de `1.5` y el fondo de las cajas. La página tiene una portada (`.portada`), un campo (`.campo`), una nota (`.nota`), una banda (`.banda`) y un cuadrado (`.cuadrado`), además de un
«0» de referencia (`.cero`). **Probá con la ventana del navegador en `1000 × 600`.**

## 🛠️ Proceso esperado

Agregá a `intermedio-02.css` una regla por elemento.

| # | Elemento | Pedido | Valor calculado esperado |
|---|---|---|---|
| 1 | `.portada` | Un alto mínimo del `60%` del alto de la ventana | `360px` |
| 2 | `.campo` | Tipografía `monospace` y un ancho de `30` caracteres | `30` veces el ancho de `.cero` (unos `289px`) |
| 3 | `.nota` | Un alto de cinco líneas de texto; lo que sobre, recortado | `120px` |
| 4 | `.banda` | Un ancho del `20%` del ancho de la ventana | `200px` |
| 5 | `.cuadrado` | Un cuadrado cuyo lado sea el `30%` del lado menor de la ventana | `180px` de ancho y de alto |

**Parte B.** Cambiá el tamaño de la ventana a `600 × 1000` y anotá cuánto miden ahora `.portada`, `.banda` y `.cuadrado`. Explicá por qué `.cuadrado` no cambió.

## ✅ Resultado esperado

- ☑️ Cinco reglas con los valores de la tabla.
- ☑️ Las tres medidas de la Parte B y una explicación de una o dos frases.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni modifiques las reglas que ya están en la hoja.
- 🚫 No uses `px`, `%` ni `em` en las cinco reglas.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-6: Usar `ex`, `ch` y `lh` y explicar de qué dependen.
- RA-7: Reconocer las otras unidades relativas y elegir la unidad adecuada.

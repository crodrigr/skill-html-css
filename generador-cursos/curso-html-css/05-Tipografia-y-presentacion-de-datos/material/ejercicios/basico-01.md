# 🟢 Básico 01 — Dale forma al texto de una entrada

> 🟢 **Nivel:** Básico · 🕐 **Sesión 1** · 🎓 **Resultados de aprendizaje:** RA-1, RA-2, RA-3

## 🧱 Estado inicial

Abrí [`basico-01.html`](../recursos/portafolio-inicial/basico-01.html) de la carpeta `portafolio-inicial`: es una entrada del blog de Mateo Ruiz, «Cómo fotografiar con luz natural», con
una fecha, una entradilla y un cuerpo con dos subtítulos y tres párrafos. Ya está enlazada a [`css/basico-01.css`](../recursos/portafolio-inicial/css/basico-01.css), que está vacía.

## 🛠️ Proceso esperado

1. En `basico-01.css`, escribí las reglas de la tabla. Usá solo las propiedades de tipografía y de texto de la clase.
2. Comprobá cada valor con las herramientas del navegador (pestaña de estilos calculados) o con `getComputedStyle(elemento)` en la consola.

| # | Elegí… | Pedido | Valor calculado esperado |
|---|---|---|---|
| 1 | `body` | Tipografía sin serifa, con alternativas, terminando en la familia genérica | `Arial, Helvetica, sans-serif` |
| 2 | `h1` y `h2` (tres elementos) | Tipografía con serifa, con alternativas, terminando en la familia genérica | `Georgia, "Times New Roman", serif` |
| 3 | `body` | Tamaño de `1rem` y altura de línea sin unidad de `1.6` | `16px` y `25.6px` |
| 4 | `.titulo` | Texto centrado | `center` |
| 5 | `.intro` | Tamaño de `1.25rem` y cursiva | `20px` e `italic` |
| 6 | `.fecha` | Tamaño de `0.875rem`, todo en mayúsculas y letras separadas por `1px` | `14px`, `uppercase` y `1px` |
| 7 | Los tres párrafos de `.cuerpo` | Sangría de `1.5rem` y texto justificado | `24px` y `justify` |

**Parte B.** Respondé por escrito:

1. ¿Por qué cada lista de tipografías termina con `sans-serif` o `serif`?
2. ¿Qué diferencia hay entre `font-size: 1.25em` y `font-size: 1.25rem` si el elemento está dentro de un contenedor con `font-size: 1.25rem`?
3. ¿Por qué se escribe `line-height: 1.6` y no `line-height: 160%`?

## ✅ Resultado esperado

- ☑️ Siete reglas con los valores calculados de la tabla.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 Usá solo tipografías del sistema (sin fuentes descargadas ni servicios externos).
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-1: Explicar qué es la tipografía y reconocer las familias tipográficas más comunes.
- RA-2: Aplicar tipografías en CSS: familia con alternativas, tamaño, peso, estilo y altura de línea.
- RA-3: Alinear y espaciar el texto.

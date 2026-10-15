# 🟡 Intermedio 02 — Estilos según el estado y la posición

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-6

## 🧱 Estado inicial

Abrí [`intermedio-02.html`](../recursos/portafolio-inicial/intermedio-02.html) y su hoja vacía
[`intermedio-02.css`](../recursos/portafolio-inicial/css/intermedio-02.css), de la carpeta `portafolio-inicial`. La página de Mateo tiene un
menú, una tabla de seis precios, una lista numerada de cuatro pasos, una lista de una sola nota y un formulario con casillas, un campo
deshabilitado y un botón.

## 🛠️ Proceso esperado

Escribí en `intermedio-02.css` una regla para cada fila, con la declaración indicada.

| # | Elegí… | Declaración |
|---|---|---|
| 1 | Los enlaces del menú, al **pasar el cursor** | `color: #16a34a;` |
| 2 | Los enlaces, cuando reciben el **foco** | `background-color: #fef3c7;` |
| 3 | El botón, **mientras se presiona** | `background-color: #16a34a;` |
| 4 | La etiqueta que va después de una **casilla marcada** | `color: #16a34a;` |
| 5 | Los campos **deshabilitados** | `background-color: #e5e7eb;` |
| 6 | Las filas **pares** del cuerpo de la tabla | `background-color: #fef3c7;` |
| 7 | El **primer** y el **último** elemento de cada lista (una regla para cada uno) | `font-weight: bold;` |
| 8 | El **tercer** elemento de su lista | `color: #16a34a;` |
| 9 | El elemento que **no tiene hermanos** | `background-color: #fef3c7;` |

**Comprobá** cuántos elementos elige cada selector de posición y cómo se ven los estados. Para el cursor y el foco, usá la opción de las
herramientas del navegador que fuerza el estado de un elemento.

## ✅ Resultado esperado

- ☑️ Nueve reglas (diez selectores) con las declaraciones indicadas.
- ☑️ Los conteos de las filas 6 a 9 anotados.
- ☑️ Una frase que explique por qué **no** se puede comprobar de la misma manera un enlace `:visited`.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 Respetá el orden de los estados de enlace: cursor y después foco.
- 🚫 No quites el indicador de foco del navegador.

## 🎓 Resultados de aprendizaje

- RA-6: Dar estilo a un elemento según su estado o su posición con las pseudoclases, incluidas las de estructura.

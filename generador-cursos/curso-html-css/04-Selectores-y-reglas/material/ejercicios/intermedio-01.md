# 🟡 Intermedio 01 — Combinadores y selectores lógicos

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-4, RA-5

## 🧱 Estado inicial

Abrí [`intermedio-01.html`](../recursos/portafolio-inicial/intermedio-01.html) y su hoja vacía
[`intermedio-01.css`](../recursos/portafolio-inicial/css/intermedio-01.css), de la carpeta `portafolio-inicial`. Es la galería de Mateo:
un menú con una lista de enlaces, una presentación, una sección de fotos con tres tarjetas (una sin imagen) y una lista de enlaces.

## 🛠️ Proceso esperado

Escribí en `intermedio-01.css` **un selector por fila**, con una declaración que se note, y comprobá cuántos elementos elige.

| # | Elegí… | Cuántos |
|---|---|---|
| a | Los enlaces que están **dentro** del `nav` | 3 |
| b | Los `li` que son **hijos directos** de la lista de clase `menu` | 3 |
| c | El párrafo que va **inmediatamente después** de un `h2` | 1 |
| d | **Todos** los párrafos hermanos que siguen a un `h2` | 3 |
| e | Los títulos de primer, segundo y tercer nivel, con **un solo selector** | 8 |
| f | Los enlaces que **no** son externos (`href` que no empieza con `https`) | 4 |
| g | Las tarjetas (`article`) que **tienen una imagen** | 2 |

**Parte B — Especificidad.**

1. Escribí primero una regla simple `h3` que dé color verde (`#16a34a`).
2. **Debajo**, escribí una regla con `:where()` que dé color gris oscuro (`#111827`) a los `h2` y a los `h3`. Comprobá de qué color se ve un `h3` y explicá por qué.
3. Reemplazá `:where()` por `:is()`. ¿De qué color se ve ahora el `h3`? ¿Qué cambió?

## ✅ Resultado esperado

- ☑️ Siete selectores, uno por fila, con los conteos pedidos.
- ☑️ La Parte B hecha y explicada en dos o tres frases.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 El selector (c) usa un combinador de hermano; el (d), otro distinto.
- 🚫 El (e) usa un selector lógico; el (f), `:not()`; el (g), `:has()`.

## 🎓 Resultados de aprendizaje

- RA-4: Combinar selectores para elegir elementos según su relación con otros.
- RA-5: Agrupar, excluir y combinar condiciones con los selectores lógicos.

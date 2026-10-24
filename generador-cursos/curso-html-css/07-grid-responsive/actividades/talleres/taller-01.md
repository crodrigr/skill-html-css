# 🛠️ Taller 01 — Armá la maqueta

## 🎯 Objetivo

Aplicar lo aprendido en la sesión 1: reconocer las partes de una cuadrícula (RA-1), definir columnas y filas con `fr`, `repeat()` y `minmax()` (RA-2) y separar y ocupar pistas (RA-3).

## 🌍 Contexto

Trabajás solo o en pareja, con **una página propia** (o la del taller de la Clase 05) que tenga una cabecera, un menú, un contenido con varias tarjetas y un pie. Usás VS Code (o un editor en línea) y el navegador, con sus herramientas para desarrolladores. No hace falta JavaScript. Podés agregar clases al HTML. **Trabajá con la ventana del navegador bien ancha (unos `1200px`).**

## 🪜 Pasos

1. **Dibujá primero.** En papel, dibujá la maqueta: cabecera arriba, menú a la izquierda, contenido en el centro y pie abajo. Marcá las líneas, las pistas y las celdas.
2. **El contenedor.** Poné todos los bloques dentro de un contenedor y activá `display: grid`.
3. **Columnas.** Definí dos columnas: una de `200px` para el menú y otra que ocupe el resto con `fr`.
4. **Huecos.** Agregá un `gap` de `1rem` y anotá cuánto mide la segunda columna.
5. **Ocupar pistas.** Hacé que la cabecera y el pie abarquen las dos columnas, una vez con números de línea (`1 / -1`) y otra vez con `span`. Anotá si hubo diferencia.
6. **La galería.** Dentro del contenido, hacé una cuadrícula de tres columnas iguales con `repeat()` y seis tarjetas. Anotá el ancho de cada columna con un `gap` de `1rem`.
7. **Una tarjeta destacada.** Hacé que una tarjeta ocupe dos columnas y dos filas. Anotá su ancho y su alto.
8. **El experimento.** Sacá `display: grid` del contenedor y observá qué pasa; después volvé a ponerlo. Anotá lo que cambió.
9. **Comprobá** la hoja: sin `!important`, con comentarios y sin errores de estructura.

## 📦 Entregable

La carpeta del proyecto con la página y su hoja, y una nota con: el dibujo del paso 1 (foto), las medidas de los pasos 4, 6 y 7 y la observación del paso 8.

## 📋 Criterios de evaluación

- ✔️ La maqueta tiene cabecera, menú, contenido y pie en una cuadrícula.
- ✔️ Las columnas usan una medida fija y `fr`, y la galería usa `repeat()`.
- ✔️ La cabecera y el pie abarcan las dos columnas.
- ✔️ Hay un `gap` y las medidas anotadas coinciden con las que se ven en el navegador.
- ✔️ La tarjeta destacada ocupa dos columnas y dos filas.
- ✔️ La nota explica el efecto de quitar `display: grid`.
- ✔️ La hoja está ordenada, comentada y sin `!important`.

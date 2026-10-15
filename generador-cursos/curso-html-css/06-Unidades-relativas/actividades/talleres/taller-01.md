# 🛠️ Taller 01 — Escalá tu página

## 🎯 Objetivo

Aplicar lo aprendido en la clase: distinguir unidades absolutas y relativas (RA-1), usar `px` con criterio (RA-2), usar `%`, `em` y `rem` (RA-4 y RA-5), medir con `ch` y `lh` (RA-6) y elegir la unidad adecuada
en cada situación (RA-7).

## 🌍 Contexto

Trabajás solo o en pareja, con **la hoja de estilos de tu sitio** (por ejemplo, la del taller de la Clase 05) o con una página propia que tenga títulos, párrafos, una tabla o lista y una tarjeta. Usás VS Code (o un editor en
línea) y el navegador, con sus herramientas para desarrolladores y su consola. No hace falta JavaScript más allá de leer medidas en la consola, ni disposición. Podés agregar clases al HTML.

## 🪜 Pasos

1. **Inventario.** Listá cada medida de tu hoja y clasificala: absoluta o relativa. Anotá cuántas hay de cada unidad.
2. **Tamaño base.** Declará `html { font-size: 16px; }` solo para esta práctica y anotá el valor calculado de tus textos.
3. **Texto en `rem`.** Pasá todos los tamaños de letra a `rem` y comprobá que los valores calculados no cambiaron.
4. **Componente en `em`.** Elegí un botón o una etiqueta y dale un ancho y un relleno en `em`, de modo que crezcan con su letra.
5. **Contenedor en `%`.** Dale a un contenedor un ancho en `%` con un tope en `rem`. Anotá cuánto mide con la ventana en `1000 × 600` y con otra.
6. **Ancho de lectura.** Limitá un párrafo a unos `65` caracteres con `ch`.
7. **Bloque en líneas.** Dale a un bloque un alto de tres líneas con `lh`.
8. **El experimento.** Cambiá la raíz a `20px`. Anotá qué cambió y qué no (los bordes en `px`, por ejemplo), y explicá por qué.
9. **Decisiones.** Para cada una de cinco medidas de tu hoja, escribí por qué elegiste su unidad.
10. **Comprobá** la hoja: sin `!important`, con comentarios y sin errores de estructura.

## 📦 Entregable

La carpeta del proyecto con la hoja de estilos y una nota con: el inventario del paso 1, los valores calculados antes y después de los pasos 3 y 8, las dos medidas del paso 5 y las cinco justificaciones del paso 9.

## 📋 Criterios de evaluación

- ✔️ El inventario clasifica bien cada unidad.
- ✔️ Los textos están en `rem` y sus valores calculados no cambiaron.
- ✔️ Hay una medida en `em`, un ancho en `%` con tope, un ancho de lectura en `ch` y un alto en `lh`.
- ✔️ La nota explica el efecto de cambiar la raíz, incluido lo que **no** cambia.
- ✔️ Las cinco justificaciones usan el criterio de la tabla de la clase.
- ✔️ La hoja está ordenada, comentada y sin `!important`.

# 🛠️ Taller 02 — Que se adapte

## 🎯 Objetivo

Aplicar lo aprendido en las dos sesiones: preparar una página (RA-4 y RA-5), elegir una estrategia (RA-6) y escribir consultas de medios (RA-7), sobre la maqueta que armaste con Grid en el Taller 01 (RA-1 a RA-3).

## 🌍 Contexto

Partís del **resultado del Taller 01**. Usás VS Code (o un editor en línea) y el navegador, con sus herramientas para desarrolladores (el modo de dispositivos o la ventana redimensionada). No hace falta JavaScript. Podés agregar clases al HTML. Si podés, probá también la página en tu teléfono.

## 🪜 Pasos

1. **Preparación previa.** Agregá la etiqueta de la ventana de visualización, hacé que el ancho incluya relleno y borde en todos los elementos y volvé flexibles las imágenes.
2. **Buscá el desborde.** Estrechá la ventana a `500px` y anotá si aparece desplazamiento horizontal. Si aparece, encontrá la causa y corregila.
3. **Elegí la estrategia.** Escribí en una frase si vas a trabajar móvil primero o escritorio primero, y por qué.
4. **Teléfono.** Dejá la maqueta en **una columna**, con los bloques apilados.
5. **Primer punto de ruptura.** Con una consulta de `min-width`, pasá a **dos columnas** (menú y contenido lado a lado) desde `600px`. La cabecera y el pie siguen ocupando todo el ancho.
6. **Segundo punto de ruptura.** Con otra consulta, pasá a **tres columnas** desde `900px`, agregando un bloque lateral a la derecha. Escribí las consultas de menor a mayor.
7. **La galería.** Hacé que las tarjetas del contenido se acomoden solas con `auto-fit` y `minmax()`, sin consultas.
8. **Medí.** Anotá cuántas columnas y qué ancho tiene la página en `500px`, `800px` y `1200px`.
9. **El experimento del orden.** Invertí el orden de las dos consultas, observá en `1200px` qué pasa y volvé a ponerlas bien. Explicá por qué.
10. **Comprobá** la hoja: sin `!important`, con comentarios y sin errores de estructura.

## 📦 Entregable

La carpeta del proyecto con la página y su hoja, y una nota con: la causa del desborde del paso 2, la justificación del paso 3, las medidas del paso 8 y la explicación del paso 9.

## 📋 Criterios de evaluación

- ✔️ La página tiene la ventana de visualización, `border-box` e imágenes flexibles.
- ✔️ No hay desplazamiento horizontal en una ventana de `500px`.
- ✔️ La maqueta tiene una, dos y tres columnas en los tres tamaños, con puntos de ruptura en `600px` y `900px`.
- ✔️ Las consultas están escritas de menor a mayor.
- ✔️ La galería se acomoda sola sin consultas.
- ✔️ La nota explica el efecto del orden de las consultas.
- ✔️ La hoja está ordenada, comentada y sin `!important`.

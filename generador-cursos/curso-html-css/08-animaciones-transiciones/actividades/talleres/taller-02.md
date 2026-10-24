# 🛠️ Taller 02 — Animá con respeto

## 🎯 Objetivo

Aplicar lo aprendido en las dos sesiones: usar las propiedades de animación y su atajo (RA-7), definir secuencias con `from`/`to` y con porcentajes (RA-8) y respetar la preferencia de movimiento reducido (RA-9), sobre la página del Taller 01 (RA-1 a RA-6).

## 🌍 Contexto

Partís del **resultado del Taller 01**. Usás VS Code (o un editor en línea) y el navegador, con sus herramientas para desarrolladores. No hace falta JavaScript. Podés agregar clases al HTML. Para probar el movimiento reducido, activá esa opción en tu sistema operativo o emulala en las herramientas del navegador.

## 🪜 Pasos

1. **Una entrada.** Con `@keyframes` (`from` y `to`), hacé que la tarjeta **aparezca sola** al cargar la página. Anotá qué pasa al terminar si no usás relleno y arreglalo.
2. **Con el atajo.** Reescribí la animación con `animation` y comprobá que se ve igual. Poné el nombre al final.
3. **Un indicador de carga.** Hacé un elemento que **gire sin parar** (`rotate`, repeticiones infinitas, velocidad constante).
4. **Un rebote.** Con selectores porcentuales (cinco pasos), hacé que un icono **rebote**. Anotá en qué segundo cae cada paso.
5. **Repeticiones y dirección.** Probá `alternate` y un retardo en el rebote. Anotá la diferencia.
6. **Una secuencia sin `from`.** Hacé una secuencia que solo defina `to` sobre un elemento con un `transform` propio y anotá desde dónde parte.
7. **Un error a propósito.** Escribí mal el nombre de una animación y anotá qué pasa.
8. **Movimiento reducido.** Agregá la regla que **quita** las animaciones (y reduce las transiciones) si la persona prefiere menos movimiento. Probala.
9. **Evaluá lo que animaste.** Para cada animación, anotá si podría molestar a una persona sensible al movimiento y qué hiciste.
10. **Comprobá** la hoja: sin `!important`, con comentarios y sin errores de estructura.

## 📦 Entregable

La carpeta del proyecto con la página y su hoja, y una nota con: la observación del paso 1, el segundo en que cae cada paso del rebote (paso 4), las observaciones de los pasos 5 a 7 y la evaluación del paso 9.

## 📋 Criterios de evaluación

- ✔️ La tarjeta aparece sola y conserva su estado final.
- ✔️ Hay una animación con el atajo `animation`, con el nombre al final.
- ✔️ El indicador gira sin fin y el rebote usa cinco pasos porcentuales.
- ✔️ La regla de movimiento reducido quita las animaciones y funciona al activarla.
- ✔️ La nota explica el efecto de las secuencias sin `from` y de un nombre mal escrito.
- ✔️ La evaluación del paso 9 identifica qué podría molestar.
- ✔️ La hoja está ordenada, comentada y sin `!important`.

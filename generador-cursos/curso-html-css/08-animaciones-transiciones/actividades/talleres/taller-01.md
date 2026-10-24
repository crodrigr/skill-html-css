# 🛠️ Taller 01 — Dale vida a tu interfaz

## 🎯 Objetivo

Aplicar lo aprendido en la sesión 1: usar las propiedades de transición y su atajo (RA-1 y RA-2), diseñar transiciones de entrada y de salida (RA-3) y elegir la función de tiempo adecuada, incluidas una curva propia y una por pasos (RA-4 a RA-6).

## 🌍 Contexto

Trabajás solo o en pareja, con **una página propia** (o la del taller de la Clase 07) que tenga un menú con enlaces, un botón y una tarjeta. Usás VS Code (o un editor en línea) y el navegador, con sus herramientas para desarrolladores. No hace falta JavaScript. Podés agregar clases al HTML. **Probá pasando el cursor sobre los elementos.**

## 🪜 Pasos

1. **Detectá los cambios bruscos.** Pasá el cursor por el menú, el botón y la tarjeta y anotá qué propiedades cambian de golpe.
2. **Una transición en el botón.** Suavizá el color de fondo con las cuatro propiedades por separado. Anotá la duración que elegiste y por qué.
3. **Pasala al atajo.** Reescribí la transición del paso 2 con `transition` y comprobá que se ve igual.
4. **Entrada y salida.** Hacé que el botón se oscurezca **rápido** al entrar el cursor y vuelva **despacio** al salir. Anotá dónde escribiste cada transición.
5. **Varias propiedades.** En la tarjeta, suavizá la opacidad y un pequeño desplazamiento hacia arriba (`translateY`) con tiempos distintos, en una sola declaración.
6. **Elegí el ritmo.** Probá la tarjeta con `ease-out`, `ease-in` y `linear`. Anotá cuál te parece más natural para algo que **aparece** y por qué.
7. **Una curva propia.** Reemplazá la función por un `cubic-bezier()` con un pequeño rebote. Anotá los cuatro valores y qué hace cada par.
8. **Un movimiento por pasos.** Hacé que un elemento de tu página avance en **cinco saltos** con `steps()`. Anotá qué diferencia hay con una curva.
9. **Lo que no se anima.** Intentá animar un cambio de `display` o una altura `auto` y anotá qué pasó.
10. **Comprobá** la hoja: sin `!important`, con comentarios y sin errores de estructura.

## 📦 Entregable

La carpeta del proyecto con la página y su hoja, y una nota con: los cambios bruscos del paso 1, las decisiones de los pasos 2, 4 y 6, los valores del paso 7 y la observación del paso 9.

## 📋 Criterios de evaluación

- ✔️ Hay una transición con las cuatro propiedades y otra con el atajo, y se ven iguales.
- ✔️ La entrada y la salida del botón tienen tiempos distintos y están escritas en el lugar correcto.
- ✔️ La tarjeta anima dos propiedades en una sola declaración.
- ✔️ Hay una curva `cubic-bezier()` con valores válidos y un `steps()`.
- ✔️ La nota explica por qué algunos cambios no se animan.
- ✔️ La hoja está ordenada, comentada y sin `!important`.

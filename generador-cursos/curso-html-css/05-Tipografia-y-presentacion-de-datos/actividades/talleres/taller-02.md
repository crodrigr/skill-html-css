# 🛠️ Taller 02 — Armá tu tarjeta

> 🕑 **Sesión 2**

## 🎯 Objetivo

Aplicar lo aprendido en la sesión 2: crear bordes distintos en cada lado y esquinas redondeadas (RA-6), calcular el tamaño de una caja y controlar el desborde (RA-7), y controlar márgenes y rellenos con sus
abreviaturas (RA-8).

## 🌍 Contexto

Trabajás solo o en pareja, con la **hoja de estilos del taller 01** (o con un sitio propio). Usás VS Code (o un editor en línea) y el navegador, con sus herramientas para desarrolladores y su consola. No hace falta
JavaScript más allá de leer medidas en la consola, ni disposición. Podés agregar clases al HTML.

## 🪜 Pasos

1. **Armá una tarjeta** de proyecto (o de producto) con un título, un texto largo y un enlace, y nombrá sus clases con una convención uniforme (por ejemplo, BEM: `tarjeta`, `tarjeta__titulo`, `tarjeta__texto`).
2. **Elegí el modo de cálculo.** Dale a la tarjeta un ancho fijo y `box-sizing: border-box`, de modo que mida **exactamente** el ancho que escribas.
3. **Bordes.** Un borde distinto por lado: al menos uno de distinto grosor, uno de distinto estilo y uno de distinto color.
4. **Esquinas.** Redondeá **solo dos** esquinas opuestas con la abreviatura de dos valores y una tercera con la propiedad de esa esquina.
5. **Rellenos y márgenes.** Usá la notación abreviada de dos valores en el relleno y de dos valores en el margen, y centrá la tarjeta horizontalmente.
6. **Desborde.** Dale al texto de la tarjeta un alto fijo y un `overflow` que muestre barras solo cuando haga falta; probá también `hidden` y compará.
7. **Dos tarjetas.** Poné una segunda tarjeta debajo y comprobá cuánto las separa. Explicá por qué no es la suma de los márgenes.
8. **Medí.** En la consola, leé `offsetWidth` de la tarjeta, `clientWidth` y la separación entre las dos. Calculá antes cada valor.
9. **Comprobá** la hoja: sin `!important`, con comentarios y sin errores de estructura.

## 📦 Entregable

La carpeta del proyecto con la tarjeta, la hoja de estilos y una nota con: el cálculo y la medida real del ancho de la tarjeta, la separación entre las dos tarjetas con su explicación y el efecto de `hidden` frente a `auto`.

## 📋 Criterios de evaluación

- ✔️ La tarjeta mide el ancho pedido de borde a borde y la nota explica el cálculo.
- ✔️ Hay bordes distintos por lado y esquinas redondeadas con la notación pedida.
- ✔️ El relleno y el margen usan la notación abreviada y la tarjeta queda centrada.
- ✔️ El texto desborda de forma controlada y la nota compara `hidden` y `auto`.
- ✔️ La nota explica el colapso de márgenes con la medida de la separación.
- ✔️ La hoja está ordenada, comentada, sin repeticiones y sin `!important`.

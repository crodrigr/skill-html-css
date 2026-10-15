# 📘 Ejemplo 02 — La unidad `px` y la densidad de píxeles

> 🎓 **Resultados de aprendizaje:** RA-2

## 🧱 Situación inicial

Lucía sabe que `px` significa «píxel», y supone que cada píxel de CSS es un punto de la pantalla. Quiere comprobar qué pasa en una pantalla de **alta densidad**, como las de muchos celulares y
portátiles. En `px.html` pone una caja de `200px × 100px`, un texto de `24px` y un borde fino de `1px`.

## 💻 Código

El contenido de `px.html` (dentro de `<main>`):

```html
<h2>Una caja de 200 píxeles</h2>
<div class="caja">200 × 100 px</div>
<p class="texto">Texto de 24 píxeles con un borde fino de 1 píxel.</p>
```

La hoja `css/px.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* El píxel de CSS: borde y contenido miden lo que dice el valor */
.caja {
  box-sizing: border-box;
  width: 200px;
  height: 100px;
  border: 1px solid #1e3a8a;
  background-color: #dbeafe;
}

.texto {
  font-size: 24px;
  border: 1px solid #1e3a8a;
}
```

## 🔍 Análisis paso a paso

1. **`px` es una unidad absoluta.** `200px` son siempre doscientos píxeles **de CSS**, sin importar el contenedor ni el tamaño de letra.
2. **Un píxel de CSS no es un punto físico.** En una pantalla común, un píxel de CSS ocupa **un** punto de la pantalla. En una pantalla de **alta densidad**, un píxel de CSS ocupa varios puntos: con una
   relación de `2`, ocupa `2 × 2 = 4` puntos físicos.
3. **La relación de densidad.** El navegador la informa con `window.devicePixelRatio`: vale `1` en una pantalla común y `2` en una de doble densidad. Se escribe en la consola con
   `window.devicePixelRatio`.
4. **Para qué sirve esta idea.** La página se dibuja **igual de grande** en las dos pantallas: la caja de `200px` ocupa el mismo tamaño aparente. Lo que cambia es la nitidez: en la pantalla de alta densidad,
   las letras y las líneas se ven más finas y definidas porque usan más puntos.
5. **Qué mide el navegador.** Las medidas del DOM (`offsetWidth`, el ancho calculado) siguen en píxeles **de CSS**: la caja mide `200` en las dos pantallas, aunque en la de alta densidad ocupe `400` puntos
   físicos.
6. **El borde de `1px`.** Sigue calculándose como `1px`; en la pantalla de doble densidad se dibuja con 2 puntos de grosor.
7. **`box-sizing: border-box`.** La caja usa `border-box` para que su ancho sea `200px` de borde a borde (ver la Clase 05).

## ✅ Resultado esperado

| Medida | Pantalla común (relación 1) | Pantalla de doble densidad (relación 2) |
|---|---|---|
| `window.devicePixelRatio` | `1` | `2` |
| `.caja` ancho calculado | `200px` | `200px` |
| `.caja` `offsetWidth` | `200` | `200` |
| `.caja` ancho en puntos físicos | `200` | `400` |
| `.caja` borde superior | `1px` | `1px` |
| `.texto` tamaño de letra | `24px` | `24px` |

- La caja se ve del mismo tamaño aparente en las dos pantallas; en la de doble densidad, el borde y el texto se ven más nítidos.

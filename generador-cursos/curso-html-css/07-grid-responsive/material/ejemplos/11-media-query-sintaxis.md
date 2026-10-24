# 📘 Ejemplo 11 — Media query: la sintaxis

> 🎓 **Resultados de aprendizaje:** RA-7
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere que su título sea más grande y la galería pase a dos columnas cuando la ventana es más ancha. En `media-query.html` usa su primera consulta de medios.

## 💻 Código

El contenido de `media-query.html` (dentro de `<main>`):

```html
<h2 class="titulo">Un título que cambia</h2>

<section class="galeria">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</section>
```

La hoja `css/media-query.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

/* Sin margen en el cuerpo: las cuadrículas ocupan todo el ancho de la ventana */
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

/* Que el ancho incluya el relleno y el borde (se explica en el Ejemplo 08) */
* {
  box-sizing: border-box;
}

.item {
  height: 60px;
  line-height: 60px;
  text-align: center;
  background-color: #dbeafe;
}

.item:nth-child(even) {
  background-color: #ccfbf1;
}

/* Estilos de partida: valen en cualquier ancho */
.titulo {
  font-size: 1.5rem;
}

.galeria {
  display: grid;
  grid-template-columns: 1fr;
  gap: 16px;
}

/* A partir de 600px de ancho de ventana (incluido), se aplican las reglas de adentro */
@media (min-width: 600px) {
  .titulo {
    font-size: 2rem;
  }

  .galeria {
    grid-template-columns: repeat(2, 1fr);
  }
}
```

## 🔍 Análisis paso a paso

1. **Qué es una consulta de medios** (*media query*). Es una **condición** sobre el dispositivo o la ventana: si se cumple, se aplican las reglas que van adentro. Se escribe con `@media`.
2. **La sintaxis.** `@media (min-width: 600px) { … }` se lee «**si** la ventana mide `600px` o más, aplicá lo que está entre llaves». Adentro van reglas normales, con sus selectores.
3. **Estilos base y estilos condicionales.** Fuera de la consulta están los estilos que valen **siempre** (título de `1.5rem` y galería de una columna). Dentro, los que **cambian** a partir de `600px` (título de `2rem` y dos columnas). La consulta solo **sobrescribe** lo que cambia.
4. **El límite se incluye.** MDN no lo dice con esas palabras, así que lo medimos: en una ventana de `599px` el título mide `24px` y la galería tiene una columna; en una de **`600px`** ya mide `32px` y hay dos columnas. `min-width: 600px` se cumple **desde** `600px`, inclusive.
5. **Los puntos de ruptura** son estos valores (`600px` en este ejemplo). Se escriben una vez y se repiten en todas las consultas del sitio, para que el diseño cambie en los mismos anchos.
6. **La consulta no sustituye a la preparación.** Para que `@media (min-width: 600px)` se comporte como se espera en un teléfono, la página necesita la etiqueta de la ventana de visualización (Ejemplos 07 y 08).

## ✅ Resultado esperado

| Ventana | `.galeria` | `.titulo` |
|---|---|---|
| `500px` | `500px` (una columna) | `24px` |
| `599px` | `599px` (una columna) | `24px` |
| `600px` | `292px 292px` (dos columnas) | `32px` |
| `800px` | `392px 392px` (dos columnas) | `32px` |

- La consulta se activa **exactamente** en `600px`.

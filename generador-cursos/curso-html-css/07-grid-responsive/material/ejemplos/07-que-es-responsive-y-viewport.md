# 📘 Ejemplo 07 — Qué es el diseño adaptable y la ventana de visualización

> 🎓 **Resultados de aprendizaje:** RA-4
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía abre su portafolio en el teléfono de una amiga y la página se corta. En `adaptable.html` compara dos cajas: una de ancho fijo y otra flexible, en tres tamaños de ventana (`500px`, `800px` y `1200px`).

## 💻 Código

El contenido de `adaptable.html` (dentro de `<main>`):

```html
<h2>Ancho fijo</h2>
<div class="fijo">Esta caja mide siempre 960px</div>

<h2>Ancho flexible</h2>
<div class="flexible">Esta caja usa el ancho disponible, hasta 960px</div>
```

La hoja `css/adaptable.css`:

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

.fijo,
.flexible {
  padding: 1rem 0;
  text-align: center;
}

/* Ancho fijo: en una ventana más angosta se sale de la pantalla */
.fijo {
  width: 960px;
  background-color: #fee2e2;
}

/* Ancho flexible: ocupa el ancho disponible y nunca pasa de 960px */
.flexible {
  max-width: 960px;
  background-color: #dcfce7;
}
```

## 🔍 Análisis paso a paso

1. **Qué es el diseño adaptable** (*responsive design*). Es un enfoque en el que **una misma página se acomoda** al tamaño y a las características del dispositivo: teléfono, tableta, computador o televisor. No son varios sitios: es uno solo que cambia.
2. **Por qué existe.** Hay pantallas de muchos tamaños. Una página pensada para `1200px` de ancho obliga a desplazarse de lado en una pantalla angosta, y eso es incómodo.
3. **La caja de ancho fijo.** `.fijo` tiene `width: 960px`. En una ventana de `500px` **sigue midiendo `960px`**: se sale de la pantalla y la página completa pasa a medir `960px` de ancho (`scrollWidth` `960`), con desplazamiento horizontal.
4. **La caja flexible.** `.flexible` usa `max-width: 960px` y ningún ancho fijo: ocupa el ancho disponible (`500px`, `800px`) y **nunca pasa de `960px`**. La página no se desborda.
5. **La ventana de visualización** (*viewport*) es la parte de la página que se ve en el dispositivo. Lo que mide `innerWidth` es su ancho: `500px`, `800px` o `1200px` en esta comprobación.
6. **La etiqueta `<meta name="viewport">`.** Mirá el `<head>` de `adaptable.html`: lleva `<meta name="viewport" content="width=device-width, initial-scale=1">`. En un **teléfono**, sin esa etiqueta el navegador dibuja la página en una ventana virtual más ancha (MDN da el ejemplo de `980px`) y la **reduce** para que quepa; con ella, usa el ancho real del dispositivo. Por eso MDN recomienda incluirla **siempre**.
7. **Un límite de esta comprobación.** El efecto de esa etiqueta solo ocurre en navegadores de teléfono y tableta. En un navegador de escritorio **no se nota**, así que acá no medimos ningún efecto: confiá en la descripción de MDN y probalo en tu teléfono si podés. Agregala a todas tus páginas desde ahora.

## ✅ Resultado esperado

| Medida | Ventana de `500px` | Ventana de `800px` | Ventana de `1200px` |
|---|---|---|---|
| `.fijo`, ancho | `960px` | `960px` | `960px` |
| `.flexible`, ancho | `500px` | `800px` | `960px` |
| Página completa (`scrollWidth`) | `960px` (se desborda) | `960px` (se desborda) | `1200px` (cabe) |

- En la ventana de `500px` aparece una barra de desplazamiento horizontal por culpa de `.fijo`.
- `.flexible` se ve completa en las tres ventanas.

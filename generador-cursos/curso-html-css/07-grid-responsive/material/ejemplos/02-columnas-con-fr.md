# 📘 Ejemplo 02 — Columnas con `fr`

> 🎓 **Resultados de aprendizaje:** RA-2
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía necesita distintos repartos de ancho: una barra lateral fija y un contenido flexible, una proporción de uno a dos, y un reparto por porcentajes. En `columnas.html` prueba cada forma de definir columnas con la ventana en `1200px` de ancho.

## 💻 Código

El contenido de `columnas.html` (dentro de `<main>`):

```html
<h2>Medidas fijas: 200px 300px 200px</h2>
<section class="fijas">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</section>

<h2>Fija y fracciones: 200px 1fr 1fr</h2>
<section class="mixta">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</section>

<h2>Fracciones desiguales: 1fr 2fr 1fr</h2>
<section class="fraccion">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</section>

<h2>Porcentajes: 25% 50% 25%</h2>
<section class="porcentaje">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</section>

<h2>Un elemento ancho dentro de 1fr 1fr 1fr</h2>
<section class="crece">
  <div class="item"><div class="ancho">Elemento de 600px</div></div>
  <div class="item">2</div>
  <div class="item">3</div>
</section>

<h2>Lo mismo con minmax(0, 1fr)</h2>
<section class="controlado">
  <div class="item"><div class="ancho">Elemento de 600px</div></div>
  <div class="item">2</div>
  <div class="item">3</div>
</section>
```

La hoja `css/columnas.css`:

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

.item {
  height: 60px;
  line-height: 60px;
  text-align: center;
  background-color: #dbeafe;
}

.item:nth-child(even) {
  background-color: #ccfbf1;
}

/* Medidas fijas: lo que sobra queda vacío a la derecha */
.fijas {
  display: grid;
  grid-template-columns: 200px 300px 200px;
}

/* fr reparte solo el espacio que sobra después de la columna fija */
.mixta {
  display: grid;
  grid-template-columns: 200px 1fr 1fr;
}

/* 2fr recibe el doble de espacio que 1fr */
.fraccion {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
}

/* Los porcentajes se calculan sobre el ancho del contenedor */
.porcentaje {
  display: grid;
  grid-template-columns: 25% 50% 25%;
}

/* Un elemento que no se puede achicar */
.ancho {
  width: 600px;
  background-color: #fee2e2;
}

/* 1fr nunca baja del tamaño mínimo de su contenido: la primera columna crece a 600px */
.crece {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}

/* minmax(0, 1fr) permite que la columna baje de ese mínimo: las tres miden lo mismo */
.controlado {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
}
```

## 🔍 Análisis paso a paso

1. **Medidas fijas.** `200px 300px 200px` crea tres columnas de esos anchos. Suman `700px`: sobran `500px` a la derecha, que quedan vacíos.
2. **La unidad `fr`** (*fraction*, fracción). Una pista en `fr` toma una **parte proporcional del espacio libre**. `1fr 1fr` reparte el espacio libre en dos partes iguales.
3. **Mezclar fijas y `fr`.** En `200px 1fr 1fr`, primero se descuentan los `200px` de la columna fija; los `1000px` que sobran se reparten: `500px` y `500px`. **`fr` reparte solo lo que sobra.**
4. **Fracciones desiguales.** En `1fr 2fr 1fr` hay `1 + 2 + 1 = 4` partes: cada parte vale `1200 ÷ 4 = 300px`, así que las columnas miden `300px`, `600px` y `300px`.
5. **Porcentajes.** `25% 50% 25%` da lo mismo en este caso (`300px 600px 300px`), pero un porcentaje se calcula sobre el ancho del contenedor y **no** descuenta huecos. En una prueba aparte, con `gap: 16px`, `25% 50% 25%` mide `1232px` de ancho total (`1200 + 32`) y se sale de la ventana; con `1fr 2fr 1fr` las columnas bajan a `292px 584px 292px` y todo cabe.
6. **Un elemento ancho.** `1fr` en realidad es `minmax(auto, 1fr)`: la columna **no baja del tamaño mínimo de su contenido**. Si un elemento mide `600px` y no se puede achicar, `.crece` queda en `600px 300px 300px`: la primera columna se llevó más de lo previsto.
7. **Cómo evitarlo.** `minmax(0, 1fr)` permite que la columna baje de ese mínimo: `.controlado` queda en `400px 400px 400px` y el elemento ancho **sobresale** de su columna (mide `600px` en una de `400px`). Elegí entre las dos según quieras que la columna crezca o que el contenido sobresalga.

## ✅ Resultado esperado

| Contenedor | Columnas escritas | Columnas calculadas (ventana de `1200px`) |
|---|---|---|
| `.fijas` | `200px 300px 200px` | `200px 300px 200px` |
| `.mixta` | `200px 1fr 1fr` | `200px 500px 500px` |
| `.fraccion` | `1fr 2fr 1fr` | `300px 600px 300px` |
| `.porcentaje` | `25% 50% 25%` | `300px 600px 300px` |
| `.crece` | `1fr 1fr 1fr` con un elemento de `600px` | `600px 300px 300px` |
| `.controlado` | `repeat(3, minmax(0, 1fr))` | `400px 400px 400px` |

- Las tres primeras filas de la tabla suman `1200px` (salvo `.fijas`, que suma `700px`).

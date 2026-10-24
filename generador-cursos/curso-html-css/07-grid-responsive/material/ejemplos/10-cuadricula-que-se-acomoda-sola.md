# 📘 Ejemplo 10 — Una cuadrícula que se acomoda sola

> 🎓 **Resultados de aprendizaje:** RA-6
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía descubre que puede lograr una galería adaptable **sin escribir ninguna consulta de medios**. En `acomoda-sola.html` usa `repeat(auto-fit, minmax(200px, 1fr))` con seis y con tres elementos.

## 💻 Código

El contenido de `acomoda-sola.html` (dentro de `<main>`):

```html
<h2>auto-fit con seis elementos</h2>
<section class="fit">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</section>

<h2>auto-fit con tres elementos</h2>
<section class="fit-pocos">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</section>

<h2>auto-fill con tres elementos</h2>
<section class="fill-pocos">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</section>
```

La hoja `css/acomoda-sola.css`:

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

/* Tantas columnas de 200px como quepan; las columnas vacías se pliegan y el espacio se reparte */
.fit,
.fit-pocos {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 16px;
}

/* Con auto-fill las columnas vacías se conservan: los tres elementos no se estiran */
.fill-pocos {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 16px;
}
```

## 🔍 Análisis paso a paso

1. **`auto-fit` y `auto-fill`.** En lugar de un número fijo de columnas, `repeat(auto-fit, minmax(200px, 1fr))` significa «poné **tantas columnas de al menos `200px` como quepan**». El navegador calcula el número según el ancho disponible.
2. **La cuenta.** Con `gap: 16px`: en `500px` caben `2` columnas de `242px`; en `800px`, `3` de `256px`; en `1200px`, `5` de `227.2px`. Es decir, `n = ⌊(ancho + hueco) ÷ (mínimo + hueco)⌋`. Las columnas luego se estiran (`1fr`) para llenar el ancho.
3. **Sin consultas de medios.** El mismo CSS da 2, 3 y 5 columnas: la cuadrícula **se acomoda sola**. Por eso suele ser suficiente para galerías de tarjetas iguales.
4. **`auto-fit` frente a `auto-fill`.** Se diferencian cuando hay **pocos elementos**. Con tres elementos en `1200px`: `auto-fit` **pliega** las columnas vacías y estira las tres que se usan (`389.33px` cada una, y dos pistas de `0px`); `auto-fill` **conserva** las vacías y los tres elementos no se estiran (cinco columnas de `227.2px`, dos vacías).
5. **Cuándo alcanza.** Alcanza para galerías y listas de tarjetas con el mismo tamaño. **No alcanza** si querés una disposición distinta (por ejemplo, mover un menú de lugar o cambiar el orden de bloques): ahí hace falta una consulta de medios (Ejemplos 11 a 13).

## ✅ Resultado esperado

| Contenedor | Ventana de `500px` | Ventana de `800px` | Ventana de `1200px` |
|---|---|---|---|
| `.fit` (6 elementos) | `242px` ×2 | `256px` ×3 | `227.2px` ×5 |
| `.fit-pocos` (`auto-fit`, 3 elementos) | `242px` ×2 | `256px` ×3 | `389.33px` ×3 y dos pistas de `0px` |
| `.fill-pocos` (`auto-fill`, 3 elementos) | `242px` ×2 | `256px` ×3 | `227.2px` ×5 (dos vacías) |

- Con pocos elementos, `auto-fit` los estira para llenar la fila y `auto-fill` los deja en su tamaño.

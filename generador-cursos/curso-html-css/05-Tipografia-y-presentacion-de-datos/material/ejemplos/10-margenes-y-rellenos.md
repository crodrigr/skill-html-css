# 📘 Ejemplo 10 — Márgenes y rellenos

> 🕐 **Sesión 2** · 🎓 **Resultados de aprendizaje:** RA-8 (y repasa RA-6 y RA-7)

## 🧱 Situación inicial

Lucía necesita separar sus bloques unos de otros (**márgenes**) y dar aire al contenido dentro de cada bloque (**rellenos**). Quiere dominar las abreviaturas de uno a cuatro
valores, centrar una caja, entender por qué dos márgenes verticales no se suman y juntar todo en una tarjeta. Lo practica en `espacios.html`.

## 💻 Código

El contenido de `espacios.html` (dentro de `<main>`):

```html
<h2>Márgenes: de uno a cuatro valores</h2>
<div class="bloque margen-1">margin: 10px</div>
<div class="bloque margen-2">margin: 10px 20px</div>
<div class="bloque margen-3">margin: 5px 10px 15px</div>
<div class="bloque margen-4">margin: 5px 10px 15px 20px</div>

<h2>Rellenos: de uno a cuatro valores</h2>
<div class="bloque relleno-1">padding: 10px</div>
<div class="bloque relleno-2">padding: 10px 20px</div>
<div class="bloque relleno-3">padding: 5px 10px 15px</div>
<div class="bloque relleno-4">padding: 5px 10px 15px 20px</div>

<h2>Centrar una caja</h2>
<div class="bloque centrada">margin: 0 auto</div>

<h2>Colapso de márgenes</h2>
<div class="bloque apilada apilada--arriba">Margen inferior: 30px</div>
<div class="bloque apilada apilada--abajo">Margen superior: 20px</div>

<h2>Todo junto: una tarjeta</h2>
<article class="tarjeta">
  <h3 class="tarjeta__titulo">Proyecto del mes</h3>
  <p>Una tarjeta con un borde distinto por lado, dos esquinas redondeadas, relleno y margen.</p>
</article>
```

La hoja `css/espacios.css`:

```css
/* Cada bloque tiene un fondo para ver su tamaño */
.bloque {
  background-color: #dbeafe;
}

/* Márgenes con uno a cuatro valores */
.margen-1 {
  margin: 10px;
}

.margen-2 {
  margin: 10px 20px;
}

.margen-3 {
  margin: 5px 10px 15px;
}

.margen-4 {
  margin: 5px 10px 15px 20px;
}

/* Rellenos con uno a cuatro valores */
.relleno-1 {
  padding: 10px;
}

.relleno-2 {
  padding: 10px 20px;
}

.relleno-3 {
  padding: 5px 10px 15px;
}

.relleno-4 {
  padding: 5px 10px 15px 20px;
}

/* Centrar: ancho fijo y márgenes laterales automáticos */
.centrada {
  width: 200px;
  margin: 0 auto;
}

/* Dos bloques apilados: los márgenes verticales colapsan */
.apilada {
  height: 40px;
}

.apilada--arriba {
  margin-bottom: 30px;
}

.apilada--abajo {
  margin-top: 20px;
}

/* La tarjeta: borde distinto por lado, dos esquinas redondeadas, relleno y margen */
.tarjeta {
  width: 320px;
  box-sizing: border-box;
  border-top: 4px solid #1e3a8a;
  border-right: 1px solid #94a3b8;
  border-bottom: 4px double #1e3a8a;
  border-left: 1px solid #94a3b8;
  border-radius: 16px 0;
  padding: 20px 24px;
  margin: 16px auto;
  background-color: #ffffff;
}
```

## 🔍 Análisis paso a paso

1. **Margen y relleno.** `margin` es el espacio **fuera** del borde; `padding`, el espacio **dentro**. El fondo de un elemento se extiende bajo el relleno, no bajo el margen.
2. **Uno a cuatro valores.** Las dos propiedades usan la misma notación:
   - **1 valor**: los cuatro lados (`10px`).
   - **2 valores**: el primero para arriba y abajo; el segundo, para izquierda y derecha (`10px 20px`).
   - **3 valores**: arriba; izquierda y derecha; abajo (`5px 10px 15px`).
   - **4 valores**: arriba, derecha, abajo, izquierda, en el sentido de las agujas del reloj (`5px 10px 15px 20px`).
3. **Un atajo para recordarlo.** Los valores recorren la caja **como un reloj**, empezando por arriba. Si faltan valores, los lados que faltan copian a su opuesto.
4. **Valores negativos.** Un margen admite valores negativos, que acercan el elemento a sus vecinos; un relleno no (son inválidos).
5. **Centrar con `auto`.** `margin: 0 auto` con un `width` fijo reparte el espacio sobrante entre los márgenes izquierdo y derecho: la caja queda centrada. Sin `width`,
   la caja ya ocupa todo el ancho y no hay espacio que repartir.
6. **Colapso de márgenes.** Los márgenes **verticales** contiguos de dos hermanos no se suman: se combinan en uno solo, del tamaño del **mayor**. Acá, `30px` y `20px` dejan **30px**
   entre las cajas, no 50. Solo ocurre en vertical; los márgenes horizontales sí se suman.
7. **Cuándo no colapsan.** MDN señala varios casos en los que no hay colapso: elementos flotantes o con posición absoluta (fuera de esta clase) y contenedores `flex` o `grid`
   (que se ven más adelante).
8. **La tarjeta.** Junta lo aprendido: bordes distintos por lado (`4px solid` arriba, `1px solid` a los lados, `4px double` abajo), esquinas redondeadas de `16px` arriba a la
   izquierda y abajo a la derecha (`16px 0`), relleno `20px 24px` y margen `16px auto` con un ancho de `320px`. Como usa `box-sizing: border-box`, la tarjeta mide **320px** de borde a borde.

## ✅ Resultado esperado

| Clase | Propiedad | Arriba / derecha / abajo / izquierda |
|---|---|---|
| `.margen-1` | `margin` | 10 / 10 / 10 / 10 |
| `.margen-2` | `margin` | 10 / 20 / 10 / 20 |
| `.margen-3` | `margin` | 5 / 10 / 15 / 10 |
| `.margen-4` | `margin` | 5 / 10 / 15 / 20 |
| `.relleno-4` | `padding` | 5 / 10 / 15 / 20 |
| `.relleno-3` | `padding` (abajo / izquierda) | 15 / 10 |

| Medida | Valor |
|---|---|
| `.centrada` (márgenes izquierdo y derecho) | iguales entre sí (el espacio sobrante, repartido en partes iguales) |
| Separación entre `.apilada--arriba` y `.apilada--abajo` | **30px** |
| `.tarjeta` de borde a borde (`offsetWidth`) | **320px** |
| `.tarjeta` esquinas (arriba-izquierda, arriba-derecha, abajo-derecha, abajo-izquierda) | 16, 0, 16, 0 |
| `.tarjeta` relleno (arriba / izquierda) | 20px / 24px |

- Los dos bloques apilados se ven separados por 30px, aunque sus márgenes sumen 50px.
- La tarjeta se ve con un marco doble abajo, dos esquinas curvas y centrada en la página.

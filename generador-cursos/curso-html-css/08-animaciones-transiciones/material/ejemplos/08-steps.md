# 📘 Ejemplo 08 — La función `steps()`

> 🎓 **Resultados de aprendizaje:** RA-6
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere que una caja avance como las agujas de un reloj: a saltos, no de forma continua. En `pasos.html` prueba `steps()` con cuatro intervalos y distintas posiciones del salto.

## 💻 Código

El contenido de `pasos.html` (dentro de `<main>`):

```html
<h2>steps(4, end)</h2>
<div class="pista"><div class="caja fin"></div></div>

<h2>steps(4, start)</h2>
<div class="pista"><div class="caja inicio"></div></div>

<h2>steps(4, jump-none)</h2>
<div class="pista"><div class="caja sin-saltos"></div></div>

<h2>steps(1, end)</h2>
<div class="pista"><div class="caja un-paso"></div></div>
```

La hoja `css/pasos.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* La pista de 300px por la que se mueve la caja de 100px (recorre 200px) */
.pista {
  width: 300px;
  margin-bottom: 0.75rem;
  background-color: #e5e7eb;
}

.caja {
  width: 100px;
  height: 40px;
  background-color: #2563eb;
}

/* Al pasar el cursor sobre la pista, la caja se desplaza 200px */
.pista:hover .caja {
  transform: translateX(200px);
}

/* Cuatro saltos; el salto ocurre al FINAL de cada intervalo (el valor por defecto) */
.fin {
  transition: transform 2s steps(4, end);
}

/* Cuatro saltos; el salto ocurre al PRINCIPIO de cada intervalo */
.inicio {
  transition: transform 2s steps(4, start);
}

/* Cuatro intervalos sin salto en los extremos: se ven los dos extremos y dos valores intermedios */
.sin-saltos {
  transition: transform 2s steps(4, jump-none);
}

/* Un solo paso: la caja espera toda la duración y salta al final */
.un-paso {
  transition: transform 2s steps(1, end);
}
```

## 🔍 Análisis paso a paso

1. **Qué es.** `steps(n, posición)` divide la duración en `n` **intervalos iguales** y mantiene el valor **constante dentro de cada uno**: el cambio ocurre en **saltos**, no de forma continua.
2. **`steps(4, end)`** (el valor por defecto de la posición). El salto ocurre **al final** de cada intervalo. En una duración de `2s`, la caja vale `0px` entre `0` y `500 ms`, `50px` entre `500` y `1000 ms`, `100px` entre `1000` y `1500 ms` y `150px` entre `1500` y `2000 ms`; solo llega a `200px` al terminar.
3. **`steps(4, start)`.** El salto ocurre **al principio** de cada intervalo: arranca ya en `50px` y llega a `200px` antes del final (`200px` entre `1500` y `2000 ms`).
4. **`steps(4, jump-none)`.** No hay salto en los extremos: la caja muestra los **dos extremos** y los valores intermedios en partes iguales: `0px`, `66.7px`, `133.3px` y `200px`.
5. **`steps(1, end)`.** Un solo paso: la caja se queda en `0px` toda la duración y salta a `200px` al terminar.
6. **Dónde se mide.** Justo en el borde de un salto el valor ya cambió (a los `500 ms`, `steps(4, end)` ya vale `50px`). Por eso los valores de la tabla se midieron en el **medio de cada intervalo**.
7. **Para qué sirve.** Relojes y contadores, animaciones de «escritura a máquina», y animaciones cuadro a cuadro con una imagen que contiene varias poses (*sprite*). Para un movimiento natural, usá una curva.

## ✅ Resultado esperado

| Función | `250 ms` | `750 ms` | `1250 ms` | `1750 ms` |
|---|---|---|---|---|
| `steps(4, end)` | `0px` | `50px` | `100px` | `150px` |
| `steps(4, start)` | `50px` | `100px` | `150px` | `200px` |
| `steps(4, jump-none)` | `0px` | `66.7px` | `133.3px` | `200px` |
| `steps(1, end)` | `0px` | `0px` | `0px` | `0px` |

- Las cajas avanzan «a tirones»: cuatro saltos en `2s`, uno cada `500 ms`.

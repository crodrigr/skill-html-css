# 📘 Ejemplo 10 — Repeticiones y dirección

> 🎓 **Resultados de aprendizaje:** RA-7
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere que un indicador se repita varias veces, que vaya y vuelva sin parar y que espere antes de empezar. En `repeticiones.html` mueve cuatro cajas por una pista y mide su posición cada medio segundo.

## 💻 Código

El contenido de `repeticiones.html` (dentro de `<main>`):

```html
<h2>Tres repeticiones</h2>
<div class="pista"><div class="caja tres"></div></div>

<h2>Infinitas y alternadas</h2>
<div class="pista"><div class="caja alterna"></div></div>

<h2>Con retardo</h2>
<div class="pista"><div class="caja retardo"></div></div>

<h2>Media repetición</h2>
<div class="pista"><div class="caja media"></div></div>
```

La hoja `css/repeticiones.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

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

/* La secuencia: la caja se mueve de 0 a 100px */
@keyframes mover {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(100px);
  }
}

/* Tres veces, cada una de 1s; después vuelve a su lugar */
.tres {
  animation-name: mover;
  animation-duration: 1s;
  animation-timing-function: linear;
  animation-iteration-count: 3;
}

/* Sin fin; la dirección alterna: va, vuelve, va, vuelve... */
.alterna {
  animation-name: mover;
  animation-duration: 1s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}

/* Espera 1s antes de empezar */
.retardo {
  animation-name: mover;
  animation-duration: 1s;
  animation-timing-function: linear;
  animation-delay: 1s;
}

/* 0.5 repeticiones: se reproduce solo la mitad de la secuencia */
.media {
  animation-name: mover;
  animation-duration: 1s;
  animation-timing-function: linear;
  animation-iteration-count: 0.5;
}
```

## 🔍 Análisis paso a paso

1. **`animation-iteration-count`** dice **cuántas veces** se reproduce la secuencia (por defecto, `1`). `.tres` usa `3`: la caja hace el recorrido de `0` a `100px` **tres veces** y, entre una y otra, **vuelve de golpe** al principio (a los `1000 ms` está en `0` y empieza de nuevo).
2. **Cuando termina, vuelve a su aspecto.** Pasados los `3000 ms` la animación ya no se aplica y la caja usa su estado normal (`transform: none`), porque no hay modo de relleno (Ejemplo 11).
3. **`infinite`.** `animation-iteration-count: infinite` repite **sin fin**. Es el valor para indicadores de carga, pero puede molestar a quien es sensible al movimiento (Ejemplo 15).
4. **`animation-direction`.** Por defecto (`normal`) cada vuelta empieza de nuevo. Con `alternate` la **segunda vuelta va hacia atrás**, la tercera hacia adelante, y así: en `.alterna` la caja va `0 → 100px` (a los `1000 ms` está en `100px`), luego `100px → 0` (a los `2000 ms`, en `0`), y se repite. El movimiento es continuo, sin saltos.
5. **`animation-delay`.** Espera antes de empezar. `.retardo` tiene `1s`: a los `0` y `500 ms` la caja sigue en su aspecto normal (`none`); empieza a los `1000 ms` y a los `1500 ms` ya va en `50px`. El retardo **no se repite** en cada vuelta.
6. **Valores no enteros.** `animation-iteration-count: 0.5` reproduce **solo la mitad** de la secuencia. `.media` llega a `49.9px` justo antes de los `500 ms` y, al terminar, vuelve a su lugar. MDN aclara que los valores negativos no son válidos.
7. **Para qué sirve cada uno.** Un número exacto para avisos (parpadear tres veces); `infinite` y `alternate` para indicadores continuos (latir, flotar); el retardo para escalonar la aparición de varios elementos.

## ✅ Resultado esperado

| Caja | `0 ms` | `500 ms` | `1000 ms` | `1500 ms` | `2000 ms` | `2500 ms` | `3000 ms` | `3500 ms` | `4000 ms` |
|---|---|---|---|---|---|---|---|---|---|
| `.tres` | `0` | `50` | `0` | `50` | `0` | `50` | `none` | `none` | `none` |
| `.alterna` | `0` | `50` | `100` | `50` | `0` | `50` | `100` | `50` | `0` |
| `.retardo` | `none` | `none` | `0` | `50` | `none` | `none` | `none` | `none` | `none` |

(Valores de `translateX` en píxeles; `none` es el aspecto normal, sin animación.)

- `.media` (`0.5` repeticiones): `100 ms` → `10px`, `250 ms` → `25px`, `400 ms` → `40px`, `499 ms` → `49.9px` y a los `500 ms` ya terminó (`none`).

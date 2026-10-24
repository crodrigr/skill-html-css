# 📘 Ejemplo 11 — Relleno y estado de reproducción

> 🎓 **Resultados de aprendizaje:** RA-7
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía anima una caja que crece, pero al terminar vuelve a su tamaño original y durante la espera se ve distinta de lo que esperaba. En `relleno.html` prueba los cuatro modos de `animation-fill-mode` y el estado de reproducción.

## 💻 Código

El contenido de `relleno.html` (dentro de `<main>`):

```html
<h2>none (el valor por defecto)</h2>
<div class="caja c-none"></div>

<h2>forwards</h2>
<div class="caja c-forwards"></div>

<h2>backwards</h2>
<div class="caja c-backwards"></div>

<h2>both</h2>
<div class="caja c-both"></div>

<h2>animation-play-state: paused</h2>
<div class="caja c-pausada"></div>
```

La hoja `css/relleno.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.caja {
  width: 100px;
  height: 40px;
  margin-bottom: 1.5rem;
  background-color: #2563eb;
}

/* La secuencia: la caja pasa de la mitad de su tamaño al doble */
@keyframes crecer {
  from {
    transform: scale(0.5);
  }

  to {
    transform: scale(2);
  }
}

/* Todas duran 1s y esperan 1s antes de empezar; solo cambia animation-fill-mode */
.c-none,
.c-forwards,
.c-backwards,
.c-both,
.c-pausada {
  animation-name: crecer;
  animation-duration: 1s;
  animation-timing-function: linear;
  animation-delay: 1s;
}

/* none: antes y después la caja tiene su aspecto normal */
.c-none {
  animation-fill-mode: none;
}

/* forwards: al terminar conserva el último paso */
.c-forwards {
  animation-fill-mode: forwards;
}

/* backwards: durante el retardo ya muestra el primer paso */
.c-backwards {
  animation-fill-mode: backwards;
}

/* both: las dos cosas */
.c-both {
  animation-fill-mode: both;
}

/* paused: la animación queda detenida donde está (acá, sin haber empezado) */
.c-pausada {
  animation-play-state: paused;
}
```

## 🔍 Análisis paso a paso

1. **La secuencia.** `crecer` lleva la caja de `scale(0.5)` (la mitad de su tamaño) a `scale(2)` (el doble) en `1s`, después de un retardo de `1s`. Las cinco cajas solo difieren en `animation-fill-mode` (y una, en `animation-play-state`).
2. **`none`** (por defecto). Antes y después de la animación, la caja tiene su aspecto normal: durante el retardo y tras el final, `transform: none`.
3. **`backwards`.** Durante el **retardo** la caja ya muestra el **primer paso** (`scale(0.5)`) en lugar de su aspecto normal; al terminar, vuelve a `none`.
4. **`forwards`.** Al terminar, la caja **conserva el último paso** (`scale(2)`); durante el retardo, tiene su aspecto normal.
5. **`both`.** Las dos cosas: muestra el primer paso durante el retardo y conserva el último al final.
6. **Durante la animación** (a los `1500 ms`, a la mitad) las cuatro cajas son iguales: `scale(1.25)`, el punto medio entre `0.5` y `2`.
7. **`animation-play-state`.** `running` (por defecto) reproduce la animación; `paused` la **detiene donde está** y, al volver a `running`, continúa desde ahí, no desde el principio. `.c-pausada` está en `paused` desde el principio: la animación existe pero no avanza.
8. **Cuándo usar relleno.** Para animaciones de **entrada**, `both` o `backwards` evitan el «parpadeo» del elemento visible antes de empezar; para que el elemento se **quede** como terminó, `forwards`.

## ✅ Resultado esperado

| Caja | `500 ms` (en el retardo) | `1500 ms` (a mitad) | `3000 ms` (después del final) |
|---|---|---|---|
| `.c-none` | `none` | `scale(1.25)` | `none` |
| `.c-forwards` | `none` | `scale(1.25)` | `scale(2)` |
| `.c-backwards` | `scale(0.5)` | `scale(1.25)` | `none` |
| `.c-both` | `scale(0.5)` | `scale(1.25)` | `scale(2)` |

- Estado de las animaciones sin tocar el tiempo: cuatro `running` y la de `.c-pausada`, `paused`; `animation-play-state` calculado: `running` y `paused`.
- Visualmente: la caja `both` aparece pequeña desde el principio, crece y queda grande.

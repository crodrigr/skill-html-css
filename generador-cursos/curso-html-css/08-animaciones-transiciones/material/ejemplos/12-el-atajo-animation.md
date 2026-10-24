# 📘 Ejemplo 12 — El atajo `animation`

> 🎓 **Resultados de aprendizaje:** RA-7
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía lleva siete líneas por cada animación. En `atajo-animation.html` compara la forma larga con el atajo `animation` y escribe dos animaciones en una sola declaración.

## 💻 Código

El contenido de `atajo-animation.html` (dentro de `<main>`):

```html
<h2>Con las propiedades por separado</h2>
<div class="tarjeta largo">Tarjeta</div>

<h2>Con el atajo</h2>
<div class="tarjeta corto">Tarjeta</div>

<h2>Dos animaciones en una declaración</h2>
<div class="tarjeta dos">Tarjeta</div>
```

La hoja `css/atajo-animation.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.tarjeta {
  width: 300px;
  padding: 1rem;
  margin-bottom: 0.5rem;
  background-color: #dbeafe;
}

@keyframes aparecer {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

@keyframes latir {
  from {
    transform: scale(1);
  }

  to {
    transform: scale(1.1);
  }
}

/* Todas las propiedades por separado */
.largo {
  animation-name: aparecer;
  animation-duration: 2s;
  animation-timing-function: ease-out;
  animation-delay: 0.5s;
  animation-iteration-count: 2;
  animation-direction: alternate;
  animation-fill-mode: both;
}

/* Lo mismo con el atajo: duración, función, retardo, repeticiones, dirección, relleno y nombre (el nombre, al final) */
.corto {
  animation: 2s ease-out 0.5s 2 alternate both aparecer;
}

/* Dos animaciones separadas por coma: cada una con sus valores */
.dos {
  animation:
    1s ease-out aparecer,
    2s linear 1s infinite alternate latir;
}
```

## 🔍 Análisis paso a paso

1. **El atajo** reúne las propiedades de animación en una declaración: `animation: 2s ease-out 0.5s 2 alternate both aparecer;`. Reúne la duración, la función de tiempo, el retardo, las repeticiones, la dirección, el relleno, el estado y el nombre.
2. **Duración y retardo.** Como en `transition`, el **primer** tiempo es la **duración** y el **segundo** es el **retardo**: `2s ... 0.5s` es duración `2s`, retardo `0.5s`.
3. **El nombre, al final.** MDN recomienda escribir el nombre **último**: si algún valor del atajo se puede entender como otra propiedad (por ejemplo, un nombre que coincide con una palabra clave), se usa para esa propiedad y no como nombre.
4. **Misma animación, mismo resultado.** Las propiedades calculadas de `.largo` (siete propiedades) y de `.corto` (atajo) son idénticas: `aparecer`, `2s`, `ease-out`, `0.5s`, `2`, `alternate`, `both`.
5. **Los valores que no escribís** toman su valor por defecto: sin función vale `ease`; sin retardo, `0s`; sin repeticiones, `1`; sin dirección, `normal`; sin relleno, `none`.
6. **Dos animaciones.** `.dos` separa dos animaciones por coma: `aparecer` (`1s`, `ease-out`) y `latir` (`2s`, lineal, retardo `1s`, infinita y alternada). Las propiedades calculadas son listas en el mismo orden: `aparecer, latir`; `1s, 2s`; `ease-out, linear`; `0s, 1s`; `1, infinite`.
7. **Un detalle del relleno.** En `.corto` la animación dura `2` vueltas alternadas con relleno `both`. A los `1500 ms` la opacidad es `0.68`; a los `2500 ms`, `1`; a los `3500 ms`, `0.68` (va hacia atrás) y a los `4500 ms` termina en `0`: el **último paso de la segunda vuelta (hacia atrás) es `from`**, y con `forwards` la tarjeta queda **invisible**. Pensá cuántas vueltas y en qué sentido terminan.

## ✅ Resultado esperado

| Tarjeta | `animation-name` | `duration` | `timing-function` | `delay` | `iteration-count` | `direction` | `fill-mode` |
|---|---|---|---|---|---|---|---|
| `.largo` (por separado) | `aparecer` | `2s` | `ease-out` | `0.5s` | `2` | `alternate` | `both` |
| `.corto` (atajo) | `aparecer` | `2s` | `ease-out` | `0.5s` | `2` | `alternate` | `both` |
| `.dos` (dos animaciones) | `aparecer, latir` | `1s, 2s` | `ease-out, linear` | `0s, 1s` | `1, infinite` | `normal, alternate` | `none, none` |

- Opacidad de `.corto`: `0 ms` → `0`; `500 ms` → `0` (fin del retardo); `1500 ms` → `0.68`; `2500 ms` → `1`; `3500 ms` → `0.68`; `4500 ms` → `0`; `6000 ms` → `0`.

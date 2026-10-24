# 📘 Ejemplo 14 — Selectores porcentuales

> 🎓 **Resultados de aprendizaje:** RA-8
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere una bolita que **rebote**: sube, baja, sube un poco menos y baja. Eso no cabe en dos pasos. En `porcentajes.html` define cinco pasos con porcentajes.

## 💻 Código

El contenido de `porcentajes.html` (dentro de `<main>`):

```html
<h2>Rebote lineal</h2>
<div class="zona"><div class="bola rebote-lineal"></div></div>

<h2>Rebote suave (ease-in-out en cada tramo)</h2>
<div class="zona"><div class="bola rebote-suave"></div></div>

<h2>Pasos repetidos con una lista</h2>
<div class="zona"><div class="bola rebote-lista"></div></div>
```

La hoja `css/porcentajes.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.zona {
  height: 100px;
  padding-top: 70px;
  margin-bottom: 0.5rem;
  background-color: #e5e7eb;
}

.bola {
  width: 30px;
  height: 30px;
  background-color: #2563eb;
}

/* Cinco pasos: cada uno ocurre a un porcentaje de la duración (2s → 0, 0.5s, 1s, 1.5s y 2s) */
@keyframes rebote {
  0% {
    transform: translateY(0);
  }

  25% {
    transform: translateY(-60px);
  }

  50% {
    transform: translateY(0);
  }

  75% {
    transform: translateY(-30px);
  }

  100% {
    transform: translateY(0);
  }
}

.rebote-lineal {
  animation-name: rebote;
  animation-duration: 2s;
  animation-timing-function: linear;
}

/* La función de tiempo se aplica entre cada par de pasos, no en toda la animación */
.rebote-suave {
  animation-name: rebote;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
}

/* Una lista de porcentajes comparte el mismo bloque: 0%, 50% y 100% valen lo mismo */
@keyframes rebote-simple {
  0%,
  50%,
  100% {
    transform: translateY(0);
  }

  25% {
    transform: translateY(-60px);
  }

  75% {
    transform: translateY(-30px);
  }
}

.rebote-lista {
  animation-name: rebote-simple;
  animation-duration: 2s;
  animation-timing-function: linear;
}
```

## 🔍 Análisis paso a paso

1. **Los porcentajes.** Cada paso se escribe como un porcentaje de la **duración total**: `0%` es el principio y `100%` el final. Con una duración de `2s`, `25%` ocurre a los `0.5s`, `50%` a `1s` y `75%` a `1.5s`.
2. **El rebote.** `rebote` tiene cinco pasos: `0%` en `0`, `25%` en `-60px` (arriba, porque `translateY` negativo sube), `50%` en `0`, `75%` en `-30px` (un segundo rebote, más bajo) y `100%` en `0`. Medido: a los `0`, `500`, `1000`, `1500` y `2000 ms` la bolita vale exactamente `0`, `-60`, `0`, `-30` y `0`.
3. **Entre dos pasos, el navegador calcula.** Con `animation-timing-function: linear`, el valor entre pasos va en línea recta: a los `250 ms` está a mitad de camino (`-30px`); a los `125 ms`, a un cuarto (`-15px`).
4. **La función de tiempo se aplica entre cada par de pasos**, no a toda la animación. `.rebote-suave` usa `ease-in-out` y a los `125 ms` (un cuarto del primer tramo) está en `-7.75px`, bastante menos que los `-15px` de la lineal; a los `250 ms` vale `-30px` y a los `375 ms`, `-52.25px`. En cada paso clave los valores coinciden: `-60px` a los `500 ms`.
5. **Pasos con el mismo estilo.** `rebote-simple` agrupa `0%, 50%, 100%` en una **lista separada por comas** porque valen lo mismo (`translateY(0)`). Es equivalente a `rebote` y da los mismos valores.
6. **El orden no importa.** MDN dice que los porcentajes se pueden escribir en cualquier orden: el navegador los procesa en el orden en que ocurren. Aun así, conviene escribirlos de menor a mayor.
7. **Terminar.** Sin relleno, a los `2000 ms` la animación terminó y la bolita vuelve a su aspecto normal (`none`).

## ✅ Resultado esperado

| Instante | `.rebote-lineal` | `.rebote-suave` | `.rebote-lista` |
|---|---|---|---|
| `0 ms` (`0%`) | `0px` | `0px` | `0px` |
| `125 ms` | `-15px` | `-7.75px` | — |
| `250 ms` | `-30px` | `-30px` | `-30px` |
| `375 ms` | — | `-52.25px` | — |
| `500 ms` (`25%`) | `-60px` | `-60px` | `-60px` |
| `750 ms` | `-30px` | — | `-30px` |
| `1000 ms` (`50%`) | `0px` | — | `0px` |
| `1500 ms` (`75%`) | `-30px` | — | `-30px` |
| `2000 ms` (`100%`) | termina (`none`) | — | termina (`none`) |

(Valores de `translateY`.)

- La bolita sube a `60px`, baja, sube a `30px` y baja: dos rebotes decrecientes en dos segundos.

# 🔑 Soluciones — Ejercicios de la Clase 08 (material docente)

No compartir este archivo con los estudiantes. Cada hoja se probó en Chrome sobre la página de partida del ejercicio: pasa `validar_css.py` y cumple los valores de su tabla o de sus casos de prueba, fijando el instante de cada transición o animación (y simulando el cursor o el movimiento reducido cuando el ejercicio lo pide).

---

## 🟢 Básico 01 — Tus primeras transiciones

**Hoja.**

```css
/* Tamaño base */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.boton {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  margin-bottom: 1rem;
  color: #ffffff;
  background-color: #16a34a;
  text-decoration: none;
}

/* Al pasar el cursor: fondo gris oscuro y opacidad 0.6 */
.boton:hover {
  background-color: #111827;
  opacity: 0.6;
}

/* 1. Las cuatro propiedades por separado */
.boton-a {
  transition-property: background-color;
  transition-duration: 0.4s;
  transition-timing-function: ease-in;
  transition-delay: 0.2s;
}

/* 2. Lo mismo con el atajo */
.boton-b {
  transition: background-color 0.4s ease-in 0.2s;
}

/* 3. Dos transiciones en una declaración, cada una con sus valores */
.boton-c {
  transition: background-color 0.3s, opacity 1s ease-out 0.2s;
}
```

**Medidas comprobadas.** `.boton-a` y `.boton-b`: `background-color`, `0.4s`, `ease-in`, `0.2s`. `.boton-c`: `background-color, opacity`, `0.3s, 1s`, `ease, ease-out`, `0s, 0.2s`. Fondo de `.boton-a` con el cursor: `100 ms` `rgb(22, 163, 74)`, `400 ms` `rgb(20, 119, 63)`, `600 ms` `rgb(17, 24, 39)`. `.boton-c`: a los `300 ms` el fondo ya terminó y la opacidad vale `0.94`; a los `700 ms`, `0.73`; a los `1200 ms`, `0.6`. Sin la solución: `transition-duration` `0s` y ninguna transición activa.

**Parte B.**

1. Por el orden: el **primer** valor de tiempo es la duración (`0.4s`) y el **segundo** es el retardo (`0.2s`).
2. Sin duración vale `0s`: no hay transición y el cambio es instantáneo.
3. Termina primero el fondo (`0.3s`); la opacidad dura `1s` y además espera `0.2s`, así que termina a los `1.2s`.

---

## 🟢 Básico 02 — Entrada, salida y ritmo

**Hoja.**

```css
/* Tamaño base */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.boton {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  margin-bottom: 1rem;
  color: #ffffff;
  background-color: #16a34a;
  text-decoration: none;
}

/* Al pasar el cursor: fondo gris oscuro y opacidad 0.6 */
.boton:hover {
  background-color: #111827;
  opacity: 0.6;
}

.pista {
  width: 300px;
  margin-bottom: 0.75rem;
  background-color: #fef3c7;
}

.caja {
  width: 100px;
  height: 40px;
  background-color: #16a34a;
}

/* Al pasar el cursor sobre la pista, la caja se desplaza 200px */
.pista:hover .caja {
  transform: translateX(200px);
}

/* 1. Salida: la transición del estado base, lenta (0.8s) y que arranca despacio */
.enlace {
  transition: background-color 0.8s ease-in;
}

/* 1. Entrada: la transición de :hover, rápida (0.2s) y que frena al final */
.enlace:hover {
  transition: background-color 0.2s ease-out;
}

/* 2. Tres cajas con el mismo tiempo (2s) y distinto ritmo */
.c1 {
  transition: transform 2s ease-in;
}

.c2 {
  transition: transform 2s linear;
}

.c3 {
  transition: transform 2s ease-out;
}
```

**Medidas comprobadas.** Enlace: sin cursor `0.8s` y `ease-in`; con el cursor, `0.2s` y `ease-out`. Entrada: `100 ms` `rgb(19, 68, 50)`, `200 ms` `rgb(17, 24, 39)`. Salida: `200 ms` `rgb(17, 37, 42)`, `400 ms` `rgb(19, 68, 50)`, `600 ms` `rgb(20, 110, 61)`, `800 ms` `rgb(22, 163, 74)`. Cajas a los `500`, `1000` y `1500 ms`: `.c1` `18.7`, `63.1`, `124.4px`; `.c2` `50`, `100`, `150px`; `.c3` `75.6`, `136.9`, `181.3px`.

**Parte B.**

1. Al entrar, el estado de destino es `:hover`, así que manda su transición; al salir, el destino es el estado base, y manda la suya. Escribirlas en esos lugares permite darles tiempos distintos.
2. Si la transición estuviera solo en `:hover`, la entrada se animaría pero la salida no: el color volvería de golpe.
3. `ease-out`: el panel llega rápido a su lugar y se asienta despacio.

---

## 🟡 Intermedio 01 — Curvas y pasos

**Hoja.**

```css
/* Tamaño base */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.pista {
  width: 300px;
  margin-bottom: 0.75rem;
  background-color: #fef3c7;
}

.caja {
  width: 100px;
  height: 40px;
  background-color: #16a34a;
}

/* Al pasar el cursor sobre la pista, la caja se desplaza 200px */
.pista:hover .caja {
  transform: translateX(200px);
}

/* 1. Una curva propia: retrocede al principio y se pasa del destino */
.elastica {
  transition: transform 2s cubic-bezier(0.68, -0.55, 0.27, 1.55);
}

/* 2. Un reloj: cuatro saltos, cada uno al final de su intervalo */
.reloj {
  transition: transform 2s steps(4, end);
}

/* 3. Cuatro intervalos sin salto en los extremos */
.sin-extremos {
  transition: transform 2s steps(4, jump-none);
}
```

**Medidas comprobadas.** `.elastica`: `500 ms` `-16.6px`, `1000 ms` `119.3px`, `1500 ms` `217.8px`. `.reloj`: `250`, `750`, `1250` y `1750 ms` → `0`, `50`, `100` y `150px`. `.sin-extremos`: `0`, `66.7`, `133.3` y `200px`.

**Parte B.**

1. `x1 = 2` está fuera del rango `0` a `1` que se exige a `x1` y `x2`. Se ignora **toda** la declaración `transition`: no hay transición y la caja llega de golpe (no se usa `ease` como respaldo).
2. Con `end`, el primer intervalo vale el valor inicial (`0px`) y el salto ocurre al final; con `start`, el salto ocurre al principio y el primer intervalo ya vale `50px`.
3. En el medio de cada intervalo: justo en el borde del salto el valor ya cambió (a los `500 ms`, `steps(4, end)` ya vale `50px`).

---

## 🟡 Intermedio 02 — Tu primera animación

**Hoja.**

```css
/* Tamaño base */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.aviso {
  width: 300px;
  padding: 1rem;
  margin-bottom: 1.5rem;
  background-color: #fef3c7;
}

.indicador {
  width: 60px;
  height: 60px;
  background-color: #16a34a;
}

/* 1. La secuencia de entrada: de invisible y desplazado hacia arriba a visible y en su lugar */
@keyframes entrar {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* El aviso la usa 1.5s, con ease-out, y conserva el estado inicial durante la espera y el final al terminar */
.aviso {
  animation-name: entrar;
  animation-duration: 1.5s;
  animation-timing-function: ease-out;
  animation-fill-mode: both;
}

/* 2. La secuencia de giro: una vuelta completa */
@keyframes girar {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}

/* El indicador gira sin parar, a velocidad constante, con el atajo */
.indicador {
  animation: girar 2s linear infinite;
}
```

**Medidas comprobadas.** `.aviso`: `0 ms` `0` y `translateY(-20px)`; `375 ms` `0.38` y `-12.44px`; `750 ms` `0.68` y `-6.31px`; `1125 ms` `0.91` y `-1.87px`; `1500 ms` y `2000 ms` `1` y sin desplazamiento. `.indicador`: `0 ms` giro de `0°`, `500 ms` `matrix(0, 1, -1, 0, 0, 0)`, `1000 ms` `matrix(-1, 0, 0, -1, 0, 0)`, `1500 ms` `matrix(0, -1, 1, 0, 0, 0)`, `2000 ms` `matrix(1, 0, 0, 1, 0, 0)`. Sin la solución no hay ninguna animación activa.

**Parte B.**

1. Durante el retardo, sin `backwards` o `both`, el aviso se vería con su aspecto normal (visible); recién al empezar saltaría a invisible y volvería a aparecer: un parpadeo. Con `backwards` o `both` se ve invisible (primer paso) durante la espera.
2. No hay ninguna secuencia con ese nombre: **no se anima** y no aparece ningún error.
3. Porque, si un valor del atajo puede entenderse como otra propiedad (por ejemplo, un nombre que coincide con una palabra clave), se usa para esa propiedad. Al final no hay confusión.

---

## 🔴 Desafío 01 — Una tarjeta con vida

**Hoja.**

```css
/* Base: tamaño y tipografía */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* La tarjeta, el icono y el botón */
.tarjeta {
  width: 300px;
  padding: 1rem;
  background-color: #fef3c7;
}

.icono {
  width: 40px;
  height: 40px;
  margin-bottom: 1rem;
  background-color: #16a34a;
}

.boton {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  color: #ffffff;
  background-color: #16a34a;
  text-decoration: none;
}

/* Secuencias */
@keyframes aparecer {
  from {
    opacity: 0;
    transform: translateY(20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes rebote {
  0% {
    transform: translateY(0);
  }

  25% {
    transform: translateY(-30px);
  }

  50% {
    transform: translateY(0);
  }

  75% {
    transform: translateY(-15px);
  }

  100% {
    transform: translateY(0);
  }
}

/* La tarjeta aparece sola (0.8s) y conserva sus estados antes y después */
.tarjeta {
  animation: aparecer 0.8s ease-out both;
}

/* El icono rebota sin parar, a partir de que termina la entrada de la tarjeta */
.icono {
  animation: rebote 2s linear 0.8s infinite;
}

/* El botón: sale despacio (0.6s) y entra rápido (0.2s) */
.boton {
  transition: background-color 0.6s ease-in;
}

.boton:hover {
  background-color: #111827;
  transition: background-color 0.2s ease-out;
}

/* Movimiento reducido: sin animaciones y con el cambio de color al instante */
@media (prefers-reduced-motion: reduce) {
  .tarjeta,
  .icono {
    animation: none;
  }

  .boton,
  .boton:hover {
    transition: none;
  }
}
```

**Medidas comprobadas.**

| Caso | Resultado |
|---|---|
| Tarjeta a los `0`, `400`, `800` y `1200 ms` | `0` / `translateY(20px)`; `0.68` / `6.31px`; `1` / sin desplazamiento; `1` / sin desplazamiento |
| Icono a los `0` y `400 ms` | sin movimiento |
| Icono a los `1300`, `1800`, `2300`, `2800` y `3300 ms` | `-30px`, `0px`, `-15px`, `0px` y `-30px` |
| Botón con el cursor, `100` y `200 ms` | `rgb(19, 68, 50)` y `rgb(17, 24, 39)` |
| Botón al salir, `300` y `600 ms` | `rgb(19, 68, 50)` y `rgb(22, 163, 74)` |
| Con movimiento reducido | cero animaciones activas; `animation-name` `none` en la tarjeta y el icono; `transition-duration` `0s` en el botón; tarjeta con `opacity` `1` |
| Sin hoja (partida) | cero animaciones y ninguna transición |

**Notas de corrección.**

- El icono usa un **retardo de `0.8s`** para empezar cuando termina la entrada de la tarjeta; por eso a los `400 ms` aún no se mueve.
- La tarjeta usa relleno `both` (`ease-out both` en el atajo): antes de empezar ya muestra el primer paso y al final conserva el último.
- La regla de movimiento reducido incluye `.boton:hover` para que la transición de entrada también se quite (la de `:hover` pisa a la del estado base).
- Se acepta una hoja con los mismos valores medidos aunque ordene los bloques de otra manera, mientras tenga comentarios, no repita reglas y no use `!important`.

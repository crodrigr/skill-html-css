# 📘 Ejemplo 03 — El atajo `transition`

> 🎓 **Resultados de aprendizaje:** RA-2
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía se cansó de escribir cuatro líneas por cada transición. En `atajo.html` compara la forma larga con el atajo `transition` y escribe dos transiciones en una sola declaración.

## 💻 Código

El contenido de `atajo.html` (dentro de `<main>`):

```html
<h2>Con las cuatro propiedades</h2>
<p><a class="boton largo" href="#">Reservar</a></p>

<h2>Con el atajo</h2>
<p><a class="boton corto" href="#">Reservar</a></p>

<h2>Varias transiciones en una declaración</h2>
<p><a class="boton varias" href="#">Reservar</a></p>
```

La hoja `css/atajo.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* El botón: un enlace con aspecto de botón, en azul */
.boton {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  color: #ffffff;
  background-color: #2563eb;
  text-decoration: none;
}

.boton:hover {
  background-color: #111827;
  opacity: 0.6;
}

/* Las cuatro propiedades por separado */
.largo {
  transition-property: background-color;
  transition-duration: 0.4s;
  transition-timing-function: ease-in;
  transition-delay: 0.2s;
}

/* Lo mismo con el atajo: propiedad, duración, función de tiempo y retardo */
.corto {
  transition: background-color 0.4s ease-in 0.2s;
}

/* Dos transiciones separadas por coma, cada una con sus valores */
.varias {
  transition: background-color 0.3s, opacity 1s ease-out 0.2s;
}
```

## 🔍 Análisis paso a paso

1. **El atajo** reúne las cuatro propiedades en una sola: `transition: background-color 0.4s ease-in 0.2s;`. El orden es: **propiedad, duración, función de tiempo y retardo**.
2. **Cómo distingue la duración del retardo.** Escribís dos tiempos: el **primero** que aparezca es la **duración** y el **segundo** es el **retardo** (según MDN). Por eso `0.4s ease-in 0.2s` es «duración `0.4s`, retardo `0.2s`».
3. **Misma transición, mismo resultado.** Las propiedades calculadas de `.largo` (forma larga) y de `.corto` (atajo) son idénticas: `background-color`, `0.4s`, `ease-in`, `0.2s`.
4. **Valores que se pueden omitir.** Se puede omitir la función de tiempo (vale `ease`) y el retardo (vale `0s`). La propiedad, si falta, vale `all`; la duración, si falta, vale `0s` y **no hay transición**.
5. **Varias transiciones.** `.varias` escribe dos separadas por una coma: `background-color 0.3s` y `opacity 1s ease-out 0.2s`. Cada una tiene sus propios valores: `duration` `0.3s, 1s`, `timing-function` `ease, ease-out`, `delay` `0s, 0.2s`.
6. **Cada una con su ritmo.** El fondo termina a los `300 ms` (ya está en `rgb(17, 24, 39)`), mientras que la opacidad termina recién a los `1200 ms` (`0.6`): a los `300 ms` va en `0.94`, a los `700 ms`, en `0.73`.
7. **El retardo en el atajo.** En `.largo` (retardo `0.2s`), a los `100 ms` el color sigue en el azul inicial; a los `400 ms` ya cambió (`rgb(31, 75, 173)`); a los `600 ms` (`0.2 + 0.4s`) termina.

## ✅ Resultado esperado

| Botón | `transition-property` | `duration` | `timing-function` | `delay` |
|---|---|---|---|---|
| `.largo` (cuatro propiedades) | `background-color` | `0.4s` | `ease-in` | `0.2s` |
| `.corto` (atajo) | `background-color` | `0.4s` | `ease-in` | `0.2s` |
| `.varias` (dos transiciones) | `background-color, opacity` | `0.3s, 1s` | `ease, ease-out` | `0s, 0.2s` |

| Instante | `.varias`: fondo | `.varias`: opacidad |
|---|---|---|
| `0 ms` | `rgb(37, 99, 235)` | `1` |
| `300 ms` | `rgb(17, 24, 39)` | `0.94` |
| `700 ms` | `rgb(17, 24, 39)` | `0.73` |
| `1200 ms` | `rgb(17, 24, 39)` | `0.6` |

- `.largo` y `.corto` se comportan igual: a los `100 ms` siguen azules; a los `400 ms` van en `rgb(31, 75, 173)`.

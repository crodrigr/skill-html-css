# 📘 Ejemplo 04 — Transiciones de entrada y de salida

> 🎓 **Resultados de aprendizaje:** RA-3
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere que el botón se oscurezca **rápido** al pasar el cursor, pero vuelva a su color **despacio** al sacarlo. En `entrada-salida.html` compara tres formas de escribir la transición.

## 💻 Código

El contenido de `entrada-salida.html` (dentro de `<main>`):

```html
<h2>Rápido al entrar, lento al salir</h2>
<p><a class="boton diferente" href="#">Reservar</a></p>

<h2>Misma transición en los dos sentidos</h2>
<p><a class="boton igual" href="#">Reservar</a></p>

<h2>La transición solo en :hover</h2>
<p><a class="boton solo-hover" href="#">Reservar</a></p>
```

La hoja `css/entrada-salida.css`:

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
}

/* La transición del estado BASE manda al salir: 1s */
.diferente {
  transition: background-color 1s ease-in;
}

/* La transición del estado :hover manda al entrar: 0.2s */
.diferente:hover {
  transition: background-color 0.2s ease-out;
}

/* Una sola transición en el estado base: vale en los dos sentidos */
.igual {
  transition: background-color 0.5s;
}

/* La transición está solo en :hover: entra suave, pero sale de golpe */
.solo-hover:hover {
  transition: background-color 0.5s;
}
```

## 🔍 Análisis paso a paso

1. **La regla que manda.** Cuando una propiedad cambia, el navegador usa la transición del **estado de destino**. Al **entrar** (el destino es `:hover`) manda la transición escrita en `:hover`; al **salir** (el destino es el estado base) manda la del estado base.
2. **`.diferente`.** El estado base declara `1s ease-in` y `:hover` declara `0.2s ease-out`. Lo medido: la **entrada** dura `0.2s` con `ease-out` (`0 ms`: azul; `100 ms`: `rgb(23, 48, 101)`; `200 ms`: `rgb(17, 24, 39)`); la **salida** dura `1s` con `ease-in` (`250 ms`: `rgb(19, 31, 57)`; `500 ms`: `rgb(23, 48, 101)`; `750 ms`: `rgb(29, 71, 161)`; `1000 ms`: azul).
3. **`.igual`.** Una sola transición en el estado base (`0.5s`) vale **en los dos sentidos**, porque la regla `.igual` se aplica al elemento sea cual sea su estado: la misma duración y la misma función rigen al entrar y al salir. Es lo más simple y lo habitual.
4. **`.solo-hover`.** La transición está **solo en `:hover`**. La **entrada** se anima (`250 ms`: `rgb(21, 39, 78)`; `500 ms`: `rgb(17, 24, 39)`), pero la **salida no**: al sacar el cursor, el color vuelve de golpe a `rgb(37, 99, 235)` y no se crea ninguna transición.
5. **Regla práctica.** Escribí la transición en el **estado base** para que valga en los dos sentidos; agregá una distinta en `:hover` (o `:focus`) solo cuando quieras que la entrada tenga otro tiempo o ritmo.
6. **Para qué sirve.** Una salida más lenta que la entrada es agradable: responde enseguida al cursor y se retira con calma. Al revés (entrada lenta) la interfaz se siente torpe.

## ✅ Resultado esperado

| Botón | Entrada | Salida |
|---|---|---|
| `.diferente` | `0.2s ease-out`: `100 ms` → `rgb(23, 48, 101)`, `200 ms` → `rgb(17, 24, 39)` | `1s ease-in`: `250 ms` → `rgb(19, 31, 57)`, `500 ms` → `rgb(23, 48, 101)`, `750 ms` → `rgb(29, 71, 161)`, `1000 ms` → `rgb(37, 99, 235)` |
| `.igual` | `0.5s`: `250 ms` → `rgb(21, 39, 78)`, `500 ms` → `rgb(17, 24, 39)` | `0.5s`: `250 ms` → `rgb(33, 84, 196)`, `500 ms` → `rgb(37, 99, 235)` |
| `.solo-hover` | `0.5s`: `250 ms` → `rgb(21, 39, 78)`, `500 ms` → `rgb(17, 24, 39)` | **sin transición**: vuelve de golpe a `rgb(37, 99, 235)` |

- Propiedades de `.diferente`: en el estado base `transition-duration` `1s` y `ease-in`; con el cursor encima, `0.2s` y `ease-out`.

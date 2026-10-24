# 📘 Ejemplo 02 — Retardo y varias propiedades

> 🎓 **Resultados de aprendizaje:** RA-1
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere que el botón espere un poco antes de cambiar, que el fondo y la opacidad tengan tiempos distintos y entender qué pasa con las propiedades que no nombra. En `retardo.html` prueba cuatro botones con el cursor encima.

## 💻 Código

El contenido de `retardo.html` (dentro de `<main>`):

```html
<h2>Con retardo</h2>
<p><a class="boton con-retardo" href="#">Reservar</a></p>

<h2>Una lista de propiedades</h2>
<p><a class="boton lista" href="#">Reservar</a></p>

<h2>Todas las propiedades</h2>
<p><a class="boton todas" href="#">Reservar</a></p>

<h2>Solo el fondo</h2>
<p><a class="boton solo-fondo" href="#">Reservar</a></p>
```

La hoja `css/retardo.css`:

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

/* Al pasar el cursor cambian el fondo, el color del texto y la opacidad */
.boton:hover {
  background-color: #111827;
  color: #fef3c7;
  opacity: 0.6;
}

/* Un retardo de 1s: el cambio empieza un segundo después */
.con-retardo {
  transition-property: background-color;
  transition-duration: 0.5s;
  transition-delay: 1s;
}

/* Una lista separada por comas: cada propiedad con su duración, en el mismo orden */
.lista {
  transition-property: background-color, opacity;
  transition-duration: 0.4s, 1s;
}

/* all: se anima cualquier propiedad que cambie */
.todas {
  transition-property: all;
  transition-duration: 0.5s;
}

/* Solo el fondo se anima: el color del texto y la opacidad cambian al instante */
.solo-fondo {
  transition-property: background-color;
  transition-duration: 0.5s;
}
```

## 🔍 Análisis paso a paso

1. **`transition-delay`** es el tiempo que **espera** el navegador antes de empezar. `.con-retardo` tiene `1s`: durante el primer segundo el botón sigue azul y recién después empieza el cambio de `0.5s`.
2. **Los tiempos se cuentan desde que cambia el valor.** El color sigue en `rgb(37, 99, 235)` a los `0`, `500` y `1000 ms` (retardo); a los `1250 ms` (mitad de la duración) está en `rgb(21, 39, 78)`; a los `1500 ms`, en `rgb(17, 24, 39)`.
3. **Varias propiedades.** `transition-property: background-color, opacity` es una **lista separada por comas**. `transition-duration: 0.4s, 1s` es otra lista y se lee **en el mismo orden**: el fondo dura `0.4s` y la opacidad, `1s`.
4. **Las dos listas se emparejan por posición.** A los `200 ms` el fondo ya está casi terminado (`rgb(21, 39, 78)`) y la opacidad recién bajó a `0.88`; a los `400 ms` el fondo terminó (`rgb(17, 24, 39)`) y la opacidad va en `0.73`; a los `1000 ms` la opacidad llegó a `0.6`. Si una lista es más corta que otra, el navegador la repite.
5. **`all`.** `transition-property: all` anima **cualquier** propiedad que cambie. Con el cursor encima, el navegador crea tres transiciones: `background-color`, `color` y `opacity`.
6. **Lo que no se nombra cambia al instante.** `.solo-fondo` anima solo `background-color`. En el instante `0 ms` el fondo todavía es azul (`rgb(37, 99, 235)`), pero el color del texto ya es `rgb(254, 243, 199)` y la opacidad ya es `0.6`: esas dos propiedades **no están en la lista** y cambian de golpe.
7. **Consejo.** `all` es cómodo, pero anima también lo que no pensabas animar. En componentes reales conviene nombrar las propiedades.

## ✅ Resultado esperado

| Botón | Configuración | Valores medidos |
|---|---|---|
| `.con-retardo` | `delay` `1s`, `duration` `0.5s` | `0`, `500`, `1000 ms`: azul · `1250 ms`: `rgb(21, 39, 78)` · `1500 ms`: `rgb(17, 24, 39)` |
| `.lista` | fondo `0.4s`, opacidad `1s` | `200 ms`: fondo `rgb(21, 39, 78)` y opacidad `0.88` · `400 ms`: fondo final y opacidad `0.73` · `1000 ms`: opacidad `0.6` |
| `.todas` | `all`, `0.5s` | tres transiciones: `background-color`, `color`, `opacity` |
| `.solo-fondo` | solo `background-color` | a los `0 ms`: fondo azul, pero texto `rgb(254, 243, 199)` y opacidad `0.6` ya cambiados |

- El botón con retardo parece «no reaccionar» durante un segundo y luego cambia con suavidad.

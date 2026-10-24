# 📘 Ejemplo 01 — Qué es una transición

> 🎓 **Resultados de aprendizaje:** RA-1
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía tiene un botón «Reservar» azul que se pone gris oscuro al pasar el cursor. Hoy el cambio es **instantáneo** y se siente brusco. En `transicion.html` compara dos botones: uno sin transición y otro con una transición de `0.3s` sobre el color de fondo.

## 💻 Código

El contenido de `transicion.html` (dentro de `<main>`):

```html
<h2>Sin transición</h2>
<p><a class="boton boton-seco" href="#">Reservar</a></p>

<h2>Con transición</h2>
<p><a class="boton boton-suave" href="#">Reservar</a></p>
```

La hoja `css/transicion.css`:

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

/* Al pasar el cursor, el fondo cambia a gris oscuro */
.boton:hover {
  background-color: #111827;
}

/* Este botón no declara ninguna transición: el cambio es instantáneo */
.boton-seco {
  margin: 0;
}

/* Este botón sí: anima el fondo durante 0.3 segundos */
.boton-suave {
  transition-property: background-color;
  transition-duration: 0.3s;
}
```

## 🔍 Análisis paso a paso

1. **Qué es una transición.** Es un cambio **gradual** del valor de una propiedad entre dos estados. Ocurre cuando **cambia el valor**: acá, cuando el botón pasa de su estado normal a `:hover`.
2. **Sin transición.** `.boton-seco` no declara nada (el valor por defecto es `transition-duration: 0s`): al pasar el cursor, el fondo salta de golpe a `rgb(17, 24, 39)`. No se crea ninguna transición (la cuenta de transiciones activas es `0`).
3. **`transition-property`** dice **qué propiedad** se anima. `background-color` anima solo el fondo. Si no se la escribe, vale `all` (todas las propiedades).
4. **`transition-duration`** dice **cuánto dura** el cambio. `0.3s` son `300` milisegundos. Sin duración (o con `0s`) no hay transición: es **obligatoria**.
5. **Los valores intermedios.** Con la duración de `0.3s`, el color pasa por valores intermedios: a los `0 ms` es `rgb(37, 99, 235)` y a los `300 ms`, `rgb(17, 24, 39)`. A la mitad (`150 ms`) ya está en `rgb(21, 39, 78)`, casi en el final: la función de tiempo por defecto es `ease`, que empieza rápido (se ve en el Ejemplo 06).
6. **La salida.** Al sacar el cursor, la misma transición se aplica en sentido contrario: del gris oscuro al azul en otros `300 ms` (a los `150 ms`, `rgb(33, 84, 196)`).
7. **Para qué sirve.** Un cambio gradual avisa que algo cambió sin sobresaltar. Los cambios de estado de botones, enlaces y tarjetas son el uso más común.

## ✅ Resultado esperado

| Instante | `.boton-seco` | `.boton-suave` (transición de `0.3s`) |
|---|---|---|
| Antes de pasar el cursor | `rgb(37, 99, 235)` | `rgb(37, 99, 235)` |
| `0 ms` (entra el cursor) | `rgb(17, 24, 39)` (de golpe) | `rgb(37, 99, 235)` |
| `75 ms` | `rgb(17, 24, 39)` | `rgb(29, 68, 155)` |
| `150 ms` | `rgb(17, 24, 39)` | `rgb(21, 39, 78)` |
| `225 ms` | `rgb(17, 24, 39)` | `rgb(18, 27, 47)` |
| `300 ms` | `rgb(17, 24, 39)` | `rgb(17, 24, 39)` |

- Propiedades calculadas del botón suave: `transition-property: background-color`, `transition-duration: 0.3s`, `transition-timing-function: ease` y `transition-delay: 0s`.
- Visualmente: el botón seco cambia de color de golpe; el suave se oscurece en un instante breve, rápido al principio y más despacio al final.

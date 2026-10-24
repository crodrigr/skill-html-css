# 📘 Ejemplo 09 — Qué es una animación

> 🎓 **Resultados de aprendizaje:** RA-7, RA-8
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere que una tarjeta de bienvenida **aparezca sola** al cargar la página, subiendo suavemente. Una transición no alcanza, porque nadie cambia un valor. En `animacion.html` usa su primera animación y la compara con una transición.

## 💻 Código

El contenido de `animacion.html` (dentro de `<main>`):

```html
<h2>Una animación de entrada</h2>
<div class="tarjeta">Hola, soy una tarjeta que aparece sola.</div>

<h2>Una transición necesita una interacción</h2>
<div class="tarjeta tarjeta-transicion">Pasá el cursor por acá.</div>
```

La hoja `css/animacion.css`:

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
  background-color: #dbeafe;
}

/* La secuencia: dos pasos, from (el principio) y to (el final) */
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

/* Se asocia a la tarjeta por su nombre y se le da una duración: empieza sola, al cargar la página */
.tarjeta {
  animation-name: aparecer;
  animation-duration: 1s;
}

/* Una transición, en cambio, solo ocurre cuando cambia un valor (acá, al pasar el cursor) */
.tarjeta-transicion {
  animation-name: none;
  transition: opacity 1s linear;
}

.tarjeta-transicion:hover {
  opacity: 0.4;
}
```

## 🔍 Análisis paso a paso

1. **Qué es una animación.** Es una **secuencia de estilos** que se reproduce sobre un elemento, descrita en una regla `@keyframes` y asociada al elemento con las propiedades `animation-*`. Puede empezar **sola**, sin que nadie interactúe.
2. **La secuencia, con `@keyframes`.** `@keyframes aparecer` tiene un nombre y dos pasos: `from` (el principio, equivale a `0%`) con `opacity: 0` y `translateY(20px)`, y `to` (el final, equivale a `100%`) con `opacity: 1` y `translateY(0)`. `translateY` mueve el elemento en vertical (el `20px` positivo lo baja).
3. **Asociarla a un elemento.** `animation-name: aparecer` une la tarjeta con la secuencia por su **nombre**, y `animation-duration: 1s` le da su duración. **Sin duración no se anima** (vale `0s`).
4. **Qué pasó al cargar.** A los `0 ms` la tarjeta es invisible (`opacity` `0`) y está `20px` más abajo; a los `500 ms` (la mitad) ya está casi en su lugar: `opacity` `0.8` y `3.95px` de desplazamiento (la función de tiempo por defecto es `ease`); a los `1000 ms` está terminada: `opacity` `1`, sin desplazamiento.
5. **Sin relleno, vuelve a su aspecto.** Al terminar, la animación deja de aplicarse y la tarjeta usa sus estilos normales (`opacity` `1`, `transform` `none`). Si querés que conserve el último paso, existe `animation-fill-mode` (Ejemplo 11).
6. **Transición frente a animación.** `.tarjeta-transicion` no tiene animación y usa `transition: opacity 1s linear`: no pasa nada hasta que el cursor entra; entonces la opacidad baja de `1` a `0.4` (a los `500 ms`, `0.7`). La transición **necesita un cambio**; la animación **no**.
7. **Cuándo usar cada una.** Transición: cambios entre **dos estados** disparados por una interacción. Animación: entradas, indicadores de carga, avisos y secuencias de **varios pasos**, o que se repiten.

## ✅ Resultado esperado

| Instante | `opacity` | `transform` |
|---|---|---|
| `0 ms` | `0` | `translateY(20px)` |
| `250 ms` | `0.41` | `translateY(11.83px)` |
| `500 ms` | `0.80` | `translateY(3.95px)` |
| `750 ms` | `0.96` | `translateY(0.79px)` |
| `1000 ms` | `1` | `none` |
| `1500 ms` (ya terminó) | `1` | `none` |

- Propiedades calculadas de la tarjeta: `animation-name: aparecer`, `animation-duration: 1s`, `animation-timing-function: ease`, `animation-iteration-count: 1` y `animation-fill-mode: none`.
- La tarjeta sube desde abajo y se vuelve visible al cargar la página, sin que nadie haga nada.

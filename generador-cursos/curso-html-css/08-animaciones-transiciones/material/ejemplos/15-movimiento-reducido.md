# 📘 Ejemplo 15 — Movimiento reducido

> 🎓 **Resultados de aprendizaje:** RA-9
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Una lectora le escribe a Lucía: el indicador que late sin parar le provoca mareo. Lucía descubre que puede **respetar la preferencia** de quien pide menos movimiento. En `reducido.html` agrega una regla con `prefers-reduced-motion`.

## 💻 Código

El contenido de `reducido.html` (dentro de `<main>`):

```html
<h2>Un indicador que late sin parar</h2>
<div class="indicador latido"></div>

<h2>Una tarjeta que aparece</h2>
<div class="tarjeta entrada">Hola, soy una tarjeta que aparece sola.</div>

<h2>Un botón con transición</h2>
<p><a class="boton boton-suave" href="#">Reservar</a></p>
```

La hoja `css/reducido.css`:

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

.indicador {
  width: 60px;
  height: 60px;
  background-color: #16a34a;
}

.tarjeta {
  width: 300px;
  padding: 1rem;
  background-color: #dbeafe;
}

@keyframes latir {
  from {
    transform: scale(1);
  }

  to {
    transform: scale(1.3);
  }
}

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

/* Una animación que no termina nunca: puede molestar a quien es sensible al movimiento */
.latido {
  animation: latir 1s ease-in-out infinite alternate;
}

.entrada {
  animation: aparecer 1s ease-out;
}

.boton:hover {
  background-color: #111827;
}

.boton-suave {
  transition: background-color 0.3s;
}

/* Si la persona pidió menos movimiento: sin animaciones y con el cambio de color al instante */
@media (prefers-reduced-motion: reduce) {
  .latido,
  .entrada {
    animation: none;
  }

  .boton-suave {
    transition: none;
  }
}
```

## 🔍 Análisis paso a paso

1. **Por qué importa.** Algunas personas tienen trastornos vestibulares o son sensibles al movimiento: las animaciones grandes, que se repiten o que escalan pueden causar malestar. MDN advierte, por ejemplo, que escalar o desplazar objetos grandes puede desencadenar síntomas.
2. **Qué es `prefers-reduced-motion`.** Es una condición de consulta de medios (Clase 07) que detecta si la persona activó, en su dispositivo, la opción de **reducir el movimiento**. Tiene dos valores: `no-preference` (no expresó preferencia) y `reduce` (pidió menos movimiento).
3. **Cómo se aplica.** Dentro de `@media (prefers-reduced-motion: reduce) { ... }` se **quitan o se reducen** las animaciones: acá, `animation: none` en el indicador y en la tarjeta, y `transition: none` en el botón.
4. **Sin la preferencia.** `.latido` tiene la animación `latir` y `.entrada` tiene `aparecer`: la página tiene dos animaciones activas (`latir` y `aparecer`) y el botón tiene `transition-duration: 0.3s`.
5. **Con movimiento reducido.** Con la preferencia activada, `animation-name` calculado es `none` en las dos, **no hay ninguna animación activa** y la duración de la transición del botón es `0s`: el cambio de color es instantáneo.
6. **Cómo probarlo.** En los ajustes de accesibilidad de tu sistema operativo buscá la opción de reducir el movimiento o las animaciones (el nombre cambia según el sistema). Las herramientas para desarrolladores del navegador también permiten emular la preferencia.
7. **Qué conviene reducir.** Lo que **se repite sin fin**, lo que **se desplaza o escala mucho** y los efectos parpadeantes. Un cambio de color suave o una aparición gradual suelen ser aceptables, pero lo más seguro es dar a la persona la opción.
8. **Reducir no es siempre quitar.** Muchas veces se reemplaza el movimiento por un cambio simple (por ejemplo, de opacidad). Lo importante es que **la información no dependa del movimiento**.

## ✅ Resultado esperado

| Condición | Animaciones activas | `.latido` `animation-name` | `.entrada` `animation-name` | `.boton-suave` `transition-duration` |
|---|---|---|---|---|
| Sin preferencia | `latir`, `aparecer` | `latir` | `aparecer` | `0.3s` |
| Con `prefers-reduced-motion: reduce` | ninguna (`0`) | `none` | `none` | `0s` |

- Con la preferencia activada, el indicador queda quieto y la tarjeta aparece sin moverse.

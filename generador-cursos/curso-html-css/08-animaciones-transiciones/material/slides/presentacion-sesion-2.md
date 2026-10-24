# 🎬 Animaciones y keyframes

Curso **HTML y CSS** · Clase 08 · **Sesión 2**

---

## 🎯 Objetivos de la sesión

- 🔹 Explicar qué es una animación y usar sus propiedades.
- 🔹 Definir secuencias con `@keyframes` (`from`, `to` y porcentajes).
- 🔹 Respetar a quienes prefieren menos movimiento.

> 📌 Se necesita de la sesión 1: `transition`, funciones de tiempo.

---

## 🎭 Transición frente a animación

![Comparación en dos columnas. La transición va de un estado a otro cuando cambia un valor, por ejemplo al pasar el cursor, con un solo tramo y se define con la propiedad transition. La animación se reproduce sola o cuando se la asocia a un elemento, puede tener muchos pasos, repetirse y alternar, y se define con la regla keyframes y la propiedad animation.](../imagenes/transicion-frente-a-animacion.svg)

---

## 🔑 `@keyframes`: `from` y `to`

```css
@keyframes aparecer {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}
```

- `from` = `0%`; `to` = `100%`.
- Si falta uno, se usa el valor que el elemento ya tiene.

---

## 🔗 Asociarla a un elemento

```css
.tarjeta {
  animation-name: aparecer;
  animation-duration: 1s;
}
```

- El **nombre** debe coincidir con el de la secuencia.
- Sin duración, no se anima.

---

## 🎛️ Repeticiones y dirección

- `animation-iteration-count`: número o `infinite`.
- `animation-direction`: `alternate` va y vuelve.
- `animation-delay`: espera antes de empezar.

---

## 🧩 Relleno y reproducción

![Una animación con un retardo de 1 segundo, una duración de 1 segundo, 2 repeticiones alternadas y relleno both. De 0 a 1000 milisegundos es el retardo y, por el relleno hacia atrás, la caja ya muestra el primer paso. De 1000 a 2000 milisegundos va de 0 a 100 píxeles. De 2000 a 3000 vuelve de 100 a 0 porque la dirección alterna. Después de 3000 milisegundos termina y, por el relleno hacia adelante, conserva el último paso.](../imagenes/fases-de-una-animacion.svg)

---

## ✂️ El atajo `animation`

```css
.tarjeta {
  animation: 2s ease-out 0.5s 2 alternate both aparecer;
}
```

- El primer tiempo es la duración; el segundo, el retardo.
- El nombre, **al final**.

---

## 📊 Selectores porcentuales

![Arriba, una secuencia con dos pasos: from, que equivale a 0 por ciento, con opacidad 0 y desplazada 20 píxeles hacia abajo, y to, que equivale a 100 por ciento, con opacidad 1 y sin desplazamiento. Abajo, un rebote con cinco pasos en 2 segundos: 0 por ciento en 0 píxeles, 25 por ciento en menos 60, 50 por ciento en 0, 75 por ciento en menos 30 y 100 por ciento en 0; los pasos caen a 0, 0.5, 1, 1.5 y 2 segundos.](../imagenes/keyframes-from-to-y-porcentajes.svg)

---

## 🏀 El rebote

- `0%` → `0` · `25%` → `-60px` · `50%` → `0` · `75%` → `-30px` · `100%` → `0`.
- Con `2s`, cada paso cae a `0.5s`.
- La función de tiempo se aplica **entre cada par de pasos**.

---

## ♿ Movimiento reducido

```css
@media (prefers-reduced-motion: reduce) {
  .latido { animation: none; }
}
```

- Quitá o reducí lo que se repite o se mueve mucho.
- La información no debe depender del movimiento.

---

## ⚠️ Errores comunes

- 🚫 Un nombre que no coincide con la secuencia.
- 🚫 Olvidar la duración de la animación.
- 🚫 Animaciones infinitas sin regla de movimiento reducido.
- 🚫 Animar medidas pesadas en lugar de `opacity` y `transform`.

---

## 🛠️ Actividad

**Taller 02 — Animá con respeto.**

Y los ejercicios **Intermedio 02** y **Desafío 01**.

---

## ✅ Resumen y evaluación

- 🔹 Animación = secuencia (`@keyframes`) + propiedades `animation-*`.
- 🔹 `from`/`to` y porcentajes ubican los pasos.
- 🔹 Respetá `prefers-reduced-motion`.
- 🔹 Cierre: **Quiz 01** (12 ítems).

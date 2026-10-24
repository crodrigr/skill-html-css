# ⏱️ Transiciones y funciones de tiempo

Curso **HTML y CSS** · Clase 08 · **Sesión 1**

---

## 🎯 Objetivos de la sesión

- 🔹 Suavizar cambios con transiciones (propiedades y atajo).
- 🔹 Diseñar transiciones de entrada y de salida.
- 🔹 Elegir el ritmo: funciones predefinidas, `cubic-bezier()` y `steps()`.

> 📌 Se recomiendan las Clases 01 a 07.

---

## 🌊 ¿Qué es una transición?

Un cambio **gradual** del valor de una propiedad, cuando ese valor cambia.

- Sin transición: el cambio es **instantáneo**.
- Con transición: pasa por valores intermedios.
- Hace falta una **duración**: sin ella (`0s`), no hay transición.

---

## 🕒 Las cuatro propiedades

![Una transición con un retardo de 1 segundo y una duración de 0.5 segundos. Entre 0 y 1000 milisegundos el botón sigue azul (retardo); entre 1000 y 1500 milisegundos el color cambia gradualmente; desde 1500 milisegundos queda en gris oscuro. Se muestran los colores medidos en 0, 1000, 1250 y 1500 milisegundos.](../imagenes/linea-de-tiempo-de-una-transicion.svg)

---

## ✂️ El atajo `transition`

```css
.boton {
  transition: background-color 0.4s ease-in 0.2s;
}
```

- Propiedad · duración · función · retardo.
- El **primer** tiempo es la duración; el **segundo**, el retardo.
- Varias transiciones, separadas por coma.

---

## ↔️ Entrada y salida

![Dos tiras de color a la misma escala de tiempo. Al entrar con el cursor, la regla de hover manda: 0.2 segundos con ease-out, y el botón pasa de azul a gris oscuro rápido. Al salir, manda la regla del estado base: 1 segundo con ease-in, y vuelve de gris oscuro a azul lentamente.](../imagenes/entrada-y-salida.svg)

---

## 🚫 Lo que no se anima

- `auto` → `100px`: no hay valores intermedios.
- `display`: valor discreto, sin intermedios.
- Duración `0s`: no hay tiempo para animar.
- Mejor animar `opacity` y `transform`.

---

## 🎚️ Funciones de tiempo

![Cinco gráficas del progreso del cambio a lo largo del tiempo: linear es una recta; ease arranca con rapidez y termina despacio; ease-in arranca despacio y termina rápido; ease-out arranca rápido y termina despacio; ease-in-out arranca y termina despacio. Debajo de cada gráfica, los cuatro valores de su cubic-bezier.](../imagenes/funciones-de-tiempo-predefinidas.svg)

---

## 🧮 `cubic-bezier()`

![Una curva cubic-bezier(0.68, -0.55, 0.27, 1.55) dibujada sobre un eje de tiempo de 0 a 1 y de progreso de menos 0.6 a 1.6. Los dos puntos de control, P1 con x 0.68 e y menos 0.55 y P2 con x 0.27 e y 1.55, tiran de la curva desde los extremos. La curva baja por debajo de 0 al principio y se pasa de 1 antes de asentarse.](../imagenes/curva-cubic-bezier.svg)

---

## 🪜 `steps()`

![Tres gráficas escalonadas de steps(4) con cuatro intervalos. Con end, el salto ocurre al final de cada intervalo y los valores en el medio de cada intervalo son 0, 50, 100 y 150 píxeles. Con start, el salto ocurre al principio y los valores son 50, 100, 150 y 200. Con jump-none no hay salto en los extremos y los valores son 0, 66.7, 133.3 y 200.](../imagenes/funcion-steps.svg)

---

## ⚠️ Errores comunes

- 🚫 Olvidar la duración.
- 🚫 La transición solo en `:hover`: la salida es de golpe.
- 🚫 `x1` o `x2` fuera de `0` a `1` en `cubic-bezier()`.
- 🚫 Usar `all` sin pensar qué más cambia.

---

## 🛠️ Actividad

**Taller 01 — Dale vida a tu interfaz.**

Y los ejercicios **Básico 01**, **Básico 02** e **Intermedio 01**.

---

## ✅ Resumen de la sesión

- 🔹 Transición = cambio gradual; necesita duración.
- 🔹 La transición del estado de **destino** es la que manda.
- 🔹 Palabras clave, curvas y saltos dan el ritmo.
- 🔹 Próxima sesión: secuencias con animaciones.

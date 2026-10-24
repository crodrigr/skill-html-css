# 🟡 Intermedio 02 — Tu primera animación

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-7, RA-8 · 🗓️ **Sesión 2**

## 🧱 Estado inicial

Abrí [`intermedio-02.html`](../recursos/portafolio-inicial/intermedio-02.html) y su hoja [`css/intermedio-02.css`](../recursos/portafolio-inicial/css/intermedio-02.css). La hoja define un `.aviso` (una tarjeta crema) y un `.indicador` (un cuadrado verde de `60px`). Todavía no hay ninguna secuencia ni animación.

## 🛠️ Proceso esperado

Escribí en `intermedio-02.css` lo siguiente y comprobá los valores.

1. **Una secuencia de entrada** llamada `entrar`: en `from`, el aviso es invisible (`opacity` `0`) y está `20px` más arriba (`translateY(-20px)`); en `to`, es visible (`opacity` `1`) y en su lugar (`translateY(0)`).
2. **Asociarla al `.aviso`** con las propiedades por separado: dura `1.5s`, con función `ease-out` y relleno `both` (muestra el primer paso durante una espera y conserva el último al terminar).
3. **Una secuencia de giro** llamada `girar`: de `rotate(0deg)` a `rotate(360deg)`.
4. **Asociarla al `.indicador`** con el atajo `animation`: `2s`, velocidad constante y **sin fin**.

Valores esperados:

| Elemento | `0 ms` | `750 ms` | `1500 ms` | Después |
|---|---|---|---|---|
| `.aviso` (`opacity` / `translateY`) | `0` / `-20px` | `0.68` / `-6.31px` | `1` / `0` | conserva `1` / `0` (`2000 ms`) |

| Instante | `.indicador` (`transform`) |
|---|---|
| `0 ms` | giro de `0°` |
| `500 ms` | `matrix(0, 1, -1, 0, 0, 0)` (un cuarto de vuelta) |
| `1000 ms` | `matrix(-1, 0, 0, -1, 0, 0)` (media vuelta) |
| `1500 ms` | `matrix(0, -1, 1, 0, 0, 0)` |
| `2000 ms` | `matrix(1, 0, 0, 1, 0, 0)` (vuelta completa; vuelve a empezar) |

**Parte B.** Respondé:

1. ¿Qué se vería en el aviso si le agregaras un retardo de `1s` y no usaras `animation-fill-mode`?
2. ¿Qué ocurre si el nombre de `animation-name` no coincide con el de la secuencia?
3. ¿Por qué es mejor escribir el nombre al final en el atajo `animation`?

## ✅ Resultado esperado

- ☑️ Las dos secuencias y las dos asociaciones, con los valores de la tabla.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 Usá solo `opacity` y `transform` en las secuencias.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-7: Usar las propiedades de animación y el atajo `animation`.
- RA-8: Definir una secuencia con `@keyframes` (`from` y `to`).

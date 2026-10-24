# 🟢 Básico 02 — Entrada, salida y ritmo

> 🟢 **Nivel:** Básico · 🎓 **Resultados de aprendizaje:** RA-3, RA-4 · 🗓️ **Sesión 1**

## 🧱 Estado inicial

Abrí [`basico-02.html`](../recursos/portafolio-inicial/basico-02.html) y su hoja [`css/basico-02.css`](../recursos/portafolio-inicial/css/basico-02.css). La hoja ya define `.boton` y su `:hover` (fondo gris oscuro y opacidad `0.6`) y tres pistas de `300px` con una caja de `100px` cada una (`.c1`, `.c2` y `.c3`) que se desplaza `200px` cuando el cursor pasa por la pista. Ninguna tiene transición todavía. En la página hay un enlace con aspecto de botón (`.enlace`).

## 🛠️ Proceso esperado

Escribí en `basico-02.css` las reglas de la tabla y comprobá cada valor.

| # | Elegí… | Pedido | Valor esperado |
|---|---|---|---|
| 1 | `.enlace` | **Salida lenta y entrada rápida** del color de fondo: al salir, `0.8s` con función `ease-in`; al entrar, `0.2s` con `ease-out` | sin cursor: `transition-duration` `0.8s` y `ease-in`; con el cursor: `0.2s` y `ease-out` |
| 2 | `.c1` | Desplazamiento en `2s` que **arranca despacio y termina rápido** | `18.7px`, `63.1px` y `124.4px` a los `500`, `1000` y `1500 ms` |
| 3 | `.c2` | Desplazamiento en `2s` a **velocidad constante** | `50px`, `100px` y `150px` |
| 4 | `.c3` | Desplazamiento en `2s` que **arranca rápido y termina despacio** | `75.6px`, `136.9px` y `181.3px` |

Comprobá además el fondo del enlace: en la **entrada**, a los `100 ms`, `rgb(19, 68, 50)` (y a los `200 ms`, `rgb(17, 24, 39)`); en la **salida**, a los `400 ms`, `rgb(19, 68, 50)` y a los `800 ms`, `rgb(22, 163, 74)`.

**Parte B.** Respondé:

1. ¿Por qué la transición de entrada se escribe en `:hover` y la de salida en el estado base?
2. ¿Qué pasaría con la salida si escribieras la transición **solo** en `.enlace:hover`?
3. ¿Qué función de tiempo usarías para un panel que **entra** a la pantalla y por qué?

## ✅ Resultado esperado

- ☑️ Cuatro reglas (o grupos de reglas) con los valores de la tabla.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 Usá palabras clave para las funciones de tiempo (nada de `cubic-bezier()`).
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-3: Diseñar transiciones de entrada y de salida.
- RA-4: Elegir una función de tiempo predefinida.

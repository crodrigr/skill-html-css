# 🟡 Intermedio 01 — Curvas y pasos

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-5, RA-6 · 🗓️ **Sesión 1**

## 🧱 Estado inicial

Abrí [`intermedio-01.html`](../recursos/portafolio-inicial/intermedio-01.html) y su hoja [`css/intermedio-01.css`](../recursos/portafolio-inicial/css/intermedio-01.css). La hoja define tres pistas de `300px` con una caja de `100px` cada una (`.elastica`, `.reloj` y `.sin-extremos`) que se desplaza `200px` cuando el cursor pasa por la pista. Todavía no tienen transición.

## 🛠️ Proceso esperado

Escribí en `intermedio-01.css` las reglas de la tabla, todas con una duración de `2s`, y comprobá el desplazamiento (en píxeles) en cada instante.

| # | Elegí… | Pedido | Valores esperados |
|---|---|---|---|
| 1 | `.elastica` | Una curva propia, `cubic-bezier(0.68, -0.55, 0.27, 1.55)`: la caja retrocede un poco y se pasa de su destino | `500 ms`: `-16.6px` · `1000 ms`: `119.3px` · `1500 ms`: `217.8px` |
| 2 | `.reloj` | Un movimiento a saltos: **cuatro pasos**, cada salto al **final** de su intervalo | `250 ms`: `0px` · `750 ms`: `50px` · `1250 ms`: `100px` · `1750 ms`: `150px` |
| 3 | `.sin-extremos` | **Cuatro intervalos sin salto en los extremos** | `250 ms`: `0px` · `750 ms`: `66.7px` · `1250 ms`: `133.3px` · `1750 ms`: `200px` |

**Parte B.** Respondé:

1. ¿Por qué `cubic-bezier(2, 0, 0.5, 1)` no funciona? ¿Qué pasa con toda la declaración `transition`?
2. ¿En qué se diferencian `steps(4, end)` y `steps(4, start)` en el valor del primer intervalo?
3. ¿Dónde conviene medir un `steps()` y por qué no en el borde de un salto?

## ✅ Resultado esperado

- ☑️ Tres reglas con los valores de la tabla.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 Escribí cada transición con el atajo `transition`.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-5: Crear una función de tiempo con `cubic-bezier()`.
- RA-6: Crear una función de salto con `steps()`.

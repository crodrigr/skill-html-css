# 📏 Unidades relativas

Curso **HTML y CSS** · Clase 06

---

## 🎯 Objetivos de la clase

- 🔹 Distinguir las unidades absolutas de las relativas.
- 🔹 Usar `px`, `%`, `em` y `rem`, y saber respecto de qué se calcula cada una.
- 🔹 Conocer `ex`, `ch`, `lh` y las unidades de ventana, y elegir la unidad adecuada.

> 📌 Se recomiendan las Clases 01 a 05.

---

## 📏 ¿Qué es una unidad?

El **sufijo** que dice en qué se mide un número: `200px`, `50%`, `1.5rem`.

- Un número distinto de cero **necesita** unidad.
- El `0` es la excepción.
- Entre el número y la unidad, **sin espacio**.

---

## 🧭 Dos tipos de unidades

![Árbol de las unidades de CSS: las absolutas (px, cm, mm, Q, in, pt, pc), con un tamaño fijo, y las relativas, que se calculan a partir de otro valor: el porcentaje, que depende del contenedor; em, ex, ch y lh, que dependen de la letra; rem y rlh, que dependen de la raíz; y vw, vh, vmin y vmax, que dependen de la ventana.](../imagenes/tipos-de-unidades.svg)

---

## 🔲 La unidad `px`

- Unidad **absoluta** de uso habitual en pantalla.
- `200px` son siempre 200 píxeles **de CSS**.
- Ideal para lo fijo y pequeño: bordes finos.

---

## 🔬 Densidad de píxeles

![Una caja de 200 píxeles de CSS en dos pantallas: en una pantalla común cada píxel de CSS es un punto físico y la caja usa 200 puntos; en una pantalla de alta densidad con una relación de 2, cada píxel de CSS son 2 por 2 puntos físicos y la caja usa 400 puntos, pero ocupa el mismo tamaño aparente.](../imagenes/densidad-de-pixeles.svg)

---

## 📎 Otras unidades absolutas

| Unidad | Equivale a |
|---|---|
| `1in` | `96px` = `2.54cm` = `25.4mm` = `72pt` = `6pc` |
| `1pc` | `16px` |
| `1pt` | ≈ `1.33px` |

> ⚠️ Un «centímetro» de CSS no es un centímetro real en pantalla. Se usan sobre todo para imprimir.

---

## 💯 El porcentaje `%`

| Propiedad | Se calcula sobre… |
|---|---|
| `width` | El ancho del contenedor |
| `font-size` | La letra del padre |
| `height` | El alto del contenedor (si está definido) |
| `padding`, `margin` | El **ancho** del contenedor |

---

## 🔤 La unidad `em`

- `1em` = el tamaño de letra del elemento (en `font-size`, el del padre).
- **Se acumula** al anidar.

```css
.nivel { font-size: 1.25em; }
```

`16 → 20 → 25 → 31.25 px`

---

## 🧮 `em` acumulativo

![Tres niveles anidados, cada uno con font-size de 1.25em: el primero mide 20 píxeles porque su padre mide 16; el segundo, 25 porque su padre mide 20; y el tercero, 31.25 porque su padre mide 25. A la derecha, los mismos niveles con 1.25rem miden 20 píxeles los tres.](../imagenes/em-acumulativo.svg)

---

## 🌱 La unidad `rem`

- Se mide contra la letra de la **raíz** (`html`).
- **No se acumula**: es predecible.
- Respeta la preferencia de letra de quien visita la página.

> 💡 En esta clase: `html { font-size: 16px; }`.

---

## 🔡 `ex`, `ch` y `lh`

| Unidad | Qué mide |
|---|---|
| `ex` | La altura de la «x» (menor que `1em`) |
| `ch` | El ancho del «0» |
| `lh` | La altura de línea |

`20ch` = veinte «0»; `3lh` = tres líneas. `ex` y `ch` dependen de la tipografía.

---

## 🪟 Unidades de ventana

| Unidad | Qué es |
|---|---|
| `vw` / `vh` | 1% del ancho / alto de la ventana |
| `vmin` / `vmax` | 1% del lado menor / mayor |
| `rlh` | La altura de línea de la raíz |

> ⚠️ Son recientes en parte: comprobá la compatibilidad en MDN.

---

## 🧰 Elegir la unidad

| Situación | Unidad |
|---|---|
| Texto | `rem` |
| Acompañar la letra de un componente | `em` |
| Borde fino | `px` |
| Acompañar al contenedor | `%` |
| Ancho de lectura | `ch` |
| Alto en líneas | `lh` |
| Según la ventana | `vh`, `vw` |

> 💡 Para mezclar unidades existe `calc()`; hoy solo la mencionamos.

---

## 🚧 Errores frecuentes

| Error | Cómo evitarlo |
|---|---|
| `width: 200;` | Un número necesita unidad: `200px` |
| `30 ch` | Sin espacio: `30ch` |
| `height: 50%` sin alto en el contenedor | Definí el alto del contenedor |
| `em` anidado que crece | Usá `rem` |

---

## 🛠️ Actividad práctica

**Taller 01 — Escalá tu página**

Pasar una hoja con tamaños en `px` a unidades relativas.

---

## 🎓 Resumen y evaluación

- ✅ Unidades absolutas y relativas.
- ✅ `px`, densidad, `%`, `em` y `rem`.
- ✅ `ex`, `ch`, `lh` y unidades de ventana.
- ✅ Cómo elegir la unidad.

📝 Ahora: **Quiz 01** (8 ítems).

# 📘 Ejemplo 01 — Tipos de unidades

> 🎓 **Resultados de aprendizaje:** RA-1

## 🧱 Situación inicial

Lucía ya usó `px`, `%`, `em` y `rem` en sus hojas sin pensar mucho en qué significan. Quiere entender qué es una **unidad** y cómo se clasifican. En la página `tipos.html` pone cinco cajas, cada una con
un ancho escrito con una unidad distinta, y dos casos especiales: un número **sin** unidad y el cero.

## 💻 Código

El contenido de `tipos.html` (dentro de `<main>`):

```html
<h2>Absolutas y relativas</h2>
<div class="marco">
  <div class="caja caja--px">200px (absoluta)</div>
  <div class="caja caja--cm">5cm (absoluta)</div>
  <div class="caja caja--porcentaje">50% (relativa al contenedor)</div>
  <div class="caja caja--em">12.5em (relativa a la letra)</div>
  <div class="caja caja--rem">12.5rem (relativa a la letra de la raíz)</div>
</div>

<h2>Sin unidad</h2>
<div class="marco">
  <div class="caja caja--sin-unidad">width: 200 (sin unidad: se ignora)</div>
  <div class="caja caja--cero">margin: 0 (el cero no necesita unidad)</div>
</div>
```

La hoja `css/tipos.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* Un marco de 400px para que el porcentaje tenga contra qué calcularse */
.marco {
  width: 400px;
  margin-bottom: 16px;
  background-color: #eff6ff;
}

.caja {
  background-color: #dbeafe;
  margin-bottom: 8px;
}

/* Absolutas: un tamaño fijo */
.caja--px {
  width: 200px;
}

.caja--cm {
  width: 5cm;
}

/* Relativas: se calculan a partir de otro valor */
.caja--porcentaje {
  width: 50%;
}

.caja--em {
  width: 12.5em;
}

.caja--rem {
  width: 12.5rem;
}

/* Un número distinto de cero sin unidad no es válido: el navegador ignora la declaración */
.caja--sin-unidad {
  width: 200;
}

/* El cero es la única excepción: no necesita unidad */
.caja--cero {
  margin: 0;
}
```

## 🔍 Análisis paso a paso

1. **Qué es una unidad.** En CSS, un número de longitud va acompañado de una **unidad** que dice «en qué se mide»: `200px` son doscientos píxeles. Sin la unidad, el número no dice nada.
2. **Dos tipos.** Las unidades **absolutas** (`px`, `cm`…) tienen un tamaño fijo, que no depende de ningún otro elemento. Las **relativas** (`%`, `em`, `rem`…) se **calculan** a partir de otro valor: el
   contenedor, la letra o la ventana. Se llama **valor de referencia** a ese otro valor.
3. **Absolutas.** `.caja--px` pide `200px` y `.caja--cm`, `5cm`. Las dos son absolutas: el valor calculado no cambia si cambia el contenedor. (`5cm` se convierte en unos `189px`.)
4. **Relativas.** `.caja--porcentaje` pide `50%` y se calcula contra el ancho de su contenedor, el marco de `400px`: da `200px`. `.caja--em` pide `12.5em` y se calcula contra el tamaño de letra del elemento
   (`16px`): `12.5 × 16 = 200px`. `.caja--rem` pide `12.5rem` y se calcula contra el tamaño de letra de la raíz (`16px`): también `200px`.
5. **El mismo resultado, tres caminos.** Las cuatro cajas (`200px`, `50%`, `12.5em` y `12.5rem`) miden lo mismo hoy, pero **cambian de forma distinta** si cambia el contenedor o el tamaño de letra.
6. **Un valor sin unidad.** `width: 200;` **no es válido**: el navegador ignora la declaración y la caja ocupa todo el ancho del marco (`400px`). No da error visible: simplemente no hace nada.
7. **La excepción: el cero.** `0` es la única medida que se escribe sin unidad, porque vale lo mismo en todas.
8. **El tamaño base.** Todas las hojas de esta clase declaran `html { font-size: 16px; }`, el valor por defecto de los navegadores, para que los cálculos den lo mismo en cualquier equipo.

## ✅ Resultado esperado

| Clase | Valor escrito | Tipo | Ancho calculado |
|---|---|---|---|
| `.caja--px` | `200px` | Absoluta | `200px` |
| `.caja--cm` | `5cm` | Absoluta | `188.969px` (≈ `189px`) |
| `.caja--porcentaje` | `50%` | Relativa (al contenedor de `400px`) | `200px` |
| `.caja--em` | `12.5em` | Relativa (a la letra de `16px`) | `200px` |
| `.caja--rem` | `12.5rem` | Relativa (a la letra de la raíz de `16px`) | `200px` |
| `.caja--sin-unidad` | `200` (sin unidad) | Inválida: se ignora | `400px` (el ancho del marco) |
| `.caja--cero` | `margin: 0` | Sin unidad (excepción) | margen `0px` |

- `html` calcula `font-size: 16px`.
- La caja `.caja--sin-unidad` se ve tan ancha como el marco, no como las demás.

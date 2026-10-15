# 📘 Ejemplo 07 — `ex`, `ch` y `lh`

> 🎓 **Resultados de aprendizaje:** RA-6

## 🧱 Situación inicial

Lucía quiere dar a un campo un ancho de «20 caracteres», a un bloque una altura de «tres líneas de texto» y entender qué mide `ex`. Usa las unidades que **dependen de la tipografía**. Lo prueba en `tipograficas.html`.

## 💻 Código

El contenido de `tipograficas.html` (dentro de `<main>`):

```html
<h2>ch: el ancho del cero</h2>
<p class="medida"><span class="cero">0</span></p>
<div class="campo">Un campo de 20 caracteres de ancho</div>

<h2>lh: la altura de una línea</h2>
<div class="tres-lineas">Un bloque de tres líneas de alto, con el texto que sea.</div>

<h2>ex: la altura de la x</h2>
<div class="ancho-em">10em</div>
<div class="ancho-ex">10ex</div>
```

La hoja `css/tipograficas.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* ch: el ancho del carácter «0» de la tipografía del elemento */
.medida {
  font-family: monospace;
}

.cero {
  display: inline-block;
}

.campo {
  font-family: monospace;
  width: 20ch;
  background-color: #dbeafe;
}

/* lh: la altura de una línea de texto del elemento */
.tres-lineas {
  line-height: 1.6;
  height: 3lh;
  background-color: #dbeafe;
}

/* ex: la altura de la «x» de la tipografía; es menor que 1em */
.ancho-em {
  width: 10em;
  background-color: #dbeafe;
}

.ancho-ex {
  width: 10ex;
  background-color: #ccfbf1;
}
```

## 🔍 Análisis paso a paso

1. **`ch`.** Es el ancho del carácter «0» (cero) de la tipografía del elemento. `20ch` son veinte veces ese ancho: sirve para dar a un campo o a un párrafo el ancho de **una cantidad de caracteres**.
2. **Depende de la tipografía.** Con `monospace`, todos los caracteres miden lo mismo; con otra tipografía, el «0» tiene otro ancho y `20ch` cambia. Por eso, en este ejemplo, el ancho en píxeles **no se fija**: se
   describe como relación. En el equipo donde se probó, el «0» mide unos `9.64px` y `.campo` mide unos `192.7px`, es decir, veinte veces ese ancho.
3. **`lh`.** Es la altura de línea (`line-height`) del elemento. `3lh` son tres líneas de texto: con `line-height: 1.6` y letra de `16px`, cada línea mide `25.6px` y el bloque mide unos `76.8px`
   (en Chrome, `76.78px`, porque el navegador redondea la altura de línea).
4. **Para qué sirve `lh`.** Para que un bloque muestre un **número exacto de líneas**, aunque cambie el tamaño de la letra o la altura de línea: la altura acompaña.
5. **`ex`.** Es la altura de la letra «x» minúscula de la tipografía. Es **menor que `1em`**: en el equipo donde se probó, `1ex` mide unos `8.45px` con letra de `16px` (cerca de la mitad de `1em`), y por eso `10ex`
   (unos `84.5px`) es menos de `10em` (`160px`).
6. **Depende de la tipografía.** Igual que `ch`, `ex` cambia con la tipografía; se usa poco.
7. **Compatibilidad.** `lh` es una unidad reciente: comprobá su compatibilidad en MDN antes de usarla en un sitio real; en este ejemplo se verificó en Chrome. Si un navegador no la reconoce, ignora la declaración, como
   un valor sin unidad.

## ✅ Resultado esperado

| Elemento | Escrito | Valor calculado (en el equipo de prueba) |
|---|---|---|
| `.cero` | un «0» en `monospace` | `9.64px` de ancho |
| `.campo` | `width: 20ch` | `192.7px` (20 veces el ancho del «0») |
| `.tres-lineas` | `line-height: 1.6` y `height: 3lh` | altura de línea `25.6px`; alto `76.78px` (≈ `76.8px`) |
| `.ancho-em` | `width: 10em` (letra de `16px`) | `160px` |
| `.ancho-ex` | `width: 10ex` (letra de `16px`) | `84.5px` (menos que `10em`) |

- `.ancho-ex` se ve claramente más angosto que `.ancho-em`: un `ex` es cerca de la mitad de un `em`.
- Los valores de `ch` y `ex` pueden diferir en otros equipos; la relación (veinte «0», menos que `em`) se mantiene.

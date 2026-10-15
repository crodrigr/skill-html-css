# 📘 Ejemplo 06 — La unidad `rem`

> 🎓 **Resultados de aprendizaje:** RA-5

## 🧱 Situación inicial

Lucía vio que `em` se acumula al anidar. Prueba `rem` («root em», `em` de la raíz) con los mismos tres niveles y compara. Después imagina que una persona configuró su navegador con una letra más grande, y cambia el
tamaño de la raíz para ver el efecto. Lo hace en `rem.html`.

## 💻 Código

El contenido de `rem.html` (dentro de `<main>`):

```html
<h2>Con em: se acumula</h2>
<div class="con-em con-em-1">Nivel 1
  <div class="con-em con-em-2">Nivel 2
    <div class="con-em con-em-3">Nivel 3</div>
  </div>
</div>

<h2>Con rem: no se acumula</h2>
<div class="con-rem con-rem-1">Nivel 1
  <div class="con-rem con-rem-2">Nivel 2
    <div class="con-rem con-rem-3">Nivel 3</div>
  </div>
</div>
```

La hoja `css/rem.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* em: cada nivel multiplica sobre el anterior */
.con-em {
  font-size: 1.25em;
}

/* rem: todos los niveles se miden contra la raíz */
.con-rem {
  font-size: 1.25rem;
}
```

## 🔍 Análisis paso a paso

1. **Qué es `rem`.** Es una unidad relativa al tamaño de letra del **elemento raíz** (`html`), no del padre. Siempre se mide contra el mismo valor.
2. **Sin acumulación.** Los tres niveles piden `1.25rem`: los tres miden `1.25 × 16 = 20px`, aunque estén anidados. Con `em`, los mismos niveles darían `20px`, `25px` y `31.25px`.
3. **Por qué importa.** Con `rem`, el tamaño de un elemento no depende de dónde esté: es **predecible**.
4. **Cambiar la raíz.** Si el tamaño de la raíz cambia (por ejemplo, a `20px`), **todo** lo que está en `rem` cambia en proporción: `1.25rem` pasa a `25px` en los tres niveles. Lo que está en `em` anidado cambia
   más todavía: el nivel 3 pasa de `31.25px` a `39.0625px`.
5. **La preferencia de quien visita.** Muchas personas configuran en su navegador un tamaño de letra mayor que `16px`. Si la raíz no fija un valor en `px`, `rem` respeta esa preferencia y el diseño crece con ella. Por eso
   se recomienda `rem` para el texto.
6. **En esta clase.** Fijamos `html { font-size: 16px; }` solo para que los cálculos den lo mismo en cualquier equipo; en un sitio real, conviene dejar que el navegador decida.
7. **Cuándo usar cada una.** `rem` para tamaños de texto y espacios generales; `em` para medidas que deben acompañar a la letra **de un componente** (un botón, una etiqueta).

## ✅ Resultado esperado

| Elemento | Escrito | Con la raíz en `16px` | Con la raíz en `20px` |
|---|---|---|---|
| `.con-em-1` | `1.25em` | `20px` | `25px` |
| `.con-em-2` | `1.25em` | `25px` | `31.25px` |
| `.con-em-3` | `1.25em` | `31.25px` | `39.0625px` |
| `.con-rem-1` | `1.25rem` | `20px` | `25px` |
| `.con-rem-2` | `1.25rem` | `20px` | `25px` |
| `.con-rem-3` | `1.25rem` | `20px` | `25px` |

- Con `em`, los niveles se ven cada vez más grandes; con `rem`, los tres se ven del mismo tamaño.

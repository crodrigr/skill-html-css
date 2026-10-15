# 📘 Ejemplo 05 — La unidad `em`

> 🎓 **Resultados de aprendizaje:** RA-5

## 🧱 Situación inicial

Lucía quiere que cada nivel anidado de una lista de ideas sea un poco más grande que el anterior, y usa `em`. En `em.html` pone tres niveles anidados con `font-size: 1.25em` y una caja con medidas en `em`.

## 💻 Código

El contenido de `em.html` (dentro de `<main>`):

```html
<h2>Un nivel dentro de otro</h2>
<div class="nivel nivel-1">Nivel 1
  <div class="nivel nivel-2">Nivel 2
    <div class="nivel nivel-3">Nivel 3</div>
  </div>
</div>

<h2>En ancho y en relleno</h2>
<div class="caja">font-size: 20px; width: 10em; padding: 1em</div>
```

La hoja `css/em.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* Cada nivel pide 1.25em: se multiplica sobre el tamaño del nivel anterior */
.nivel {
  font-size: 1.25em;
}

/* En width y padding, em se mide contra el tamaño de letra del propio elemento */
.caja {
  font-size: 20px;
  width: 10em;
  padding: 1em;
  background-color: #dbeafe;
}
```

## 🔍 Análisis paso a paso

1. **Qué es `em`.** Es una unidad relativa a la **letra**: `1em` es el tamaño de letra del elemento. Su nombre viene de la «eme» tipográfica.
2. **En `font-size`.** Como el elemento no puede medirse contra su propia letra (todavía no está calculada), `em` se mide contra el tamaño de letra del **padre**: `1.25em` dentro de un padre de `16px` da `20px`.
3. **El efecto acumulativo.** Cada nivel pide `1.25em` **sobre el nivel anterior**: el nivel 1 mide `16 × 1.25 = 20px`; el nivel 2, `20 × 1.25 = 25px`; y el nivel 3, `25 × 1.25 = 31.25px`. Cuantos más niveles,
   más crece (mirá el diagrama de la explicación).
4. **Cómo evitarlo.** Si querés el mismo tamaño en todos los niveles, usá `rem` (Ejemplo 06) o `em` solo en el nivel que corresponde.
5. **En `width`, `padding` y `margin`.** Acá `em` se mide contra el tamaño de letra del **propio elemento**: la caja tiene `font-size: 20px`, así que `10em` son `200px` de ancho y `1em` son `20px` de relleno.
6. **Para qué sirve.** Medidas que **acompañan a la letra**: si agrandás el texto de la caja, su ancho y su relleno crecen con él. Es útil para botones y etiquetas.
7. **Cuidado con el anidado.** Mezclar `em` en `font-size` y en `padding` de elementos anidados hace difícil predecir los valores: calculalos nivel por nivel.

## ✅ Resultado esperado

| Elemento | Escrito | Se calcula contra | Valor calculado |
|---|---|---|---|
| `.nivel-1` | `font-size: 1.25em` | Padre: `16px` | `20px` |
| `.nivel-2` | `font-size: 1.25em` | Padre: `20px` | `25px` |
| `.nivel-3` | `font-size: 1.25em` | Padre: `25px` | `31.25px` |
| `.caja` | `width: 10em` | Su propia letra: `20px` | `200px` |
| `.caja` | `padding: 1em` | Su propia letra: `20px` | `20px` en los cuatro lados |

- Los tres niveles se ven cada vez más grandes, y cada uno dentro del anterior.

# 📘 Ejemplo 03 — Otras unidades absolutas

> 🎓 **Resultados de aprendizaje:** RA-3

## 🧱 Situación inicial

Lucía encontró en una hoja ajena medidas como `2.54cm` y `72pt`, y se pregunta si son lo mismo que `96px`. En `absolutas.html` pone siete cajas con **la misma medida escrita de siete formas**.

## 💻 Código

El contenido de `absolutas.html` (dentro de `<main>`):

```html
<h2>Seis formas de escribir 96 píxeles</h2>
<div class="caja caja--px">96px</div>
<div class="caja caja--in">1in</div>
<div class="caja caja--cm">2.54cm</div>
<div class="caja caja--mm">25.4mm</div>
<div class="caja caja--q">101.6Q</div>
<div class="caja caja--pt">72pt</div>
<div class="caja caja--pc">6pc</div>
```

La hoja `css/absolutas.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.caja {
  height: 24px;
  margin-bottom: 8px;
  background-color: #dbeafe;
}

/* Todas miden lo mismo: 1 pulgada = 96px = 2.54cm = 25.4mm = 101.6Q = 72pt = 6pc */
.caja--px {
  width: 96px;
}

.caja--in {
  width: 1in;
}

.caja--cm {
  width: 2.54cm;
}

.caja--mm {
  width: 25.4mm;
}

.caja--q {
  width: 101.6Q;
}

.caja--pt {
  width: 72pt;
}

.caja--pc {
  width: 6pc;
}
```

## 🔍 Análisis paso a paso

1. **Las unidades.** `cm` (centímetro), `mm` (milímetro), `Q` (cuarto de milímetro), `in` (pulgada), `pt` (punto) y `pc` (pica) son **absolutas**: su valor no depende de otro elemento.
2. **La equivalencia.** Una pulgada son `96px`; el navegador convierte todo a píxeles de CSS con estas relaciones: `1in = 96px = 2.54cm = 25.4mm = 101.6Q = 72pt = 6pc`.
3. **Cada caja.** `1in`, `2.54cm`, `25.4mm`, `101.6Q`, `72pt` y `6pc` valen **lo mismo** que `96px`: las siete cajas miden `96px`.
4. **Otras equivalencias útiles.** `1cm` ≈ `37.8px`; `1mm` ≈ `3.78px`; `1pt` ≈ `1.33px`; `1pc` = `16px`.
5. **Por qué casi no se usan en pantalla.** Estas unidades vienen de la impresión. En una **impresora**, `1cm` coincide con un centímetro real. En una **pantalla**, el navegador aplica la relación fija de arriba (`1in = 96px`) y el tamaño físico de ese «centímetro» depende del tamaño y de la densidad
   de la pantalla: no se puede contar con que mida un centímetro de regla. Por eso sirven sobre todo en hojas de estilo **para imprimir**.
6. **Qué usar en pantalla.** Para pantalla, `px` para medidas fijas y las unidades relativas para todo lo que deba adaptarse (se comparan en el Ejemplo 09).
7. **`Q`.** Es la menos común: cada `Q` es un cuarto de milímetro. Se menciona para reconocerla.

## ✅ Resultado esperado

| Clase | Valor escrito | Ancho calculado |
|---|---|---|
| `.caja--px` | `96px` | `96px` |
| `.caja--in` | `1in` | `96px` |
| `.caja--cm` | `2.54cm` | `96px` |
| `.caja--mm` | `25.4mm` | `96px` |
| `.caja--q` | `101.6Q` | `96px` |
| `.caja--pt` | `72pt` | `96px` |
| `.caja--pc` | `6pc` | `96px` |

- Las siete cajas se ven **exactamente del mismo ancho**.

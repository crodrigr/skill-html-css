# 📘 Ejemplo 04 — Porcentajes

> 🎓 **Resultados de aprendizaje:** RA-4

## 🧱 Situación inicial

Lucía quiere que algunas medidas sean «la mitad de» otra. Usa el porcentaje (`%`) y se encuentra con que **no siempre se calcula contra lo mismo**: depende de la propiedad. En `porcentajes.html` prueba
el ancho, el tamaño de letra, el alto y el relleno, siempre dentro de un marco de `400px` de ancho.

## 💻 Código

El contenido de `porcentajes.html` (dentro de `<main>`):

```html
<h2>Ancho</h2>
<div class="marco">
  <div class="mitad">width: 50%</div>
</div>

<h2>Tamaño de letra</h2>
<div class="marco">
  <p class="grande">font-size: 150%</p>
</div>

<h2>Alto</h2>
<div class="marco marco--sin-alto">
  <div class="mitad-alto">height: 50%</div>
</div>
<div class="marco marco--con-alto">
  <div class="mitad-alto">height: 50%</div>
</div>

<h2>Relleno</h2>
<div class="marco">
  <div class="relleno">padding: 10%</div>
</div>
```

La hoja `css/porcentajes.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* El contenedor: 400px de ancho */
.marco {
  width: 400px;
  margin-bottom: 16px;
  background-color: #eff6ff;
}

/* El ancho en %: la mitad del ancho del contenedor */
.mitad {
  width: 50%;
  background-color: #dbeafe;
}

/* El tamaño de letra en %: se calcula sobre la letra del padre (16px) */
.grande {
  font-size: 150%;
  margin: 0;
}

/* El alto en %: solo funciona si el contenedor tiene un alto definido */
.mitad-alto {
  height: 50%;
  line-height: 1.5;
  background-color: #dbeafe;
}

.marco--con-alto {
  height: 200px;
}

/* El relleno en %: se calcula sobre el ANCHO del contenedor, también arriba y abajo */
.relleno {
  padding: 10%;
  background-color: #dbeafe;
}
```

## 🔍 Análisis paso a paso

1. **Un porcentaje es relativo.** `%` significa «tanto por ciento **de otro valor**». Ese otro valor (el valor de referencia) cambia según la propiedad.
2. **En `width`.** Se calcula sobre el **ancho del contenedor**: `50%` de `400px` son `200px`.
3. **En `font-size`.** Se calcula sobre el **tamaño de letra del padre**: `150%` de `16px` son `24px`.
4. **En `height`.** Se calcula sobre el **alto del contenedor, pero solo si ese alto está definido**. En el marco `.marco--con-alto` (`height: 200px`), `50%` da `100px`. En el marco sin alto definido, el porcentaje
   **no se puede calcular** y el elemento queda con su alto automático: acá, una línea de texto de `24px` (`1.5 × 16px`).
5. **En `padding` (y en `margin`).** Se calcula sobre el **ancho** del contenedor, **también para arriba y abajo**: `10%` de `400px` son `40px` en los **cuatro** lados, aunque el contenedor sea más bajo.
6. **Cuándo conviene.** El porcentaje sirve para medidas que deben **acompañar** al contenedor: si el marco mide `600px`, `50%` pasa a ser `300px` sin tocar la hoja.
7. **Cuidado.** Un porcentaje de alto sin alto definido es un error muy común: no da ningún aviso, solo no funciona.

## ✅ Resultado esperado

| Clase | Propiedad y valor | Referencia | Valor calculado |
|---|---|---|---|
| `.mitad` | `width: 50%` | Ancho del contenedor (`400px`) | `200px` |
| `.grande` | `font-size: 150%` | Letra del padre (`16px`) | `24px` |
| `.marco--sin-alto .mitad-alto` | `height: 50%` | Alto del contenedor: no definido | `24px` (alto automático) |
| `.marco--con-alto .mitad-alto` | `height: 50%` | Alto del contenedor (`200px`) | `100px` |
| `.relleno` | `padding: 10%` | **Ancho** del contenedor (`400px`) | `40px` arriba, derecha, abajo e izquierda |

- El elemento con alto en porcentaje y sin alto definido en el contenedor se ve de una sola línea; con el alto definido, ocupa la mitad del marco.

# 📘 Ejemplo 07 — La función `cubic-bezier()`

> 🎓 **Resultados de aprendizaje:** RA-5
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere un movimiento con carácter propio: que la caja se pase un poco de su destino y vuelva. Las palabras clave no lo permiten. En `bezier.html` crea sus propias curvas con `cubic-bezier()`.

## 💻 Código

El contenido de `bezier.html` (dentro de `<main>`):

```html
<h2>cubic-bezier(0.68, -0.55, 0.27, 1.55)</h2>
<div class="pista"><div class="caja rebasa"></div></div>

<h2>cubic-bezier(0.1, 0.7, 1, 0.1)</h2>
<div class="pista"><div class="caja propia"></div></div>

<h2>cubic-bezier(0.42, 0, 0.58, 1)</h2>
<div class="pista"><div class="caja igual-a-ease-in-out"></div></div>

<h2>Un valor x fuera de [0, 1]</h2>
<div class="pista"><div class="caja invalida"></div></div>
```

La hoja `css/bezier.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* La pista de 300px por la que se mueve la caja de 100px (recorre 200px) */
.pista {
  width: 300px;
  margin-bottom: 0.75rem;
  background-color: #e5e7eb;
}

.caja {
  width: 100px;
  height: 40px;
  background-color: #2563eb;
}

/* Al pasar el cursor sobre la pista, la caja se desplaza 200px */
.pista:hover .caja {
  transform: translateX(200px);
}

/* Los valores de y pueden salirse de 0 a 1: la caja se pasa de su destino y vuelve */
.rebasa {
  transition: transform 2s cubic-bezier(0.68, -0.55, 0.27, 1.55);
}

/* Una curva propia: arranca rápido, casi se detiene y termina rápido */
.propia {
  transition: transform 2s cubic-bezier(0.1, 0.7, 1, 0.1);
}

/* Estos cuatro valores son los de ease-in-out */
.igual-a-ease-in-out {
  transition: transform 2s cubic-bezier(0.42, 0, 0.58, 1);
}

/* x1 = 2 está fuera de 0 a 1: la función es inválida y el navegador la ignora */
.invalida {
  transition: transform 2s cubic-bezier(2, 0, 0.5, 1);
}
```

## 🔍 Análisis paso a paso

1. **Qué es.** `cubic-bezier(x1, y1, x2, y2)` define una curva con **cuatro números**: son las coordenadas de **dos puntos de control** (P1 y P2). La curva siempre empieza en `(0, 0)` y termina en `(1, 1)`; P1 y P2 «tiran» de ella (diagrama de la explicación).
2. **Qué representa cada eje.** El eje horizontal es el **tiempo** (de `0` a `1`) y el vertical, el **progreso del cambio** (`0` es el inicio y `1`, el final). Una curva empinada es un cambio rápido; una curva plana, un cambio lento.
3. **Los límites.** `x1` y `x2` **deben estar entre `0` y `1`** (el tiempo no retrocede). `y1` e `y2` **pueden salirse**: la curva se pasa de `1` o baja de `0`.
4. **`.rebasa`** usa `cubic-bezier(0.68, -0.55, 0.27, 1.55)`. Como `y1` es negativo, la caja **retrocede** al principio (`-16.6px` a los `500 ms`); como `y2` pasa de `1`, **se pasa del destino** (`217.8px` a los `1500 ms`, con un destino de `200px`) y vuelve a `200px`.
5. **`.propia`** usa `cubic-bezier(0.1, 0.7, 1, 0.1)`: arranca muy rápido (`70.1px` a los `500 ms`), casi se detiene (`83.5px` a los `1000 ms` y `98px` a los `1500 ms`) y recorre el resto de golpe al final.
6. **Las palabras clave son curvas.** `.igual-a-ease-in-out` usa `cubic-bezier(0.42, 0, 0.58, 1)`, que son exactamente los valores de `ease-in-out`: da los mismos `25.8px`, `100px` y `174.2px`.
7. **Un valor inválido.** `.invalida` escribe `x1 = 2`, fuera de `0` a `1`. Toda la declaración `transition` se **ignora**: la duración calculada es `0s` y no se crea ninguna transición; la caja llega a `200px` de golpe. Ojo: no se usa `ease` como respaldo.
8. **Comprobación.** Los valores medidos coinciden con la fórmula de la curva de Bézier (con un error menor que `0.1px`).

## ✅ Resultado esperado

| Caja | `cubic-bezier` | `25%` (`500 ms`) | `50%` (`1000 ms`) | `75%` (`1500 ms`) | `100%` |
|---|---|---|---|---|---|
| `.rebasa` | `(0.68, -0.55, 0.27, 1.55)` | `-16.6px` | `119.3px` | `217.8px` | `200px` |
| `.propia` | `(0.1, 0.7, 1, 0.1)` | `70.1px` | `83.5px` | `98px` | `200px` |
| `.igual-a-ease-in-out` | `(0.42, 0, 0.58, 1)` | `25.8px` | `100px` | `174.2px` | `200px` |
| `.invalida` | `(2, 0, 0.5, 1)` | sin transición: `200px` de golpe | | | |

- `.rebasa` se ve como un movimiento «elástico»: retrocede un poco, se pasa del destino y vuelve.

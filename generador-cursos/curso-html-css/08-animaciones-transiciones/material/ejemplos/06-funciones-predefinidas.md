# 📘 Ejemplo 06 — Funciones de tiempo predefinidas

> 🎓 **Resultados de aprendizaje:** RA-4
>
> 📐 **Cómo se midió.** Con Chrome: se fijó el instante exacto de cada transición o animación y se leyó el valor calculado en ese momento. Cuando el ejemplo habla del cursor, se simuló el estado `:hover`. Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía quiere que una caja recorra una pista en `2s`, pero no sabe qué ritmo elegir. En `predefinidas.html` pone cinco cajas, cada una con una función de tiempo distinta, y las mueve a la vez con el cursor sobre la pista.

## 💻 Código

El contenido de `predefinidas.html` (dentro de `<main>`):

```html
<h2>linear</h2>
<div class="pista"><div class="caja linear"></div></div>
<h2>ease</h2>
<div class="pista"><div class="caja ease"></div></div>
<h2>ease-in</h2>
<div class="pista"><div class="caja ease-in"></div></div>
<h2>ease-out</h2>
<div class="pista"><div class="caja ease-out"></div></div>
<h2>ease-in-out</h2>
<div class="pista"><div class="caja ease-in-out"></div></div>
```

La hoja `css/predefinidas.css`:

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

/* La misma duración (2s) con cada función de tiempo predefinida */
.linear {
  transition: transform 2s linear;
}

.ease {
  transition: transform 2s ease;
}

.ease-in {
  transition: transform 2s ease-in;
}

.ease-out {
  transition: transform 2s ease-out;
}

.ease-in-out {
  transition: transform 2s ease-in-out;
}
```

## 🔍 Análisis paso a paso

1. **Qué es una función de tiempo.** Define **cómo avanza** el cambio durante la duración: no todo el cambio tiene que ir a la misma velocidad.
2. **Las cinco predefinidas.** `linear` (velocidad constante), `ease` (arranca rápido y termina despacio; es la de por defecto), `ease-in` (arranca despacio y termina rápido), `ease-out` (arranca rápido y termina despacio) y `ease-in-out` (arranca y termina despacio).
3. **Qué se midió.** La caja se desplaza `200px` (`translateX`) en `2s`. En cada instante, la posición es `200 × progreso`. A la **mitad del tiempo** (`1000 ms`) `linear` va en `100px`, `ease` en `160.5px`, `ease-in` en `63.1px`, `ease-out` en `136.9px` y `ease-in-out` en `100px`.
4. **`ease` no es `ease-out`.** Se parecen, pero `ease` arranca con un empujón inicial más fuerte (`81.7px` a los `500 ms`, frente a `75.6px` de `ease-out`) y termina más despacio.
5. **`ease-in` y `ease-out` son espejos.** A los `500 ms` `ease-in` va en `18.7px` y `ease-out` en `75.6px`; a los `1500 ms`, `124.4px` y `181.3px`. `ease-in-out` es simétrica: a los `500 ms` y a los `1500 ms` está a la misma distancia de los extremos (`25.8px` y `174.2px`).
6. **Cómo elegir.** Para lo que **entra** a la pantalla conviene `ease-out` (llega rápido y se asienta); para lo que **sale**, `ease-in`; para movimientos que van y vuelven, `ease-in-out`; `linear` para giros continuos y barras de progreso.
7. **Cada valor sale de una curva.** Cada palabra clave equivale a un `cubic-bezier()` (Ejemplo 07): `ease` es `cubic-bezier(0.25, 0.1, 0.25, 1)`, `ease-in` es `cubic-bezier(0.42, 0, 1, 1)`, `ease-out` es `cubic-bezier(0, 0, 0.58, 1)` y `ease-in-out` es `cubic-bezier(0.42, 0, 0.58, 1)`. Los valores medidos coinciden con la fórmula de la curva.

## ✅ Resultado esperado

| Función | `0%` (`0 ms`) | `25%` (`500 ms`) | `50%` (`1000 ms`) | `75%` (`1500 ms`) | `100%` (`2000 ms`) |
|---|---|---|---|---|---|
| `linear` | `0px` | `50px` | `100px` | `150px` | `200px` |
| `ease` | `0px` | `81.7px` | `160.5px` | `192.1px` | `200px` |
| `ease-in` | `0px` | `18.7px` | `63.1px` | `124.4px` | `200px` |
| `ease-out` | `0px` | `75.6px` | `136.9px` | `181.3px` | `200px` |
| `ease-in-out` | `0px` | `25.8px` | `100px` | `174.2px` | `200px` |

- Las cinco cajas parten y llegan a la vez, pero a mitad de camino van en lugares distintos: `ease` y `ease-out` van adelante, `ease-in` atrás y `linear` justo en el medio.

# 📘 Ejemplo 09 — Desborde del contenido (`overflow`)

> 🕐 **Sesión 2** · 🎓 **Resultados de aprendizaje:** RA-7

## 🧱 Situación inicial

Lucía tiene una caja de `200px × 80px` con un contenido de `400px × 160px`: no entra. Quiere ver qué pasa con cada valor de `overflow` y cómo controlar los ejes por
separado. Lo prueba en `overflow.html` con cinco recuadros iguales.

## 💻 Código

El contenido de `overflow.html` (dentro de `<main>`):

```html
<h2>Cinco formas de tratar el desborde</h2>
<p>Cada recuadro mide 200 por 80 píxeles y su contenido, 400 por 160.</p>
<div class="recuadro recuadro--visible"><div class="contenido">visible</div></div>
<div class="recuadro recuadro--oculto"><div class="contenido">hidden</div></div>
<div class="recuadro recuadro--barras"><div class="contenido">scroll</div></div>
<div class="recuadro recuadro--auto"><div class="contenido">auto</div></div>
<div class="recuadro recuadro--solo-x"><div class="contenido">overflow-x: scroll y overflow-y: hidden</div></div>
```

La hoja `css/overflow.css`:

```css
/* Un recuadro pequeño con un contenido que no entra */
.recuadro {
  width: 200px;
  height: 80px;
  border: 2px solid #1e3a8a;
  margin-bottom: 24px;
}

.contenido {
  width: 400px;
  height: 160px;
  background-color: #fef3c7;
}

/* Por defecto el contenido sobresale; el margen deja lugar para verlo */
.recuadro--visible {
  overflow: visible;
  margin-bottom: 120px;
}

/* Se recorta lo que no entra */
.recuadro--oculto {
  overflow: hidden;
}

/* Siempre hay barras de desplazamiento */
.recuadro--barras {
  overflow: scroll;
}

/* Hay barras solo si el contenido no entra */
.recuadro--auto {
  overflow: auto;
}

/* Un valor para cada eje */
.recuadro--solo-x {
  overflow-x: scroll;
  overflow-y: hidden;
}
```

## 🔍 Análisis paso a paso

1. **El problema.** El contenido (`400px × 160px`) es el doble que la caja (`200px × 80px`). A lo que no entra se le llama **desborde** (*overflow*).
2. **`visible` (el valor inicial).** El contenido **sobresale** de la caja y se dibuja fuera de ella, sobre lo que haya debajo. Por eso el recuadro tiene un margen
   inferior grande: sin él, taparía a los siguientes.
3. **`hidden`.** Lo que no entra se **recorta**, y no hay barras. El contenido sigue ahí (su `scrollWidth` es `400`), pero no se ve.
4. **`scroll`.** Recorta y **siempre** muestra las barras de desplazamiento, haya o no desborde.
5. **`auto`.** Recorta y muestra las barras **solo si hace falta**. Es la opción más común para cajas con texto de largo variable.
6. **Un valor por eje.** `overflow-x` controla el eje horizontal y `overflow-y`, el vertical. `.recuadro--solo-x` pone `scroll` en horizontal y `hidden` en vertical: aparece
   la barra horizontal y lo que sobra hacia abajo se recorta. También se puede escribir `overflow: scroll hidden;`, con el primer valor para `x` y el segundo para `y`.
7. **Aviso.** Si un eje es `visible` y el otro no, el `visible` se comporta como `auto`: no podés tener un eje visible y el otro recortado.
8. **Qué no vemos.** Existen también el valor `clip` y la propiedad `text-overflow`, que quedan fuera de esta clase.

## ✅ Resultado esperado

| Recuadro | `overflow` | `offsetWidth` | `scrollWidth` | `clientWidth` |
|---|---|---|---|---|
| `.recuadro--visible` | `visible` | 204 | 400 | 200 |
| `.recuadro--oculto` | `hidden` | 204 | 400 | 200 |
| `.recuadro--barras` | `scroll` | 204 | 400 | 185 (*) |
| `.recuadro--auto` | `auto` | 204 | 400 | menor que 200 (*) |

(*) La barra de desplazamiento ocupa unos píxeles dentro de la caja; el tamaño depende del navegador y del sistema (en Chrome para Linux, 15px).

- Todos miden `204px` de borde a borde: `200px` de contenido y `2px` de borde a cada lado.
- `scrollHeight` vale `160` en todos los recuadros que recortan o desplazan.
- En `.recuadro--solo-x` solo se ve la barra horizontal.

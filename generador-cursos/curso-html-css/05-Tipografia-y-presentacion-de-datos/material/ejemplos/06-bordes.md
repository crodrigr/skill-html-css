# 📘 Ejemplo 06 — Bordes

> 🕐 **Sesión 2** · 🎓 **Resultados de aprendizaje:** RA-6

## 🧱 Situación inicial

Lucía quiere enmarcar bloques de su sitio: una nota, una tarjeta, un recuadro. Prueba los distintos estilos de borde, escribe el borde con propiedades separadas y con la
abreviatura, y da a una caja un borde **distinto en cada lado**. Lo practica en `bordes.html`.

## 💻 Código

El contenido de `bordes.html` (dentro de `<main>`):

```html
<h2>Estilos de borde</h2>
<div class="borde borde--solido">Sólido</div>
<div class="borde borde--punteado">Punteado</div>
<div class="borde borde--discontinuo">Discontinuo</div>
<div class="borde borde--doble">Doble</div>
<div class="borde borde--sin-estilo">Sin estilo: no se ve</div>

<h2>Propiedades por separado</h2>
<div class="borde borde--componentes">Ancho, estilo y color por separado</div>

<h2>Un borde distinto en cada lado</h2>
<div class="borde borde--lados">Cuatro lados distintos</div>
<div class="borde borde--solo-abajo">Solo el lado de abajo</div>

<h2>Uno a cuatro valores</h2>
<div class="borde borde--valores">Anchos y colores en dos valores</div>
```

La hoja `css/bordes.css`:

```css
/* Relleno común para que el texto no toque el borde */
.borde {
  padding: 12px;
  margin-bottom: 12px;
}

/* La abreviatura: ancho, estilo y color */
.borde--solido {
  border: 3px solid #2563eb;
}

.borde--punteado {
  border: 3px dotted #2563eb;
}

.borde--discontinuo {
  border: 3px dashed #2563eb;
}

.borde--doble {
  border: 6px double #2563eb;
}

/* Sin estilo no hay borde: el estilo por defecto es none y el ancho se reduce a 0 */
.borde--sin-estilo {
  border: 3px #2563eb;
}

/* Las tres propiedades por separado */
.borde--componentes {
  border-width: 2px;
  border-style: solid;
  border-color: #16a34a;
}

/* Un borde distinto por lado */
.borde--lados {
  border-top: 4px solid #1e3a8a;
  border-right: 1px solid #94a3b8;
  border-bottom: 4px double #1e3a8a;
  border-left: 1px solid #94a3b8;
}

.borde--solo-abajo {
  border-bottom: 3px solid #f59e0b;
}

/* Con dos valores: el primero es arriba y abajo; el segundo, izquierda y derecha */
.borde--valores {
  border-style: solid;
  border-width: 1px 6px;
  border-color: #2563eb #16a34a;
}
```

## 🔍 Análisis paso a paso

1. **Las tres propiedades de un borde.** Un borde tiene **grosor** (`border-width`), **estilo** (`border-style`) y **color** (`border-color`). La abreviatura `border` las junta
   en una sola declaración: `border: 3px solid #2563eb;`.
2. **Estilos.** `solid` (continuo), `dotted` (de puntos), `dashed` (de rayas) y `double` (doble línea; con 1px o 2px no se distinguen las dos líneas, por eso conviene 3px o más).
3. **Sin estilo no hay borde.** El estilo inicial es `none`. Por eso `border: 3px #2563eb;` no dibuja nada: el estilo calculado es `none` y el grosor se reduce a **0px**,
   aunque hayas escrito 3px. Es el error más común con los bordes.
4. **Por separado.** `border-width: 2px; border-style: solid; border-color: #16a34a;` da el mismo resultado que `border: 2px solid #16a34a;`. La forma por separado sirve
   cuando querés cambiar una sola cosa más adelante.
5. **Un borde por lado.** `border-top`, `border-right`, `border-bottom` y `border-left` aceptan, cada uno, grosor, estilo y color. `.borde--lados` pone arriba `4px solid`,
   a la derecha y a la izquierda `1px solid` y abajo `4px double`.
6. **Un solo lado.** `.borde--solo-abajo` dibuja solamente el borde de abajo: los otros tres quedan en `0px`.
7. **Uno a cuatro valores.** `border-width` y `border-color` aceptan uno a cuatro valores, con la misma regla que `margin`: con **dos**, el primero es arriba y abajo y el segundo,
   izquierda y derecha. `.borde--valores` da `1px` arriba y abajo, `6px` a los costados, y azul arriba y abajo con verde a los costados. Las reglas completas están en el
   [Ejemplo 10](10-margenes-y-rellenos.md).
8. **El borde suma tamaño.** El borde es una de las capas de la caja y **agranda** el elemento. Se mide en el [Ejemplo 08](08-modelo-de-cajas.md).

## ✅ Resultado esperado

| Clase | Propiedad | Valor calculado |
|---|---|---|
| `.borde--solido` | ancho / estilo / color | `3px` / `solid` / `rgb(37, 99, 235)` |
| `.borde--punteado`, `.borde--discontinuo` | estilo | `dotted`, `dashed` |
| `.borde--doble` | estilo / ancho | `double` / `6px` |
| `.borde--sin-estilo` | estilo / ancho | `none` / `0px` (no se ve) |
| `.borde--componentes` | ancho / color | `2px` / `rgb(22, 163, 74)` |
| `.borde--lados` | arriba, derecha, abajo, izquierda | `4px solid`, `1px solid`, `4px double`, `1px solid` |
| `.borde--solo-abajo` | arriba / abajo | `0px` / `3px` |
| `.borde--valores` | anchos (arriba, derecha, abajo, izquierda) | `1px`, `6px`, `1px`, `6px` |
| `.borde--valores` | colores (arriba, derecha, abajo, izquierda) | azul, verde, azul, verde |

- La caja `.borde--sin-estilo` se muestra **sin borde**.
- La caja `.borde--lados` tiene un marco grueso arriba y doble abajo, y más fino a los costados.

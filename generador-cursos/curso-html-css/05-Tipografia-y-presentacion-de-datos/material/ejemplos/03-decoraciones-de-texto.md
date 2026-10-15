# 📘 Ejemplo 03 — Decoraciones de texto

> 🕐 **Sesión 1** · 🎓 **Resultados de aprendizaje:** RA-4

## 🧱 Situación inicial

Lucía quiere destacar algunas partes de su artículo: subrayar, tachar un dato viejo, marcar un título con una línea y dar profundidad a un título con una sombra. También
quiere saber cómo quitar el subrayado de un enlace sin que deje de verse como enlace. Lo prueba en `decoraciones.html`.

## 💻 Código

El contenido de `decoraciones.html` (dentro de `<main>`):

```html
<h2>Líneas</h2>
<p class="subrayado">Texto subrayado</p>
<p class="tachado">Texto tachado</p>
<p class="superior">Texto con línea superior</p>
<p class="ondulado">Subrayado ondulado en rojo</p>
<p class="doble">Subrayado doble en verde</p>
<p>Un enlace que <a class="limpio" href="index.html">no se subraya</a> y otro que <a href="index.html">sí</a>.</p>

<h2>Sombras</h2>
<p class="sombra">Texto con sombra</p>
<p class="resplandor">Texto con resplandor</p>
<p class="relieve">Texto en relieve</p>
```

La hoja `css/decoraciones.css`:

```css
/* Líneas: tipo, estilo y color en una sola declaración */
.subrayado {
  text-decoration: underline;
}

.tachado {
  text-decoration: line-through;
}

.superior {
  text-decoration: overline;
}

.ondulado {
  text-decoration: underline wavy #dc2626;
}

.doble {
  text-decoration: underline double #16a34a;
}

/* Quitar el subrayado de un enlace: hay que dejar otra señal de que es un enlace */
.limpio {
  text-decoration: none;
}

/* Sombras: desplazamiento horizontal, vertical, desenfoque y color */
.sombra {
  text-shadow: 2px 2px 4px #94a3b8;
}

.resplandor {
  text-shadow: 0 0 8px #f59e0b;
}

/* Dos sombras a la vez, separadas por una coma */
.relieve {
  color: #1e3a8a;
  text-shadow: -1px -1px 0 #ffffff, 1px 1px 0 #94a3b8;
}
```

## 🔍 Análisis paso a paso

1. **La línea.** `text-decoration` es una **abreviatura** de `text-decoration-line` (qué línea), `text-decoration-style` (cómo se dibuja), `text-decoration-color` (de qué
   color) y `text-decoration-thickness` (qué grosor, que no usamos en esta clase). Las líneas son `underline` (debajo), `overline` (encima) y `line-through` (tachado).
2. **El estilo.** `solid` (continua, el valor inicial), `double`, `dotted`, `dashed` y `wavy` (ondulada).
3. **Todo junto.** `underline wavy #dc2626` pide una línea de **subrayado**, **ondulada** y de color **rojo**. Los tres valores pueden ir en cualquier orden.
4. **Valores iniciales.** Si no indicás el estilo, es `solid`; si no indicás el color, usa el color del texto (`currentcolor`).
5. **Quitar el subrayado.** `text-decoration: none` lo elimina. Pero los enlaces **ya vienen subrayados** y mucha gente depende de esa señal para reconocerlos: MDN advierte
   que hay que tener cuidado al quitarlo. Si lo quitás, dejá otra señal clara (un color distinto o un fondo).
6. **`text-shadow`.** Sus valores son: desplazamiento horizontal, desplazamiento vertical, desenfoque (opcional) y color. Solo los dos desplazamientos son obligatorios.
   `2px 2px 4px #94a3b8` baja y mueve la sombra 2px y la desenfoca 4px; con desplazamientos de `0` y un desenfoque, la sombra rodea las letras como un **resplandor**.
7. **Valores negativos y varias sombras.** Los desplazamientos pueden ser negativos (hacia la izquierda o hacia arriba); el desenfoque, no. Se pueden dar **varias
   sombras** separadas por comas: la primera queda encima. `.relieve` usa dos para dar la ilusión de relieve.
8. **Legibilidad.** Una sombra muy fuerte o muy desenfocada cansa la vista; usala en títulos, no en párrafos largos.

## ✅ Resultado esperado

| Clase | Propiedad | Valor calculado |
|---|---|---|
| `.subrayado`, `.tachado`, `.superior` | `text-decoration-line` | `underline`, `line-through`, `overline` |
| `.ondulado` | línea / estilo / color | `underline` / `wavy` / `rgb(220, 38, 38)` |
| `.doble` | estilo / color | `double` / `rgb(22, 163, 74)` |
| `.limpio` | `text-decoration-line` | `none` |
| `.sombra` | `text-shadow` | `rgb(148, 163, 184) 2px 2px 4px` |
| `.resplandor` | `text-shadow` | `rgb(245, 158, 11) 0px 0px 8px` |
| `.relieve` | `text-shadow` | `rgb(255, 255, 255) -1px -1px 0px, rgb(148, 163, 184) 1px 1px 0px` |

- El enlace con `.limpio` se ve sin subrayado y el otro enlace, con su subrayado habitual.
- El texto con `.resplandor` se ve rodeado por un halo anaranjado.

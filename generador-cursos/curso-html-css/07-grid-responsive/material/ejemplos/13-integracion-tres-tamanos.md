# 📘 Ejemplo 13 — Integración: una página en tres tamaños

> 🎓 **Resultados de aprendizaje:** RA-6, RA-7
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Lucía junta todo: una página con cabecera, menú, contenido, lateral y pie que se reorganiza según el ancho. En `integracion.html` usa Grid con **dos puntos de ruptura** (`600px` y `900px`) y la estrategia móvil primero.

## 💻 Código

El contenido de `integracion.html` (dentro de `<main>`):

```html
<div class="sitio">
  <div class="cabecera">Cabecera</div>
  <div class="menu">Menú</div>
  <div class="contenido">Contenido</div>
  <div class="lateral">Lateral</div>
  <div class="pie">Pie</div>
</div>
```

La hoja `css/integracion.css`:

```css
/* Tamaño base: 16px, declarado para que los cálculos no dependan del equipo */
html {
  font-size: 16px;
}

/* Sin margen en el cuerpo: las cuadrículas ocupan todo el ancho de la ventana */
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

/* Que el ancho incluya el relleno y el borde (se explica en el Ejemplo 08) */
* {
  box-sizing: border-box;
}

.sitio > div {
  padding: 1rem;
  background-color: #dbeafe;
}

.cabecera,
.pie {
  background-color: #fef3c7;
}

/* TELÉFONO (menos de 600px): una sola columna, los bloques se apilan */
.sitio {
  display: grid;
  grid-template-columns: 1fr;
  gap: 16px;
}

/* TABLETA (600px o más): dos columnas; la cabecera, el lateral y el pie abarcan las dos */
@media (min-width: 600px) {
  .sitio {
    grid-template-columns: 200px 1fr;
  }

  .cabecera,
  .lateral,
  .pie {
    grid-column: 1 / -1;
  }
}

/* COMPUTADOR (900px o más): tres columnas; el lateral vuelve a ocupar solo una */
@media (min-width: 900px) {
  .sitio {
    grid-template-columns: 200px 1fr 200px;
  }

  .lateral {
    grid-column: auto;
  }
}
```

## 🔍 Análisis paso a paso

1. **Base (teléfono, menos de `600px`).** Una sola columna (`1fr`) y un `gap` de `16px`: los cinco bloques se **apilan** en el orden del HTML, cada uno a todo el ancho (`500px` en una ventana de `500px`).
2. **Tableta (`600px` o más).** `.sitio` pasa a dos columnas `200px 1fr`. La cabecera, el lateral y el pie usan `grid-column: 1 / -1` (de la primera a la **última** línea) y abarcan las dos columnas; el menú y el contenido quedan **lado a lado** en una fila. En `800px`: `200px 584px` (`800 − 200 − 16`).
3. **Computador (`900px` o más).** Tres columnas `200px 1fr 200px`. La consulta de `900px` **solo reemplaza** las columnas y devuelve el lateral a **una** celda con `grid-column: auto`: pasa a la tercera columna, a la derecha del contenido. En `1200px`: `200px 768px 200px` (`1200 − 400 − 32`).
4. **Qué se reutiliza.** La consulta de `900px` no vuelve a escribir todo: las reglas de la cabecera y el pie (`1 / -1`) siguen valiendo porque ya se aplicaron desde `600px`. Cada consulta cambia **solo lo que cambia**.
5. **El orden de las consultas.** Van de menor a mayor (`600px` y luego `900px`): en una ventana de `1200px` se cumplen las dos y gana la segunda, que es la que se quiere.
6. **Resultado.** Una misma página con una, dos y tres columnas **sin duplicar el HTML**. Probala en tu navegador arrastrando el borde de la ventana: el diseño cambia exactamente en `600px` y en `900px`.

## ✅ Resultado esperado

| Medida | `500px` | `800px` | `1200px` |
|---|---|---|---|
| `.sitio`, columnas | `500px` | `200px 584px` | `200px 768px 200px` |
| `.cabecera`, ancho | `500px` | `800px` | `1200px` |
| `.menu`, ancho | `500px` | `200px` | `200px` |
| `.contenido`, ancho | `500px` | `584px` | `768px` |
| `.lateral`, ancho / `offsetLeft` | `500px` / `0` | `800px` / `0` (abarca las dos columnas) | `200px` / `1000` (tercera columna) |
| `.pie`, ancho | `500px` | `800px` | `1200px` |

- En teléfono todo se apila; en tableta el lateral va debajo del contenido; en computador va a su derecha.

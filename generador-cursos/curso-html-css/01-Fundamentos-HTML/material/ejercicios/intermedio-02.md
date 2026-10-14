# 🟡 Intermedio 02 — Arreglá la galería de Mateo

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-6

## 🧱 Estado inicial

Abrí [`galeria.html`](../recursos/portafolio-inicial/galeria.html) de la carpeta `portafolio-inicial`. La carpeta del sitio
tiene esta forma:

```text
portafolio-inicial/
├── galeria.html
├── imagenes/
│   ├── boda.png
│   ├── paisaje.png
│   └── retrato.png
└── video/
    └── demo.mp4
```

Al abrir la galería, **no se ve ninguna de las tres fotos como corresponde** y el video no aparece.

## 🛠️ Proceso esperado

1. Abrí la página en el navegador y encontrá **tres errores** en las imágenes. Para cada uno, anotá qué pasa y cómo se
   corrige.
2. Corregí los tres errores y recargá hasta que se vean las tres fotos.
3. En la sección «Video», hacé que el reproductor muestre el archivo `video/demo.mp4`, con **controles** y un texto
   para los navegadores que no admiten video.
4. En «Dónde trabajo», incrustá con `iframe` este mapa de OpenStreetMap (con un `title` que lo describa):
   `https://www.openstreetmap.org/export/embed.html?bbox=-60.75%2C-33.0%2C-60.6%2C-32.9&layer=mapnik`
   (en HTML, el `&` de la dirección se escribe `&amp;`).

## ✅ Resultado esperado

- ☑️ Los tres errores identificados y corregidos; las tres fotos se ven.
- ☑️ Un video con controles que se reproduce.
- ☑️ Un mapa incrustado con `title`.
- ☑️ Todas las imágenes con `alt`.

## 🚧 Restricciones

- 🚫 No cambies el nombre de las carpetas ni de los archivos: corregí el código.
- 🚫 No dejes ninguna imagen sin `alt` ni uses «imagen» como único texto alternativo.
- 🚫 No agregues CSS.

## 🎓 Resultados de aprendizaje

- RA-6: Incorporar imágenes, video y contenido incrustado con la etiqueta iframe.

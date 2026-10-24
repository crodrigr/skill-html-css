# 📘 Ejemplo 08 — Preparación previa de la página

> 🎓 **Resultados de aprendizaje:** RA-5
>
> 📐 **Cómo se midió.** Con Chrome, con la ventana del ancho indicado y sin barra de desplazamiento vertical (una barra de unos 15px resta ancho). Los decimales se redondean a dos cifras.

## 🧱 Situación inicial

Antes de escribir consultas de medios, Lucía prepara su página para que no se desborde. En `preparacion.html` compara una sección **sin preparar** y una **preparada**, que tienen una caja de ancho `100%` con relleno y borde, y una imagen de `1200px` de ancho.

## 💻 Código

El contenido de `preparacion.html` (dentro de `<main>`):

```html
<h2>Sin preparar</h2>
<section class="sin-preparar">
  <div class="caja">Ancho 100%, relleno 20px y borde 5px</div>
  <img src="imagenes/portada.png" alt="Portada del sitio de Lucía: franja de 1200 por 300 píxeles">
</section>

<h2>Preparado</h2>
<section class="preparado">
  <div class="caja">Ancho 100%, relleno 20px y borde 5px</div>
  <img src="imagenes/portada.png" alt="Portada del sitio de Lucía: franja de 1200 por 300 píxeles">
</section>
```

La hoja `css/preparacion.css`:

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

.caja {
  width: 100%;
  padding: 20px;
  border: 5px solid #111827;
  background-color: #dbeafe;
}

/* Preparación 1: el ancho incluye el relleno y el borde */
.preparado,
.preparado * {
  box-sizing: border-box;
}

/* Preparación 2: la imagen nunca pasa del ancho de su contenedor y conserva su proporción */
.preparado img {
  max-width: 100%;
  height: auto;
}
```

## 🔍 Análisis paso a paso

1. **Preparación 1 — la ventana de visualización.** Es la etiqueta del Ejemplo 07 en el `<head>`. Sin ella, en un teléfono nada de lo que sigue se comporta como se espera.
2. **Preparación 2 — el ancho que incluye el relleno y el borde.** Por defecto (`box-sizing: content-box`), `width` mide **solo el contenido**: la caja `.caja` pide `width: 100%`, pero además tiene `20px` de relleno y `5px` de borde por lado, así que mide `100% + 50px`: `550px` en una ventana de `500px`. Se sale por `50px`.
3. **`box-sizing: border-box`** hace que `width` incluya el relleno y el borde. En `.preparado`, la misma caja mide exactamente `500px` en una ventana de `500px`. MDN lo ilustra con una caja de `350px` y un borde de `10px`: `370px` en `content-box` y `350px` en `border-box`.
4. **Preparación 3 — imágenes flexibles.** La imagen mide `1200px` de ancho. Sin preparar, **sobresale** de cualquier ventana más angosta y hace que la página mida `1200px` (`scrollWidth` `1200` aun en una ventana de `500px`).
5. **`max-width: 100%` y `height: auto`.** La regla `img { max-width: 100%; height: auto; }` impide que la imagen pase del ancho de su contenedor y mantiene su proporción: en `500px` mide `500 × 125`; en `800px`, `800 × 200`; y en `1200px` conserva su tamaño natural (`1200 × 300`).
6. **Para todas las páginas.** Desde el siguiente ejemplo, todas las hojas empiezan con `* { box-sizing: border-box; }`, que aplica la preparación 2 a **todos** los elementos.
7. **Comprobación.** Si ocultás la sección sin preparar, la página preparada mide exactamente `500px` en una ventana de `500px`: ya **no hay desplazamiento horizontal**.

## ✅ Resultado esperado

| Medida | Ventana de `500px` | Ventana de `800px` | Ventana de `1200px` |
|---|---|---|---|
| `.sin-preparar .caja`, ancho | `550px` | `850px` | `1250px` |
| `.preparado .caja`, ancho | `500px` | `800px` | `1200px` |
| `.sin-preparar img`, ancho | `1200px` | `1200px` | `1200px` |
| `.preparado img`, ancho | `500px` (alto `125px`) | `800px` (alto `200px`) | `1200px` (alto `300px`) |

- Con la sección sin preparar visible, la página mide `1200px` o más de ancho en cualquier ventana.
- Con solo la sección preparada, la página mide `500px` en una ventana de `500px`.

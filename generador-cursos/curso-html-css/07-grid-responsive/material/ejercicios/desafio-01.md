# 🔴 Desafío 01 — El portafolio adaptable de Mateo

> 🔴 **Nivel:** Desafío · 🎓 **Resultados de aprendizaje:** RA-2, RA-3, RA-6, RA-7 · 🗓️ **Sesión 2**

## 🧱 Estado inicial

Abrí [`desafio.html`](../recursos/portafolio-inicial/desafio.html) de la carpeta `portafolio-inicial` y su hoja vacía [`css/desafio.css`](../recursos/portafolio-inicial/css/desafio.css). La página de Mateo tiene un contenedor `.pagina` con una `.cabecera`, un `.menu`, un `.contenido` (con un título y una `.galeria` de cuatro fotos) y un `.pie`. El `<head>` ya incluye la etiqueta de la ventana de visualización. La paleta de Mateo es gris oscuro `#111827` y crema `#fef3c7`. **Sin estilos, con la ventana en `500px` la página mide `648px` de ancho** (las fotos miden `640px`). Probá en ventanas de `500px`, `800px` y `1200px`, sin barra de desplazamiento vertical.

## 🛠️ Proceso esperado

Escribí en `desafio.css` una hoja **ordenada y comentada** que cumpla todo lo siguiente.

1. **Base.** Tamaño base de `16px` en `html`, margen `0` y tipografía sin serifa en el cuerpo, el ancho que incluye relleno y borde en **todos** los elementos y las imágenes que nunca pasan del ancho de su contenedor.
2. **Colores.** `.cabecera` y `.pie` con fondo `#111827` y texto `#fef3c7`; `.menu` con fondo `#fef3c7`. Relleno de `1rem` en la cabecera, el menú, el contenido y el pie.
3. **Teléfono (móvil primero).** `.pagina` como cuadrícula de **una columna** con un hueco de `1rem`: los cuatro bloques se apilan.
4. **Tableta (de `600px` a `899px`).** Dos columnas iguales. Usá **una sola condición** con `and`.
5. **Computador (desde `900px`).** Dos columnas: una de `220px` para el menú y otra que ocupe el resto.
6. **Cabecera y pie.** Desde `600px`, deben abarcar **todas** las columnas, sea cual sea su cantidad.
7. **Galería.** Una cuadrícula que muestre **tantas columnas de al menos `250px` como quepan**, con un hueco de `1rem`, **sin consultas de medios**.
8. **Reglas claras.** Hoja ordenada por temas, con un comentario antes de cada bloque, sin reglas repetidas y sin `!important`.

## ✅ Resultado esperado

- ☑️ Una hoja con todas las reglas de la lista, ordenada y comentada.
- ☑️ El HTML sin cambios.
- ☑️ La hoja pasa la revisión de estructura sin errores.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni sus clases.
- 🚫 No uses `!important`, ni `style`, ni un bloque `<style>`.
- 🚫 Los puntos de ruptura son `600px` y `900px`; no inventes otros.
- 🚫 Sin Flexbox, `clamp()`, `min()` ni `max()`.

## 🎓 Resultados de aprendizaje

- RA-2: Definir columnas con `repeat()` y `minmax()`.
- RA-3: Huecos y elementos que abarcan varias pistas.
- RA-6: Estrategia móvil primero y cuadrícula que se acomoda sola.
- RA-7: Consultas de medios con `min-width`, `max-width` y `and`.

## 🧪 Casos de prueba

| # | Ventana | Comprobación | Resultado esperado |
|---|---|---|---|
| 1 | `500px` | `.pagina`, columnas | `500px` (una columna) |
| 2 | `500px` | `.contenido`, ancho; `.galeria`, columnas | `500px`; `468px` |
| 3 | `500px` | Foto: ancho y alto | `468px` y `293px` (conserva la proporción) |
| 4 | `500px` | Página (`scrollWidth`) | `500px` (sin desplazamiento horizontal) |
| 5 | `599px` | `.pagina`, columnas | `599px` (todavía una columna) |
| 6 | `600px` | `.pagina`, columnas; `.cabecera`, ancho | `292px 292px`; `600px` |
| 7 | `800px` | `.pagina`, columnas | `392px 392px` |
| 8 | `800px` | `.menu` y `.contenido`, ancho; `.galeria`, columnas | `392px` y `392px`; `360px` |
| 9 | `899px` | `.pagina`, columnas | `441.5px 441.5px` |
| 10 | `900px` | `.pagina`, columnas | `220px 664px` |
| 11 | `1200px` | `.pagina`, columnas; `.contenido`, ancho | `220px 964px`; `964px` |
| 12 | `1200px` | `.galeria`, columnas; foto, alto | `300px 300px 300px`; `188px` |
| 13 | `1200px` | `.cabecera` y `.pie`, ancho | `1200px` |
| 14 | La hoja | Sin `!important`, sin reglas repetidas, con comentarios, una condición con `and`; pasa `validar_css.py` | — |

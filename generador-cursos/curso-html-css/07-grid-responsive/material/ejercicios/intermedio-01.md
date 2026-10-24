# 🟡 Intermedio 01 — Prepará la página

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-4, RA-5 · 🗓️ **Sesión 2**

## 🧱 Estado inicial

Abrí [`intermedio-01.html`](../recursos/portafolio-inicial/intermedio-01.html) y su hoja [`css/intermedio-01.css`](../recursos/portafolio-inicial/css/intermedio-01.css), de la carpeta `portafolio-inicial`. El `<head>` ya incluye la etiqueta de la ventana de visualización. La hoja da un `width: 960px` al `.contenedor` (con `20px` de relleno y `4px` de borde) y un `width: 100%` a la `.tarjeta` (con `16px` de relleno y `2px` de borde). La página tiene además una imagen de `1200px` de ancho. **Con la ventana en `500px`, la página mide `1224px` de ancho** y tiene desplazamiento horizontal.

## 🛠️ Proceso esperado

Escribí en `intermedio-01.css` los cambios necesarios para que la página **no se desborde**:

1. Que el ancho de **todos** los elementos incluya el relleno y el borde.
2. Que `.contenedor` use el ancho disponible, sin ancho fijo, con un máximo de `960px`.
3. Que las imágenes nunca pasen del ancho de su contenedor y no se deformen.

Comprobá cada medida en tres ventanas (sin barra de desplazamiento vertical).

| Ventana | `.contenedor` | `.tarjeta` | Imagen | Página (`scrollWidth`) |
|---|---|---|---|---|
| `500px` | `500px` | `452px` | `452 × 113` | `500px` |
| `800px` | `800px` | `752px` | `752 × 188` | `800px` |
| `1200px` | `960px` | `912px` | `912 × 228` | `1200px` |

**Parte B.** Respondé:

1. ¿Por qué la tarjeta mide `452px` en una ventana de `500px` y no `500px`?
2. ¿Qué etiqueta del `<head>` hace falta para que esto funcione en un teléfono real y por qué no se puede comprobar su efecto en un navegador de escritorio?

## ✅ Resultado esperado

- ☑️ La hoja con los tres cambios y las medidas de la tabla.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 No uses consultas de medios en este ejercicio.
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-4: Explicar el diseño adaptable y la ventana de visualización.
- RA-5: Preparar una página: ancho con `border-box` e imágenes flexibles.

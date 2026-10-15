# 🟡 Intermedio 01 — Un informe con texto, datos y decoraciones

> 🟡 **Nivel:** Intermedio · 🕐 **Sesión 1** · 🎓 **Resultados de aprendizaje:** RA-2, RA-3, RA-4, RA-5

## 🧱 Estado inicial

Abrí [`intermedio-01.html`](../recursos/portafolio-inicial/intermedio-01.html) y su hoja vacía [`css/intermedio-01.css`](../recursos/portafolio-inicial/css/intermedio-01.css), de la carpeta
`portafolio-inicial`. Es el informe mensual de Mateo: un aviso, un resumen con un precio anterior y uno nuevo, una tabla de sesiones, una lista de pendientes y un enlace a la galería.
La paleta de Mateo es gris oscuro `#111827`, verde `#16a34a` y crema `#fef3c7`; además usa el rojo `#dc2626` para lo que ya no vale.

## 🛠️ Proceso esperado

Escribí una hoja **ordenada y comentada** que cumpla todo lo siguiente.

1. **Base.** Texto sin serifa con alternativas, altura de línea `1.6` y color gris oscuro. El `h1` con serifa con alternativas y una sombra verde de `2px 2px 4px`.
2. **Aviso.** `.aviso` en mayúsculas, con las letras separadas `2px` y en negrita.
3. **Precios.** `.antes` tachado con la línea roja; `.nuevo` en negrita y verde.
4. **Menú y enlaces.** Los enlaces del `nav` sin subrayado, pero **con subrayado al pasar el cursor**. El enlace `.volver` con un subrayado **ondulado y verde**.
5. **Tabla.** Bordes unidos de `1px` continuos grises, relleno de `8px` y `12px`, y las cantidades (`.cantidad`) a la derecha.
6. **Lista.** `.pendientes` con viñeta cuadrada.

**Parte B.** Cuando le quitaste el subrayado a los enlaces del menú, ¿qué otra señal dejaste (o dejarías) para que se reconozcan como enlaces, y por qué importa?

## ✅ Resultado esperado

- ☑️ Una hoja con todas las reglas de la lista, ordenada y comentada.
- ☑️ El HTML sin cambios.
- ☑️ Una respuesta de dos o tres frases a la Parte B.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases.
- 🚫 No uses `!important`, ni `style`, ni un bloque `<style>`.
- 🚫 Cada color se escribe como valor hexadecimal.
- 🚫 No agregues propiedades que no se vieron en las Clases 03 a 05.

## 🎓 Resultados de aprendizaje

- RA-2: Aplicar tipografías en CSS.
- RA-3: Alinear y espaciar el texto.
- RA-4: Aplicar decoraciones y sombras al texto.
- RA-5: Dar estilo a tablas y listas.

## 🧪 Casos de prueba

| # | Comprobación | Resultado esperado |
|---|---|---|
| 1 | `body` | Familia `Arial, Helvetica, sans-serif`, altura de línea `25.6px` |
| 2 | `h1` | Familia `Georgia, "Times New Roman", serif` y sombra `rgb(22, 163, 74) 2px 2px 4px` |
| 3 | `.aviso` | `uppercase`, letras separadas `2px` y peso `700` |
| 4 | `.antes` | Línea `line-through` de color `rgb(220, 38, 38)` |
| 5 | `.nuevo` | Peso `700` y color `rgb(22, 163, 74)` |
| 6 | `nav a` (dos enlaces) | Sin subrayado (`none`); con el cursor encima (estado simulado), `underline` |
| 7 | `.volver` | `underline`, `wavy` y color `rgb(22, 163, 74)` |
| 8 | `table` y `td` | `collapse`; borde de `1px`; relleno izquierdo `12px` |
| 9 | `.cantidad` (cuatro celdas) | Texto a la derecha |
| 10 | `.pendientes` | `square` |
| 11 | La hoja | Sin `!important`, con comentarios y sin errores en `validar_css.py` |

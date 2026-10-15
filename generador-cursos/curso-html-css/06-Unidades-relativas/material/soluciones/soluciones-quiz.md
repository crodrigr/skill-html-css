# 🔑 Soluciones — Quiz 01 de la Clase 06 (material docente)

No compartir este archivo con los estudiantes. Las respuestas con código se comprobaron en Chrome.

| Ítem | Tipo | Respuesta correcta | RA |
|---|---|---|---|
| 1 | Selección múltiple | **C** | RA-1 |
| 2 | Selección múltiple | **C** | RA-2 |
| 3 | Identificación de resultado | **C** | RA-3 |
| 4 | Selección múltiple | **B** | RA-4 |
| 5 | Identificación de resultado | **C** | RA-5 |
| 6 | Selección múltiple | **C** | RA-5 |
| 7 | Corrección de errores | Ver abajo | RA-1, RA-6 |
| 8 | Problema breve | Ver abajo | RA-7 |

## Justificaciones

**1. C.** `rem` se calcula a partir del tamaño de letra de la raíz. `cm`, `pt` e `in` son unidades absolutas heredadas de la impresión.

**2. C.** Con una relación de `2`, cada píxel de CSS ocupa `2 × 2` puntos físicos: una caja de `100px` de ancho usa `200` puntos de ancho (y `200` de alto). En CSS sigue midiendo `100px`; la comprobación con una escala de `2` dio `offsetWidth`
igual al valor de CSS.

**3. C.** `1pc` son `16px` (12 puntos): `3pc` son `48px` (comprobado en Chrome con `6pc` = `96px`).

**4. B.** El relleno en porcentaje se calcula sobre el **ancho** del contenedor, también arriba y abajo: `10%` de `400px` son `40px` (comprobado: `40px`). El alto del contenedor (`100px`) no interviene.

**5. C.** Cada nivel multiplica sobre el anterior: `16 × 1.5 = 24`, `24 × 1.5 = 36` y `36 × 1.5 = 54` (comprobado: `54px`).

**6. C.** `rem` se mide siempre contra la raíz, así que no se acumula. `em` se acumula en `font-size`; el `%` también, porque se calcula sobre la letra del padre; `ch` depende de la tipografía, no de la anidación.

**7. Dos errores** (en cualquier orden):

1. **`30 ch` tiene un espacio.** Entre el número y la unidad no va un espacio: se escribe `30ch`. Con el espacio, el navegador ignora la declaración y el campo ocupa todo el ancho (comprobado: `764px`, el ancho de la página).
2. **`200` no tiene unidad.** Un número distinto de cero necesita unidad: `200px`. Sin ella, el navegador ignora la declaración (comprobado: alto automático de `18px`).

Hoja corregida:

```css
.campo {
  width: 30ch;
}

.bloque {
  height: 200px;
}
```

**8. Respuesta de ejemplo** (se acepta otra unidad con una justificación válida):

| Situación | Unidad | Justificación |
|---|---|---|
| (a) Tamaño del texto principal | `rem` | Respeta el tamaño de letra que cada persona eligió en su navegador y no se acumula |
| (b) Borde fino | `px` | Debe ser fijo: `1px` es `1px` |
| (c) Ancho máximo de lectura | `ch` | Se mide en caracteres: unos `65` por línea se leen cómodos |
| (d) Alto de tres líneas | `lh` | Sigue a la altura de línea y muestra siempre tres líneas |
| (e) Mitad de la altura de la ventana | `vh` | `50vh` es el `50%` del alto de la ventana |

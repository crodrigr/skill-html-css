# 🔑 Soluciones — Quiz 01 de la Clase 07 (material docente)

No compartir este archivo con los estudiantes. Las respuestas con medidas se comprobaron en Chrome con la ventana indicada.

| Ítem | Tipo | Respuesta correcta | RA | Sesión |
|---|---|---|---|---|
| 1 | Selección múltiple | **C** | RA-1 | 1 |
| 2 | Identificación de resultado | **C** | RA-2 | 1 |
| 3 | Selección múltiple | **B** | RA-2 | 1 |
| 4 | Identificación de resultado | **B** | RA-3 | 1 |
| 5 | Selección múltiple | **B** | RA-3 | 1 |
| 6 | Selección múltiple | **B** | RA-4 | 2 |
| 7 | Corrección de errores | Ver abajo | RA-5 | 2 |
| 8 | Selección múltiple | **C** | RA-6 | 2 |
| 9 | Identificación de resultado | **B** | RA-7 | 2 |
| 10 | Problema breve | Ver abajo | RA-7 | 2 |

## Justificaciones

**1. C.** La celda es el cruce de una fila y una columna. Una línea es una división, una pista es una fila o una columna entera y el contenedor es el elemento con `display: grid`.

**2. C.** Primero se descuenta la columna fija (`200px`); `fr` reparte los `1000px` que sobran entre dos columnas: `500px` cada una (comprobado: `200px 500px 500px`).

**3. B.** `minmax(200px, 1fr)` impide que la columna baje de `200px`. Tres columnas suman `600px`, más que la ventana de `500px`: la cuadrícula se sale (comprobado: `200px 200px 200px` y `scrollWidth` de `600px`).

**4. B.** Los dos huecos suman `32px`; los `1168px` restantes se reparten en tres: `389.33px` (comprobado). `400px` ignora el hueco; `384px` es el ancho de un elemento con margen de `8px`, no con `gap`.

**5. B.** `span 2` indica cuántas pistas ocupa el elemento. `grid-column: 2` lo colocaría en la columna 2, solo una; `grid-columns` y `column-span` no existen en Grid.

**6. B.** Según MDN, sin la etiqueta un navegador móvil dibuja la página en una ventana virtual más ancha (por ejemplo, `980px`) y la reduce; con `width=device-width` usa el ancho real del dispositivo. No afecta a los navegadores de escritorio, no cambia columnas ni vuelve flexibles las imágenes.

**7. Corrección de errores.** Dos errores:

1. La caja pide `width: 100%` **y** suma relleno y borde (por defecto el ancho solo mide el contenido): mide `100% + 50px` y se sale (comprobado: `550px` en una ventana de `500px`).
2. La imagen tiene un ancho fijo de `1200px`, que no se adapta a la ventana.

```css
* {
  box-sizing: border-box;
}

.caja {
  width: 100%;
  padding: 20px;
  border: 5px solid #111827;
}

img {
  max-width: 100%;
  height: auto;
}
```

Se acepta cualquier versión que haga que el ancho incluya relleno y borde (`box-sizing: border-box` en `.caja` o en `*`) y que la imagen sea flexible (`max-width: 100%`, o `width: 100%` con `height: auto`). Con eso, la página mide `500px` en una ventana de `500px`.

**8. C.** `auto-fit` con `minmax()` solo cambia **cuántas columnas** caben (2, 3 o 5 según el ancho, comprobado en el Ejemplo 10). Mover el menú, cambiar el orden o ocultar un bloque son **otra disposición** y piden una consulta de medios.

**9. B.** `min-width: 600px` se cumple **desde** `600px`, inclusive (comprobado: en `600px` el título pasó de `24px` a `32px`). `2rem` con base de `16px` son `32px`.

**10. Problema breve.** En una ventana de `1200px` se cumplen **las dos** consultas (`900px` y `600px`). Las dos tienen la misma especificidad y gana la que aparece **después**: la de `600px`, con dos columnas. (Comprobado con un caso equivalente: en `1200px` quedó con dos columnas de `588px`.) Se corrige escribiéndolas de **menor a mayor**:

```css
.g { display: grid; grid-template-columns: 1fr; }

@media (min-width: 600px) {
  .g { grid-template-columns: repeat(2, 1fr); }
}

@media (min-width: 900px) {
  .g { grid-template-columns: repeat(3, 1fr); }
}
```

Con ese orden, en `1200px` gana la de `900px` (tres columnas). También se acepta cerrar el rango de la consulta de `600px` con `and (max-width: 899px)`.

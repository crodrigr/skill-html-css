# 🔑 Soluciones — Quiz 01 de la Clase 02 (material docente)

No compartir este archivo con los estudiantes.

| Ítem | Tipo | Respuesta correcta | RA |
|---|---|---|---|
| 1 | Selección múltiple | **A** | RA-1 |
| 2 | Selección múltiple | **C** | RA-2 |
| 3 | Identificación de resultado | **A** | RA-2 |
| 4 | Selección múltiple | **B** | RA-3 |
| 5 | Corrección de errores | Ver abajo | RA-4 |
| 6 | Selección múltiple | **B** | RA-5 |
| 7 | Identificación de resultado | **A** | RA-6 |
| 8 | Problema breve | Ver abajo | RA-6 |

## Justificaciones

**1. A.** `<hr>` marca un cambio de tema y se muestra como una línea horizontal. Un título de segundo nivel es `<h2>`, los
elementos de una lista van en `<li>` y una cita extensa es `<blockquote>`.

**2. C.** Una celda de encabezado es `<th>`. `<td>` es una celda de datos, `<tr>` una fila y `<caption>` el título de la tabla.

**3. A.** `colspan="2"` hace que la primera celda ocupe el ancho de las dos columnas; la segunda fila tiene dos celdas, una por
columna.

**4. B.** Una sublista se escribe **dentro de un `<li>`** de la lista exterior. No puede ser hijo directo de otro `<ul>` o `<ol>`.

**5. Dos errores** (en cualquier orden):

1. **`<cite>` para el nombre de una persona.** `<cite>` es para títulos de obras: «Marta Gómez» va como texto común
   (`<p>— Marta Gómez</p>`).
2. **Comillas escritas a mano en el `<q>`.** El navegador agrega las comillas: `<q>explica todo con paciencia</q>`.

**6. B.** Un formulario es un conjunto de campos con los que la persona ingresa información en la página.

**7. A.** `?nombre=Ana&edad=30`. Se envía cada campo con `name` y su valor. El botón `submit` no tiene `name`, así que no
viaja (comprobado en Chrome).

**8. Respuesta esperada:**

| Dato | `type` |
|---|---|
| (a) correo | `email` |
| (b) edad | `number` |
| (c) novedades (sí o no) | `checkbox` |
| (d) una opción entre mañana y tarde | `radio` (con el mismo `name`) |
| (e) clave | `password` |

Con `method="get"` los datos quedan **visibles en la dirección**, incluida la clave: `password` solo la oculta en pantalla,
no la protege.

# 🔑 Soluciones — Quiz 01 de la Clase 03 (material docente)

No compartir este archivo con los estudiantes.

| Ítem | Tipo | Respuesta correcta | RA |
|---|---|---|---|
| 1 | Selección múltiple | **B** | RA-1 |
| 2 | Selección múltiple | **C** | RA-2 |
| 3 | Identificación de resultado | **C** | RA-3 |
| 4 | Selección múltiple | **C** | RA-4 |
| 5 | Identificación de resultado | **C** | RA-5 |
| 6 | Corrección de errores | Ver abajo | RA-6 |
| 7 | Selección múltiple | **D** | RA-7 |
| 8 | Problema breve | Ver abajo | RA-8 |

## Justificaciones

**1. B.** CSS significa *Cascading Style Sheets* (hojas de estilo en cascada) y define el aspecto de una página, separándolo del
contenido, que es el HTML.

**2. C.** Con un archivo externo enlazado desde las cinco páginas, un cambio llega a todas. El estilo en línea y el bloque copiado
obligan a repetir los estilos, y MDN considera una mala práctica el estilo en línea.

**3. C.** En `.destacado { color: green; }`, `.destacado` es el selector, `color` es la propiedad y `green` es el valor; `{ }` delimita el
bloque de declaraciones.

**4. C.** Lo que se cambia en las herramientas es una prueba en pantalla: el archivo en disco no se modifica. Para conservar el cambio,
hay que copiarlo al archivo y guardarlo.

**5. C.** Las tres reglas se aplican, pero el identificador (100) es más específico que la clase (10) y que el elemento (1): el texto se
ve azul (`rgb(0, 0, 255)`, comprobado en Chrome).

**6. Dos errores** (en cualquier orden):

1. **El nombre de la variable no empieza con dos guiones.** `color-principal: #2563eb;` no define una variable: hay que escribir
   `--color-principal: #2563eb;`.
2. **El nombre usado en `var()` no coincide.** Los nombres distinguen mayúsculas: `--Color-principal` es otra variable. Hay que
   escribir `var(--color-principal)`.

Hoja corregida:

```css
:root {
  --color-principal: #2563eb;
}

a {
  color: var(--color-principal);
}
```

**7. D.** `rgb(255 0 0 / 0.5)` es el mismo rojo, pero con un 50% de transparencia (se calcula como `rgba(255, 0, 0, 0.5)`). Las otras tres
formas dan `rgb(255, 0, 0)` (comprobado en Chrome).

**8. Respuesta esperada:** un **color con canal alfa en `background-color`**, por ejemplo `background-color: rgb(30 58 138 / 0.5);`.
`opacity` atenúa el elemento completo, incluido el texto; el canal alfa afecta solo al fondo y deja el texto blanco y nítido.

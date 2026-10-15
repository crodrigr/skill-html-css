# 🔑 Soluciones — Quiz 01 de la Clase 04 (material docente)

No compartir este archivo con los estudiantes.

| Ítem | Tipo | Respuesta correcta | RA |
|---|---|---|---|
| 1 | Selección múltiple | **B** | RA-1 |
| 2 | Selección múltiple | **C** | RA-2 |
| 3 | Selección múltiple | **A** | RA-3 |
| 4 | Identificación de resultado | **B** | RA-4 |
| 5 | Selección múltiple | **B** | RA-5 |
| 6 | Identificación de resultado | **B** | RA-6 |
| 7 | Corrección de errores | Ver abajo | RA-6 |
| 8 | Problema breve | Ver abajo | RA-7 |

## Justificaciones

**1. B.** Un selector que empieza con punto es un selector de **clase**: elige los elementos con `class="destacado"`. El de identificador empieza con `#` y el de
elemento no lleva prefijo.

**2. C.** `$=` significa «termina en»: `a[href$=".pdf"]` elige los enlaces cuyo `href` termina en `.pdf`. La coincidencia exacta es `=`, «empieza con» es `^=` y «contiene» es `*=`.

**3. A.** `tarjeta__boton--grande`: el elemento se une al bloque con dos guiones bajos y el modificador se une al elemento con dos guiones (variante
habitual de la comunidad). `tarjeta__boton__grande` sería un elemento de un elemento, que BEM no admite. En la convención oficial de bem.info, el mismo
modificador se escribiría `tarjeta__boton_grande`.

**4. B.** `section > p` elige solo los **hijos directos**: los párrafos «Uno» y «Dos». «Tres» está dentro del `div`: es descendiente, pero no hijo directo
(comprobado en Chrome: 2 elementos).

**5. B.** `:not()` excluye: elige los enlaces cuyo `href` **no** empieza con `https`. También incluye, por esa misma razón, a un `<a>` sin `href`, que no cumple la condición; la opción D
describe solo ese caso y no el selector completo.

**6. B.** `:nth-child(even)` elige las posiciones pares, contando desde 1: la segunda y la cuarta, «Dos» y «Cuatro» (comprobado en Chrome).

**7. Dos errores** (en cualquier orden):

1. **El orden de los estados.** `a:hover` está **antes** de `a:visited`; como valen lo mismo, la regla posterior gana y un enlace visitado se queda violeta aun con el
   cursor encima. El orden recomendado es normal, visitado, cursor y foco: `a:visited` primero y `a:hover` después.
2. **`li:nth-child(0)` no elige nada.** Las posiciones se cuentan desde **1**. Para elegir el primero hay que escribir `li:nth-child(1)` (o `li:first-child`).

Hoja corregida:

```css
a:visited {
  color: purple;
}

a:hover {
  color: red;
}

li:first-child {
  color: green;
}
```

**8. Respuesta esperada.** El selector largo `main article.tarjeta h3.tarjeta__titulo` vale `0-2-3` (dos clases y tres etiquetas) y `.tarjeta__titulo` vale solo `0-1-0`, así que la primera gana aunque
venga antes (comprobado en Chrome: el título se ve azul). Se resuelve **simplificando el selector**: dejar una sola regla `.tarjeta__titulo { color: red; }` y borrar la larga, con lo
que no hace falta `!important`.

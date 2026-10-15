# 🔑 Soluciones — Quizzes de la Clase 05 (material docente)

No compartir este archivo con los estudiantes. Las respuestas con código se comprobaron en Chrome.

## Quiz 01 (sesión 1)

| Ítem | Tipo | Respuesta correcta | RA |
|---|---|---|---|
| 1 | Selección múltiple | **C** | RA-1 |
| 2 | Selección múltiple | **B** | RA-2 |
| 3 | Identificación de resultado | **C** | RA-2 |
| 4 | Selección múltiple | **B** | RA-3 |
| 5 | Identificación de resultado | **A** | RA-4 |
| 6 | Selección múltiple | **B** | RA-5 |
| 7 | Corrección de errores | Ver abajo | RA-5 |
| 8 | Problema breve | Ver abajo | RA-2, RA-3 |

### Justificaciones del quiz 01

**1. C.** En una tipografía de ancho fijo, todas las letras miden lo mismo (por eso se usa para código). A describe a las letras con serifa; B, a las sin serifa.

**2. B.** Las alternativas se separan con comas, los nombres con espacios van entre comillas y la lista termina con la familia genérica. A usa punto y coma. C es válida pero pone `serif` primero: como `serif` siempre está
disponible, el navegador nunca llegaría a `Georgia` ni a `Times New Roman`. D encierra toda la lista entre comillas y la convierte en **un solo nombre** de tipografía, que no existe.

**3. C.** `.b` pide `1.5em` y `em` se mide contra el tamaño del padre: `1.5 × 20px = 30px` (comprobado en Chrome: `30px`). Con `1.5rem` habría dado `24px`.

**4. B.** `text-indent` sangra **solo la primera línea** del bloque; `2rem` son `32px`. Las demás líneas no se mueven.

**5. A.** `underline` es la línea (debajo del texto), `wavy` el estilo (ondulado) y `#dc2626` el color (rojo). Comprobado: línea `underline`, estilo `wavy`.

**6. B.** `border-collapse: collapse` une los bordes de las celdas vecinas en una sola línea. `border-spacing: 0` en las celdas no tiene efecto (se aplica en la tabla y con bordes separados). `single` no es un valor válido. `caption-side` mueve el título de la tabla.

**7. Dos errores** (en cualquier orden):

1. **`list-style-type: none` deja la sangría.** El menú sin viñetas sigue con los `40px` de relleno izquierdo que trae la lista: para que quede pegado al borde, hay que agregar `padding-left: 0`. (El navegador da a `ul` y `ol` un relleno izquierdo de 40px; comprobado.)
2. **`list-style-position: adentro` no es un valor válido.** Los valores son `inside` (dentro) y `outside` (fuera); el navegador ignora el valor inválido y deja `outside` (comprobado).

Hoja corregida:

```css
.menu {
  list-style-type: none;
  padding-left: 0;
}

.pasos {
  list-style-type: upper-roman;
  list-style-position: inside;
}
```

**8. Respuesta de ejemplo** (se aceptan al menos tres cambios con su motivo):

```css
.parrafo {
  font-size: 1rem;
  line-height: 1.6;
  letter-spacing: normal;
  text-align: left;
}
```

- `font-size: 1rem`: `11px` es muy chico y no respeta el tamaño que cada persona eligió en su navegador.
- `line-height: 1.6`: con `1` las líneas se tocan; para el texto principal se recomienda al menos `1.5`.
- `letter-spacing: normal` (o un valor chico): `3px` entre letras rompe la forma de las palabras.
- `text-align: left`: en una columna de `200px`, el justificado deja grandes huecos entre palabras.

## Quiz 02 (sesión 2)

| Ítem | Tipo | Respuesta correcta | RA |
|---|---|---|---|
| 1 | Selección múltiple | **B** | RA-6 |
| 2 | Selección múltiple | **A** | RA-6 |
| 3 | Selección múltiple | **A** | RA-6 |
| 4 | Identificación de resultado | **C** | RA-7 |
| 5 | Selección múltiple | **C** | RA-7 |
| 6 | Identificación de resultado | **B** | RA-8 |
| 7 | Corrección de errores | Ver abajo | RA-8 |
| 8 | Problema breve | Ver abajo | RA-7 |

### Justificaciones del quiz 02

**1. B.** `border: 4px red;` no indica el estilo; el estilo inicial es `none` y el borde no se dibuja (comprobado: estilo `none` y grosor `0px`).

**2. A.** `border-bottom` fija grosor, estilo y color del lado de abajo (comprobado: abajo `solid`, arriba `none`). C da `3px` de grosor abajo pero sin estilo, por lo que no se ve (comprobado: `0px` y `none`); B y D no son sintaxis válida.

**3. A.** Con cuatro valores, el orden es arriba-izquierda, arriba-derecha, abajo-derecha y abajo-izquierda: `10px`, `0`, `10px`, `0` redondea arriba a la izquierda y abajo a la derecha (comprobado: `10px`, `0px`, `10px`, `0px`).

**4. C.** `300 + 20 + 20 + 5 + 5 = 350` (comprobado: `offsetWidth` `350`). El margen no se incluye; con él serían `370`.

**5. C.** `auto` recorta y muestra las barras solo si hace falta. `hidden` recorta sin barras, `scroll` muestra barras siempre y `visible` deja sobresalir el contenido.

**6. B.** Con tres valores: arriba `5px`; izquierda y derecha `10px`; abajo `15px`. El izquierdo vale `10px` (comprobado).

**7. Dos errores** (en cualquier orden):

1. **`padding: -10px`.** Un relleno no admite valores negativos: la declaración es inválida y el navegador la ignora (relleno `0`; comprobado).
2. **`margin` con cinco valores.** La notación admite de uno a cuatro: con cinco, la declaración es inválida y se ignora (márgenes `0`; comprobado).

Regla corregida:

```css
.tarjeta {
  padding: 10px;
  margin: 10px 20px 30px 40px;
}
```

**8. Respuesta.**

- Con el cálculo por defecto: `width: 336px` (`400 − 30 − 30 − 2 − 2`; comprobado: `offsetWidth` `400`).
- Con `box-sizing: border-box`: `width: 400px` (comprobado: `offsetWidth` `400`).
- Se prefiere `border-box` porque el ancho que escribís es el que la caja ocupa de borde a borde: si después cambiás el relleno o el borde, la caja no se agranda y no hay que volver a restar.

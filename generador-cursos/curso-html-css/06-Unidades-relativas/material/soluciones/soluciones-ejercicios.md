# 🔑 Soluciones — Ejercicios de la Clase 06 (material docente)

No compartir este archivo con los estudiantes. Cada hoja se probó en Chrome sobre la página de partida del ejercicio: pasa `validar_css.py` y cumple los valores calculados de su tabla o de sus casos de prueba, con la ventana en
`1000 × 600` cuando el ejercicio lo pide. Los valores que dependen de la tipografía (`ch`) se comparan con la medida del «0» y no con un número fijo.

---

## 🟢 Básico 01 — Clasificá y convertí las unidades absolutas

**Parte A.**

| Valor | Tipo |
|---|---|
| `12pt`, `3cm`, `96px`, `2in` | Absoluta |
| `50%`, `2em`, `1.5rem`, `10vw`, `8ch` | Relativa |
| `0` | Sin unidad (vale en todas) |

**Parte B.** `1in` = `96px`; `2.54cm` = `96px`; `72pt` = `96px`; `3pc` = `48px`; `0.5in` = `48px`.

**Parte C.**

```css
/* Tamaño base y aspecto común */
html {
  font-size: 16px;
}

.caja {
  height: 24px;
  margin-bottom: 8px;
  background-color: #fef3c7;
}

/* Cuatro formas de escribir 192px (2 pulgadas) */
.pulgada {
  width: 2in;
}

.pica {
  width: 12pc;
}

.punto {
  width: 144pt;
}

.centimetro {
  width: 5.08cm;
}
```

Cada caja calcula `192px` (comprobado): `2in = 2 × 96`; `12pc = 12 × 16`; `144pt = 144 × 4/3`; `5.08cm = 2 × 2.54cm`.

**Parte D.** Una caja de `150px` de ancho ocupa `300` puntos físicos de ancho (`150 × 2`) y, si mide `100px` de alto, `200` puntos de alto.

---

## 🟢 Básico 02 — Porcentajes, `em` y `rem`

```css
/* Tamaño base */
html {
  font-size: 16px;
}

.marco {
  width: 600px;
  margin-bottom: 16px;
  background-color: #fef3c7;
}

/* Porcentajes: contra el ancho del marco (600px) y la letra del padre (16px) */
.mitad {
  width: 50%;
}

.letra {
  font-size: 125%;
}

.relleno {
  padding: 5%;
}

/* em: contra la letra del propio elemento (20px) */
.boton {
  font-size: 20px;
  width: 15em;
  padding: 0.5em;
}

/* rem: contra la raíz (16px) */
.titulo-rem {
  font-size: 1.5rem;
}

/* Tres niveles de 1.5em: 24px, 36px y 54px */
.nivel {
  font-size: 1.5em;
}
```

**Parte B.**

1. Porque el relleno en porcentaje se calcula sobre el **ancho** del contenedor (`600px`), también para arriba y abajo: `5%` de `600px` son `30px`. El alto del marco no interviene.
2. Porque `em` se acumula: cada nivel multiplica sobre el nivel anterior: `16 × 1.5 = 24`, `24 × 1.5 = 36` y `36 × 1.5 = 54`.
3. Fila 5: `.titulo-rem` pasaría a `1.5 × 20 = 30px`. Fila 6: los niveles pasarían a `30px`, `45px` y `67.5px`, porque la letra del primer nivel parte del tamaño de la raíz.

**Comprobación.** Valores calculados: `.mitad` `300px`; `.letra` `20px`; `.relleno` `30px`; `.boton` ancho `300px` y relleno `10px`; `.titulo-rem` `24px`; niveles `24px`, `36px` y `54px`.

---

## 🟡 Intermedio 01 — De `em` a `rem`

```css
/* Tamaño base */
html {
  font-size: 16px;
}

/* Con rem, los tres niveles miden lo mismo: no se acumula */
.nivel {
  font-size: 1.5rem;
}

/* El botón: la letra fija y el ancho y el relleno acompañan a la letra con em */
.boton {
  font-size: 18px;
  width: 12em;
  padding: 0.5em 1em;
}
```

**Pasos 1 y 4.** Con la regla original (`1.5em`), los tres niveles miden `24px`, `36px` y `54px`: cada uno multiplica sobre el anterior. Con `1.5rem` miden `24px` los tres. Con la raíz en `20px`, los niveles pasan a `30px`
los tres y el ancho del botón sigue en `216px`.

**Parte B.** El botón tiene `font-size: 18px` (fijo en `px`) y su ancho y su relleno están en `em`, es decir, **relativos a su propia letra**: como la letra no depende de la raíz, nada cambia. Los niveles, en `rem`, se miden
contra la raíz y por eso crecen con ella.

**Comprobación.** Con la raíz de `16px`: niveles `24px`; botón ancho `216px` (`12 × 18`) y relleno `9px` y `18px`.

---

## 🟡 Intermedio 02 — `ch`, `lh` y las unidades de ventana

```css
/* Tamaño base y altura de línea de la página */
html {
  font-size: 16px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.5;
}

.campo, .nota, .banda, .cuadrado {
  background-color: #fef3c7;
}

.medida {
  font-family: monospace;
}

.cero {
  display: inline-block;
}

/* Portada: el 60% del alto de la ventana */
.portada {
  min-height: 60vh;
}

/* Campo de 30 caracteres */
.campo {
  font-family: monospace;
  width: 30ch;
}

/* Nota: cinco líneas de alto */
.nota {
  height: 5lh;
  overflow: hidden;
}

/* Banda: el 20% del ancho de la ventana */
.banda {
  width: 20vw;
}

/* Cuadrado: el 30% del lado menor de la ventana, en los dos ejes */
.cuadrado {
  width: 30vmin;
  height: 30vmin;
}
```

**Parte B.** Con `600 × 1000`: `.portada` pasa a `600px` (`60vh` de `1000px`), `.banda` a `120px` (`20vw` de `600px`) y `.cuadrado` sigue en `180px`, porque se mide con `vmin` y el lado menor de la ventana sigue siendo `600px`.

**Comprobación (ventana `1000 × 600`).** `.portada` `360px`; `.campo` unos `289px` (30 veces el ancho del «0», `9.64px` en el equipo de prueba); `.nota` `120px` (5 × `24px`); `.banda` `200px`; `.cuadrado` `180px` de ancho y de alto.

---

## 🔴 Desafío 01 — La hoja de Mateo, con la unidad adecuada

```css
/* Tamaño base declarado */
html {
  font-size: 16px;
}

/* Texto: rem para el tamaño y una altura de línea sin unidad */
body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
}

/* Sección que ocupa la mitad de la ventana */
.portada {
  min-height: 50vh;
}

/* Contenedor flexible con un tope */
.contenedor {
  width: 80%;
  max-width: 40rem;
}

/* Ancho de lectura de 40 caracteres */
.resumen {
  max-width: 40ch;
}

.cero {
  display: inline-block;
}

/* Tarjeta: letra fija de 20px y relleno que acompaña a la letra */
.tarjeta {
  font-size: 20px;
  width: 20rem;
  padding: 1.5em;
  border: 1px solid #111827;
  background-color: #fef3c7;
}

/* Alto de tres líneas de texto */
.bloque {
  height: 3lh;
  overflow: hidden;
}

/* Cinta: la mitad del ancho y el 10% del alto de la ventana */
.cinta {
  width: 50vw;
  height: 10vh;
  background-color: #fef3c7;
}
```

**Notas.**

- `.contenedor` pide el `80%`, pero el tope de `40rem` (`640px`) gana: con la ventana de `1000px`, el `80%` pasaría de ese tope.
- `.resumen` con `max-width: 40ch` mide 40 veces el ancho del «0» de su misma tipografía (en el equipo de prueba, `355.9px` frente a `40 × 8.91px`).
- `.tarjeta` conserva su letra en `20px`, así que el relleno de `1.5em` son `30px` aunque cambie la raíz; el ancho en `rem` sí cambia (`20rem` = `400px` con la raíz de `20px`).
- `.bloque` con `3lh` mide unos `76.8px` (en Chrome, `76.78px`).

**Comprobación (11 casos de prueba, ventana `1000 × 600`).** `html` `16px`; `body` `16px` y `25.6px`; `.portada` `300px`; `.contenedor` `640px`; `.resumen` igual a 40 veces `.cero` (diferencia menor que `1px`); `.tarjeta` `20px`, `320px` y
relleno de `30px`; borde `1px solid rgb(17, 24, 39)`; `.bloque` `76.78px`; `.cinta` `500px` y `60px`; con la raíz en `20px`, `body` `20px`, `.tarjeta` de `400px` y relleno de `30px`.

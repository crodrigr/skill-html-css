# 📝 Quiz 01 — Tipografía y presentación de datos (sesión 1)

8 ítems. Sin respuestas (ver `material/soluciones/soluciones-quiz.md` para la clave, material
exclusivamente docente).

---

**1. [selección múltiple]** 🔘
¿Cuál de estas frases describe a una tipografía de **ancho fijo** (*monospace*)?

A. Los trazos de las letras terminan en pequeños remates.
B. Los trazos de las letras terminan lisos.
C. Todas las letras ocupan el mismo ancho.
D. Las letras son más anchas que altas.

_RA: RA-1_

---

**2. [selección múltiple]** 🔘
¿Cuál es la forma más segura de pedir una tipografía con serifa, con alternativas?

A. `font-family: Georgia; Times New Roman; serif;`
B. `font-family: Georgia, "Times New Roman", serif;`
C. `font-family: serif, Georgia, "Times New Roman";`
D. `font-family: "Georgia, Times New Roman, serif";`

_RA: RA-2_

---

**3. [identificación de resultado]** 🔍
Con este código, ¿cuántos píxeles mide el texto del párrafo `.b`?

```html
<div class="a">
  <p class="b">Texto</p>
</div>
```

```css
.a {
  font-size: 20px;
}

.b {
  font-size: 1.5em;
}
```

A. 16
B. 24
C. 30
D. 32

_RA: RA-2_

---

**4. [selección múltiple]** 🔘
Un párrafo de tres líneas tiene `text-indent: 2rem` y el tamaño base es de `16px`. ¿Qué se ve?

A. Las tres líneas se desplazan `32px` hacia la derecha.
B. Solo la primera línea se desplaza `32px` hacia la derecha.
C. Solo la última línea se desplaza `32px` hacia la derecha.
D. El párrafo queda centrado.

_RA: RA-3_

---

**5. [identificación de resultado]** 🔍
¿Qué se ve con esta regla?

```css
.x {
  text-decoration: underline wavy #dc2626;
}
```

A. Una línea ondulada roja debajo del texto.
B. El texto tachado con una línea ondulada roja.
C. Un subrayado continuo rojo.
D. Una línea ondulada, del color del texto, encima del texto.

_RA: RA-4_

---

**6. [selección múltiple]** 🔘
Una tabla con `th, td { border: 1px solid #2563eb; }` se ve con **dos líneas** entre las celdas. ¿Qué declaración las une en una sola?

A. `border-spacing: 0;` en las celdas.
B. `border-collapse: collapse;` en la tabla.
C. `border-style: single;` en la tabla.
D. `caption-side: bottom;` en la tabla.

_RA: RA-5_

---

**7. [corrección de errores]** ✏️
Silvia quiere un menú sin viñetas y pegado al borde izquierdo, y una lista de pasos con numeración romana **dentro** del texto. Su hoja tiene **dos errores**. Encontralos y escribí la hoja corregida.

```css
.menu {
  list-style-type: none;
}

.pasos {
  list-style-type: upper-roman;
  list-style-position: adentro;
}
```

_RA: RA-5_

---

**8. [problema breve]** 🧩
Este párrafo de una columna de `200px` se lee con dificultad. Escribí cómo lo corregirías, cambiando **al menos tres** declaraciones, y explicá en una frase por qué mejora cada cambio.

```css
.parrafo {
  font-size: 11px;
  line-height: 1;
  letter-spacing: 3px;
  text-align: justify;
}
```

_RA: RA-2, RA-3_

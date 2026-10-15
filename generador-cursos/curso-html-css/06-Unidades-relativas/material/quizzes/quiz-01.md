# 📝 Quiz 01 — Unidades relativas

8 ítems. Sin respuestas (ver `material/soluciones/soluciones-quiz.md` para la clave, material
exclusivamente docente).

---

**1. [selección múltiple]** 🔘
¿Cuál de estas unidades es **relativa**?

A. `cm`
B. `pt`
C. `rem`
D. `in`

_RA: RA-1_

---

**2. [selección múltiple]** 🔘
En una pantalla de alta densidad con `devicePixelRatio` de `2`, ¿cuántos **puntos físicos** de ancho ocupa una caja de `100px`?

A. 50
B. 100
C. 200
D. 400

_RA: RA-2_

---

**3. [identificación de resultado]** 🔍
¿Cuántos píxeles de CSS mide `3pc`?

A. 3
B. 36
C. 48
D. 96

_RA: RA-3_

---

**4. [selección múltiple]** 🔘
Un contenedor mide `400px` de ancho por `100px` de alto. Su hijo tiene `padding: 10%`. ¿Cuántos píxeles de relleno tiene el hijo **arriba**?

A. 10
B. 40
C. 100
D. 400

_RA: RA-4_

---

**5. [identificación de resultado]** 🔍
Con la raíz en `16px`, ¿cuántos píxeles mide el texto del tercer nivel?

```html
<div class="n">Uno
  <div class="n">Dos
    <div class="n">Tres</div>
  </div>
</div>
```

```css
.n {
  font-size: 1.5em;
}
```

A. 24
B. 36
C. 54
D. 72

_RA: RA-5_

---

**6. [selección múltiple]** 🔘
¿Cuál de estas unidades **no se acumula** al anidar elementos?

A. `em`
B. `%`
C. `rem`
D. `ch`

_RA: RA-5_

---

**7. [corrección de errores]** ✏️
Esta hoja tiene **dos errores**: el navegador ignora dos declaraciones. Encontralos y escribí la hoja corregida con el mismo propósito (un campo de 30 caracteres de ancho y un bloque de 200 píxeles de alto).

```css
.campo {
  width: 30 ch;
}

.bloque {
  height: 200;
}
```

_RA: RA-1, RA-6_

---

**8. [problema breve]** 🧩
Elegí una unidad para cada situación y justificá la elección en una frase: (a) el tamaño del texto principal, (b) un borde fino, (c) el ancho máximo de lectura de un párrafo, (d) el alto de un bloque que muestra
exactamente tres líneas, (e) una sección que ocupa la mitad de la altura de la ventana.

_RA: RA-7_

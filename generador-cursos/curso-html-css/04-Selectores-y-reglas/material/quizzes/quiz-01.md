# 📝 Quiz 01 — Selectores y reglas

8 ítems. Sin respuestas (ver `material/soluciones/soluciones-quiz.md` para la clave, material
exclusivamente docente).

---

**1. [selección múltiple]** 🔘
¿Qué elementos elige el selector `.destacado`?

A. Todas las etiquetas `<destacado>`.
B. Los elementos que tienen `class="destacado"`.
C. El único elemento que tiene `id="destacado"`.
D. Todos los elementos de la página.

_RA: RA-1_

---

**2. [selección múltiple]** 🔘
¿Qué enlaces elige el selector `a[href$=".pdf"]`?

A. Los que tienen exactamente `href=".pdf"`.
B. Los que tienen un `href` que **empieza** con `.pdf`.
C. Los que tienen un `href` que **termina** en `.pdf`.
D. Los que tienen un `href` que **contiene** `.pdf` en cualquier lugar, pero no al final.

_RA: RA-2_

---

**3. [selección múltiple]** 🔘
Con la convención de esta clase, ¿cómo se nombra el modificador «grande» del elemento «botón» del bloque «tarjeta»?

A. `tarjeta__boton--grande`
B. `tarjeta--boton__grande`
C. `tarjeta__boton__grande`
D. `tarjetaBotonGrande`

_RA: RA-3_

---

**4. [identificación de resultado]** 🔍
Con este HTML, ¿cuántos párrafos elige el selector `section > p`?

```html
<section>
  <h2>Título</h2>
  <p>Uno</p>
  <p>Dos</p>
  <div>
    <p>Tres</p>
  </div>
</section>
```

A. 1
B. 2
C. 3
D. 4

_RA: RA-4_

---

**5. [selección múltiple]** 🔘
¿Qué elige el selector `a:not([href^="https"])`?

A. Los enlaces cuyo `href` empieza con `https`.
B. Los enlaces cuyo `href` **no** empieza con `https`.
C. Todos los elementos que no son enlaces.
D. Los enlaces que no tienen `href`.

_RA: RA-5_

---

**6. [identificación de resultado]** 🔍
Con esta lista, ¿qué elementos elige `li:nth-child(even)`?

```html
<ul>
  <li>Uno</li>
  <li>Dos</li>
  <li>Tres</li>
  <li>Cuatro</li>
  <li>Cinco</li>
</ul>
```

A. «Uno», «Tres» y «Cinco».
B. «Dos» y «Cuatro».
C. Solo «Dos».
D. Ninguno.

_RA: RA-6_

---

**7. [corrección de errores]** 🛠️
Esta hoja tiene **dos errores**: un enlace visitado no cambia de color al pasar el cursor, y una regla no elige nada. Encontralos y explicá cómo
corregirlos.

```css
a:hover {
  color: red;
}

a:visited {
  color: purple;
}

li:nth-child(0) {
  color: green;
}
```

_RA: RA-6_

---

**8. [problema breve]** 🧩
Esta hoja tiene dos reglas para el mismo título. El título se ve azul, aunque la segunda regla dice rojo.

```css
main article.tarjeta h3.tarjeta__titulo {
  color: blue;
}

.tarjeta__titulo {
  color: red;
}
```

Explicá en dos frases por qué ocurre y cómo reescribirías la hoja para que el título se vea rojo sin usar `!important`.

_RA: RA-7_

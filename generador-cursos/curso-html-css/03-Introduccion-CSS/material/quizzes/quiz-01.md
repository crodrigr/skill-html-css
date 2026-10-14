# 📝 Quiz 01 — Introducción a CSS

8 ítems. Sin respuestas (ver `material/soluciones/soluciones-quiz.md` para la clave, material
exclusivamente docente).

---

**1. [selección múltiple]** 🔘
¿Qué significa la sigla CSS y para qué se usa?

A. *Computer Style Syntax*: para programar el comportamiento de una página.
B. *Cascading Style Sheets* (hojas de estilo en cascada): para definir el aspecto de una página, separándolo del contenido.
C. *Content Structure System*: para definir la estructura de una página.
D. *Colored Style Sets*: para elegir solo los colores de una página.

_RA: RA-1_

---

**2. [selección múltiple]** 🔘
Un sitio tiene cinco páginas que deben compartir el mismo aspecto. ¿Qué forma de enlazar CSS conviene usar?

A. Un atributo `style` en cada elemento de cada página.
B. Un bloque `<style>` copiado en cada página.
C. Un archivo `.css` externo, enlazado con `<link rel="stylesheet">` desde las cinco páginas.
D. Escribir los estilos dentro del `<body>`, entre comentarios.

_RA: RA-2_

---

**3. [identificación de resultado]** 🔍
En la regla `.destacado { color: green; }`, ¿qué es `green`?

A. El selector.
B. La propiedad.
C. El valor.
D. El bloque de declaraciones.

_RA: RA-3_

---

**4. [selección múltiple]** 🔘
Cambiás un color en las herramientas para desarrolladores del navegador y la página se ve como querías. ¿Qué pasó con tu archivo `.css`?

A. Se modificó y se guardó solo.
B. Se modificó, pero hay que guardarlo.
C. No cambió: el cambio es una prueba y hay que copiarlo al archivo.
D. Se borró y se reemplazó por la versión del navegador.

_RA: RA-4_

---

**5. [identificación de resultado]** 🔍
Estas son las reglas de la hoja y este es el párrafo. ¿De qué color se ve el texto?

```css
p {
  color: gray;
}

.destacado {
  color: green;
}

#aviso {
  color: blue;
}
```

```html
<p class="destacado" id="aviso">Un párrafo</p>
```

A. Gris, porque `p` es la primera regla.
B. Verde, porque las clases son más específicas que los identificadores.
C. Azul, porque el identificador es más específico que la clase y que el elemento.
D. Negro, porque las tres reglas se anulan entre sí.

_RA: RA-5_

---

**6. [corrección de errores]** 🛠️
Esta hoja quiere definir y usar una variable, pero **no funciona**. Encontrá **dos errores** y explicá cómo corregir cada uno.

```css
:root {
  color-principal: #2563eb;
}

a {
  color: var(--Color-principal);
}
```

_RA: RA-6_

---

**7. [selección múltiple]** 🔘
Cuatro de estas formas escriben el mismo rojo sólido. ¿Cuál **no**?

A. `#ff0000`
B. `rgb(255, 0, 0)`
C. `hsl(0, 100%, 50%)`
D. `rgb(255 0 0 / 0.5)`

_RA: RA-7_

---

**8. [problema breve]** 🧩
Una caja tiene texto blanco sobre un fondo azul oscuro. Querés que el fondo se vea semitransparente, pero que el texto siga nítido. ¿Usarías `opacity: 0.5` o un color con canal alfa en `background-color`? Explicá por qué en dos frases y escribí la declaración que usarías.

_RA: RA-8_

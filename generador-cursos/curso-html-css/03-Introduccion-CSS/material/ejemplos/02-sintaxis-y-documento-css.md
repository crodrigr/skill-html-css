# 📘 Ejemplo 02 — Sintaxis y documento CSS

## 🧱 Situación inicial

Lucía ya enlazó `css/estilos.css` a sus páginas. Ahora tiene que escribir las reglas. Quiere dar color a los títulos y a los
enlaces, resaltar un párrafo con una clase, y probar cada tipo de selector en una página de práctica, `selectores.html`.

## 💻 Código

Reglas para un elemento (`h2` y `a`, de `estilos.css`):

```css
h2 {
  color: var(--color-oscuro);
}

/* Enlaces */
a {
  color: var(--color-principal);
}
```

Una regla para una clase y otra para un identificador:

```css
.destacado {
  color: var(--color-principal);
  background-color: #ffffff;
}

#portada {
  background-color: var(--color-fondo);
  background-image: url("../imagenes/portada.png");
  background-repeat: no-repeat;
  background-size: cover;
}
```

Los cinco selectores esenciales, en `css/selectores.css`:

```css
/* Selector universal: se aplica a todos los elementos */
* {
  border-style: solid;
  border-width: 1px;
  border-color: #f59e0b;
}

/* Selector de elemento */
p {
  color: #1f2937;
}

/* Selector de grupo: la misma regla para dos selectores */
h1, h2 {
  color: #1e3a8a;
}

/* Selector de clase */
.destacado {
  color: #2563eb;
}

/* Selector de identificador */
#aviso {
  color: #16a34a;
}
```

## 🔍 Análisis paso a paso

1. **La regla.** Un selector (`h2`), un bloque entre llaves y, adentro, declaraciones: `color: var(--color-oscuro);`. Cada declaración
   tiene una propiedad, dos puntos, un valor y un punto y coma.
2. **Selector de elemento.** `h2` y `a` se aplican a **todos** los títulos de segundo nivel y a **todos** los enlaces.
3. **Selector de clase.** `.destacado` (con punto) se aplica a los elementos con `class="destacado"`. Se puede usar en muchos.
4. **Selector de identificador.** `#portada` (con numeral) se aplica al elemento con `id="portada"`. Hay uno por página.
5. **Selector de grupo.** `h1, h2` escribe la misma regla para dos selectores, separados por coma.
6. **Selector universal.** `*` se aplica a **todos** los elementos. En `selectores.css` dibuja un borde naranja alrededor de
   cada elemento, y por eso se ven los contornos de todos.
7. **El documento CSS.** `estilos.css` es un archivo de texto con las reglas una debajo de otra. Los comentarios `/* … */` las
   organizan por tema y el navegador los ignora.
8. **Comprobar.** Abre `selectores.html` y revisa cada color con las herramientas del navegador (Ejemplo 03).

## ✅ Resultado esperado

- Los títulos `h1` y `h2` de `selectores.html` se ven en **azul oscuro** (`rgb(30, 58, 138)`): los alcanza la regla de grupo.
- El párrafo común se ve en gris oscuro (`rgb(31, 41, 55)`).
- El párrafo con `class="destacado"` se ve **azul** (`rgb(37, 99, 235)`).
- El párrafo con `id="aviso"` se ve **verde** (`rgb(22, 163, 74)`).
- **Todos** los elementos, incluido `body`, tienen un borde naranja de 1 píxel, por el selector universal.

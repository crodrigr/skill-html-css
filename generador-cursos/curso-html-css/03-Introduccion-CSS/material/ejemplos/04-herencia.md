# 📘 Ejemplo 04 — Herencia

## 🧱 Situación inicial

Lucía quiere que todo el contenido de una sección tenga el mismo color de texto y un borde alrededor. Pensó en escribir una
regla para cada párrafo y cada énfasis, pero alguien le dijo que alcanza con definirlo **una sola vez** en el contenedor. En una
página de práctica, `herencia.html`, comprueba qué llega a los elementos internos y qué no.

## 💻 Código

La página `herencia.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Herencia | Lucía Fernández</title>
    <link rel="stylesheet" href="css/herencia.css">
  </head>
  <body>
    <h1>Herencia</h1>

    <main>
      <p>Un párrafo con <em>énfasis</em> y un <a href="index.html">enlace común</a>.</p>
      <p>Un enlace que <a class="hereda" href="index.html">hereda el color</a> y otro que <a class="inicial" href="index.html">vuelve al valor inicial</a>.</p>
    </main>
  </body>
</html>
```

La hoja `css/herencia.css`:

```css
/* Herencia: lo que se define en main llega a sus elementos internos */
main {
  color: #16a34a;
  border-style: solid;
  border-width: 2px;
  border-color: #f59e0b;
}

/* inherit: el enlace toma el color de su padre */
.hereda {
  color: inherit;
}

/* initial: el enlace vuelve al valor inicial de la propiedad */
.inicial {
  color: initial;
}
```

## 🔍 Análisis paso a paso

1. **Definir en el contenedor.** La regla `main` pone `color: #16a34a;` (verde) y un borde. Los párrafos, el énfasis y los enlaces están
   **dentro** de `main`: son sus **hijos**.
2. **El color se hereda.** Los párrafos (`p`) y el énfasis (`em`) toman el verde de `main` sin tener ninguna regla propia.
3. **El borde no se hereda.** Solo `main` tiene borde: `border` es una propiedad que **no se hereda**. Los párrafos no tienen borde.
4. **El enlace común tampoco lo hereda.** El navegador le da su propio color azul, que prevalece sobre el heredado.
5. **`inherit`.** El enlace con `class="hereda"` tiene `color: inherit;`: se le pide tomar el valor de su padre y se ve verde.
6. **`initial`.** El enlace con `class="inicial"` tiene `color: initial;`: vuelve al **valor inicial** de la propiedad, que es el color de
   texto por defecto (negro), no el verde ni el azul de los enlaces.
7. **Comprobar.** Con el Inspector, Lucía selecciona cada elemento y mira su color calculado.

## ✅ Resultado esperado

- El texto de `main`, el de cada párrafo y el del `<em>` se ven **verdes** (`rgb(22, 163, 74)`).
- Solo `main` tiene **borde sólido naranja** (`border-top-style: solid`); los párrafos no tienen borde (`none`).
- El primer enlace conserva el **azul del navegador** (`rgb(0, 0, 238)`).
- El enlace `.hereda` se ve **verde**, como su padre.
- El enlace `.inicial` se ve **negro** (`rgb(0, 0, 0)`).

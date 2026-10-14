# 📘 Ejemplo 05 — La cascada

## 🧱 Situación inicial

En la hoja de Lucía hay reglas que dicen cosas distintas sobre el color de un mismo párrafo: una para todos los `p`, otra para
los de clase `destacado`, otra para el identificador `aviso`. Lucía quiere **predecir** qué color tendrá cada párrafo antes de abrir
la página, y entender qué pasa si agrega `!important`. Usa una página de práctica, `cascada.html`.

## 💻 Código

La página `cascada.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Cascada | Lucía Fernández</title>
    <link rel="stylesheet" href="css/cascada.css">
  </head>
  <body>
    <h1>Cascada</h1>

    <p>Un párrafo común.</p>
    <p class="destacado">Un párrafo con clase.</p>
    <p id="aviso" class="destacado">Un párrafo con clase e identificador.</p>
    <p class="nota">Un párrafo con dos reglas del mismo peso.</p>
    <a href="index.html">Un enlace sin regla del autor</a>
  </body>
</html>
```

La hoja `css/cascada.css`:

```css
/* Especificidad: elemento (1) < clase (10) < identificador (100) */
p {
  color: gray;
}

.destacado {
  color: green;
}

#aviso {
  color: blue;
}

/* Orden de aparición: con el mismo peso, gana la última */
.nota {
  color: teal;
}

.nota {
  color: orange;
}
```

La regla con `!important` que agrega después (en `css/cascada-importante.css`):

```css
p {
  color: red !important;
}
```

## 🔍 Análisis paso a paso

1. **Hay varias reglas para un mismo elemento.** Un `<p>` recibe, como mínimo, la regla `p`. Si además tiene una clase o un
   identificador, recibe más reglas. Hay que decidir cuál gana.
2. **Origen.** Todas son del **autor** (de Lucía). Los estilos del navegador (como el azul de los enlaces) pierden contra las
   del autor.
3. **Importancia.** Ninguna lleva `!important` todavía.
4. **Especificidad.** Elemento (`p`) vale 1, clase (`.destacado`) vale 10 e identificador (`#aviso`) vale 100.
   - El párrafo común solo recibe `p`: se ve **gris**.
   - El párrafo con clase recibe `p` (1) y `.destacado` (10): gana la clase y se ve **verde**.
   - El párrafo con clase e identificador recibe `p`, `.destacado` y `#aviso` (100): gana el identificador y se ve **azul**.
5. **Orden de aparición.** El cuarto párrafo recibe dos reglas con **la misma especificidad**: `.nota { color: teal; }` y,
   más abajo, `.nota { color: orange; }`. Gana la **última**: se ve **naranja**.
6. **Origen frente al autor.** El enlace de la página no tiene ninguna regla de Lucía: se queda con el color del navegador.
7. **Agregar `!important`.** En `cascada-importante.css`, `p { color: red !important; }` anula todo lo anterior, aunque el
   selector `p` sea el menos específico.
8. **La lección.** `!important` resuelve el problema, pero hace la hoja difícil de mantener. Conviene usarlo solo cuando no haya
   otra salida.

## ✅ Resultado esperado

Con `cascada.css`:

| Elemento | Color que se ve | Por qué |
|---|---|---|
| `<p>` común | Gris (`rgb(128, 128, 128)`) | Solo lo alcanza `p` |
| `<p class="destacado">` | Verde (`rgb(0, 128, 0)`) | La clase (10) gana al elemento (1) |
| `<p id="aviso" class="destacado">` | Azul (`rgb(0, 0, 255)`) | El identificador (100) gana a la clase (10) |
| `<p class="nota">` | Naranja (`rgb(255, 165, 0)`) | Misma especificidad: gana la última regla |
| El enlace | Azul del navegador (`rgb(0, 0, 238)`) | Sin regla del autor |

Con `cascada-importante.css`, **los cuatro párrafos se ven rojos** (`rgb(255, 0, 0)`).

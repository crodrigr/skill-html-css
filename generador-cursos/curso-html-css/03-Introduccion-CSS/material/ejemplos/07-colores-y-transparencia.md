# 📘 Ejemplo 07 — Colores y transparencia

## 🧱 Situación inicial

Lucía quiere elegir bien el color de su sitio. Sabe que existen varias formas de escribir un mismo color y quiere comprobar que dan
el mismo resultado. También quiere un fondo azul **semitransparente** para las citas de sus clientes. Lo prueba en una página de
práctica, `colores.html`.

## 💻 Código

La hoja `css/colores.css`:

```css
/* Propiedades de color: color (texto), background-color (fondo) y border-color (borde) */
p {
  color: #ffffff;
  border-style: solid;
  border-width: 2px;
  border-color: #1e3a8a;
}

/* Un color por nombre */
.nombre {
  background-color: royalblue;
}

/* El mismo azul principal escrito de tres formas */
.hexadecimal {
  background-color: #2563eb;
}

.rgb {
  background-color: rgb(37, 99, 235);
}

.hsl {
  background-color: hsl(221, 83%, 53%);
}

/* El mismo azul con un 50% de transparencia (canal alfa) */
.alfa-rgb {
  background-color: rgb(37 99 235 / 0.5);
}

.alfa-hsl {
  background-color: hsl(221 83% 53% / 50%);
}

.alfa-hex {
  background-color: #2563eb80;
}
```

Y la regla de las citas en el sitio real (de `estilos.css`):

```css
/* Citas: un color con transparencia (canal alfa) */
blockquote {
  background-color: rgb(37 99 235 / 0.15);
}
```

## 🔍 Análisis paso a paso

1. **Propiedades de color.** `color` colorea el texto (blanco, en la página de práctica), `background-color` el fondo y `border-color`
   el borde. El borde necesita `border-style` y `border-width`: sin ellos no se ve.
2. **Por nombre.** `royalblue` es un color con nombre. Es cómodo, pero hay una lista limitada de nombres y no alcanza para cualquier color.
3. **Hexadecimal.** `#2563eb` son tres pares de dígitos: rojo `25`, verde `63` y azul `eb`, en base 16.
4. **RGB.** `rgb(37, 99, 235)` son los mismos tres valores en base 10, de 0 a 255. Es **exactamente** el mismo color que el
   hexadecimal.
5. **HSL.** `hsl(221, 83%, 53%)` describe el color por su tono (en grados), su saturación y su luminosidad. Escrito con números
   redondeados, el navegador lo calcula como `rgb(36, 99, 235)`: **casi** el mismo color, con una diferencia de un punto en un canal
   que no se nota.
6. **Transparencia con alfa.** Un cuarto valor, de 0 a 1 (o de 0% a 100%), después de una barra: `rgb(37 99 235 / 0.5)` y
   `hsl(221 83% 53% / 50%)`. En hexadecimal se agregan dos dígitos: `#2563eb80`, donde `80` es aproximadamente la mitad.
7. **Las citas.** En el sitio, `blockquote` usa `rgb(37 99 235 / 0.15)`: un azul muy suave, que deja ver el fondo de la página.
8. **Cuidado con el contraste.** El texto oscuro sobre ese fondo suave se lee bien; el texto blanco no se leería.

## ✅ Resultado esperado

| Elemento de `colores.html` | Color de fondo que se calcula |
|---|---|
| `.nombre` (`royalblue`) | `rgb(65, 105, 225)` |
| `.hexadecimal` | `rgb(37, 99, 235)` |
| `.rgb` | `rgb(37, 99, 235)` (idéntico al hexadecimal) |
| `.hsl` | `rgb(36, 99, 235)` (casi idéntico) |
| `.alfa-rgb`, `.alfa-hex` | `rgba(37, 99, 235, 0.5)` |
| `.alfa-hsl` | `rgba(36, 99, 235, 0.5)` |

- Los tres azules sólidos se ven **iguales a simple vista**; los tres con alfa se ven **más claros**, porque dejan pasar el blanco de
  la página.
- Todos los párrafos tienen borde azul oscuro de 2 píxeles (`border-color`).
- En el sitio, las citas se ven con un fondo azul **muy suave** (`rgba(37, 99, 235, 0.15)`).

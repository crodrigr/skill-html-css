# 📘 Ejemplo 08 — Gradientes, imágenes y opacidad

## 🧱 Situación inicial

Lucía quiere darle más identidad a su sitio: un título con un **gradiente** de azul oscuro a azul, un fondo con una **imagen** de
portada y un patrón en el pie, y una letra chica más **tenue**. Primero lo prueba en una página de práctica, `fondos.html`, con
cajas de 400 × 80 píxeles.

## 💻 Código

La hoja `css/fondos.css`:

```css
/* Una caja de práctica */
.caja {
  width: 400px;
  height: 80px;
  color: #ffffff;
  background-color: #1e3a8a;
}

/* Gradientes: se escriben en background-image */
.lineal {
  background-image: linear-gradient(90deg, #1e3a8a, #2563eb);
}

.radial {
  background-image: radial-gradient(circle, #f59e0b, #1e3a8a);
}

/* Imágenes de fondo: la ruta es relativa a este archivo CSS */
.patron {
  color: #1f2937;
  background-image: url("../imagenes/patron.png");
  background-repeat: repeat;
}

.portada {
  color: #1f2937;
  background-image: url("../imagenes/portada.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

/* Opacidad frente a color con alfa */
.con-opacidad {
  opacity: 0.5;
}

.con-alfa {
  background-color: rgb(30 58 138 / 0.5);
}
```

Y su uso en el sitio real (de `estilos.css`): el gradiente de los títulos y las imágenes de la portada y del pie.

```css
h1 {
  color: #ffffff;
  background-color: var(--color-oscuro);
  background-image: linear-gradient(90deg, var(--color-oscuro), var(--color-principal));
}
```

```css
#portada {
  background-color: var(--color-fondo);
  background-image: url("../imagenes/portada.png");
  background-repeat: no-repeat;
  background-size: cover;
}
```

```css
footer {
  background-color: var(--color-fondo);
  background-image: url("../imagenes/patron.png");
  background-repeat: repeat;
}

small {
  opacity: 0.7;
}
```

## 🔍 Análisis paso a paso

1. **Un gradiente es una imagen.** Se escribe en `background-image`, no en `background-color`. Se deja también un `background-color`
   por si el navegador no lo entiende.
2. **Gradiente lineal.** `linear-gradient(90deg, #1e3a8a, #2563eb)` va de izquierda a derecha: `90deg` equivale a `to right`.
   Por defecto el gradiente va hacia abajo (`to bottom`). Con más colores se pueden indicar paradas en porcentajes.
3. **Gradiente radial.** `radial-gradient(circle, #f59e0b, #1e3a8a)` parte del centro con el naranja y termina en azul oscuro en los
   bordes. La forma puede ser `circle` o `ellipse`.
4. **Imagen de fondo.** `background-image: url("../imagenes/patron.png")`. La ruta se cuenta **desde el archivo CSS**: el CSS
   está en `css/` y la imagen, en `imagenes/`, por eso `../imagenes/`.
5. **Repetición.** `repeat` (por defecto) repite el mosaico en horizontal y vertical: sirve para un patrón. `no-repeat` la muestra una
   sola vez.
6. **Tamaño y posición.** `background-size: cover` agranda la imagen para llenar la caja, recortando lo que sobre. `background-position:
   center` la centra.
7. **Opacidad.** `opacity: 0.5` hace a la caja **y a todo su contenido** medio transparente. `rgb(30 58 138 / 0.5)` en
   `background-color` hace transparente **solo el fondo**: el texto queda blanco y nítido.
8. **No se hereda.** El párrafo de la caja con opacidad tiene `opacity: 1`, pero se dibuja dentro de la caja ya atenuada.

## ✅ Resultado esperado

- La caja `.lineal` pasa de azul oscuro (izquierda) a azul (derecha): `linear-gradient(90deg, rgb(30, 58, 138), rgb(37, 99, 235))`.
- La caja `.radial` tiene un **centro naranja** que se oscurece hacia **azul oscuro** en los bordes.
- La caja `.patron` muestra un mosaico de **puntitos celestes** que se repite.
- La caja `.portada` muestra **una sola imagen** de círculos suaves, centrada, que cubre toda la caja (`background-position: 50% 50%`).
- La caja `.con-opacidad` tiene opacidad 0,5: **se ve todo más tenue, también el texto**.
- La caja `.con-alfa` tiene el fondo semitransparente (`rgba(30, 58, 138, 0.5)`) pero su texto **sigue blanco** (`rgb(255, 255, 255)`).
- En el sitio, los títulos `h1` se ven con **gradiente azul**, la portada del inicio con su **imagen**, el pie con el **patrón** y la letra
  chica con opacidad 0,7.

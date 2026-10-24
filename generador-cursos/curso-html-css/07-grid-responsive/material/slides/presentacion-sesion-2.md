# 📱 Diseño adaptable y consultas de medios

Curso **HTML y CSS** · Clase 07 · **Sesión 2**

---

## 🎯 Objetivos de la sesión

- 🔹 Explicar qué es el diseño adaptable y la ventana de visualización.
- 🔹 Preparar una página para que no se desborde.
- 🔹 Elegir una estrategia y escribir consultas de medios.

> 📌 Se necesita de la sesión 1: `display: grid`, `fr`, `repeat()` y `gap`.

---

## 🌐 ¿Qué es el diseño adaptable?

**Una** página que se acomoda al tamaño del dispositivo.

- Ancho fijo (`960px`) → se sale de una pantalla angosta.
- Ancho flexible (`max-width`) → usa lo que hay.

---

## 🪟 La ventana de visualización

![Dos teléfonos. Sin la etiqueta meta viewport, según MDN el navegador móvil dibuja la página en una ventana virtual de unos 980 píxeles y la reduce para que quepa, y el texto queda diminuto. Con la etiqueta, la página se dibuja en el ancho real del dispositivo y el texto se lee bien.](../imagenes/ventana-de-visualizacion.svg)

---

## 🧰 Preparación previa

- 🔹 `<meta name="viewport" content="width=device-width, initial-scale=1">`
- 🔹 `* { box-sizing: border-box; }`
- 🔹 `img { max-width: 100%; height: auto; }`

> ⚠️ El efecto de la etiqueta solo se ve en teléfonos y tabletas.

---

## 🧭 Estrategias de diseño

![Dos recorridos que llegan al mismo resultado. Móvil primero: se escribe una columna, con min-width 600px pasa a dos y con min-width 900px a tres. Escritorio primero: se escribe tres columnas, con max-width 899px pasa a dos y con max-width 599px a una.](../imagenes/movil-primero-frente-a-escritorio-primero.svg)

---

## 🧲 La cuadrícula que se acomoda sola

```css
.galeria {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 16px;
}
```

- En `500px`: 2 columnas · `800px`: 3 · `1200px`: 5.
- Alcanza para tarjetas iguales; para **otra disposición**, una consulta.

---

## ❓ ¿Qué es una consulta de medios?

![Un eje con el ancho de la ventana dividido por dos puntos de ruptura, 600 y 900 píxeles, en tres tramos: menos de 600 con una columna, de 600 a 899 con dos y 900 o más con tres. Se marcan las ventanas de comprobación de 500, 800 y 1200 píxeles.](../imagenes/puntos-de-ruptura-y-media-query.svg)

---

## 🎛️ Condiciones

- `(min-width: 600px)`: 600px **o más**.
- `(min-width: 600px) and (max-width: 899px)`: un tramo.
- `(max-width: 599px), (min-width: 900px)`: **o**.
- `(orientation: landscape)`: ancho mayor que alto.

---

## 🔢 El orden importa

- Si dos consultas coinciden, **gana la que va después**.
- Móvil primero: de **menor a mayor**.
- Revisá que los rangos se **toquen**.

---

## 🧩 Todo junto

![La misma página en tres ventanas. A 500 píxeles todos los bloques se apilan en una columna. A 800 píxeles hay dos columnas: el menú y el contenido van juntos y la cabecera, el lateral y el pie ocupan el ancho. A 1200 píxeles hay tres columnas: menú, contenido y lateral en la misma fila, entre la cabecera y el pie.](../imagenes/misma-cuadricula-en-tres-tamanos.svg)

---

## ⚠️ Errores comunes

- 🚫 Olvidar la ventana de visualización.
- 🚫 Ancho fijo en `px` en cajas y imágenes.
- 🚫 Consultas de `min-width` de mayor a menor.
- 🚫 Rangos que dejan huecos (`500px` y `700px`).

---

## 🛠️ Actividad

**Taller 02 — Que se adapte.**

Y los ejercicios **Intermedio 01**, **Intermedio 02** y el **Desafío 01**. Probá en `500px`, `800px` y `1200px`.

---

## ✅ Resumen y evaluación

- 🔹 Medidas flexibles + preparación previa.
- 🔹 Móvil primero con `min-width`; `auto-fit` para galerías.
- 🔹 Las consultas cambian la disposición en los puntos de ruptura.
- 🔹 Cierre: **Quiz 01** (10 ítems).

# 📘 Ejemplo 08 — Modelo de cajas

> 🕐 **Sesión 2** · 🎓 **Resultados de aprendizaje:** RA-7

## 🧱 Situación inicial

Lucía pone dos cajas en `cajas.html` con **exactamente las mismas medidas**: `200px` de ancho, `20px` de relleno, `5px` de borde y `10px` de margen. Una mide más que la otra.
Quiere entender por qué y cuánto espacio ocupa cada una.

## 💻 Código

El contenido de `cajas.html` (dentro de `<main>`):

```html
<h2>Dos cajas con las mismas medidas</h2>
<div class="caja caja--a">Caja A: content-box</div>
<div class="caja caja--b">Caja B: border-box</div>
```

La hoja `css/cajas.css`:

```css
/* Las mismas medidas para las dos cajas */
.caja {
  width: 200px;
  padding: 20px;
  border: 5px solid #2563eb;
  margin: 10px;
  background-color: #dbeafe;
}

/* Cálculo por defecto: el ancho es solo el del contenido */
.caja--a {
  box-sizing: content-box;
}

/* El ancho incluye el relleno y el borde */
.caja--b {
  box-sizing: border-box;
}
```

## 🔍 Análisis paso a paso

1. **Las cuatro capas.** Todo elemento es una caja, de adentro hacia afuera: **contenido**, **relleno** (`padding`, el espacio entre el contenido y el borde), **borde** y **margen**
   (el espacio fuera del borde, que separa la caja de las vecinas). Mirá el diagrama de la explicación.
2. **Qué mide `width`.** Por defecto (`box-sizing: content-box`) `width` es **solo el ancho del contenido**; el relleno y el borde se **suman** por fuera.
3. **Caja A (`content-box`).** `200 + 20 + 20 + 5 + 5 = 250px` de borde a borde. Con los márgenes (`10 + 10`) ocupa **270px** de ancho en la línea.
4. **Caja B (`border-box`).** Con `box-sizing: border-box`, `width` **incluye** el relleno y el borde: la caja mide **200px** de borde a borde y el contenido queda en
   `200 − 20 − 20 − 5 − 5 = 150px`. El margen sigue siendo externo y no se incluye.
5. **Por qué se usa `border-box`.** Si pedís una caja de `200px`, mide `200px` aunque le agregues relleno o borde. Es más fácil calcular y evita que las cajas se pasen del
   espacio disponible.
6. **Cómo comprobarlo.** En las herramientas del navegador, la pestaña de estilos muestra el diagrama de la caja con sus cuatro medidas. En la consola, `elemento.offsetWidth`
   devuelve el ancho de borde a borde y `elemento.clientWidth`, el de contenido más relleno.
7. **El margen nunca se incluye.** Ni `content-box` ni `border-box` meten el margen dentro de `width`.
8. **Un atajo habitual.** Muchos sitios aplican `border-box` a todos los elementos con `* { box-sizing: border-box; }`. En esta clase lo escribimos solo en la caja que lo necesita.

## ✅ Resultado esperado

| Caja | `box-sizing` | `width` | Ancho de borde a borde (`offsetWidth`) | Contenido más relleno (`clientWidth`) | Ancho del contenido |
|---|---|---|---|---|---|
| A | `content-box` | `200px` | **250** | 240 | 200 |
| B | `border-box` | `200px` | **200** | 190 | 150 |

- Ambas tienen margen de `10px` y se ven con el mismo fondo y el mismo borde; **la caja A se ve 50px más ancha** que la B.

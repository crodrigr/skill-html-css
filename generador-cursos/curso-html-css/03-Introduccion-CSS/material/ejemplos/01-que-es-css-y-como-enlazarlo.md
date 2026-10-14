# 📘 Ejemplo 01 — Qué es CSS y cómo enlazarlo

## 🧱 Situación inicial

Lucía tiene su sitio de siete páginas hecho con HTML: se ve con el aspecto por defecto del navegador. Quiere que sus títulos
tengan color, y le dijeron que eso se hace con **CSS**. Antes de empezar, quiere saber **qué es** y **cómo se conecta** con sus
páginas. Probará las tres formas de enlazar CSS en una página de práctica, `enlazar.html`.

## 💻 Código

La página de práctica `enlazar.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Formas de enlazar CSS | Lucía Fernández</title>
    <!-- 1. Archivo externo -->
    <link rel="stylesheet" href="css/estilos.css">
    <!-- 2. Bloque interno -->
    <style>
      .interno {
        color: purple;
      }
    </style>
  </head>
  <body>
    <h1>Formas de enlazar CSS</h1>
    <h2>Estilo del archivo externo</h2>
    <p class="interno">Un párrafo con el estilo del bloque interno.</p>
    <!-- 3. Estilo en línea -->
    <p style="color: orange;">Un párrafo con estilo en línea.</p>
  </body>
</html>
```

La página real de Lucía, `index.html`, enlaza su hoja de estilos con una línea como la segunda de este fragmento, dentro de `<head>`:

```html
<title>Lucía Fernández | Desarrolladora web</title>
<link rel="stylesheet" href="css/estilos.css">
```

## 🔍 Análisis paso a paso

1. **Qué es CSS.** Significa *Cascading Style Sheets* (hojas de estilo en cascada). Es el lenguaje con el que se define **cómo se ve**
   una página. El HTML sigue diciendo **qué es** cada cosa.
2. **Por qué se usa.** Separa el contenido de la presentación: Lucía puede cambiar colores y letras sin tocar el texto.
3. **Forma 1: archivo externo.** `<link rel="stylesheet" href="css/estilos.css">` dentro de `<head>`. `rel="stylesheet"` indica que es una hoja
   de estilos y `href` es la ruta al archivo (relativa a la página).
4. **Forma 2: bloque interno.** Un `<style>` dentro de `<head>`, con reglas adentro. Vale solo para esa página.
5. **Forma 3: estilo en línea.** Un atributo `style` en un elemento. Afecta solo a ese elemento.
6. **Probar.** Lucía abre `enlazar.html`. El título viene del archivo externo (es blanco sobre un gradiente azul), el primer
   párrafo toma el color del bloque interno (violeta) y el segundo, el del estilo en línea (naranja).
7. **Elegir.** Para un sitio de siete páginas, el archivo externo es la mejor opción: las siete lo enlazan y un cambio llega a
   todas. El estilo en línea se evita: es difícil de mantener y MDN lo considera una mala práctica.

## ✅ Resultado esperado

- En `enlazar.html`, el `h1` se ve con **texto blanco** (`rgb(255, 255, 255)`) y un **fondo azul con degradado**: viene del archivo externo.
- El párrafo con `class="interno"` se ve **violeta** (`rgb(128, 0, 128)`): viene del bloque interno.
- El párrafo con `style="color: orange;"` se ve **naranja** (`rgb(255, 165, 0)`): viene del estilo en línea.
- El contenido de la página no cambió: solo su aspecto.

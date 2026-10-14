# 📘 Ejemplo 02 — Estructura, sintaxis y DOM

## 🧱 Situación inicial

Lucía ya tiene su primera página. Ahora quiere entender por qué funciona, y qué pasa cuando algo se escribe mal. Parte de
este documento:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Sobre mí | Lucía Fernández</title>
  </head>
  <body>
    <h1>Sobre mí</h1>
    <p>Me llamo <strong>Lucía</strong> y soy desarrolladora web.</p>
  </body>
</html>
```

## 💻 Código

Una versión con **dos errores**:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Sobre mí | Lucía Fernández
  </head>
  <body>
    <h1>Sobre mí</h1>
    <p>Me llamo <strong>Lucía y soy desarrolladora web.</p></strong>
  </body>
</html>
```

## 🔍 Análisis paso a paso

1. **La estructura.** El documento correcto tiene `doctype`, un `html` que contiene un `head` y un `body`. Todo lo que
   se ve va en el `body`; el `head` guarda datos de la página, como el `title`.
2. **La sintaxis de un elemento.** `<strong>Lucía</strong>` tiene etiqueta de apertura, contenido y etiqueta de cierre
   (con barra). `lang="es"` es un **atributo**: nombre, signo igual y valor entre comillas.
3. **Error 1: etiqueta sin cerrar.** En la versión con errores, `<title>` no tiene su `</title>`. Hay que agregarlo
   antes de `</head>`. Es el error más común.
4. **Error 2: etiquetas solapadas.** `<strong>` se abrió dentro de `<p>`, así que debe **cerrarse antes** que `</p>`.
   Corrección: `<p>Me llamo <strong>Lucía</strong> y soy desarrolladora web.</p>`.
5. **La regla de la anidación.** La última etiqueta que se abre es la primera que se cierra.
6. **El árbol DOM.** El navegador organiza el documento correcto así:

   | Nivel | Elementos |
   |---|---|
   | 1 | `html` |
   | 2 | `head` y `body` (hijos de `html`) |
   | 3 | `meta` y `title` (hijos de `head`); `h1` y `p` (hijos de `body`) |
   | 4 | el texto de `title`; `strong` y el texto de `p` |

   Cada elemento tiene un **padre** (el que lo contiene) y puede tener **hijos** (los que anida). El árbol completo
   es el DOM.

## ✅ Resultado esperado

- El documento **corregido** coincide con el de la situación inicial y se ve como una página con el título «Sobre mí» y
  un párrafo con «Lucía» en negrita.
- Con los errores, el navegador **no avisa**: intenta adivinar y el resultado puede cambiar (por ejemplo, el resto del
  documento puede quedar dentro del título). Por eso conviene revisar cada etiqueta cerrada.
- Podés explicar el DOM como un árbol cuya raíz es `html`, con `head` y `body` como hijos.

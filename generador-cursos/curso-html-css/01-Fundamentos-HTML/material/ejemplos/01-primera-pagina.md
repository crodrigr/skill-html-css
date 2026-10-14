# 📘 Ejemplo 01 — Tu primera página

## 🧱 Situación inicial

Lucía Fernández quiere tener un sitio personal. Todavía no tiene nada: ni carpeta ni archivos. Tiene instalado **VS Code**
y un navegador. Vamos a acompañarla en su primera página.

## 💻 Código

Dentro de la carpeta `portafolio`, el archivo `index.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Lucía Fernández | Desarrolladora web</title>
  </head>
  <body>
    <h1>Lucía Fernández</h1>
    <p>Desarrolladora web junior</p>
  </body>
</html>
```

## 🔍 Análisis paso a paso

1. **Crear la carpeta.** Lucía crea una carpeta llamada `portafolio` en sus documentos.
2. **Abrirla en VS Code.** En VS Code elige *Archivo → Abrir carpeta* y selecciona `portafolio`. El panel lateral
   aparece vacío.
3. **Crear el archivo.** Con el botón de «nuevo archivo» del panel lateral crea `index.html`. La extensión `.html` le
   indica al sistema que es una página web.
4. **Escribir el código.** Copia la estructura mínima: el `doctype`, el `html` con `lang="es"`, el `head` con
   `meta charset` y `title`, y el `body` con un título y un párrafo.
5. **Guardar.** Guarda con `Ctrl + S`. Mientras haya cambios sin guardar, VS Code muestra un punto en la pestaña.
6. **Abrirla en el navegador.** Hace doble clic en `index.html` desde la carpeta (o clic derecho → *Abrir con* →
   navegador).
7. **Cambiar y recargar.** Cambia «junior» por «junior en formación», guarda y recarga la página con `F5`: el cambio
   aparece.

> 💡 **Sin VS Code.** En un editor en línea escribís el mismo código y ves el resultado al lado, sin crear archivos.

## ✅ Resultado esperado

- La **pestaña** del navegador muestra el texto «Lucía Fernández | Desarrolladora web» (viene de `title`).
- En la página se ve un **título grande** con el texto «Lucía Fernández» y, debajo, un **párrafo** con «Desarrolladora
  web junior».
- Al cambiar el texto, guardar y recargar, el cambio se ve en el navegador.
- Las tildes se ven bien gracias a `meta charset="utf-8"`.

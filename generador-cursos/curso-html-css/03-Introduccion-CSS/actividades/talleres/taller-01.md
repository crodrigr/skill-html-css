# 🛠️ Taller 01 — Dale estilo a tu sitio

## 🎯 Objetivo

Aplicar lo aprendido en la clase: enlazar una hoja de estilos (RA-1 y RA-2), escribir reglas con selectores esenciales (RA-3), revisar con
las herramientas del navegador (RA-4), cuidar la herencia y la cascada (RA-5), usar variables (RA-6), elegir y escribir colores (RA-7) y
usar un gradiente, una imagen de fondo y opacidad (RA-8).

## 🌍 Contexto

Trabajás solo o en pareja, con las **dos páginas** (`servicios.html` y `contacto.html`) del taller de la Clase 02 y su tema propio. Usás
VS Code (o un editor en línea) y un navegador. No hace falta JavaScript ni tipografía ni disposición. Podés usar las imágenes de
`recursos/portafolio-inicial/imagenes` o tus propias imágenes.

## 🪜 Pasos

1. **Creá la hoja.** Hacé una carpeta `css/` y un archivo `estilos.css` con un comentario que lo describa.
2. **Enlazala** desde las dos páginas con `<link rel="stylesheet" href="css/estilos.css">` en el `<head>`.
3. **Definí una paleta** de cuatro colores en variables dentro de `:root` y usá las variables en tus reglas.
4. **Escribí reglas** con selectores de elemento (por ejemplo, `h1` y `h2`), de clase (una clase que agregues al HTML) y de identificador.
   Agrupá con una coma al menos dos elementos.
5. **Escribí un mismo color de tres formas distintas** (hexadecimal, `rgb()` y `hsl()`) en una página de prueba y comprobá con las
   herramientas del navegador que se ven iguales o casi iguales.
6. **Agregá un fondo:** un gradiente lineal en el título, una imagen de fondo (con el tamaño y la repetición que correspondan) en la
   cabecera o el pie, y un elemento con un color con transparencia.
7. **Bajá la opacidad** de un elemento y anotá en una frase en qué se diferencia de la transparencia de un color con alfa.
8. **Revisá** con las herramientas del navegador: ninguna declaración tachada o inválida, y las rutas de las imágenes bien contadas
   desde el archivo CSS.

## 📦 Entregable

La carpeta del proyecto con las dos páginas, `css/estilos.css` y las imágenes, y una nota con la frase del paso 7.

## 📋 Criterios de evaluación

- ✔️ La hoja está enlazada desde las dos páginas y no se usa `style` ni `<style>`.
- ✔️ Hay una paleta en variables y las reglas la usan.
- ✔️ Se usan los cuatro tipos de selector pedidos y al menos un grupo.
- ✔️ El mismo color escrito de tres formas se ve igual o casi igual.
- ✔️ Hay un gradiente lineal, una imagen de fondo con las rutas correctas y un color con transparencia.
- ✔️ La nota explica bien la diferencia entre opacidad y alfa.
- ✔️ No se usa `!important` y no se cambió el contenido del HTML.

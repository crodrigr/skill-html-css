# 🟢 Básico 01 — Enlazá una hoja de estilos y escribí tres reglas

> 🟢 **Nivel:** Básico · 🎓 **Resultados de aprendizaje:** RA-1, RA-2, RA-3

## 🧱 Estado inicial

Mateo Ruiz, fotógrafo de Rosario, quiere darle color a su página de inicio. Abrí
[`basico-01.html`](../recursos/portafolio-inicial/basico-01.html) de la carpeta `portafolio-inicial`. La página tiene un título,
dos subtítulos y dos párrafos: uno con `class="destacado"` y otro con `id="aviso"`. **No está enlazada a ninguna hoja de estilos.**
En la carpeta `css/` hay un archivo vacío, [`basico-01.css`](../recursos/portafolio-inicial/css/basico-01.css).

## 🛠️ Proceso esperado

1. En `basico-01.html`, **enlazá** `css/basico-01.css` con la forma que conviene para un sitio de varias páginas, dentro de
   `<head>`.
2. En `basico-01.css`, escribí **tres reglas**:
   - Una regla de **elemento** para `h1`: texto verde, `#16a34a`.
   - Una regla de **clase** para `.destacado`: texto `#111827` y fondo crema `#fef3c7`.
   - Una regla de **identificador** para `#aviso`: texto `#b45309`.
3. Guardá y abrí la página en el navegador.
4. Respondé: ¿qué significa la sigla **CSS**? ¿Por qué se usa una hoja externa en lugar de escribir `style` en cada elemento?

## ✅ Resultado esperado

- ☑️ Una línea `<link rel="stylesheet" href="css/basico-01.css">` dentro de `<head>`.
- ☑️ Tres reglas con la sintaxis correcta (selector, llaves, propiedad, valor y punto y coma).
- ☑️ El `h1` se ve verde; el párrafo `.destacado`, de texto oscuro sobre fondo crema; el párrafo `#aviso`, de color ocre.
- ☑️ Una respuesta de una o dos frases a cada pregunta del paso 4.

## 🚧 Restricciones

- 🚫 No uses el atributo `style` ni un bloque `<style>`.
- 🚫 No cambies el contenido de la página ni sus `class` o `id`.
- 🚫 Escribí solo estos tres selectores.

## 🎓 Resultados de aprendizaje

- RA-1: Explicar qué es CSS, qué significa y por qué se usa.
- RA-2: Enlazar CSS a una página HTML y elegir la forma más adecuada.
- RA-3: Escribir reglas con la sintaxis correcta y organizarlas en un documento CSS.

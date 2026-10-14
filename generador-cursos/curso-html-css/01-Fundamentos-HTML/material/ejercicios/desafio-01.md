# 🔴 Desafío 01 — De `div` a una página semántica

> 🔴 **Nivel:** Desafío · 🎓 **Resultados de aprendizaje:** RA-3, RA-4, RA-5, RA-6, RA-7

## 🧱 Estado inicial

Abrí [`desafio-con-divs.html`](../recursos/portafolio-inicial/desafio-con-divs.html) de la carpeta `portafolio-inicial`.
Es la página de inicio de Mateo hecha **solo con `div`**: se ve bien, pero nada dice qué es cada parte. Tiene una
cabecera con navegación, tres temas («Trabajos destacados», «Servicios» y «Contacto») y un pie. Dentro de «Trabajos
destacados» hay un `div` que agrupa las dos fotos.

## 🛠️ Proceso esperado

1. **Reescribir** la página con etiquetas semánticas: cabecera, navegación, contenido principal, una sección por tema y
   pie.
2. **Decidir qué `div` se mantiene.** Indicá cuál es y por qué. Dejá un comentario junto a ese `div` que lo explique.
3. **Documentar** con un comentario cada bloque principal.
4. **Marcar** con formato la frase «Escribime» (énfasis) en «Contacto».
5. **Agregar al pie** un enlace «Volver arriba» que lleve a la cabecera con un ancla (poné el `id` en la cabecera).
6. **Incrustar** un mapa de OpenStreetMap con `iframe` dentro de la sección «Contacto»:
   `https://www.openstreetmap.org/export/embed.html?bbox=-60.75%2C-33.0%2C-60.6%2C-32.9&layer=mapnik`
7. **Probar** la página en el navegador: los enlaces, el ancla, las imágenes y el mapa.

## ✅ Resultado esperado

- ☑️ Una página semántica que se ve prácticamente igual que la original.
- ☑️ Un `div` que se mantiene, con su justificación.
- ☑️ Comentarios, un énfasis, un ancla funcionando y un mapa incrustado.
- ☑️ El documento pasa la revisión de estructura sin errores.

## 🚧 Restricciones

- 🚫 No cambies los textos ni los nombres de archivo de las imágenes.
- 🚫 No uses más de un `<main>` ni más de un `<h1>`.
- 🚫 No agregues CSS ni JavaScript.

## 🎓 Resultados de aprendizaje

- RA-3: Escribir un documento con estructura válida y buena anidación.
- RA-4: Marcar el texto con formato y documentarlo con comentarios.
- RA-5: Crear hipervínculos y anclas.
- RA-6: Incorporar contenido incrustado con `iframe`.
- RA-7: Organizar una página con etiquetas semánticas y decidir cuándo usar `div`.

## 🧪 Casos de prueba

| # | Comprobación | Resultado esperado |
|---|---|---|
| 1 | Contar los `<main>` | Exactamente uno |
| 2 | Contar los `<h1>` | Exactamente uno, dentro de `<header>` |
| 3 | El `<nav>` | Está dentro de `<header>` y contiene los cuatro enlaces |
| 4 | Contar las `<section>` | Tres, cada una con su título `<h2>` |
| 5 | El pie | Es un `<footer>` y contiene «Volver arriba» |
| 6 | Los `div` que quedan | Exactamente uno, con un comentario que explica por qué |
| 7 | Clic en «Contacto» | La página baja hasta la sección `contacto` |
| 8 | Clic en «Volver arriba» | La página vuelve a la cabecera |
| 9 | Todas las imágenes | Tienen `alt` y se ven |
| 10 | El `iframe` | Tiene `title` y muestra el mapa |
| 11 | La revisión de estructura | 0 errores |

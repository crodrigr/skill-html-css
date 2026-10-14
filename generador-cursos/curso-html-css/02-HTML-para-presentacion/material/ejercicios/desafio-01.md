# 🔴 Desafío 01 — La página de servicios y reserva de Mateo

> 🔴 **Nivel:** Desafío · 🎓 **Resultados de aprendizaje:** RA-1, RA-2, RA-3, RA-4, RA-5, RA-6

## 🧱 Estado inicial

Abrí [`desafio-reserva.html`](../recursos/portafolio-inicial/desafio-reserva.html) de la carpeta `portafolio-inicial`. Tiene
el título «Servicios y reserva» y, debajo, **todo el contenido de la página sin marcar**: servicios, cómo reservar, precios,
una opinión y los datos que debe pedir el formulario de reserva. Tu tarea es convertirlo en una página completa.

## 🛠️ Proceso esperado

1. **Estructura.** Organizá la página con una cabecera (con el `h1` y un `id` para volver arriba), un contenido principal con
   **una sección por tema** (cinco) y un pie con un enlace «Volver arriba».
2. **Separadores.** Poné un separador entre cada par de secciones.
3. **Listas.** «Servicios» es una lista no enumerada con una sublista en «Eventos»; «Cómo reservar» es una lista enumerada.
4. **Tabla.** «Precios» es una tabla con título «Precios por sesión», encabezados, tres filas de datos y un pie con la
   aclaración «Todos los precios incluyen la edición básica» en **una celda que ocupe las dos columnas**.
5. **Cita.** La opinión es una cita extensa con la fuente `https://mateo-ruiz.example/opiniones/laura` y la atribución
   «— Laura Díaz, novia» fuera de la cita.
6. **Formulario.** «Reserva» es un formulario con los cinco datos indicados, etiquetas asociadas, un botón «Reservar» y los
   tipos, nombres y valores que correspondan (nombres: `nombre`, `correo`, `tipo`, `fotos` y `ofertas`).
7. **Comentarios.** Dejá un comentario antes de cada bloque principal.
8. **Probar** la página en el navegador y con los dos envíos del formulario (completo y sin marcar tipo ni ofertas).

## ✅ Resultado esperado

- ☑️ Una página con cabecera, contenido principal con cinco secciones y pie.
- ☑️ Listas, tabla, cita y formulario marcados con las etiquetas adecuadas.
- ☑️ Los dos envíos con la dirección esperada.
- ☑️ El documento pasa la revisión de estructura sin errores.

## 🚧 Restricciones

- 🚫 No cambies los textos ni los datos del archivo de partida (solo agregá etiquetas, atributos y comentarios).
- 🚫 No uses `div`: para cada parte hay una etiqueta que la describe.
- 🚫 El formulario usa `method="get"`, sin `action`, y solo datos inventados.
- 🚫 No uses tablas para ubicar elementos ni agregues CSS o JavaScript.

## 🎓 Resultados de aprendizaje

- RA-1: Separar y organizar el contenido con separadores.
- RA-2: Presentar datos en una tabla con filas, columnas y encabezados.
- RA-3: Crear listas no enumeradas y enumeradas, con sublistas.
- RA-4: Marcar citas y atribuir su fuente.
- RA-5: Explicar qué es un formulario y qué información recoge.
- RA-6: Escribir un formulario básico con `form` e `input`.

## 🧪 Casos de prueba

| # | Comprobación | Resultado esperado |
|---|---|---|
| 1 | Contar los `<main>` y los `<h1>` | Uno de cada uno; el `h1` dentro de `<header>` |
| 2 | Contar las `<section>` | Cinco, cada una con su título `<h2>` |
| 3 | Contar los `<hr>` | Cuatro |
| 4 | Las listas | Dos `<ul>` (la sublista dentro de un `<li>`) y un `<ol>` con tres `<li>` |
| 5 | La tabla | `caption`, `thead` con dos `th`, `tbody` con tres filas de dos `td` y `tfoot` con `colspan="2"` |
| 6 | La cita | Un `<blockquote>` con `cite` y la atribución fuera de él |
| 7 | El formulario | `method="get"`, sin `action`, con tres `radio` que comparten `name="tipo"` |
| 8 | Cada `label` | Su `for` coincide con el `id` de su campo |
| 9 | Envío completo (Ana Pérez, `ana@example.com`, evento, 20 fotos, ofertas) | La dirección termina en `?nombre=Ana+P%C3%A9rez&correo=ana%40example.com&tipo=evento&fotos=20&ofertas=si` |
| 10 | Envío sin elegir tipo ni marcar ofertas (Ana, `ana@example.com`) | La dirección termina en `?nombre=Ana&correo=ana%40example.com&fotos=10` |
| 11 | Un correo sin forma de correo | El navegador no envía el formulario |
| 12 | Contar los `<div>` | Cero |
| 13 | La revisión de estructura | 0 errores |

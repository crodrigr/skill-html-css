# 🧭 Guía paso a paso — Portal de la Academia (Módulos 01 y 02: HTML)

> 👩‍🏫 **Material docente.** Guía única para construir **junto con los estudiantes**, en vivo, el frente web del **sistema académico** del curso de Spring Boot (**estudiantes**, **cursos** y **matrículas**), aplicando lo visto en el [Módulo 01](../01-Fundamentos-HTML/material/ejemplos/explicacion-conceptual.md) y el [Módulo 02](../02-HTML-para-presentacion/material/ejemplos/explicacion-conceptual.md).
> Contiene código completo: no se entrega a los estudiantes antes de resolver el taller.
>
> 📦 **Proyectos terminados:** [`academia-m01/`](codigo/academia-m01/) (fin de la Parte 1) y [`academia-m02/`](codigo/academia-m02/) (fin de la Parte 2) · 🔗 **Mismo sistema** que la [guía de la Academia del curso de Spring Boot](../../../../curso-spring-boot/generador-cursos/curso-spring-boot/guias/modulo-03-diseno-api-rest-con-dto/02-academica-dtos.md): allí se construye la API; aquí, las páginas que más adelante la van a consumir.
>
> ✅ **Verificada.** Las páginas de ambas partes pasan el validador de HTML del curso (`herramientas/validar_html.py`) sin errores.
>
> 🧭 **Idea central.** El portal se construye en **dos partes** sobre el mismo proyecto: la **Parte 1** (Módulo 01) arma estructura, texto, enlaces, multimedia y semántica; la **Parte 2** (Módulo 02) presenta los datos con **tablas, listas, cita y formulario**. Se elige la etiqueta según la forma del dato.

<details>
<summary><strong>🎯 Objetivo</strong></summary>

> Construir el portal de la academia **sin CSS ni JavaScript**, en dos sesiones de 1 h 30 min.
>
> **Parte 1 — Módulo 01.** Al terminar, el estudiante:
>
> - Prepara el entorno y escribe la **estructura mínima** de cada documento.
> - Marca texto con significado y deja **comentarios**.
> - Conecta las páginas con **enlaces**, una dirección externa y **anclas**.
> - Incorpora una **imagen** con `alt` y un **video** con controles.
> - Reorganiza con **etiquetas semánticas** y sabe cuándo bastaría un `div`.
>
> **Parte 2 — Módulo 02.** Al terminar, el estudiante:
>
> - Separa los temas con `hr` y presenta datos en una **tabla completa** (`caption`, `thead`, `tbody`, `tfoot`, `colspan`).
> - Escribe una lista no enumerada con **sublista** y una lista enumerada.
> - Marca un testimonio con `blockquote` y `cite`.
> - Escribe un **formulario** `method="get"` con cinco tipos de campo, `label`, `name` y `value`, y explica qué datos viajan en la dirección.

</details>

<details>
<summary><strong>📝 Introducción: el problema y sus requerimientos</strong></summary>

> > 🗣️ **Para abrir la sesión.** Se lee el problema y se pregunta: «¿qué datos de la academia ya conocemos del curso de Spring Boot?». Cada dato que digan se convierte en un trozo de página.
>
> ### 🏫 El problema
>
> La **Academia de programación** quiere un portal web donde cualquier persona vea quiénes estudian, qué cursos hay y cómo se matricula. Por ahora el portal es **estático**: se escribe a mano. Cuando se llegue a JavaScript, mostrará los datos reales de la API.
>
> ### 🧩 De la entidad a la página
>
> | Entidad (API) | Atributos | Parte 1 (Módulo 01) | Parte 2 (Módulo 02) |
> |---|---|---|---|
> | **Estudiante** | `name`, `age`, `email` | `estudiantes.html`: un `article` por persona | Una **tabla** con una fila por persona |
> | **Curso** | `name`, `price`, `maxCapacity` | `cursos.html`: una `section` por curso | **Lista** de oferta y **tabla** de precios y cupos |
> | **Matrícula** | estudiante + curso | Enlaces del estudiante a sus cursos | **Formulario** `matricula.html` (el `EnrollmentRequest` de la API) |
>
> | Si el dato es… | Etiqueta | Ejemplo en el portal |
> |---|---|---|
> | Un bloque autónomo o un tema | `article` / `section` | Estudiante, curso (Parte 1) |
> | Filas y columnas con el mismo significado | `table` | Estudiantes, cursos |
> | Elementos sin orden / pasos con orden | `ul` / `ol` + `li` | Oferta / cómo te matriculás |
> | Palabras de otra fuente | `blockquote` | Testimonio |
> | Datos que escribe el usuario | `form` + `input` | Matrícula |
>
> <details>
> <summary><strong>✅ Requerimientos funcionales — Parte 1</strong></summary>
>
> >
> > | Código | Requerimiento | Página | Contenido |
> > |---|---|---|---|
> > | **RF-1.01** | Presentar la academia con una bienvenida y un video. | `index.html` | Estructura, formato de texto, video |
> > | **RF-1.02** | Mostrar el logo con texto alternativo. | `index.html` | Imagen y `alt` |
> > | **RF-1.03** | Listar los estudiantes con nombre, edad y correo. | `estudiantes.html` | Títulos, párrafos, `mailto:` |
> > | **RF-1.04** | Listar los cursos con precio y cupo máximo. | `cursos.html` | `section` con `id` |
> > | **RF-1.05** | Navegar entre las páginas desde cualquiera. | todas | Enlaces relativos |
> > | **RF-1.06** | Saltar a un curso desde la misma página o desde un estudiante. | `cursos.html`, `estudiantes.html` | Anclas y fragmentos |
> > | **RF-1.07** | Remitir a la documentación oficial en una pestaña nueva. | `index.html` | Enlace externo |
> >
> </details>
>
> <details>
> <summary><strong>✅ Requerimientos funcionales — Parte 2</strong></summary>
>
> >
> > | Código | Requerimiento | Página | Contenido |
> > |---|---|---|---|
> > | **RF-2.01** | Mostrar los estudiantes en una tabla con nombre, edad, correo y número de cursos. | `estudiantes.html` | Tabla |
> > | **RF-2.02** | Mostrar los cursos con precio y cupo máximo, y una nota al pie. | `cursos.html` | `tfoot` y `colspan` |
> > | **RF-2.03** | Listar la oferta de cursos, con los temas de Java como sublista. | `cursos.html` | `ul` anidada |
> > | **RF-2.04** | Explicar la matrícula en tres pasos. | `cursos.html` | `ol` |
> > | **RF-2.05** | Mostrar un testimonio con su fuente. | `cursos.html` | `blockquote`, `cite` |
> > | **RF-2.06** | Separar los temas de la página. | `cursos.html`, `estudiantes.html` | `hr` |
> > | **RF-2.07** | Pedir nombre, correo, edad, curso y aceptación del reglamento. | `matricula.html` | `form`, `input` |
> >
> </details>
>
> <details>
> <summary><strong>🛠️ Requerimientos no funcionales y restricciones</strong></summary>
>
> >
> > | Código | Requerimiento |
> > |---|---|
> > | **RNF-01** | Solo HTML. **Sin CSS ni JavaScript** (llegan en módulos posteriores). |
> > | **RNF-02** | Todas las etiquetas cerradas y bien anidadas; `lang="es"` y `charset="UTF-8"`. |
> > | **RNF-03** | Toda imagen lleva `alt`; el video lleva `controls`. |
> > | **RNF-04** | Rutas **relativas**; nombres de archivo en minúsculas y sin espacios. |
> > | **RNF-05** | Tipos de `input` permitidos: `text`, `email`, `number`, `radio`, `checkbox` y `submit`. |
> > | **RNF-06** | Formulario con `method="get"` y **sin `action`**: ningún dato sale del equipo. |
> > | **RNF-07** | Cada `label for` coincide con un `id`; cada campo (salvo `submit`) lleva `name`; `radio` y `checkbox` llevan `value`. |
> > | **RNF-08** | Las tablas son para **datos**, no para armar el diseño. |
> > | **RNF-09** | **Solo datos inventados** (correos `@academia.test`). |
> > | **RNF-10** | Duración: 2 sesiones de 1 h 30 min, trabajo individual o en parejas, con VS Code y un navegador. |
> >
> > > 💡 **Alcance.** Quedan fuera: selector, área de texto, validación avanzada, envío a un servidor y todo el estilo (Módulo 03 en adelante).
>
> </details>

</details>

<details>
<summary><strong>⏱️ Plan de las sesiones</strong></summary>

> | Paso | Minutos | Actividad |
> |---|---:|---|
> | | | **Sesión 1 — Parte 1 (Módulo 01)** |
> | 0 | 0 – 10 | Entorno: carpeta, VS Code y navegador |
> | 1 | 10 – 25 | La primera página: estructura mínima (`index.html`) |
> | 2 | 25 – 40 | Texto con significado y comentarios |
> | 3 | 40 – 55 | Las páginas de datos: `estudiantes.html` y `cursos.html` |
> | 4 | 55 – 70 | Enlaces, ancla y enlace externo |
> | 5 | 70 – 80 | Imagen y video |
> | 6 | 80 – 90 | Semántica y revisión final |
> | | | **Sesión 2 — Parte 2 (Módulo 02)** |
> | 7 | 0 – 10 | Punto de partida: el portal de la Parte 1 |
> | 8 | 10 – 25 | Tabla de estudiantes (`thead`, `tbody`, `tfoot`) |
> | 9 | 25 – 40 | Cursos: listas, separadores y tabla |
> | 10 | 40 – 48 | Pasos de matrícula y testimonio |
> | 11 | 48 – 65 | El formulario de matrícula |
> | 12 | 65 – 80 | Probar el formulario y leer la dirección |
> | 13 | 80 – 90 | Revisión final |
>
> > 💡 **Ritmo.** Después de cada paso se guarda y se **recarga el navegador** (`F5`). Quien no ve el cambio, revisa la etiqueta que acaba de escribir.

</details>

<details>
<summary><strong>🏗️ Arquitectura: el árbol de archivos (🆕 nuevo · ✏️ cambia en la Parte 2)</strong></summary>

> ```text
> 📁 academia
> ├── 🆕 index.html          bienvenida · logo · video · enlace externo   (✏️ P2: nav con «Matricular»; sin video)
> ├── 🆕 estudiantes.html    un article por estudiante                    (✏️ P2: tabla)
> ├── 🆕 cursos.html         una section por curso, con id                (✏️ P2: listas · hr · tabla · cita)
> ├── 🆕 matricula.html      (Parte 2) formulario GET
> ├── 📁 imagenes
> │   └── 🆕 logo.svg
> └── 📁 video
>     └── 🆕 recorrido.mp4   (solo en la Parte 1)
> ```

</details>

---

<details>
<summary><strong>🅰️ PARTE 1 — Módulo 01: Fundamentos HTML (Pasos 0 a 6)</strong></summary>

> Carpeta de trabajo: `academia-m01`. Resultado: [`codigo/academia-m01/`](codigo/academia-m01/).

</details>

---


<details>
<summary><strong>🚀 Paso 0 — Entorno</strong></summary>

> <details>
> <summary><strong>Paso 0.1 · Carpeta y archivos</strong></summary>
>
> > 1. Se crea la carpeta `academia-m01` con las subcarpetas `imagenes` y `video`.
> > 2. Se abre en VS Code (`Archivo → Abrir carpeta`).
> > 3. Se crean los tres archivos vacíos: `index.html`, `estudiantes.html` y `cursos.html`.
> > 4. Se copia el logo en `imagenes/logo.svg` y el video en `video/recorrido.mp4` desde la carpeta [`codigo/academia-m01`](codigo/academia-m01/) (el video es de práctica: se puede cambiar por otro propio).
> >
> > > ✅ **Punto de control.** Hacer doble clic en un archivo abre el navegador, aunque esté vacío. No se necesita servidor.
>
> </details>

</details>

---

<details>
<summary><strong>🌱 Paso 1 — La primera página: estructura mínima</strong></summary>

> <details>
> <summary><strong>Paso 1.1 · El esqueleto</strong></summary>
>
> > 🗣️ **Se explica antes de escribir:** `<!DOCTYPE html>` avisa al navegador que es HTML moderno; `html` envuelve todo; `head` lleva lo que **no se ve** (codificación y título); `body` lleva lo que **sí se ve**.
> >
> > <details>
> > <summary><strong>📄 index.html</strong> <em>(esqueleto)</em></summary>
> >
> > ```html
> > <!DOCTYPE html>
> > <html lang="es">
> > <head>
> >   <meta charset="UTF-8">
> >   <title>Academia — Inicio</title>
> > </head>
> > <body>
> >   <h1>Academia de programación</h1>
> > </body>
> > </html>
> > ```
> >
> > </details>
> >
> > **Se prueba:** la pestaña del navegador dice «Academia — Inicio» y la página muestra el título.
> >
> > > ⚠️ **Error típico.** Olvidar `charset`: «Pérez» se ve «PÃ©rez». Se agrega y se recarga.
>
> </details>
>
> <details>
> <summary><strong>Paso 1.2 · Lo mismo en las otras dos páginas</strong></summary>
>
> > Se copia el esqueleto en `estudiantes.html` y `cursos.html`, y se cambian el `title` (`Academia — Estudiantes`, `Academia — Cursos`) y el `h1` (`Estudiantes`, `Cursos`).
> >
> > > 🧠 **Para preguntar:** ¿por qué cada página lleva su propio `title`? *(Aparece en la pestaña, en el historial y en los buscadores.)*
>
> </details>

</details>

---

<details>
<summary><strong>✍️ Paso 2 — Texto con significado y comentarios</strong></summary>

> <details>
> <summary><strong>Paso 2.1 · La bienvenida (RF-1.01)</strong></summary>
>
> > Dentro del `body` de `index.html`, bajo el `h1`, se agrega la bienvenida:
> >
> > ```html
> >   <h2>Bienvenida</h2>
> >   <!-- Este párrafo se reutiliza en las demás páginas del portal -->
> >   <p>La <strong>Academia</strong> enseña programación a personas <em>sin experiencia previa</em>.
> >   Aquí podés ver quiénes estudian, qué cursos hay y cuántos cupos quedan.</p>
> >   <p>Este portal es el <mark>frente web</mark> del sistema académico que se construye en el curso de Spring Boot.</p>
> > ```
> >
> > | Etiqueta | Significa | No es |
> > |---|---|---|
> > | `strong` | importancia | «ponerlo en negrita» |
> > | `em` | énfasis | «ponerlo en cursiva» |
> > | `mark` | resaltado | un color de fondo |
> >
> > > 💡 El comentario `<!-- … -->` **no se muestra**, pero sí queda en el código. Se comprueba con `Ctrl+U` (ver código fuente).
>
> </details>

</details>

---

<details>
<summary><strong>🗂️ Paso 3 — Las páginas de datos</strong></summary>

> <details>
> <summary><strong>Paso 3.1 · Estudiantes (RF-1.03)</strong></summary>
>
> > 🗣️ **Se pregunta:** ¿qué campos tiene un estudiante en la API? *(`name`, `age`, `email`.)* Cada persona es un bloque autónomo, así que se usa `article`.
> >
> > ```html
> >   <article>
> >     <h2>Ana Pérez</h2>
> >     <p>Edad: 24 años</p>
> >     <p>Correo: <a href="mailto:ana@academia.test">ana@academia.test</a></p>
> >   </article>
> > ```
> >
> > Se repite para **Luis Gómez** (31 años, `luis@academia.test`) y **Marta Ruiz** (19 años, `marta@academia.test`). El código completo está en [`estudiantes.html`](codigo/academia-m01/estudiantes.html).
>
> </details>
>
> <details>
> <summary><strong>Paso 3.2 · Cursos (RF-1.04)</strong></summary>
>
> > Cada curso tiene `name`, `price` y `maxCapacity`. Cada uno es un tema con título propio: `section`, y con un **`id`** para poder saltar a él (se usa en el Paso 4).
> >
> > ```html
> >   <!-- Se usa section porque cada curso es un tema con su propio título -->
> >   <section id="java">
> >     <h2>Java desde cero</h2>
> >     <p>Precio: $180.000 · Cupo máximo: 20 personas</p>
> >     <p>Variables, condicionales, ciclos y clases. Es la base para el curso de <em>Spring Boot</em>.</p>
> >   </section>
> > ```
> >
> > Se repite con `id="web"` (HTML y CSS, $150.000, cupo 25) e `id="git"` (Git, $90.000, cupo 30). Ver [`cursos.html`](codigo/academia-m01/cursos.html).
> >
> > > ⚠️ **Error típico.** Dos elementos con el mismo `id`. Cada `id` es único en la página.
>
> </details>

</details>

---

<details>
<summary><strong>🔗 Paso 4 — Enlaces, ancla y enlace externo</strong></summary>

> <details>
> <summary><strong>Paso 4.1 · Navegación entre páginas (RF-1.05)</strong></summary>
>
> > En **las tres páginas**, dentro de un `header`, el mismo bloque de navegación:
> >
> > ```html
> >     <nav>
> >       <a href="index.html">Inicio</a> |
> >       <a href="estudiantes.html">Estudiantes</a> |
> >       <a href="cursos.html">Cursos</a>
> >     </nav>
> > ```
> >
> > > ✅ **Punto de control.** Desde cualquier página se llega a las otras dos y se vuelve. Al estar todos los archivos en la misma carpeta, la ruta es solo el nombre.
>
> </details>
>
> <details>
> <summary><strong>Paso 4.2 · Anclas (RF-1.06)</strong></summary>
>
> > 1. En `cursos.html`, bajo la navegación: `<p>Ir a: <a href="#java">Java</a> · <a href="#web">HTML y CSS</a> · <a href="#git">Git</a></p>`.
> > 2. En `estudiantes.html`, en cada estudiante, la línea de cursos enlaza **a otra página y a un punto de ella**:
> >    `<p>Cursos: <a href="cursos.html#java">Java desde cero</a></p>`.
> > 3. En los `footer`: `<a href="#">Volver arriba</a>`.
> >
> > > 🧠 **Para preguntar:** ¿qué diferencia hay entre `#java` y `cursos.html#java`? *(El primero busca en la página actual; el segundo abre la otra página y baja al `id`.)*
>
> </details>
>
> <details>
> <summary><strong>Paso 4.3 · Enlace externo (RF-1.07)</strong></summary>
>
> > En `index.html`:
> >
> > ```html
> >   <h2>Para saber más</h2>
> >   <p>La documentación oficial de HTML está en
> >   <a href="https://developer.mozilla.org/es/docs/Web/HTML" target="_blank" rel="noopener">MDN Web Docs</a>.</p>
> > ```
> >
> > `target="_blank"` abre otra pestaña; `rel="noopener"` evita que la pestaña nueva controle a la de origen.
>
> </details>

</details>

---

<details>
<summary><strong>🖼️ Paso 5 — Imagen y video</strong></summary>

> <details>
> <summary><strong>Paso 5.1 · El logo (RF-1.02)</strong></summary>
>
> > Al principio del `body` de `index.html`:
> >
> > ```html
> >   <img src="imagenes/logo.svg" alt="Logo de la Academia de programación" width="240" height="80">
> > ```
> >
> > > 💡 **`alt`** es lo que lee un lector de pantalla y lo que se muestra si el archivo no carga. Para comprobarlo, se cambia `logo.svg` por `logo-roto.svg` y se mira la página; luego se vuelve atrás.
>
> </details>
>
> <details>
> <summary><strong>Paso 5.2 · El video (RF-1.01)</strong></summary>
>
> > ```html
> >   <h2>Recorrido en video</h2>
> >   <video src="video/recorrido.mp4" controls width="480">
> >     Tu navegador no reproduce video.
> >   </video>
> > ```
> >
> > > ⚠️ **Error típico.** Sin `controls` el video no tiene botón de reproducir y parece una imagen.
>
> </details>

</details>

---

<details>
<summary><strong>🏛️ Paso 6 — Semántica y revisión final</strong></summary>

> <details>
> <summary><strong>Paso 6.1 · Reorganizar con etiquetas semánticas (RA-7)</strong></summary>
>
> > Se revisa cada página y se agrupa su contenido así:
> >
> > | Zona | Etiqueta | Qué lleva |
> > |---|---|---|
> > | Cabecera | `header` | logo, `h1` y `nav` |
> > | Contenido principal | `main` | **uno solo** por página |
> > | Temas | `section` / `article` | cursos / estudiantes |
> > | Pie | `footer` | aviso de datos inventados y «Volver arriba» |
> >
> > Se pide a los estudiantes que **comparen** su `index.html` con [la versión terminada](codigo/academia-m01/index.html) y expliquen en voz alta por qué cada bloque tiene esa etiqueta.
> >
> > > 🧠 **Para preguntar:** si en `estudiantes.html` solo quisiera agrupar tres párrafos sin significado propio, ¿qué etiqueta usaría? *(Un `div`, y se deja un comentario que lo explique.)*
>
> </details>
>
> <details>
> <summary><strong>Paso 6.2 · Lista de verificación</strong></summary>
>
> > - [ ] Las tres páginas abren sin errores y cada una tiene su `title`.
> > - [ ] La navegación funciona en ambos sentidos.
> > - [ ] Las tres anclas de `cursos.html` saltan al curso correcto.
> > - [ ] El logo se ve, tiene `alt` y el video se reproduce.
> > - [ ] El enlace externo abre una pestaña nueva.
> > - [ ] Hay al menos dos comentarios y ningún `id` repetido.
> > - [ ] No hay CSS ni JavaScript.
> >
> > **Verificación automática (docente):**
> >
> > ```bash
> > python3 herramientas/validar_html.py curso-html-css/guias/codigo/academia-m01
> > # 3 archivo(s), 0 error(es)
> > ```
>
> </details>

</details>

---

<details>
<summary><strong>🅱️ PARTE 2 — Módulo 02: HTML para presentación (Pasos 7 a 13)</strong></summary>

> Se parte del proyecto terminado en la Parte 1. Carpeta de trabajo: `academia-m02`. Resultado: [`codigo/academia-m02/`](codigo/academia-m02/).

</details>

---


<details>
<summary><strong>🚀 Paso 7 — Punto de partida de la Parte 2</strong></summary>

> <details>
> <summary><strong>Paso 7.1 · El proyecto</strong></summary>
>
> > Se copia la carpeta terminada de la Parte 1 como `academia-m02` y se agrega al `nav` de **todas** las páginas el enlace nuevo:
> >
> > ```html
> >     <nav>
> >       <a href="index.html">Inicio</a> |
> >       <a href="estudiantes.html">Estudiantes</a> |
> >       <a href="cursos.html">Cursos</a> |
> >       <a href="matricula.html">Matricular</a>
> >     </nav>
> > ```
> >
> > > ⚠️ El enlace a `matricula.html` queda roto hasta el Paso 11; es normal y sirve para ver cómo falla un enlace.
> > > Para simplificar la carpeta se quita el video de `index.html` y las anclas de `estudiantes.html` pasan a `cursos.html#cursos`.
>
> </details>

</details>

---

<details>
<summary><strong>📊 Paso 8 — Tabla de estudiantes (RF-2.01)</strong></summary>

> <details>
> <summary><strong>Paso 8.1 · Del `article` a la tabla</strong></summary>
>
> > 🗣️ **Se pregunta:** ¿qué tienen en común Ana, Luis y Marta? *(Los mismos campos.)* Datos con las mismas columnas piden una tabla.
> >
> > <details>
> > <summary><strong>📄 estudiantes.html</strong> <em>(reemplaza el contenido de `main`)</em></summary>
> >
> > ```html
> >   <main>
> >     <p>Cada estudiante tiene un <strong>nombre</strong>, una <strong>edad</strong> y un <strong>correo</strong> único.</p>
> >
> >     <hr>
> >
> >     <table>
> >       <caption>Estudiantes matriculados</caption>
> >       <thead>
> >         <tr>
> >           <th>Nombre</th>
> >           <th>Edad</th>
> >           <th>Correo</th>
> >           <th>Cursos</th>
> >         </tr>
> >       </thead>
> >       <tbody>
> >         <tr>
> >           <td>Ana Pérez</td>
> >           <td>24</td>
> >           <td><a href="mailto:ana@academia.test">ana@academia.test</a></td>
> >           <td>1</td>
> >         </tr>
> >         <!-- Luis Gómez (31, luis@academia.test, 2) y Marta Ruiz (19, marta@academia.test, 1) -->
> >       </tbody>
> >       <tfoot>
> >         <tr>
> >           <td colspan="4">Datos inventados. Un estudiante puede estar en varios cursos.</td>
> >         </tr>
> >       </tfoot>
> >     </table>
> >   </main>
> > ```
> >
> > </details>
> >
> > | Pieza | Para qué |
> > |---|---|
> > | `caption` | Título de la tabla |
> > | `thead` / `th` | Encabezados |
> > | `tbody` / `td` | Filas de datos |
> > | `tfoot` + `colspan="4"` | Nota que ocupa **las cuatro** columnas |
> >
> > Se completan las filas de Luis y Marta ([código final](codigo/academia-m02/estudiantes.html)).
> >
> > > ⚠️ **Error típico.** Una fila con tres `td` en una tabla de cuatro columnas: la tabla se «descuadra». Se cuenta por fila.
>
> </details>

</details>

---

<details>
<summary><strong>📚 Paso 9 — Cursos: listas, separadores y tabla (RF-2.02, RF-2.03, RF-2.06)</strong></summary>

> <details>
> <summary><strong>Paso 9.1 · Oferta con sublista</strong></summary>
>
> > En `cursos.html` se reemplazan las tres `section` de la Parte 1 por:
> >
> > ```html
> >     <section id="cursos">
> >       <h2>Oferta de cursos</h2>
> >       <ul>
> >         <li>Java desde cero
> >           <ul>
> >             <li>Variables y condicionales</li>
> >             <li>Ciclos y clases</li>
> >           </ul>
> >         </li>
> >         <li>HTML y CSS</li>
> >         <li>Git</li>
> >       </ul>
> >     </section>
> >
> >     <hr>
> > ```
> >
> > > 💡 **Regla.** La sublista va **dentro** del `li` al que pertenece, no como hermana del `li`.
>
> </details>
>
> <details>
> <summary><strong>Paso 9.2 · Precios y cupos</strong></summary>
>
> > ```html
> >     <section>
> >       <h2>Precios y cupos</h2>
> >       <table>
> >         <caption>Cursos de la Academia</caption>
> >         <thead>
> >           <tr><th>Curso</th><th>Precio</th><th>Cupo máximo</th></tr>
> >         </thead>
> >         <tbody>
> >           <tr><td>Java desde cero</td><td>$180.000</td><td>20</td></tr>
> >           <tr><td>HTML y CSS</td><td>$150.000</td><td>25</td></tr>
> >           <tr><td>Git</td><td>$90.000</td><td>30</td></tr>
> >         </tbody>
> >         <tfoot>
> >           <tr><td colspan="3">Precios en pesos. El cupo máximo es el tope de matriculados.</td></tr>
> >         </tfoot>
> >       </table>
> >     </section>
> >
> >     <hr>
> > ```
> >
> > (En el [código final](codigo/academia-m02/cursos.html) cada celda va en su propia línea, igual que en el Paso 8.)
>
> </details>

</details>

---

<details>
<summary><strong>🗣️ Paso 10 — Pasos de matrícula y testimonio (RF-2.04, RF-2.05)</strong></summary>

> <details>
> <summary><strong>Paso 10.1 · Lista enumerada</strong></summary>
>
> > ```html
> >     <section>
> >       <h2>Cómo te matriculás</h2>
> >       <ol>
> >         <li>Elegí un curso de la tabla.</li>
> >         <li>Completá el <a href="matricula.html">formulario de matrícula</a>.</li>
> >         <li>Esperá la confirmación de la Academia.</li>
> >       </ol>
> >     </section>
> >
> >     <hr>
> > ```
> >
> > > 🧠 **Para preguntar:** ¿por qué acá `ol` y en la oferta `ul`? *(Los pasos tienen orden; los cursos no.)*
>
> </details>
>
> <details>
> <summary><strong>Paso 10.2 · Cita con fuente</strong></summary>
>
> > ```html
> >     <section>
> >       <h2>Lo que dicen</h2>
> >       <blockquote cite="https://academia.test/opiniones/ana">
> >         <p>Entré sin saber qué era una variable y salí armando mi primera página.</p>
> >       </blockquote>
> >       <p>— Ana Pérez, estudiante de Java desde cero</p>
> >     </section>
> > ```
> >
> > > ⚠️ **Error típico.** Poner el nombre de la persona dentro de `<cite>`: esa etiqueta es para el **título de una obra**. La atribución va fuera del `blockquote`, y la dirección de la fuente, en el atributo `cite`.
>
> </details>

</details>

---

<details>
<summary><strong>📝 Paso 11 — El formulario de matrícula (RF-2.07)</strong></summary>

> <details>
> <summary><strong>Paso 11.1 · De la API al formulario</strong></summary>
>
> > 🗣️ **Se conecta con el curso de Spring Boot:** la API recibe un `EnrollmentRequest` con quién y en qué curso. El formulario pide esos datos.
> >
> > | Campo del formulario | Tipo | `name` | Valor que viaja |
> > |---|---|---|---|
> > | Nombre | `text` | `nombre` | lo escrito |
> > | Correo | `email` | `correo` | lo escrito |
> > | Edad | `number` | `edad` | lo escrito |
> > | Curso | `radio` | `curso` | `java`, `web` o `git` |
> > | Reglamento | `checkbox` | `acepta` | `si` (solo si está marcada) |
> > | — | `submit` | — | — |
>
> </details>
>
> <details>
> <summary><strong>Paso 11.2 · Escribir la página</strong></summary>
>
> > Se crea `matricula.html` con la estructura de siempre y, dentro de `main`:
> >
> > ```html
> >     <p>Usá <strong>solo datos inventados</strong>: el formulario no se envía a ningún servidor.</p>
> >
> >     <form method="get">
> >       <p>
> >         <label for="nombre">Nombre:</label>
> >         <input type="text" id="nombre" name="nombre" value="Ana Pérez">
> >       </p>
> >       <p>
> >         <label for="correo">Correo:</label>
> >         <input type="email" id="correo" name="correo">
> >       </p>
> >       <p>
> >         <label for="edad">Edad:</label>
> >         <input type="number" id="edad" name="edad">
> >       </p>
> >
> >       <p>Curso:</p>
> >       <p>
> >         <input type="radio" id="java" name="curso" value="java">
> >         <label for="java">Java desde cero</label>
> >         <input type="radio" id="web" name="curso" value="web">
> >         <label for="web">HTML y CSS</label>
> >         <input type="radio" id="git" name="curso" value="git">
> >         <label for="git">Git</label>
> >       </p>
> >
> >       <p>
> >         <input type="checkbox" id="acepta" name="acepta" value="si">
> >         <label for="acepta">Acepto el reglamento de la Academia</label>
> >       </p>
> >
> >       <p><input type="submit" value="Matricular"></p>
> >     </form>
> > ```
> >
> > | Detalle | Por qué |
> > |---|---|
> > | `label for="x"` + `id="x"` | Al hacer clic en el texto se activa el campo |
> > | Los tres `radio` con el **mismo `name`** | Solo se elige uno |
> > | `value="Ana Pérez"` en el nombre | Valor inicial que se puede cambiar |
> > | Sin `action` | No sale ningún dato del equipo |
> >
> > Página completa: [`matricula.html`](codigo/academia-m02/matricula.html).
>
> </details>

</details>

---

<details>
<summary><strong>🧪 Paso 12 — Probar el formulario y leer la dirección</strong></summary>

> <details>
> <summary><strong>Paso 12.1 · Primer envío</strong></summary>
>
> > Se completa con `Luis Gómez`, `luis@academia.test`, `31`, curso **HTML y CSS**, reglamento **marcado**, y se pulsa **Matricular**. La barra de direcciones muestra algo como:
> >
> > ```text
> > matricula.html?nombre=Luis+G%C3%B3mez&correo=luis%40academia.test&edad=31&curso=web&acepta=si
> > ```
> >
> > | Parte | Significado |
> > |---|---|
> > | `?` | Aquí empiezan los datos |
> > | `nombre=…` | `name` del campo = valor |
> > | `&` | Separa un dato del siguiente |
> > | `+` y `%C3%B3` | Espacio y «ó» codificados para que viajen en la dirección |
> >
> > > 📝 Los estudiantes **anotan la dirección**: es parte del entregable.
>
> </details>
>
> <details>
> <summary><strong>Paso 12.2 · Segundo envío, sin marcar la casilla</strong></summary>
>
> > Se repite sin marcar el reglamento. La dirección queda **sin** `&acepta=si`.
> >
> > > 🧠 **Para preguntar:** ¿por qué falta ese dato? *(Una casilla desmarcada no envía nada: el navegador solo manda los campos activos. Lo mismo pasa con un `radio` sin elegir.)*
> >
> > ```text
> > matricula.html?nombre=Luis+G%C3%B3mez&correo=luis%40academia.test&edad=31&curso=web
> > ```
> >
> > Esto es justo lo que la API tendrá que **validar** más adelante: que no llegue una matrícula sin aceptar el reglamento.
>
> </details>

</details>

---

<details>
<summary><strong>✅ Paso 13 — Revisión final</strong></summary>

> <details>
> <summary><strong>Paso 13.1 · Lista de verificación</strong></summary>
>
> > - [ ] Las dos tablas tienen `caption`, `thead`, `tbody` y `tfoot`, y el `colspan` coincide con el número de columnas.
> > - [ ] La sublista está **dentro** de un `li`.
> > - [ ] Hay una lista enumerada y los temas de `cursos.html` están separados con `hr`.
> > - [ ] El `blockquote` tiene `cite` y la atribución está fuera.
> > - [ ] El formulario usa `method="get"`, sin `action`, con cinco tipos de campo.
> > - [ ] Cada `label for` coincide con un `id`; cada campo tiene `name`.
> > - [ ] Las dos direcciones están anotadas y la explicación del Paso 12.2 es correcta.
> > - [ ] No hay CSS ni JavaScript.
> >
> > **Verificación automática (docente):**
> >
> > ```bash
> > python3 herramientas/validar_html.py curso-html-css/guias/codigo/academia-m02
> > # 4 archivo(s), 0 error(es)
> > ```
>
> </details>

</details>

---

<details>
<summary><strong>🚧 Errores frecuentes y cómo se ven</strong></summary>

> | Síntoma | Causa probable | Arreglo |
> |---|---|---|
> | «Pérez» se ve «PÃ©rez» | Falta `<meta charset="UTF-8">` o el archivo no está en UTF-8 | Agregarlo y guardar en UTF-8 |
> | Todo aparece en un párrafo | Faltan `</p>` o hay una etiqueta sin cerrar | Revisar el cierre de cada etiqueta |
> | El enlace «no hace nada» | Mayúsculas o nombre mal escrito en `href` | Copiar el nombre exacto del archivo |
> | El ancla no baja | El `id` no coincide con el `#` | Comparar letra por letra |
> | La imagen no se ve | Ruta equivocada | Revisar `imagenes/logo.svg` y las mayúsculas |
> | La tabla se ve corrida | Filas con distinta cantidad de celdas | Contar `td` por fila; ajustar `colspan` |
> | La sublista sale al nivel de la principal | `ul` hija fuera del `li` | Moverla dentro del `li` |
> | Se pueden marcar los tres cursos | Los `radio` tienen `name` distinto | Mismo `name` en los tres |
> | Hacer clic en el texto no activa el campo | `for` e `id` no coinciden | Igualarlos |
> | La dirección no trae un campo | Falta su `name` o la casilla no está marcada | Revisar `name` y el estado |
> | El enlace «Matricular» da error | Falta `matricula.html` | Crear el archivo en la misma carpeta |

</details>

<details>
<summary><strong>🔭 Qué sigue</strong></summary>

> En el Módulo 03 el mismo portal recibe su **primer CSS**, sin cambiar el HTML. Los datos de esta guía (tablas y formulario) son los que se estilizarán en los módulos 04 y 05.

</details>

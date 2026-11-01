# 🧭 Guía paso a paso — Portal de la Academia (Módulo 01: Fundamentos HTML)

> 👩‍🏫 **Material docente.** Guía para construir **junto con los estudiantes**, en vivo, el frente web del **sistema académico** del curso de Spring Boot (**estudiantes**, **cursos** y **matrículas**), aplicando lo visto en el [Módulo 01](../../material/ejemplos/explicacion-conceptual.md).
> Contiene código completo: no se entrega a los estudiantes antes de resolver el taller.
>
> 📦 **Proyecto terminado:** [`academia-m01/`](codigo/academia-m01/) · 🔗 **Es el mismo sistema** de la [guía de la Academia del curso de Spring Boot](../../../../../../curso-spring-boot/generador-cursos/curso-spring-boot/guias/modulo-03-diseno-api-rest-con-dto/02-academica-dtos.md): allí se construye la API; aquí, las páginas que más adelante la van a consumir.
>
> ✅ **Verificada.** Las tres páginas pasan el validador de HTML del curso (`herramientas/validar_html.py`) sin errores.
>
> 🧭 **Idea central.** Cada requerimiento del sistema académico se traduce en **una pieza de HTML** del módulo: la estructura en `index.html`, los datos de las entidades en texto marcado, la navegación en enlaces y anclas, y la organización en etiquetas semánticas.

<details>
<summary><strong>🎯 Objetivo</strong></summary>

> Construir un sitio de **tres páginas** (`index.html`, `estudiantes.html`, `cursos.html`) que muestre la información de la academia, **sin CSS ni JavaScript**.
>
> Al terminar, el estudiante:
>
> - Prepara el entorno y abre una página en el navegador (RA-2).
> - Escribe la **estructura mínima** de cada documento (RA-3).
> - Marca texto con significado y deja **comentarios** (RA-4).
> - Conecta las páginas con **enlaces**, una dirección externa y **anclas** (RA-5).
> - Incorpora una **imagen** con `alt` y un **video** con controles (RA-6).
> - Reorganiza con **etiquetas semánticas** (`header`, `nav`, `main`, `section`, `article`, `footer`) y sabe cuándo bastaría un `div` (RA-7).

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
> | Entidad (API) | Atributos | Dónde aparece en el portal |
> |---|---|---|
> | **Estudiante** | `name`, `age`, `email` | `estudiantes.html`: un `article` por persona |
> | **Curso** | `name`, `price`, `maxCapacity` | `cursos.html`: una `section` por curso |
> | **Matrícula** | estudiante + curso | Enlaces del estudiante a sus cursos (se forma en el Módulo 02) |
>
> <details>
> <summary><strong>✅ Requerimientos funcionales</strong></summary>
>
> >
> > | Código | Requerimiento | Página | Contenido del módulo |
> > |---|---|---|---|
> > | **RF-01** | Presentar la academia con una bienvenida y un video. | `index.html` | Estructura, formato de texto, video |
> > | **RF-02** | Mostrar el logo con texto alternativo. | `index.html` | Imagen y `alt` |
> > | **RF-03** | Listar los estudiantes con nombre, edad y correo. | `estudiantes.html` | Títulos, párrafos, enlace `mailto:` |
> > | **RF-04** | Listar los cursos con precio y cupo máximo. | `cursos.html` | `section` con `id` |
> > | **RF-05** | Navegar entre las tres páginas desde cualquiera. | las tres | Enlaces relativos |
> > | **RF-06** | Saltar a un curso desde la misma página o desde un estudiante. | `cursos.html`, `estudiantes.html` | Anclas y fragmentos |
> > | **RF-07** | Remitir a la documentación oficial en una pestaña nueva. | `index.html` | Enlace externo |
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
> > | **RNF-05** | **Solo datos inventados** (correos `@academia.test`). |
> > | **RNF-06** | Duración: 1 h 30 min, trabajo individual o en parejas, con VS Code y un navegador. |
> >
> > > 💡 **Alcance.** Quedan fuera: tablas, listas con sublistas y formularios (Módulo 02), y todo el estilo (Módulo 03 en adelante).
>
> </details>

</details>

<details>
<summary><strong>⏱️ Plan de la sesión</strong></summary>

> | Paso | Minutos | Actividad |
> |---|---:|---|
> | 0 | 0 – 10 | Entorno: carpeta, VS Code y navegador |
> | 1 | 10 – 25 | La primera página: estructura mínima (`index.html`) |
> | 2 | 25 – 40 | Texto con significado y comentarios |
> | 3 | 40 – 55 | Las páginas de datos: `estudiantes.html` y `cursos.html` |
> | 4 | 55 – 70 | Enlaces, ancla y enlace externo |
> | 5 | 70 – 80 | Imagen y video |
> | 6 | 80 – 90 | Semántica y revisión final |
>
> > 💡 **Ritmo.** Después de cada paso se guarda y se **recarga el navegador** (`F5`). Quien no ve el cambio, revisa la etiqueta que acaba de escribir.

</details>

<details>
<summary><strong>🏗️ Arquitectura: el árbol de archivos (🆕 nuevo)</strong></summary>

> ```text
> 📁 academia-m01
> ├── 🆕 index.html          bienvenida · logo · video · enlace externo
> ├── 🆕 estudiantes.html    un article por estudiante
> ├── 🆕 cursos.html         una section por curso, con id
> ├── 📁 imagenes
> │   └── 🆕 logo.svg
> └── 📁 video
>     └── 🆕 recorrido.mp4
> ```

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
> <summary><strong>Paso 2.1 · La bienvenida (RF-01)</strong></summary>
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
> <summary><strong>Paso 3.1 · Estudiantes (RF-03)</strong></summary>
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
> <summary><strong>Paso 3.2 · Cursos (RF-04)</strong></summary>
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
> <summary><strong>Paso 4.1 · Navegación entre páginas (RF-05)</strong></summary>
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
> <summary><strong>Paso 4.2 · Anclas (RF-06)</strong></summary>
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
> <summary><strong>Paso 4.3 · Enlace externo (RF-07)</strong></summary>
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
> <summary><strong>Paso 5.1 · El logo (RF-02)</strong></summary>
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
> <summary><strong>Paso 5.2 · El video (RF-01)</strong></summary>
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
> > python3 herramientas/validar_html.py curso-html-css/01-Fundamentos-HTML/actividades/guias/codigo
> > # 3 archivo(s), 0 error(es)
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

</details>

<details>
<summary><strong>🔭 Qué sigue</strong></summary>

> En el [Módulo 02](../../../02-HTML-para-presentacion/actividades/guias/guia-academia-modulo-02.md) el mismo portal incorpora **listas, tablas, una cita y el formulario de matrícula**. El código de partida es el que se acaba de terminar.

</details>

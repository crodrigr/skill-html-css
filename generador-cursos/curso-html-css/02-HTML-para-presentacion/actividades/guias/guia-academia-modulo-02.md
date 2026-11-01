# 🧭 Guía paso a paso — Portal de la Academia (Módulo 02: HTML para presentación)

> 👩‍🏫 **Material docente.** Guía para construir **junto con los estudiantes**, en vivo, la segunda versión del portal del **sistema académico** (**estudiantes**, **cursos** y **matrículas**), aplicando lo visto en el [Módulo 02](../../material/ejemplos/explicacion-conceptual.md).
> Parte del [portal del Módulo 01](../../../01-Fundamentos-HTML/actividades/guias/guia-academia-modulo-01.md). Contiene código completo: no se entrega a los estudiantes antes de resolver el taller.
>
> 📦 **Proyecto terminado:** [`academia-m02/`](codigo/academia-m02/) · 🔗 **Mismo sistema** que la [guía de la Academia del curso de Spring Boot](../../../../../../curso-spring-boot/generador-cursos/curso-spring-boot/guias/modulo-03-diseno-api-rest-con-dto/02-academica-dtos.md): el formulario de matrícula refleja el `EnrollmentRequest` de la API.
>
> ✅ **Verificada.** Las cuatro páginas pasan el validador de HTML del curso (`herramientas/validar_html.py`) sin errores.
>
> 🧭 **Idea central.** Los datos de la academia tienen **forma de tabla** (estudiantes y cursos), **de lista** (oferta y pasos) y **de formulario** (la matrícula). Se elige la etiqueta según la forma del dato.

<details>
<summary><strong>🎯 Objetivo</strong></summary>

> Ampliar el portal con **listas, separadores, tablas, una cita y un formulario**, **sin CSS ni JavaScript**.
>
> Al terminar, el estudiante:
>
> - Separa los temas con `hr` (RA-1).
> - Presenta datos en una **tabla completa**: `caption`, `thead`, `tbody`, `tfoot` y `colspan` (RA-2).
> - Escribe una lista no enumerada con **sublista** y una lista enumerada (RA-3).
> - Marca un testimonio con `blockquote` y `cite` (RA-4).
> - Escribe un **formulario** `method="get"` con cinco tipos de campo, `label`, `name` y `value` (RA-5 y RA-6).
> - Lee la **dirección** que genera el envío y explica qué datos viajan.

</details>

<details>
<summary><strong>📝 Introducción: qué cambia respecto al Módulo 01</strong></summary>

> <details>
> <summary><strong>🔁 Lo que se repite</strong></summary>
>
> | Pieza | Igual que en el Módulo 01 |
> |---|---|
> | Estructura mínima | `DOCTYPE`, `html lang`, `head` con `charset` y `title` |
> | Semántica | `header`, `nav`, `main`, `section`, `footer` en cada página |
> | Navegación | Mismo `nav`, ahora con un enlace más |
>
> </details>
>
> <details>
> <summary><strong>🆕 Lo que es nuevo en el portal</strong></summary>
>
> | Novedad | Por qué importa |
> |---|---|
> | **Tabla de estudiantes** | Reemplaza los `article`: son datos con las mismas columnas (`name`, `age`, `email`). |
> | **Tabla de cursos** | `name`, `price`, `maxCapacity`; el pie aclara qué es el cupo. |
> | **Listas** | La oferta de cursos (con sublista) y los pasos de matrícula (con orden). |
> | **Cita** | Un testimonio con su fuente. |
> | **Formulario `matricula.html`** | Es la pantalla de `POST /enrollments`: pide quién y en qué curso. |
>
> </details>
>
> <details>
> <summary><strong>🔍 Cuál etiqueta para cuál dato</strong></summary>
>
> | El dato es… | Etiqueta | Ejemplo en el portal |
> |---|---|---|
> | Filas y columnas con el mismo significado | `table` | Estudiantes, cursos |
> | Elementos sin orden | `ul` + `li` | Oferta de cursos |
> | Pasos con orden | `ol` + `li` | Cómo te matriculás |
> | Palabras de otra fuente | `blockquote` | Testimonio |
> | Datos que escribe el usuario | `form` + `input` | Matrícula |
>
> </details>
>
> <details>
> <summary><strong>✅ Requerimientos funcionales</strong></summary>
>
> >
> > | Código | Requerimiento | Página | Contenido del módulo |
> > |---|---|---|---|
> > | **RF-01** | Mostrar los estudiantes en una tabla con nombre, edad, correo y número de cursos. | `estudiantes.html` | Tabla |
> > | **RF-02** | Mostrar los cursos con precio y cupo máximo, y una nota al pie. | `cursos.html` | Tabla con `tfoot` y `colspan` |
> > | **RF-03** | Listar la oferta de cursos, con los temas de Java como sublista. | `cursos.html` | `ul` anidada |
> > | **RF-04** | Explicar la matrícula en tres pasos. | `cursos.html` | `ol` |
> > | **RF-05** | Mostrar un testimonio con su fuente. | `cursos.html` | `blockquote`, `cite` |
> > | **RF-06** | Separar los temas de la página. | `cursos.html`, `estudiantes.html` | `hr` |
> > | **RF-07** | Pedir nombre, correo, edad, curso y aceptación del reglamento. | `matricula.html` | `form`, `input` |
> >
> </details>
>
> <details>
> <summary><strong>🛠️ Requerimientos no funcionales y restricciones</strong></summary>
>
> >
> > | Código | Requerimiento |
> > |---|---|
> > | **RNF-01** | Solo HTML. **Sin CSS ni JavaScript.** |
> > | **RNF-02** | Tipos de `input` permitidos: `text`, `email`, `number`, `radio`, `checkbox` y `submit`. |
> > | **RNF-03** | Formulario con `method="get"` y **sin `action`**: ningún dato sale del equipo. |
> > | **RNF-04** | Cada `label for` coincide con un `id`; cada campo (salvo `submit`) lleva `name`; `radio` y `checkbox` llevan `value`. |
> > | **RNF-05** | Las tablas son para **datos**, no para armar el diseño. |
> > | **RNF-06** | **Solo datos inventados.** |
> > | **RNF-07** | Duración: 1 h 30 min, trabajo individual o en parejas. |
> >
> > > 💡 **Alcance.** Quedan fuera: selector, área de texto, validación avanzada y envío a un servidor. Cuando el portal use JavaScript, el formulario se enviará a la API.
>
> </details>

</details>

<details>
<summary><strong>⏱️ Plan de la sesión</strong></summary>

> | Paso | Minutos | Actividad |
> |---|---:|---|
> | 0 | 0 – 10 | Punto de partida: el portal del Módulo 01 |
> | 1 | 10 – 25 | Tabla de estudiantes (`thead`, `tbody`, `tfoot`) |
> | 2 | 25 – 40 | Cursos: listas, separadores y tabla |
> | 3 | 40 – 48 | Pasos de matrícula y testimonio |
> | 4 | 48 – 65 | El formulario de matrícula |
> | 5 | 65 – 80 | Probar el formulario y leer la dirección |
> | 6 | 80 – 90 | Revisión final |
>
> > 💡 **Ritmo.** El Paso 0 es el proyecto ya terminado del Módulo 01; el tiempo se dedica a los Pasos 1 a 6.

</details>

<details>
<summary><strong>🏗️ Arquitectura: el árbol de archivos (🆕 nuevo · ✏️ cambia)</strong></summary>

> ```text
> 📁 academia-m02
> ├── ✏️ index.html          nav con «Matricular»; sin video
> ├── ✏️ estudiantes.html    article → tabla
> ├── ✏️ cursos.html         + listas · hr · tabla · cita
> ├── 🆕 matricula.html      formulario GET
> └── 📁 imagenes
>     └── logo.svg
> ```

</details>

---

<details>
<summary><strong>🚀 Paso 0 — Punto de partida</strong></summary>

> <details>
> <summary><strong>Paso 0.1 · El proyecto</strong></summary>
>
> > Se copia la carpeta terminada del Módulo 01 como `academia-m02` y se agrega al `nav` de **todas** las páginas el enlace nuevo:
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
> > > ⚠️ El enlace a `matricula.html` queda roto hasta el Paso 4; es normal y sirve para ver cómo falla un enlace.
> > > Para simplificar la carpeta se quita el video de `index.html` y las anclas de `estudiantes.html` pasan a `cursos.html#cursos`.
>
> </details>

</details>

---

<details>
<summary><strong>📊 Paso 1 — Tabla de estudiantes (RF-01)</strong></summary>

> <details>
> <summary><strong>Paso 1.1 · Del `article` a la tabla</strong></summary>
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
<summary><strong>📚 Paso 2 — Cursos: listas, separadores y tabla (RF-02, RF-03, RF-06)</strong></summary>

> <details>
> <summary><strong>Paso 2.1 · Oferta con sublista</strong></summary>
>
> > En `cursos.html` se reemplazan las tres `section` del Módulo 01 por:
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
> <summary><strong>Paso 2.2 · Precios y cupos</strong></summary>
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
> > (En el [código final](codigo/academia-m02/cursos.html) cada celda va en su propia línea, igual que en el Paso 1.)
>
> </details>

</details>

---

<details>
<summary><strong>🗣️ Paso 3 — Pasos de matrícula y testimonio (RF-04, RF-05)</strong></summary>

> <details>
> <summary><strong>Paso 3.1 · Lista enumerada</strong></summary>
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
> <summary><strong>Paso 3.2 · Cita con fuente</strong></summary>
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
<summary><strong>📝 Paso 4 — El formulario de matrícula (RF-07)</strong></summary>

> <details>
> <summary><strong>Paso 4.1 · De la API al formulario</strong></summary>
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
> <summary><strong>Paso 4.2 · Escribir la página</strong></summary>
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
<summary><strong>🧪 Paso 5 — Probar el formulario y leer la dirección</strong></summary>

> <details>
> <summary><strong>Paso 5.1 · Primer envío</strong></summary>
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
> <summary><strong>Paso 5.2 · Segundo envío, sin marcar la casilla</strong></summary>
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
<summary><strong>✅ Paso 6 — Revisión final</strong></summary>

> <details>
> <summary><strong>Paso 6.1 · Lista de verificación</strong></summary>
>
> > - [ ] Las dos tablas tienen `caption`, `thead`, `tbody` y `tfoot`, y el `colspan` coincide con el número de columnas.
> > - [ ] La sublista está **dentro** de un `li`.
> > - [ ] Hay una lista enumerada y los temas de `cursos.html` están separados con `hr`.
> > - [ ] El `blockquote` tiene `cite` y la atribución está fuera.
> > - [ ] El formulario usa `method="get"`, sin `action`, con cinco tipos de campo.
> > - [ ] Cada `label for` coincide con un `id`; cada campo tiene `name`.
> > - [ ] Las dos direcciones están anotadas y la explicación del Paso 5.2 es correcta.
> > - [ ] No hay CSS ni JavaScript.
> >
> > **Verificación automática (docente):**
> >
> > ```bash
> > python3 herramientas/validar_html.py curso-html-css/02-HTML-para-presentacion/actividades/guias/codigo
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

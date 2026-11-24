# 📝 Examen 1 — Talleres y eventos de Café Altiplano

> 🎓 **Evaluación de las Unidades 01 a 07.** Sobre tu **proyecto final de Café Altiplano**, vas a agregar una **página nueva**: `talleres.html`. Se evalúa que apliques lo aprendido por tu cuenta, en una situación nueva y en poco tiempo.

## 🧭 Resumen

| | |
|---|---|
| **Examen** | 1 de 3 · **Talleres y eventos** |
| **Qué agregás** | Una página nueva, `talleres.html`, integrada al sitio |
| **Punto de partida** | Tu **proyecto final** (4 páginas + hojas de estilo) en su repositorio. No se empieza de cero |
| **Unidades que evalúa** | 01 a 07, con más peso en **02** (tabla y formulario) y **07** (Grid y galería) |
| **Tiempo** | **3 horas en total**, en una sola sesión de clase. Incluyen el `README`, la entrega y la sustentación |
| **Modalidad** | Individual |
| **Entrega** | **Enlace del repositorio** de tu proyecto final, con la nueva implementación en la rama `examen-01` |
| **Herramientas** | Editor de código y navegador con sus herramientas para desarrolladores. **Solo HTML y CSS** |
| **Consulta** | Tus apuntes, las guías y MDN. Sin copiar código de otra persona ni de una IA sin entenderlo: se pide explicarlo en la sustentación |

## 🏪 El encargo

**Café Altiplano** quiere abrir sus puertas a la comunidad con **talleres mensuales** (catas, latte art, filtrados…). Pide una página que:

- muestre la **agenda** de talleres con fecha, sede, duración, cupos y precio,
- presente cada taller en una **tarjeta**,
- explique **cómo inscribirse** y qué incluye cada taller,
- permita **inscribirse** con un formulario,
- y se lea bien en un **teléfono**, una **tableta** y un **computador**.

Los textos y datos están abajo. **Tu trabajo es la estructura, el estilo y la adaptación.** Todos los datos son inventados.

## 📚 Contenido de la página

### 🧾 Introducción

> Cada mes abrimos nuestras sedes para aprender sobre café: desde probar sin ver la etiqueta hasta dibujar corazones en la espuma. Los cupos son limitados.

### 🗓️ Agenda (tabla)

| Fecha | Taller | Sede | Duración | Cupos | Precio |
|---|---|---|---|---:|---:|
| 7 de marzo | Cata a ciegas | Centro | 2 h | 12 | $ 18 |
| 14 de marzo | Latte art para principiantes | Norte | 3 h | 8 | $ 35 |
| 21 de marzo | Métodos de filtrado en casa | Centro | 2 h | 15 | $ 22 |
| 28 de marzo | Del grano a la taza: tueste y origen | Sur | 3 h | 10 | $ 40 |
| 4 de abril | Café y repostería: maridaje | Norte | 2 h | 12 | $ 28 |

### 🃏 Tarjetas (galería de 6)

| Taller | Descripción | Nivel |
|---|---|---|
| Cata a ciegas | Reconocé aromas y sabores sin ver la etiqueta. | Básico |
| Latte art para principiantes | Primeros dibujos en la espuma: corazón y hoja. | Básico |
| Métodos de filtrado en casa | Prensa, filtro y moka: cuándo usar cada uno. | Intermedio |
| Del grano a la taza | Cómo el tueste y el origen cambian el sabor. | Intermedio |
| Café y repostería | Combinaciones que se potencian. | Básico |
| Pequeños baristas | Taller para niñas y niños de 8 a 12 años, con un adulto. | Básico |

### 🪜 Cómo inscribirte (lista **ordenada**)

1. Elegí el taller y la fecha.
2. Completá el formulario de esta página.
3. Recibirás la confirmación por correo en 24 horas.
4. Presentate 10 minutos antes en la sede.

### ✅ Qué incluye cada taller (lista **sin orden**)

- Todos los materiales
- Degustación de tres cafés
- Certificado de participación
- 10 % de descuento en la carta ese día

### 🎚️ Niveles (lista de **definición**)

- **Básico**: no requiere experiencia previa.
- **Intermedio**: conviene haber asistido a un taller básico.

### ✍️ Formulario de inscripción

Campos: nombre completo · correo · taller (lista desplegable con los 5 de la agenda) · nivel (opciones: Básico / Intermedio) · número de acompañantes (0 a 3) · casilla «Quiero recibir recordatorios» · comentarios (texto largo). Botón **Inscribirme**.

## 📋 Requerimientos

### 🧱 Unidad 01 — Estructura

| Código | Requerimiento |
|---|---|
| **E1-RF-01** | `talleres.html` con `<!DOCTYPE html>`, `lang="es"`, `charset`, `viewport`, un `<title>` propio, estructura semántica (`header`, `nav`, `main`, `section`, `footer`), **un solo `h1`** y títulos en orden. |
| **E1-RF-02** | El **menú** incluye el enlace **Talleres** en las **cinco** páginas y funciona. En `talleres.html` se distingue la **página actual**. |
| **E1-RF-03** | Al menos una imagen con `alt` útil dentro de `figure` con `figcaption`, y comentarios HTML que separan las partes de la página. |

### 📝 Unidad 02 — Datos y formulario

| Código | Requerimiento |
|---|---|
| **E1-RF-04** | La **agenda** es una `table` con `caption`, `thead`, `tbody` y `th` con `scope`. |
| **E1-RF-05** | La lista **ordenada** (`ol`), la **sin orden** (`ul`) y la de **definición** (`dl`) con el contenido indicado. |
| **E1-RF-06** | **Formulario** con `fieldset` y `legend`; cada campo con `label for`; un `select`, un grupo de `radio`, un campo `number` (mín. 0, máx. 3), un `checkbox` y un `textarea`; campos `required` y `placeholder`. |

### 🎨 Unidad 03 — Introducción a CSS

| Código | Requerimiento |
|---|---|
| **E1-RF-07** | Todo el estilo en **hojas externas** (las que ya tenés, por tema; o una `talleres.css` enlazada solo en la página nueva). Cero `style=""` y cero `<style>`. |
| **E1-RF-08** | **Ningún color suelto**: todos salen de variables de `:root` (si necesitás uno nuevo, lo agregás ahí). |
| **E1-RF-09** | La portada de la página usa un **gradiente** o una **imagen de fondo**, y hay un color con **transparencia** (`rgba` u `opacity`). |

### 🎯 Unidad 04 — Selectores y reglas

| Código | Requerimiento |
|---|---|
| **E1-RF-10** | Clases **BEM** para lo nuevo (por ejemplo `taller__titulo`, `taller--destacado`). |
| **E1-RF-11** | Al menos **un** selector de atributo, **un** combinador, **un** selector lógico (`:is()`, `:not()` o `:has()`) y **`:nth-child()`** para las filas alternas de la agenda. |
| **E1-RF-12** | `:hover` y `:focus` visibles en el menú, el botón y los campos. Sin `!important` ni `id` para dar estilo. |

### 🔤 Unidad 05 — Tipografía, datos y cajas

| Código | Requerimiento |
|---|---|
| **E1-RF-13** | La **agenda** se lee bien: bordes colapsados, relleno, **precio y cupos a la derecha**, filas alternas, dentro de un contenedor con `overflow-x: auto` para que no rompa la página a 500 px. |
| **E1-RF-14** | Las **tarjetas** tienen borde, esquinas redondeadas, relleno y margen coherentes. Jerarquía tipográfica clara y `line-height` cómodo. |

### 📏 Unidad 06 — Unidades relativas

| Código | Requerimiento |
|---|---|
| **E1-RF-15** | Letras en **`rem`** (ninguna en `px`); espacios y anchos máximos en `rem`; `px` solo en bordes. |
| **E1-RF-16** | `ch` en el ancho de lectura de los párrafos, un `%` y un `vh` (por ejemplo, la altura mínima de la portada). |

### 🧩 Unidad 07 — Grid y diseño adaptable

| Código | Requerimiento |
|---|---|
| **E1-RF-17** | **Móvil primero**: una columna en la hoja base; **dos desde 600 px** y **tres desde 900 px** en el contenedor principal, con las consultas escritas de menor a mayor. |
| **E1-RF-18** | Cabecera, portada y pie a **todo el ancho** (`grid-column: 1 / -1`); **la agenda ocupa dos columnas** desde 600 px (`span 2`). |
| **E1-RF-19** | Las **6 tarjetas** forman una **galería** que se acomoda sola con `repeat(auto-fit, minmax(…, 1fr))`, **sin consultas**. Espacios entre bloques con `gap`. |
| **E1-RF-20** | **Sin desplazamiento horizontal** a 500, 800 y 1200 px, y el resto del sitio no se rompió. |

### 🚫 Restricciones

| Código | Restricción |
|---|---|
| **RNF-01** | Solo **HTML y CSS**. Sin JavaScript ni frameworks. |
| **RNF-02** | **Sin Flexbox** ni animaciones. La disposición es con **Grid**. |
| **RNF-03** | Sin `style=""`, `<style>` ni `!important`. |
| **RNF-04** | Solo datos inventados. Usá los campos y tipos de entrada vistos en clase. |

## ⏱️ Plan sugerido de la sesión (3 horas)

| Tiempo | Qué hacés | ✅ Hito |
|---|---|---|
| 0:00 – 0:40 | Creás `talleres.html` con todo el contenido, la tabla, las listas y el formulario, y agregás el enlace al menú de las 5 páginas | Se ve como documento sin estilo y los enlaces funcionan |
| 0:40 – 1:30 | Estilo: variables, gradiente, tabla, tarjetas, estados y BEM | Se ve completa y con identidad en ventana ancha |
| 1:30 – 2:20 | Unidades relativas y maqueta de **una columna** | Se ve bien a 500 px |
| 2:20 – 2:45 | Puntos de ruptura (600 y 900), galería y pruebas a 500, 800 y 1200 px | Sin desbordes |
| 2:45 – 3:00 | `README`, commit final, `git push` y enlace | Rama `examen-01` subida y enlace listo |

> ⏳ **Las 3 horas incluyen todo.** Los textos del enunciado están para **copiar y pegar**: lo que se evalúa es la estructura, el estilo y la adaptación, no la escritura. La **sustentación** (hasta 5 minutos) ocurre **dentro** de la sesión: el docente te llama desde el minuto **1:45**; cuando te llame, pausá tu trabajo y volvés después.

## 📦 Qué entregás

**El enlace del repositorio** de tu proyecto final, con la nueva implementación en la **rama `examen-01`**. Es **el mismo repositorio** que ya tenés: no crees uno nuevo ni subas un zip.

```bash
git switch -c examen-01                 # crea la rama desde tu proyecto final
# ... trabajás en la página y en el menú ...
git add .
git commit -m "Agrega la página de talleres"
git push -u origin examen-01
```

El enlace tiene este formato (y debe abrir sin iniciar sesión, o con acceso concedido al docente):

```text
https://github.com/<usuario>/<repositorio>/tree/examen-01
```

**Condiciones del repositorio**

- Todo el trabajo va en la rama `examen-01`; la rama principal conserva tu **proyecto final intacto**.
- Hacé **commits frecuentes**: al menos **4** durante la sesión, con mensajes claros. El historial muestra tu trabajo.
- Se evalúa lo que esté **subido (`push`) hasta el final de la sesión**; los commits posteriores no cuentan.
- La estructura del proyecto no cambia: agregás `talleres.html` junto a las otras páginas, y tus reglas en `css/`.

**`README.md` del repositorio.** Agregá una sección **«Examen 1»** (media página) con:

1. **Qué agregaste** y en qué archivos tocaste CSS.
2. **Tabla de medidas** de `talleres.html` (500 / 800 / 1200 px: columnas y si hay desplazamiento horizontal).
3. **Tres unidades**: para tres medidas de la página nueva, cuál usaste y por qué.
4. **Una dificultad** y cómo la resolviste.

## 🎤 Sustentación (hasta 5 minutos, dentro de las 3 horas)

- Abrí la página en los tres tamaños.
- Respondé una pregunta de estructura, una de estilo y una de Grid.
- Hacé **un cambio en vivo**, por ejemplo: pasar la galería a mínimo `14rem` o mover el punto de ruptura de 900 a 1000 px.

## ✅ Lista de control

- [ ] El enlace **Talleres** está en las cinco páginas y funciona.
- [ ] La tabla, las tres listas y el formulario completo están en la página.
- [ ] Probé a **500, 800 y 1200 px** sin desplazamiento horizontal.
- [ ] No hay `style=""`, `<style>`, `!important`, Flexbox ni JavaScript.
- [ ] Ninguna letra en `px`; ningún color suelto fuera de `:root`.
- [ ] Probé el formulario con `Tab`: el foco se ve.
- [ ] La sección «Examen 1» del `README.md` tiene las cuatro partes.
- [ ] Hice `git push` de la rama `examen-01` y el enlace abre.
- [ ] Hay al menos **4 commits** con mensajes claros.
- [ ] La rama principal sigue con mi proyecto final sin cambios.

## 💡 Consejos

- **Primero contenido, luego estilo, al final la adaptación.**
- No empieces por el Grid: con la maqueta de una columna ya se ve bien.
- Si algo se sale de la pantalla, sospechá de la **tabla** y del **formulario**.

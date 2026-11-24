# 📝 Examen 2 — Nuestra historia (Café Altiplano)

> 🎓 **Evaluación de las Unidades 01 a 07.** Sobre tu **proyecto final de Café Altiplano**, vas a agregar una **página nueva**: `nosotros.html`. Se evalúa que apliques lo aprendido por tu cuenta, con más peso en **tipografía, color y unidades relativas**.

## 🧭 Resumen

| | |
|---|---|
| **Examen** | 2 de 3 · **Nuestra historia** |
| **Qué agregás** | Una página nueva, `nosotros.html`, integrada al sitio |
| **Punto de partida** | Tu **proyecto final** (4 páginas + hojas de estilo) |
| **Unidades que evalúa** | 01 a 07, con más peso en **03** (color, gradiente, fondo), **05** (tipografía y cajas) y **06** (unidades) |
| **Tiempo** | **3 horas en total**, en una sola sesión de clase. Incluyen el `README`, la entrega y la sustentación |
| **Modalidad** | Individual |
| **Entrega** | **Enlace del repositorio** de tu proyecto final, con la nueva implementación en la rama `examen-02` |
| **Herramientas** | Editor de código y navegador. **Solo HTML y CSS** |
| **Consulta** | Tus apuntes, las guías y MDN. Sin copiar código de otra persona ni de una IA sin entenderlo |

## 🏪 El encargo

Los clientes preguntan **quiénes están detrás** de Café Altiplano. La cafetería pide una página que cuente:

- su **historia** en una línea de tiempo,
- las **personas** del equipo,
- sus **valores** y una **frase** de la fundadora,
- unas **cifras** de orgullo y un **glosario** del café,
- y un formulario para **escribirles**.

Debe verse **cuidada y legible** en teléfono, tableta y computador. Los datos son inventados.

## 📚 Contenido de la página

### 🏷️ Portada

Título: **Nuestra historia**. Subtítulo: *De tres mesas a tres sedes, siempre con café de origen.*

### 🕰️ Línea de tiempo (lista **ordenada**)

1. **2016** — Abrimos el primer local en el centro: 20 m² y tres mesas.
2. **2018** — Empezamos a tostar nuestro propio café.
3. **2020** — Inauguramos la sede Norte.
4. **2022** — Nace el programa «Café con origen» con cinco cooperativas.
5. **2024** — Abrimos la sede Sur y ya somos 12 baristas.

### 👥 Equipo (tarjetas, 4)

| Nombre | Cargo | Frase |
|---|---|---|
| Lucía Paredes | Fundadora | «Un buen café empieza en la finca». |
| Mateo Quispe | Maestro tostador | «El tueste es escuchar al grano». |
| Camila Rojas | Jefa de baristas | «Cada taza es una conversación». |
| Andrés Salas | Compras y origen | «Pagar justo es parte del sabor». |

### 💬 Cita

> «Queremos que cada persona que entre se lleve algo más que un café.» — **Lucía Paredes**, fundadora (`cite`).

### ⭐ Valores (lista **sin orden**)

- Origen trazable
- Pago justo a productores
- Cero desperdicio
- Un espacio para quedarse

### 🔢 Cifras (tabla pequeña)

| Dato | Valor |
|---|---:|
| Sedes | 3 |
| Cooperativas aliadas | 5 |
| Baristas | 12 |
| Años de trayectoria | 8 |

### 📖 Glosario (lista de **definición**)

- **Tueste**: proceso de calentar el grano verde para desarrollar su sabor.
- **Origen**: lugar donde se cultivó el café.
- **Cata**: degustación atenta para reconocer aromas y sabores.
- **Barista**: persona especializada en preparar café.

### ✉️ Formulario «Escribinos»

Campos: nombre · correo · motivo (opciones: Consulta / Sugerencia / Trabajo) · mensaje (texto largo). Botón **Enviar mensaje**.

## 📋 Requerimientos

### 🧱 Unidad 01 — Estructura

| Código | Requerimiento |
|---|---|
| **E2-RF-01** | `nosotros.html` con `<!DOCTYPE html>`, `lang="es"`, `charset`, `viewport`, `<title>` propio, estructura semántica y **un solo `h1`** con títulos en orden. |
| **E2-RF-02** | El menú incluye **Nosotros** en las **cinco** páginas; en `nosotros.html` se distingue la página actual. |
| **E2-RF-03** | Un **índice con anclas internas** al inicio (Historia · Equipo · Valores · Cifras · Glosario) que lleva a cada sección. Comentarios HTML que separan las partes. |

### 📝 Unidad 02 — Datos y formulario

| Código | Requerimiento |
|---|---|
| **E2-RF-04** | Línea de tiempo con `ol`, valores con `ul` y glosario con `dl`. |
| **E2-RF-05** | La cita usa `blockquote` y `cite`. Las cifras, una `table` con `caption`, `thead`, `tbody` y `th scope`. |
| **E2-RF-06** | Formulario con `fieldset`/`legend`, `label for` en cada campo, un `select`, un `textarea`, `required` y `placeholder`. |

### 🎨 Unidad 03 — Introducción a CSS

| Código | Requerimiento |
|---|---|
| **E2-RF-07** | Estilo solo en **hojas externas**, ordenadas por tema. Sin `style=""` ni `<style>`. |
| **E2-RF-08** | Paleta en variables de `:root`. **Ningún color suelto** fuera. Un **modo de contraste**: el texto sobre fondos oscuros o con gradiente mantiene buena lectura. |
| **E2-RF-09** | La portada con **gradiente** y **imagen de fondo**; una **transparencia** (`rgba`/`opacity`) en un elemento. |
| **E2-RF-10** | **Herencia**: el color de letra se declara en pocos elementos y se hereda; no se repite regla por regla. |

### 🎯 Unidad 04 — Selectores y reglas

| Código | Requerimiento |
|---|---|
| **E2-RF-11** | Clases **BEM** (`persona__nombre`, `persona--fundadora`…). |
| **E2-RF-12** | Un selector de atributo, un combinador, un selector lógico; `:hover` y `:focus` visibles. Una regla con `:first-child` o `:last-child` para destacar el primer o último hito de la línea de tiempo. |
| **E2-RF-13** | Sin `!important` ni `id` para estilo. Reglas **ordenadas y comentadas**. |

### 🔤 Unidad 05 — Tipografía y cajas

| Código | Requerimiento |
|---|---|
| **E2-RF-14** | `font-family` con **alternativas**; jerarquía clara (`h1` > `h2` > `h3` > texto); `line-height` cómodo; una cita con estilo propio (cursiva, borde lateral…). |
| **E2-RF-15** | La **línea de tiempo** se reconoce visualmente (sin números por defecto, borde lateral, separación entre hitos). La tabla de cifras, legible y con valores a la derecha. |
| **E2-RF-16** | **Tarjetas del equipo** con borde, esquinas redondeadas, relleno y margen. `box-sizing: border-box` y página centrada con `max-width`. |

### 📏 Unidad 06 — Unidades relativas

| Código | Requerimiento |
|---|---|
| **E2-RF-17** | Letras en **`rem`** (ninguna en `px`), espacios en `rem`, `px` solo para bordes. |
| **E2-RF-18** | **`ch`** para limitar el ancho de la cita y de los párrafos; al menos un **`%`** y un **`vh`** (por ejemplo, la altura mínima de la portada). |
| **E2-RF-19** | Una escala tipográfica pensada: títulos en `rem` con una **relación clara** (por ejemplo, 2,25 · 1,75 · 1,25 · 1). |

### 🧩 Unidad 07 — Grid y diseño adaptable

| Código | Requerimiento |
|---|---|
| **E2-RF-20** | **Móvil primero**: una columna en la hoja base; **dos desde 600 px** y **tres desde 900 px** en el contenedor principal; consultas de menor a mayor. |
| **E2-RF-21** | Portada, cita y pie a **todo el ancho** (`1 / -1`). Las **cifras** forman una cuadrícula con `auto-fit`/`minmax()` y las **tarjetas del equipo** se acomodan con Grid. Un bloque con `span 2`. |
| **E2-RF-22** | Espacios con `gap`. **Sin desplazamiento horizontal** a 500, 800 y 1200 px. |

### 🚫 Restricciones

Las mismas del examen 1: **solo HTML y CSS**, **sin Flexbox ni animaciones**, sin `style=""`, `<style>` ni `!important`, solo datos inventados.

## ⏱️ Plan sugerido de la sesión (3 horas)

| Tiempo | Qué hacés | ✅ Hito |
|---|---|---|
| 0:00 – 0:40 | Estructura, índice de anclas, listas, tabla, cita y formulario; enlace en las 5 páginas | Documento sin estilo funcionando |
| 0:40 – 1:35 | Paleta, portada con gradiente y fondo, tipografía, línea de tiempo, cita, tarjetas | Página con identidad en ventana ancha |
| 1:35 – 2:15 | Todo en `rem`, `ch`, `%` y `vh`; maqueta de **una columna** | Se ve bien a 500 px |
| 2:15 – 2:45 | Puntos de ruptura y pruebas a 500, 800 y 1200 px | Sin desbordes |
| 2:45 – 3:00 | `README`, commit final, `git push` y enlace | Rama `examen-02` subida y enlace listo |

> ⏳ **Las 3 horas incluyen todo.** Los textos del enunciado están para **copiar y pegar**: lo que se evalúa es la estructura, el estilo y la adaptación, no la escritura. La **sustentación** (hasta 5 minutos) ocurre **dentro** de la sesión: el docente te llama desde el minuto **1:45**; cuando te llame, pausá tu trabajo y volvés después.

## 📦 Qué entregás

**El enlace del repositorio** de tu proyecto final, con la nueva implementación en la **rama `examen-02`**. Es **el mismo repositorio** que ya tenés: no crees uno nuevo ni subas un zip.

```bash
git switch -c examen-02                 # crea la rama desde tu proyecto final
# ... trabajás en la página y en el menú ...
git add .
git commit -m "Agrega la página Nosotros"
git push -u origin examen-02
```

El enlace tiene este formato (y debe abrir sin iniciar sesión, o con acceso concedido al docente):

```text
https://github.com/<usuario>/<repositorio>/tree/examen-02
```

**Condiciones del repositorio**

- Todo el trabajo va en la rama `examen-02`; la rama principal conserva tu **proyecto final intacto**.
- Hacé **commits frecuentes**: al menos **4** durante la sesión, con mensajes claros. El historial muestra tu trabajo.
- Se evalúa lo que esté **subido (`push`) hasta el final de la sesión**; los commits posteriores no cuentan.
- La estructura del proyecto no cambia: agregás `nosotros.html` junto a las otras páginas, y tus reglas en `css/`.

**`README.md` del repositorio.** Agregá una sección **«Examen 2»** (media página) con:

1. **Qué agregaste** y en qué hojas de estilo tocaste CSS.
2. **Tabla de medidas** de `nosotros.html` (500 / 800 / 1200 px: columnas y si hay desplazamiento horizontal).
3. **Tres medidas** con la unidad elegida y su razón, incluida tu **escala tipográfica**.
4. **Una dificultad** y cómo la resolviste.

## 🎤 Sustentación (hasta 5 minutos, dentro de las 3 horas)

Mostrá la página en los tres tamaños, respondé una pregunta de cada bloque y hacé **un cambio en vivo**: por ejemplo, cambiar la escala tipográfica a otra relación, o la paleta entera cambiando solo las variables de `:root`.

## ✅ Lista de control

- [ ] **Nosotros** está en el menú de las cinco páginas.
- [ ] Ordenada, sin orden, definición, cita, tabla y formulario completos.
- [ ] Ninguna letra en `px`; todos los colores salen de `:root`.
- [ ] La portada tiene gradiente, fondo y una transparencia.
- [ ] Sin desplazamiento horizontal a 500, 800 y 1200 px.
- [ ] Sin `style=""`, `<style>`, `!important`, Flexbox ni JavaScript.
- [ ] La sección «Examen 2» del `README.md` tiene las cuatro partes.
- [ ] Hice `git push` de la rama `examen-02` y el enlace abre.
- [ ] Hay al menos **4 commits** con mensajes claros.
- [ ] La rama principal sigue con mi proyecto final sin cambios.

## 💡 Consejos

- Cambiá la paleta **solo en `:root`** para comprobar que no quedan colores sueltos.
- La **jerarquía** se nota con tamaño, peso y espacio, no solo con color.
- Si una frase se sale de la pantalla, revisá los anchos en `ch` y `rem`.

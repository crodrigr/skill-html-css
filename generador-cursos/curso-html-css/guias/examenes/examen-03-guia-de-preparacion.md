# 📝 Examen 3 — Guía para preparar café en casa (Café Altiplano)

> 🎓 **Evaluación de las Unidades 01 a 07.** Sobre tu **proyecto final de Café Altiplano**, vas a agregar una **página nueva**: `guia.html`. Se evalúa que apliques lo aprendido por tu cuenta, con más peso en **estructura, selectores y diseño adaptable**.

## 🧭 Resumen

| | |
|---|---|
| **Examen** | 3 de 3 · **Guía de preparación** |
| **Qué agregás** | Una página nueva, `guia.html`, integrada al sitio |
| **Punto de partida** | Tu **proyecto final** (4 páginas + hojas de estilo) |
| **Unidades que evalúa** | 01 a 07, con más peso en **01** (estructura y anclas), **04** (selectores) y **07** (Grid) |
| **Tiempo** | **3 horas en total**, en una sola sesión de clase. Incluyen el `README`, la entrega y la sustentación |
| **Modalidad** | Individual |
| **Entrega** | **Enlace del repositorio** de tu proyecto final, con la nueva implementación en la rama `examen-03` |
| **Herramientas** | Editor de código y navegador. **Solo HTML y CSS** |
| **Consulta** | Tus apuntes, las guías y MDN. Sin copiar código de otra persona ni de una IA sin entenderlo |

## 🏪 El encargo

Muchos clientes compran el café en grano y preguntan **cómo prepararlo en casa**. Café Altiplano pide una **guía**:

- con un **índice** para saltar a cada método,
- que explique **tres métodos** (prensa francesa, filtro y moka) con sus ingredientes y pasos,
- que **compare** los métodos en una tabla,
- con **consejos** del barista aparte del texto principal,
- y con un formulario para **recibir la guía por correo**.

Debe leerse bien en teléfono, tableta y computador. Los datos son inventados.

## 📚 Contenido de la página

### 🧭 Introducción

> Un buen café en casa depende de tres cosas: la molienda, la proporción y el tiempo. Elegí un método y seguí los pasos.

### 🔗 Índice (anclas)

Prensa francesa · Filtro · Moka · Comparación · Glosario

### ☕ Los tres métodos

Cada método tiene un título, una imagen con pie, una lista de **ingredientes** (sin orden) y una lista de **pasos** (ordenada):

**Prensa francesa**

- Ingredientes: 30 g de café molido grueso · 500 ml de agua a 94 °C · prensa de 600 ml
- Pasos: 1. Echá el café en la prensa. 2. Agregá el agua y mezclá. 3. Esperá 4 minutos. 4. Presioná el émbolo despacio. 5. Serví de inmediato.

**Filtro**

- Ingredientes: 20 g de café molido medio · 320 ml de agua a 93 °C · filtro y cafetera
- Pasos: 1. Enjuagá el filtro con agua caliente. 2. Agregá el café. 3. Mojá el café y esperá 30 segundos. 4. Vertí el resto del agua en círculos. 5. Servilo cuando termine de gotear.

**Moka**

- Ingredientes: 15 g de café molido fino · agua hasta la válvula · cafetera moka de 3 tazas
- Pasos: 1. Llená la base con agua caliente. 2. Agregá el café sin apretarlo. 3. Cerrá y llevá a fuego bajo. 4. Retirá al oír el borboteo. 5. Serví.

### 📊 Comparación (tabla)

| Método | Molienda | Proporción | Tiempo | Dificultad |
|---|---|---|---:|---|
| Prensa francesa | Gruesa | 1:16 | 4 min | Fácil |
| Filtro | Media | 1:16 | 3 min | Media |
| Moka | Fina | 1:7 | 5 min | Media |

### 💡 Consejos del barista (`aside`)

- Usá agua filtrada.
- Muelé el café justo antes de prepararlo.
- Limpiá la cafetera después de cada uso.

Cita: «El mejor café es el que se prepara con calma.» — **Camila Rojas**, jefa de baristas.

### 📖 Glosario (lista de **definición**)

- **Molienda**: tamaño de las partículas del café.
- **Proporción**: relación entre café y agua.
- **Extracción**: cuánto sabor pasa del café al agua.

### ✉️ Formulario «Recibir la guía»

Campos: nombre · correo · método favorito (lista desplegable: Prensa / Filtro / Moka) · nivel (opciones: Principiante / Con experiencia) · casilla «Acepto recibir novedades». Botón **Quiero la guía**.

## 📋 Requerimientos

### 🧱 Unidad 01 — Estructura

| Código | Requerimiento |
|---|---|
| **E3-RF-01** | `guia.html` con `<!DOCTYPE html>`, `lang="es"`, `charset`, `viewport`, `<title>` propio, **un solo `h1`** y títulos en orden. |
| **E3-RF-02** | Estructura semántica **completa**: `header`, `nav`, `main`, una `section` por método, `aside` para los consejos y `footer`. |
| **E3-RF-03** | **Índice con anclas internas** que lleva a cada método, a la comparación y al glosario (`id` en las secciones, **solo para el ancla**). |
| **E3-RF-04** | El menú incluye **Guía** en las **cinco** páginas y marca la página actual. Cada método con `figure` y `figcaption`; imagen con `alt` útil. |

### 📝 Unidad 02 — Datos y formulario

| Código | Requerimiento |
|---|---|
| **E3-RF-05** | Ingredientes con `ul`, pasos con `ol` y glosario con `dl`. Cita con `blockquote` y `cite`. |
| **E3-RF-06** | Tabla comparativa con `caption`, `thead`, `tbody` y `th scope`. |
| **E3-RF-07** | Formulario con `fieldset`/`legend`, `label for`, `select`, `radio`, `checkbox`, `required` y `placeholder`. |

### 🎨 Unidad 03 — Introducción a CSS

| Código | Requerimiento |
|---|---|
| **E3-RF-08** | Estilo en **hojas externas** por tema; paleta en `:root`; **ningún color suelto**. |
| **E3-RF-09** | Un **gradiente** o **imagen de fondo** en la cabecera de la guía, y una transparencia (`rgba`/`opacity`). Herencia del color de letra. |

### 🎯 Unidad 04 — Selectores y reglas

| Código | Requerimiento |
|---|---|
| **E3-RF-10** | Clases **BEM** (`metodo__titulo`, `metodo--destacado`…). |
| **E3-RF-11** | Al menos **tres** de estos: selector de atributo (por ejemplo `a[href^="#"]`), combinador hijo (`>`), hermano adyacente (`+`), `:is()`/`:not()`/`:has()`, `:first-child`/`:last-child`. Cada uno con **sentido** en la página. |
| **E3-RF-12** | `:hover` y `:focus` visibles en el índice, el menú, el botón y los campos; filas alternas en la tabla con `:nth-child()`. |
| **E3-RF-13** | Sin `!important`, sin `id` para dar estilo (solo para anclas), reglas ordenadas y comentadas. |

### 🔤 Unidad 05 — Tipografía y cajas

| Código | Requerimiento |
|---|---|
| **E3-RF-14** | Familia con alternativas, jerarquía clara y `line-height` cómodo. Las listas de pasos se ven **claras** (números visibles, buena separación). |
| **E3-RF-15** | El **`aside`** de consejos se distingue como caja (borde, fondo, relleno). Tabla legible, con `overflow-x: auto` en su contenedor. |
| **E3-RF-16** | `box-sizing: border-box` y página centrada con `max-width`. |

### 📏 Unidad 06 — Unidades relativas

| Código | Requerimiento |
|---|---|
| **E3-RF-17** | Letras y espacios en **`rem`**; `px` solo en bordes. `ch` en el ancho de lectura de los pasos; un `%` y un `vh`. |

### 🧩 Unidad 07 — Grid y diseño adaptable

| Código | Requerimiento |
|---|---|
| **E3-RF-18** | **Móvil primero**: una columna en la hoja base; **dos desde 600 px**; **tres desde 900 px**. Consultas de menor a mayor. |
| **E3-RF-19** | A 900 px o más, los **tres métodos** quedan **uno por columna**. A 600 px, **dos columnas** y el tercer método ocupa **dos** (`span 2`). |
| **E3-RF-20** | La cabecera, el **índice**, la **tabla comparativa** y el pie ocupan **todo el ancho** (`grid-column: 1 / -1`). El `aside` ocupa una columna a 900 px y todo el ancho por debajo. |
| **E3-RF-21** | Espacios con `gap`; imágenes flexibles (`max-width: 100%; height: auto`). **Sin desplazamiento horizontal** a 500, 800 y 1200 px. |

### 🚫 Restricciones

Las mismas de los otros exámenes: **solo HTML y CSS**, **sin Flexbox ni animaciones**, sin `style=""`, `<style>` ni `!important`, datos inventados. Las imágenes pueden reutilizar las de tu proyecto.

## ⏱️ Plan sugerido de la sesión (3 horas)

| Tiempo | Qué hacés | ✅ Hito |
|---|---|---|
| 0:00 – 0:45 | Estructura semántica, índice de anclas, listas, tabla, `aside` y formulario; enlace en las 5 páginas | Documento sin estilo y con anclas funcionando |
| 0:45 – 1:35 | Estilo: variables, gradiente, selectores avanzados, estados, `aside`, listas de pasos | Se ve completa en ventana ancha |
| 1:35 – 2:15 | `rem`, `ch`, `%`, `vh` y maqueta de **una columna** | Se ve bien a 500 px |
| 2:15 – 2:45 | Puntos de ruptura 600 y 900, `span`, `1 / -1` y pruebas a 500, 800 y 1200 px | Sin desbordes |
| 2:45 – 3:00 | `README`, commit final, `git push` y enlace | Rama `examen-03` subida y enlace listo |

> ⏳ **Las 3 horas incluyen todo.** Los textos del enunciado están para **copiar y pegar**: lo que se evalúa es la estructura, el estilo y la adaptación, no la escritura. La **sustentación** (hasta 5 minutos) ocurre **dentro** de la sesión: el docente te llama desde el minuto **1:45**; cuando te llame, pausá tu trabajo y volvés después.

## 📦 Qué entregás

**El enlace del repositorio** de tu proyecto final, con la nueva implementación en la **rama `examen-03`**. Es **el mismo repositorio** que ya tenés: no crees uno nuevo ni subas un zip.

```bash
git switch -c examen-03                 # crea la rama desde tu proyecto final
# ... trabajás en la página y en el menú ...
git add .
git commit -m "Agrega la guía de preparación"
git push -u origin examen-03
```

El enlace tiene este formato (y debe abrir sin iniciar sesión, o con acceso concedido al docente):

```text
https://github.com/<usuario>/<repositorio>/tree/examen-03
```

**Condiciones del repositorio**

- Todo el trabajo va en la rama `examen-03`; la rama principal conserva tu **proyecto final intacto**.
- Hacé **commits frecuentes**: al menos **4** durante la sesión, con mensajes claros. El historial muestra tu trabajo.
- Se evalúa lo que esté **subido (`push`) hasta el final de la sesión**; los commits posteriores no cuentan.
- La estructura del proyecto no cambia: agregás `guia.html` junto a las otras páginas, y tus reglas en `css/`.

**`README.md` del repositorio.** Agregá una sección **«Examen 3»** (media página) con:

1. **Qué agregaste** y en qué hojas de estilo tocaste CSS.
2. **Tabla de medidas** de `guia.html` (500 / 800 / 1200 px: columnas y si hay desplazamiento horizontal).
3. **Tres selectores** que usaste y por qué.
4. **Una dificultad** y cómo la resolviste.

## 🎤 Sustentación (hasta 5 minutos, dentro de las 3 horas)

Mostrá la página en los tres tamaños, respondé una pregunta de cada bloque y hacé **un cambio en vivo**: por ejemplo, que el `aside` pase a ocupar dos columnas a 900 px, o que el índice quede en dos columnas.

## ✅ Lista de control

- [ ] **Guía** está en el menú de las cinco páginas y las anclas funcionan.
- [ ] Hay `ul`, `ol`, `dl`, `blockquote`, tabla y formulario completos.
- [ ] Al menos **tres** selectores de la lista E3-RF-11, con sentido.
- [ ] A 900 px los tres métodos están en tres columnas; a 600 px, en dos con el tercero ocupando dos.
- [ ] Sin desplazamiento horizontal a 500, 800 y 1200 px.
- [ ] Sin `style=""`, `<style>`, `!important`, Flexbox ni JavaScript.
- [ ] Ninguna letra en `px`; ningún color suelto.
- [ ] La sección «Examen 3» del `README.md` tiene las cuatro partes.
- [ ] Hice `git push` de la rama `examen-03` y el enlace abre.
- [ ] Hay al menos **4 commits** con mensajes claros.
- [ ] La rama principal sigue con mi proyecto final sin cambios.

## 💡 Consejos

- Hacé el **índice** primero: te obliga a pensar en la estructura.
- Los `id` sirven para las anclas, **no** para dar estilo.
- Probá cada ruptura (600 y 900) con la ventana real, no solo con el cálculo.

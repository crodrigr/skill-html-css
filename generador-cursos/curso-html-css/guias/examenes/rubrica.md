# 🧮 Rúbrica y guía de corrección — Exámenes 1, 2 y 3 (Unidades 01 a 07)

> 👩‍🏫 **Material docente.** No se entrega a los estudiantes antes de la evaluación. Los enunciados están en [examen-01](examen-01-talleres-y-eventos.md), [examen-02](examen-02-nuestra-historia.md) y [examen-03](examen-03-guia-de-preparacion.md).

## ⏱️ Logística de la sesión (3 horas)

- Cada examen se aplica en **una sesión de 3 horas**. Las 3 horas incluyen la **entrega** y la **sustentación**.
- La sustentación se hace **durante la sesión**, desde el minuto **1:45** hasta el **3:00** (75 minutos de ventana).
- **Cuenta rápida:** 5 min × estudiantes ≤ 75 min → hasta **15 estudiantes**. Con más, usar **3 minutos** por persona (hasta 25 estudiantes) o sustentar por **muestreo** (pregunta + cambio en vivo a quienes se elijan, y a los demás una pregunta escrita).
- Mientras el docente sustenta, el resto sigue con los puntos de ruptura, las pruebas y el `README`.
- Se entrega **el enlace del repositorio** del proyecto final del estudiante (rama `examen-01`, `examen-02` o `examen-03`, según el examen). Recoger los enlaces en una lista compartida o en la plataforma al terminar.

## 🔎 Cómo se corrige (≈ 20 minutos por estudiante, fuera de la sesión)

1. **Validación automática** (3 min). Clonar el repositorio en una carpeta aparte, cambiar a la rama del examen y validar desde `generador-cursos/`:

   ```bash
   git clone <enlace-del-repositorio> /tmp/estudiante
   git -C /tmp/estudiante switch examen-01          # o examen-02 / examen-03
   python3 herramientas/validar_html.py /tmp/estudiante/talleres.html   # o nosotros.html / guia.html
   python3 herramientas/validar_css.py /tmp/estudiante/css
   ```

   Los errores señalan dónde mirar; **no restan por sí solos**.
2. **Búsqueda de prohibiciones** (2 min): `style=`, `<style`, `!important`, `display: flex`, `<script` y `font-size` en `px`.
3. **Revisión visual** (8 min): abrir la **página nueva** con las herramientas del navegador a **500, 800 y 1200 px** y contrastar con el `README`. Comprobar que **el resto del sitio no se rompió** y que el enlace del menú está en las **cinco** páginas.
4. **Lectura del código y del `README`** (7 min).
5. **Sustentación** (ya hecha en clase): contrastar lo que respondió con lo que entregó.

## 📊 Distribución de puntos (100 por examen)

El peso cambia según el foco de cada examen.

| Unidad | Examen 1 · Talleres | Examen 2 · Historia | Examen 3 · Guía |
|---|---:|---:|---:|
| 01 Estructura | 8 | 8 | **14** |
| 02 Datos y formulario | **16** | 10 | 12 |
| 03 Introducción a CSS | 8 | **14** | 8 |
| 04 Selectores | 12 | 14 | **16** |
| 05 Tipografía y cajas | 14 | **18** | 10 |
| 06 Unidades relativas | 10 | **14** | 10 |
| 07 Grid y adaptable | **26** | 16 | **24** |
| Entrega y sustentación | 6 | 6 | 6 |
| **Total** | **100** | **100** | **100** |

> 🧩 Cada examen premia la competencia que **más pide** su página: la tabla y la galería (1), la tipografía y el color (2) y la estructura con el Grid (3).

## 🧾 Rúbrica detallada

Cada criterio se califica en cuatro niveles: **Logrado** (100 %), **Casi** (70 %), **Parcial** (40 %) y **No logrado** (0 %). Los puntos son **Ex 1 / Ex 2 / Ex 3**; «—» indica que ese examen no lo evalúa.

### Unidad 01 — Estructura

| Criterio | Ex 1 / 2 / 3 | Logrado | No logrado |
|---|---|---|---|
| Documento y semántica (E1-RF-01 · E2-RF-01 · E3-RF-01 y 02) | 4 / 4 / 6 | Doctype, `lang`, `charset`, `viewport`, `title` propio, semántica completa, un solo `h1` | Todo en `div` o varios `h1` |
| Menú en las 5 páginas y página actual (RF-02 · RF-02 · RF-04) | 2 / 2 / 3 | Enlace nuevo en todas, funciona y la actual se distingue | Enlace ausente o roto en alguna |
| Anclas, figuras y comentarios (RF-03 · RF-03 · RF-03 y 04) | 2 / 2 / 5 | Anclas que llevan a su sección (Ex 2 y 3), `figure/figcaption`, `alt` útil, comentarios | Faltan anclas o `alt` |

### Unidad 02 — Datos y formulario

| Criterio | Ex 1 / 2 / 3 | Logrado | No logrado |
|---|---|---|---|
| Tabla (RF-04 · RF-05 · RF-06) | 4 / 3 / 4 | `caption`, `thead`, `tbody`, `th scope` | Tabla hecha con `div` |
| Listas y cita (RF-05 · RF-04 y 05 · RF-05) | 4 / 3 / 3 | `ol`, `ul`, `dl` bien elegidas; `blockquote` y `cite` (Ex 2 y 3) | Falta algún tipo |
| Formulario (RF-06 · RF-06 · RF-07) | 8 / 4 / 5 | `fieldset/legend`, `label for`, campos pedidos, `required`, `placeholder` | Campos sin etiqueta o sin `name` |

### Unidad 03 — Introducción a CSS

| Criterio | Ex 1 / 2 / 3 | Logrado | No logrado |
|---|---|---|---|
| Hojas externas, sin estilo en línea | 2 / 3 / 2 | Estilo por tema, ningún `style=""` ni `<style>` | Estilo en línea |
| Variables, sin colores sueltos | 3 / 4 / 3 | Todo color sale de `:root` | Colores repetidos en las reglas |
| Gradiente, fondo y transparencia (Ex 3 incluye la herencia) | 3 / 4 / 3 | Presentes y visibles | Falta alguno |
| Herencia del color | — / 3 / — | Se declara en pocos elementos | Se repite regla por regla |

### Unidad 04 — Selectores y reglas

| Criterio | Ex 1 / 2 / 3 | Logrado | No logrado |
|---|---|---|---|
| BEM | 3 / 3 / 3 | Nombres coherentes `bloque__elemento--modificador` | Sin criterio |
| Selectores avanzados | 4 / 5 / 6 | Atributo, combinador, lógico y `:nth-child` (Ex 1); más `:first-child`/`:last-child` (Ex 2); **tres** con sentido (Ex 3) | Faltan |
| Estados | 3 / 3 / 4 | `:hover` y `:focus` visibles en menú, botón y campos (Ex 3: también el índice) | Solo `:hover` o foco invisible |
| Orden y limpieza | 2 / 3 / 3 | Sin `!important`; `id` solo para anclas; reglas comentadas | `!important` o `id` para estilo |

### Unidad 05 — Tipografía, datos y cajas

| Criterio | Ex 1 / 2 / 3 | Logrado | No logrado |
|---|---|---|---|
| Tipografía y jerarquía | 3 / 5 / 3 | Familia con alternativas, jerarquía clara, `line-height`; cita con estilo (Ex 2) | Todo igual |
| Datos legibles | 5 / 4 / 3 | Agenda (Ex 1), línea de tiempo y cifras (Ex 2), pasos y tabla (Ex 3); con `overflow-x: auto` en la tabla | La tabla rompe a 500 px |
| Cajas | 4 / 6 / 2 | Tarjetas (Ex 1 y 2) o `aside` (Ex 3) con borde, esquinas, relleno y margen | Sin cajas diferenciadas |
| Border-box y página centrada | 2 / 3 / 2 | `border-box` global; `max-width` + `margin: 0 auto` | Falta alguno |

### Unidad 06 — Unidades relativas

| Criterio | Ex 1 / 2 / 3 | Logrado | No logrado |
|---|---|---|---|
| Letras en `rem` | 3 / 4 / 3 | Ningún `font-size` en `px` | Letras en `px` |
| Espacios y anchos en `rem` | 3 / 4 / 3 | `px` solo en bordes | Espacios en `px` |
| `ch`, `%` y `vh` | 4 / 4 / 4 | Uno de cada uno, con sentido | Falta alguno |
| Escala tipográfica (E2-RF-19) | — / 2 / — | Relación clara entre títulos | Tamaños sin relación |

### Unidad 07 — Grid y adaptable

| Criterio | Ex 1 / 2 / 3 | Logrado | No logrado |
|---|---|---|---|
| Móvil primero y puntos de ruptura 600 y 900 | 8 / 5 / 7 | Base de una columna; 1 → 2 → 3 medidas; consultas de menor a mayor | Escritorio primero o columnas distintas |
| Ocupar columnas (`1 / -1`, `span`) | 5 / 3 / 9 | Ex 1 y 2: cabecera, portada y pie a todo el ancho y un `span 2`. Ex 3: además tres métodos uno por columna a 900 px, el tercero con `span 2` a 600 px y `aside` correcto | Sin control de columnas |
| Galería o cuadrícula `auto-fit` | 6 / 3 / — | `repeat(auto-fit, minmax())` sin consultas | Con consultas o columnas fijas |
| `gap` e imágenes flexibles | 3 / 2 / 3 | Espacios con `gap`; `max-width: 100%; height: auto` | Márgenes sueltos |
| Sin desplazamiento horizontal | 4 / 3 / 5 | La página nueva y el resto, a 500/800/1200 px | Desborde en alguna |

### Entrega y sustentación (6 pts)

| Criterio | Pts | Logrado |
|---|---:|---|
| Repositorio y rama según el enunciado | 1 | El enlace abre, la rama es la pedida, la principal quedó intacta y hay **al menos 4 commits** con mensajes claros |
| `README` con las partes pedidas | 2 | Qué agregó, tabla de medidas, unidades o selectores, dificultad |
| Sustentación: explica su código | 2 | Responde con claridad |
| Cambio en vivo | 1 | Lo hace en pocos minutos |

## 📏 Valores de referencia para la medición

Columnas del contenedor principal de la **página nueva** (Chrome; el «teléfono» se mide a 500 px). Una barra de desplazamiento resta unos 15 px: medir con ventana alta.

| Ventana | Examen 1 `talleres` | Examen 2 `nosotros` | Examen 3 `guia` | Desborde |
|---|---|---|---|---|
| 500 px | 1 | 1 | 1 | no |
| 800 px | 2 | 2 | 2 (el tercer método con `span 2`) | no |
| 1200 px | 3 | 3 | 3 (un método por columna) | no |

Los estudiantes pueden nombrar distinto sus clases; lo que importa es el **número de columnas** y que no haya desborde.

## 🎯 Cambios en vivo sugeridos

| Examen | Ejemplos |
|---|---|
| 1 | Galería con mínimo `14rem`; ruptura de 900 a 1000 px; agregar una columna a la tabla (`Nivel`) |
| 2 | Otra escala tipográfica; cambiar toda la paleta solo en `:root`; hacer que la cita ocupe 2 columnas |
| 3 | `aside` en dos columnas a 900 px; índice en dos columnas; resaltar con `:has()` la sección que contiene una tabla |

## ⚖️ Criterios de decisión

- **Las restricciones restan.** Flexbox, JavaScript, frameworks, `style=""`, `<style>` o `!important` se califican como **No logrado** en el criterio afectado y se anotan en el acta.
- **Se evalúa lo subido en la sesión.** Se revisa el último commit hecho **hasta el cierre** (comparar las fechas del historial); los commits posteriores no cuentan. Si el enlace no abre o la rama no existe, se pide corregirlo de inmediato y se anota en el acta.
- **El historial es evidencia.** Un único commit enorme al final, o un historial que no se corresponde con la sustentación, puede reducir la nota de las unidades afectadas.
- **El resto del sitio cuenta.** Si agregar la página nueva rompe otra página (menú, desborde), se descuenta en «Menú en las 5 páginas» o en «Sin desplazamiento horizontal».
- **Equivalencias.** Es válida cualquier técnica que cumpla el requerimiento con lo visto en las unidades.
- **Aprobación sugerida: 60 puntos**, con al menos la **mitad de los puntos de la Unidad 07**.
- **Integridad.** Si la sustentación no coincide con el código, se puede reducir la nota de las unidades afectadas.

## 🚦 Niveles de desempeño global

| Puntaje | Nivel | Lectura |
|---:|---|---|
| 90 – 100 | 🟢 Sobresaliente | Página nueva sólida e integrada, adaptable y con criterio propio |
| 75 – 89 | 🔵 Competente | Cumple lo pedido; pequeños detalles de orden o de contraste |
| 60 – 74 | 🟡 En desarrollo | Funcional, con huecos en adaptabilidad o en alguna unidad |
| < 60 | 🔴 Insuficiente | No logra el diseño adaptable o no aplica las técnicas pedidas |

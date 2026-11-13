# 🧮 Rúbrica y guía de corrección — Proyecto final (Unidades 01 a 07)

> 👩‍🏫 **Material docente.** No se entrega a los estudiantes antes de la evaluación. El enunciado está en [enunciado.md](enunciado.md); la solución de referencia, en [`codigo/solucion/`](codigo/solucion/).

## 🔎 Cómo se corrige

1. **Revisión automática** (5 minutos). Con la carpeta del estudiante descomprimida:

   ```bash
   python3 codigo/verificar_proyecto.py <carpeta-del-estudiante>
   ```

   El script comprueba validación, prohibiciones (`style=""`, `!important`, Flexbox, JavaScript, `px` en letras, colores sueltos), la presencia de cada técnica pedida y el **desplazamiento horizontal** a 500, 800 y 1200 px. **Un ❌ no resta puntos por sí solo**: indica dónde mirar (por ejemplo, una técnica puede estar bien aplicada con otra sintaxis).
2. **Revisión visual** (10 minutos). Abrir cada página con las herramientas del navegador a 500, 800 y 1200 px y contrastar con la tabla del `README`.
3. **Lectura del código y del `README`** (10 minutos).
4. **Sustentación** (5 minutos): pregunta por bloque y un cambio en vivo.

## 📊 Distribución de puntos (100)

| Unidad | Criterio | Puntos |
|---|---|---:|
| 01 | Estructura y semántica, menú, anclas, imágenes | **10** |
| 02 | Tablas, listas, cita y formulario | **12** |
| 03 | Hojas externas, variables, gradiente, fondo, herencia | **12** |
| 04 | Selectores, estados, BEM, orden de reglas | **14** |
| 05 | Tipografía, tablas/listas con estilo, cajas | **14** |
| 06 | Unidades relativas y su justificación | **12** |
| 07 | Grid y diseño adaptable | **20** |
| — | Entrega, `README` y sustentación | **6** |
| | **Total** | **100** |

> 🧩 Las dos unidades que **más pesan** (05 y 07 con 34 puntos) son las que mejor muestran la **maquetación** y el **diseño responsive**, que son el objetivo del proyecto.

## 🧾 Rúbrica detallada

Cada criterio se califica en cuatro niveles: **Logrado** (100 %), **Casi** (70 %), **Parcial** (40 %) y **No logrado** (0 %).

### Unidad 01 — Estructura (10 pts)

| Criterio | Pts | Logrado | No logrado |
|---|---:|---|---|
| Documento completo (RF-01.1) | 2 | Las 4 páginas con doctype, `lang`, `charset` y `title` distinto | Falta algo en varias páginas |
| Semántica (RF-01.2) | 3 | `header`, `nav`, `main`, `section`/`aside`, `footer`; un `h1`; títulos en orden | Todo en `div` o varios `h1` |
| Menú y enlaces (RF-01.3) | 2 | Igual en las 4 páginas y todos los enlaces funcionan | Enlaces rotos o menú distinto |
| Anclas, imágenes y enlace externo (RF-01.4, 01.5) | 2 | Índice con anclas; `alt` útil; `figure/figcaption`; `rel` seguro | Faltan `alt` o anclas |
| Comentarios (RF-01.6) | 1 | Separan las partes | Ninguno |

### Unidad 02 — Datos y formulario (12 pts)

| Criterio | Pts | Logrado | No logrado |
|---|---:|---|---|
| Tablas (RF-02.1) | 3 | `caption`, `thead`, `tbody`, `th scope` | Tabla hecha con `div` o sin encabezados |
| Listas y cita (RF-02.2, 02.3) | 3 | `ul`, `ol`, `dl` bien elegidas; `blockquote` y `cite` | Faltan tipos de lista |
| Formulario (RF-02.4) | 6 | `fieldset/legend`; cada campo con `label for`; `select`, `radio`, `checkbox`, `textarea`; `required` y `placeholder` | Campos sin etiqueta o sin `name` |

### Unidad 03 — Introducción a CSS (12 pts)

| Criterio | Pts | Logrado | No logrado |
|---|---:|---|---|
| Hojas externas ordenadas (RF-03.1) | 3 | Varias hojas enlazadas, una por tema | Todo en una hoja desordenada, o estilo en línea |
| Variables y paleta (RF-03.2) | 4 | Paleta en `:root`; **ningún** color suelto fuera | Colores repetidos en las reglas |
| Gradiente, fondo y transparencia (RF-03.3) | 3 | Los tres presentes y visibles | Falta alguno |
| Herencia (RF-03.4) | 2 | El color se hereda; no se repite | Se repite en cada regla |

### Unidad 04 — Selectores (14 pts)

| Criterio | Pts | Logrado | No logrado |
|---|---:|---|---|
| BEM (RF-04.1) | 3 | Nombres coherentes `bloque__elemento--modificador` | Nombres sin criterio |
| Atributo, combinador y lógico (RF-04.2) | 4 | Los tres usados con sentido | Falta alguno |
| Estados (RF-04.3) | 3 | `:hover` y `:focus` visibles en menú, botón y campos | Solo `:hover` o foco invisible |
| Filas alternas y página actual (RF-04.4) | 2 | `:nth-child` y menú que marca la página | Falta alguno |
| Orden y limpieza (RF-04.5) | 2 | Sin `!important`, sin `id` para estilo, comentadas | `!important` o `id` |

### Unidad 05 — Tipografía y cajas (14 pts)

| Criterio | Pts | Logrado | No logrado |
|---|---:|---|---|
| Tipografía y jerarquía (RF-05.1) | 3 | Familia con alternativas; jerarquía clara; `line-height` | Todo igual de grande |
| Tablas y listas legibles (RF-05.2) | 3 | Bordes colapsados, relleno, precios a la derecha | Tabla sin estilo |
| Tarjetas (RF-05.3) | 3 | Borde, esquinas, relleno y margen coherentes | Sin cajas diferenciadas |
| Border-box y página centrada (RF-05.4) | 3 | `border-box` global; `max-width` + `margin: 0 auto` | Falta alguno |
| Overflow en tablas (RF-05.5) | 2 | Contenedor con `overflow-x: auto` | La tabla rompe la página a 500 px |

### Unidad 06 — Unidades relativas (12 pts)

| Criterio | Pts | Logrado | No logrado |
|---|---:|---|---|
| Letras en `rem` (RF-06.1) | 3 | Ningún `font-size` en `px`; raíz en `100 %` | Letras en `px` |
| Espacios y anchos en `rem` (RF-06.2) | 3 | `px` solo en bordes | Espacios en `px` |
| `ch` (RF-06.3) | 2 | `max-width` de lectura en `ch` | Ausente |
| `%` y `vh` (RF-06.4) | 2 | Uno de cada uno, con sentido | Falta alguno |
| Justificación de cinco medidas (RF-06.5) | 2 | Cinco decisiones razonadas con el criterio visto | Menos de cinco o sin razón |

### Unidad 07 — Grid y adaptable (20 pts)

| Criterio | Pts | Logrado | No logrado |
|---|---:|---|---|
| Viewport e imágenes flexibles (RF-07.1) | 2 | Meta en las 4 páginas; `max-width: 100%` | Falta la meta |
| Móvil primero (RF-07.2) | 3 | Base de una columna; `min-width` para lo demás | Escritorio primero con `max-width` o sin lógica |
| Puntos de ruptura 600 y 900 (RF-07.3) | 5 | 1 → 2 → 3 columnas medidas con 500/800/1200; consultas de menor a mayor | Columnas distintas de las pedidas |
| Ocupar columnas (RF-07.4) | 3 | `1 / -1` en cabecera, portada y pie; un `span 2` | Sin control de columnas |
| Galería `auto-fit` (RF-07.5) | 3 | `repeat(auto-fit, minmax())` sin consultas | Con consultas o columnas fijas |
| `gap` (RF-07.6) | 1 | Los espacios entre bloques con `gap` | Márgenes sueltos |
| Sin scroll horizontal (RF-07.7) | 3 | Ninguna página desborda a 500/800/1200 | Desborde en alguna |

### Entrega y sustentación (6 pts)

| Criterio | Pts | Logrado |
|---|---:|---|
| Carpeta y nombres según el enunciado | 1 | Estructura pedida |
| `README` con las 5 partes | 2 | Mapa, tabla de medidas, 5 justificaciones, decisiones, dificultades |
| Sustentación: explica su código | 2 | Responde con claridad |
| Cambio en vivo | 1 | Lo hace en pocos minutos |

## 📏 Valores de referencia para la medición

Medidas de la **solución de referencia** (Chrome headless; el «teléfono» se mide a 500 px porque Chrome no baja de ahí). Una barra de desplazamiento vertical resta unos 15 px: medir con ventana alta (`ANCHOx2000`).

| Ventana | Columnas del contenedor `.pagina` | Desborde horizontal |
|---|---|---|
| 500 px | 1 | no |
| 800 px | 2 | no |
| 1200 px | 3 | no |

Los estudiantes pueden llamar distinto a sus clases; lo que importa es el **número de columnas** del contenedor principal y que no haya desborde.

## ⚖️ Criterios de decisión

- **Las restricciones no suman, restan.** Si hay Flexbox, JavaScript o frameworks (RNF-01 y RNF-02), la parte correspondiente se califica como **No logrado** y se anota en el acta.
- **Equivalencias.** Es válida cualquier técnica que cumpla el requerimiento con lo visto en las unidades (por ejemplo, otro nombre de clase, otro orden de hojas).
- **Aprobación sugerida: 60 puntos**, con al menos **10 de 20 en la Unidad 07** (es la competencia central del proyecto).
- **Integridad.** Si la sustentación no coincide con el código entregado, se puede reducir la nota de las unidades afectadas.

## 🚦 Niveles de desempeño global

| Puntaje | Nivel | Lectura |
|---:|---|---|
| 90 – 100 | 🟢 Sobresaliente | Maqueta sólida y adaptable, con criterio propio en las decisiones |
| 75 – 89 | 🔵 Competente | Cumple lo pedido; pequeños desbordes o detalles de orden |
| 60 – 74 | 🟡 En desarrollo | Sitio funcional, pero con huecos en adaptabilidad o en unidades |
| < 60 | 🔴 Insuficiente | No logra el diseño adaptable o no usa las técnicas pedidas |

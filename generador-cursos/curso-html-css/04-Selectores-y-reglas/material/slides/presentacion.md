# 🎯 Selectores y reglas

Curso **HTML y CSS** · Clase 04

---

## 🎯 Objetivos de la clase

- 🔹 Elegir elementos con precisión: atributos, relaciones, estados y posiciones.
- 🔹 Nombrar clases con BEM.
- 🔹 Escribir reglas claras y mantenibles.

> 📌 Se recomiendan las Clases 01 a 03.

---

## 🎯 ¿Qué es un selector?

El patrón que **elige los elementos** a los que se aplica una regla.

| Selector | Elige |
|---|---|
| `h2` | Todos los `h2` |
| `.destacado` | Los de `class="destacado"` |
| `#contacto` | El de `id="contacto"` |
| `h1, h3` | Los de cualquiera de los dos |

---

## 🔖 Selectores de atributos

![Cinco selectores de atributo aplicados a dos enlaces: uno con href https://lucia-fernandez.example/cv.pdf y otro con href proyectos.html. Cada fila indica si el selector elige o no a cada enlace.](../imagenes/selectores-de-atributos.svg)

---

## 🧱 BEM: la idea

![El bloque tarjeta contiene los elementos tarjeta__imagen, tarjeta__titulo, tarjeta__texto y tarjeta__enlace; los modificadores tarjeta--destacada, del bloque, y tarjeta__titulo--grande, del elemento titulo, cambian su aspecto.](../imagenes/bem-bloque-elemento-modificador.svg)

---

## 🏷️ BEM: los nombres

| Parte | Ejemplo |
|---|---|
| Bloque | `tarjeta` |
| Elemento | `tarjeta__titulo` |
| Modificador | `tarjeta--destacada` |

> 📌 La documentación oficial usa **un guion bajo** para el modificador; `--` es una variante habitual. Elegí **una**.

---

## 🔗 Combinadores

![En una sección con un título h2, dos párrafos p1 y p2 y un div que contiene un párrafo p3: el espacio elige p1, p2 y p3; el signo mayor elige p1 y p2; el signo más elige p1; la tilde elige p1 y p2.](../imagenes/combinadores.svg)

---

## 🧮 Selectores lógicos: `:is()` y `:where()`

```css
:is(h1, h2, h3) { color: #1e3a8a; }
:where(ul, ol) li { color: #16a34a; }
```

- `:is()` suma la especificidad de su argumento más específico.
- `:where()` **siempre vale cero**.

---

## 🚫 `:not()` y `:has()`

```css
a:not([href^="https"]) { … }
article:has(img) { … }
```

- `:not()` **excluye**.
- `:has()` elige un elemento **según lo que contiene**.

> 📌 `:has()` es reciente (Chrome y Edge 105, Firefox 121, Safari 15.4).

---

## 🖱️ Pseudoclases de estado

| Pseudoclase | Cuándo |
|---|---|
| `:hover` | El cursor está encima |
| `:focus` | El elemento tiene el foco |
| `:active` | Se está presionando |
| `:checked` | Casilla u opción marcada |
| `:disabled` | Elemento deshabilitado |

---

## 🔒 `:visited` y el orden

- Orden de los enlaces: **normal → visitado → cursor → foco**.
- `:visited` está **limitado por privacidad**: solo cambia colores y no se puede leer.
- `:hover` no existe en pantallas táctiles.

---

## 🔢 Pseudoclases de estructura

![Cinco elementos li numerados del 1 al 5: li:first-child elige el 1, li:last-child el 5, li:nth-child(3) el 3, li:nth-child(even) el 2 y el 4, y li:nth-child(odd) el 1, el 3 y el 5; li:only-child solo elige un li sin hermanos.](../imagenes/posiciones-entre-hermanos.svg)

---

## ➗ `:nth-child()` y `:nth-of-type()`

- Se cuenta **desde 1**.
- `odd`, `even` o `An+B`: `2n`, `2n+1`, `n+3`.
- `:nth-child()` cuenta **todos** los hermanos; `:nth-of-type()`, los de la misma etiqueta.

---

## 🧹 Reglas claras

| Práctica | Cómo |
|---|---|
| Ordenar | Primero lo general, después los componentes |
| Agrupar | Una regla por selector |
| Comentar | Un comentario antes de cada bloque |
| Simplificar | Un solo selector de clase |

---

## ⚖️ Especificidad: no la pelees

`main article.tarjeta h3.tarjeta__titulo` vale `0-2-3` y **no lo anula** un `.tarjeta__titulo` posterior (`0-1-0`).

Solución: **selectores simples**, sin `!important`.

---

## 🚧 Errores frecuentes

| Error | Cómo evitarlo |
|---|---|
| `:hover` antes de `:visited` | Respetá el orden de los enlaces |
| `:nth-child(0)` | Se cuenta desde 1 |
| Un selector mal escrito en un grupo | Revisalo: puede anular toda la regla |
| Selectores larguísimos | Una clase por elemento |

---

## 🛠️ Actividad práctica

**Taller 01 — Dale estilo a tu galería**

Una hoja ordenada, con BEM y los selectores de la clase.

---

## 🎓 Resumen y evaluación

- ✅ Selectores básicos, de atributos, combinadores y lógicos.
- ✅ Pseudoclases de estado y de estructura.
- ✅ BEM y reglas claras.

📝 Ahora: **Quiz 01** (8 ítems).

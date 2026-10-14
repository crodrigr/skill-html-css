# 📋 HTML para presentación

Curso **HTML y CSS** · Clase 02

---

## 🎯 Objetivos de la clase

- 🔹 Separar el contenido y presentarlo en listas.
- 🔹 Armar tablas con encabezados y celdas combinadas.
- 🔹 Marcar citas y referencias.
- 🔹 Escribir un formulario básico.

> 📌 Se recomienda haber hecho la Clase 01.

---

## ➖ Separadores

```html
<h2>Servicios</h2>
<p>…</p>
<hr>
<h2>Cómo trabajamos</h2>
```

`<hr>`: un cambio de tema. Es una etiqueta vacía.

---

## 📋 Listas

| Etiqueta | Se ve como | Cuándo |
|---|---|---|
| `<ul>` | Viñetas | El orden no importa |
| `<ol>` | Números | El orden importa |
| `<li>` | Un elemento | Siempre dentro de `<ul>` u `<ol>` |

---

## 🪆 Listas dentro de listas

![Una lista no enumerada ul contiene elementos li; la sublista de panaderías y consultorios va dentro del primer li, no directamente dentro del ul exterior.](../imagenes/listas-anidadas.svg)

La sublista va **dentro de un `<li>`**.

---

## 📊 Tablas: la estructura

![Una tabla tiene un caption arriba, un thead con los encabezados th, un tbody con las filas de datos td y un tfoot con una celda que ocupa tres columnas con colspan.](../imagenes/estructura-de-una-tabla.svg)

---

## 🧩 Tablas: combinar celdas

```html
<td colspan="3">Todos los precios incluyen una revisión</td>
<th rowspan="2">Lunes y martes</th>
```

- `colspan`: ocupa varias **columnas**.
- `rowspan`: ocupa varias **filas**.

> ⚠️ Las celdas combinadas complican la tabla para las tecnologías de apoyo.

---

## 🚫 ¿Cuándo no usar una tabla?

- ✅ Para **datos** con filas y columnas.
- ❌ No para ubicar un menú o columnas de texto.

Eso se resuelve con CSS, el próximo módulo.

---

## 💬 Citas y referencias

| Etiqueta | Para qué |
|---|---|
| `<blockquote>` | Cita extensa |
| `<q>` | Cita corta en una oración |
| `<cite>` | Título de una obra |

La atribución va **fuera** del `<blockquote>`.

---

## 📨 ¿Qué es un formulario?

Un conjunto de **campos** con los que la persona **ingresa información** en la página.

```html
<form method="get">
  …campos…
</form>
```

---

## 🧱 La sintaxis básica

![Un form con method get contiene campos input con type, name y value y etiquetas label; al enviarlo, los nombres y valores aparecen en la dirección de la página.](../imagenes/anatomia-de-un-formulario.svg)

---

## ⌨️ Input: `type`, `value` y `name`

- `type`: qué clase de campo es.
- `value`: el valor inicial, o el que se envía.
- `name`: el nombre con el que viaja el dato.

> ⚠️ Un campo **sin `name` no se envía**.

---

## 🔠 Los tipos esenciales

| `type` | Qué hace |
|---|---|
| `text` · `email` · `number` | Texto, correo (se valida), número |
| `password` | Oculta lo que escribís |
| `checkbox` · `radio` | Casilla · una opción entre varias |
| `submit` | Envía el formulario |

---

## 🚀 Enviar sin servidor

Con `method="get"` y sin `action`, la página se recarga con los datos en la dirección:

`contacto.html?nombre=Ana&paginas=3`

> 🔒 Con `get` todo queda visible: **nunca** pruebes con una clave real.

---

## 🚧 Errores frecuentes

| Error | Cómo evitarlo |
|---|---|
| Sublista fuera de un `<li>` | Escribila dentro de un `<li>` |
| Tabla para el diseño | Usá tablas solo para datos |
| `<cite>` para una persona | Usalo para títulos de obras |
| Campo sin `name` | Poné siempre `name` |

---

## 🛠️ Actividad práctica

**Taller 01 — Armá tu página de servicios y contacto**

Una página de servicios con listas, tabla y cita, y una de contacto con formulario.

---

## 🎓 Resumen y evaluación

- ✅ Separadores, listas, tablas y citas.
- ✅ Formulario: `form`, `input`, `type`, `value`.
- ✅ Datos de prueba y sin servidor.

📝 Ahora: **Quiz 01** (8 ítems).

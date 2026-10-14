# 🌐 Fundamentos HTML

Curso **HTML y CSS** · Clase 01

---

## 🎯 Objetivos de la clase

- 🔹 Entender qué es HTML5 y preparar tu entorno.
- 🔹 Escribir documentos con buena estructura, texto y comentarios.
- 🔹 Crear enlaces e incorporar multimedia.
- 🔹 Organizar la página con etiquetas semánticas.

> 📌 No hace falta saber programar.

---

## 🌐 ¿Qué es HTML5?

- Lenguaje de **marcado**: da estructura y significado al contenido.
- **No** es un lenguaje de programación.
- El **navegador** lo lee y lo muestra como página.

> 💡 El aspecto (colores, tipografías) lo define CSS, el próximo módulo.

---

## 🧰 Entorno de desarrollo

Dos herramientas alcanzan:

| Herramienta | Para qué |
|---|---|
| 📝 Editor de código (VS Code) | Escribir y guardar el archivo `.html` |
| 🌍 Navegador | Ver y probar la página |

> 💡 Sin VS Code, podés usar un editor en línea.

---

## 🏗️ Estructura de un documento

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Mi página</title>
  </head>
  <body>
    <h1>Hola</h1>
  </body>
</html>
```

`head`: datos de la página · `body`: lo que se ve.

---

## 🌳 El DOM

![El navegador convierte el documento en un árbol: html contiene head y body; head contiene meta y title; body contiene header, main y footer; main contiene un título h2 y un párrafo.](../imagenes/arbol-dom.svg)

Cada etiqueta anidada es un **hijo** de la que la contiene.

---

## ✏️ Sintaxis y anidación

![Un elemento HTML se forma con una etiqueta de apertura que puede llevar atributos, el contenido y una etiqueta de cierre con una barra; juntos forman el elemento.](../imagenes/anatomia-de-una-etiqueta.svg)

La última etiqueta que se abre es la primera que se cierra.

---

## ✍️ Texto y formato

| Texto | Formato |
|---|---|
| `h1`–`h6`, `p`, `br`, `hr` | `strong`, `em`, `mark` |
| `ul`, `ol`, `li` | `small`, `sub`, `sup` |
| | `del`, `ins`, `code` |

> 💡 Un solo `h1` por página.

---

## 💬 Comentarios

```html
<!-- Esto no se ve en el navegador -->
```

- Explican y organizan el código.
- Cualquiera puede leerlos: nada privado.

---

## 🔗 Hipervínculos y direcciones

![La dirección https://lucia-fernandez.example:443/proyectos/panaderia.html?categoria=web&orden=reciente#resultados se divide en protocolo, dominio, puerto, ruta, parámetros y ancla.](../imagenes/partes-de-una-direccion.svg)

---

## ⚓ Rutas, anclas y fragmentos

- 📁 Ruta relativa: `sobre-mi.html`, `imagenes/foto.png`.
- ⚓ Ancla: `href="#contacto"` + `id="contacto"`.
- 🔦 Fragmento de texto: `#:~:text=` — **opcional del navegador**.

> 📌 Si no se admite, el enlace funciona igual.

---

## 🖼️ Imágenes

```html
<img src="imagenes/foto-lucia.png" alt="Retrato de Lucía">
```

- `src`: la ruta. `alt`: qué muestra.
- Si no se ve: revisá carpeta, nombre y extensión.

---

## 🎬 Video e iframe

- `<video controls>` con `<source>`.
- `<iframe title="…" src="…">` incrusta otra página.

> ⚠️ Algunos sitios no se dejan incrustar.

---

## 🧭 Semántica

![Una página semántica tiene header arriba con nav, un main en el centro con secciones y artículos, un aside lateral y un footer al pie.](../imagenes/estructura-semantica.svg)

---

## 📦 ¿Y el `div`?

- Contenedor **genérico**, sin significado.
- Usalo **solo si ninguna etiqueta semántica** describe lo que agrupás.

---

## 🚧 Errores frecuentes

| Error | Cómo evitarlo |
|---|---|
| Etiqueta sin cerrar | Cerrala siempre |
| Etiquetas solapadas | Cerrá en orden inverso |
| Imagen que no se ve | Revisá ruta y extensión |
| Imagen sin `alt` | Describí lo que muestra |

---

## 🛠️ Actividad práctica

**Taller 01 — Construí tu primer sitio**

Tres páginas, con tu propio tema: estructura, texto, enlaces, multimedia y semántica.

---

## 🎓 Resumen y evaluación

- ✅ HTML marca estructura y significado.
- ✅ Estructura, sintaxis y anidación correctas.
- ✅ Enlaces, multimedia y semántica.

📝 Ahora: **Quiz 01** (8 ítems).

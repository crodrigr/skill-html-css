# 🟢 Básico 01 — Elegí los elementos justos

> 🟢 **Nivel:** Básico · 🎓 **Resultados de aprendizaje:** RA-1, RA-2

## 🧱 Estado inicial

Abrí [`basico-01.html`](../recursos/portafolio-inicial/basico-01.html) de la carpeta `portafolio-inicial`: es la página de inicio de
Mateo Ruiz, con un menú, una lista de enlaces, tres precios y un formulario de reserva. Ya está enlazada a
[`css/basico-01.css`](../recursos/portafolio-inicial/css/basico-01.css), que está vacía.

## 🛠️ Proceso esperado

1. Para cada fila de la tabla, escribí en `basico-01.css` **un selector** que elija exactamente esos elementos, y dale una declaración que
   se note (por ejemplo, `background-color: #fef3c7;`).
2. Comprobá **cuántos elementos** elige cada selector (con las herramientas del navegador o con `document.querySelectorAll("…").length` en la
   consola) y anotalo.

| # | Elegí… | Cuántos deben ser |
|---|---|---|
| 1 | Todos los títulos de segundo nivel | 3 |
| 2 | El elemento cuyo `id` es `reserva` | 1 |
| 3 | Los párrafos de clase `precio` | 3 |
| 4 | Los enlaces cuyo `href` empieza con `https` | 2 |
| 5 | Los enlaces cuyo `href` termina en `.pdf` | 1 |
| 6 | Los campos de tipo correo | 1 |
| 7 | Los enlaces que se abren en una pestaña nueva | 1 |

**Parte B.** Respondé: ¿qué diferencia hay entre `a[href^="https"]` y `a[href*="https"]`? ¿Y entre `.precio` y `p.precio`?

## ✅ Resultado esperado

- ☑️ Siete selectores, uno por fila, que eligen **exactamente** los elementos indicados.
- ☑️ Los siete conteos anotados.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni agregues clases o identificadores.
- 🚫 Cada selector tiene que elegir **solo** lo pedido, ni más ni menos.
- 🚫 Usá solo selectores de elemento, clase, identificador y atributo.

## 🎓 Resultados de aprendizaje

- RA-1: Explicar qué es un selector y usar los selectores básicos para elegir elementos.
- RA-2: Elegir elementos por sus atributos y por el valor de estos.

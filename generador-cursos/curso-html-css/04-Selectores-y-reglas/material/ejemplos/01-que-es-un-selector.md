# 📘 Ejemplo 01 — Qué es un selector

## 🧱 Situación inicial

Lucía armó una página de práctica, `laboratorio-basicos.html`, que reúne títulos, párrafos, listas, tarjetas, una tabla y un formulario.
Antes de usar selectores más avanzados, quiere repasar los básicos y comprobar **cuántos elementos elige cada uno**, para no aplicar un
estilo a más (o a menos) de lo que quiere.

## 💻 Código

Una parte del HTML de la página (de `laboratorio.html`, la página común de la clase):

```html
<h2>Enlaces</h2>
<p class="destacado">Esta página reúne todo lo que vamos a seleccionar.</p>
<p>Los enlaces de ejemplo:</p>
```

```html
<h2 id="contacto">Contacto</h2>
```

La hoja `css/selectores-basicos.css`:

```css
/* Selector de elemento: todos los títulos de segundo nivel */
h2 {
  color: #1e3a8a;
}

/* Selector de grupo: la misma regla para dos selectores */
h1, h3 {
  color: #2563eb;
}

/* Selector de clase: los elementos con class="destacado" */
.destacado {
  background-color: #fef3c7;
}

/* Selector de identificador: el elemento con id="contacto" */
#contacto {
  color: #16a34a;
}
```

## 🔍 Análisis paso a paso

1. **Qué es un selector.** Es lo que se escribe antes de las llaves: dice **a qué elementos** se aplica la regla.
2. **Selector de elemento.** `h2` elige **todos** los títulos de segundo nivel de la página: son **5**.
3. **Selector de grupo.** `h1, h3` aplica una misma regla a los elementos que elige **cualquiera** de los dos selectores: 1 `h1` y 3 `h3`,
   **4** en total.
4. **Selector de clase.** `.destacado` elige los elementos con `class="destacado"`: en esta página es **1** (el párrafo de presentación).
5. **Selector de identificador.** `#contacto` elige el elemento con `id="contacto"`: es **1**, y es un `h2`.
6. **Dos reglas para un mismo elemento.** El `h2#contacto` recibe la regla de `h2` (azul oscuro) y la de `#contacto` (verde). Gana el
   identificador, porque su especificidad es mayor (100 frente a 1).
7. **Comprobar.** Lucía cuenta con las herramientas del navegador (o con `document.querySelectorAll("h2").length` en la consola) y
   compara con lo que esperaba.

## ✅ Resultado esperado

| Selector | Elementos que elige |
|---|---|
| `h2` | 5 |
| `h1, h3` | 4 (1 `h1` y 3 `h3`) |
| `.destacado` | 1 |
| `#contacto` | 1 |

- Los cuatro títulos `h2` que no son `#contacto` se ven en **azul oscuro** (`rgb(30, 58, 138)`).
- El `h1` y los `h3` se ven en **azul** (`rgb(37, 99, 235)`).
- El párrafo `.destacado` tiene fondo **crema** (`rgb(254, 243, 199)`).
- El título `#contacto` se ve en **verde** (`rgb(22, 163, 74)`): gana el identificador.

# 📘 Ejemplo 01 — Tipografías en CSS

> 🕐 **Sesión 1** · 🎓 **Resultados de aprendizaje:** RA-1, RA-2

## 🧱 Situación inicial

Lucía quiere que su artículo se lea con comodidad. En la página `tipografia.html` elige una tipografía para el texto, otra para los títulos y otra para el código, y
ajusta el tamaño, el peso, el estilo y la altura de línea. Solo usa tipografías **del sistema**, es decir, las que ya están instaladas en el equipo de quien visita la página.

## 💻 Código

El contenido de `tipografia.html` (dentro de `<main>`):

```html
<h2>Una familia con alternativas</h2>
<p>Un sitio web nace de una pregunta sencilla: ¿qué querés que haga la persona que lo visita? Si la respuesta es leer, el texto manda; si es comprar, mandan las fotos y los precios. Con esa respuesta clara, el resto de las decisiones se toma casi solo.</p>
<p class="alternativa">Este párrafo pide una tipografía que no existe y, por eso, usa la alternativa de la lista.</p>

<h2>Tamaños</h2>
<p class="px">Veinte píxeles, con px.</p>
<p class="em">Veinte píxeles, con em.</p>
<p class="rem">Veinte píxeles, con rem.</p>
<p class="porcentaje">Veinte píxeles, con porcentaje.</p>
<div class="contenedor">
  <p class="em">Dentro de un contenedor, em se multiplica otra vez.</p>
  <p class="rem">Dentro de un contenedor, rem no cambia.</p>
</div>

<h2>Peso y estilo</h2>
<p class="liviano">Peso liviano (300).</p>
<p class="negrita">Peso negrita (700).</p>
<p class="cursiva">Texto en cursiva.</p>

<h2>Altura de línea</h2>
<p class="apretado">También conviene pensar en quién va a mantener el sitio. Un blog necesita publicar con frecuencia, mientras que una página de aterrizaje se escribe una vez y se revisa cada tanto. Elegir un tipo de sitio que no podés sostener es la forma más rápida de abandonarlo.</p>
<p class="comodo">También conviene pensar en quién va a mantener el sitio. Un blog necesita publicar con frecuencia, mientras que una página de aterrizaje se escribe una vez y se revisa cada tanto. Elegir un tipo de sitio que no podés sostener es la forma más rápida de abandonarlo.</p>

<p>El código se escribe así: <code>font-family: Arial, sans-serif;</code></p>
```

La hoja `css/tipografia.css`:

```css
/* Tipografía base: el texto con una sans-serif, los títulos con una serif y el código con una de ancho fijo */
body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
}

h1, h2 {
  font-family: Georgia, "Times New Roman", serif;
}

h1 {
  font-size: 2rem;
}

h2 {
  font-size: 1.5rem;
}

code {
  font-family: "Courier New", monospace;
}

/* La primera tipografía no existe: el navegador usa la siguiente que encuentre */
.alternativa {
  font-family: "Fuente Inexistente", Georgia, serif;
}

/* Cuatro formas de pedir 20 píxeles, con el tamaño base de 16px */
.px {
  font-size: 20px;
}

.em {
  font-size: 1.25em;
}

.rem {
  font-size: 1.25rem;
}

.porcentaje {
  font-size: 125%;
}

/* Un contenedor más grande: em toma el tamaño del contenedor; rem, el de la raíz */
.contenedor {
  font-size: 1.25em;
}

/* Peso y estilo */
.liviano {
  font-weight: 300;
}

.negrita {
  font-weight: 700;
}

.cursiva {
  font-style: italic;
}

/* Altura de línea: un número sin unidad se multiplica por el tamaño de la letra */
.apretado {
  line-height: 1;
}

.comodo {
  line-height: 1.6;
}
```

## 🔍 Análisis paso a paso

1. **Una pila de alternativas.** `font-family` recibe una **lista** separada por comas, de la más preferida a la menos preferida. El navegador usa la primera que
   encuentra instalada. Por eso la lista siempre termina con una **familia genérica** (`serif`, `sans-serif` o `monospace`): si ninguna de las anteriores está disponible,
   el navegador elige una de ese tipo.
2. **Tres familias, tres usos.** El texto usa `Arial, Helvetica, sans-serif` (sin serifa), los títulos `Georgia, "Times New Roman", serif` (con serifa) y el código
   `"Courier New", monospace` (ancho fijo). Los nombres con espacios, como `"Times New Roman"`, se escriben entre comillas.
3. **La alternativa en acción.** `.alternativa` pide `"Fuente Inexistente"` primero. Como no existe, el navegador sigue con `Georgia` y, si tampoco está, con la serif
   genérica. El valor calculado conserva la **lista completa**; qué tipografía se ve depende de lo que haya instalado cada equipo.
4. **Cuatro formas de pedir el mismo tamaño.** Con el tamaño base de `16px`, las cuatro clases (`20px`, `1.25em`, `1.25rem` y `125%`) calculan **20px**. La diferencia
   aparece al anidar: `em` y `%` se miden contra el tamaño del **padre** y `rem`, contra el de la **raíz** (`html`).
5. **Dentro de un contenedor.** `.contenedor` vale `1.25em` (20px). Su párrafo `.em` vuelve a multiplicar por 1,25 y calcula **25px**; su párrafo `.rem` sigue en **20px**.
   Por eso `rem` es la unidad más previsible para el texto. Además, MDN recomienda las unidades relativas porque respetan el tamaño que cada persona eligió en su
   navegador; un tamaño fijo en `px` no lo hace en algunos navegadores.
6. **Peso y estilo.** `font-weight: 700` equivale a `bold` y `300` pide un peso liviano; si la tipografía no tiene ese peso, el navegador usa el más cercano.
   `font-style: italic` pide cursiva.
7. **Altura de línea.** Un número **sin unidad** (`1.6`) se multiplica por el tamaño de la propia letra: `1.6 × 16px = 25.6px`. Con `1`, las líneas quedan tan juntas
   como la letra (16px) y el texto se vuelve incómodo. MDN recomienda esta forma sin unidad (evita problemas de herencia con `em` o `%`) y un mínimo de `1.5`
   para el texto principal.
8. **Código.** `<code>` toma `"Courier New", monospace`: en ancho fijo, todas las letras ocupan el mismo espacio.

## ✅ Resultado esperado

| Elemento | Propiedad | Valor calculado |
|---|---|---|
| `body` | `font-family` | `Arial, Helvetica, sans-serif` |
| `body` | `font-size` / `line-height` | `16px` / `25.6px` |
| `h1` | `font-family` / `font-size` | `Georgia, "Times New Roman", serif` / `32px` |
| `h2` | `font-size` | `24px` |
| `code` | `font-family` | `"Courier New", monospace` |
| `.px`, `.em`, `.rem`, `.porcentaje` | `font-size` | `20px` las cuatro |
| `.contenedor .em` | `font-size` | `25px` |
| `.contenedor .rem` | `font-size` | `20px` |
| `.liviano` / `.negrita` | `font-weight` | `300` / `700` |
| `.cursiva` | `font-style` | `italic` |
| `.apretado` / `.comodo` | `line-height` | `16px` / `25.6px` |

- Los títulos se ven con **serifa**, el texto **sin serifa** y el código en **ancho fijo** (si no están instaladas `Georgia`, `Arial` o `Courier New`, se ve la
  familia genérica de cada pila).
- El párrafo `.apretado` queda visiblemente más denso que el `.comodo`.

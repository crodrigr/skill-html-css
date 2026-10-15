# 📘 Ejemplo 02 — Textos y alineaciones

> 🕐 **Sesión 1** · 🎓 **Resultados de aprendizaje:** RA-3

## 🧱 Situación inicial

Lucía ya eligió la tipografía de su artículo. Ahora quiere controlar **cómo se acomoda el texto**: alinear los párrafos, dar una sangría a la primera línea, separar
letras y palabras, y cambiar entre mayúsculas y minúsculas sin reescribir el HTML. Lo practica en `texto.html`.

## 💻 Código

El contenido de `texto.html` (dentro de `<main>`):

```html
<h2>Alineación</h2>
<p class="izquierda">Un sitio web nace de una pregunta sencilla: ¿qué querés que haga la persona que lo visita? Si la respuesta es leer, el texto manda; si es comprar, mandan las fotos y los precios. Con esa respuesta clara, el resto de las decisiones se toma casi solo.</p>
<p class="centrado">Texto centrado</p>
<p class="derecha">Texto a la derecha</p>
<p class="justificado">También conviene pensar en quién va a mantener el sitio. Un blog necesita publicar con frecuencia, mientras que una página de aterrizaje se escribe una vez y se revisa cada tanto. Elegir un tipo de sitio que no podés sostener es la forma más rápida de abandonarlo.</p>

<h2>Sangría</h2>
<p class="sangria">Por último, mirá el presupuesto con calma. Los costos mensuales incluyen el alojamiento, el dominio y el tiempo de mantenimiento. Un sitio pequeño y bien hecho rinde más que uno enorme que nadie actualiza.</p>

<h2>Espaciado</h2>
<p class="letras">Letras separadas por dos píxeles.</p>
<p class="palabras">Palabras separadas por diez píxeles más.</p>

<h2>Mayúsculas y minúsculas</h2>
<p class="mayusculas">Todo en mayúsculas</p>
<p class="minusculas">TODO EN MINÚSCULAS</p>
<p class="capitalizado">la primera letra de cada palabra</p>
```

La hoja `css/texto.css`:

```css
/* Alineación del texto dentro de su caja */
.izquierda {
  text-align: left;
}

.centrado {
  text-align: center;
}

.derecha {
  text-align: right;
}

.justificado {
  text-align: justify;
}

/* Sangría: deja espacio antes de la primera línea */
.sangria {
  text-indent: 2rem;
}

/* Espacio entre letras y entre palabras */
.letras {
  letter-spacing: 2px;
}

.palabras {
  word-spacing: 10px;
}

/* Mayúsculas y minúsculas sin cambiar el texto del HTML */
.mayusculas {
  text-transform: uppercase;
}

.minusculas {
  text-transform: lowercase;
}

.capitalizado {
  text-transform: capitalize;
}
```

## 🔍 Análisis paso a paso

1. **`text-align`.** Alinea el texto **dentro de su caja**: `left` (izquierda), `center` (centro), `right` (derecha) y `justify` (justificado: se estiran los espacios para
   que cada línea llegue de borde a borde, salvo la última).
2. **Justificado.** Con renglones cortos deja «ríos» de espacio blanco; conviene usarlo en columnas anchas.
3. **`text-indent`.** Deja un espacio antes de la **primera línea** del bloque. `2rem` equivale a **32px** con el tamaño base. Acepta longitudes, porcentajes (del ancho de
   la caja) y valores negativos.
4. **`letter-spacing`.** Se **suma** al espacio natural entre las letras: `2px` las separa dos píxeles más. Acepta valores negativos, que juntan las letras.
5. **`word-spacing`.** Hace lo mismo con el espacio entre **palabras**: `10px` más. MDN advierte que un valor muy grande, positivo o negativo, vuelve ilegible el texto.
6. **`text-transform`.** Cambia las mayúsculas y minúsculas **al mostrar**, no en el HTML: `uppercase` (todo en mayúsculas), `lowercase` (todo en minúsculas) y
   `capitalize` (la primera letra de cada palabra en mayúscula). El valor inicial es `none`.
7. **Qué conviene.** Dejá el texto del HTML escrito normalmente y usá `text-transform` solo para el aspecto: un lector de pantalla leerá el texto original.

## ✅ Resultado esperado

| Clase | Propiedad | Valor calculado |
|---|---|---|
| `.izquierda`, `.centrado`, `.derecha`, `.justificado` | `text-align` | `left`, `center`, `right`, `justify` |
| `.sangria` | `text-indent` | `32px` |
| `.letras` | `letter-spacing` | `2px` |
| `.palabras` | `word-spacing` | `10px` |
| `.mayusculas`, `.minusculas`, `.capitalizado` | `text-transform` | `uppercase`, `lowercase`, `capitalize` |

- El párrafo `.capitalizado` se muestra como «La Primera Letra De Cada Palabra».
- Solo la **primera línea** de `.sangria` aparece desplazada hacia la derecha.
- El párrafo `.justificado` llena cada renglón hasta ambos bordes, menos el último.

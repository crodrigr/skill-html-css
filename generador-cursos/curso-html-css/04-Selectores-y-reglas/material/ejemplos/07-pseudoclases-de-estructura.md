# 📘 Ejemplo 07 — Pseudoclases de estructura

## 🧱 Situación inicial

La página de Lucía tiene listas y una tabla de habilidades. Quiere resaltar el primer y el último elemento de cada lista, dar a la tabla filas
alternas para que se lea mejor, destacar el tercer paso y el segundo párrafo, y dar un estilo especial a una lista que tiene un solo elemento. No
quiere escribir una clase para cada uno: usa **pseudoclases de estructura** en `laboratorio-estructura.html`.

## 💻 Código

Las listas y la tabla (de `laboratorio.html`):

```html
<table>
  <caption>Mis habilidades</caption>
  <thead>
    <tr><th>Habilidad</th><th>Nivel</th></tr>
  </thead>
  <tbody>
    <tr><td>HTML</td><td>Alto</td></tr>
    <tr><td>CSS</td><td>Medio</td></tr>
    <tr><td>Formularios</td><td>Medio</td></tr>
    <tr><td>Accesibilidad</td><td>Básico</td></tr>
    <tr><td>Git</td><td>Básico</td></tr>
  </tbody>
</table>

<h2>Pasos y notas</h2>
<ol class="pasos">
  <li>Elegir los elementos</li>
  <li>Escribir la regla</li>
  <li>Comprobar el resultado</li>
</ol>
<ul class="nota">
  <li>Una nota con un solo elemento</li>
</ul>
```

La hoja `css/estructura.css`:

```css
/* :first-child: el primer elemento entre sus hermanos */
li:first-child {
  color: #16a34a;
}

/* :last-child: el último elemento entre sus hermanos */
li:last-child {
  background-color: #fef3c7;
}

/* :nth-child(): por posición, contando desde 1 entre todos los hermanos */
li:nth-child(3) {
  color: #dc2626;
}

tr:nth-child(even) {
  background-color: #dbeafe;
}

/* :nth-of-type(): por posición entre los hermanos de la misma etiqueta */
p:nth-of-type(2) {
  background-color: #e0f2fe;
}

/* :only-child: un elemento sin hermanos */
li:only-child {
  font-weight: bold;
}
```

## 🔍 Análisis paso a paso

1. **`:first-child`.** `li:first-child` elige el `li` que es el primer hijo de su padre: son **3** (el primero de la lista de enlaces, de la de pasos y el
   único de la nota). Se ven en verde.
2. **`:last-child`.** `li:last-child` elige el último: también **3** (el último de cada lista). Se ven con fondo crema.
3. **`:only-child`.** `li:only-child` elige el `li` que **no tiene hermanos**: es **1** (el de la nota). Como es a la vez el primero y el último, recibe
   también las reglas anteriores, y además se ve en negrita.
4. **`:nth-child()`.** `li:nth-child(3)` elige el `li` que ocupa el tercer lugar de su padre, contando desde 1: son **2** («Mis proyectos» y «Comprobar el
   resultado»). Se ven en rojo.
5. **Filas alternas.** `tr:nth-child(even)` elige las filas pares de su padre. En esta tabla son **2**: «CSS» y «Accesibilidad», la segunda y la cuarta del cuerpo.
   La fila de encabezados está en otro padre (`thead`), por eso no cuenta con las del cuerpo.
6. **`:nth-of-type()`.** `p:nth-of-type(2)` elige el `p` que es el **segundo de su tipo** entre sus hermanos: son **3** (en `main`, en el formulario y en el pie).
   Cada tarjeta tiene un solo `p`, así que ninguna se elige.
7. **`:nth-child()` o `:nth-of-type()`.** El primero cuenta todos los hermanos; el segundo, solo los de la misma etiqueta.

## ✅ Resultado esperado

| Selector | Elementos que elige |
|---|---|
| `li:first-child` | 3 |
| `li:last-child` | 3 |
| `li:nth-child(3)` | 2 |
| `tr:nth-child(even)` | 2 |
| `p:nth-of-type(2)` | 3 |
| `li:only-child` | 1 |

- Las filas «CSS» y «Accesibilidad» tienen fondo **celeste** (`rgb(219, 234, 254)`).
- El `li` de la nota (único) se ve en **verde**, con fondo **crema** y en **negrita**.
- El tercer elemento de la lista de enlaces y de la de pasos se ve en **rojo**.

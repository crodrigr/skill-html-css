# 📘 Ejemplo 02 — Selectores de atributos

## 🧱 Situación inicial

En `laboratorio-atributos.html`, Lucía quiere distinguir sus enlaces según a dónde llevan: los externos (`https`), los que abren en una
pestaña nueva, los que van a un PDF y los que mencionan sus proyectos. Ninguno tiene una clase propia, pero todos tienen un atributo
`href`. También quiere resaltar los campos de correo. Usa **selectores de atributos**.

## 💻 Código

Los enlaces de la página (de `laboratorio.html`):

```html
<ul class="enlaces">
  <li><a href="https://developer.mozilla.org/es/" target="_blank" rel="noopener">MDN en español</a></li>
  <li><a href="https://lucia-fernandez.example/cv.pdf">Mi currículum (PDF)</a></li>
  <li><a href="proyectos.html">Mis proyectos</a></li>
  <li><a href="#contacto">Ir al contacto</a></li>
</ul>
```

El campo de correo:

```html
<input type="email" id="correo" name="correo">
```

La hoja `css/atributos.css`:

```css
/* [a]: los enlaces que tienen el atributo href */
a[href] {
  color: #2563eb;
}

/* [a="v"]: los enlaces que se abren en una pestaña nueva */
a[target="_blank"] {
  background-color: #fef3c7;
}

/* [a^="v"]: los enlaces cuyo href empieza con https */
a[href^="https"] {
  color: #16a34a;
}

/* [a$="v"]: los enlaces cuyo href termina en .pdf */
a[href$=".pdf"] {
  color: #dc2626;
}

/* [a*="v"]: los enlaces cuyo href contiene la palabra proyectos */
a[href*="proyectos"] {
  background-color: #dbeafe;
}

/* El selector de atributo también sirve para los campos de un formulario */
input[type="email"] {
  background-color: #dbeafe;
}
```

## 🔍 Análisis paso a paso

1. **Presencia.** `a[href]` elige los enlaces que tienen el atributo `href`, sea cual sea su valor. Son **13**: todos los de la página.
2. **Valor exacto.** `a[target="_blank"]` elige solo los que abren en una pestaña nueva: **1** (el de MDN).
3. **Empieza con.** `a[href^="https"]` elige los enlaces cuyo `href` empieza con `https`: **2** (MDN y el PDF).
4. **Termina en.** `a[href$=".pdf"]` elige los enlaces cuyo `href` termina en `.pdf`: **1** (el currículum).
5. **Contiene.** `a[href*="proyectos"]` elige los enlaces cuyo `href` contiene la palabra `proyectos`: **5** (el del menú, el de la lista y los
   tres de las tarjetas).
6. **Un atributo de un campo.** `input[type="email"]` elige los campos de tipo correo: **1**.
7. **La cascada sigue funcionando.** El enlace del PDF cumple `a[href]`, `a[href^="https"]` y `a[href$=".pdf"]`. Las tres reglas tienen la misma
   especificidad (una etiqueta y un atributo), así que gana la **última** que fija el color: la del `.pdf`, en rojo.
8. **Las comillas.** El valor va entre comillas en el selector, como en el HTML.

## ✅ Resultado esperado

| Selector | Elementos que elige |
|---|---|
| `a[href]` | 13 |
| `a[target="_blank"]` | 1 |
| `a[href^="https"]` | 2 |
| `a[href$=".pdf"]` | 1 |
| `a[href*="proyectos"]` | 5 |
| `input[type="email"]` | 1 |

- El enlace de **MDN** se ve en **verde** (`rgb(22, 163, 74)`) y con fondo **crema** (abre en una pestaña nueva).
- El enlace del **PDF** se ve en **rojo** (`rgb(220, 38, 38)`).
- El enlace a `proyectos.html` se ve en **azul** (`rgb(37, 99, 235)`) con fondo **celeste** (`rgb(219, 234, 254)`).
- El enlace `#contacto` se ve en **azul**, sin fondo.
- El campo de correo tiene fondo **celeste**.

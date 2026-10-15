# 📘 Ejemplo 06 — Pseudoclases de estado

## 🧱 Situación inicial

Lucía quiere que su sitio **responda** a lo que hace quien lo visita: que un enlace cambie al pasar el cursor o al recibir el foco, que
un botón se vea distinto mientras se presiona, que la etiqueta de una casilla marcada se destaque y que un campo deshabilitado se note.
Usa **pseudoclases** en `laboratorio-pseudoclases.html`.

## 💻 Código

El formulario de la página (de `laboratorio.html`):

```html
<h2 id="contacto">Contacto</h2>
<form method="get">
  <p>
    <label for="nombre">Nombre</label>
    <input type="text" id="nombre" name="nombre">
  </p>
  <p>
    <label for="correo">Correo</label>
    <input type="email" id="correo" name="correo">
  </p>
  <p>
    <input type="checkbox" id="novedades" name="novedades" value="si" checked>
    <label for="novedades">Quiero recibir novedades</label>
  </p>
  <p>
    <label for="codigo">Código (no disponible)</label>
    <input type="text" id="codigo" name="codigo" disabled>
  </p>
  <p>
    <button type="button" class="boton">Probar</button>
  </p>
</form>
```

La hoja `css/pseudoclases.css`:

```css
/* Orden recomendado para los enlaces: normal, visitado, pasar el cursor, foco */
a {
  color: #2563eb;
}

a:visited {
  color: #7c3aed;
}

a:hover {
  color: #dc2626;
}

a:focus {
  background-color: #fef3c7;
}

/* :active: mientras se presiona el botón */
.boton:active {
  background-color: #16a34a;
}

/* :checked: la etiqueta de una casilla marcada */
input:checked + label {
  color: #16a34a;
}

/* :disabled: un campo que no se puede usar */
input:disabled {
  background-color: #e5e7eb;
}
```

## 🔍 Análisis paso a paso

1. **`:hover`.** `a:hover` cambia el color del enlace a **rojo** mientras el cursor está encima.
2. **`:focus`.** `a:focus` pone un fondo **crema** al enlace que recibe el foco (por clic, por toque o con la tecla Tab). No se quita el contorno del
   navegador: el fondo se **suma** a él.
3. **`:active`.** `.boton:active` pone el fondo **verde** mientras se presiona el botón.
4. **`:checked`.** `input:checked + label` elige la etiqueta que viene justo después de una casilla marcada. La casilla de novedades viene marcada
   (`checked`), así que su etiqueta se ve **verde**.
5. **`:disabled`.** `input:disabled` da fondo **gris** al campo «Código», que está deshabilitado.
6. **`:visited`.** `a:visited` pinta de violeta los enlaces visitados. Por privacidad, el navegador limita este estado (solo permite cambiar colores) y
   las herramientas de lectura de estilos informan el color **sin visitar**: por eso **no se puede comprobar** con una prueba automática.
7. **El orden.** Las reglas de enlace van en el orden recomendado: normal (`a`), visitado, cursor, foco. Al valer lo mismo, gana la última: si
   `a:hover` estuviera antes de `a:visited`, un enlace visitado no cambiaría al pasar el cursor.
8. **Cómo se probó.** Los estados `:hover`, `:focus` y `:active` no se pueden provocar sin un puntero real: se **simularon** agregando una clase a
   los elementos antes de leer los estilos. `:checked` y `:disabled` son estados reales de la página.
9. **Cuidado con la accesibilidad.** `:hover` no existe en pantallas táctiles: nada importante debe depender de él. Y el foco nunca se
   quita sin reemplazarlo por otro indicador visible.

## ✅ Resultado esperado

| Estado | Elemento | Resultado |
|---|---|---|
| Normal | El enlace «Inicio» | Azul (`rgb(37, 99, 235)`), sin fondo |
| `:hover` | «Inicio» | Rojo (`rgb(220, 38, 38)`); otros enlaces siguen azules |
| `:focus` | «Inicio» | Fondo crema (`rgb(254, 243, 199)`); otros enlaces, sin fondo |
| `:active` | El botón «Probar» | Fondo verde (`rgb(22, 163, 74)`); normal: gris claro (`rgb(239, 239, 239)`) |
| `:checked` | Etiqueta «Quiero recibir novedades» | Verde (`rgb(22, 163, 74)`); la etiqueta «Nombre» sigue negra |
| `:disabled` | El campo «Código» | Fondo gris (`rgb(229, 231, 235)`); el campo «Nombre» sigue blanco |

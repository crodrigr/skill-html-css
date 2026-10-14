# 📘 Ejemplo 04 — ¿Qué es un formulario?

## 🧱 Situación inicial

Lucía quiere que quienes visitan su sitio puedan **escribirle**. Hasta ahora sus páginas solo muestran información. Necesita
un **formulario**: un lugar donde la persona ingrese su nombre. Como todavía no tiene un servidor que reciba los datos,
quiere ver al menos **qué se enviaría**. Empieza con el formulario más simple posible: un solo campo.

## 💻 Código

El archivo `formulario-minimo.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Formulario mínimo | Lucía Fernández</title>
  </head>
  <body>
    <h1>Formulario mínimo</h1>

    <form method="get">
      <label for="nombre">Nombre</label>
      <input type="text" id="nombre" name="nombre">
      <input type="submit" value="Enviar">
    </form>
  </body>
</html>
```

## 🔍 Análisis paso a paso

1. **La etiqueta contenedora.** Todo lo que la persona completa va dentro de `<form>`. `method="get"` indica que los datos
   se agregan a la dirección. No lleva `action`.
2. **La información que recoge.** El formulario pide **un dato**: el nombre.
3. **El campo.** `<input type="text" id="nombre" name="nombre">` es un campo de una línea. `name="nombre"` es el **nombre
   con el que viaja el dato**.
4. **La etiqueta del campo.** `<label for="nombre">Nombre</label>` es el texto que ve la persona. `for="nombre"` apunta al
   `id` del campo: al hacer clic en «Nombre», el cursor entra en el campo.
5. **El botón.** `<input type="submit" value="Enviar">` envía el formulario. `value="Enviar"` es el texto del botón.
6. **Probarlo.** Lucía abre la página, escribe «Ana» y aprieta «Enviar».
7. **Qué pasa.** La página **se recarga** y en la barra de direcciones aparece el dato:
   `formulario-minimo.html?nombre=Ana`. El nombre del campo (`nombre`) y lo que se escribió (`Ana`) quedan unidos por `=`
   después de un `?`.
8. **Qué falta.** Para **recibir y guardar** el dato, haría falta un servidor. Eso queda fuera de esta clase: aquí solo
   comprobás qué datos se enviarían, y no sale nada de tu computadora.

## ✅ Resultado esperado

- Una página con el título «Formulario mínimo», una etiqueta «Nombre», un campo de texto y un botón «Enviar».
- Al hacer clic en la palabra «Nombre», el cursor entra en el campo.
- Al escribir «Ana» y enviar, la dirección pasa a terminar en **`?nombre=Ana`** y la página vuelve a mostrarse, con el campo
  vacío.
- Si Lucía **quitara `name="nombre"`**, el dato **no aparecería** en la dirección: un campo sin `name` no se envía.

# 📘 Ejemplo 05 — Input: `type` y `value`

## 🧱 Situación inicial

Lucía ya sabe que un formulario recoge datos. Ahora quiere probar los **tipos de campo esenciales** para ver cómo cambia el
comportamiento de cada uno. Arma una página de práctica, `tipos-de-input.html`, con los siete tipos. Todos los datos son
**de prueba**.

## 💻 Código

El archivo `tipos-de-input.html`:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Tipos de input | Lucía Fernández</title>
  </head>
  <body>
    <h1>Tipos de input</h1>
    <p>Datos de prueba: no escribas datos reales.</p>

    <form method="get">
      <p>
        <label for="usuario">Texto (text)</label>
        <input type="text" id="usuario" name="usuario" value="ana">
      </p>
      <p>
        <label for="correo">Correo (email)</label>
        <input type="email" id="correo" name="correo">
      </p>
      <p>
        <label for="edad">Número (number)</label>
        <input type="number" id="edad" name="edad" value="30">
      </p>
      <p>
        <label for="clave">Contraseña (password)</label>
        <input type="password" id="clave" name="clave">
      </p>
      <p>
        <input type="checkbox" id="acepto" name="acepto" value="si">
        <label for="acepto">Casilla (checkbox)</label>
      </p>
      <p>Opción (radio):</p>
      <p>
        <input type="radio" id="color-azul" name="color" value="azul">
        <label for="color-azul">Azul</label>
        <input type="radio" id="color-verde" name="color" value="verde">
        <label for="color-verde">Verde</label>
      </p>
      <p>
        <input type="submit" value="Enviar">
      </p>
    </form>
  </body>
</html>
```

## 🔍 Análisis paso a paso

1. **Texto.** `type="text"` es un campo de una línea. Lucía le puso `value="ana"`: aparece **ya escrito**. Ese es el valor
   inicial.
2. **Correo.** `type="email"` se ve como un campo de texto, pero el navegador **valida** que tenga forma de correo
   (con una arroba) antes de enviar.
3. **Número.** `type="number"` muestra flechas para subir y bajar, y solo admite números. Con `value="30"` empieza en 30.
4. **Contraseña.** `type="password"` **oculta** lo que se escribe con puntos. Solo oculta en pantalla: **no protege** el dato.
5. **Casilla.** `type="checkbox"` se marca o se desmarca. `value="si"` es lo que **se envía si está marcada**.
6. **Opciones.** Los dos `type="radio"` comparten `name="color"`: forman un grupo y se puede marcar **uno solo**. Cada uno tiene
   su `value`, que es lo que se envía.
7. **Botón.** `type="submit"` envía el formulario. Su `value="Enviar"` es el texto que se ve en el botón.
8. **Probar con datos.** Lucía escribe «ana», `ana@example.com`, 30, la contraseña de prueba `prueba123`, marca la casilla y
   elige «Verde». Aprieta «Enviar».
9. **Mirar la dirección.** Queda así (con `&` entre un dato y otro):
   `tipos-de-input.html?usuario=ana&correo=ana%40example.com&edad=30&clave=prueba123&acepto=si&color=verde`.
   La arroba se envía como `%40`.
10. **Mirar lo que no viaja.** Si no marca la casilla ni elige un color, **`acepto` y `color` no aparecen** en la dirección: lo
    que no está marcado no se envía.
11. **La validación.** Si en «Correo» escribe `noesuncorreo`, el navegador **no envía** el formulario y avisa del error.
12. **El cuidado con la contraseña.** La clave **apareció en la dirección**: con `method="get"`, todo queda visible. Por eso
    nunca se prueba con una contraseña real, y por eso los datos sensibles se envían de otra forma, con un servidor (fuera de
    esta clase).

## ✅ Resultado esperado

- Una página con siete campos: texto con «ana», correo, número con 30, contraseña, casilla, dos opciones y un botón.
- Al escribir la contraseña se ven **puntos**, no las letras.
- Al enviar con todo completo, la dirección termina en
  `?usuario=ana&correo=ana%40example.com&edad=30&clave=prueba123&acepto=si&color=verde`.
- Al enviar sin marcar la casilla ni las opciones, la dirección termina en `?usuario=ana&correo=ana%40example.com&edad=30&clave=`
  (la clave vacía **sí** viaja, vacía).
- Con un correo sin forma de correo, **no se envía** y el navegador avisa.

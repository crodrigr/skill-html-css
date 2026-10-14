# 📝 Quiz 01 — HTML para presentación

8 ítems. Sin respuestas (ver `material/soluciones/soluciones-quiz.md` para la clave, material
exclusivamente docente).

---

**1. [selección múltiple]** 🔘
¿Para qué sirve la etiqueta `<hr>`?

A. Para marcar un cambio de tema, que el navegador muestra como una línea horizontal.
B. Para crear un título de segundo nivel.
C. Para agrupar los elementos de una lista.
D. Para marcar una cita extensa.

_RA: RA-1_

---

**2. [selección múltiple]** 🔘
En una tabla, ¿qué etiqueta se usa para una celda de **encabezado**?

A. `<td>`
B. `<tr>`
C. `<th>`
D. `<caption>`

_RA: RA-2_

---

**3. [identificación de resultado]** 🔍
Mirá esta tabla. ¿Cómo se ve en el navegador?

```html
<table>
  <tr>
    <td colspan="2">Horarios</td>
  </tr>
  <tr>
    <td>Mañana</td>
    <td>9 a 12 h</td>
  </tr>
</table>
```

A. La primera fila tiene una celda que ocupa el ancho de las dos columnas; la segunda tiene dos celdas.
B. La primera fila tiene dos celdas y la segunda tiene una celda que ocupa dos filas.
C. La tabla tiene una sola columna.
D. «Horarios» aparece como título de la página.

_RA: RA-2_

---

**4. [selección múltiple]** 🔘
¿Cuál es la forma correcta de escribir una **sublista** dentro de una lista?

A. Poner el `<ul>` interno directamente dentro del `<ul>` exterior, entre dos `<li>`.
B. Poner el `<ul>` interno dentro de un `<li>` del `<ul>` exterior.
C. Poner el `<ul>` interno antes del `<ul>` exterior.
D. Reemplazar los `<li>` de la sublista por `<p>`.

_RA: RA-3_

---

**5. [corrección de errores]** 🛠️
Esta cita tiene **dos errores**. Encontralos y explicá cómo corregir cada uno.

```html
<blockquote>
  <p>El sitio quedó mejor de lo que imaginaba.</p>
</blockquote>
<p>— <cite>Marta Gómez</cite></p>
<p>Otra clienta dijo que <q>"explica todo con paciencia"</q>.</p>
```

_RA: RA-4_

---

**6. [selección múltiple]** 🔘
¿Qué es un formulario en una página web?

A. Una tabla con los datos de la persona que visita la página.
B. Un conjunto de campos con los que la persona ingresa información en la página.
C. Una lista de enlaces a otras páginas.
D. Un comentario que el navegador no muestra.

_RA: RA-5_

---

**7. [identificación de resultado]** 🔍
Este formulario no tiene servidor. Una persona escribe «Ana» en el campo y aprieta «Enviar».

```html
<form method="get">
  <input type="text" name="nombre">
  <input type="number" name="edad" value="30">
  <input type="submit" value="Enviar">
</form>
```

¿Cómo termina la dirección de la página después de enviar?

A. `?nombre=Ana&edad=30`
B. `?Ana&30`
C. `?nombre=Ana&edad=30&submit=Enviar`
D. La dirección no cambia y no se envía nada.

_RA: RA-6_

---

**8. [problema breve]** 🧩
Para cada uno de estos cinco datos, indicá qué `type` de `input` elegirías: (a) el correo de la persona; (b) su edad; (c) si
quiere recibir novedades (sí o no); (d) una sola opción entre «mañana» y «tarde»; (e) una clave de acceso. Y, en una frase,
explicá por qué no conviene probar una clave real con `method="get"`.

_RA: RA-6_

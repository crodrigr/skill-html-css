# 🟡 Intermedio 02 — Completá el formulario de reserva

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-5, RA-6

## 🧱 Estado inicial

Abrí [`reserva-base.html`](../recursos/portafolio-inicial/reserva-base.html) de la carpeta `portafolio-inicial`. Mateo
quiere que sus clientes reserven una sesión desde su página. El formulario ya tiene las etiquetas (`label`) de cada dato, pero
los campos `<input>` están **vacíos**: sin tipo, sin nombre, sin valor, y falta el botón de envío.

Los datos que hay que pedir son:

| Dato | Cómo se completa | Nombre sugerido |
|---|---|---|
| Nombre | Texto libre | `nombre` |
| Correo | Un correo | `correo` |
| Tipo de sesión | **Una sola** opción entre retrato, evento y álbum | `tipo` |
| Cantidad de fotos | Un número, con **10** como valor sugerido | `fotos` |
| Recibir ofertas | Sí o no | `ofertas` |

## 🛠️ Proceso esperado

1. Para cada `<input>`, agregar el **`id`** que coincide con el `for` de su etiqueta.
2. Elegir el **`type`** adecuado para cada dato.
3. Agregar el **`name`** sugerido. Las tres opciones del tipo de sesión comparten el mismo `name`.
4. Agregar el **`value`** que corresponda: el valor que se envía en cada opción (`retrato`, `evento`, `album`) y en la
   casilla (`si`), y el valor sugerido del número (10).
5. Agregar el **botón de envío**, con el texto «Reservar».
6. Probar: completar con datos inventados («Ana Pérez», `ana@example.com`), elegir «Evento», poner 20 fotos, marcar las
   ofertas y enviar. Anotar la dirección que aparece.
7. Probar de nuevo **sin elegir tipo ni marcar las ofertas**. Anotar la dirección y explicar qué datos no viajaron.

## ✅ Resultado esperado

- ☑️ Siete campos `input` completos y un botón de envío.
- ☑️ Los tipos correctos: texto, correo, tres opciones, número y casilla.
- ☑️ Las dos direcciones anotadas y una explicación de una frase sobre lo que no viajó.
- ☑️ El documento pasa la revisión de estructura sin errores.

## 🚧 Restricciones

- 🚫 No agregues campos nuevos ni cambies las etiquetas.
- 🚫 No agregues `action`: el formulario sigue sin servidor.
- 🚫 Usá solo datos inventados.
- 🚫 No agregues CSS ni JavaScript.

## 🎓 Resultados de aprendizaje

- RA-5: Explicar qué es un formulario y qué información recoge.
- RA-6: Escribir un formulario básico con `form` e `input`, usando los atributos `type` y `value`.

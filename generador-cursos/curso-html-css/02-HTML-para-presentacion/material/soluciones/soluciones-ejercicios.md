# 🔑 Soluciones — Ejercicios de la Clase 02 (material docente)

No compartir este archivo con los estudiantes.

Todo el código de estas soluciones se validó con la revisión de estructura del curso y se abrió en Chrome; los formularios
se probaron enviándolos. Los ejercicios **cerrados** tienen una sola respuesta defendible.

---

## 🟢 Básico 01 — Separadores y listas

### ✅ Respuesta o criterio

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Servicios | Mateo Ruiz</title>
  </head>
  <body>
    <h1>Servicios de Mateo Ruiz</h1>

    <h2>Lo que fotografío</h2>
    <ul>
      <li>Retratos</li>
      <li>Eventos
        <ul>
          <li>Bodas</li>
          <li>Cumpleaños</li>
        </ul>
      </li>
      <li>Álbumes impresos</li>
    </ul>

    <hr>

    <h2>Cómo es una sesión</h2>
    <ol>
      <li>Coordinamos la fecha</li>
      <li>Hacemos la sesión</li>
      <li>Elijo las mejores fotos</li>
      <li>Entrego el álbum</li>
    </ol>
  </body>
</html>
```

Los servicios y la sublista son **no enumerados** (`ul`): no tienen orden. Los pasos de la sesión son **enumerados** (`ol`):
el orden importa.

### 🔍 Justificación

La sublista de «Bodas» y «Cumpleaños» está **dentro del `li` de «Eventos»**, no directamente dentro del `ul` exterior. El
`hr` marca el cambio de tema entre las dos secciones.

### 🔎 Verificación

Recuento: `h1` = 1, `h2` = 2, `ul` = 2, `ol` = 1, `li` = 9, `hr` = 1. La sublista está dentro de un `li`. La revisión de
estructura pasa sin errores.

---

## 🟢 Básico 02 — Armá una tabla de precios

### ✅ Respuesta o criterio

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Precios | Mateo Ruiz</title>
  </head>
  <body>
    <h1>Precios</h1>

    <table>
      <caption>Precios por sesión</caption>
      <thead>
        <tr>
          <th>Sesión</th>
          <th>Precio en USD</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Retrato</td>
          <td>70</td>
        </tr>
        <tr>
          <td>Evento</td>
          <td>150</td>
        </tr>
        <tr>
          <td>Álbum impreso</td>
          <td>90</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

### 🔍 Justificación

Los encabezados («Sesión» y «Precio en USD») son `th` dentro de `thead`; los datos son `td` dentro de `tbody`; el título es
un `caption`, que va primero dentro de la tabla.

### 🔎 Verificación

Recuento: `table` = 1, `caption` = 1, `thead` = 1, `tbody` = 1, `th` = 2, `td` = 6 (tres filas de dos). Los datos
coinciden con los del enunciado. La revisión de estructura pasa sin errores.

---

## 🟡 Intermedio 01 — Completá las tablas y marcá las citas

### ✅ Respuesta o criterio

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Paquetes y opiniones | Mateo Ruiz</title>
  </head>
  <body>
    <h1>Paquetes y opiniones</h1>

    <h2>Paquetes</h2>
    <table>
      <caption>Paquetes de fotos</caption>
      <thead>
        <tr>
          <th>Paquete</th>
          <th>Fotos</th>
          <th>Precio en USD</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Básico</td>
          <td>10</td>
          <td>70</td>
        </tr>
        <tr>
          <td>Completo</td>
          <td>25</td>
          <td>120</td>
        </tr>
        <tr>
          <td>Premium</td>
          <td>40</td>
          <td>160</td>
        </tr>
      </tbody>
      <tfoot>
        <tr>
          <td colspan="3">Los precios no incluyen el álbum impreso</td>
        </tr>
      </tfoot>
    </table>

    <h2>Horarios</h2>
    <table>
      <caption>Horarios de atención</caption>
      <tbody>
        <tr>
          <th rowspan="2">Sábados</th>
          <td>Mañana</td>
          <td>10 a 13 h</td>
        </tr>
        <tr>
          <td>Tarde</td>
          <td>15 a 19 h</td>
        </tr>
      </tbody>
    </table>

    <h2>Opiniones</h2>
    <blockquote cite="https://mateo-ruiz.example/opiniones/laura">
      <p>Mateo logró que mi boda se vea tal como la recordamos. Las fotos son naturales y se nota el cuidado en cada detalle.</p>
    </blockquote>
    <p>— Laura Díaz, novia</p>
    <p>Otro cliente dijo que <q cite="https://mateo-ruiz.example/opiniones/diego">se nota el cuidado en cada foto</q>.</p>
    <p>Para prepararte, leé <cite>Guía para preparar una sesión</cite>.</p>
  </body>
</html>
```

### 🔍 Justificación

La aclaración pasa al `tfoot` en una celda con `colspan="3"` (la tabla tiene tres columnas). «Sábados» lleva `rowspan="2"` y
la segunda fila tiene **una celda menos**. La opinión larga es un `blockquote` con `cite`; la atribución queda **fuera** de
él. La frase corta es un `q` (sin comillas escritas a mano). El título de la guía es `cite`; el nombre de Laura no lo es,
porque `cite` es para títulos de obras.

### 🔎 Verificación

Recuento: `table` = 2, `caption` = 2, `thead` = 1, `tfoot` = 1, `blockquote` = 1, `q` = 1, `cite` = 1. El `colspan` vale 3
y el `rowspan`, 2. La revisión de estructura pasa sin errores.

---

## 🟡 Intermedio 02 — Completá el formulario de reserva

### ✅ Respuesta o criterio

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Reserva | Mateo Ruiz</title>
  </head>
  <body>
    <h1>Reservá tu sesión</h1>
    <p>Datos de prueba: este formulario no se envía a ningún servidor.</p>

    <form method="get">
      <p>
        <label for="nombre">Nombre</label>
        <input type="text" id="nombre" name="nombre">
      </p>
      <p>
        <label for="correo">Correo</label>
        <input type="email" id="correo" name="correo">
      </p>
      <p>Tipo de sesión:</p>
      <p>
        <input type="radio" id="tipo-retrato" name="tipo" value="retrato">
        <label for="tipo-retrato">Retrato</label>
        <input type="radio" id="tipo-evento" name="tipo" value="evento">
        <label for="tipo-evento">Evento</label>
        <input type="radio" id="tipo-album" name="tipo" value="album">
        <label for="tipo-album">Álbum</label>
      </p>
      <p>
        <label for="fotos">Cantidad de fotos</label>
        <input type="number" id="fotos" name="fotos" value="10">
      </p>
      <p>
        <input type="checkbox" id="ofertas" name="ofertas" value="si">
        <label for="ofertas">Quiero recibir ofertas</label>
      </p>
      <p>
        <input type="submit" value="Reservar">
      </p>
    </form>
  </body>
</html>
```

| Dato | `type` | `name` | `value` |
|---|---|---|---|
| Nombre | `text` | `nombre` | — |
| Correo | `email` | `correo` | — |
| Tipo de sesión | `radio` (tres) | `tipo` (el mismo) | `retrato`, `evento`, `album` |
| Cantidad de fotos | `number` | `fotos` | `10` |
| Recibir ofertas | `checkbox` | `ofertas` | `si` |
| Botón | `submit` | — | `Reservar` |

**Direcciones** (probadas en Chrome):

- Con Ana Pérez, `ana@example.com`, «Evento», 20 fotos y ofertas marcadas:
  `?nombre=Ana+P%C3%A9rez&correo=ana%40example.com&tipo=evento&fotos=20&ofertas=si`.
- Sin elegir tipo ni marcar ofertas: `?nombre=Ana&correo=ana%40example.com&fotos=10`. **No viajaron `tipo` ni `ofertas`**:
  las opciones y las casillas sin marcar no se envían.

### 🔍 Justificación

Cada dato lleva el `type` que describe su comportamiento. Los `radio` de un grupo comparten `name` y cada uno lleva su
`value`; la casilla también necesita `value`. El `value="10"` del número es el valor inicial.

### 🔎 Verificación

La revisión de estructura pasa sin errores (cada `label for` coincide con un `id`, ningún `input` sin `name`). Las dos
direcciones coinciden con las anotadas.

---

## 🔴 Desafío 01 — La página de servicios y reserva de Mateo

### ✅ Respuesta o criterio

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Servicios y reserva | Mateo Ruiz</title>
  </head>
  <body>
    <header id="arriba">
      <h1>Servicios y reserva</h1>
    </header>

    <main>
      <!-- Servicios: lista no enumerada con una sublista -->
      <section>
        <h2>Servicios</h2>
        <ul>
          <li>Retratos</li>
          <li>Eventos
            <ul>
              <li>Bodas</li>
              <li>Cumpleaños</li>
            </ul>
          </li>
          <li>Álbumes impresos</li>
        </ul>
      </section>

      <hr>

      <!-- Cómo reservar: lista enumerada, el orden importa -->
      <section>
        <h2>Cómo reservar</h2>
        <ol>
          <li>Elegís el tipo de sesión</li>
          <li>Completás el formulario</li>
          <li>Mateo te escribe para coordinar</li>
        </ol>
      </section>

      <hr>

      <!-- Precios: tabla con pie que ocupa las dos columnas -->
      <section>
        <h2>Precios</h2>
        <table>
          <caption>Precios por sesión</caption>
          <thead>
            <tr>
              <th>Sesión</th>
              <th>Precio en USD</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Retrato</td>
              <td>70</td>
            </tr>
            <tr>
              <td>Evento</td>
              <td>150</td>
            </tr>
            <tr>
              <td>Álbum</td>
              <td>90</td>
            </tr>
          </tbody>
          <tfoot>
            <tr>
              <td colspan="2">Todos los precios incluyen la edición básica</td>
            </tr>
          </tfoot>
        </table>
      </section>

      <hr>

      <section>
        <h2>Opinión</h2>
        <blockquote cite="https://mateo-ruiz.example/opiniones/laura">
          <p>Mateo me ayudó a elegir las mejores fotos y el álbum quedó hermoso.</p>
        </blockquote>
        <p>— Laura Díaz, novia</p>
      </section>

      <hr>

      <!-- Reserva: formulario con method="get" y sin action -->
      <section>
        <h2>Reserva</h2>
        <form method="get">
          <p>
            <label for="nombre">Nombre</label>
            <input type="text" id="nombre" name="nombre">
          </p>
          <p>
            <label for="correo">Correo</label>
            <input type="email" id="correo" name="correo">
          </p>
          <p>Tipo de sesión:</p>
          <p>
            <input type="radio" id="tipo-retrato" name="tipo" value="retrato">
            <label for="tipo-retrato">Retrato</label>
            <input type="radio" id="tipo-evento" name="tipo" value="evento">
            <label for="tipo-evento">Evento</label>
            <input type="radio" id="tipo-album" name="tipo" value="album">
            <label for="tipo-album">Álbum</label>
          </p>
          <p>
            <label for="fotos">Cantidad de fotos</label>
            <input type="number" id="fotos" name="fotos" value="10">
          </p>
          <p>
            <input type="checkbox" id="ofertas" name="ofertas" value="si">
            <label for="ofertas">Quiero recibir ofertas</label>
          </p>
          <p>
            <input type="submit" value="Reservar">
          </p>
        </form>
      </section>
    </main>

    <footer>
      <p><a href="#arriba">Volver arriba</a></p>
    </footer>
  </body>
</html>
```

### 🔍 Justificación

La estructura usa `header`, `main` con cinco `section` y `footer`; no queda ningún `div`. Entre las secciones hay cuatro
`hr`. La sublista va dentro del `li` de «Eventos». La tabla tiene un pie con `colspan="2"` porque tiene dos columnas. La cita
lleva `cite` y su atribución fuera. El formulario usa `method="get"`, sin `action`.

### 🔎 Verificación

Se cumplen los 13 casos de prueba:

| # | Resultado |
|---|---|
| 1 | Un `<main>` y un `<h1>` dentro de `<header>` |
| 2 | Cinco `<section>` con su `<h2>` |
| 3 | Cuatro `<hr>` |
| 4 | Dos `<ul>` (sublista dentro de un `<li>`) y un `<ol>` con tres `<li>` |
| 5 | `caption`, `thead` con dos `th`, `tbody` con tres filas y `tfoot` con `colspan="2"` |
| 6 | Un `<blockquote>` con `cite` y la atribución fuera |
| 7 | `method="get"`, sin `action`, tres `radio` con `name="tipo"` |
| 8 | Cada `label for` coincide con un `id` |
| 9 | Envío completo: `?nombre=Ana+P%C3%A9rez&correo=ana%40example.com&tipo=evento&fotos=20&ofertas=si` |
| 10 | Sin tipo ni ofertas: `?nombre=Ana&correo=ana%40example.com&fotos=10` |
| 11 | Con un correo inválido el navegador no envía el formulario |
| 12 | Cero `<div>` |
| 13 | La revisión de estructura da 0 errores |

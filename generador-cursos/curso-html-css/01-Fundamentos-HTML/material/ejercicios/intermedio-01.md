# 🟡 Intermedio 01 — Conectá las páginas de Mateo

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-5

## 🧱 Estado inicial

Abrí [`index.html`](../recursos/portafolio-inicial/index.html) de la carpeta `portafolio-inicial`. Es la página de inicio
de Mateo, con dos secciones (`servicios` y `contacto`, que ya tienen su `id`), pero **no tiene ningún enlace**. En la
misma carpeta están `galeria.html` y `sobre-mi.html`.

Además, un cliente le pasó esta dirección:

`https://mateo-ruiz.example/galeria/bodas.html?anio=2025&tipo=color#album-3`

## 🛠️ Proceso esperado

**Parte A — Enlazar.** En `index.html`:

1. Convertí la línea «Inicio | Galería | Sobre mí» en tres enlaces a `index.html`, `galeria.html` y `sobre-mi.html`.
2. Agregá, al lado, un enlace «Servicios» y otro «Contacto» que salten a sus secciones de la misma página.
3. Convertí «Wikipedia, artículo “Fotografía”» en un enlace a `https://es.wikipedia.org/wiki/Fotograf%C3%ADa` que se abra
   en una **pestaña nueva** con `rel="noopener"`.

**Parte B — Analizar.** Escribí cada parte de la dirección del cliente: protocolo, dominio, ruta, parámetros (con sus
nombres y valores) y ancla. Indicá además si tiene puerto.

**Parte C — Responder.** ¿Qué `href` usarías en `galeria.html` para volver al inicio? ¿Y cuál desde una página que
estuviera en una subcarpeta `fotos/` para llegar a `index.html`?

## ✅ Resultado esperado

- ☑️ Cinco enlaces que funcionan (tres de páginas, dos de anclas) y uno externo que abre una pestaña nueva.
- ☑️ La dirección dividida en sus partes, con los dos parámetros y su ancla.
- ☑️ Dos rutas relativas correctas.

## 🚧 Restricciones

- 🚫 Los enlaces a las páginas del sitio usan rutas relativas, sin dominio.
- 🚫 No cambies los `id` existentes.
- 🚫 No uses fragmentos de texto en este ejercicio.

## 🎓 Resultados de aprendizaje

- RA-5: Crear hipervínculos e identificar las partes de una dirección web.

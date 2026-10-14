# 🔑 Soluciones — Quiz 01 de la Clase 01 (material docente)

No compartir este archivo con los estudiantes.

| Ítem | Tipo | Respuesta correcta | RA |
|---|---|---|---|
| 1 | Selección múltiple | **B** | RA-1 |
| 2 | Selección múltiple | **A** | RA-2 |
| 3 | Identificación de resultado | **A** | RA-4 |
| 4 | Selección múltiple | **C** | RA-5 |
| 5 | Selección múltiple | **B** | RA-3 |
| 6 | Identificación de resultado | **B** | RA-5 |
| 7 | Corrección de errores | Ver abajo | RA-6 |
| 8 | Problema breve | Ver abajo | RA-7 |

## Justificaciones

**1. B.** HTML5 es un lenguaje de **marcado**: describe estructura y significado. No calcula ni decide (A), no es un
navegador (C) ni un editor (D).

**2. A.** Para HTML alcanza con un editor de código (por ejemplo, VS Code) y un navegador. Un servidor, una base de
datos o un compilador no son necesarios.

**3. A.** `<del>` tacha el precio anterior e `<ins>` marca el nuevo; `<ul>` con `<li>` es una lista con viñetas (la
numerada sería `<ol>`).

**4. C.** `?tema=html` son los **parámetros** (*query string*): empiezan con `?`. El protocolo es `https://`, la ruta
`/blog/entrada.html` y el ancla `#comentarios`.

**5. B.** Las etiquetas deben cerrarse en orden inverso al que se abrieron: `<strong>` se abre dentro de `<p>` y se
cierra antes que `</p>`. A y D solapan las etiquetas y C deja `strong` sin cerrar.

**6. B.** Los fragmentos de texto son una función del navegador: si no se admite, se ignora el fragmento y se abre la
página desde arriba, sin error.

**7. Dos errores** (se aceptan en cualquier orden):

1. La **carpeta** está mal escrita: es `imagenes`, no `imagen` → `src="imagenes/foto-mateo.png"`.
2. Falta el atributo **`alt`** con la descripción de la imagen → por ejemplo, `alt="Retrato de Mateo sonriendo"`.

Código corregido: `<img src="imagenes/foto-mateo.png" alt="Retrato de Mateo sonriendo">`.

**8. Respuesta esperada:** cabecera con el menú → `<header>` (con `<nav>` para el menú); contenido principal →
`<main>`; pie → `<footer>`. Se sigue usando `div` **cuando se necesita agrupar elementos sin significado propio** (por
ejemplo, para darles estilo) y ninguna etiqueta semántica lo describe.

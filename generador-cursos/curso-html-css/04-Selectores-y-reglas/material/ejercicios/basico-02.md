# 🟢 Básico 02 — Renombrá las clases con BEM

> 🟢 **Nivel:** Básico · 🎓 **Resultados de aprendizaje:** RA-3

## 🧱 Estado inicial

Abrí [`basico-02.html`](../recursos/portafolio-inicial/basico-02.html) y su hoja
[`basico-02.css`](../recursos/portafolio-inicial/css/basico-02.css), de la carpeta `portafolio-inicial`. La página de Mateo tiene dos
«fotos del mes», cada una con una imagen, un título, el autor y un botón. Las clases funcionan, pero sus nombres no dicen a qué
componente pertenecen:

| Clase actual | Qué es |
|---|---|
| `caja` | La tarjeta completa (el **bloque**) |
| `destacada` | Una variante de la tarjeta: la de la foto destacada |
| `img` | La imagen de la tarjeta |
| `t` | El título de la tarjeta |
| `autor` | El autor, de la tarjeta |
| `btn` | El botón (el enlace) de la tarjeta |
| `btn-grande` | Una variante del botón: el botón grande |

## 🛠️ Proceso esperado

1. Elegí el nombre del **bloque**: `foto`.
2. Escribí el nombre BEM de cada clase de la tabla, con la convención de esta clase (elementos con `__` y modificadores con `--`).
3. Cambiá los nombres **en el HTML y en la hoja de estilos**. Recordá que un modificador va **junto** a la clase de su bloque o elemento.
4. Comprobá que la página **se ve igual** que antes.
5. Respondé: ¿por qué `foto__boton` y no `foto__enlace__boton`? ¿Qué cambia en la convención oficial de bem.info respecto de los modificadores?

## ✅ Resultado esperado

- ☑️ Los siete nombres BEM escritos en una lista.
- ☑️ El HTML y la hoja actualizados, y la página con el mismo aspecto.
- ☑️ Dos respuestas de una o dos frases.

## 🚧 Restricciones

- 🚫 Usá el bloque `foto`.
- 🚫 Nombres en minúsculas y, si fueran varias palabras, separadas con guion.
- 🚫 No cambies el contenido de la página ni sus estilos: solo los nombres de las clases.

## 🎓 Resultados de aprendizaje

- RA-3: Nombrar las clases de un proyecto con la metodología BEM (bloque, elemento y modificador).

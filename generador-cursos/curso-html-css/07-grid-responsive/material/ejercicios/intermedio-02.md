# 🟡 Intermedio 02 — Dos consultas de medios

> 🟡 **Nivel:** Intermedio · 🎓 **Resultados de aprendizaje:** RA-6, RA-7 · 🗓️ **Sesión 2**

## 🧱 Estado inicial

Abrí [`intermedio-02.html`](../recursos/portafolio-inicial/intermedio-02.html) y su hoja [`css/intermedio-02.css`](../recursos/portafolio-inicial/css/intermedio-02.css), de la carpeta `portafolio-inicial`. La hoja ya tiene la preparación previa, un `.titulo` de `1.25rem` y una `.galeria` de **una columna** con `gap: 24px` y ocho `.foto`. Es el diseño del teléfono (móvil primero).

## 🛠️ Proceso esperado

Agregá a la hoja **dos consultas de medios con `min-width`**, escritas de menor a mayor:

- **Desde `600px`:** la galería con dos columnas iguales y el título en `1.75rem`.
- **Desde `900px`:** la galería con cuatro columnas iguales y el título en `2.25rem`.

Comprobá en cada ventana (sin barra de desplazamiento vertical):

| Ventana | `.galeria` (columnas calculadas) | `.titulo` |
|---|---|---|
| `500px` | `500px` | `20px` |
| `599px` | `599px` | `20px` |
| `600px` | `288px 288px` | `28px` |
| `899px` | `437.5px 437.5px` | `28px` |
| `900px` | `207px 207px 207px 207px` | `36px` |
| `1200px` | `282px 282px 282px 282px` | `36px` |

**Parte B.** Respondé:

1. ¿Por qué la consulta de `900px` tiene que ir **después** de la de `600px`?
2. ¿Qué pasaría en una ventana de `1200px` si escribieras las dos consultas en el orden inverso?
3. ¿Qué otra técnica, sin consultas de medios, haría que las columnas se ajusten solas, y en qué caso no alcanzaría?

## ✅ Resultado esperado

- ☑️ Dos consultas de medios con las reglas pedidas y los valores de la tabla.
- ☑️ Una respuesta de una o dos frases a cada pregunta de la Parte B.
- ☑️ El HTML sin cambios.

## 🚧 Restricciones

- 🚫 No cambies el HTML ni los estilos base de la hoja de partida.
- 🚫 Usá solo `min-width` (nada de `max-width`).
- 🚫 No uses `!important` ni el atributo `style`.

## 🎓 Resultados de aprendizaje

- RA-6: Aplicar la estrategia móvil primero.
- RA-7: Escribir consultas de medios con `min-width` y entender el orden.

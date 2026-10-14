# 🔴 Desafío 01 — Dale estilo a la página de Mateo

> 🔴 **Nivel:** Desafío · 🎓 **Resultados de aprendizaje:** RA-1, RA-2, RA-3, RA-4, RA-5, RA-6, RA-7, RA-8

## 🧱 Estado inicial

Abrí [`desafio.html`](../recursos/portafolio-inicial/desafio.html) de la carpeta `portafolio-inicial`: es la página de inicio de
Mateo con cabecera, navegación, tres secciones (`portada`, `servicios` y `opiniones`) y pie. Ya tiene el enlace a
[`css/desafio.css`](../recursos/portafolio-inicial/css/desafio.css), que está **vacío**. La paleta de Mateo es gris oscuro `#111827`,
verde `#16a34a` y crema `#fef3c7`. En `imagenes/` están `patron.png` y `portada.png`.

## 🛠️ Proceso esperado

1. **Variables.** Definí en `:root` las tres variables de la paleta y usalas en **todas** las reglas.
2. **Base.** El `body` lleva texto gris oscuro sobre fondo crema. Los `h2` van en gris oscuro y los enlaces, en verde.
3. **Título con gradiente.** El `h1` lleva texto crema sobre un gradiente lineal de izquierda a derecha, de gris oscuro a verde.
4. **Portada.** La sección `#portada` lleva `portada.png` como fondo, una sola vez, cubriendo toda la sección; con un fondo crema de
   respaldo.
5. **Clase.** Los párrafos `.destacado` van en verde sobre fondo blanco.
6. **Citas con transparencia.** El `blockquote` lleva el verde con un 20% de transparencia como fondo.
7. **Pie.** El `footer` repite `patron.png` como fondo, con un fondo crema de respaldo.
8. **Opacidad.** La letra chica (`small`) se ve al 70% de opacidad.
9. **Revisar.** Con las herramientas del navegador, comprobá cada valor y que no haya ninguna declaración ignorada.
10. **Comentar.** Agregá un comentario antes de cada bloque de reglas.

## ✅ Resultado esperado

- ☑️ Una hoja con variables, comentarios y reglas con la sintaxis correcta.
- ☑️ El aspecto descrito en cada paso.
- ☑️ El HTML sin cambios.
- ☑️ La hoja pasa la revisión de estructura sin errores.

## 🚧 Restricciones

- 🚫 No cambies el HTML (solo está permitido lo que ya trae).
- 🚫 Cada color de la paleta se escribe **una sola vez**, en `:root` (la única excepción es el color con transparencia del `blockquote`, que se escribe con canal alfa).
- 🚫 No uses `!important`, ni `style`, ni un bloque `<style>`.
- 🚫 Solo selectores de elemento, clase, identificador y agrupación; solo gradientes lineales y radiales.
- 🚫 No agregues propiedades de tipografía ni de disposición.

## 🎓 Resultados de aprendizaje

- RA-1 y RA-2: Una hoja de estilos externa, enlazada a la página.
- RA-3: Reglas con la sintaxis correcta, organizadas y comentadas.
- RA-4: Revisión de los estilos con las herramientas del navegador.
- RA-5: Selectores y cascada sin recurrir a `!important`.
- RA-6: Variables CSS.
- RA-7: Colores y transparencia con canal alfa.
- RA-8: Gradiente, imágenes de fondo y opacidad.

## 🧪 Casos de prueba

| # | Comprobación | Resultado esperado |
|---|---|---|
| 1 | `:root` | Define `--color-oscuro`, `--color-verde` y `--color-crema` |
| 2 | `body` | Texto `rgb(17, 24, 39)` y fondo `rgb(254, 243, 199)` |
| 3 | `h1` | Texto `rgb(254, 243, 199)` y `linear-gradient(90deg, rgb(17, 24, 39), rgb(22, 163, 74))` |
| 4 | `h2` | Texto `rgb(17, 24, 39)` |
| 5 | Enlaces | Texto `rgb(22, 163, 74)` |
| 6 | `.destacado` | Texto `rgb(22, 163, 74)` |
| 7 | `#portada` | Imagen de fondo, `no-repeat` y `cover` |
| 8 | `blockquote` | Fondo `rgba(22, 163, 74, 0.2)` |
| 9 | `footer` | Imagen de fondo con `repeat` |
| 10 | `small` | Opacidad `0.7` |
| 11 | Colores de la paleta | Escritos una sola vez, en `:root` (salvo el verde con alfa del `blockquote`) |
| 12 | `!important`, `style` y `<style>` | No aparecen |
| 13 | La revisión de estructura de la hoja | 0 errores |

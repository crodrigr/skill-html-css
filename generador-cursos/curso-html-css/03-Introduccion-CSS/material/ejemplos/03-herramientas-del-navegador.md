# 📘 Ejemplo 03 — Las herramientas del navegador

## 🧱 Situación inicial

Lucía escribió tres reglas en `errores-a-proposito.css` y **ninguna se ve como esperaba**: el título no es rojo, el segundo párrafo no es
azul, y el primero no tiene el fondo que quería. Todavía no sabe qué falló. Va a usar las herramientas para desarrolladores del
navegador para descubrirlo.

## 💻 Código

La hoja de estilos `css/errores-a-proposito.css` (con errores intencionales):

```css
/* Una declaración inválida se ignora y la regla sigue con las demás */
.uno {
  color: #16a34a;
  background-color: colorinexistente;
}

/* En un grupo, un selector mal escrito invalida toda la regla */
.dos, ..mal {
  color: #dc2626;
}

/* Una declaración sin los dos puntos se ignora */
.tres {
  color #2563eb;
  background-color: #fef3c7;
}
```

## 🔍 Análisis paso a paso

1. **Abrir las herramientas.** Con **F12** o **Ctrl + Shift + I** (en Mac, **⌘ + ⌥ + I**), o con clic derecho sobre un elemento y
   *Inspeccionar*.
2. **Inspeccionar un elemento.** Lucía hace clic derecho sobre el primer párrafo y elige *Inspeccionar*. En el panel de estilos
   ve las reglas que lo alcanzan, de la más específica a la menos específica.
3. **Detectar el primer problema.** En la regla `.uno`, la línea `background-color: colorinexistente;` aparece **tachada o marcada
   como inválida**: el navegador no entiende ese valor y la **ignora**. La otra declaración (`color: #16a34a;`) sigue valiendo.
4. **Detectar el segundo.** Al inspeccionar el título, **no aparece** ninguna regla de `.dos`. En el CSS, el selector `..mal` está
   mal escrito (dos puntos): en un **grupo**, un selector inválido hace que **toda la regla se ignore**.
5. **Detectar el tercero.** En `.tres`, la declaración `color #2563eb;` no tiene los dos puntos: se ignora. La otra
   (`background-color`) sí se aplica.
6. **Probar un arreglo en vivo.** En el panel de estilos, Lucía hace clic sobre el valor de `color` y escribe `red`: ve el cambio
   al instante.
7. **Un aviso.** Ese cambio **no modifica el archivo `errores-a-proposito.css`**. Solo es una prueba. Para que se conserve, tiene que
   copiar la corrección al archivo y guardarlo.
8. **Corregir en el archivo.** Quita `colorinexistente`, escribe `.dos, .mal` (con un solo punto) y agrega los dos puntos que faltaban
   en `color: #2563eb;`.
9. **Un valor de respaldo.** Cuando una función es muy nueva y un navegador viejo no la entiende, la declaración se ignora. Por
   eso conviene escribir antes un valor conocido: `background-color: #2563eb;` y, después,
   `background-color: rgb(37 99 235 / 0.9);`. Si el navegador no entiende la segunda, se queda con la primera.

## ✅ Resultado esperado

- Con el archivo **tal como está**: el primer párrafo se ve **verde** (`rgb(22, 163, 74)`) y **sin fondo** (la declaración inválida se
  ignoró); el título `.dos` se ve **negro** (`rgb(0, 0, 0)`: toda la regla se ignoró); el segundo párrafo se ve **negro**
  pero con **fondo crema** (`rgb(254, 243, 199)`).
- Un cambio hecho en las herramientas se ve en pantalla, pero el **archivo no cambia**: al recargar la página, vuelve todo como
  estaba.
- Después de corregir el archivo, el título se ve **rojo**, y el segundo párrafo, **azul**.

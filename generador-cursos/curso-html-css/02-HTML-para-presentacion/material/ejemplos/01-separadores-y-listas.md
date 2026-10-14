# 📘 Ejemplo 01 — Separadores y listas

## 🧱 Situación inicial

Lucía quiere sumar a su sitio una página de **servicios y tarifas**. Tiene el contenido escrito en un documento sin
formato: una lista de servicios (con dos tipos de sitios para negocios), los cuatro pasos de su forma de trabajo y varios
temas que quiere separar. Crea el archivo `servicios.html` con la estructura mínima de la Clase 01 y empieza por las
secciones de **servicios** y **cómo trabajamos**.

## 💻 Código

Las secciones de servicios y de «Cómo trabajamos», con sus separadores (de `servicios.html`):

```html
<section>
  <h2>Servicios</h2>
  <!-- Lista no enumerada: el orden no importa -->
  <ul>
    <li>Sitios para negocios
      <ul>
        <li>Panaderías</li>
        <li>Consultorios</li>
      </ul>
    </li>
    <li>Sitios personales</li>
    <li>Blogs</li>
  </ul>
</section>
```

```html
<hr>
```

```html
<section>
  <h2>Cómo trabajamos</h2>
  <!-- Lista enumerada: el orden sí importa -->
  <ol>
    <li>Hablamos</li>
    <li>Escribo el contenido</li>
    <li>Lo reviso con vos</li>
    <li>Lo publicamos</li>
  </ol>
</section>
```

El archivo completo está en `recursos/portafolio-final/servicios.html`.

## 🔍 Análisis paso a paso

1. **Decidir el tipo de lista.** Los servicios **no tienen un orden**: usa una lista no enumerada, `<ul>`. Los pasos para
   trabajar **sí tienen orden**: usa una lista enumerada, `<ol>`.
2. **Un `<li>` por elemento.** Cada servicio y cada paso van en su propio `<li>`, siempre dentro de `<ul>` o `<ol>`.
3. **Anidar una sublista.** «Sitios para negocios» tiene dos variantes. Lucía abre un `<ul>` nuevo **dentro del `<li>`**
   de «Sitios para negocios», no directamente dentro del `<ul>` exterior.
4. **Cerrar en orden.** Cierra primero el `<ul>` de la sublista, luego el `</li>` y recién después sigue con
   «Sitios personales».
5. **Agregar separadores.** Entre «Servicios» y «Cómo trabajamos» pone un `<hr>`: es un cambio de tema. `<hr>` no lleva
   cierre.
6. **Comentar.** Deja una nota antes de cada lista para recordar por qué eligió ese tipo.
7. **Probar.** Guarda y abre `servicios.html` en el navegador.

## ✅ Resultado esperado

- Una **lista con viñetas** de tres servicios: «Sitios para negocios», «Sitios personales» y «Blogs».
- Bajo «Sitios para negocios», una **sublista con viñetas más adentro**: «Panaderías» y «Consultorios».
- Una **línea horizontal** entre «Servicios» y «Cómo trabajamos».
- Una **lista numerada** del 1 al 4: «Hablamos», «Escribo el contenido», «Lo reviso con vos» y «Lo publicamos».
- Los comentarios **no se ven** en la página.

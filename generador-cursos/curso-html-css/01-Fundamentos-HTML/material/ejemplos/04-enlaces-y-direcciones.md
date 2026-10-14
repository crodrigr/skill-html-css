# 📘 Ejemplo 04 — Enlaces y direcciones

## 🧱 Situación inicial

Las tres páginas de Lucía (`index.html`, `sobre-mi.html` y `proyectos.html`) están en la misma carpeta, pero no están
conectadas. Quiere que desde cualquier página se pueda ir a las otras, y recomendar un sitio de referencia. Además, quiere
entender una dirección larga que le pasó un cliente:

`https://lucia-fernandez.example:443/proyectos/panaderia.html?categoria=web&orden=reciente#resultados`

## 💻 Código

La navegación, que se repite en cada página:

```html
<nav>
  <a href="index.html">Inicio</a> |
  <a href="sobre-mi.html">Sobre mí</a> |
  <a href="proyectos.html">Proyectos</a>
</nav>
```

Un enlace a un sitio externo, que abre en una pestaña nueva:

```html
<a href="https://developer.mozilla.org/es/" target="_blank" rel="noopener">MDN en español</a>
```

## 🔍 Análisis paso a paso

1. **Enlaces a otras páginas del sitio.** Como los archivos están en la misma carpeta, alcanza con la **ruta relativa**
   `sobre-mi.html`. No hace falta escribir el dominio.
2. **Enlace a un sitio externo.** Se usa la dirección **absoluta** completa, con `https://`. Con `target="_blank"` se
   abre en otra pestaña y `rel="noopener"` es una precaución de seguridad.
3. **Analizar la dirección larga.**

   | Parte | Valor |
   |---|---|
   | Protocolo | `https://` |
   | Dominio | `lucia-fernandez.example` |
   | Puerto | `:443` (opcional; es el habitual de `https`) |
   | Ruta | `/proyectos/panaderia.html` |
   | Parámetros | `?categoria=web&orden=reciente` (dos: `categoria` vale `web` y `orden` vale `reciente`) |
   | Ancla | `#resultados` |

4. **Cómo se separan.** Los parámetros empiezan con `?` y se separan entre sí con `&`; el ancla empieza con `#` y va
   siempre al final.
5. **Probarlo.** Lucía abre `index.html`, hace clic en «Sobre mí» y luego en «Proyectos»: cada clic cambia de página.

## ✅ Resultado esperado

- Los enlaces se ven **subrayados y en azul**; al hacer clic en uno de la navegación se abre la página correspondiente.
- «MDN en español» abre el sitio de MDN en una **pestaña nueva**.
- Podés nombrar las seis partes de la dirección larga (protocolo, dominio, puerto, ruta, parámetros y ancla) y decir cuál
  empieza con `?` y cuál con `#`.
- El dominio `.example` no existe: esa dirección es solo para analizar.

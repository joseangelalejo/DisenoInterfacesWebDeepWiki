# Cheatsheet examen - HTML y CSS

Referencia rápida para resolver una actividad de maquetación como `Act10-PracticaCine`.

---

## 1. Antes de escribir código

1. Lee el enunciado entero.
2. Identifica páginas, secciones y elementos repetidos.
3. Mira el wireframe y el mockup.
4. Apunta colores, tipografías, tamaños y espaciados.
5. Decide qué va con Flexbox y qué va con Grid.
6. Diseña primero la versión móvil.

**Regla de oro:** primero HTML semántico, después CSS. No intentes arreglar con CSS una estructura HTML mal planteada.

---

## 2. HTML base

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Web de cine</title>
    <link rel="stylesheet" href="cine.css">
  </head>
  <body>
    <header class="site-header">
      <a class="logo" href="/">Cine</a>
      <nav aria-label="Navegación principal">
        <a href="#cartelera">Cartelera</a>
        <a href="#contacto">Contacto</a>
      </nav>
    </header>

    <main>
      <section id="cartelera" aria-labelledby="titulo-cartelera">
        <h1 id="titulo-cartelera">Cartelera</h1>
        <div class="movie-grid">
          <article class="movie-card">
            <img src="img/pelicula.jpg" alt="Cartel de la película">
            <h2>Película</h2>
            <p>Información de la película.</p>
            <a href="#detalle">Ver más</a>
          </article>
        </div>
      </section>
    </main>

    <footer>
      <p>&copy; 2026</p>
    </footer>
  </body>
</html>
```

### Comprobaciones

- [ ] `lang`, `charset` y `viewport`.
- [ ] Título descriptivo.
- [ ] Un único `main`.
- [ ] Encabezados en orden.
- [ ] `nav` con etiqueta accesible.
- [ ] `article` para tarjetas repetibles.
- [ ] `alt` en imágenes.

---

## 3. Reset y variables

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: system-ui, sans-serif;
  line-height: 1.5;
}

img {
  display: block;
  max-width: 100%;
}

:root {
  --fondo: #f8fafc;
  --superficie: #ffffff;
  --texto: #172033;
  --principal: #172554;
  --acento: #f97316;
  --espacio: 1rem;
  --radio: 0.75rem;
}
```

---

## 4. Contenedor general

```css
.container {
  width: min(100% - 2rem, 1200px);
  margin-inline: auto;
}
```

Es mejor que fijar `width: 1200px`, porque se adapta a pantallas pequeñas.

---

## 5. Cabecera y menú

```css
.site-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  padding: 1rem;
}

.site-header nav {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.site-header a {
  color: inherit;
  text-decoration: none;
}

.site-header a:hover,
.site-header a:focus-visible {
  text-decoration: underline;
}
```

Si en móvil no cabe:

```css
@media (max-width: 700px) {
  .site-header {
    align-items: flex-start;
    flex-direction: column;
  }

  .site-header nav {
    flex-direction: column;
  }
}
```

---

## 6. Grid para tarjetas

```css
.movie-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1.5rem;
}

.movie-card {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  overflow: hidden;
  background: var(--superficie);
  border-radius: var(--radio);
  box-shadow: 0 0.5rem 1.5rem rgb(0 0 0 / 0.12);
}

.movie-card img {
  width: 100%;
  aspect-ratio: 2 / 3;
  object-fit: cover;
}

.movie-card h2,
.movie-card p,
.movie-card a {
  margin-inline: 1rem;
}

.movie-card a {
  margin-bottom: 1rem;
}
```

### Grid manual

```css
.layout {
  display: grid;
  grid-template-columns: 220px 1fr;
  gap: 2rem;
}

.featured {
  grid-column: span 2;
}
```

`repeat(auto-fit, minmax(...))` suele ser la solución más rápida para una galería responsive.

---

## 7. Flexbox: qué propiedad usar

```css
.fila {
  display: flex;
  flex-direction: row;
  justify-content: center; /* eje principal */
  align-items: center;     /* eje cruzado */
  gap: 1rem;
  flex-wrap: wrap;
}
```

| Necesidad | Propiedad |
|---|---|
| Dirección fila/columna | `flex-direction` |
| Separar en el eje principal | `justify-content` |
| Alinear en el eje cruzado | `align-items` |
| Espacio entre elementos | `gap` |
| Permitir salto de línea | `flex-wrap` |
| Hacer crecer un elemento | `flex-grow` |
| Cambiar orden | `order` |

**Trampa común:** si cambias `flex-direction` a `column`, el eje principal deja de ser horizontal.

---

## 8. Formularios

```html
<form class="contact-form">
  <label for="nombre">Nombre</label>
  <input id="nombre" name="nombre" type="text" required>

  <label for="email">Correo</label>
  <input id="email" name="email" type="email" required>

  <label for="mensaje">Mensaje</label>
  <textarea id="mensaje" name="mensaje" rows="5"></textarea>

  <button type="submit">Enviar</button>
</form>
```

```css
.contact-form {
  display: grid;
  gap: 0.75rem;
  max-width: 32rem;
}

.contact-form input,
.contact-form textarea,
.contact-form button {
  font: inherit;
  padding: 0.75rem;
}

.contact-form input:focus,
.contact-form textarea:focus,
.contact-form button:focus-visible {
  outline: 3px solid #93c5fd;
  outline-offset: 2px;
}
```

---

## 9. Media queries

```css
/* Base: móvil */
.layout {
  display: grid;
  grid-template-columns: 1fr;
}

/* Pantallas más grandes */
@media (min-width: 768px) {
  .layout {
    grid-template-columns: 240px 1fr;
  }
}

@media (min-width: 1100px) {
  .movie-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}
```

No uses demasiados breakpoints. Añade uno cuando el diseño deje de funcionar, no porque exista un tamaño estándar.

---

## 10. Posicionamiento

```css
.card {
  position: relative;
}

.badge {
  position: absolute;
  top: 0.75rem;
  right: 0.75rem;
}

.header-fixed {
  position: sticky;
  top: 0;
  z-index: 10;
}
```

- `static`: posición normal.
- `relative`: conserva su espacio y sirve como referencia.
- `absolute`: sale del flujo y se posiciona respecto al ancestro adecuado.
- `fixed`: se fija a la ventana.
- `sticky`: se comporta normal hasta alcanzar un límite.

---

## 11. Dark mode y estados

```css
@media (prefers-color-scheme: dark) {
  :root {
    --fondo: #0f172a;
    --superficie: #1e293b;
    --texto: #e2e8f0;
  }
}

a:hover,
button:hover {
  filter: brightness(0.9);
}

a:focus-visible,
button:focus-visible {
  outline: 3px solid #60a5fa;
}
```

No ocultes el foco del teclado con `outline: none` sin proporcionar una alternativa visible.

---

## 12. Checklist final de examen

- [ ] La estructura HTML representa el diseño.
- [ ] No hay etiquetas sin cerrar.
- [ ] Las imágenes no deforman su proporción.
- [ ] No aparece scroll horizontal.
- [ ] Las tarjetas mantienen una distribución coherente.
- [ ] Flexbox/Grid resuelven la maquetación, no márgenes arbitrarios.
- [ ] La página funciona en móvil y escritorio.
- [ ] Los enlaces tienen estados `hover` y `focus`.
- [ ] Los formularios tienen labels.
- [ ] El contraste permite leer el contenido.
- [ ] La página no depende únicamente del color.
- [ ] Se han revisado la consola y las rutas de imágenes/CSS.


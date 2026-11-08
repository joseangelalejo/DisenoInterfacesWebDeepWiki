# Apuntes de HTML y CSS - Unidad 2

Apuntes prácticos para construir interfaces web a partir de un enunciado, un wireframe y un mockup.

---

## 1. Proceso de trabajo

1. Leer el enunciado completo.
2. Separar la interfaz en bloques: cabecera, navegación, contenido, tarjetas, formularios y pie.
3. Identificar qué elementos son repetitivos y convertirlos en componentes HTML coherentes.
4. Crear la estructura semántica.
5. Aplicar estilos generales.
6. Elegir Flexbox o Grid según el problema.
7. Adaptar el diseño a móvil, tablet y escritorio.
8. Revisar accesibilidad y estados visuales.

**Trampa común:** empezar escribiendo CSS sin entender la estructura. Primero hay que decidir qué representa cada elemento y después cómo se distribuye.

---

## 2. HTML semántico

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Título de la página</title>
    <link rel="stylesheet" href="css/estilos.css">
  </head>
  <body>
    <header>
      <nav aria-label="Navegación principal">
        <a href="#">Inicio</a>
        <a href="#peliculas">Películas</a>
      </nav>
    </header>

    <main>
      <section id="peliculas" aria-labelledby="titulo-peliculas">
        <h1 id="titulo-peliculas">Películas</h1>
        <article class="card">
          <h2>Película</h2>
          <p>Descripción.</p>
        </article>
      </section>
    </main>

    <footer>
      <p>&copy; 2026</p>
    </footer>
  </body>
</html>
```

Elementos principales:

| Elemento | Uso |
|---|---|
| `header` | Cabecera o introducción |
| `nav` | Navegación |
| `main` | Contenido principal, único por página |
| `section` | Bloque temático con título |
| `article` | Contenido independiente o repetible |
| `aside` | Contenido complementario |
| `footer` | Pie de página |

Usa `div` cuando no exista un elemento semántico mejor. El HTML debe describir el contenido, no solo servir como contenedor visual.

---

## 3. Selectores CSS y cascada

```css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
}

.card {
  padding: 1rem;
}

#peliculas {
  max-width: 1200px;
}

nav a:hover {
  text-decoration: underline;
}
```

Prioridad aproximada:

1. Estilos inline.
2. Selectores por id.
3. Clases, atributos y pseudoclases.
4. Elementos y pseudoelementos.

Es mejor usar clases reutilizables que llenar el CSS de ids.

Pseudoclases útiles:

```css
a:hover { }
input:focus { }
input:checked { }
li:first-child { }
button:disabled { }
```

---

## 4. Variables y estilos base

```css
:root {
  --color-principal: #172554;
  --color-acento: #f97316;
  --color-fondo: #f8fafc;
  --color-texto: #172033;
  --radio: 0.75rem;
  --sombra: 0 0.5rem 1.5rem rgb(0 0 0 / 0.12);
}

body {
  background: var(--color-fondo);
  color: var(--color-texto);
}

.card {
  border-radius: var(--radio);
  box-shadow: var(--sombra);
}
```

Las variables facilitan cambiar el tema completo y mantener coherencia visual.

---

## 5. Modelo de caja

Cada elemento tiene:

```text
margin
  border
    padding
      content
```

```css
* {
  box-sizing: border-box;
}

.box {
  width: 300px;
  padding: 1rem;
  border: 2px solid #222;
  margin: 1rem;
}
```

Con `border-box`, el `width` incluye contenido, padding y borde. Es la opción más cómoda para evitar desbordamientos.

---

## 6. Flexbox

Flexbox sirve especialmente para distribuir elementos en una dimensión: una fila o una columna.

```css
.menu {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  flex-wrap: wrap;
}
```

### Propiedades del contenedor

- `display: flex`
- `flex-direction`
- `justify-content`: eje principal
- `align-items`: eje cruzado
- `align-content`: varias líneas
- `gap`
- `flex-wrap`

### Propiedades de los hijos

```css
.item {
  flex: 1 1 250px;
}

.item-destacado {
  order: -1;
  flex-grow: 2;
}
```

**Trampa común:** `justify-content` no siempre trabaja horizontalmente; depende de `flex-direction`.

---

## 7. CSS Grid

Grid es adecuado para una distribución bidimensional con filas y columnas.

```css
.galeria {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
}

.destacada {
  grid-column: span 2;
}
```

Grid adaptable:

```css
.galeria {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1rem;
}
```

Áreas:

```css
.layout {
  display: grid;
  grid-template-columns: 220px 1fr;
  grid-template-areas:
    "menu contenido"
    "menu pie";
}

.menu { grid-area: menu; }
.contenido { grid-area: contenido; }
.pie { grid-area: pie; }
```

Usa Grid cuando el diseño se entiende como una cuadrícula y Flexbox cuando se trata de alinear elementos en un eje.

---

## 8. Responsive design

```css
img {
  max-width: 100%;
  height: auto;
}

@media (max-width: 768px) {
  .menu {
    flex-direction: column;
    align-items: stretch;
  }

  .layout {
    grid-template-columns: 1fr;
    grid-template-areas:
      "contenido"
      "menu"
      "pie";
  }
}
```

Buenas prácticas:

- Diseñar primero la versión móvil.
- Usar unidades relativas (`rem`, `%`, `fr`, `minmax`).
- Evitar anchos fijos innecesarios.
- Añadir breakpoints cuando el contenido lo necesite, no por usar números automáticamente.
- Probar en móvil, tablet y escritorio.

---

## 9. Formularios

```html
<form>
  <label for="email">Correo electrónico</label>
  <input id="email" name="email" type="email" required>

  <label for="tipo">Tipo</label>
  <select id="tipo" name="tipo">
    <option value="general">General</option>
  </select>

  <button type="submit">Enviar</button>
</form>
```

```css
form {
  display: grid;
  gap: 0.75rem;
  max-width: 32rem;
}

input,
select,
textarea,
button {
  font: inherit;
  padding: 0.75rem;
}

input:focus,
select:focus,
textarea:focus {
  outline: 3px solid #93c5fd;
  outline-offset: 2px;
}
```

Cada campo debe tener `label`, `name` y un tipo correcto. No uses placeholder como sustituto del label.

---

## 10. Imágenes, tarjetas y navegación

```html
<article class="card">
  <img src="img/cartel.jpg" alt="Cartel de la película">
  <div class="card__content">
    <h2>La película</h2>
    <p>Información breve.</p>
    <a class="button" href="#detalle">Ver detalle</a>
  </div>
</article>
```

```css
.card img {
  display: block;
  width: 100%;
  aspect-ratio: 2 / 3;
  object-fit: cover;
}

.button {
  display: inline-block;
  text-decoration: none;
  background: var(--color-acento);
  color: white;
  padding: 0.7rem 1rem;
  border-radius: 0.5rem;
}

.button:hover {
  filter: brightness(0.9);
}
```

El texto alternativo debe describir la imagen cuando aporta información. Si es puramente decorativa, puede ser `alt=""`.

---

## 11. Dark mode y preferencias

```css
@media (prefers-color-scheme: dark) {
  :root {
    --color-fondo: #0f172a;
    --color-texto: #e2e8f0;
    --color-principal: #bfdbfe;
  }
}

@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    scroll-behavior: auto !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 12. Checklist de calidad

- [ ] `lang="es"` y `meta viewport`.
- [ ] Título descriptivo.
- [ ] HTML semántico.
- [ ] Un solo `main`.
- [ ] Jerarquía correcta de encabezados.
- [ ] Labels asociados a inputs.
- [ ] Imágenes con `alt`.
- [ ] CSS externo y organizado.
- [ ] `box-sizing: border-box`.
- [ ] No hay desbordamiento horizontal.
- [ ] Flexbox/Grid usados donde corresponde.
- [ ] Responsive probado.
- [ ] Estados `hover` y `focus` visibles.
- [ ] Contraste suficiente.
- [ ] No se depende solo del color.


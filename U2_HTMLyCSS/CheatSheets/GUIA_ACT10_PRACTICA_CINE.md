# Guía orientativa - Act 10: práctica Cine

Guía para afrontar una actividad tipo examen basada en una web de cine. La actividad original se encuentra en [Act10-PracticaCine](../Actividades/Act10-PracticaCine/).

---

## 1. Material disponible

- [Enunciado](../Actividades/Act10-PracticaCine/Enunciado-Webdeuncine.pdf)
- [Wireframe y mockup](../Actividades/Act10-PracticaCine/WebCine-WireframeyMockup1.pdf)
- [HTML base](../Actividades/Act10-PracticaCine/Cine.html)
- [CSS base](../Actividades/Act10-PracticaCine/cine.css)

Antes de empezar hay que abrir el enunciado y el mockup. El HTML/CSS inicial puede estar vacío o incompleto, por lo que no se debe asumir que los nombres o requisitos están ya resueltos.

---

## 2. Analizar el diseño

Haz una lista de bloques antes de escribir:

```text
Página
├── Cabecera
│   ├── Logo
│   └── Navegación
├── Contenido principal
│   ├── Hero o presentación
│   ├── Cartelera
│   ├── Tarjetas de películas
│   └── Formulario o información adicional
└── Pie de página
```

Después apunta:

- Número de columnas.
- Orden de los elementos.
- Anchura máxima.
- Colores.
- Tipografías.
- Espaciados.
- Imágenes y proporciones.
- Qué cambia en móvil.

---

## 3. Crear el HTML

Usa etiquetas semánticas:

```html
<header>...</header>
<nav aria-label="Navegación principal">...</nav>
<main>
  <section aria-labelledby="titulo">
    <h1 id="titulo">Cartelera</h1>
    <article>...</article>
  </section>
</main>
<footer>...</footer>
```

Para una película:

```html
<article class="pelicula">
  <img src="img/cartel.jpg" alt="Cartel de Nombre de película">
  <div class="pelicula__info">
    <h2>Nombre de película</h2>
    <p>Género · Duración</p>
    <a href="#detalle">Más información</a>
  </div>
</article>
```

Evita llenar todo de `div`. Una tarjeta repetida es un `article`; una zona temática suele ser un `section`.

---

## 4. Crear el CSS por capas

### Capa 1: base

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  background: #f4f4f5;
  color: #18181b;
  font-family: system-ui, sans-serif;
}

img {
  display: block;
  max-width: 100%;
}
```

### Capa 2: estructura

```css
.contenedor {
  width: min(100% - 2rem, 1200px);
  margin-inline: auto;
}

.cabecera {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}
```

### Capa 3: componentes

```css
.cartelera {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1.5rem;
}

.pelicula {
  overflow: hidden;
  border-radius: 0.75rem;
  background: white;
  box-shadow: 0 0.5rem 1.5rem rgb(0 0 0 / 0.12);
}
```

### Capa 4: responsive

```css
@media (max-width: 700px) {
  .cabecera {
    align-items: stretch;
    flex-direction: column;
  }
}
```

---

## 5. Cómo elegir Flexbox o Grid

### Flexbox

Usa Flexbox para:

- Menú horizontal.
- Alinear logo y navegación.
- Alinear botones dentro de una tarjeta.
- Centrar elementos en una fila o columna.

### Grid

Usa Grid para:

- Cartelera de películas.
- Galería.
- Layout con sidebar y contenido.
- Distribuciones con filas y columnas.

No hace falta usar ambos en todo: elige el que describa mejor el problema.

---

## 6. Responsive del cine

La versión móvil suele necesitar:

- Menú en columna.
- Una columna de tarjetas.
- Imágenes que no desborden.
- Texto y botones con tamaño legible.
- Menos padding lateral.

```css
.cartelera {
  grid-template-columns: 1fr;
}

@media (min-width: 600px) {
  .cartelera {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1000px) {
  .cartelera {
    grid-template-columns: repeat(4, 1fr);
  }
}
```

También puede resolverse de forma automática:

```css
.cartelera {
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
}
```

---

## 7. Orden recomendado para resolverlo en el examen

1. Crear la estructura HTML completa.
2. Comprobar que todos los textos e imágenes aparecen.
3. Aplicar reset y variables.
4. Centrar el contenido con un contenedor.
5. Maquetar cabecera y navegación.
6. Resolver la cartelera con Grid.
7. Diseñar una tarjeta y reutilizar sus clases.
8. Añadir formularios y estados.
9. Añadir responsive.
10. Comparar con el mockup y corregir detalles.

No pierdas tiempo intentando dejar perfecto un botón antes de haber construido la estructura completa.

---

## 8. Fallos frecuentes

- Usar una imagen con una ruta incorrecta.
- Olvidar `box-sizing: border-box`.
- Fijar anchos en píxeles que rompen el móvil.
- Usar `position: absolute` para maquetar toda la página.
- Aplicar `justify-content` esperando que funcione en el eje equivocado.
- No poner `min-width: 0` en un elemento Grid/Flex que desborda.
- Ocultar el foco del teclado.
- Usar un placeholder sin `label`.
- No comprobar el diseño en móvil.
- Hacer que la apariencia dependa solo del color.

---

## 9. Checklist de entrega

- [ ] La página carga sin errores.
- [ ] Todas las rutas de CSS e imágenes funcionan.
- [ ] El resultado se parece al mockup.
- [ ] El diseño es responsive.
- [ ] El HTML es semántico.
- [ ] Las tarjetas tienen una estructura consistente.
- [ ] Los enlaces y botones se distinguen.
- [ ] Los formularios son utilizables.
- [ ] El foco del teclado es visible.
- [ ] No hay scroll horizontal.
- [ ] Se han revisado varios tamaños de ventana.


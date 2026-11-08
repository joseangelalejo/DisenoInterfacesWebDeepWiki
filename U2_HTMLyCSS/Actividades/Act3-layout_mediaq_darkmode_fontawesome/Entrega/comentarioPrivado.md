# Comentario privado entrega Classroom

## PORCENTAJE DE TRABAJO REALIZADO

**90 %**.

Están todos los apartados de la premisa y los tres bonus. Lo que falta es que en móvil los bloques pasen a 100 % y el menú a vertical, que no he hecho a propósito (ver problemas técnicos).

Ayuda de Claude para evaluación por rúbrica.

## PUNTUACIÓN DE AUTOEVALUACIÓN SEGÚN LA RÚBRICA: 32/40

- Estructura básica de la landing, HTML semántico con header, secciones y footer: 10/10
- Maquetación con `inline-block`, dos bloques al 50 % correctamente alineados: 8/8
- Media queries Level 4: 0/8. El @media (`width <= 600px`) existe y se aplica, pero solo compacta tamaños. No pasa los bloques a 100 % ni el menú a vertical.
- Modo oscuro automático con `@media (prefers-color-scheme: dark)`: 6/6
- Font Awesome en el footer (Facebook, Twitter, Instagram): 4/4
- Icono adicional de Font Awesome (calendario en Fecha y ubicación en Lugar): 2/2
- Imagen destacada con placehold.co: 2/2

**Bonus hechos**: `:hover` en el botón de comprar entradas, `:hover`, :active y :focus en el menú, y tipografía distinta (Georgia) en modo oscuro. Además, hover con iconos más grandes en las redes sociales.

## PROBLEMAS TÉCNICOS ENCONTRADOS

- **El wireframe y la premisa se contradicen**. La premisa dice que con `width <= 600px` el menú pasa a vertical y los bloques de la sección secundaria pasan a 100 % (block). El wireframe, que es una vista estrecha, muestra el menú horizontal y el botón a la derecha de la información del evento. Seguí el wireframe, y por eso me pongo 0/8 en ese apartado.
- **Hueco entre inline-block**. Dos bloques al 50 % se apilaban por el espacio en blanco entre las etiquetas del HTML. Lo resolví con font-size: 0 en el contenedor y restaurando el tamaño en los hijos.
- **Cabecera con flex**. Usé `display: flex` en el header para alinear el logo y el menú, como se permitía. El resto de la maquetación no usa flex ni grid.
- **Ajuste a móvil**. A 412 px el botón y el título se desbordaban, así que reduje paddings y tamaños de letra dentro del media query.
- **Hover en vista móvil**. `:hover` no se dispara en la vista adaptable con simulación táctil activada, igual que en un móvil real. Añadí :focus y :active para que el menú reaccione al tocarlo.
- **Hover con font-size**. Agrandar iconos y enlaces con font-size en `:hover` mueve el contenido de alrededor. Con transform: scale() no se movería.

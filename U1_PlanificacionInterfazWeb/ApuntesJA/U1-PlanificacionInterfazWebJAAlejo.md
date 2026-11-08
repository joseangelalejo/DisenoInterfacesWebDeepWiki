# U1 - Planificación de una interfaz web

Apuntes de planificación de interfaces web para **Diseño de Interfaces Web**. La planificación sirve para decidir qué necesita la interfaz, cómo se organiza y cómo se va a presentar antes de empezar a maquetar con HTML y CSS.

---

## Índice

- [U1 - Planificación de una interfaz web](#u1---planificación-de-una-interfaz-web)
  - [Índice](#índice)
  - [Fundamentos del diseño](#fundamentos-del-diseño)
    - [Comunicación visual](#comunicación-visual)
    - [Elementos de la comunicación visual](#elementos-de-la-comunicación-visual)
    - [Principios básicos](#principios-básicos)
    - [Buenas prácticas de diseño](#buenas-prácticas-de-diseño)
  - [Color, tipografía e iconografía](#color-tipografía-e-iconografía)
  - [Color y contraste](#color-y-contraste)
    - [Contraste y accesibilidad](#contraste-y-accesibilidad)
  - [Tipografía](#tipografía)
    - [Tipos principales](#tipos-principales)
    - [Jerarquía tipográfica](#jerarquía-tipográfica)
  - [Iconografía](#iconografía)
  - [Guías de estilo y componentes](#guías-de-estilo-y-componentes)
    - [Qué es una guía de estilo](#qué-es-una-guía-de-estilo)
    - [Contenido de una guía de estilo](#contenido-de-una-guía-de-estilo)
    - [Componentes de interfaz](#componentes-de-interfaz)
    - [Consistencia y reutilización](#consistencia-y-reutilización)
  - [Estructura, navegación y maquetación](#estructura-navegación-y-maquetación)
  - [Arquitectura de la información](#arquitectura-de-la-información)
  - [Mapa de navegación](#mapa-de-navegación)
  - [Wireframes](#wireframes)
  - [Mockups](#mockups)
    - [Diferencia entre mapa, wireframe y mockup](#diferencia-entre-mapa-wireframe-y-mockup)
  - [Prototipos](#prototipos)
  - [Maquetación web](#maquetación-web)
  - [Layouts comunes](#layouts-comunes)
    - [Blog](#blog)
    - [Ecommerce](#ecommerce)
    - [Landing page Estructura](#landing-page-estructura)
  - [Caracterización del público](#caracterización-del-público)
    - [Internautas](#internautas)
    - [Principiantes y usuarios ocasionales](#principiantes-y-usuarios-ocasionales)
    - [Usuarios y expertos reincidentes](#usuarios-y-expertos-reincidentes)
    - [Usuarios internacionales](#usuarios-internacionales)
    - [Equipo de trabajo](#equipo-de-trabajo)
  - [Estructura básica de una web](#estructura-básica-de-una-web)
    - [Header](#header)
    - [Menú](#menú)
    - [Main](#main)
    - [Footer](#footer)
  - [Landing page](#landing-page)
    - [Elementos habituales](#elementos-habituales)
    - [Recomendaciones para una landing](#recomendaciones-para-una-landing)
    - [Ejemplo de estructura](#ejemplo-de-estructura)
  - [Proceso de trabajo](#proceso-de-trabajo)
    - [Fase 1: análisis](#fase-1-análisis)
    - [Fase 2: arquitectura](#fase-2-arquitectura)
    - [Fase 3: diseño](#fase-3-diseño)
    - [Fase 4: prototipo](#fase-4-prototipo)
    - [Fase 5: implementación](#fase-5-implementación)
    - [Fase 6: pruebas](#fase-6-pruebas)
  - [Práctica recomendada](#práctica-recomendada)
  - [Checklist de examen](#checklist-de-examen)

---

## Fundamentos del diseño

### Comunicación visual

La comunicación visual es la transmisión de información, ideas o emociones mediante elementos que el usuario puede percibir visualmente. En una interfaz web se utilizan imágenes, colores, formas, tipografías, iconos, espacios y composición.

No se trata solo de que una web sea bonita. El diseño debe ayudar al usuario a:

- Entender qué ofrece la página.
- Encontrar rápidamente la información.
- Saber qué acciones puede realizar.
- Distinguir la información principal de la secundaria.
- Recordar la identidad de la marca.
- Usar la interfaz sin confusión.

### Elementos de la comunicación visual

| Elemento | Función |
|---|---|
| Imágenes | Mostrar productos, situaciones, personas o contenido visual |
| Color | Transmitir identidad, jerarquía, estados y emociones |
| Formas | Organizar bloques y dirigir la atención |
| Tipografía | Comunicar el contenido y establecer jerarquías |
| Iconos | Representar acciones o conceptos de forma rápida |
| Espacio | Separar grupos y mejorar la legibilidad |
| Composición | Organizar todos los elementos en un conjunto equilibrado |

### Principios básicos

- **Jerarquía visual:** lo importante debe llamar la atención antes.
- **Contraste:** diferenciar elementos mediante tamaño, color, peso o espacio.
- **Alineación:** colocar los elementos siguiendo referencias comunes.
- **Proximidad:** los elementos relacionados deben aparecer juntos.
- **Repetición:** reutilizar estilos para transmitir consistencia.
- **Equilibrio:** distribuir el peso visual de la página.
- **Simplicidad:** eliminar elementos que no aporten información o funcionalidad.

> **Idea importante:** una interfaz debe ser comprensible antes de ser decorativa.

### Buenas prácticas de diseño

Al analizar una web conviene preguntarse:

1. ¿Se entiende en pocos segundos qué ofrece?
2. ¿Se identifica fácilmente la navegación?
3. ¿Existe una jerarquía clara de títulos y contenidos?
4. ¿Los botones parecen botones?
5. ¿Hay suficiente contraste?
6. ¿La información está agrupada de forma lógica?
7. ¿La página funciona en móvil?
8. ¿Los formularios son fáciles de completar?
9. ¿Hay demasiado contenido o elementos que distraen?
10. ¿La identidad visual se mantiene en todas las páginas?

---

## Color, tipografía e iconografía

## Color y contraste

El color puede utilizarse para:

- Identificar una marca.
- Destacar llamadas a la acción.
- Separar secciones.
- Indicar estados: éxito, error, aviso o información.
- Crear una sensación concreta.
- Guiar la atención del usuario.

Una paleta básica puede tener:

- **Color primario:** color principal de la marca.
- **Color secundario:** color de apoyo.
- **Color de acento:** usado para destacar acciones.
- **Color de fondo:** superficie principal o alternativa.
- **Color de texto:** debe ofrecer contraste suficiente.
- **Colores de estado:** éxito, error, advertencia e información.

```css
:root {
  --color-primario: #172554;
  --color-acento: #f97316;
  --color-fondo: #f8fafc;
  --color-superficie: #ffffff;
  --color-texto: #172033;
  --color-error: #b91c1c;
  --color-exito: #15803d;
}
```

### Contraste y accesibilidad

El contraste es la diferencia visual entre el texto y su fondo. Si es insuficiente, la información resulta difícil de leer, especialmente para personas con baja visión o en condiciones de iluminación desfavorables.

Buenas prácticas:

- No usar texto claro sobre un fondo claro.
- No depender únicamente del color para comunicar un estado.
- Comprobar el contraste de textos, botones y enlaces.
- Mantener visible el estado `focus` de los controles.
- Usar una herramienta de contraste cuando sea necesario.
- Seguir las recomendaciones de accesibilidad de WCAG.

**Trampa común:** que una combinación “se vea bien” no significa que sea accesible.

## Tipografía

La tipografía influye en la legibilidad, la personalidad y la jerarquía de la interfaz.

### Tipos principales

- **Serif:** tienen remates en los extremos de las letras. Pueden transmitir tradición o formalidad.
- **Sans serif:** no tienen remates. Suelen ser claras y habituales en interfaces digitales.
- **Monoespaciadas:** cada carácter ocupa el mismo ancho. Se usan sobre todo para código.

### Jerarquía tipográfica

```text
Título principal
  Subtítulo o introducción
    Encabezado de sección
      Texto normal
        Nota o información secundaria
```

Se puede crear jerarquía con:

- Tamaño.
- Peso.
- Color.
- Altura de línea.
- Espaciado.
- Mayúsculas, usadas con moderación.

Buenas prácticas:

- Usar como máximo dos familias tipográficas en una web.
- Elegir fuentes legibles.
- Mantener una escala de tamaños coherente.
- Usar una altura de línea cómoda.
- No usar demasiados estilos distintos.
- Comprobar que la fuente tenga los caracteres necesarios.

```css
body {
  font-family: system-ui, sans-serif;
  font-size: 1rem;
  line-height: 1.5;
}

h1 {
  font-size: clamp(2rem, 5vw, 4rem);
  line-height: 1.1;
}
```

## Iconografía

Los iconos representan acciones, objetos o conceptos de forma visual. Deben ser fáciles de reconocer y coherentes entre sí.

Buenas prácticas:

- Usar iconos con significado claro.
- Mantener el mismo estilo visual.
- No mezclar bibliotecas sin necesidad.
- Acompañar con texto las acciones que puedan resultar ambiguas.
- Proporcionar una etiqueta accesible a los iconos que funcionen como botones.
- Usar bibliotecas conocidas como Font Awesome o Material Icons cuando el proyecto lo permita.

```html
<button type="button" aria-label="Abrir menú">
  <span aria-hidden="true">☰</span>
</button>
```

---

## Guías de estilo y componentes

### Qué es una guía de estilo

Una guía de estilo es un documento que recoge las reglas visuales y técnicas que debe seguir una interfaz. Su objetivo es que todas las páginas y componentes mantengan una apariencia coherente.

### Contenido de una guía de estilo

Puede incluir:

- **Identidad de marca:** logotipo, filosofía y valores.
- **Paleta de colores:** colores primarios, secundarios y estados.
- **Tipografía:** familias, tamaños, pesos y espaciados.
- **Imágenes y gráficos:** estilo, formatos y tamaños.
- **Iconografía:** biblioteca, tamaños y usos.
- **Espaciado:** márgenes, rellenos y separación entre componentes.
- **Rejilla:** columnas, anchos máximos y alineaciones.
- **Componentes:** botones, formularios, tarjetas, menús y modales.
- **Estados:** normal, hover, focus, activo, deshabilitado y error.
- **Accesibilidad:** contraste, foco, textos alternativos y navegación por teclado.
- **Especificaciones técnicas:** convenciones de nombres y organización del CSS.

### Componentes de interfaz

Un componente es una pieza reutilizable de la interfaz con una función y un estilo definidos.

Ejemplos:

- Botones.
- Menús.
- Enlaces.
- Formularios.
- Tarjetas.
- Alertas.
- Modales.
- Migas de pan.
- Paginación.
- Cabecera y pie.

Un botón debería definir, como mínimo:

```text
Estado normal
Estado hover
Estado focus
Estado activo
Estado deshabilitado
```

### Consistencia y reutilización

La reutilización evita diseñar cada elemento desde cero y permite corregir un componente en un único lugar.

```css
.button {
  display: inline-block;
  padding: 0.75rem 1rem;
  border: 0;
  border-radius: 0.5rem;
  background: var(--color-acento);
  color: white;
  text-decoration: none;
}

.button:hover {
  filter: brightness(0.9);
}
```

---

## Estructura, navegación y maquetación

## Arquitectura de la información

La arquitectura de la información organiza el contenido y define cómo se relacionan las páginas. Antes de diseñar una interfaz hay que saber:

- Qué contenido existe.
- Cómo se agrupa.
- Qué importancia tiene cada bloque.
- Cómo llegará el usuario a cada sección.
- Qué acciones debe poder realizar.

Una arquitectura clara reduce la carga mental del usuario.

## Mapa de navegación

El mapa de navegación es un esquema que muestra la estructura y jerarquía de las páginas de una web. Representa **qué páginas existen y cómo se relacionan**.

Ejemplo:

```text
Home
├── Productos
│   ├── Categoría
│   └── Detalle de producto
├── Blog
│   └── Artículo
├── Contacto
└── Carrito
    └── Checkout
```

Sirve para:

- Planificar el menú.
- Detectar páginas que faltan.
- Evitar duplicidades.
- Entender la profundidad de navegación.
- Decidir qué contenido depende de cada página.

> **Mapa de navegación = arquitectura del sitio.**

## Wireframes

Un wireframe es un bosquejo de una página. Se centra en la estructura, la distribución y la funcionalidad, no en la apariencia final.

Normalmente contiene:

- Cajas.
- Textos provisionales.
- Botones.
- Bloques de imagen.
- Menús.
- Formularios.
- Indicaciones de interacción.

Un wireframe suele evitar:

- Colores definitivos.
- Tipografías finales.
- Imágenes reales.
- Detalles decorativos.

Ventajas:

- Es rápido de modificar.
- Permite detectar problemas de distribución pronto.
- Facilita hablar con el cliente o el equipo.
- Evita perder tiempo en estilos antes de validar la estructura.

> **Wireframe = esqueleto o plano de una página.**

## Mockups

Un mockup es una representación visual estática y detallada de la interfaz. Parte de la estructura del wireframe y añade la apariencia prevista:

- Colores.
- Tipografías.
- Imágenes.
- Iconos.
- Espaciados.
- Componentes visuales.

El mockup sirve para comprobar cómo será el resultado visual antes de implementarlo.

### Diferencia entre mapa, wireframe y mockup

| Recurso | Responde a | Representa |
|---|---|---|
| Mapa de navegación | ¿Qué páginas hay? | Relación entre páginas |
| Wireframe | ¿Cómo se distribuye una página? | Estructura y funcionalidad |
| Mockup | ¿Cómo se verá? | Apariencia visual detallada |
| Prototipo | ¿Cómo se utilizará? | Interacciones y flujo |

## Prototipos

Un prototipo permite simular la navegación y algunas interacciones de la interfaz. Puede ser de baja o alta fidelidad.

- **Baja fidelidad:** rápido, básico y centrado en el flujo.
- **Alta fidelidad:** más parecido al resultado final y con más interacciones.

Herramientas habituales:

- Figma.
- Whimsical.
- Adobe XD.

## Maquetación web

La maquetación es la organización de los elementos dentro de una página. Una buena maquetación crea equilibrio, orden y legibilidad.

Conceptos clave:

- **Rejilla (grid):** divide el espacio en filas y columnas.
- **Alineación:** mantiene los elementos relacionados sobre referencias comunes.
- **Espacio en blanco:** crea separación y mejora la lectura.
- **Agrupación:** coloca juntos los elementos relacionados.
- **Flujo visual:** guía el recorrido de la mirada.
- **Responsive design:** adapta la interfaz a distintos tamaños.

En HTML y CSS:

- Usa HTML semántico para representar la estructura.
- Usa Flexbox para alinear en una dimensión.
- Usa Grid para filas y columnas.
- Usa media queries para adaptar el diseño.
- Evita maquetar toda la página mediante posiciones absolutas.

## Layouts comunes

### Blog

```text
Cabecera
├── Navegación
├── Listado de artículos
│   ├── Imagen
│   ├── Título
│   ├── Resumen
│   └── Enlace
└── Barra lateral o categorías
```

### Ecommerce

```text
Cabecera
├── Categorías
├── Producto
│   ├── Imagen
│   ├── Descripción
│   ├── Precio
│   └── Botón de compra
└── Carrito
```

### Landing page Estructura

```text
Cabecera
├── Hero y propuesta de valor
├── Beneficios
├── Cómo funciona
├── Testimonios
├── Preguntas frecuentes
├── Llamada a la acción
└── Footer
```

Son patrones habituales porque responden a necesidades frecuentes, pero deben adaptarse al contenido y al público.

---

## Caracterización del público

No todos los usuarios tienen los mismos conocimientos, necesidades, dispositivos o expectativas. El diseño debe adaptarse al público objetivo.

### Internautas

Son usuarios que navegan por internet con distintos niveles de experiencia. Suelen esperar:

- Carga rápida.
- Navegación reconocible.
- Información directa.
- Compatibilidad con distintos dispositivos.
- Enlaces y botones fáciles de identificar.

### Principiantes y usuarios ocasionales

Necesitan una interfaz especialmente clara:

- Menús sencillos.
- Textos explicativos.
- Pocas opciones simultáneas.
- Formularios guiados.
- Mensajes de error comprensibles.
- Acciones principales destacadas.

No conviene asumir que conocen la terminología técnica.

### Usuarios y expertos reincidentes

Visitan la aplicación con frecuencia y valoran:

- Rapidez.
- Atajos.
- Consistencia.
- Información densa, pero bien organizada.
- Recordar preferencias.
- No repetir pasos innecesarios.

### Usuarios internacionales

La interfaz puede necesitar:

- Traducciones.
- Formatos de fecha y hora locales.
- Monedas y unidades adaptadas.
- Iconos comprensibles culturalmente.
- Espacio suficiente para textos más largos.
- Evitar expresiones o colores con significados locales problemáticos.

### Equipo de trabajo

Una interfaz profesional normalmente se construye en equipo. Pueden participar:

- Cliente o responsable del producto.
- Diseñador UX/UI.
- Desarrollador frontend.
- Desarrollador backend.
- Responsable de contenidos.
- Persona encargada de accesibilidad y pruebas.

Una guía de estilo, un mapa de navegación y unos wireframes facilitan la comunicación entre todos.

---

## Estructura básica de una web

### Header

El `header` contiene la introducción de la página o sección. Puede incluir:

- Logotipo.
- Nombre de la marca.
- Eslogan.
- Menú.
- Acciones de usuario.
- Redes sociales.

El logotipo suele enlazar con la página de inicio.

```html
<header class="site-header">
  <a href="/" class="logo">Marca</a>
  <nav aria-label="Navegación principal">
    <a href="#servicios">Servicios</a>
    <a href="#contacto">Contacto</a>
  </nav>
</header>
```

### Menú

El menú debe mostrar las secciones principales y mantener una estructura coherente.

Buenas prácticas:

- Etiquetas claras.
- Orden lógico.
- Estado activo visible.
- Navegación accesible con teclado.
- Adaptación a pantallas pequeñas.
- No esconder información importante tras demasiados niveles.

### Main

El `main` contiene el contenido principal de la página. Debe haber un único `main` por documento.

### Footer

El `footer` puede contener:

- Información legal.
- Contacto.
- Redes sociales.
- Enlaces secundarios.
- Copyright.
- Información de accesibilidad.

---

## Landing page

Una landing page es una página diseñada para conseguir un objetivo concreto: registrarse, comprar, solicitar información, descargar algo o realizar otra conversión.

### Elementos habituales

1. **Propuesta de valor:** explica rápidamente qué se ofrece.
2. **Hero:** bloque inicial con título, imagen y llamada a la acción.
3. **Beneficios:** razones para elegir el producto o servicio.
4. **Explicación:** cómo funciona.
5. **Contenido multimedia:** imágenes o vídeos relevantes.
6. **Testimonios:** opiniones de usuarios.
7. **Premios o reconocimientos:** elementos que generan confianza.
8. **Formulario:** debe ser cómodo y pedir solo lo necesario.
9. **Redes sociales:** conexión con la comunidad.
10. **CTA (Call To Action):** acción principal que se quiere conseguir.

### Recomendaciones para una landing

- Escribir claro.
- Explicar el producto o servicio.
- Listar la información importante.
- Eliminar distracciones.
- Repetir la llamada a la acción en puntos razonables.
- Usar imágenes relacionadas con el objetivo.
- Mostrar señales de confianza.
- Facilitar la lectura desde móvil.

**Trampa común:** una landing no debe tener muchas acciones principales compitiendo entre sí. El usuario debe entender qué se espera de él.

### Ejemplo de estructura

```html
<main>
  <section class="hero">
    <h1>Aprende de forma sencilla</h1>
    <p>Propuesta de valor clara y breve.</p>
    <a class="button" href="#registro">Empezar ahora</a>
  </section>

  <section aria-labelledby="beneficios">
    <h2 id="beneficios">Beneficios</h2>
    <!-- Tarjetas de beneficios -->
  </section>

  <section id="registro" aria-labelledby="titulo-registro">
    <h2 id="titulo-registro">Regístrate</h2>
    <!-- Formulario -->
  </section>
</main>
```

---

## Proceso de trabajo

### Fase 1: análisis

- Leer el objetivo del proyecto.
- Identificar el público.
- Recopilar contenidos.
- Analizar referencias y webs similares.
- Detectar restricciones técnicas.

### Fase 2: arquitectura

- Organizar la información.
- Crear el mapa de navegación.
- Definir las páginas y sus relaciones.
- Decidir la navegación principal y secundaria.

### Fase 3: diseño

- Crear wireframes.
- Validar la distribución.
- Crear la guía de estilo.
- Preparar mockups.
- Definir componentes reutilizables.

### Fase 4: prototipo

- Conectar pantallas.
- Simular las acciones principales.
- Revisar el flujo del usuario.
- Detectar problemas antes de programar.

### Fase 5: implementación

- Crear HTML semántico.
- Añadir CSS.
- Usar Flexbox y Grid.
- Añadir responsive design.
- Incorporar accesibilidad.

### Fase 6: pruebas

- Comprobar distintos tamaños de pantalla.
- Revisar navegación y enlaces.
- Revisar formularios.
- Comprobar contraste y foco.
- Verificar imágenes y textos.
- Pedir a otra persona que pruebe la interfaz.

---

## Práctica recomendada

Para practicar esta unidad:

1. Elegir un sitio web sencillo.
2. Crear su mapa de navegación.
3. Diseñar la portada, una sección de contenido y un formulario.
4. Crear un wireframe.
5. Crear un pequeño mockup.
6. Definir una guía de estilos.
7. Implementar la interfaz con HTML y CSS.

Herramientas posibles:

- Figma.
- Whimsical.
- Papel y lápiz para el primer borrador.

---

## Checklist de examen

- [ ] Sé explicar la diferencia entre mapa de navegación, wireframe, mockup y prototipo.
- [ ] Sé explicar qué es la comunicación visual.
- [ ] Distingo color, tipografía, iconografía y composición.
- [ ] Sé justificar el uso del contraste y la accesibilidad.
- [ ] Sé describir una guía de estilo.
- [ ] Conozco los componentes habituales de una interfaz.
- [ ] Sé explicar qué es una rejilla y qué aporta el espacio en blanco.
- [ ] Puedo identificar un layout de blog, ecommerce o landing page.
- [ ] Sé adaptar una interfaz a principiantes, expertos e internacionales.
- [ ] Conozco la función del header, menú, main y footer.
- [ ] Sé explicar qué es una CTA.
- [ ] Puedo proponer un proceso de trabajo completo.

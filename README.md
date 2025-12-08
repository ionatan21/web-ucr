# 📘 Guía de Reutilización de Estilos CSS

## 🎯 Índice
- [Paleta de Colores](#paleta-de-colores)
- [Tipografía](#tipografía)
- [Componentes Reutilizables](#componentes-reutilizables)
- [Layouts](#layouts)
- [Patrones de Diseño](#patrones-de-diseño)
- [Responsive Design](#responsive-design)
- [Casos de Uso Comunes](#casos-de-uso-comunes)

---

## 🎨 Paleta de Colores

### Colores Principales
```css
/* Color de Marca Principal */
#6EC1E4  /* Celeste corporativo - Títulos, labels, elementos destacados */

/* Azules (Enlaces) */
#0056b3  /* Azul enlaces estándar */
#003d80  /* Azul enlaces hover */
#0d6efd  /* Azul activo (tabs, botones) */

/* Grises (Texto) */
#4a4a4a  /* Gris oscuro - Texto principal (body) */
#555     /* Gris medio - Texto secundario */
#777     /* Gris claro - Metadatos */
#444     /* Gris items */

/* Fondos */
#ffffff  /* Blanco - Tarjetas, fondos principales */
#fafafa  /* Gris muy claro - Fondos secundarios */
#f7f7f7  /* Gris claro - Elementos inline (datetime) */
#f1f3f5  /* Gris claro - Badges, pills */
#f5f5f5  /* Gris hover */

/* Bordes */
#dee2e6  /* Gris borde - Separadores */
#ececec  /* Gris borde claro */

/* Mensajes de Estado */
#e8f8f3  /* Fondo mensaje éxito */
#2ecc71  /* Borde mensaje éxito */
#145a32  /* Texto mensaje éxito */
#117a65  /* Enlaces en mensajes */
```

---

## 📝 Tipografía

### Fuentes Principales
```css
/* Títulos y Labels */
font-family: "Roboto", sans-serif;
font-weight: 700;  /* Bold */

/* Texto de contenido */
font-family: truenorg;

/* Códigos, fechas, horas */
font-family: monospace;
```

### Tamaños de Fuente
```css
/* Títulos */
h1: 2.2rem;     /* Título principal (1.8rem en tablet) */
h2: 1.5rem;     /* Subtítulos (1.3rem en móvil) */

/* Texto */
body: 1rem;     /* Texto base */
small: 0.95rem; /* Labels, campos */
meta: 0.85rem;  /* Metadatos */
```

---

## 🧩 Componentes Reutilizables

### 1. **Tarjeta de Contenido**
```css
/* Clase: article.node */
background-color: #ffffff;
border-radius: 0.75rem;
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.04);
padding: 1.5rem 1.25rem;
```

**Uso:**
```html
<article class="node">
  <!-- Tu contenido aquí -->
</article>
```

**Cuándo usar:**
- Páginas de detalle de contenido
- Artículos
- Posts de blog
- Información destacada

---

### 2. **Sistema de Campos (Label + Items)**
```css
/* Estructura:
   .field
     .field__label
     .field__items
       .field__item
*/
```

**Uso:**
```html
<div class="field">
  <div class="field__label">NOMBRE DEL CAMPO</div>
  <div class="field__items">
    <div class="field__item">Valor 1</div>
    <div class="field__item">Valor 2</div>
  </div>
</div>
```

**Cuándo usar:**
- Mostrar datos estructurados
- Formularios de solo lectura
- Metadatos
- Listas de información

---

### 3. **Badges de Archivo (File Pills)**
```css
/* Clase: .file */
display: inline-flex;
border-radius: 999px;
background-color: #f1f3f5;
padding: 0.35rem 0.7rem;
```

**Uso:**
```html
<span class="file">
  <a href="/path/to/file.pdf">documento.pdf</a>
</span>
```

**Cuándo usar:**
- Links de descarga
- Archivos adjuntos
- Documentos
- PDFs, DOCs, etc.

---

### 4. **Sistema de Pestañas**
```css
/* Estructura:
   .tabs-wrapper
     .nav.nav-tabs
       .nav-item
         .nav-link (+ .active)
*/
```

**Uso:**
```html
<div class="tabs-wrapper tabs-primary">
  <ul class="nav nav-tabs">
    <li class="nav-item">
      <a class="nav-link active" href="#">Ver</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="#">Editar</a>
    </li>
  </ul>
</div>
```

**Cuándo usar:**
- Navegación de secciones
- Paneles de administración
- Vistas alternativas del mismo contenido

---

### 5. **Mensajes del Sistema**
```css
/* Clase: .messages.messages--status */
background: #e8f8f3;
border: 1px solid #2ecc71;
color: #145a32;
```

**Uso:**
```html
<div data-drupal-messages>
  <div class="messages__wrapper">
    <div class="messages messages--status">
      ¡Operación exitosa!
    </div>
  </div>
</div>
```

**Variantes:**
- `.messages--status` - Éxito (verde)
- `.messages--error` - Error (rojo) - *Añadir colores*
- `.messages--warning` - Advertencia (amarillo) - *Añadir colores*

---

### 6. **Campo Multimedia**
```css
/* Clase: .field--name-field-img */
/* Soporta: Audio, Documentos, Imágenes, Video, Embeds */
```

**Uso:**
```html
<div class="field field--name-field-img">
  <div class="field__items">
    <div class="field__item">
      <!-- Audio -->
      <audio controls src="audio.mp3"></audio>
      
      <!-- Imagen -->
      <div class="media--type-image">
        <img src="image.jpg" alt="Descripción">
      </div>
      
      <!-- Video -->
      <video controls src="video.mp4"></video>
      
      <!-- Embed (YouTube) -->
      <iframe class="media-oembed-content" src="..."></iframe>
    </div>
  </div>
</div>
```

**Cuándo usar:**
- Galerías de imágenes
- Contenido multimedia
- Videos embebidos
- Podcasts/audio

---

### 7. **Datetime Badge**
```css
/* Clase: .datetime */
font-family: monospace;
background: #f7f7f7;
padding: 0.1rem 0.35rem;
border-radius: 0.25rem;
```

**Uso:**
```html
<time class="datetime" datetime="2025-12-08">
  08/12/2025 - 14:30
</time>
```

**Cuándo usar:**
- Fechas de publicación
- Timestamps
- Horarios
- Fechas de eventos

---

## 📐 Layouts

### Layout Vertical Centrado
```css
/* Clase: .region.region-content o .view-content .views-row */
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
gap: 20px;
padding: 1.5rem 1rem;
```

**Uso:**
```html
<div class="region region-content">
  <!-- Contenido automáticamente centrado y espaciado -->
  <h1>Título</h1>
  <p>Contenido</p>
  <img src="imagen.jpg">
</div>
```

**Cuándo usar:**
- Páginas de landing
- Contenido centrado
- Secciones de hero
- Layouts simples verticales

---

### Layout de Items Flexibles
```css
/* Clase: .field__items */
display: flex;
flex-wrap: wrap;
gap: 0.75rem;
```

**Uso:**
```html
<div class="field__items">
  <span class="field__item">Tag 1</span>
  <span class="field__item">Tag 2</span>
  <span class="field__item">Tag 3</span>
</div>
```

**Cuándo usar:**
- Tags
- Etiquetas
- Listas de valores
- Badges múltiples

---

## 🎭 Patrones de Diseño

### Patrón: Título + Contenido
```html
<div class="region region-content">
  <!-- Título -->
  <div id="block-bootstrap5-page-title">
    <h1>Título de la Página</h1>
  </div>
  
  <!-- Contenido -->
  <article class="node">
    <div class="node__content">
      <div class="field field--name-body">
        <p>Contenido aquí...</p>
      </div>
    </div>
  </article>
</div>
```

---

### Patrón: Metadatos + Contenido
```html
<article class="node">
  <!-- Metadatos -->
  <div class="node__meta">
    <div class="node__submitted">
      Por <a href="#" class="username">Usuario</a>
      el <time class="datetime">08/12/2025</time>
    </div>
  </div>
  
  <!-- Contenido -->
  <div class="node__content">
    <!-- Campos aquí -->
  </div>
</article>
```

---

### Patrón: Lista de Campos
```html
<div class="node__content">
  <!-- Campo 1 -->
  <div class="field field--type-email">
    <div class="field__label">Email</div>
    <div class="field__items">
      <div class="field__item">email@example.com</div>
    </div>
  </div>
  
  <!-- Campo 2 -->
  <div class="field field--type-datetime">
    <div class="field__label">Fecha</div>
    <div class="field__items">
      <time class="datetime">08/12/2025</time>
    </div>
  </div>
  
  <!-- Campo 3 (múltiples items) -->
  <div class="field">
    <div class="field__label">Categorías</div>
    <div class="field__items">
      <span class="field__item">Categoría 1</span>
      <span class="field__item">Categoría 2</span>
    </div>
  </div>
</div>
```

---

## 📱 Responsive Design

### Breakpoints Estándar
```css
/* Tablet */
@media (max-width: 768px) {
  /* Ajustes para pantallas medianas */
  padding: 1rem 0.75rem;
  font-size: 1.8rem; /* Títulos */
}

/* Móvil */
@media (max-width: 480px) {
  /* Ajustes para pantallas pequeñas */
  padding: 0.75rem 0.5rem;
  font-size: 1.3rem; /* Subtítulos */
}
```

### Estrategia Responsive
1. **Desktop First**: Los estilos base son para desktop
2. **Media Queries**: Reducir padding/margin en móvil
3. **Fuentes**: Reducir tamaños en breakpoints
4. **Espaciado**: Comprimir gaps y márgenes

---

## 💡 Casos de Uso Comunes

### Caso 1: Página de Artículo
```html
<div class="region region-content">
  <!-- Título -->
  <div id="block-bootstrap5-page-title">
    <h1>Título del Artículo</h1>
  </div>
  
  <!-- Artículo -->
  <article class="node">
    <!-- Meta -->
    <div class="node__meta">
      <div class="node__submitted">
        Por <a href="#" class="username">Autor</a>
        el <time class="datetime">08/12/2025</time>
      </div>
    </div>
    
    <!-- Contenido -->
    <div class="node__content">
      <!-- Imagen destacada -->
      <div class="field field--name-field-img">
        <div class="field__items">
          <div class="field__item">
            <img src="featured.jpg" alt="Imagen destacada">
          </div>
        </div>
      </div>
      
      <!-- Texto -->
      <div class="field field--name-body">
        <h2>Introducción</h2>
        <p>Lorem ipsum dolor sit amet...</p>
        
        <h2>Desarrollo</h2>
        <p>Consectetur adipiscing elit...</p>
      </div>
      
      <!-- Archivos adjuntos -->
      <div class="field">
        <div class="field__label">Documentos</div>
        <div class="field__items">
          <span class="file">
            <a href="doc1.pdf">Documento 1.pdf</a>
          </span>
          <span class="file">
            <a href="doc2.pdf">Documento 2.pdf</a>
          </span>
        </div>
      </div>
    </div>
  </article>
</div>
```

---

### Caso 2: Listado de Contenido (Views)
```html
<div class="view-content">
  <!-- Item 1 -->
  <div class="views-row">
    <img src="thumb1.jpg" alt="Thumbnail">
    <h3>Título del Item</h3>
    <p>Descripción breve del contenido...</p>
  </div>
  
  <!-- Item 2 -->
  <div class="views-row">
    <img src="thumb2.jpg" alt="Thumbnail">
    <h3>Título del Item 2</h3>
    <p>Otra descripción...</p>
  </div>
</div>
```

---

### Caso 3: Formulario de Datos (Solo Lectura)
```html
<article class="node">
  <div class="node__content">
    <!-- Email -->
    <div class="field field--type-email">
      <div class="field__label">Correo Electrónico</div>
      <div class="field__items">
        <div class="field__item">contacto@example.com</div>
      </div>
    </div>
    
    <!-- Teléfono -->
    <div class="field">
      <div class="field__label">Teléfono</div>
      <div class="field__items">
        <div class="field__item">+506 1234-5678</div>
      </div>
    </div>
    
    <!-- Dirección -->
    <div class="field">
      <div class="field__label">Dirección</div>
      <div class="field__items">
        <div class="field__item">San José, Costa Rica</div>
      </div>
    </div>
    
    <!-- Horario -->
    <div class="field field--type-datetime">
      <div class="field__label">Horario de Atención</div>
      <div class="field__items">
        <time class="datetime">Lunes a Viernes: 8:00 - 17:00</time>
      </div>
    </div>
  </div>
</article>
```

---

### Caso 4: Galería Multimedia
```html
<div class="field field--name-field-img">
  <div class="field__items">
    <!-- Imagen 1 -->
    <div class="field__item">
      <div class="media--type-image">
        <img src="gallery1.jpg" alt="Foto 1">
      </div>
    </div>
    
    <!-- Video -->
    <div class="field__item">
      <video controls>
        <source src="video.mp4" type="video/mp4">
      </video>
    </div>
    
    <!-- YouTube Embed -->
    <div class="field__item">
      <iframe class="media-oembed-content" 
              src="https://www.youtube.com/embed/..."
              frameborder="0"
              allowfullscreen>
      </iframe>
    </div>
    
    <!-- Audio -->
    <div class="field__item">
      <audio controls>
        <source src="podcast.mp3" type="audio/mpeg">
      </audio>
    </div>
  </div>
</div>
```

---

## 🔧 Tips de Personalización

### Modificar Colores de Marca
```css
/* Buscar y reemplazar en tu CSS */
#6EC1E4 → TU_COLOR_PRINCIPAL

/* Aplicar a: */
- h1, h2, h3, h4, h5
- .field__label
- Títulos de página
```

### Modificar Espaciado Global
```css
/* Ajustar gap en contenedores */
.region.region-content {
  gap: 30px; /* En lugar de 20px */
}

/* Ajustar margin-bottom en campos */
.field {
  margin-bottom: 1.5rem; /* En lugar de 1rem */
}
```

### Modificar Bordes Redondeados
```css
/* Buscar border-radius y ajustar */
border-radius: 0.75rem; → border-radius: 1rem; /* Más redondeado */
border-radius: 0.5rem;  → border-radius: 0.25rem; /* Menos redondeado */
```

### Añadir Nuevos Tipos de Mensaje
```css
/* Mensaje de error */
.region.region-content .messages--error {
  background: #fee;
  border: 1px solid #e74c3c;
  color: #c0392b;
}

/* Mensaje de advertencia */
.region.region-content .messages--warning {
  background: #fff3cd;
  border: 1px solid #f39c12;
  color: #8e5a00;
}
```

---

## 📋 Checklist de Implementación

- [ ] Copiar colores de la paleta a tu variables CSS
- [ ] Importar fuentes (Roboto, truenorg)
- [ ] Aplicar estructura HTML correcta (`.region.region-content`)
- [ ] Usar `.field` para datos estructurados
- [ ] Implementar `.node` para tarjetas de contenido
- [ ] Añadir clases `.file` para archivos
- [ ] Configurar mensajes del sistema
- [ ] Testear responsive en 768px y 480px
- [ ] Validar contraste de colores (accesibilidad)
- [ ] Optimizar imágenes y media

---

## 🚀 Ejemplos de Extensión

### Crear un Nuevo Componente Basado en Estilos Existentes

```css
/* Nuevo componente: Card destacada */
.featured-card {
  /* Basado en article.node */
  background-color: #ffffff;
  border-radius: 0.75rem;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.04);
  padding: 1.5rem 1.25rem;
  
  /* Añadidos personalizados */
  border-left: 4px solid #6EC1E4;  /* Borde de marca */
  background: linear-gradient(135deg, #ffffff 0%, #f8fcfe 100%);
}

.featured-card h2 {
  /* Basado en h2 del sistema */
  font-family: "Roboto", sans-serif;
  font-weight: 700;
  color: #6ec1e4;
  
  /* Personalización */
  font-size: 1.8rem;
  margin-bottom: 1rem;
}
```

---

## 📚 Recursos Adicionales

- **Bootstrap 5**: Los estilos base usan clases de Bootstrap
- **Drupal Field API**: Estructura de campos compatible
- **Flexbox Guide**: Para entender los layouts
- **Media Queries**: Para responsive design

---

## 🆘 Solución de Problemas

### Los estilos no se aplican
1. Verifica que la estructura HTML sea correcta
2. Asegúrate de que las clases estén bien escritas
3. Revisa la especificidad CSS (usa DevTools)
4. Confirma que el CSS esté cargado

### Las imágenes no se ven bien
1. Verifica que `border-radius: 10px` esté aplicado
2. Asegúrate de que las imágenes tengan `max-width: 100%`
3. Revisa el ratio de aspecto (`height: auto`)

### El responsive no funciona
1. Verifica los breakpoints (768px, 480px)
2. Asegúrate de tener `<meta name="viewport">` en el HTML
3. Testea en DevTools con dispositivos reales

---

## 📝 Notas Finales

- **Mantenibilidad**: Los comentarios en el CSS indican qué es reutilizable
- **Modularidad**: Puedes copiar secciones completas a otros proyectos
- **Escalabilidad**: Fácil añadir nuevos componentes siguiendo los patrones
- **Consistencia**: Todos los componentes usan la misma paleta y tipografía

---

**¿Preguntas?** Revisa los comentarios en el archivo CSS para más detalles sobre cada componente.

**Versión**: 1.0  
**Última actualización**: Diciembre 2025

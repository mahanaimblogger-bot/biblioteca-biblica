# 📖 Biblioteca de Recursos Bíblicos - Sistema Modular

## 📁 Estructura de Carpetas

La biblioteca está organizada jerárquicamente de la siguiente manera:

```
biblioteca-biblica/
├── catalogo.json                          # Índice principal de la biblioteca
├── index.html                             # Página web principal
│
└── libros/
    ├── genesis/
    │   ├── capitulo-1/
    │   │   └── estudio/
    │   │       ├── metadata.json          # Metadatos del estudio
    │   │       └── contenido.html         # Contenido HTML del estudio
    │   │
    │   ├── capitulo-4/
    │   │   ├── estudio/
    │   │   │   ├── metadata.json
    │   │   │   └── contenido.html
    │   │   └── sermon/
    │   │       ├── metadata.json
    │   │       └── contenido.html
    │   │
    │   └── capitulo-13/
    │       └── estudio/
    │           ├── metadata.json
    │           └── contenido.html
    │
    ├── salmos/
    │   └── capitulo-23/
    │       └── estudio/
    │           ├── metadata.json
    │           └── contenido.html
    │
    ├── romanos/
    │   └── capitulo-8/
    │       └── video/
    │           ├── metadata.json
    │           └── contenido.html
    │
    └── juan/
        └── capitulo-3/
            └── estudio/
                ├── metadata.json
                └── contenido.html
```

---

## 📝 Cómo Agregar un Nuevo Recurso

### Paso 1: Actualizar el catálogo (`catalogo.json`)

Agrega el libro y capítulo si no existen:

```json
{
  "libros": [
    {
      "id": "nombre-libro",
      "nombre": "Nombre del Libro",
      "abreviatura": "Abrev",
      "testamento": "antiguo|nuevo",
      "capitulos": [
        {
          "numero": 1,
          "recursos": ["estudio", "sermon"]
        }
      ]
    }
  ]
}
```

### Paso 2: Crear la estructura de carpetas

```
libros/
└── nombre-libro/
    └── capitulo-N/
        └── tipo-recurso/
            ├── metadata.json
            └── contenido.html
```

### Paso 3: Crear el archivo `metadata.json`

```json
{
  "tipo": "estudio",
  "titulo": "Título del Recurso",
  "subtitulo": "Subtítulo descriptivo",
  "autor": "Nombre del autor",
  "fechaCreacion": "2025-01-15",
  "fechaActualizacion": "2025-04-10",
  "versiculoClave": {
    "referencia": "Libro Capítulo:Versículo",
    "texto": "Texto del versículo..."
  },
  "temas": ["Tema 1", "Tema 2", "Tema 3"],
  "videoYoutube": "ID_DEL_VIDEO",
  "enlacePDF": "https://enlace-al-pdf.com",
  "archivoContenido": "contenido.html",
  "disponible": true
}
```

### Paso 4: Crear el archivo `contenido.html`

Este archivo contiene el HTML que se mostrará dentro del contenedor de la página.

**Ejemplo mínimo:**

```html
<h1 class="titulo-entrada">Título del Estudio</h1>

<div class="cita-versiculo">
<h3>Referencia</h3>
<p>Texto del versículo...</p>
</div>

<h2 class="subtitulo">Primera Sección</h2>
<p>Contenido del estudio...</p>

<div class="destacado">
<strong>Punto importante:</strong>
Explicación del punto...
</div>
```

---

## 🎨 Clases CSS Disponibles

### Títulos y Encabezados
| Clase | Uso |
|-------|-----|
| `titulo-entrada` | Título principal del recurso |
| `subtitulo` | Subtítulos de sección (h2) |

### Cajas Especiales
| Clase | Descripción |
|-------|-------------|
| `cita-versiculo` | Cita bíblica destacada |
| `caja-contexto` | Información contextual |
| `caja-linguistica` | Notas lingüísticas/hebreas |
| `caja-meditar` | Preguntas de reflexión |
| `caja-arqueologica` | Evidencia arqueológica |
| `caja-profetica` | Análisis profético |
| `destacado` | Punto destacado con borde |
| `destacado-dramatico` | Punto muy importante (fondo oscuro) |
| `aplicacion` | Aplicación práctica |

### Otros Elementos
| Clase | Uso |
|-------|-----|
| `versiculo` | Versículo simple |
| `separador` | Separador decorativo |
| `indice-nav` | Índice de navegación |
| `volver-indice` | Enlace para volver al índice |
| `contenedor-video` | Contenedor de video YouTube |
| `btn-descargar-pdf` | Botón de descarga PDF |
| `hebreo` | Texto en hebreo (RTL) |

### Tablas
Las tablas se estilizan automáticamente con encabezados oscuros y filas alternadas.

---

## 🎬 Tipos de Recurso Soportados

| Tipo | Icono | Carpeta |
|------|-------|---------|
| Estudio | 📖 | `estudio/` |
| Sermón | 🛐 | `sermon/` |
| Video | 🎬 | `video/` |
| Audio | 🎧 | `audio/` |
| Diapositivas | 📊 | `diapositiva/` |
| PDF | 📄 | `pdf/` |

---

## 🔧 Configuración

En el archivo `index.html`, puedes ajustar la ruta base:

```javascript
const CONFIG = {
    basePath: './biblioteca-biblica/', // Ruta a la carpeta de la biblioteca
    catalogFile: 'catalogo.json'
};
```

---

## 📋 Ejemplo Completo: Agregar Éxodo 20

### 1. Actualizar catálogo:

```json
{
  "id": "exodo",
  "nombre": "Éxodo",
  "abreviatura": "Éx",
  "testamento": "antiguo",
  "capitulos": [
    {
      "numero": 20,
      "recursos": ["estudio", "sermon"]
    }
  ]
}
```

### 2. Crear carpetas:

```
biblioteca-biblica/libros/exodo/capitulo-20/estudio/
biblioteca-biblica/libros/exodo/capitulo-20/sermon/
```

### 3. Crear metadata.json para el estudio:

```json
{
  "tipo": "estudio",
  "titulo": "Los Diez Mandamientos",
  "subtitulo": "La ley dada en el Sinaí",
  "autor": "Tu Nombre",
  "fechaCreacion": "2025-04-10",
  "fechaActualizacion": "2025-04-10",
  "versiculoClave": {
    "referencia": "Éxodo 20:1-2",
    "texto": "Y habló Dios todas estas palabras, diciendo: Yo soy Jehová tu Dios, que te saqué de la tierra de Egipto, de casa de servidumbre."
  },
  "temas": ["Ley", "Mandamientos", "Pacto", "Sinaí"],
  "archivoContenido": "contenido.html",
  "disponible": true
}
```

### 4. Crear contenido.html:

```html
<h1 class="titulo-entrada">Los Diez Mandamientos</h1>

<div class="cita-versiculo">
<h3>Éxodo 20:1-17</h3>
<p>Y habló Dios todas estas palabras...</p>
</div>

<div class="caja-contexto">
<h3>📍 Contexto del Pasaje</h3>
<ul>
<li><strong>Autor:</strong> Moisés</li>
<li><strong>Ubicación:</strong> Monte Sinaí</li>
<li><strong>Fecha:</strong> c. 1446 a.C.</li>
</ul>
</div>

<h2 class="subtitulo">Introducción</h2>
<p>Contenido del estudio...</p>
```

---

## 🚀 Cómo Ejecutar

### Opción 1: Servidor Local (Recomendado)

Debido a las restricciones CORS de los navegadores, necesitas un servidor local:

```bash
# Con Python 3
cd /home/z/my-project/biblioteca-biblica
python -m http.server 8000

# Luego abre en el navegador:
# http://localhost:8000
```

### Opción 2: Extensión de VS Code

Usa la extensión "Live Server" para servir los archivos.

### Opción 3: Hosting Web

Sube toda la carpeta `biblioteca-biblica` a cualquier servidor web (GitHub Pages, Netlify, Vercel, etc.)

---

## ✅ Ventajas del Sistema Modular

1. **Escalabilidad**: Agrega nuevos recursos sin tocar el código
2. **Organización**: Cada recurso en su propia carpeta
3. **Mantenimiento**: Actualiza un recurso sin afectar otros
4. **Colaboración**: Múltiples personas pueden trabajar en diferentes recursos
5. **Portabilidad**: Fácil de respaldar y mover
6. **Flexibilidad**: Soporta cualquier tipo de contenido HTML

---

## 📞 Soporte

Para preguntas o sugerencias, contacta al equipo de desarrollo.

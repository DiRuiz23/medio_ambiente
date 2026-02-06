# Documentación Técnica - Sitio Web de Conciencia Ambiental

##  Índice

1. [Descripción del Proyecto](#descripción-del-proyecto)
2. [Tecnologías Utilizadas](#tecnologías-utilizadas)
3. [Estructura del Proyecto](#estructura-del-proyecto)
4. [Proceso de Implementación](#proceso-de-implementación)
5. [Características Implementadas](#características-implementadas)
6. [Guía de Instalación](#guía-de-instalación)

---

## Descripción del Proyecto

Aplicación web educativa sobre medio ambiente desarrollada con Flask que presenta información sobre la importancia del cuidado ambiental, sistemas de gestión ambiental, y las 3 R del reciclaje (Reducir, Reutilizar, Reciclar).

**Objetivo:** Crear una plataforma web visualmente atractiva y educativa que genere conciencia ambiental mediante contenido informativo y diseño moderno.

---

## Tecnologías Utilizadas

### Backend

- **Python** - Lenguaje de programación
- **Flask** - Framework web minimalista
  - `Flask` - Clase principal de la aplicación
  - `render_template` - Motor de plantillas Jinja2

### Frontend

- **HTML5** - Estructura de las páginas
- **CSS3** - Estilos personalizados
- **Bootstrap 5.3.2** - Framework CSS para diseño responsive
- **Google Fonts** - Tipografía moderna
  - Montserrat (títulos)
  - Open Sans (texto)

### Arquitectura

- **Patrón MVC** - Model-View-Controller
- **Motor de plantillas Jinja2** - Herencia de templates
- **Servidor de desarrollo Flask** - Puerto 5000 (debug mode)

---

## Estructura del Proyecto

```
medio_ambiente/
│
├── app.py                          # Aplicación principal Flask
├── DOCUMENTACION_TECNICA.md        # Este documento
│
├── static/                         # Recursos estáticos
│   ├── css/
│   │   └── style.css              # Estilos personalizados
│   └── images/                    # Imágenes del sitio
│       ├── ambiente.jpg
│       ├── sistema.jpg
│       ├── futuro.jpg
│       ├── reducir.jpg
│       ├── reutilizar.jpg
│       └── reciclar.jpg
│
└── templates/                      # Plantillas HTML
    ├── base.html                  # Plantilla base (navbar, footer)
    ├── index.html                 # Página principal
    ├── sistema.html               # Sistema de Gestión Ambiental
    ├── futuro.html                # El futuro del planeta
    └── tres_r.html                # Las 3 R del reciclaje
```

---

## Proceso de Implementación

### Fase 1: Configuración Inicial del Proyecto

#### Paso 1.1: Crear estructura de directorios

```bash
mkdir medio_ambiente
cd medio_ambiente
mkdir static static/css static/images templates
```

#### Paso 1.2: Crear entorno virtual

```bash
python -m venv venv
venv\Scripts\Activate.ps1  # Windows PowerShell
```

#### Paso 1.3: Instalar Flask

```bash
pip install Flask
```

#### Paso 1.4: Crear aplicación Flask básica ([app.py](file:///c:/Repositorios/medio_ambiente/app.py))

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html', breadcrumb=["Inicio"])

@app.route('/sistema-ambiental')
def sistema():
    return render_template('sistema.html',
                         breadcrumb=["Inicio", "Sistema de Gestión Ambiental"])

@app.route('/futuro')
def futuro():
    return render_template('futuro.html',
                         breadcrumb=["Inicio", "Futuro del Planeta"])

@app.route('/tres-r')
def tres_r():
    return render_template('tres_r.html',
                         breadcrumb=["Inicio", "Las 3 R"])

if __name__ == '__main__':
    app.run(debug=True)
```

**Conceptos clave:**

- `@app.route()` - Decorador que define las rutas URL
- `render_template()` - Renderiza plantillas HTML con contexto
- `breadcrumb` - Lista pasada como contexto a las plantillas

---

### Fase 2: Creación de Plantillas HTML

#### Paso 2.1: Plantilla base ([base.html](file:///c:/Repositorios/medio_ambiente/templates/base.html))

**Características implementadas:**

- DOCTYPE HTML5
- Meta tags para charset y viewport (responsive)
- Vinculación de Google Fonts
- Navbar responsive con Bootstrap 5
- Sistema de breadcrumb dinámico
- Footer común para todas las páginas
- Bloque de contenido heredable (`{% block content %}`)

**Elementos clave del navbar:**

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-success">
  <div class="container">
    <a class="navbar-brand" href="/">🌍 Medio Ambiente</a>
    <button class="navbar-toggler" ...>
    <div class="collapse navbar-collapse">
      <ul class="navbar-nav ms-auto">
        <li><a href="/">Inicio</a></li>
        <li><a href="/sistema-ambiental">Sistema Ambiental</a></li>
        <li><a href="/futuro">Futuro</a></li>
        <li><a href="/tres-r">3 R</a></li>
      </ul>
    </div>
  </div>
</nav>
```

**Sistema de breadcrumb:**

```html
<nav>
  <ol class="breadcrumb">
    {% for item in breadcrumb %}
    <li class="breadcrumb-item">{{ item }}</li>
    {% endfor %}
  </ol>
</nav>
```

#### Paso 2.2: Plantilla de inicio ([index.html](file:///c:/Repositorios/medio_ambiente/templates/index.html))

Estructura de 5 secciones:

1. **Hero Section** - Presentación principal con imagen
2. **Cards de navegación** - 3 tarjetas enlazadas a secciones
3. **Estadísticas** - 4 datos impactantes sobre el medio ambiente
4. **Call to Action** - Sección motivacional con badges

#### Paso 2.3: Plantillas de contenido

- [sistema.html](file:///c:/Repositorios/medio_ambiente/templates/sistema.html) - Card con imagen y descripción de SGA
- [futuro.html](file:///c:/Repositorios/medio_ambiente/templates/futuro.html) - Card con impacto en futuras generaciones
- [tres_r.html](file:///c:/Repositorios/medio_ambiente/templates/tres_r.html) - 3 cards independientes (Reducir, Reutilizar, Reciclar)

---

### Fase 3: Diseño Visual y Estilos CSS

#### Paso 3.1: Paleta de colores personalizada

```css
:root {
  --verde-primario: #2d6a4f; /* Verde oscuro */
  --verde-secundario: #52b788; /* Verde medio */
  --verde-claro: #95d5b2; /* Verde claro */
  --tierra: #8b4513; /* Marrón */
  --cielo: #87ceeb; /* Azul cielo */
  --blanco: #ffffff;
  --gris-oscuro: #212529;
}
```

**Justificación:** Colores inspirados en la naturaleza para reforzar el tema ambiental.

#### Paso 3.2: Tipografía moderna

```css
body {
  font-family: "Open Sans", sans-serif;
  color: #333;
  line-height: 1.7;
}

h1,
h2,
h3,
h4,
h5,
h6,
.navbar-brand {
  font-family: "Montserrat", sans-serif;
  font-weight: 700;
}
```

**Decisión de diseño:**

- **Open Sans** - Legibilidad óptima para párrafos
- **Montserrat** - Impacto visual en títulos

#### Paso 3.3: Navbar con gradiente

```css
.navbar {
  background: linear-gradient(
    135deg,
    var(--verde-primario) 0%,
    var(--verde-secundario) 100%
  ) !important;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
```

#### Paso 3.4: Efectos hover en navegación

```css
.nav-link::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 2px;
  background: var(--blanco);
  transition: all 0.3s ease;
  transform: translateX(-50%);
}

.nav-link:hover::after {
  width: 80%;
}
```

#### Paso 3.5: Cards elegantes

```css
.content-card {
  background: var(--blanco);
  border: none;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition:
    transform 0.4s ease,
    box-shadow 0.4s ease;
}

.content-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 50px rgba(45, 106, 79, 0.2);
}

.content-card:hover img {
  transform: scale(1.05);
}
```

**Efectos implementados:**

- Elevación al hacer hover (-10px en Y)
- Sombra más pronunciada
- Zoom de imagen (scale 1.05)

#### Paso 3.6: Animaciones de entrada

```css
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.container {
  animation: fadeIn 0.6s ease-out;
}

.content-card {
  animation: fadeIn 0.7s ease-out 0.2s both;
}
```

## Guía de Instalación

### Requisitos previos

- Python 3.8 o superior
- pip (gestor de paquetes de Python)

### Instalación paso a paso

1. **Clonar o descargar el proyecto**

```bash
cd c:\Repositorios\medio_ambiente
```

2. **Crear entorno virtual**

```bash
python -m venv venv
```

3. **Activar entorno virtual**

```bash
# Windows PowerShell
.\venv\Scripts\Activate.ps1

# Windows CMD
.\venv\Scripts\activate.bat
```

4. **Instalar dependencias**

```bash
pip install Flask
```

5. **Agregar las imágenes necesarias**
   Colocar en `static/images/`:

- `ambiente.jpg` - Imagen para página principal
- `sistema.jpg` - Sistema de Gestión Ambiental
- `futuro.jpg` - El futuro del planeta
- `reducir.jpg` - Icono Reducir
- `reutilizar.jpg` - Icono Reutilizar
- `reciclar.jpg` - Icono Reciclar

6. **Ejecutar la aplicación**

```bash
python app.py
```

7. **Acceder al sitio**
   Abrir navegador en: `http://localhost:5000`

---

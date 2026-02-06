# Sitio Web de Conciencia Ambiental

Aplicación web educativa desarrollada con Flask que promueve la conciencia ambiental a través de información sobre sistemas de gestión ambiental y las 3 R del reciclaje.

##  Características

-  Diseño moderno y responsive con Bootstrap 5
-  Animaciones suaves y efectos hover
-  Paleta de colores inspirada en la naturaleza
-  Tipografía profesional (Google Fonts)
-  Estadísticas impactantes sobre el medio ambiente
-  Sistema de navegación intuitivo

##  Secciones

1. **Inicio** - Landing page con hero section, estadísticas y call to action
2. **Sistema Ambiental** - Información sobre sistemas de gestión ambiental
3. **Futuro** - Impacto de nuestras acciones en las próximas generaciones
4. **Las 3 R** - Reducir, Reutilizar y Reciclar

##  Tecnologías

- **Backend:** Python + Flask
- **Frontend:** HTML5, CSS3, Bootstrap 5.3.2
- **Fuentes:** Google Fonts (Montserrat, Open Sans)

##  Instalación

1. Clonar el repositorio:

```bash
git clone https://github.com/TU_USUARIO/medio_ambiente.git
cd medio_ambiente
```

2. Crear entorno virtual:

```bash
python -m venv venv
```

3. Activar entorno virtual:

```bash
# Windows PowerShell
.\venv\Scripts\Activate.ps1

# Windows CMD
.\venv\Scripts\activate.bat
```

4. Instalar dependencias:

```bash
pip install Flask
```

5. Agregar imágenes en `static/images/`:
   - `ambiente.jpg`
   - `sistema.jpg`
   - `futuro.jpg`
   - `reducir.jpg`
   - `reutilizar.jpg`
   - `reciclar.jpg`

6. Ejecutar la aplicación:

```bash
python app.py
```

7. Abrir en el navegador: `http://localhost:5000`

##  Estructura del Proyecto

```
medio_ambiente/
├── app.py                    # Aplicación Flask
├── static/
│   ├── css/
│   │   └── style.css        # Estilos personalizados
│   └── images/              # Imágenes del sitio
├── templates/               # Plantillas HTML
│   ├── base.html           # Template base
│   ├── index.html          # Página principal
│   ├── sistema.html        # Sistema ambiental
│   ├── futuro.html         # Futuro del planeta
│   └── tres_r.html         # Las 3 R
└── DOCUMENTACION_TECNICA.md # Documentación completa
```

##  Autor

Juan Diego Ruiz Rivera

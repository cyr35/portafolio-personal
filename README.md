# Portfolio Sergio Carvajal

Portfolio personal profesional con diseño minimalista y gestión de contenido mediante JSON.

## 🚀 Características

- **Diseño Responsivo**: Optimizado para desktop, tablet y móvil
- **Light Mode Minimalista**: Paleta gris-azul profesional
- **Contenido Dinámico**: Basado en `data.json` (fácil de actualizar)
- **Sin Dependencias Externas**: HTML, CSS, JavaScript vanilla
- **Deploy en Cloudflare Pages**: Gratis y con dominio personalizado
- **Compatible con GitHub**: Control de versión integrado

## 📁 Estructura del Proyecto

```
portfolio/
├── index.html          # Sitio principal (HTML + CSS + JS)
├── data.json          # Base de datos del contenido
├── README.md          # Este archivo
├── .gitignore         # Archivos a ignorar en Git
└── .nojekyll          # Para que Cloudflare Pages renderice correctamente
```

## 🛠️ Setup Inicial

### 1. Clonar o Descargar Archivos

```bash
git clone https://github.com/yourusername/portfolio.git
cd portfolio
```

O simplemente descarga los archivos en una carpeta local.

### 2. Personalizar `data.json`

Abre `data.json` y actualiza:

**Profile (sección de contacto)**
```json
"profile": {
    "name": "Tu Nombre",
    "title": "Tu Título Profesional",
    "location": "Tu Ciudad, País",
    "email": "tu-email@ejemplo.com",
    "phone": "+XX XXX XXX XXXX",
    "linkedin": "https://linkedin.com/in/tu-usuario",
    "github": "https://github.com/tu-usuario",
    "about": "Descripción completa aquí..."
}
```

**Skills** - Agregar/editar categorías:
```json
"skills": {
    "Tu Categoría": [
        "Skill 1",
        "Skill 2",
        "Skill 3"
    ]
}
```

**Proyectos** - Agregar nuevos proyectos:
```json
{
    "id": X,
    "title": "Nombre del Proyecto",
    "category": "Categoría",
    "description": "Descripción breve",
    "technologies": ["Tech1", "Tech2"],
    "achievements": ["Logro 1", "Logro 2"],
    "featured": true  // Aparece destacado
}
```

**Blog** - Agregar artículos:
```json
{
    "id": X,
    "title": "Título del Artículo",
    "excerpt": "Resumen corto",
    "content": "Contenido completo del artículo",
    "date": "2024-01-15",
    "category": "Categoría",
    "readTime": "5 min"
}
```

**Testimonios** - Agregar referencias:
```json
{
    "id": X,
    "author": "Nombre de Persona",
    "position": "Su Posición",
    "text": "El testimonio",
    "company": "Empresa",
    "date": "2024-01-10"
}
```

### 3. Prueba Local

Abre `index.html` en tu navegador o sirve localmente:

```bash
# Con Python 3
python -m http.server 8000

# Con Node.js
npx http-server

# Con VS Code
Instala "Live Server" extension y haz clic derecho > "Open with Live Server"
```

Visita `http://localhost:8000` (o el puerto que uses)

## 📤 Deploy en Cloudflare Pages

### Opción A: Cloudflare Pages (Recomendado)

1. **Sube a GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/yourusername/portfolio.git
   git branch -M main
   git push -u origin main
   ```

2. **Conecta con Cloudflare Pages**
   - Ve a [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - Click "Pages" en el menú izquierdo
   - Click "Connect to Git"
   - Autoriza GitHub y selecciona tu repositorio `portfolio`
   - Settings:
     - Project name: `portfolio` (o tu preferencia)
     - Production branch: `main`
     - Framework: `None` (esto es static)
     - Build command: (dejar en blanco)
     - Build output directory: (dejar en blanco)
   - Click "Save and Deploy"

3. **Espera el deploy** (~1-2 minutos)
   - Tu sitio estará en `https://portfolio.pages.dev`

4. **Configura Dominio Personalizado (Opcional)**
   - En Cloudflare Pages, click en "Custom domain"
   - Ingresa tu dominio (ej: `sergio-carvajal.dev`)
   - Sigue las instrucciones para actualizar DNS

### Opción B: Despliegue Manual

Si prefieres no usar GitHub:

1. Crea un proyecto vacío en Cloudflare Pages
2. Sube los archivos manualmente vía Cloudflare Dashboard
3. Deploy automático

## 📝 Cómo Mantener el Contenido

### Actualizar Información

1. **Edita `data.json`** directamente
2. **Commit y Push a GitHub**
   ```bash
   git add data.json
   git commit -m "Update: descripción del cambio"
   git push
   ```
3. **Cloudflare Pages redeploy automáticamente** en ~1 minuto

### Agregar Nuevo Proyecto

1. Abre `data.json`
2. En la sección `"projects": [...]`, agrega un nuevo objeto:
   ```json
   {
       "id": 6,
       "title": "Mi Nuevo Proyecto",
       "category": "Infrastructure",
       "description": "Descripción del proyecto",
       "technologies": ["Docker", "Linux"],
       "achievements": ["Logro 1", "Logro 2"],
       "featured": true
   }
   ```
3. Guarda, commit y push

### Agregar Artículo de Blog

1. En la sección `"blog": [...]`, agrega:
   ```json
   {
       "id": 5,
       "title": "Cómo Configurar VPN en Linux",
       "excerpt": "Guía paso a paso para configurar un servidor VPN",
       "content": "El contenido del artículo aquí...",
       "date": "2024-05-14",
       "category": "Networking",
       "readTime": "10 min"
   }
   ```

## 🎨 Personalizar Estilos

Para cambiar colores, fuentes o diseño:

1. Abre `index.html`
2. Busca la sección `:root` en el `<style>`
3. Modifica las variables CSS:
   ```css
   :root {
       --primary-color: #0f172a;      /* Color oscuro principal */
       --accent-color: #0ea5e9;       /* Azul destacado */
       --text-primary: #1e293b;       /* Texto principal */
       /* ... más variables */
   }
   ```

## 🔧 Troubleshooting

### El sitio no carga en Cloudflare Pages

1. Verifica que `index.html` está en la raíz
2. Verifica que `data.json` está en la raíz
3. En Cloudflare, asegúrate que "Build output directory" esté vacío
4. Haz un nuevo push para retrigger el deploy

### Los datos no aparecen

1. Abre la consola del navegador (F12)
2. Busca errores en la pestaña "Console"
3. Verifica que `data.json` sea JSON válido (usa [jsonlint.com](https://jsonlint.com))

### Las imágenes no cargan

Este sitio no usa imágenes. Si quieres agregarlas:
1. Sube a una carpeta `/images` en el repositorio
2. Referencia en HTML: `<img src="images/nombre.jpg" alt="...">`
3. O usa URLs externas

## 📋 Checklist antes de Publicar

- [ ] Actualizar `data.json` con tu información
- [ ] Revisar todas las secciones en navegador local
- [ ] Verificar links (email, LinkedIn, GitHub)
- [ ] Ajustar colores si lo deseas
- [ ] Crear repositorio GitHub
- [ ] Conectar con Cloudflare Pages
- [ ] Configurar dominio personalizado
- [ ] Compartir URL pública

## 🚀 Optimizaciones Futuras

Cosas que puedes agregar sin complicar mucho:

- [ ] Favicon personalizado
- [ ] Dark mode toggle (CSS + JS)
- [ ] Formulario de contacto (Formspree, Netlify Forms)
- [ ] Analytics (Google Analytics, Cloudflare Analytics)
- [ ] Open Graph meta tags (para mejor compartición)
- [ ] Animations on scroll
- [ ] Search functionality

## 📄 Licencia

Este proyecto es tuyo. Úsalo, modifícalo y comparte como desees.

---

**¿Preguntas?** Revisa la documentación de Cloudflare Pages: https://developers.cloudflare.com/pages/

# 🚀 Quick Start Guide - Primeros Pasos

Sigue estos pasos para tener tu portfolio online en Cloudflare Pages en **menos de 10 minutos**.

## Paso 1: Personaliza tu `data.json` (2 minutos)

1. Abre `data.json` con un editor de texto (VS Code, Notepad, etc.)
2. Actualiza la sección `profile`:
   ```json
   "profile": {
       "name": "Sergio Carvajal Appelgren",
       "email": "sergio.carvajal.a@gmail.com",
       "phone": "+1 (437) 660-9353",
       "linkedin": "https://linkedin.com/in/sergio-carvajal-a-79209829b",
       "github": "https://github.com/yourusername"  // ← Cambia esto
   }
   ```
3. Guarda el archivo (Ctrl+S)

## Paso 2: Prueba Localmente (1 minuto)

1. Abre `index.html` con tu navegador
2. Verifica que ves tu nombre y datos
3. Navega por las secciones

## Paso 3: Crea un Repositorio en GitHub (2 minutos)

1. Ve a https://github.com/new
2. Name: `portfolio` (o `mi-portfolio`)
3. Description: "My professional portfolio"
4. Make it **Public**
5. Click "Create repository"
6. **Copia la URL** (parecerá a: `https://github.com/yourusername/portfolio.git`)

## Paso 4: Sube los Archivos a GitHub (3 minutos)

### Con Git (Terminal/CMD):

```bash
# Navega a la carpeta de tu proyecto
cd /ruta/a/tu/portfolio

# Inicializa git
git init

# Agrega todos los archivos
git add .

# Crea el primer commit
git commit -m "Initial commit: Portfolio setup"

# Conecta con tu repositorio GitHub
git remote add origin https://github.com/yourusername/portfolio.git

# Cambia la rama a 'main'
git branch -M main

# Sube a GitHub
git push -u origin main
```

### Sin Git (Alternativa Manual):

1. Ve a tu repositorio en GitHub
2. Click "Add file" > "Upload files"
3. Arrastra los archivos a la ventana
4. Click "Commit changes"

## Paso 5: Deploy en Cloudflare Pages (2 minutos)

1. Ve a https://dash.cloudflare.com/
   - Si no tienes cuenta, crea una (es gratis)

2. Click en **"Pages"** en el menú izquierdo

3. Click **"Connect to Git"**

4. Autoriza GitHub y busca tu repositorio `portfolio`

5. En la configuración:
   - **Project name**: `portfolio`
   - **Production branch**: `main`
   - **Framework**: Dejar en blanco (None)
   - **Build command**: Dejar en blanco
   - **Build output directory**: Dejar en blanco

6. Click **"Save and Deploy"**

7. **¡Listo!** Tu sitio estará en `https://portfolio.pages.dev` en 1-2 minutos

## Paso 6: Comparte tu Portafolio

Tu URL: `https://portfolio.pages.dev`

Puedes:
- Agregar a tu LinkedIn
- Compartir en email
- Incluir en tu CV/Resume

---

## 📝 Próximos Pasos (Opcional)

### Personalizar Dominio

Si tienes un dominio (ej: `tu-nombre.com`):

1. En Cloudflare Pages, click "Custom domains"
2. Ingresa tu dominio
3. Sigue las instrucciones para actualizar DNS

### Agregar Más Proyectos/Blog

1. Edita `data.json` directamente en GitHub o localmente
2. Agrega un nuevo proyecto:
   ```json
   {
       "id": 6,
       "title": "Mi Nuevo Proyecto",
       "category": "Infrastructure",
       "description": "...",
       "technologies": ["Docker", "Linux"],
       "achievements": ["...", "..."],
       "featured": true
   }
   ```
3. Push a GitHub
4. Cloudflare Pages se actualiza automáticamente (~1 min)

### Cambiar Colores/Diseño

Abre `index.html` y busca las variables CSS:

```css
:root {
    --primary-color: #0f172a;      /* Negro-azul */
    --accent-color: #0ea5e9;       /* Azul cielo */
    --text-primary: #1e293b;       /* Gris oscuro */
    --text-secondary: #64748b;     /* Gris claro */
}
```

Cambia los colores HEX según tu preferencia.

---

## ✅ Checklist Final

- [ ] `data.json` personalizado con tu info
- [ ] Repositorio GitHub creado
- [ ] Archivos pusheados a GitHub
- [ ] Cloudflare Pages conectado
- [ ] Sitio live en `https://portfolio.pages.dev`
- [ ] URL compartida en LinkedIn/CV

---

## 🆘 Problemas Comunes

**P: El sitio no aparece en Cloudflare**
- A: Espera 2-3 minutos después de hacer push
- Verifica que `index.html` y `data.json` estén en la raíz

**P: Los datos no se actualizan**
- A: Verifica que `data.json` sea JSON válido (sin errores de sintaxis)
- Hard refresh: Ctrl+Shift+R (Windows) o Cmd+Shift+R (Mac)

**P: Quiero cambiar el dominio después**
- A: En Cloudflare Pages > Custom domains > Cambia cuando quieras

---

¡Listo! Ahora tienes un portfolio profesional online. 🎉

Cualquier cambio en `data.json`, simplemente push a GitHub y Cloudflare se actualiza automáticamente.

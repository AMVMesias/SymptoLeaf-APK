# 🚀 Guía Rápida de Despliegue en GitHub Pages

## Pasos para Publicar tu Landing Page

### 1️⃣ Inicializar y Preparar el Repositorio

```powershell
# Navega a la carpeta SymptoLeaf-APK
cd "c:\Users\mesia\Desktop\Universidad\Moviles\3P\Apk Page\SymptoLeaf-APK"

# Inicializa Git (si no está inicializado)
git init

# Agrega todos los archivos
git add .

# Crea el primer commit
git commit -m "🌿 feat: Add SymptoLeaf landing page with APK"
```

### 2️⃣ Crear Repositorio en GitHub

1. Ve a [GitHub](https://github.com) e inicia sesión
2. Click en el botón **"+"** en la esquina superior derecha
3. Selecciona **"New repository"**
4. Nombre del repositorio: `SymptoLeaf-APK` o `symptolea` (tu elección)
5. Descripción: `Landing page oficial para SymptoLeaf - Detección de enfermedades en plantas con IA`
6. Selecciona **Public** (GitHub Pages requiere repos públicos en plan gratuito)
7. ❌ NO marques "Initialize with README" (ya tienes uno)
8. Click en **"Create repository"**

### 3️⃣ Conectar y Subir tu Código

```powershell
# Reemplaza TU-USUARIO con tu nombre de usuario de GitHub
git remote add origin https://github.com/TU-USUARIO/SymptoLeaf-APK.git

# Renombra la rama a 'main' (si es necesario)
git branch -M main

# Sube todos los archivos a GitHub
git push -u origin main
```

### 4️⃣ Activar GitHub Pages

1. En tu repositorio de GitHub, ve a **Settings** (⚙️ Configuración)
2. En el menú lateral izquierdo, busca y click en **Pages**
3. En **Source** (Fuente):
   - Branch: Selecciona `main`
   - Folder: Selecciona `/ (root)`
4. Click en **Save** (Guardar)
5. ⏳ Espera 2-5 minutos mientras GitHub construye tu sitio

### 5️⃣ ¡Listo! Accede a tu Página

Tu landing page estará disponible en:
```
https://TU-USUARIO.github.io/SymptoLeaf-APK/
```

O si nombraste el repo diferente:
```
https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/
```

---

## 📋 Checklist de Verificación

Antes de publicar, verifica que:

- [ ] El archivo `symptoleaf.apk` existe y es menor a 100MB
- [ ] Las imágenes en `assets/` se cargan correctamente
- [ ] El archivo `index.html` no tiene errores de sintaxis
- [ ] Los estilos en `styles.css` funcionan bien
- [ ] El JavaScript en `script.js` no tiene errores
- [ ] El README.md tiene instrucciones claras

---

## 🔄 Actualizar la Página

Cuando necesites hacer cambios:

```powershell
# Navega a tu carpeta
cd "c:\Users\mesia\Desktop\Universidad\Moviles\3P\Apk Page\SymptoLeaf-APK"

# Haz tus cambios en los archivos...

# Agrega los cambios
git add .

# Crea un commit descriptivo
git commit -m "✨ update: Mejora en la sección de características"

# Sube los cambios
git push
```

Los cambios se verán reflejados en tu sitio en 1-2 minutos.

---

## 🎨 Actualizaciones Comunes

### Actualizar el APK
```powershell
# Desde tu proyecto Flutter, compila una nueva versión
cd "c:\Users\mesia\AndroidStudioProjects\SymptoLeaf"
flutter build apk --release

# Copia el nuevo APK
Copy-Item "build\app\outputs\flutter-apk\app-release.apk" -Destination "..\SymptoLeaf-APK\symptoleaf.apk" -Force

# Sube los cambios
cd "..\SymptoLeaf-APK"
git add symptoleaf.apk
git commit -m "🔄 update: Nueva versión del APK"
git push
```

### Cambiar Colores del Tema
Edita las variables en `styles.css` (líneas 10-15):
```css
--primary: #10B981;       /* Verde principal */
--secondary: #3B82F6;     /* Azul secundario */
--accent: #8B5CF6;        /* Morado acento */
```

### Agregar Screenshots
1. Agrega imágenes nuevas en la carpeta `assets/`
2. Actualiza el HTML en `index.html` (sección Screenshots)
3. Commit y push

---

## ⚠️ Solución de Problemas

### "El APK es muy grande (> 100MB)"
```powershell
# Opción 1: Genera APKs separados por arquitectura (más pequeños)
flutter build apk --release --split-per-abi

# Esto crea 3 APKs más pequeños:
# - app-armeabi-v7a-release.apk (ARM 32-bit)
# - app-arm64-v8a-release.apk (ARM 64-bit) ← La más común
# - app-x86_64-release.apk (x86 64-bit)

# Usa solo el arm64 que es el más compatible
Copy-Item "build\app\outputs\flutter-apk\app-arm64-v8a-release.apk" -Destination "..\SymptoLeaf-APK\symptoleaf.apk"
```

### "La página no se ve"
- Espera 5-10 minutos después de activar GitHub Pages
- Verifica que el repositorio sea **público**
- Limpia la caché del navegador (Ctrl + F5)
- Revisa la consola del navegador (F12) para ver errores

### "Las imágenes no cargan"
- Verifica que las rutas sean correctas (case-sensitive en Linux)
- Asegúrate de que los archivos existan en `assets/`
- Revisa que no haya espacios en los nombres de archivos

---

## 🌐 Dominio Personalizado (Opcional)

Para usar `www.symptolea.com` en lugar de `usuario.github.io`:

1. Compra un dominio en Namecheap, GoDaddy, etc.
2. En GitHub Pages settings, agrega tu dominio en "Custom domain"
3. En tu proveedor de dominio, configura estos DNS:

```
Tipo    Host    Valor
A       @       185.199.108.153
A       @       185.199.109.153
A       @       185.199.110.153
A       @       185.199.111.153
CNAME   www     TU-USUARIO.github.io
```

4. Espera 24-48 horas para propagación DNS

---

## 📊 Añadir Google Analytics (Opcional)

Para trackear visitantes, agrega antes de `</head>` en `index.html`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

Obtén tu ID en [Google Analytics](https://analytics.google.com/)

---

## 💡 Tips Pro

1. **Optimiza las imágenes**: Usa herramientas como TinyPNG para reducir el tamaño
2. **SEO**: Edita las meta tags en `index.html` para mejor posicionamiento
3. **Social Media**: Agrega Open Graph tags para compartir en redes sociales
4. **PWA**: Considera convertir la página en Progressive Web App

---

## ✅ Siguiente Paso

**¡Ejecuta los comandos de la sección 1 y 3 para publicar ahora!** 🚀

```powershell
cd "c:\Users\mesia\Desktop\Universidad\Moviles\3P\Apk Page\SymptoLeaf-APK"
git init
git add .
git commit -m "🌿 feat: Add SymptoLeaf landing page"
# Luego sigue las instrucciones de GitHub
```

---

**¿Necesitas ayuda?** Consulta la [documentación oficial de GitHub Pages](https://docs.github.com/es/pages)

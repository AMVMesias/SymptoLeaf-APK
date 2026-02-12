# SymptoLeaf Landing Page 🌿

Landing page oficial para SymptoLeaf - Aplicación móvil inteligente para la detección de enfermedades en plantas usando Machine Learning e IA Generativa.

## 🚀 Despliegue en GitHub Pages

Esta página está diseñada para ser desplegada en GitHub Pages. Sigue estos pasos:

### 1. Preparar el Repositorio

```bash
# Asegúrate de estar en la carpeta correcta
cd "SymptoLeaf-APK"

# Inicializa el repositorio (si no está inicializado)
git init

# Agrega todos los archivos
git add .

# Crea el primer commit
git commit -m "🌿 Initial commit: SymptoLeaf landing page"
```

### 2. Agregar el APK

**IMPORTANTE**: Antes de subir, necesitas copiar el APK compilado a esta carpeta.

```bash
# Copia el APK desde la carpeta de build de Flutter
# Desde la raíz del proyecto Flutter:
cp "build/app/outputs/flutter-apk/app-release.apk" "../SymptoLeaf-APK/symptoleaf.apk"
```

### 3. Subir a GitHub

```bash
# Crea un nuevo repositorio en GitHub llamado "SymptoLeaf-APK"
# Luego conecta tu repositorio local:

git remote add origin https://github.com/TU-USUARIO/SymptoLeaf-APK.git
git branch -M main
git push -u origin main
```

### 4. Activar GitHub Pages

1. Ve a tu repositorio en GitHub
2. Click en **Settings** (Configuración)
3. En el menú lateral, click en **Pages**
4. En **Source**, selecciona la rama `main` y carpeta `/ (root)`
5. Click en **Save**
6. ¡Listo! Tu página estará disponible en `https://TU-USUARIO.github.io/SymptoLeaf-APK/`

## 📁 Estructura de Archivos

```
SymptoLeaf-APK/
├── index.html          # Página principal
├── styles.css          # Estilos CSS
├── script.js           # JavaScript para interactividad
├── README.md           # Este archivo
├── symptoleaf.apk      # APK de la aplicación (debes agregarlo)
└── assets/
    ├── logo.png        # Logo de la aplicación
    └── app_showcase.png # Screenshot de la app
```

## 🎨 Características de la Landing Page

- ✨ **Diseño Moderno**: UI/UX limpio con gradientes y animaciones suaves
- 📱 **Responsive**: Adaptable a móviles, tablets y desktop
- 🎭 **Animaciones**: Efectos de scroll y transiciones fluidas
- 🚀 **Performance**: Optimizado para carga rápida
- ♿ **Accesibilidad**: Navegación por teclado y estructura semántica
- 🎨 **Tema Verde**: Colores acordes al concepto eco-friendly de la app

## 🔧 Personalización

### Cambiar Colores

Edita las variables CSS en `styles.css`:

```css
:root {
    --primary: #10B981;       /* Color principal */
    --secondary: #3B82F6;     /* Color secundario */
    --accent: #8B5CF6;        /* Color de acento */
}
```

### Actualizar Contenido

- Edita el texto directamente en `index.html`
- Reemplaza las imágenes en la carpeta `assets/`
- Actualiza los enlaces y URLs según necesites

### Agregar Analytics

Para trackear visitantes, agrega Google Analytics antes de `</head>` en `index.html`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=TU-ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'TU-ID');
</script>
```

## 📱 Agregar el APK

**MUY IMPORTANTE**: GitHub tiene un límite de 100MB por archivo. Si tu APK es mayor:

### Opción 1: Optimizar el APK
```bash
# Desde tu proyecto Flutter, genera un APK optimizado
flutter build apk --release --split-per-abi
# Esto genera APKs separados por arquitectura (arm64, armeabi, x86)
```

### Opción 2: Usar Git LFS (Large File Storage)
```bash
# Instala Git LFS
git lfs install

# Trackea archivos .apk
git lfs track "*.apk"

# Agrega y commitea
git add .gitattributes
git add symptoleaf.apk
git commit -m "Add APK with Git LFS"
```

### Opción 3: Hosting Externo
Si el APK es muy grande, súbelo a:
- Google Drive
- Dropbox
- Firebase Storage
- GitHub Releases

Luego actualiza el link en `index.html`:
```html
<a href="TU-LINK-DIRECTO" class="btn btn-download" download>
```

## 🌐 Dominio Personalizado (Opcional)

Para usar un dominio personalizado como `symptolea.com`:

1. Compra un dominio
2. En tu repositorio GitHub, ve a **Settings > Pages**
3. En **Custom domain**, ingresa tu dominio
4. En tu proveedor de dominio, agrega estos registros DNS:

```
Tipo    Nombre    Valor
A       @         185.199.108.153
A       @         185.199.109.153
A       @         185.199.110.153
A       @         185.199.111.153
CNAME   www       TU-USUARIO.github.io
```

## 🐛 Solución de Problemas

### La página no carga
- Verifica que el repositorio sea público
- Espera 5-10 minutos después de activar GitHub Pages
- Revisa la consola del navegador (F12) para errores

### Las imágenes no se ven
- Verifica que los archivos estén en la carpeta `assets/`
- Asegúrate de que los nombres coincidan exactamente (sensible a mayúsculas)

### El APK no descarga
- Verifica que el archivo `symptoleaf.apk` exista
- Si es muy grande, considera las opciones mencionadas arriba

## 📞 Soporte

Para problemas o sugerencias relacionadas con:
- El diseño de la página: Revisa el código HTML/CSS/JS
- La aplicación Flutter: Consulta el README principal del proyecto
- GitHub Pages: [Documentación oficial](https://docs.github.com/es/pages)

## 📄 Licencia

Este proyecto landing page está bajo licencia MIT, al igual que la aplicación SymptoLeaf.

---

**Desarrollado con ❤️ para SymptoLeaf**

🌿 Cuidando el planeta, una planta a la vez.

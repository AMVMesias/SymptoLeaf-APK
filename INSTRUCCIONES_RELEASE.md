# 📦 Cómo Subir el APK como GitHub Release

El APK pesa **307 MB**, por lo que no se puede subir directamente al repositorio. 
En su lugar, lo subiremos como **GitHub Release**.

## Pasos para Crear un Release

### Opción 1: Desde la Interfaz Web de GitHub (MÁS FÁCIL)

1. Ve a tu repositorio: https://github.com/AMVMesias/SymptoLeaf-APK

2. En el lado derecho, busca la sección **"Releases"** y haz click en **"Create a new release"**
   - O ve directamente a: https://github.com/AMVMesias/SymptoLeaf-APK/releases/new

3. **Tag version**: Escribe `v1.0.0`

4. **Release title**: Escribe `SymptoLeaf v1.0.0 - Release Inicial`

5. **Description**: Copia y pega esto:
   ```markdown
   ## 🌿 SymptoLeaf - Detección de Enfermedades en Plantas con IA

   Primera versión oficial de SymptoLeaf.

   ### ✨ Características
   - 🔍 Detección en tiempo real de 38+ enfermedades
   - 🤖 Recomendaciones con Google Gemini AI
   - 📱 Funciona 100% offline
   - 💬 Chatbot agrícola integrado

   ### 📱 Instalación
   1. Descarga el archivo `symptoleaf.apk` a continuación
   2. Habilita "Instalar desde fuentes desconocidas" en Android
   3. Abre el APK y sigue las instrucciones
   4. ¡Disfruta!

   ### 📊 Información Técnica
   - **Versión:** 1.0.0
   - **Android mínimo:** 5.0 (API 21)
   - **Tamaño:** ~307 MB
   - **Arquitecturas:** Universal (ARM, ARM64, x86)

   ### 🐛 Reportar Problemas
   Si encuentras algún bug, por favor abre un [Issue](https://github.com/AMVMesias/SymptoLeaf-APK/issues).
   ```

6. **Attach files**: 
   - Arrastra y suelta el archivo `symptoleaf.apk` desde:
   - `c:\Users\mesia\Desktop\Universidad\Moviles\3P\Apk Page\SymptoLeaf-APK\symptoleaf.apk`
   - O haz click en "Attach binaries" y selecciona el archivo

7. Click en **"Publish release"**

8. ¡Listo! Ahora copia el enlace de descarga del Release

---

### Opción 2: Desde la Línea de Comandos (GitHub CLI)

Si tienes GitHub CLI instalado:

```powershell
# Instala GitHub CLI si no lo tienes
# winget install --id GitHub.cli

# Inicia sesión
gh auth login

# Navega a tu carpeta
cd "c:\Users\mesia\Desktop\Universidad\Moviles\3P\Apk Page\SymptoLeaf-APK"

# Crea el release y sube el APK
gh release create v1.0.0 symptoleaf.apk `
  --title "SymptoLeaf v1.0.0 - Release Inicial" `
  --notes "Primera versión oficial de SymptoLeaf con detección IA de enfermedades en plantas"
```

---

## 🔗 Actualizar el Enlace de Descarga en la Web

Una vez creado el Release:

1. Ve a: https://github.com/AMVMesias/SymptoLeaf-APK/releases/tag/v1.0.0

2. Haz **click derecho** sobre el archivo `symptoleaf.apk` → **Copiar dirección del enlace**

3. El enlace será algo como:
   ```
   https://github.com/AMVMesias/SymptoLeaf-APK/releases/download/v1.0.0/symptoleaf.apk
   ```

4. Abre el archivo `index.html` y busca la línea (aproximadamente línea 396):
   ```html
   <a href="symptoleaf.apk" class="btn btn-download" download>
   ```

5. Reemplázala con:
   ```html
   <a href="https://github.com/AMVMesias/SymptoLeaf-APK/releases/download/v1.0.0/symptoleaf.apk" class="btn btn-download" download>
   ```

6. Guarda, commit y push:
   ```powershell
   git add index.html
   git commit -m "🔗 update: Link APK download to GitHub Release"
   git push
   ```

---

## ✅ Verificación

- [ ] Release creado en GitHub
- [ ] APK subido al Release
- [ ] Enlace de descarga actualizado en `index.html`
- [ ] GitHub Pages activado
- [ ] Página funcionando en: https://amvmesias.github.io/SymptoLeaf-APK/

---

## 💡 Ventajas de Usar Releases

✅ No cuenta contra el límite de tamaño del repo
✅ Los usuarios ven las versiones históricas
✅ Puedes agregar notas de cada versión
✅ Enlace de descarga permanente
✅ Estadísticas de descargas


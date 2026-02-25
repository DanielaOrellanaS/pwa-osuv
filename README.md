# 🎻 OSUV Asistencia — App Móvil

**Orquesta Sinfónica Universidad UTE Victoria**  
Control de asistencia a ensayos — PWA (Progressive Web App)

---

## ¿Qué es esto?

Una aplicación web progresiva (PWA) que funciona **como app nativa en el celular**, sin necesidad de:
- ❌ Servidor de pago
- ❌ Base de datos externa
- ❌ Play Store / App Store
- ✅ Todo se guarda en la memoria del celular (localStorage)
- ✅ Funciona sin internet (modo offline)
- ✅ Se puede instalar en el celular como app

---

## 📁 Archivos

```
osuv-asistencia/
├── index.html      ← La aplicación completa
├── manifest.json   ← Configuración PWA (instalable)
├── sw.js           ← Service Worker (offline)
└── README.md       ← Este archivo
```

---

## 🚀 Cómo usar en VS Code

### Opción 1 — Live Server (Recomendado)

1. Abre la carpeta `osuv-asistencia/` en VS Code
2. Instala la extensión **Live Server** (ritwickdey.LiveServer)
3. Clic derecho en `index.html` → **Open with Live Server**
4. Se abre en el navegador: `http://127.0.0.1:5500`

### Opción 2 — Python (si ya tienes Python instalado)

```bash
cd osuv-asistencia
python -m http.server 8080
```
Abre `http://localhost:8080` en el navegador.

---

## 📱 Cómo instalar en el celular (sin Play Store)

### Android (Chrome):
1. Abre la app en Chrome en el celular
2. Toca el menú ⋮ → **"Añadir a pantalla de inicio"**
3. ¡Listo! Aparece como app en el celular

### iPhone (Safari):
1. Abre la app en Safari en el iPhone
2. Toca el botón Compartir 📤 → **"Añadir a pantalla de inicio"**
3. ¡Listo!

---

## 📡 Cómo compartir con otros músicos / director (GRATIS)

Para que más de una persona use la app desde el celular, necesitas publicarla.  
Estas opciones son **completamente gratuitas**:

### GitHub Pages (recomendado)
1. Crea una cuenta en [github.com](https://github.com)
2. Crea un repositorio nuevo
3. Sube los 3 archivos (`index.html`, `manifest.json`, `sw.js`)
4. Ve a Settings → Pages → Source: main branch
5. Tu app estará en: `https://tu-usuario.github.io/nombre-repo/`

### Netlify Drop
1. Ve a [netlify.com/drop](https://app.netlify.com/drop)
2. Arrastra la carpeta `osuv-asistencia/` al navegador
3. ¡En 30 segundos tienes una URL pública gratis!

---

## ⚠️ Nota sobre los datos

Los datos se guardan en el **localStorage del navegador/celular**. Esto significa:
- Cada celular tiene sus propios datos
- Si desinstalan el navegador, los datos se pierden
- **Usa la función "Exportar Backup JSON"** regularmente para hacer respaldo

Para sincronizar entre múltiples dispositivos, usa la función de **Exportar/Importar JSON**.

---

## 🎼 Funcionalidades

| Pantalla | Descripción |
|----------|-------------|
| 📋 Asistencia | Toma asistencia por ensayo con 4 estados |
| 📅 Historial | Ver todos los ensayos registrados por mes |
| 📊 Estadísticas | Ranking de asistencia por músico |
| 🎻 Músicos | Agregar/eliminar músicos, exportar CSV |

### Estados de asistencia:
- ✅ **Presente**
- ⏰ **Tardanza**
- 📝 **Justificado**
- ❌ **Ausente**

### Exportación:
- **CSV** — Se abre directamente en Excel
- **JSON** — Backup completo para restaurar o transferir entre dispositivos

---

## 🛠️ Personalización

Para agregar nuevas secciones de instrumentos, edita el `<select>` con `id="new-instrument"` en `index.html`.

Para cambiar los colores, edita las variables CSS en `:root { ... }` al inicio del archivo.

---

*Desarrollado para la Orquesta Sinfónica Universidad UTE Victoria 🎻*

---

## 📊 Sincronización con Google Sheets

El director puede sincronizar toda la base de datos de asistencia directamente a un Google Sheet compartido (visible para todos con el link), sin costo adicional.

### Configuración (5 minutos, una sola vez):

1. Crea un Google Sheet en sheets.google.com y comparte el link en modo "Solo lectura" con quien quieras
2. En el Sheet ve a **Extensiones → Apps Script**
3. Borra el código existente y pega el código que aparece en la app (botón "Cómo configurar")
4. Clic en **Implementar → Nueva implementación → Aplicación web**
5. En "Quién tiene acceso" selecciona **Cualquier usuario**
6. Copia la URL generada y pégala en la sección Google Sheets de la app
7. Desde ahí puedes tocar **Sincronizar ahora** cuando quieras actualizar el Sheet

El Sheet se actualiza con una hoja por mes (Marzo 2026, Abril 2026, etc.) con el formato de asistencia.


# 📋 AsistCtrl — Control de Asistencia

Sistema dinámico de control de asistencia de alumnos, deployable en **GitHub + Vercel**.

## 🚀 Deploy en Vercel

### 1. Sube a GitHub
```bash
git init
git add .
git commit -m "AsistCtrl v1.0"
git remote add origin https://github.com/TU_USUARIO/asistctrl.git
git push -u origin main
```

### 2. Deploy en Vercel
1. Ve a [vercel.com](https://vercel.com) → **New Project**
2. Importa tu repositorio de GitHub
3. Framework: **Other** (HTML estático)
4. Root Directory: `/`
5. Click **Deploy** ✅

URL quedará tipo: `https://asistctrl.vercel.app`

---

## ☁ Activar Backup en Drive / OneDrive

### Google Drive
1. Ve a [console.cloud.google.com](https://console.cloud.google.com)
2. Crea un proyecto → habilita **Google Drive API**
3. Crea credenciales OAuth 2.0 → copia el `client_id`
4. En `index.html`, reemplaza en `backupDrive()`:
```javascript
const CLIENT_ID = 'TU_CLIENT_ID_AQUI';
const SCOPES = 'https://www.googleapis.com/auth/drive.file';
// Usar Google Identity Services (GIS)
```
5. Ver docs: https://developers.google.com/drive/api/guides/manage-uploads

### OneDrive (Microsoft)
1. Ve a [portal.azure.com](https://portal.azure.com)
2. Registra una app → copia el `client_id`
3. En `index.html`, reemplaza en `backupOneDrive()`:
```javascript
const MSAL_CONFIG = { auth: { clientId: 'TU_CLIENT_ID' } };
// Usar @azure/msal-browser
```
4. Ver docs: https://learn.microsoft.com/graph/api/driveitem-put-content

---

## 📦 Estructura del Proyecto
```
/
├── index.html        ← App completa (single-file)
├── vercel.json       ← Config de Vercel
└── README.md         ← Este archivo
```

## ✨ Características
- ✅ Hasta **35 alumnos por curso**
- ✅ Múltiples cursos (A, B, C, + agregar más)
- ✅ Navegación por meses
- ✅ 4 estados: Falta / Tardanza / Tardanza Justif. / Puntual
- ✅ Estadísticas automáticas por alumno y por día
- ✅ Exportar a **CSV**
- ✅ Backup **local (.json)** / Drive / OneDrive
- ✅ Restaurar desde backup
- ✅ Datos guardados en **localStorage** del navegador
- ✅ 100% offline-capable, sin backend

## 🔧 Tecnologías
- HTML5 + CSS3 + Vanilla JS
- Sin dependencias externas
- Compatible con todos los navegadores modernos

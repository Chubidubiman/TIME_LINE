# 📅 Timeline Viewer

Visualizador interactivo de líneas de tiempo generadas desde archivos Excel. Permite cargar datos, visualizarlos en formato vertical u horizontal, personalizar etiquetas, cambiar el tema visual y exportar la línea de tiempo como imagen.

🔗 **Repositorio:** [github.com/Chubidubiman/TIME_LINE](https://github.com/Chubidubiman/TIME_LINE)

---

## ✨ Características

- 📂 **Carga de archivos Excel** — Soporta `.xlsx` y `.xls` mediante drag & drop o selector de archivo
- 🎨 **Código de colores automático** — Cada responsable recibe un color único y consistente
- 🔀 **Dos modos de vista** — Alterna entre vista **Vertical** y **Horizontal** con un clic
- ✏️ **Títulos editables** — El título principal y la etiqueta de la leyenda son editables directamente en pantalla
- 🖼️ **Exportación a imagen** — Descarga la línea de tiempo completa como `.png` respetando el tema y título personalizado
- 📋 **Plantilla de ejemplo** — Descarga un Excel de muestra con el formato correcto
- 🌙☀️ **Tema oscuro / claro** — Switch para alternar entre temas; la preferencia se guarda automáticamente

---

## 🚀 Uso

### Opción 1 — Abrir directamente en el navegador

```bash
# Simplemente abre el archivo en tu navegador
start index.html        # Windows
open index.html         # macOS
xdg-open index.html     # Linux
```

### Opción 2 — Servidor local (recomendado)

```bash
# Con Node.js instalado:
npx serve .

# O con Python:
python -m http.server 8080
```

Luego abre `http://localhost:8080` en tu navegador.

---

## 📊 Formato del archivo Excel

El archivo debe tener **exactamente estas tres columnas** en la primera hoja, con encabezados en la fila 1:

| Columna A | Columna B    | Columna C    |
|-----------|--------------|--------------|
| Fecha     | Descripcion  | Responsable  |
| 15/01/2025 | Inicio del proyecto | Juan Perez |
| 01/02/2025 | Revisión de diseño  | Maria Lopez |

### Formatos de fecha aceptados

| Formato        | Ejemplo      |
|----------------|--------------|
| `DD/MM/AAAA`   | 15/01/2025   |
| `DD-MM-AAAA`   | 15-01-2025   |
| `AAAA-MM-DD`   | 2025-01-15   |
| Fecha de Excel | (nativo)     |

> 💡 Puedes descargar una plantilla de ejemplo desde el botón **"Descargar plantilla de ejemplo"** dentro de la aplicación.

---

## 🖥️ Interfaz

### Pantalla de carga
```
┌────────────────────────────────────────┐        [☀️ Claro] ← esquina fija
│           Timeline Viewer              │
│   Visualiza lineas de tiempo...        │
│                                        │
│   ┌──────────────────────────────┐     │
│   │  📅  Arrastra tu Excel aquí  │     │
│   └──────────────────────────────┘     │
│                                        │
│   [ Descargar plantilla de ejemplo ]   │
│                                        │
│   🐙 github.com/Chubidubiman/TIME_LINE │
└────────────────────────────────────────┘
```

### Pantalla de línea de tiempo
```
┌──────────────────────────────────────────────────────────┐   [☀️ Claro]
│  Linea de Tiempo*  [Vertical][Horizontal] [Exportar] [←] │  ← * Editable
├──────────────────────────────────────────────────────────┤
│  Responsables*:  ● Juan  ● Maria  ● Carlos               │  ← * Editable
├──────────────────────────────────────────────────────────┤
│                                                          │
│   [Evento 1]          ●                                  │
│                       │                                  │
│                       ●          [Evento 2]              │
│                       │                                  │
│   [Evento 3]          ●                                  │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

### Títulos editables
Haz clic sobre **"Linea de Tiempo"** o **"Responsables:"** para editarlos. Ambos cambios se reflejan automáticamente en la imagen exportada.

### Cambio de tema
El botón **☀️ Claro / 🌙 Oscuro** en la esquina superior derecha alterna entre temas. La preferencia se guarda en `localStorage` y se restaura al recargar la página. La imagen exportada también respeta el tema activo al momento de exportar.

---

## 📁 Estructura del proyecto

```
TIME_LINE/
├── index.html          # Aplicación completa (HTML + CSS + JS en un solo archivo)
├── README.md           # Este archivo
├── .gitignore          # Archivos ignorados por Git
└── .claude/
    └── launch.json     # Configuración del servidor de desarrollo
```

---

## 🛠️ Tecnologías utilizadas

| Librería | Versión | Uso |
|----------|---------|-----|
| [SheetJS (xlsx)](https://sheetjs.com/) | 0.18.5 | Lectura de archivos Excel |
| [html2canvas](https://html2canvas.hertzen.com/) | 1.4.1 | Exportación a imagen PNG |

Ambas librerías se cargan desde CDN — no se requiere instalación.

---

## 📦 Sin dependencias de build

Este proyecto es un **único archivo HTML estático**. No necesita:
- `npm install`
- Proceso de compilación
- Framework o bundler

---

## 📄 Licencia

MIT — libre para uso personal y comercial.

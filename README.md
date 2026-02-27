# 📅 Timeline Viewer

Visualizador interactivo de líneas de tiempo generadas desde archivos Excel. Permite cargar datos, visualizarlos en formato vertical u horizontal, personalizar etiquetas y exportar la línea de tiempo como imagen.

---

## ✨ Características

- 📂 **Carga de archivos Excel** — Soporta `.xlsx` y `.xls` mediante drag & drop o selector de archivo
- 🎨 **Código de colores automático** — Cada responsable recibe un color único y consistente
- 🔀 **Dos modos de vista** — Alterna entre vista **Vertical** y **Horizontal** con un clic
- ✏️ **Títulos editables** — El título principal y la etiqueta de la leyenda son editables directamente en pantalla
- 🖼️ **Exportación a imagen** — Descarga la línea de tiempo completa como archivo `.png` con el título personalizado
- 📋 **Plantilla de ejemplo** — Descarga un Excel de muestra con el formato correcto
- 🌙 **Tema oscuro** — Interfaz moderna con fondo oscuro y colores degradados

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

```
┌─────────────────────────────────────────────────────────┐
│  Linea de Tiempo*    [Vertical][Horizontal] [Exportar]  │  ← * Editable
├─────────────────────────────────────────────────────────┤
│  Responsables*:  ● Juan  ● Maria  ● Carlos              │  ← * Editable
├─────────────────────────────────────────────────────────┤
│                                                         │
│   [Evento 1]          ●                                 │
│                       │                                 │
│                       ●          [Evento 2]             │
│                       │                                 │
│   [Evento 3]          ●                                 │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Títulos editables
Haz clic sobre **"Linea de Tiempo"** o **"Responsables:"** para editarlos. El cambio se refleja automáticamente en la imagen exportada.

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

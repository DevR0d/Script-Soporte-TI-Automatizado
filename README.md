# 🛠️ Kit de Soporte TI Automatizado

Este proyecto proporciona un **script integral de mantenimiento y soporte TI** en PowerShell, acompañado de un archivo `.bat` para programar su ejecución automática mediante el **Programador de tareas de Windows**.  
Está diseñado para técnicos de soporte que necesiten una herramienta **profesional, amigable y auditable**.

---

## 📌 Funcionalidades principales

- **Menú interactivo** para decidir qué acciones ejecutar.
- **Limpieza y optimización**:
  - Archivos temporales (`%TEMP%`, `C:\Windows\Temp`)
  - Caché de navegadores (Edge, Chrome, Firefox)
  - Prefetch
  - Descargas de Windows Update
  - Papelera de reciclaje
  - Optimización/desfragmentación de disco
- **Funciones críticas de soporte TI**:
  - Reparación de archivos del sistema con **SFC** (`sfc /scannow`)
  - Corrección de errores de disco con **CHKDSK** (`chkdsk /f`)
  - Reinicio de servicios críticos (Windows Update, BITS)
- **Logging dual**:
  - `Mantenimiento_Log.txt` → registro plano para auditoría rápida
  - `Mantenimiento_Log.html` → reporte visual con tabla y formato legible en navegador

---

## 📂 Archivos del proyecto

- `mantenimiento_profesional.ps1` → Script PowerShell con menú interactivo y funciones de soporte.
- `configurar_mantenimiento.bat` → Asistente para crear la tarea programada en Windows.

---

## 🚀 Instalación y uso

1. **Descargar los archivos** y colocarlos en:
   - `mantenimiento_profesional.ps1` → Carpeta *Documentos* del usuario.
   - `configurar_mantenimiento.bat` → Carpeta a elección (ej. Escritorio).
2. **Ejecutar el `.bat` como administrador**:
   - Preguntará:
     - Frecuencia (diario, semanal, mensual)
     - Hora exacta (formato 24h, ej. `08:00`)
     - Cuenta de ejecución (usuario actual o SYSTEM)
   - Creará la tarea en el **Programador de tareas**.
3. **Automatización**:
   - A la hora configurada, se abrirá el menú interactivo del script.
   - El técnico podrá elegir qué rutinas ejecutar o correr todas en un solo paso.
4. **Logs y reportes**:
   - Se generan automáticamente en la carpeta *Documentos*:
     - `Mantenimiento_Log.txt`
     - `Mantenimiento_Log.html`

---

## 📊 Ejemplo de reporte HTML

```html
<h1>Reporte de Mantenimiento - 2026-10-09</h1>
<table>
<tr><th>Fecha/Hora</th><th>Acción</th><th>Detalle</th></tr>
<tr><td>2026-10-09 08:00:01</td><td>Limpieza</td><td>Archivos temporales</td></tr>
<tr><td>2026-10-09 08:05:12</td><td>Optimización</td><td>Desfragmentación disco C</td></tr>
<tr><td>2026-10-09 08:15:30</td><td>Reparación</td><td>SFC /scannow ejecutado</td></tr>
</table>

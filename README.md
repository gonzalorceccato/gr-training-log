# GR Training Log

App móvil (PWA) para registrar entrenamientos y antropometría de Gonzalo Rodríguez.
Corre 100% en el navegador, sin backend: los datos se guardan en `localStorage` del dispositivo.

## Qué hace

- **Rutina**: muestra la rutina fuerza-potencia actual (Lun/Mié/Vie). Editable en texto libre (JSON) desde la app.
- **Registrar**: cargar series, reps, kg y RPE reales de cada sesión.
- **Antropometría**: cargar peso, cintura, los 6 pliegues y los perímetros de cada medición. Viene precargada con el historial 01/2025–09/2026 del proyecto.
- **Historial**: ver y borrar registros pasados.
- **Exportar**: genera un JSON con todo (rutina + entrenamientos + antropometría) para copiar/descargar y pegarlo en el chat de Claude y pedir un informe o una nueva progresión. También permite importar ese JSON de vuelta (para restaurar en otro dispositivo).

## Cómo publicarla en GitHub Pages

1. Creá un repositorio nuevo en GitHub (puede ser privado), por ejemplo `gr-training-log`.
2. Subí estos archivos (`index.html`, `manifest.json`, `sw.js`, `icon.png`) a la raíz del repo.
3. En el repo: **Settings → Pages → Source: main branch, carpeta /(root)** → Save.
4. GitHub te da una URL tipo `https://<tu-usuario>.github.io/gr-training-log/`. Esa es la app.
5. Abrí esa URL desde el navegador del teléfono → menú → **"Agregar a pantalla de inicio"** (Android/Chrome) o **"Compartir → Agregar a inicio"** (iPhone/Safari). Queda como un ícono más, se abre a pantalla completa.

## Importante sobre los datos

Los datos viven **solo en el navegador de ese teléfono** (localStorage). Si borrás datos del navegador, cambiás de teléfono, o usás el modo privado, se pierden. Por eso:

- Usá **Exportar → Descargar .json** cada tanto como respaldo.
- Para pedirme un informe o una progresión nueva en el chat, generá el export y pegame el JSON (o subime el archivo).
- Si algún día querés que los datos se sincronicen solos entre dispositivos y yo pueda leerlos sin que me pegues nada, avisame — existe una versión con base de datos compartida, pero implica otra arquitectura (Claude Artifact en vez de GitHub Pages puro).

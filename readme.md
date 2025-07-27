# 🎧 Music Unrar

Aplicación de escritorio para **descomprimir archivos **``** y **``** de música** y organizar carpetas con nombres limpios de Artista – Álbum – Año.

---

## 📦 ¿Qué es?

`MusicUnrar.exe` es un ejecutable Windows generado con PyInstaller que incorpora:

- **7-Zip** embebido (si proporcionas `7z.dll`) o usa tu propia instalación en `C:\Program Files\7-Zip\7z.exe`.
- Lógica de **limpieza de nombres** y **consulta a MusicBrainz** para extraer metadata (artista, álbum, año).
- Manejo de errores por archivo, sin consola visible.

---

## ✅ Características principales

- 🔹 Soporta `.rar` y `.zip` sin instalar Python ni librerías externas.
- 🔹 Extracción silenciosa sin mostrar ventana de consola.
- 🔹 Limpia nombres «contaminados» (prefijos numéricos, URLs, créditos, etiquetas de página…).
- 🔹 Opcionalmente consulta y valida metadata en MusicBrainz.
- 🔹 Renombra automáticamente a `Artista - Álbum - Año`.
- 🔹 Borra el archivo comprimido tras la extracción.
- 🔹 Genera listados finales:
  - Archivos que **fallaron** al procesar.
  - Archivos cuyo **nombre no cambió** tras limpieza.

---

## 📥 Descarga

Descarga el ZIP que contiene:

- `MusicUnrar.exe`: ejecutable principal.
- (Opcional) `7z.dll` o `7za.dll` si no tienes 7-Zip en tu PATH.
- Carpeta `1001/` con tus archivos `.rar` o `.zip`.

**Enlace de descarga:** [Descargar MusicUnrar.zip](sandbox:/mnt/data/MusicUnrar.zip)

---

## 🚀 Uso

1. **Extrae** el contenido del ZIP en una carpeta.
2. **Coloca** tus archivos `.rar`/`.zip` dentro de la subcarpeta `1001/` que genera la descarga.
3. Haz **doble clic** en `MusicUnrar.exe`.
4. La aplicación procesará todos los ficheros, creando la carpeta `descomprimidos/` con subcarpetas:
   ```
   descomprimidos/
   ├── Artista - Álbum - Año/
   │   ├── 01 Título.mp3
   │   └── ...
   ```
5. Al finalizar verás un informe emergente (o un log en pantalla) con:
   - Archivos que **fallaron**.
   - Archivos **sin cambio de nombre**.

---

## ⚙️ Requisitos previos

- Windows 10/11.
- **(Opcional)** 7-Zip instalado en `C:\Program Files\7-Zip\7z.exe`, si no incluyes `7z.dll`.

---

## 📝 Notas

- Si no deseas consultar MusicBrainz, elimina o renombra `config.ini` (si se incluye) con la opción `use_musicbrainz=false`.
- Para personalizar la ruta del extractor, crea un archivo `config.ini` junto al `.exe` con:
  ```ini
  [extractor]
  path = C:\Program Files\7-Zip\7z.exe
  ```

---

© 2025 MusicUnrarBot


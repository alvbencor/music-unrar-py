# 🎧 music-unrar-py

Script en Python para **descomprimir archivos `.rar` y `.zip` de música**, obtener automáticamente **el nombre correcto del artista, álbum y año** desde la base de datos de [MusicBrainz](https://musicbrainz.org/), y organizar las carpetas limpiamente.

---

## ✅ Características

- ✅ Soporte para `.rar` y `.zip`
- ✅ Extracción con 7-Zip (`7z.exe`) usando el modo de preservación de estructura
- ✅ Limpieza avanzada de nombres contaminados (por ejemplo: `by Corbacho`, `flacworld.com`, `Pg. 123`, etc.)
- ✅ Consulta automática de metadatos en **MusicBrainz**
- ✅ Verificación del número de pistas para asegurar precisión
- ✅ Renombrado automático del directorio de salida como:  
  ```
  Artista - Álbum - Año
  ```
- ✅ Eliminación del archivo comprimido original después de la extracción
- ✅ Carpetas organizadas en una estructura persistente bajo `descomprimidos/`

---

## 📦 Requisitos

- **Python 3.6+**
- **7-Zip instalado** en:
  ```
  C:\Program Files\7-Zip\7z.exe
  ```
  Si está en otro sitio, edita la variable `EXTRACTOR` en el script.

- **Librería requests**:
  ```bash
  pip install requests
  ```

---

## 🧑‍💻 Uso

1. Coloca este script y los archivos `.rar` o `.zip` en la misma carpeta.
2. Abre una terminal en esa carpeta.
3. Ejecuta:
   ```bash
   python full_music_unarchiver.py
   ```

---

## 📁 Estructura de salida esperada

```
descomprimidos/
├── Paco de Lucía - Siroco - 1987/
│   ├── 01 La Cañada.mp3
│   └── ...
├── Enrique Morente - Despegando - 1977/
│   ├── ...
```

---

## 🧹 ¿Qué limpia el script?

Ejemplos de cosas que limpia automáticamente del nombre del archivo:

- Prefijos numéricos: `01 -`, `123.`
- Guiones bajos y puntos como separadores
- Webs embebidas: `flacworld.com`, `musicagratis.net`, etc.
- Créditos tipo `by Corbacho`, `[by alguien]`, `(por alguien)`
- Etiquetas de página: `- Pg. 45`
- Caracteres ilegales de Windows (`:`, `*`, `?`, etc.)

---

## ⚠ Limitaciones conocidas

- Si MusicBrainz no encuentra coincidencia o el número de pistas no coincide, se usará el nombre limpio como fallback.
- El script no descarga portadas ni letras (por ahora).

---

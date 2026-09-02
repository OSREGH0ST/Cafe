# Café Terraza Quetzal — Sitio Web

Sitio estático de una sola página (single-page) para Café Terraza Quetzal, Aguascalientes. HTML/CSS/JS puro, sin frameworks ni build step.

## Estructura del proyecto

```
quetzal-site/
├── index.html    # Marcado y contenido (es-MX)
├── styles.css    # Estilos (paleta terracota/crema/verde, tipografía Playfair Display + Inter)
└── script.js     # Año dinámico en footer, toggle de menú móvil
```

## Dependencias externas (runtime)

- **Google Fonts** (`fonts.googleapis.com`) — Playfair Display + Inter
- **Unsplash** (`images.unsplash.com`) — imágenes placeholder; reemplazar por fotos propias en `/assets/` antes de producción

No hay dependencias de build (npm, bundlers, etc.). El sitio corre directo desde el navegador.

## Vista previa local

```bash
# Opción 1: abrir directo
xdg-open index.html          # Linux
start index.html             # Windows (cmd)
open index.html              # macOS

# Opción 2: servidor local (recomendado, evita problemas de rutas relativas)
python3 -m http.server 8000
# → http://localhost:8000
```

---

## Git — inicializar y subir a GitHub

Asumo que ya tienes un repositorio vacío creado en GitHub (`ejemplo: github.com/osregh0st/quetzal-site`). Ajusta la URL del remoto.

```bash
cd quetzal-site
git init
git add .
git commit -m "Initial commit: sitio Café Terraza Quetzal"
git branch -M main
git remote add origin https://github.com/osregh0st/quetzal-site.git
git push -u origin main
```

Cambios subsecuentes:

```bash
git add .
git commit -m "descripción del cambio"
git push
```

## Clonar el repo (git clone)

```bash
git clone https://github.com/osregh0st/quetzal-site.git
cd quetzal-site
```

## Descargar sin git, vía curl

Si no quieres instalar/usar git, puedes bajar el repo como tarball directamente:

```bash
# Rama main como .tar.gz (usa codeload.github.com)
curl -L -o quetzal-site.tar.gz https://codeload.github.com/osregh0st/quetzal-site/tar.gz/refs/heads/main
tar -xzf quetzal-site.tar.gz

# Alternativa: .zip vía GitHub API
curl -L -o quetzal-site.zip https://api.github.com/repos/osregh0st/quetzal-site/zipball/main
```

> **Nota Windows/PowerShell:** `curl` en PowerShell es un alias de `Invoke-WebRequest`, que no soporta las mismas flags (`-L`, `-o`) igual que el curl real. Usa `curl.exe` explícitamente para forzar el binario real:
> ```powershell
> curl.exe -L -o quetzal-site.tar.gz https://codeload.github.com/osregh0st/quetzal-site/tar.gz/refs/heads/main
> ```

## Deploy sugerido

- **GitHub Pages:** Settings → Pages → Deploy from branch (`main`, `/root`) — cero configuración, sirve `index.html` directo.
- **Netlify / Vercel:** drag-and-drop la carpeta o conecta el repo; sin build command necesario.

## Pendientes antes de producción

- [ ] Reemplazar imágenes de Unsplash por fotografía propia del local
- [ ] Confirmar horario/dirección contra Google Maps (última verificación: Mar–Dom 4:00–11:00 p.m., cerrado lunes)
- [ ] Agregar favicon real (actualmente emoji SVG inline)
- [ ] Minificar CSS/JS si el hosting no lo hace automáticamente

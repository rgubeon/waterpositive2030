# Water Positive 2030 — Suntory Beverage & Food Iberia

Sitio estático de una sola página. No necesita build ni dependencias: se sirve tal cual.

## Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub (público o privado con Pages habilitado).
2. Sube el contenido de esta carpeta **al raíz del repositorio** (no dentro de una subcarpeta):
   ```
   git init
   git add .
   git commit -m "Water Positive 2030"
   git branch -M main
   git remote add origin https://github.com/<usuario>/<repo>.git
   git push -u origin main
   ```
3. En GitHub: **Settings → Pages → Build and deployment**
   - Source: *Deploy from a branch*
   - Branch: `main` / carpeta `/ (root)`
4. En 1-2 minutos la web estará en `https://<usuario>.github.io/<repo>/`.

## Estructura

```
index.html      Página completa (marcado + lógica)
support.js      Runtime necesario para index.html
assets/         Imágenes, logos, vídeos y pósters
docs/           PDFs de "Documentos de interés"
.nojekyll       Evita que Jekyll procese los archivos
```

## Notas

- Todas las rutas son relativas, así que funciona igual en la raíz del dominio o en un subdirectorio (`/<repo>/`).
- Tipografía Roboto desde Google Fonts (requiere conexión). Para uso 100% offline, descarga la fuente y sustituye el `<link>` de `index.html` por un `@font-face` local.
- Los vídeos son los archivos más pesados del repositorio; GitHub recomienda no superar 100 MB por archivo (ninguno lo hace) y 1 GB por repositorio.

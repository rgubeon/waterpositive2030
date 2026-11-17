# Water Positive 2030 — Suntory Beverage & Food Iberia

Microsite estático de una sola página (proyecto BEESCH025926). No necesita build: se sirve tal cual.

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub.
2. Sube el contenido de este zip **a la raíz del repositorio** (no dentro de una subcarpeta):
   ```
   git init
   git add .
   git commit -m "Water Positive 2030"
   git branch -M main
   git remote add origin https://github.com/<usuario>/<repo>.git
   git push -u origin main
   ```
3. En GitHub: **Settings → Pages → Build and deployment** → Source: *Deploy from a branch* → Branch: `main` / `/ (root)`.
4. En 1-2 minutos estará en `https://<usuario>.github.io/<repo>/`.

## Estructura

```
index.html   Página completa (marcado + lógica)
support.js   Runtime que interpreta index.html
assets/      Imágenes, logos, vídeos, pósters y portadas de noticias
docs/        PDFs de "Documentos de interés" y comunicado AWS
.nojekyll    Evita que GitHub Pages procese los archivos con Jekyll
```

## Dependencias externas (requieren conexión)

- `support.js` carga React 18.3.1 y Babel standalone 7.29.0 desde `unpkg.com`.
- La tipografía Roboto se carga desde Google Fonts.

Si unpkg o Google Fonts no responden, la página no se pinta o se ve con otra tipografía.
Para un despliegue sin dependencias externas, descarga esos ficheros y sirve copias locales.

## Pendiente del cliente

Estos documentos aparecen en la web como **«Próximamente»** hasta recibir el PDF:

| Documento en la web | Archivo esperado |
|---|---|
| Biodiversidad y microbioma del suelo mediante ADN ambiental – Agricultura regenerativa | `Summary_report_on_SGS_DNA_sampling_002.pdf` |
| Cálculo del ahorro de agua con cubiertas vegetales | `Ahorro_Cubiertas_Vegetales.pdf` |
| Taller sobre cubiertas vegetales con ASAJA Toledo | `Workshop_ASAJA_Toledo_23-03-2026.pdf` |
| Validación del beneficio hídrico de la restauración del río Tajuña | `2026_VWBA_Sign-Off_Report_-Spain-_Mediodes_TAJUÑA_SUNTORY.pdf` |

Para activarlos: copia el PDF en `docs/` con un nombre sin espacios ni acentos y, en `index.html`,
busca el título del documento en `static DOCUMENTOS` y cambia `archivo: null` por `archivo: 'docs/<nombre>.pdf'`.

## Notas

- Todas las rutas son relativas: funciona en la raíz de un dominio o en un subdirectorio (`/<repo>/`).
- Ningún archivo supera los 100 MB que permite GitHub (el mayor ronda los 21 MB).

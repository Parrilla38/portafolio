# Portafolio · @parrilla_opos

Web personal de Jesús: IA, oposiciones, apps y herramientas para opositores.

Sitio estático (HTML + CSS + JS, sin build). Vercel lo sirve tal cual: framework «Other», sin comando de build, carpeta raíz `/`.
`vercel.json` activa URLs limpias (`/aviso-legal`, `/privacidad`), la página 404 y cabeceras de seguridad y caché.

## Poner tu dominio (cuando lo compres)

1. **Vercel** → proyecto → *Settings* → *Domains* → *Add* → escribe tu dominio (por ejemplo `midominio.es`) y también `www.midominio.es`.
2. **En tu registrador** (donde compraste el dominio) crea los registros DNS que te enseñe Vercel en esa pantalla (normalmente un registro `A` para el dominio y un `CNAME` para `www`). Vercel pone el candado HTTPS solo.
3. **Avisa a la web de su dirección** (canonical, imagen para compartir, sitemap), desde la carpeta del portafolio en el PC:

   ```
   python scripts/preparar_despliegue.py https://midominio.es
   ```

   y sube el cambio:

   ```
   cd despliegue/parrilla-opos
   git add --all index.html aviso-legal.html privacidad.html 404.html robots.txt sitemap.xml
   git commit -m "Dominio propio"
   git push
   ```

4. Opcional: da de alta el sitemap (`https://midominio.es/sitemap.xml`) en Google Search Console.

## Qué hay aquí

- `index.html`: la web. `aviso-legal.html`, `privacidad.html`, `404.html` y `legal.css`.
- `assets/`: imágenes WebP, tráiler comprimido y fuentes propias (Bricolage Grotesque y Schibsted Grotesk, licencia SIL OFL).
- `og.png`: imagen al compartir el enlace. `favicon.svg`, `favicon-32.png`, `apple-touch-icon.png`.
- `robots.txt` y `sitemap.xml`: los genera el script con el dominio.

Sin cookies, sin analítica y sin llamadas a terceros al cargar.

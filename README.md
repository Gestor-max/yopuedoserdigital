# Yo Puedo Ser Digital

Landing page estática para [yopuedoserdigital.com](https://yopuedoserdigital.com) — mentoría para conseguir empleo remoto en dólares desde LATAM.

## Estructura

```
├── index.html              # Página principal
├── 404.html                # Página de error
├── assets/
│   ├── css/
│   │   ├── styles.css      # Estilos principales
│   │   └── cta-kit.css     # Kit de CTAs (botones de conversión)
│   └── js/
│       └── main.js         # Header sticky, nav móvil, animaciones
└── .github/workflows/
    └── deploy.yml          # Deploy automático a Cloudflare Pages
```

## Desarrollo local

Es un sitio 100% estático. Sirve la carpeta con cualquier servidor:

```bash
npx serve .
# o
python -m http.server 8080
```

## Deploy

- **Automático:** cada push a `main` despliega a Cloudflare Pages vía GitHub Actions (usa el secret `CLOUDFLARE_API_TOKEN` y la variable `CLOUDFLARE_ACCOUNT_ID`).
- **Manual:** `npx wrangler pages deploy . --project-name=yopuedoserdigital`

## Personalizar

- **Colores y fuentes:** variables CSS al inicio de `assets/css/styles.css`.
- **CTA de WhatsApp:** busca `wa.me/000000000000` en `index.html` y reemplázalo por el número real.
- **Email de contacto:** reemplaza `hola@yopuedoserdigital.com` en `index.html`.

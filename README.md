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

- **Manual:** `npx wrangler pages deploy . --project-name=yopuedoserdigital`
- **Dominios:** `yopuedoserdigital.com` y `www.yopuedoserdigital.com` (CNAME → `yopuedoserdigital.pages.dev`, proxied) configurados como custom domains del proyecto Pages.
- **DNS:** la zona vive en Cloudflare. El registro MX/SPF del hosting de correo se conservó intacto; solo los registros web (A/AAAA apex/www) apuntan a Pages.
- **Auto-deploy (opcional):** conectar el repo en Pages → Settings → Builds & deployments → Connect to Git, o vía GitHub Actions (secret `CLOUDFLARE_API_TOKEN` + variable `CLOUDFLARE_ACCOUNT_ID`).

## Personalizar

- **Colores y fuentes:** variables CSS al inicio de `assets/css/styles.css`.
- **CTA de WhatsApp:** busca `wa.me/000000000000` en `index.html` y reemplázalo por el número real.
- **Email de contacto:** reemplaza `hola@yopuedoserdigital.com` en `index.html`.

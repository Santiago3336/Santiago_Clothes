# Notas de seguridad y cumplimiento

Notas internas, no enlazadas desde el sitio. Última revisión: 18 de octubre de 2026.

## Datos personales

- **La página no recoge ni envía datos personales.** No usa `fetch`, `XMLHttpRequest`, `sendBeacon` ni WebSocket. No tiene formularios con `action`. No usa cookies, `localStorage` ni `sessionStorage`, y no tiene analítica.
- El visitante no escribe ningún dato. La talla elegida solo arma el texto del pedido que se muestra en pantalla, y nunca va a una URL.
- Los botones de la marca ficticia (WhatsApp, «Cómo llegar», Instagram, TikTok) **no abren nada externo**: muestran un diálogo que explica qué haría la página real.
- Los únicos enlaces reales son los de Santiago: WhatsApp, GitHub, Instagram y el correo de trabajo `contacto.santiagosierra@gmail.com`, que salen de `CONTACTO`.

## Terceros

- El único tercero es **Google Fonts** (`fonts.googleapis.com` y `fonts.gstatic.com`), que recibe la IP del visitante.
- El mapa que se ve al abrir la página es un **SVG ilustrativo**. Antes del 6 de octubre de 2026 había un iframe de Google Maps que cargaba `maps.googleapis.com`, `maps.gstatic.com`, `places.googleapis.com` y `www.google.com` sin que el visitante lo pidiera.
- Desde el 18 de octubre de 2026, el botón «Ver el mapa real de Bucaramanga» crea el iframe de Google Maps **solo al hacer clic** (vista general de la ciudad, sin ningún local). Hasta ese clic Google no recibe nada. Después del clic Google recibe la IP del visitante y puede usar cookies, como en cualquier mapa incrustado. Como lo pide el visitante y el texto de al lado avisa que se carga desde Google, no hace falta un banner de cookies. Si algún día el mapa se carga solo, sí haría falta aviso y consentimiento (Ley 1581).

## Hosting

- GitHub Pages publicado desde `main`. En `*.github.io` el HTTPS es obligatorio.
- GitHub Pages no permite cabeceras HTTP propias. Para sitios de clientes conviene usar Netlify o Cloudflare Pages con `_headers`.
- Este archivo se excluye del sitio publicado en `_config.yml`, pero sigue visible en el repositorio público. No escribir aquí nada privado.

## Pendientes

- El historial de git conserva versiones anteriores con un correo personal en `CONTACTO`. Ya no se publica en el sitio. Reescribir el historial es destructivo, así que solo se haría si Santiago lo pide.

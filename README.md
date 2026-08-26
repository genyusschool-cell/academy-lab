# Replica Academy + Lab — Genyus School

Página "Academy + Lab" replicada como Design Component autónomo, sin header ni footer, lista para incrustar en la web de Genyus.

## Contenido

- `Academy Lab.dc.html` — la página completa (Design Component).
- `support.js` — runtime que necesita el `.dc.html`.
- `image-slot.js` — componente de imágenes arrastrables.
- `_ds/` — Genyus School Design System (tokens, estilos, bundle, fuentes).
- `uploads/` — fotos usadas en la página.

## Uso

Abre `Academy Lab.dc.html` en un navegador, o incrústalo en un iframe. Todas las rutas son relativas, así que mantén la estructura de carpetas tal cual.

### Notas

- Hay un margen blanco superior de 96px porque la web destino tiene un head fijo.
- Los dos formularios envían a Slack vía webhooks (inscripción y contacto).
- Los botones "Reservar plaza" hacen scroll al formulario del final.

# Genyus Academy + Lab — versión para Framer

Página **estática autónoma**: un solo `index.html` sin React, sin CDNs y sin runtime.
Solo depende de dos carpetas locales: `fonts/` y `uploads/`.

## Subir a GitHub / Vercel

Sube el contenido de esta carpeta a la raíz del repo:

```
index.html
fonts/
uploads/
```

Vercel lo sirve como sitio estático sin configuración.

## Insertar en Framer

1. Framer → **Embed** → *URL* → pega la URL de Vercel.
2. Ancho: **100%** (Fill). Alto: **Fill** o un valor fijo generoso.
3. Si el embed queda con altura fija, la página hace scroll dentro de él; eso es
   inevitable en cualquier iframe salvo que el contenedor escuche la altura.
   La página ya envía su altura al contenedor (`postMessage`), así que si algún día
   puedes añadir código en Framer → Settings → Custom Code → *End of `<body>`*,
   con esto el embed crece solo y desaparece el scroll interno:

```html
<script>
window.addEventListener("message", function (e) {
  var d = e.data;
  if (!d || d.genyus !== "height") return;
  document.querySelectorAll("iframe").forEach(function (f) {
    if (f.contentWindow === e.source) {
      f.style.height = d.height + "px";
      if (f.parentElement) f.parentElement.style.height = d.height + "px";
    }
  });
});
</script>
```

## Qué cambia respecto a la versión anterior

- **Sin runtime ni React**: el HTML es el contenido final, así que no hay
  contenedores con altura forzada ni doble scroll.
- **Responsive real** con `clamp()` y breakpoints en 1000px, 720px y 420px:
  se adapta al ancho del iframe, no al del navegador.
- **Iconos SVG en línea** (sin la librería externa): no se rompen al cambiar de programa.
- **Anclas por JavaScript**: los botones "Reservar plaza" localizan el contenedor que
  hace scroll (sea el documento o el iframe) y bajan al formulario.
- **Enlace directo**: `tu-url.vercel.app/#inscripcion` abre ya en el formulario.

## Formularios

Sin cambios: la inscripción envía a Slack y a la hoja de cálculo (Apps Script);
"Más info" envía a su canal de Slack. Falta la URL de la Web App del Excel B
para el formulario de "Más info".

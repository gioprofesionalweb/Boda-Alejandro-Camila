# Invitación digital · Alejandro & Camila

## Qué falta editar antes de publicar

Abre `index.html` con cualquier editor de texto (Bloc de notas, VS Code, o directo en GitHub con el ícono de lápiz) y busca el bloque `const CONFIG = { ... }` cerca del final del archivo. Ahí están marcados con 🔧 todos los datos que aún no me diste:

- [ ] `ceremony` → hora, lugar y dirección de la ceremonia
- [ ] `reception` → hora, lugar y dirección de la recepción
- [ ] `party` → hora, lugar y dirección de la fiesta
- [ ] `dressCode` → título (ej. "Formal") y nota de vestimenta
- [ ] `rsvp.whatsappNumber` → tu número con código de país, solo dígitos (ej. `5215500000000`)
- [ ] `rsvp.deadline` → fecha límite para confirmar
- [ ] `giftTable.message` y `giftTable.options` → agrega tus opciones así:
  ```js
  options: [
    { label: "Mesa de regalos Liverpool", url: "https://..." },
    { label: "Transferencia", url: "#" }
  ]
  ```

Mientras estos campos digan "🔧 EDITAR", se van a mostrar así en la tarjeta — es intencional, para que no publiques una dirección o número equivocado por accidente.

## Reusar este molde para otro evento (boda, XV años, etc.)

Todo lo que cambia entre un proyecto y otro vive en dos lugares:

1. **Paleta de colores** — arriba del todo en `<style>`, dentro de `:root{ ... }`. Cambia los valores hexadecimales (`--cream`, `--sage-deep`, `--gold`, etc.) y todo el diseño se actualiza solo.
2. **Contenido** — el objeto `CONFIG` al final del archivo (nombres, fecha, itinerario, vestimenta, RSVP, regalos).

No necesitas tocar el resto del código HTML/CSS salvo que quieras cambiar textos fijos como "Nos casamos" o el título de alguna sección.

## Estructura de carpetas (no cambies los nombres de archivo)

```
index.html
img/
  foto-hero.jpg      ← foto principal (hero)
  foto-2.jpg         ← galería
  foto-3.jpg         ← galería
  foto-4.jpg         ← galería
  foto-5.jpg         ← galería
  foto-portada.jpg   ← foto de cierre + portada al compartir el link
  musica.mp3         ← agrega tu música aquí (ver abajo)
```

## Cómo cambiar la música

1. Consigue tu MP3 (evita canciones con derechos de autor si el link será público).
2. Ponlo dentro de la carpeta `img/` con el nombre `musica.mp3`.
3. En `index.html`, busca:
   ```html
   <!-- <source src="img/musica.mp3" type="audio/mpeg"> -->
   ```
   Quita el `<!--` y el `-->` para activarlo:
   ```html
   <source src="img/musica.mp3" type="audio/mpeg">
   ```

La música arranca automáticamente cuando se toca el sello del sobre (los navegadores móviles no permiten autoplay antes de una interacción — está diseñado así a propósito).

## Portada al compartir el link (Open Graph)

Ya está configurado en el `<head>` del HTML para usar `img/foto-portada.jpg`. Una vez publicado el sitio en Netlify, revisa que `og:image` apunte a la URL pública final si le cambias el nombre al sitio, ej:
```html
<meta property="og:image" content="https://alejandro-y-camila.netlify.app/img/foto-portada.jpg">
```

## Publicar (GitHub + Netlify)

1. Sube esta carpeta completa (con `index.html` e `img/`) a un repositorio nuevo en GitHub.
2. En app.netlify.com → "Add new site" → "Import an existing project" → conecta el repositorio.
3. Deploy (no necesita build command, es HTML puro).
4. Cambia el nombre del sitio en "Site configuration" para tener un link bonito, ej. `alejandro-y-camila.netlify.app`.

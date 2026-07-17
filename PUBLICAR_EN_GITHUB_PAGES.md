# Publicar la página en GitHub Pages

Esta carpeta (`astral-web-page`) tiene un solo archivo: **`index.html`**.
Es una página autocontenida que llama a tu API de Render, dibuja la rueda natal
y muestra las posiciones y aspectos. Funciona en cualquier navegador del mundo.

> La URL de la API ya está puesta dentro del `index.html`:
> `https://astral-report-api.onrender.com`
> Si algún día cambia, editá la línea `const API_URL = "..."` (arriba del `<script>`).

## Pasos para publicarla

1. Entrá a **https://github.com/new** y creá un repo nuevo, ej: **`carta-natal`**
   (Public, sin README).
2. En el repo vacío → **uploading an existing file** → arrastrá el archivo
   **`index.html`** → **Commit changes**.
3. En el repo, andá a **Settings** (arriba) → en el menú izquierdo **Pages**.
4. En **Build and deployment** → **Source:** elegí **Deploy from a branch**.
5. En **Branch** elegí **`main`** y carpeta **`/ (root)`** → **Save**.
6. Esperá 1–2 minutos. Arriba va a aparecer:
   **“Your site is live at https://TU-USUARIO.github.io/carta-natal/”**
7. Abrí esa URL: ya tenés tu app astral online.

## Probarla

- Completá fecha, hora, buscá la ciudad (llena lat/lon) y **Calcular carta**.
- La **primera** vez que la uses tras un rato, la API de Render está “dormida” y
  tarda ~50 s en responder; después va rápido.

## (Opcional) Restringir el CORS a tu página

Mientras probás, la API acepta llamadas de cualquier origen. Cuando tengas la URL
final de GitHub Pages, podés limitarla:

1. Render → servicio `astral-report-api` → **Environment**.
2. Editá/creá la variable `ALLOW_ORIGINS` con el valor exacto de tu página, ej.:
   `https://TU-USUARIO.github.io`
3. **Save Changes** (redeploya solo).

## Qué muestra hoy y qué se puede sumar

Hoy: carta **natal** (rueda con signos/casas/planetas/aspectos + tabla + Luna Negra + Quirón).

Se puede agregar después:
- **Interpretaciones**: cargar `interpretations_es.json` y mostrar el texto de cada
  planeta en signo/casa (la API ya tiene el endpoint `/api/interpretations` si copiás
  ese archivo junto al backend).
- **Tránsitos / retorno / progresada / combinada** (la API ya calcula tránsitos).
- **Exportar a PDF** desde el navegador.

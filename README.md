# Punto

App personal para tejer: patrones, proyectos, contador de vueltas, esquema de la prenda, lana y agujas.
Un solo `index.html`, sin servidor ni cuentas: todo se guarda en el navegador del móvil.

## Archivos

| Archivo | Para qué |
|---|---|
| `index.html` | La app entera (HTML, CSS y JS). Es lo único que hay que tocar para cambiarla. |
| `manifest.webmanifest` + `icons/` | Para que se instale como app (icono, nombre, pantalla completa). |
| `sw.js` | Service worker: la app abre sin conexión una vez visitada. |
| `patrones/` | Patrones de ejemplo en JSON, listos para importar. |
| `.nojekyll` | Le dice a GitHub Pages que sirva los archivos tal cual. |

## Publicar en GitHub Pages

1. Crea un repositorio (por ejemplo `punto`) y sube esta carpeta a la rama `main`.
2. En el repositorio: **Settings → Pages → Build and deployment → Source: Deploy from a branch → `main` / `/ (root)` → Save**.
3. En un minuto la app está en `https://TU-USUARIO.github.io/punto/`.

Para actualizarla, sustituye `index.html` y haz commit. Como el service worker sirve "red primero", al abrir la app con conexión ya sale la versión nueva; si no, ciérrala del todo y vuelve a abrirla.

## Instalar en el iPhone

Abre la URL en Safari → botón **Compartir** → **Añadir a pantalla de inicio**. Se abre a pantalla completa y funciona sin conexión.

## Datos y copias

Los datos viven solo en ese navegador o en esa app instalada (no se comparten entre Safari y la app de la pantalla de inicio). En **Proyectos → botón "…"** puedes **exportar** una copia JSON e **importarla** en otro móvil o después de reinstalar. Hazlo de vez en cuando.

## Importar un patrón desde un PDF

1. **Patrones → Importar patrón desde el PDF → Copiar las instrucciones para Claude.**
2. Pega esas instrucciones en un chat de Claude junto con el PDF y di la talla. Claude devuelve un JSON.
3. Pégalo en la misma pantalla (o guárdalo como `.json` y usa "Importar desde un archivo").

Con las secciones del patrón, el proyecto tiene esquema de la prenda por casillas, "modo tejer" (instrucciones de la sección en la que estás según el contador) y lista de materiales con opción de pasarlos al stash de lana o a las agujas.

En `patrones/` hay un ejemplo: el Ruke Forest Neckwarmer.

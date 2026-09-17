# Bogotá Transparente — Prototipo (Mapa Interactivo)

Prototipo funcional (MVP) de la fase de Prototipar (Scrum) del proyecto de transparencia en el uso de recursos públicos.

## Qué es
Página web estática de una sola vista (`index.html`), sin backend: los datos de proyectos y presupuestos están de ejemplo dentro del propio archivo, pensados para demostrar la navegación real del producto (mapa → detalle de localidad → proyectos → participación ciudadana).

## Cómo publicarlo gratis con GitHub Pages

1. Crea un repositorio nuevo en GitHub (puede ser público o privado si tienen GitHub Pro/Team; Pages gratis requiere repo público).
2. Sube este archivo `index.html` (y este `README.md` si quieren) a la raíz del repo.
   - Desde la web de GitHub: botón **Add file → Upload files**, arrastra `index.html`, y dale **Commit changes**.
   - O desde terminal:
     ```
     git init
     git add index.html README.md
     git commit -m "Prototipo mapa interactivo"
     git branch -M main
     git remote add origin https://github.com/TU-USUARIO/TU-REPO.git
     git push -u origin main
     ```
3. En el repo, ve a **Settings → Pages**.
4. En "Build and deployment", selecciona **Deploy from a branch**, rama `main`, carpeta `/ (root)`, y guarda.
5. Espera 1-2 minutos. GitHub te dará el link público, normalmente:
   `https://TU-USUARIO.github.io/TU-REPO/`

Ese link ya es la página real, y cualquier compañero del equipo con acceso de escritura al repo puede seguir editando `index.html` y hacer push — Pages se actualiza sola con cada commit a `main`.

## Cómo editar los datos
Todos los datos de las localidades (presupuesto, % de ejecución, proyectos destacados) están en el arreglo `localidades` dentro de la etiqueta `<script>` al final de `index.html`. No hay que tocar el HTML ni el CSS para cambiar cifras — solo ese bloque de JavaScript.

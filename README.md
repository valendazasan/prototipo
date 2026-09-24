# Bogotá Transparente

Plataforma web con mapa interactivo para conocer cómo usan los recursos públicos las 20 alcaldías locales de Bogotá (Fondos de Desarrollo Local), con datos oficiales y actualizados.

## De dónde salen los datos

La página consulta **en vivo**, cada vez que se abre, la API pública de **SECOP II – Contratos Electrónicos** (Colombia Compra Eficiente, `datos.gov.co`, recurso `jbjy-vk9h`). No hay cifras inventadas ni guardadas en el código: lo que se ve es lo que SECOP II tiene publicado en ese momento.

- **Contratado:** suma de `valor_del_contrato` de los contratos firmados en el año por la entidad de cada localidad.
- **Pagado:** suma de `valor_pagado` de esos contratos.
- **% pagado (ejecución financiera):** pagado ÷ contratado.
- **Localidad:** se asigna por el nombre de la entidad contratante (p. ej. "Fondo de Desarrollo Local de Kennedy").
- **Mapa:** límites oficiales de las 20 localidades de IDECA, simplificados y embebidos en `index.html`.

Limitaciones (también explicadas en la página, sección *Datos abiertos*): SECOP II no publica avance físico de obra; solo aparecen contratos firmados por las alcaldías locales (no los de IDU, Secretarías, etc.); y solo lo que la entidad haya publicado en SECOP II.

## Qué hace cada sección

- **Inicio / Mapa:** mapa con D3 (*zoom to bounding box*), buscador de localidad, selector de año, indicadores de la ciudad y panel por localidad (Resumen, Proyectos, Participa).
- **Proyectos:** tabla de todos los contratos con filtros (localidad, año, texto, tipo, estado), orden por columna, paginación, enlace al expediente en SECOP II y descarga CSV.
- **Datos abiertos:** fuentes, metodología, la consulta exacta a la API y descarga del resumen por localidad.
- **Sobre el proyecto:** problema, usuaria y proceso (Design Thinking + Scrum).
- **Reportes ciudadanos:** se guardan en el navegador de quien los hace (`localStorage`) y se pueden copiar para radicarlos en **Bogotá Te Escucha**, el canal oficial del Distrito. Como la página es estática (sin servidor), los reportes no se comparten entre usuarios.

## Publicarla con GitHub Pages

1. Sube `index.html` (y este `README.md`) a la raíz de un repositorio público.
2. En el repo: **Settings → Pages → Deploy from a branch →** rama `main`, carpeta `/ (root)` → **Save**.
3. En 1–2 minutos queda en `https://TU-USUARIO.github.io/TU-REPO/`.

Cualquier compañero con permiso de escritura puede editar `index.html` y hacer push; Pages se actualiza sola.

También se puede probar sin publicar: basta con abrir `index.html` en el navegador con conexión a internet.

## Si algo no carga

La barra de estado bajo el título muestra si la conexión con datos.gov.co funcionó. Si falla, el botón **Actualizar** reintenta. La consulta a la API se puede abrir directamente desde *Datos abiertos → Abrir la consulta a la API* para ver la respuesta cruda.
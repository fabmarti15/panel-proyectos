# panel-proyectos

Índice privado de todo lo que Fabián tiene publicado: URLs vivas, repos, sitios caídos y proyectos aún locales.

**URL final:** https://fabmarti15.github.io/panel-proyectos/

El contenido va cifrado (AES-256-GCM + PBKDF2, 200.000 iteraciones). Sin la clave, `datos.js` no dice nada: no hay títulos, URLs ni carpetas en claro. El repo puede ser público sin filtrar nada.

Publicado y verificado en vivo el 28-07-2026. Repo: https://github.com/fabmarti15/panel-proyectos

## Actualizar el contenido

El listado se edita en `../proyectos.json` (queda **fuera** del repo, a propósito). Después:

```bash
cd ..
python3 cifrar.py          # pide la clave del panel
encolar -m "Actualizar inventario" "05 Herramientas/Panel de Proyectos Publicados/panel-proyectos"
```

La clave no se escribe en este archivo ni en ningún comando: `cifrar.py` la pide. Si
necesitas pasarla sin que quede en el historial de la shell, exporta `PANEL_CLAVE` en la
sesión y listo.

## Archivos

| Archivo | Qué es |
|---|---|
| `index.html` | Puerta de clave + render del panel. Todo en un archivo. |
| `datos.js` | Inventario cifrado. Generado, no editar a mano. |
| `../proyectos.json` | Fuente en claro. **Nunca commitear.** |
| `../cifrar.py` | Genera `datos.js` desde el JSON. |

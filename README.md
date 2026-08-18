# panel-proyectos

Índice privado de todo lo que Fabián tiene publicado: URLs vivas, repos, sitios caídos y proyectos aún locales.

**URL final:** https://fabmarti15.github.io/panel-proyectos/

El contenido va cifrado (AES-256-GCM + PBKDF2, 200.000 iteraciones). Sin la clave, `datos.js` no dice nada: no hay títulos, URLs ni carpetas en claro. El repo puede ser público sin filtrar nada.

Publicado y verificado en vivo el 28-07-2026. Repo: https://github.com/fabmarti15/panel-proyectos

## Sincronizar el repo local (una sola vez)

Los archivos se subieron por la web de GitHub, así que el historial local no calza con el remoto. Antes del primer `git push` desde el Mac:

```bash
cd "/Users/fabianmartinez/Documents/Claude 2/05 Herramientas/Panel de Proyectos Publicados/panel-proyectos"
git remote add origin https://github.com/fabmarti15/panel-proyectos.git
git fetch origin
git reset --hard origin/main
```

## Actualizar el contenido

El listado se edita en `../proyectos.json` (queda **fuera** del repo, a propósito). Después:

```bash
cd ..
PANEL_CLAVE=martifab python3 cifrar.py
cd panel-proyectos && git add datos.js && git commit -m "Actualizar inventario" && git push
```

## Archivos

| Archivo | Qué es |
|---|---|
| `index.html` | Puerta de clave + render del panel. Todo en un archivo. |
| `datos.js` | Inventario cifrado. Generado, no editar a mano. |
| `../proyectos.json` | Fuente en claro. **Nunca commitear.** |
| `../cifrar.py` | Genera `datos.js` desde el JSON. |

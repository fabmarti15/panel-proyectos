# Radar familiar

Panel privado con lo que hay que hacer del colegio, los deportes y la contabilidad.

Se abre con clave. El contenido va cifrado con **AES-256-GCM** y la llave se deriva con
**PBKDF2-HMAC-SHA256, 200.000 iteraciones**, usando Web Crypto en el navegador.
Sin la clave, `datos.js` no revela nombres, fechas, montos ni cuentas: es un blob base64.

Este repo puede ser público sin filtrar nada. Los HTML en claro no se commitean: viven
solo en el Mac, en `05 Herramientas/WhatsApp Asistente/salidas/radar-familia/`.

## Actualizar

Desde `05 Herramientas/Radar Familia Publicado/`:

```
PANEL_CLAVE=<clave> python3 cifrar-radar.py
```

Eso regenera `radar-familia/datos.js`. Después, commit y push de ese único archivo.

La fuente se genera cada mañana con la tarea programada `radar-colegio-diario`.

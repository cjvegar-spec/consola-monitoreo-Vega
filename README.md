# Consola de Monitoreo de Red — Camilo Javier Vega Riaño
Curso: Diseño de Redes Banda Ancha  ·  Trabajo individual
Repositorio (público): https://github.com/cjvegar-spec/consola-monitoreo-vega

## Qué hace esta herramienta
Herramienta de Centro de Operaciones de Red (NOC) simulado que automatiza el monitoreo en tiempo real de disponibilidad y latencia de infraestructura mediante Uptime Kuma sobre Docker y WSL 2, integrando alertas críticas en Telegram y un dashboard interactivo.

## Equipos que monitorea
- Cisco Catalyst 1000-24T (Host: host.docker.internal)
- Cisco Catalyst 2960-X (Host: host.docker.internal)
- Cisco ISR 4331 (Host: host.docker.internal)
- Meraki MX68CW (Host: host.docker.internal)

## Cómo se conecta todo
Un servidor local con Docker ejecuta Uptime Kuma mediante WSL 2. Uptime Kuma realiza sondeos TCP periódicos hacia los equipos de red mapeados mediante la interfaz host.docker.internal. Si se detecta una interrupción o cambio de estado, el sistema envía notificaciones críticas de forma automatizada a través de la Bot API de Telegram.

## Cómo ejecutarla
1. Instalar Docker y WSL 2.
2. Ejecutar el contenedor con Docker Compose:
   ```bash
   docker compose up -d

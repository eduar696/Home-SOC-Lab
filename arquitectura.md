# Arquitectura e Infraestructura del Laboratorio SOC

## 1. Resumen del Entorno
Este laboratorio ha sido diseñado con el propósito de centralizar la telemetría, logs y eventos de seguridad de endpoints distribuidos, permitiendo el análisis de comportamiento defensivo (Blue Teaming) y la ingeniería de detección frente a tácticas de adversarios.

## 2. Componentes de la Red e Infraestructura

El laboratorio utiliza un direccionamiento estático privado y se compone de los siguientes nodos virtuales:

| Rol del Nodo | Sistema Operativo | Dirección IP | Software / Rol Principal |
| :--- | :--- | :--- | :--- |
| **SIEM Server** | Linux / Host Principal | `192.168.0.179` | Wazuh Manager (v4.9.1) & Dashboard |
| **Monitored Endpoint** | Ubuntu Server 20.04 | `192.168.0.173` | Wazuh Agent (v4.9.1) / Servidor supervisado |
| **Attack Station** | Linux / Host Principal | `192.168.0.179` | Simulación de ataque lanzada desde la CLI local |
## 3. Configuración y Despliegue del Agente

Para lograr la visibilidad completa del endpoint supervisado (`soc-endpoint`), se realizaron los siguientes pasos de integración:

1. **Instalación del Agente:** Se desplegó el agente oficial de Wazuh mediante la CLI apuntando hacia la IP central del SIEM Manager.
2. **Activación de Servicios:** Se configuró el servicio del agente para iniciar de forma automática junto al sistema (`systemctl enable wazuh-agent`).
3. **Validación de Telemetría:** Se comprobó que el flujo de logs (`syslog`, `auth.log`) se estuviese enviando correctamente mediante la verificación de la directiva `Logcollector` en las propiedades del agente.

## 4. Capacidades de Monitorización Activas
Actualmente, el agente configurado en el servidor recopila y envía alertas automatizadas en tiempo real sobre los siguientes vectores esenciales:
- Intentos de autenticación del sistema (Éxitos / Fallos de SSH).
- Eventos críticos del módulo de autenticación PAM.
- Monitorización de integridad de archivos críticos del sistema (FIM).

---
[⬅️ Volver a la Portada Principal](README.md)

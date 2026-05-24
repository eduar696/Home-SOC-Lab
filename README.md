# Home-SOC-Lab

## 🚀 Propósito
Desarrollo de un entorno SOC de nivel profesional enfocado en la visibilidad de eventos, correlación de logs y respuesta ante incidentes, optimizando recursos mediante virtualización y gestión de endpoints.

## 🛠️ SOC Analyst Skills Demonstrated
- **Log Analysis & Correlation:** Análisis y correlación de eventos en tiempo real.
- **Threat Detection:** Identificación de patrones de ataque (Brute Force, Escaneo).
- **Linux Security Monitoring:** Monitoreo activo del sistema operativo (PAM, SSH, Sudo).
- **File Integrity Monitoring (FIM):** Detección de cambios en archivos críticos del sistema.
- **Incident Documentation:** Registro estructurado de evidencias siguiendo buenas prácticas.
- **Framework Mapping:** Clasificación de alertas utilizando **MITRE ATT&CK**.

## 🛠️ Infraestructura del Laboratorio
El entorno fue diseñado bajo un esquema de **virtualización eficiente**, optimizando los recursos de hardware disponibles en una única estación de trabajo (Host).

- **Arquitectura:** All-in-One (Wazuh Manager, Indexer y Dashboard centralizados en una única VM).
- **Entorno:** Desplegado mediante máquinas virtuales (Ubuntu Server) para simular un ecosistema de seguridad real con recursos controlados.
- **Alcance:** Implementación integral enfocada en la visibilidad de logs, monitoreo de eventos y configuración de agentes.

## Navegación del Proyecto
- 🛠️ [Configuración de Arquitectura e Infraestructura](arquitectura.md)
- 🚨 [Caso de Uso: Detección de Ataque de Fuerza Bruta SSH](use-cases/ssh-bruteforce.md)

# Home SOC Lab Deployment & Threat Detection

## Overview
Este proyecto consiste en el diseño, despliegue y configuración de un **Laboratorio SOC Doméstico** de nivel profesional. El objetivo principal es simular entornos corporativos reales para la monitorización de infraestructura, recolección centralizada de logs, análisis de telemetría y detección de actividades maliciosas (ataques) mediante reglas de correlación.

## Project Architecture
El laboratorio está estructurado bajo un modelo de monitorización defensiva y simulación de adversarios por CLI (Interfaz de Línea de Comandos):

* **SIEM / Central Management:** Sistema Anfitrión (Mi PC Real - Ubuntu Desktop `soc-lab`). Aloja el núcleo del SIEM (**Wazuh Manager v4.9.1**) encargado de centralizar, decodificar y correlacionar los logs de seguridad recibidos.
  
* **Monitored Endpoint (Victim):** Servidor virtualizado (**Ubuntu Server `soc-endpoint`** con IP `192.168.0.173`). Operando en segundo plano, está protegido con el agente de Wazuh para auditar y enviar registros críticos del sistema (`syslog`, `auth.log`, PAM) hacia el manejador.
  
* **Attack Station & Control Remoto:** Flujo gestionado mediante terminales concurrentes con perfiles de color diferenciados. Se utilizó la consola local (Fondo Morado) como la estación de ataque para lanzar vectores de fuerza bruta SSH dirigidos al endpoint. En paralelo, se mantuvo una terminal remota (Fondo Azul) para auditar el estado interno del servidor víctima de forma eficiente.
  
---

## 🛠️ Infrastructure Documentation
Para conocer en detalle el direccionamiento IP, el mapa de red, los requisitos de software y el proceso paso a paso de la instalación de los agentes, accede al informe técnico de despliegue:

👉 [**Documentación de Arquitectura e Infraestructura**](arquitectura.md)

---

## 🚨 Executed Use Cases (Casos de Uso Detectados)
A continuación se detallan las investigaciones de incidentes reales simulados en el laboratorio, analizados desde la perspectiva de un analista de seguridad de Nivel 1/2:

1. [**Detección de Ataque de Fuerza Bruta SSH**](use-cases/ssh-bruteforce.md)
   - **Enfoque:** Análisis de fallos de autenticación PAM, ráfagas de tráfico SSH y alertas críticas de nivel 10 en Wazuh frente a ataques de adivinación de credenciales.
   - **Framework:** Mapeo directo con MITRE ATT&CK T1110 (Brute Force).

---

## Skills Demonstrated
- Despliegue y configuración de plataformas SIEM (Wazuh).
- Análisis técnico de logs de seguridad y eventos de autenticación Linux.
- Mapeo y categorización de amenazas bajo el estándar MITRE ATT&CK.
- Hardening básico de sistemas operativos y análisis de telemetría defensiva (Blue Teaming).

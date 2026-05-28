# Home SOC Lab Deployment & Threat Detection

## Overview
Este proyecto consiste en el diseño, despliegue y configuración de un **Laboratorio SOC Doméstico** de nivel profesional. El objetivo principal es simular entornos corporativos reales para la monitorización de infraestructura, recolección centralizada de logs, análisis de telemetría y detección de actividades maliciosas (ataques) mediante reglas de correlación.

## Project Architecture
El laboratorio está estructurado bajo un modelo de monitorización centralizada y administración remota por CLI, donde se evalúa el comportamiento de un endpoint frente a vectores de ataque dirigidos al servidor central:

* **SIEM / Central Management (Victim):** Sistema Anfitrión (Mi PC Real - Ubuntu Desktop con entorno local configurado). Aloja el núcleo del SIEM (**Wazuh Manager v4.9.1**) encargado de la recepción, decodificación y correlación de eventos. En el flujo del laboratorio, este sistema actúa como el objetivo receptor de los intentos de acceso.
* **Monitored Endpoint & Attack Station:** Servidor virtualizado (**Ubuntu Server**). Se encuentra protegido y monitorizado activamente mediante un agente ligero de Wazuh para la recolección de logs críticos (`syslog`, `auth.log`, PAM). Para los propósitos del ejercicio, esta máquina actúa simultáneamente como el origen del ataque, ejecutando simulaciones de adversarios (como fuerza bruta SSH con usuarios existentes e inexistentes) dirigidas hacia el SIEM.
* **Flujo de Trabajo y Control Remoto:** Toda la actividad se gestionó desde el entorno gráfico de la PC Real mediante el uso de terminales concurrentes. Se estableció una conexión SSH hacia la máquina virtual utilizando perfiles de color diferenciados (Fondo Azul para la terminal remota del Endpoint / Fondo Morado para la terminal local del SIEM) para operar, ejecutar los ataques y monitorizar los registros de forma ágil sin necesidad de interactuar con la interfaz de VirtualBox.
  


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

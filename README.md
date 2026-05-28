# Home SOC Lab Deployment & Threat Detection

## Overview
Este proyecto consiste en el diseño, despliegue y configuración de un **Laboratorio SOC Doméstico** de nivel profesional. El objetivo principal es simular entornos corporativos reales para la monitorización de infraestructura, recolección centralizada de logs, análisis de telemetría y detección de actividades maliciosas (ataques) mediante reglas de correlación.

## Project Architecture
El laboratorio está estructurado bajo un modelo de monitorización centralizada que conecta sensores (endpoints) con una consola de gestión SIEM.

- **SIEM / Central Management:** Wazuh Manager (v4.9.1) encargado de la recepción de alertas, decodificación de logs y correlación de eventos.
- **Monitored Endpoints:** Servidores Linux (Ubuntu Server 20.04) protegidos mediante agentes ligeros de Wazuh para la recolección de eventos del sistema (syslog, auth.log, PAM).
- **Attack Station:** Estaciones de trabajo dedicadas (Kali Linux / Linux Nativo) utilizadas para la ejecución de simulaciones controladas de adversarios basadas en el framework MITRE ATT&CK.

---

## 🛠️ Infrastructure Documentation
Para conocer en detalle el direccionamiento IP, el mapa de red, los requisitos de software y el proceso paso a paso de la instalación de los agentes, accede al informe técnico de despliegue:

👉 [**Documentación de Arquitectura e Infraestructura**](arquitectura.md)

---

## 🚨 Executed Use Cases (Casos de Uso Detectados)
A continuación se detallan las investigaciones de incidentes reales simulados en el laboratorio, analizados desde la perspectiva de un analista de seguridad de Nivel 1/2:

1. [**Detección de Ataque de Fuerza Bruta SSH**] 
   - **Enfoque:** Análisis de fallos de autenticación PAM, ráfagas de tráfico SSH y alertas críticas de nivel 10 en Wazuh frente a ataques de adivinación de credenciales.
   - **Framework:** Mapeo directo con MITRE ATT&CK T1110 (Brute Force).

---

## Skills Demonstrated
- Despliegue y configuración de plataformas SIEM (Wazuh).
- Análisis técnico de logs de seguridad y eventos de autenticación Linux.
- Mapeo y categorización de amenazas bajo el estándar MITRE ATT&CK.
- Hardening básico de sistemas operativos y análisis de telemetría defensiva (Blue Teaming).

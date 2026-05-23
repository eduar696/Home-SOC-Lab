# Arquitectura del SOC Lab

## 1. Topología de Red
El laboratorio está compuesto por dos nodos principales conectados en una red local virtualizada.

- **Nodo Manager (Ubuntu Server):** - **IP:** 192.168.0.173
  - **Función:** Wazuh Manager, Servidor de Logs, Dashboard.
- **Nodo Agente (Ubuntu Server):**
  - **IP:** 192.168.0.xxx (Coloca aquí la IP de tu agente)
  - **Función:** Endpoint de monitoreo y generación de eventos.

## 2. Validación de Conectividad
Se ha verificado la comunicación bidireccional entre el Nodo Manager y el Nodo Agente.

### Evidencia de Configuración
<img src="docs/ip_ubuntu.jpg" width="900">
*Nodo Manager (Ubuntu): Comando `ip a`*

<img src="docs/Validación de IP Ubuntu Server.jpg" width="900">
*Nodo Agente (Ubuntu): Comando `ip a`*

---

## 3. Gestión Remota (SSH)
Acceso configurado mediante **SSH (Secure Shell)** para control total desde la terminal local.

<img src="docs/ssh-remote-management-setup.png" width="900">
*Descripción: Diferenciación visual entre PC Real (izq) y servidor remoto (der).*

---

## 4. Despliegue de Wazuh Manager
Estado del sistema tras la instalación:

<div style="display: flex; gap: 10px;">
    <img src="docs/wazuh_dashboard_ready1.png" width="45%">
    <img src="docs/wazuh_dashboard_ready2.png" width="45%">
</div>

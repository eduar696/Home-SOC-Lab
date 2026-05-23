# Arquitectura del SOC Lab

## 1. Topología de Red
El laboratorio está compuesto por dos nodos principales conectados en una red local virtualizada.

- **Nodo Manager (Ubuntu Server):** - **IP:** 192.168.0.173
  - **Función:** Wazuh Manager, Servidor de Logs, Dashboard.
- **Nodo Agente (Ubuntu Server):**
  - **IP:** 192.168.0.xxx (Recuerda actualizar con la IP real)
  - **Función:** Endpoint de monitoreo y generación de eventos.

## 2. Validación de Conectividad
Se ha verificado la comunicación bidireccional entre el Nodo Manager y el Nodo Agente.

### Evidencia de Configuración
<img src="docs/ip_ubuntu.jpg" width="900">
*Nodo Manager (Ubuntu): Comando `ip a`*

<img src="docs/Validación de IP Ubuntu Server.jpg" width="900">
*Nodo Agente (Ubuntu): Comando `ip a`*

---

## 3. Despliegue de Wazuh Manager
Tras la configuración inicial de red, procedí con la instalación de Wazuh Manager y Dashboard en el entorno Ubuntu. A continuación, el estado operativo del sistema:

<div style="display: flex; gap: 10px;">
    <img src="docs/wazuh_dashboard_ready1.png" width="45%">
    <img src="docs/wazuh_dashboard_ready2.png" width="45%">
</div>

---

## 4. Gestión Remota (SSH)
Posterior a la instalación, configuré el acceso vía **SSH (Secure Shell)** para optimizar la gestión del laboratorio desde mi terminal local, evitando el uso constante de la interfaz gráfica de VirtualBox.

<img src="docs/ssh-remote-management-setup.png" width="900">
*Descripción: Diferenciación visual entre mi PC Real (izquierda) y el servidor remoto (derecha) mediante perfiles de color.*

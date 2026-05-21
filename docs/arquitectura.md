# Arquitectura del SOC Lab

## Topología de Red
El laboratorio está compuesto por dos nodos principales conectados en una red local virtualizada/física.

- **Nodo Manager (Ubuntu Server):** - IP:192.168.0.184
  - Función: Wazuh Manager, Servidor de Logs, Dashboard.
- **Nodo Agente (Windows 7):**
  - IP:162.168.0.188
  - Función: Endpoint de monitoreo y generación de eventos.


## Validación de Conectividad
Se ha verificado la comunicación bidireccional entre el Nodo Manager y el Nodo Agente mediante pruebas de ICMP (ping).

- **Estado:** Conexión establecida.
- **Evidencia:** Ver anexos de configuración de red.

### Evidencia de Red### 


### Evidencia de Configuración de Red

**Nodo Agente (Windows 7):**
<img src="Validación de IP Windows 7.jpg" width="600">

**Nodo Manager (Ubuntu):**
<img src="ip_ubuntu.jpg" width="600">)


## Fase 2: Despliegue de Wazuh Manager
Se ha completado la instalación de Wazuh Manager y Dashboard en un entorno Ubuntu. 
A continuación se muestra la interfaz operativa:
![Wazuh Dashboard](wazuh_dashboard_ready1.png)
![Wazuh Dashboard](wazuh_dashboard_ready2.png)



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
Nota: El entorno utiliza asignación dinámica de IPs (DHCP) para fines de pruebas.
**Nodo Manager (Ubuntu):**
<img src="ip_ubuntu.jpg" width="600">)


<h2>Fase 2: Despliegue de Wazuh Manager</h2>
<p>Se ha completado la instalación de Wazuh Manager y Dashboard en un entorno Ubuntu. 
A continuación se muestra la interfaz operativa del sistema:</p>

<div style="display: flex; gap: 10px; margin-bottom: 20px;">
    <img src="wazuh_dashboard_ready1.png" alt="Wazuh Dashboard Vista 1" width="45%">
    <img src="wazuh_dashboard_ready2.png" alt="Wazuh Dashboard Vista 2" width="45%">
</div>

<p><em>En estas capturas se observa el panel de control centralizado tras la finalización del asistente de instalación.</em></p>



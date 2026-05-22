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



<img src="Validación de IP Ubuntu Server.jpg" width="900">)
**Nodo Agente (Windows 7)**

**Comando utilizado:** ip a (utilizado para listar las interfaces de red y verificar la configuración IP asignada).

**Resultado:** Se confirma la asignación dinámica de la dirección IP 192.168.0.173 a través del protocolo DHCP, estableciendo la comunicación necesaria para la integración con los servicios del laboratorio.


<img src="ip_ubuntu.jpg" width="900">)
**Nodo Manager (Ubuntu):**

<h2>Fase 2: Despliegue de Wazuh Manager</h2>
<p>Se ha completado la instalación de Wazuh Manager y Dashboard en un entorno Ubuntu. 
A continuación se muestra la interfaz operativa del sistema:</p>

<div style="display: flex; gap: 10px; margin-bottom: 20px;">
    <img src="wazuh_dashboard_ready1.png" alt="Wazuh Dashboard Vista 1" width="45%">
    <img src="wazuh_dashboard_ready2.png" alt="Wazuh Dashboard Vista 2" width="45%">
</div>

<p><em>En estas capturas se observa el panel de control centralizado tras la finalización del asistente de instalación.</em></p>



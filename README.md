# SOC Lab: Implementación de arquitectura de monitoreo y detección de amenazas

## Propósito
Desarrollo de un entorno SOC de nivel profesional enfocado en la visibilidad de eventos, correlación de logs y respuesta ante incidentes, optimizando recursos limitados mediante virtualización y gestión de endpoints remotos.

🛠️ Infraestructura Desplegada

Para el desarrollo del entorno, se ha implementado un servidor Wazuh (All-in-one) sobre una instancia virtualizada, centralizando las capacidades de seguridad en un único nodo de gestión.
Componentes de Gestión

    Wazuh Manager: Motor de correlación, análisis de logs y gestión de vulnerabilidades.

    Wazuh Indexer: Almacenamiento seguro y búsqueda de logs.

    Wazuh Dashboard: Interfaz web para la visualización de datos y respuesta ante incidentes.

    Estado del Servicio: El servidor se encuentra operativo y validado mediante systemctl status wazuh-manager, garantizando la ingesta continua de eventos.


## 📁 Documentación del Proyecto
Para ver la arquitectura detallada, topología de red y validación de servicios, consulta el archivo:
[**Ver Arquitectura del Lab**](arquitectura.md)
    

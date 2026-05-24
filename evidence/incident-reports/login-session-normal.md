# Incident Report: SSH Brute Force Detection

## 📋 Resumen del Incidente
| Campo | Detalle |
| :--- | :--- |
| **Fecha / Timestamp** | 2026-05-23 |
| **Tipo de Ataque** | SSH Brute Force (Fuerza Bruta) |
| **Severidad** | Alta / Medium |
| **IP Origen (Atacante)** | `192.168.0.179` |
| **IP Destino (Objetivo)** | `192.168.0.173` |
| **Usuario Afectado** | `root` / Usuarios inexistentes |

---

## 🔍 Análisis y Hallazgos
Se detectó una ráfaga inusual de intentos de autenticación fallidos dirigidos al puerto estándar de SSH (`22`) del servidor supervisado. Los logs del sistema muestran que el atacante intentó adivinar credenciales de forma automatizada, apuntando principalmente a la cuenta de administración `root`.

### Telemetría de Alertas (Wazuh)
- **Regla Disparada:** ID 5710 (Mitre ATT&CK T1110) - *SSH brute force trying to get access*.
- **Evidencia Adjunta:** Capturas de pantalla almacenadas en la raíz de `/evidence/` y registros de logs PAM correspondientes en el SIEM.

---

## 🛡️ Acción Tomada (Mitigación)
1. **Contención Directa:** Se ejecutó el bloqueo inmediato de la IP de origen (`192.168.0.179`) en el firewall perimetral / reglas de iptables del servidor afectado para detener la ráfaga de conexiones.
2. **Recomendación de Hardening:** Deshabilitar por completo el login directo del usuario `root` a través de SSH en el archivo `/etc/ssh/sshd_config` (`PermitRootLogin no`).

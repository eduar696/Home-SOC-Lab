# SSH Brute Force Detection

## Objective
Simulé y detecté un ataque de Fuerza Bruta SSH contra un punto final Linux monitorizado utilizando Wazuh SIEM.

## Tools
- Wazuh Manager & Agent (v4.9.1)
- Ubuntu Server 20.04

## Attack Simulation
Se generaron manualmente múltiples intentos fallidos de inicio de sesión SSH desde la estación de trabajo del SOC contra el punto final monitoreado 192.168.0.173 utilizando una cuenta de usuario inexistente (raulxi).

**Attack Command:**
`ssh raulxi@192.168.0.173`

Se provocaron intencionadamente varios fallos de autenticación para simular intentos de acceso no autorizados.

## Detection and Analysis 
Wazuh recopiló y analizó correctamente los registros de autenticación del servidor Ubuntu monitorizado.

El SIEM generó alertas relacionadas con:
- Failed authentication attempts
- PAM authentication events
- Login session activity
- Agent monitoring events

### Relevant Findings
- **Source Target:** 192.168.0.173
- **Attack Type:** SSH Brute Force Attempt
- **Authentication Status:** Failed
- **Detection Source:** Wazuh Agent
- **Monitored Endpoint:** soc-endpoint

## SOC Investigation
El SOC detectó repetidos intentos fallidos de inicio de sesión en servicios SSH, lo que indica una posible actividad de fuerza bruta.

Los intentos de autenticación utilizaron una cuenta no válida, lo que podría indicar:
- Unauthorized access attempts
- Credential guessing
- Reconnaissance behavior

El evento se registró correctamente y es visible en el panel de control de Wazuh para su posterior investigación.

## Mapeo MITRE ATT&CK
- **T1110** — Ataque de fuerza bruta
- **T1078** — Cuentas válidas (intento realizado)

## Result 
El laboratorio SOC doméstico detectó y registró con éxito actividad de autenticación SSH sospechosa utilizando Wazuh SIEM.

## Evidence

<table align="center" border="0" cellpadding="0" cellspacing="0">
  <tr>
    <td width="49%" align="center" valign="top">
      <h4>Vista del Atacante (Terminal)</h4>
      <img src="../evidence/screenshots/Vista%20del%20atacante%20(terminal%20mv).png" alt="Vista del Atacante" style="max-width:100%;" />
    </td>
    <td width="2%"></td>
    <td width="49%" align="center" valign="top">
      <h4>Vista del Analista SOC (SIEM Wazuh)</h4>
      <img src="../evidence/screenshots/Vista%20del%20Analista%20SOC%20(SIEM%20WAZUH).png" alt="Vista del Analista SOC" style="max-width:100%;" />
    </td>
  </tr>
</table>

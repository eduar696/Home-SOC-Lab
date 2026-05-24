# SSH Brute Force Detection

## Objective
Detect multiple failed SSH login attempts.

## Tools
- Wazuh Agent/Manager
- Ubuntu Server

## Attack Simulation
`ssh invaliduser@192.168.x.x` (ejecutado 5+ veces).

## Detection
Wazuh rule 5710 (SSH brute force attempt) triggered.

## Evidence
[Screenshot del Dashboard]

## MITRE ATT&CK
T1110 - Brute Force

## Result
SOC successfully detected suspicious activity.

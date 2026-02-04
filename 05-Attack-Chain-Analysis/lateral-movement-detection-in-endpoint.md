# Lateral Movement Detection in Endpoint (Wazuh SIEM)

## Scenario Overview

Simulated repeated authentication sessions and privilege usage on a monitored Kali endpoint to analyze potential lateral movement behavior.

## Alert Observations

<img width="1918" height="720" alt="image" src="https://github.com/user-attachments/assets/050453aa-b8ae-4237-94f4-87a17fc78756" />


- Multiple **PAM: Login session opened** events
- Multiple **PAM: Login session closed** events
- Repeated **Successful sudo to ROOT executed**

## Behavior Pattern Identified

| Activity | Interpretation |
|----------|----------------|
Repeated sessions | Possible access testing or movement preparation |
Privilege usage | Elevated access obtained |
Short time interval | Automated or attacker-driven behavior |

## Analysis

The combination of repeated session activity and privilege execution suggests preparation for lateral movement. In real environments, attackers use this stage to spread across systems after initial compromise.

## Decision

⚠️ Suspicious behavior consistent with **Lateral Movement stage** of an attack chain.

## Learning Outcome

- Learned to correlate authentication + privilege logs  
- Understood how lateral movement appears in SIEM  
- Improved attack chain stage recognition

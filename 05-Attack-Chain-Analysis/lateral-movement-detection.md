# 🧪 Lateral Movement Detection using Wazuh SIEM

## 📌 Scenario Overview

This lab simulates lateral movement behavior, where an attacker uses valid credentials to access multiple systems within a short time period.

The objective was to identify authentication patterns that suggest credential misuse and potential attacker expansion across systems.

---

## 🎯 Objective

To detect suspicious login behavior indicating possible lateral movement.

---

## 🛠 Lab Simulation Steps

1. Generated multiple SSH login sessions on the monitored Kali endpoint:
   ```bash
   ssh localhost
   ```
<img width="1693" height="316" alt="LM_4" src="https://github.com/user-attachments/assets/2736603e-1ac7-49c9-b939-4290089ffa50" />


Repeated several times with short intervals between sessions.

2. Exited each session and repeated to create multiple authentication events.

---

## 🔍 Logs & Evidence

Observed in Wazuh SIEM:

- Multiple successful SSH login events

- Same user account used

- Login events occurred close together in time
<img width="1906" height="638" alt="LM_1" src="https://github.com/user-attachments/assets/e2e902de-af0d-4015-a003-a2fb79ce3277" />
  

This pattern created a sequence of authentication activity.

---

## 🧠 Analysis

Normal users rarely log into multiple systems rapidly.

This behavior may indicate:

- Stolen credentials

- Account testing by attacker

- Movement from one system to another

Pattern observed:
> Valid login → Another login → Multiple sessions → Short time window

This matches lateral movement behavior.

---

## ⚠ Risk Assessment

Risk Level: *MEDIUM*

Reason:

- No immediate system modification observed

- But indicates attacker expanding access

Requires monitoring and correlation with other suspicious activity.

---

## 📤 SOC L1 Decision

Action: **Escalated for review.**

Reason:

- Repeated login pattern indicates possible credential misuse.

---

## 📘 Key Learning Outcomes

- Learned to detect lateral movement patterns

- Understood difference between normal login and suspicious login sequence

- Practiced time-based authentication analysis

- Improved behavior-based detection skills

---

## 🔑 Core SOC Principle

> Multiple valid logins in a short time window can indicate attacker movement even without failed attempts.

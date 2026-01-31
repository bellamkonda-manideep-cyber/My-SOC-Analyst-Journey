# 🧪 Outbound Behavior Hunting (C2 Pattern Detection) using Wazuh SIEM

## 📌 Scenario Overview

In this lab, outbound network behavior was simulated from a Kali Linux endpoint monitored by Wazuh SIEM.

The goal was to detect repeated outbound activity that resembles **Command & Control (C2) communication**, a common behavior of malware and compromised systems.

Unlike simple command detection, this lab focuses on **behavioral pattern recognition**.

---

## 🎯 Objective

To identify potential C2-like activity by detecting repeated execution of an outbound command.

---

## 🛠 Lab Simulation Steps

1. Generated repeated outbound traffic using:
   ```bash
   while true; do curl http://example.com > /dev/null; sleep 45; done
   ```
<img width="825" height="242" alt="image" src="https://github.com/user-attachments/assets/e6402769-bece-46d5-9543-3f0e1b0a5dbc" />


2. Allowed the loop to run for several minutes.

3. Stopped the process.

---

## 🔍 Logs & Evidence

Observed in Wazuh SIEM:

- Multiple executions of the `curl` command

- Events logged via auditd integration

- Repeated process activity across time

<img width="1916" height="910" alt="Screenshot 2026-01-30 201457 hihg1" src="https://github.com/user-attachments/assets/e1129b2e-f12f-456d-aa6e-baac1eb1de45" />


This confirmed process execution visibility and repeated behavior.

---

## 🧠 Analysis

Repeated outbound commands at regular intervals can indicate:

- Beaconing behavior

- Malware calling back to attacker server

- Early-stage C2 communication

Even though `curl` is a legitimate tool, behavior over time is suspicious.

Repeated execution → Fixed interval → External communication

This pattern aligns with C2 tactics.

---

## ⚠ Risk Assessment

Risk Level: *MEDIUM*

Reason:

- Indicates potential remote control activity

- Could allow attacker to receive commands

- Needs correlation with other suspicious behaviors

---

## 📤 SOC L1 Decision

Action: Escalated for further investigation.

Reason:

- Repeated outbound execution pattern suggests possible compromise stage.

---

## 📘 Key Learning Outcomes

- Learned difference between tool detection and behavior detection

- Practiced identifying C2-like patterns

- Improved threat hunting skills

- Understood importance of time-based analysis

---

## 🔑 Core SOC Principle

> "Repetition and timing patterns often reveal malicious behavior even when tools appear legitimate."

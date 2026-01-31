# 🧪 Case Study — Multi-Stage Attack Chain Detection using Wazuh SIEM

## 📌 Scenario Overview

This case study links multiple suspicious activities observed on a monitored Kali Linux endpoint into a **single correlated security incident**.

Instead of treating alerts individually, this investigation focuses on **attack progression analysis** — a key SOC analyst skill.

---

## 🎯 Objective

To identify and correlate multiple security events that form a **complete attack chain**, representing a real-world compromise scenario.

---

## 🔗 Attack Chain Identified

| Stage | Evidence |
|------|---------|
| **Execution** | Suspicious command execution activity |
| **Credential Misuse** | Multiple failed logins followed by success |
| **Privilege Escalation** | Successful `sudo` execution |
| **Persistence** | Cron job created to run repeatedly |
| **Command & Control (C2)** | Repeated outbound `curl` executions |

---

## 🛠 Investigation Summary

### 1️⃣ Authentication Suspicious Activity
- Observed multiple failed login attempts
- Successful login followed failures
- Privileged command execution occurred

### 2️⃣ Persistence Creation
- Cron job added to system
- Scheduled task executed automatically
- Indicates attacker maintaining access

### 3️⃣ Outbound Behavior
- Repeated `curl` executions at intervals
- Pattern resembles beaconing
- Potential C2 communication behavior

---

## 🧠 Analysis

When observed separately, each event may appear moderate.  
When correlated, they show:

```Access gained → Foothold maintained → Remote communication established```


This represents a **multi-stage compromise** rather than isolated activity.

---

## ⚠ Risk Assessment

**Risk Level: HIGH**

Because:
- Privilege usage occurred
- Persistence established
- Outbound communication observed
- Indicates system compromise

---

## 📤 SOC L1 Decision

**Action:** Escalated as a confirmed multi-stage incident.

Reason:
- Evidence shows progression through multiple attack lifecycle stages.

---

## 📘 Key Learning Outcomes

- Learned how to correlate multiple alerts into a single incident
- Understood real-world attack progression
- Practiced attack lifecycle analysis
- Improved SOC incident storytelling skills

---

## 🔑 Core SOC Principle

> Individual alerts show activity. Correlated events reveal compromise.

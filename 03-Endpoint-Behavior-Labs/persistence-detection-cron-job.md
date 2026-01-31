# 🧪 Persistence Detection (Cron Job Monitoring) using Wazuh SIEM

## 📌 Scenario Overview

In this lab, a persistence mechanism was simulated on a Kali Linux endpoint monitored by Wazuh SIEM.

The objective was to detect how attackers maintain access to a compromised system by creating scheduled tasks (cron jobs).

This lab focuses on detecting **system modification behavior**, which is a key stage in the attack lifecycle.

---

## 🎯 Objective

To simulate and detect attacker persistence using a cron job and analyze the activity in Wazuh SIEM.

---

## 🛠 Lab Simulation Steps

1. Opened crontab editor:
   ```bash
   crontab -e
   ```

2. Added a scheduled job:
   ```bash
   * * * * * echo "test persistence" >> /tmp/persist.log
   ```
<br>
   <img width="641" height="268" alt="image" src="https://github.com/user-attachments/assets/824d611d-af5b-4f1e-a746-e1811b9ce7a5" />
<br>

3. Saved and exited the editor.

4. Waited for the cron job to execute.

---

## 🔍 Logs & Evidence

Observed in Wazuh SIEM:

- Cron activity logged

- Cron modification detected

- Scheduled job execution recorded

These logs confirm system-level modification.

<img width="1919" height="795" alt="image" src="https://github.com/user-attachments/assets/97f1bf60-b6a8-4ca3-9346-54fc2f988843" />

---

## 🧠 Analysis

Cron jobs are commonly used by attackers to:

- Maintain system access

- Execute malicious scripts repeatedly

- Ensure malware runs after reboot

Even though cron is a legitimate system feature, its misuse indicates:

> "System access gained → Persistence established"

This behavior represents attacker foothold creation.

---

## ⚠ Risk Assessment

Risk Level: *MEDIUM*

Because:

- Persistence allows attacker re-entry

- Indicates system compromise may have occurred earlier

- Requires further investigation to determine source of modification

---

## 📤 SOC L1 Decision

**Action:** Escalated for further investigation.

📤 SOC L1 Decision

- Action: Escalated for further investigation.

---

## 📘 Key Learning Outcomes

- Learned how persistence appears in SIEM logs

- Understood cron job misuse as attacker technique

- Practiced endpoint behavior analysis

- Improved ability to detect system modification threats

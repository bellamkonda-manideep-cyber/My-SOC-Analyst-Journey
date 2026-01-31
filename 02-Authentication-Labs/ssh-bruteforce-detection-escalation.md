## SSH Brute-Force Detection & Escalation (Wazuh SIEM)

### Scenario Overview

* Configured Kali Linux as a monitored endpoint using Wazuh agent

* Generated multiple SSH authentication failures targeting a non-existent user account

* Observed correlated authentication events and rule escalation in Wazuh SIEM

* Performed SOC L1 investigation and escalated based on attack pattern

---
### Alert Details

* Alert Type: SSH Brute-Force Attempt

* Detection Source: Wazuh SIEM

* Affected System: Kali Linux endpoint

* Severity: Medium → High (rule correlation)

---
### Logs & Evidence

* Multiple SSH authentication failures detected within a short time window

* Attempts targeted a non-existent user, indicating enumeration or brute-force behavior

* Wazuh correlation rules triggered higher-level alerts
  
<br>
<img width="1894" height="682" alt="Wazuh SSH brute-force events" src="https://github.com/user-attachments/assets/f7cc47c1-4c6f-4ef5-82b1-cbd5861fc6d0" />

---
### Analysis

* Reviewed authentication logs generated from the Kali endpoint

* Identified a high frequency of failed SSH login attempts within one minute

* Observed repeated attempts against a non-existent user account

* Pattern indicated automated or malicious behavior rather than user error

* Activity met criteria for brute-force detection

---
### Decision (Escalated)

* Escalated to SOC L2

* Due to repeated authentication failures, short time window, invalid user targeting, and brute-force pattern

---
### Analyst Notes

* Observed 27 repeated SSH authentication failures within a one-minute window targeting a non-existent user account. Correlated events triggered brute-force detection rules in Wazuh SIEM. Escalating for further investigation and response.

---
### Learning Outcome

* Gained hands-on experience detecting brute-force attacks using Wazuh SIEM

* Learned how correlation rules elevate multiple low-level events into a higher-risk alert

* Practiced SOC L1 escalation decision-making based on behavior and context

* Improved documentation skills for SOC-to-SOC handover

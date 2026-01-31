## Authentication Failed Login Analysis (Wazuh SIEM)
### Scenario Overview

* Configured a Kali Linux system as a monitored endpoint using Wazuh agent.

* Generated multiple failed authentication attempts by entering incorrect passwords.

* Observed security events in Wazuh SIEM and followed SOC L1 investigation workflow.

* Analyzed logs, applied context, made a decision, and documented findings.

---
### Alert Details

* Alert Type: Authentication failure.

* Detected By: Wazuh SIEM.

* Monitored System: Kali Linux endpoint.

---
### Logs & Evidence

Timestamp: Jan 7, 2026 @ 14:27:44

Agent Name: kali

Log Source: Authentication logs

Event Detail: Password authentication failed 

<br>

<img width="1891" height="173" alt="image" src="https://github.com/user-attachments/assets/e633c189-5bb4-4438-8d33-f447169fc10b" />

---

### Analysis

* Reviewed authentication events generated from the Kali endpoint.

* Observed a small number of failed login attempts within a short time window.

* Activity originated from the local system with no external IP involvement.

* No indicators of brute-force behavior, lateral movement, or persistence were observed.

* Context indicated this was expected activity in a test environment.

---  

### Decision

* Closed as False Positive.

* Based on limited failed attempts, local source, and absence of malicious patterns, the activity did not indicate a real security incident.

---

### Learning Outcome

* Gained hands-on experience with Wazuh SIEM alert generation and log analysis.

* Learned how authentication failures appear in SIEM tools.

* Practiced SOC L1 decision-making using evidence and context

* Understood the importance of documenting analysis clearly for SOC workflows

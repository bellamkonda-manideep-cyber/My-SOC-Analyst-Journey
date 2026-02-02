# 🧠 Threat Hunting Playbook — SOC Analyst Pattern Library

This playbook documents common behavioral patterns used during threat hunting.  
Instead of relying only on alerts, these patterns help identify attacker activity through event correlation and behavior analysis.

---

## 🎯 Purpose

To detect hidden threats by identifying **sequences of suspicious activity** across authentication, endpoint, and network logs.

---

## 🔥 Pattern 1 — Execution → Network

**Hunt Focus:**
> Process execution → Shortly after → Outbound network connection

**Why suspicious:**
Malware often executes and immediately contacts a remote server.

**Catches:**
- Downloaders  
- Reverse shells  
- Initial Command & Control (C2)

---

## 🔥 Pattern 2 — Authentication → Privilege Use

**Hunt Focus:**
> Multiple failed logins → Successful login → sudo/admin action


**Why suspicious:**
May indicate password guessing followed by privilege escalation.

**Catches:**
- Credential compromise  
- Unauthorized admin access

---

## 🔥 Pattern 3 — Execution → Persistence

**Hunt Focus:**
> Suspicious command execution → Cron job / scheduled task / service creation

**Why suspicious:**
Attacker is establishing a foothold to maintain access.

**Catches:**
- Malware persistence  
- Backdoor installation

---

## 🔥 Pattern 4 — Persistence → Network

**Hunt Focus:**
> Scheduled task → Repeated outbound traffic


**Why suspicious:**
Persistent malware beaconing to attacker-controlled infrastructure.

**Catches:**
- C2 communication  
- Botnet activity

---

## 🔥 Pattern 5 — Authentication → Lateral Movement

**Hunt Focus:**
> User logs into multiple systems in short time


**Why suspicious:**
May indicate stolen credentials being used to move across the network.

**Catches:**
- Lateral movement  
- Account misuse

---

## 🔥 Pattern 6 — Endpoint Change → Outbound Spike

**Hunt Focus:**
> System modification → Sudden increase in outbound data


**Why suspicious:**
Could indicate data staging and exfiltration.

**Catches:**
- Data theft  
- Insider threat

---

## 🧠 Hunting Mindset

- Single events can be normal  
- **Sequences** reveal attacks  
- Context (user role, timing, system type) is critical  
- Always correlate endpoint + authentication + network logs

---

## 🔑 Core Principle

> Threat hunting is the art of connecting weak signals into a strong story of compromise.

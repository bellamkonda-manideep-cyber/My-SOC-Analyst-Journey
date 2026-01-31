# ❌ False Positive Analysis

A false positive is an alert that appears suspicious but is actually normal activity.

---

## 🔍 Common Causes

- User typo (wrong password)
- System maintenance
- IT testing activities
- Misconfigured rules

---

## 🧠 How SOC Identifies False Positives

Analysts check:

- Source IP (internal/external)
- Time of activity (business hours?)
- User role (admin or normal user?)
- Pattern (single event or repeated?)
- Related suspicious behavior?

---

## ⚠ Danger of Misclassification

| Mistake | Result |
|---------|--------|
False positive treated as attack | Wasted resources |
Real attack treated as false | Security breach |

---

## 🔑 SOC Rule

> “Logs and context decide, not assumptions.”

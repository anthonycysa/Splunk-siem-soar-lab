# 🛡️ NIST Cybersecurity Framework (CSF) Mapping for Splunk SIEM + SOAR Lab

This document maps the Splunk SIEM + SOAR playbooks to the NIST CSF Core Functions, Categories, and Subcategories, showing how the lab aligns with real-world cybersecurity controls.

---

## 🧠 Brute Force Response Playbook

| NIST CSF Function | Category (ID)       | Subcategory (ID)                          | Playbook Activity Description                              |
|-------------------|---------------------|-------------------------------------------|------------------------------------------------------------|
| **Identify**      | Risk Management Strategy (ID.RM) | ID.RM-1: Risk management processes are established | Understand and address brute force risks and likelihood.  |
| **Protect**       | Access Control (PR.AC) | PR.AC-1: Identities and credentials are managed | Monitor and restrict repeated failed login attempts.       |
| **Detect**        | Anomalies and Events (DE.AE) | DE.AE-1: Anomalous activity is detected and understood | Detect brute-force attempts based on abnormal login patterns. |
| **Respond**       | Response Planning (RS.RP) | RS.RP-1: Response plan is executed during or after an event | Initiate automated containment (e.g., block IP, disable account). |
| **Recover**       | Improvements (RC.IM) | RC.IM-1: Recovery plans incorporate lessons learned | Update detection thresholds and playbook logic post-incident. |

---

## 📧 Phishing Email Response Playbook

| NIST CSF Function | Category (ID)       | Subcategory (ID)                          | Playbook Activity Description                              |
|-------------------|---------------------|-------------------------------------------|------------------------------------------------------------|
| **Identify**      | Asset Management (ID.AM) | ID.AM-5: Resources (e.g., hardware, devices, data) are prioritized | Email threat intelligence is leveraged to prioritize response. |
| **Protect**       | Awareness and Training (PR.AT) | PR.AT-2: Users are trained to recognize and report phishing | Incorporate user-submitted reports into playbook workflow. |
| **Detect**        | Anomalies and Events (DE.AE) | DE.AE-3: Event data are aggregated and correlated from multiple sources | Analyze email header, link reputation, and user behavior. |
| **Respond**       | Analysis (RS.AN) | RS.AN-4: Incidents are categorized based on impact | Categorize phishing attempts by impact or severity. |
| **Recover**       | Communications (RC.CO) | RC.CO-2: Reputation is repaired after an incident | Notify users and teams post-remediation; document findings. |

---

✅ **How to Use This Mapping**:
- This file explains how automated playbooks align with NIST CSF controls.
- Great for audit preparedness, or SOC documentation.

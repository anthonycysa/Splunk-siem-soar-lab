# 🔐 PCI DSS Mapping for Splunk SIEM + SOAR Lab

This document maps the Splunk SIEM + SOAR playbooks to PCI DSS v4.0 requirements, demonstrating how this lab helps support and validate cardholder data security controls.

---

## 🧠 Brute Force Response Playbook

| PCI DSS Requirement | Description                                                                 | Playbook Support                                                                 |
|---------------------|-----------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| **8.3.6**           | Lock user accounts after multiple invalid access attempts                   | Detects and responds to repeated failed logins by disabling accounts/IP blocking |
| **10.2.1**          | Implement automated audit logs of user activities                           | Playbook actions logged in Splunk with timestamps and outcomes                   |
| **10.4.1.1**        | Detect anomalies and security events                                        | Alerts on brute-force patterns using correlation searches                        |
| **12.10.5**         | Include detection and response in the incident response plan                | SOAR playbook is part of defined response process                                |

---

## 📧 Phishing Email Response Playbook

| PCI DSS Requirement | Description                                                                 | Playbook Support                                                                 |
|---------------------|-----------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| **5.2.2**           | Detect and respond to malware threats                                       | Scans and analyzes suspicious links/attachments in emails                        |
| **10.2.1**          | Maintain audit logs of user activity                                        | All response steps logged and stored in Splunk                                   |
| **11.5.1.1**        | Respond to unauthorized email/messaging access attempts                     | Validates sender spoofing or credential compromise indicators                    |
| **12.10.5**         | Incident response testing and improvement                                   | Playbook actions feed into IR plans and tuning                                   |

---

✅ **Why This Matters**  
Mapping this automation lab to PCI DSS shows real-world value to auditors. It demonstrates security operations maturity and understanding of compliance-driven environments.

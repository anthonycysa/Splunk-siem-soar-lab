# MITRE ATT&CK Mapping for Splunk SIEM + SOAR Lab

This document maps the lab’s SOAR playbooks to relevant MITRE ATT&CK techniques and sub-techniques. These mappings demonstrate how Splunk can support detection and automated response aligned with real-world adversary behaviors.

---

## 🧠 Brute Force Response Playbook

### ATT&CK Tactics:
- **Initial Access (TA0001)**
- **Credential Access (TA0006)**
- **Persistence (TA0003)**

### ATT&CK Techniques:
| Technique | Name | Description |
|----------|------|-------------|
| **T1110** | Brute Force | Detects repeated failed logins across endpoints or servers. |
| **T1078** | Valid Accounts | If brute force is successful, attacker uses stolen credentials. |
| **T1556.001** | Credential Dumping: LSASS Memory | In some scenarios, brute force attempts follow with credential dumping. |

### Splunk Detection Sources:
- Windows Security Logs
- Linux auth logs
- VPN / Firewall logs

### SOAR Response Actions:
- Automatically disable user account
- Notify security team via email or Slack
- Enrich source IP with threat intel
- Add IP to blocklist

---

## 📧 Phishing Email Response Playbook

### ATT&CK Tactics:
- **Initial Access (TA0001)**
- **Execution (TA0002)**
- **Command and Control (TA0011)**

### ATT&CK Techniques:
| Technique | Name | Description |
|----------|------|-------------|
| **T1566.001** | Phishing: Spearphishing Attachment | Email contains malicious file (e.g., Word doc with macros). |
| **T1059** | Command and Scripting Interpreter | If payload is executed, attacker may use PowerShell or CMD. |
| **T1105** | Ingress Tool Transfer | Malware downloads additional tools from C2 server. |

### Splunk Detection Sources:
- Email gateway logs (e.g., Proofpoint, Microsoft 365)
- Endpoint detection (EDR alerts)
- DNS traffic (to detect C2 domains)

### SOAR Response Actions:
- Extract IOCs (IP, domain, hash) from email
- Block sender domain
- Quarantine message in inbox
- Notify SOC and affected user

---

## ✅ Summary

This lab demonstrates how security operations teams can align detection and response actions with MITRE ATT&CK to improve incident handling, prioritize threats, and communicate impact to stakeholders.

---

**Author:** [anthonycysa](https://github.com/anthonycysa)  
**Project:** [Splunk SIEM + SOAR Lab](https://github.com/anthonycysa/splunk-siem-soar-lab)

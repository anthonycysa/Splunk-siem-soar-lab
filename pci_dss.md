# 💳 PCI DSS Mapping – Splunk SIEM + SOAR Lab

This document outlines how the Splunk SIEM + SOAR lab aligns with key controls from the **PCI DSS v4.0** standard, specifically those relevant to monitoring, alerting, and automated response.

---

## 🧩 Mapped Requirements

| PCI DSS Requirement | Description                                         | Lab Implementation |
|---------------------|-----------------------------------------------------|---------------------|
| **10.2.5**          | Log all access to privileged user IDs              | Alerts for admin logins via Event ID 4624 & 4672 (Windows) |
| **10.2.6**          | Log initialization of audit logs                   | Windows log source ingestion into Splunk, including audit logs |
| **10.3.1 - 10.3.6** | Audit logs must include user ID, type, timestamp   | All Splunk detections include this metadata in alert fields |
| **10.4.1**          | Synchronize system clocks                          | Time-normalized log data ensures correlation accuracy |
| **10.6.1**          | Review logs and security events daily              | Real-time alerts and dashboards set up for continuous monitoring |
| **10.7.1**          | Retain audit logs for at least 12 months           | Configurable Splunk data retention settings (documented or simulated) |
| **11.5.1**          | Monitor for unauthorized changes to critical files | Can be simulated with file integrity logging (Sysmon + Splunk) |
| **12.10.5**         | Test incident response procedures annually         | SOAR playbooks simulate incident response (disable user, isolate host) |

---

## 🔧 Example: Splunk Alert → PCI Mapping

| Detection Use Case             | PCI DSS Control | Explanation |
|--------------------------------|------------------|-------------|
| Excessive failed login attempts | 10.2.5           | Helps track misuse of privileged credentials |
| PowerShell misuse or scripting | 10.3.1 - 10.3.6   | Each log includes full metadata for compliance |
| DNS tunneling or exfiltration  | 10.6.1            | Detected and alerted through correlation search |
| SOAR automation triggered      | 12.10.5           | Response simulation fulfills incident workflow requirement |

---

## 🔗 References

- [PCI DSS v4.0 Official Guide (PDF)](https://www.pcisecuritystandards.org/document_library?category=pcidss&document=pci_dss)
- [Splunk + PCI DSS Compliance App](https://splunkbase.splunk.com/app/3605/)

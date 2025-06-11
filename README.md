# 🔐 Splunk SIEM + SOAR Lab

This project simulates real-world SOC workflows using Splunk to detect and respond to threats with both SIEM analytics and SOAR-style playbooks.

## 📌 Use Case
Detect brute force attacks and suspicious privilege escalations in Windows event logs. Simulate SOAR-style response actions such as IP enrichment, analyst alerting, and IP blocking logic.

## 🧰 Tools
- Splunk Enterprise (Free/Trial)
- Mocked SOAR Playbooks (Markdown)
- MITRE ATT&CK framework (manual mapping)

## 📂 Project Structure
| Folder | Description |
|--------|-------------|
| `detections/` | SPL detection rules |
| `dashboards/` | Sample XML dashboard |
| `soar-playbooks/` | Simulated response logic |
| `logs/` | Sample log data |
| `docs/` | MITRE mapping + setup |

> Built to showcase SIEM analysis and SOAR logic for SOC Analyst roles.

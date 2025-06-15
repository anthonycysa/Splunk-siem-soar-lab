# 📘 NIST Cybersecurity Framework (CSF) Mapping – Splunk SIEM + SOAR Lab

This file shows how our Splunk lab supports the five NIST CSF functions and underlying categories.

---

## 🔐 NIST CSF Function Mappings

| Function | Category | Splunk Use Case |
|----------|----------|-----------------|
| **Identify** | Asset Management (ID.AM) | Splunk collects logs from multiple asset types |
| **Protect**  | Access Control (PR.AC)   | Detects privileged account activity, lateral movement |
| **Detect**   | Anomalies & Events (DE.AE) | Correlation searches for brute force, malware, etc. |
| **Respond**  | Response Planning (RS.RP) | SOAR playbooks simulate IR workflows (e.g., disable user) |
| **Recover**  | Recovery Planning (RC.RP) | Use-case placeholder; logs support IR documentation |

---

## 🧭 Visual Flowchart

![NIST Flowchart](./nist_flowchart.png)

---

## 🔗 References

- [NIST CSF Official Page](https://www.nist.gov/cyberframework)

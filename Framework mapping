📘 NIST Cybersecurity Framework (CSF) Mapping – Splunk SIEM + SOAR Lab

This document maps the lab's detection, monitoring, and response capabilities to the NIST Cybersecurity Framework (CSF). The CSF is widely used by security teams to assess maturity and align operations with industry best practices.

---

## 🔐 CSF Functions Overview

The five core functions of the NIST CSF are:

- **Identify (ID)** – Understand the environment to manage cybersecurity risk
- **Protect (PR)** – Implement safeguards to limit or contain threats
- **Detect (DE)** – Identify the occurrence of a cybersecurity event
- **Respond (RS)** – Take action after a detected event
- **Recover (RC)** – Restore capabilities after an incident

---

## 🔎 Mapped Lab Capabilities

| CSF Function | Category       | Subcategory                         | Lab Implementation Example |
|--------------|----------------|--------------------------------------|-----------------------------|
| **Identify** | ID.AM-1        | Inventory of authorized devices      | Hosts are identified and logged via Windows and Sysmon log sources |
|              | ID.RA-1        | Asset risk assessments               | Vulnerability scanning alerts integrated (future: Nessus integration) |
| **Protect**  | PR.AC-1        | Identity management & access control | Admin login attempts tracked through Windows logs |
|              | PR.DS-2        | Data-in-transit protection           | DNS tunneling detection used to uncover data exfiltration attempts |
| **Detect**   | DE.CM-7        | Unauthorized access detection        | Alerts on excessive failed logins from the same user/IP |
|              | DE.AE-1        | Detection of anomalies and events    | Detects PowerShell abuse, process injection, and abnormal task scheduling |
|              | DE.CM-1        | Continuous monitoring                | Splunk dashboards & scheduled alerts on endpoints, DNS, and Windows logs |
| **Respond**  | RS.CO-2        | Incident response coordination       | SOAR playbooks triggered to disable users or isolate endpoints |
|              | RS.AN-1        | Event analysis                       | Deep event investigation via Splunk search and visualization |
| **Recover**  | RC.IM-1        | Recovery planning and improvements   | Post-alert response workflows captured via SOAR (can be extended) |

---

## 🧩 Additional Notes

- The **Detect** and **Respond** functions are most fully implemented in this lab.
- SOAR playbooks enable simulation of automated incident response — fulfilling the **Respond** function.
- Integration with tools like Nessus or OSQuery could further strengthen **Identify** and **Protect** mappings.

---

## 🔗 References

- [NIST CSF Official Guide (v1.1)](https://nvlpubs.nist.gov/nistpubs/

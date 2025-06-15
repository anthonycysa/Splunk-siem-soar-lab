
# MITRE ATT&CK Mapping for Splunk SIEM Detection

This document maps simulated detection use cases within the Splunk SIEM and SOAR lab to the MITRE ATT&CK framework. MITRE ATT&CK (Adversarial Tactics, Techniques, and Common Knowledge) is a globally-accessible knowledge base of adversary tactics and techniques based on real-world observations.

## 🎯 Use Case Coverage

| Detection Use Case               | MITRE ATT&CK Tactic | MITRE Technique ID | Description                                  |
|----------------------------------|----------------------|--------------------|----------------------------------------------|
| Suspicious PowerShell Execution | Execution            | T1059.001          | PowerShell used for command execution        |
| Unusual Login Times              | Initial Access       | T1078              | Valid accounts used at anomalous hours       |
| Brute Force Login Attempt        | Credential Access    | T1110              | Brute force attempts against login portals   |
| Malicious File Download          | Command and Control  | T1105              | Remote file transfer from attacker server    |
| DNS Tunneling Detection          | Exfiltration         | T1048.003          | Data exfiltration via DNS                    |
| Registry Key Persistence         | Persistence          | T1547.001          | Registry run key added for persistence       |

## 🛠️ Splunk Implementation

Each detection corresponds to a Splunk search query or correlation rule within the SIEM:

- **PowerShell Execution**:
  ```spl
  index=win_logs sourcetype=WinEventLog:Security EventCode=4104 
  | search CommandLine="*Invoke*" OR CommandLine="*IEX*"
  ```

- **Brute Force Detection**:
  ```spl
  index=auth_logs sourcetype=linux_secure OR sourcetype=WinEventLog:Security
  | stats count by src_ip, user, status
  | where count > 10 AND status="failed"
  ```

- **DNS Tunneling**:
  ```spl
  index=dns_logs 
  | stats count by query 
  | where count > 100 AND like(query, "%.%.%.%")
  ```

## 📌 Notes

This mapping is part of a simulated lab environment designed to demonstrate how Splunk can detect a variety of attacker behaviors using the MITRE ATT&CK framework. It helps SOC analysts and blue teamers practice real-world detection logic aligned to a globally recognized standard.

For more on MITRE ATT&CK, visit: https://attack.mitre.org/


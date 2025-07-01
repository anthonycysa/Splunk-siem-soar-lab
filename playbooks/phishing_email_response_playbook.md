# Phishing Email Response - SOAR Playbook

## Objective
Detect and respond to phishing email activity using automated SOAR actions triggered by SIEM alerts.

---

## Trigger
- Splunk alert for suspicious email activity:
  - Subject contains keywords (e.g., “Invoice”, “Urgent”, “Account Suspension”)
  - Attachment or link flagged by email gateway
  - User-reported phishing email (via internal ticket)

---

## Automated Workflow Steps

1. **Trigger: Phishing Alert Ingested**
   - Source: Splunk (via email gateway or user report)
   - Severity: Medium–High

2. **Enrichment: Email Header & URL Analysis**
   - Action: Extract header, domain, and links
   - Use AbuseIPDB, VirusTotal, or URLhaus to check IOC reputation

3. **Attachment/Link Scan**
   - Action: Run hash or sandbox scan on attachments/URLs
   - Simulated via threat intelligence platform (mock)

4. **User Lookup**
   - Action: Identify the user who received the email
   - Correlate login patterns or endpoint alerts (Splunk search)

5. **Containment**
   - Action: Quarantine email (simulated)
   - Optional: Isolate endpoint or block malicious domain/IP

6. **Notification**
   - Action: Notify SOC team with full context
   - Includes user, sender, subject, scan results, actions taken

7. **Ticket Creation**
   - Action: Open case in ServiceNow/JIRA (mock)
   - Attach IOC evidence, results, and response actions

---

## MITRE ATT&CK Mapping
- **T1566.001** – Phishing: Spearphishing Attachment
- **T1566.002** – Phishing: Spearphishing Link
- **T1059** – Command and Scripting Interpreter (if link executes payload)

---

## Notes
- This is a simulated playbook for portfolio/demo purposes.
- No real integrations with email systems or threat intel feeds were used.

# Brute Force Login Attempt - SOAR Playbook

## Objective
Automatically detect and respond to brute force login attempts using Splunk SOAR.

---

## Trigger
- Multiple failed login attempts from a single IP within a short time window.
- Splunk correlation rule: `Brute Force Detection` fired.

---

## Automated Workflow Steps

1. **Trigger: Alert Ingested**
   - Source: Splunk (via notable event)
   - Alert Type: Brute Force Attempt

2. **Enrichment: IP Reputation Lookup**
   - Action: `lookup_ip` via VirusTotal or AbuseIPDB
   - Outcome: Gather threat reputation, geolocation, ASN info.

3. **Contextual Check: Internal vs External IP**
   - Action: Check if IP belongs to internal network range
   - Decision:
     - If Internal: Flag for internal review
     - If External: Continue

4. **Containment: Temporary IP Block**
   - Action: Trigger firewall or EDR to block IP (simulated)
   - Tool: Mock action with `block_ip` function

5. **Notification: Alert SOC Team**
   - Action: Send Slack/Email notification
   - Content: IP address, hostname, user, time, severity

6. **Case Management: Ticket Creation**
   - Action: Create case in ticketing system (e.g., ServiceNow)
   - Status: Opened with enrichment details and actions taken

7. **Post-Incident Report**
   - Action: Auto-generate and attach summary to the case

---

## MITRE ATT&CK Mapping
- **T1110** – Brute Force
- **T1078** – Valid Accounts
- **T1566.002** – Spearphishing Link (if credential phishing observed)

---

## Notes
- This is a simulated playbook for portfolio demonstration.
- No real environment integrations or live blocking actions.

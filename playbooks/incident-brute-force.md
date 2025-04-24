# Playbook: Incident Response - Brute Force Attack

## 🧩 Incident Type
Unauthorized access attempt via RDP brute force

---

## 🚨 Detection
- Wazuh Alert triggered from agent: `win-victim`
- Rule ID: 18107 (Windows Logon Failed - 4625)

---

## 🧭 Response Steps

### 🔍 1. Triage
- Confirm alert from Wazuh
- Check for repeated Event ID 4625 in logs
- Identify source IP of failed attempts

### 🛡️ 2. Containment
- Block source IP: `10.0.0.Y` via pfSense or Windows Firewall
- Isolate affected endpoint if compromise is suspected

### 📦 3. Evidence Collection
- Export Windows Event Logs (Security)
- Capture Wazuh alert snapshot
- Tag related logs in SIEM

### 📝 4. Reporting
- Create JIRA ticket with timeline, logs, and root cause
- Notify stakeholders if the attempt was sustained or near-successful

---

## 🔁 Lessons Learned
- Brute force detection was successful via built-in rules
- Consider enabling account lockout policies
- Monitor for lateral movement if credentials were compromised

---

## 📁 Artifacts
- Alert JSON: [alerts/brute-force-alert.json](../alerts/brute-force-alert.json)
- Detection Rule ID: 18107

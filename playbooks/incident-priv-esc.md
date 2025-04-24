# Playbook: Incident Response - Privilege Escalation

## 🧩 Incident Type
Potential local privilege escalation on a Windows system

---

## 🚨 Detection
- Wazuh alert from suspicious MSI installation
- Rule ID: 95007

---

## 🧭 Response Steps

### 🔍 1. Triage
- Determine method of MSI execution
- Confirm privilege gain if possible

### 🛡️ 2. Containment
- Revoke admin rights
- Isolate system

### 📦 3. Evidence Collection
- MSI file
- PowerShell logs
- Wazuh syscheck logs

### 📝 4. Report & Review
- Log incident in tracker
- Patch known vuln (e.g., AlwaysInstallElevated)

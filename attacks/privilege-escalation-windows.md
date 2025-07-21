# Attack Simulation: Windows Privilege Escalation

##  Objective
Simulate a local privilege escalation attempt using known misconfigurations (e.g. AlwaysInstallElevated).

---

##  Lab Setup
- **Target**: Windows 11 VM (domain-joined)
- **Tool**: winPEAS / PowerUp.ps1

---

##  Execution
1. Upload and run enumeration script
2. Identify AlwaysInstallElevated enabled
3. Craft malicious MSI and escalate to SYSTEM

---

##  Detection
- Script execution via PowerShell (Event ID 4104)
- Scheduled task creation or service install
- Wazuh rule: suspicious MSI execution

---

##  Lessons
- Least privilege principle
- Disable AlwaysInstallElevated via GPO
- Use AppLocker or Defender Application Control

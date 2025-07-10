# Custom Detections

This section documents custom detection rules implemented in the Wazuh SOC Lab environment. These detections enhance visibility into suspicious activity based on Windows Sysmon logs and other log sources.

## Included Rules

- **Sysmon Event ID 1 (Process Creation):**
  - Detects and logs all process creation events from Windows agents.
  - Rule ID: `100105`
  - MITRE ATT&CK: T1059.003 – Windows Command Shell

- **Winword launching PowerShell:**
  - Detects suspicious behavior where `winword.exe` spawns `powershell.exe`.
  - Rule ID: `100100`
  - MITRE ATT&CK: T1059 (Command and Scripting Interpreter), T1204 (User Execution)

Each detection includes the rule logic, alert behavior, and expected use cases.


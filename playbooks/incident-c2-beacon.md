# Playbook: Incident Response - C2 Beaconing

## 🧩 Incident Type
Suspected beaconing behavior detected from endpoint

---

## 🚨 Detection
- Rule ID: 96543
- Netstat logs + PowerShell command monitoring

---

## 🧭 Response Steps

### 🔍 1. Investigate
- Confirm periodic outbound connections
- Identify process/user initiating traffic

### 🛡️ 2. Containment
- Kill process and isolate endpoint
- Disable network interface if necessary

### 📊 3. Intelligence Gathering
- Examine destination IP logs
- Perform WHOIS and VirusTotal check

### 📝 4. Lessons
- Create detection rules for scheduled traffic
- Audit firewall egress policies

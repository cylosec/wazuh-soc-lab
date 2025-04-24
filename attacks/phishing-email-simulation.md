# Attack Simulation: Credential Harvesting via Phishing Email

## 🎯 Objective
Simulate a phishing email campaign with a fake login page to test email filtering and user awareness.

---

## 🧪 Lab Setup
- **Attacker**: Kali Linux with GoPhish and Nginx
- **Phishing Domain**: `sbaycenter.it.com`
- **Payload**: Fake password reset page (`/portal`)
- **User Target**: Windows 11 user on lab domain

---

## 🛠️ Execution
1. Launch GoPhish campaign using spoofed email
2. Monitor clicks and credential submissions
3. Capture requests to phishing domain

---

## 📈 Detection
- Wazuh HTTP logs showing inbound phishing page access
- Event logs if user submits credentials via Edge/Chrome
- Alert for outbound traffic to unusual domain

---

## 📘 Lessons
- Implement SPF, DKIM, DMARC
- Enable browser extensions for phishing protection
- Train users to report suspicious emails

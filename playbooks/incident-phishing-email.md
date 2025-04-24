# Playbook: Incident Response - Phishing Email Click

## 🧩 Incident Type
User clicked on a phishing email and accessed a fake login page

---

## 🚨 Detection
- Wazuh HTTP log monitoring
- Alert Rule ID: 92001 (Phishing link accessed)

---

## 🧭 Response Steps

### 🔍 1. Triage
- Identify user and system involved
- Validate if credentials were submitted

### 🛡️ 2. Containment
- Block phishing domain at DNS or perimeter
- Notify user to reset credentials

### 🧪 3. Investigation
- Review email headers and original message
- Trace any lateral movement attempts

### 📝 4. Reporting
- File incident report
- Update phishing awareness training

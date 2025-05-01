# SOC Lab Deployment: Wazuh SIEM Stack

## Overview
This project documents the successful deployment, troubleshooting, and upgrade of a hybrid Security Operations Center (SOC) lab using the Wazuh SIEM stack. The environment simulates real-world detection, response, and centralized logging across both Linux and macOS systems.

## Objectives
- Deploy Wazuh Manager, OpenSearch Indexer, and Wazuh Dashboard
- Integrate a macOS agent (Intel iMac) into the SIEM
- Secure the platform using TLS and role-based access control (RBAC)
- Resolve version mismatches and configuration issues
- Present the build as a portfolio-ready SOC lab

## Environment
- **Manager/Indexer/Dasbhoard**: Ubuntu Server 22.04
- **Agent**: macOS Intel iMac
- **SIEM Stack**: Wazuh 4.11.2, OpenSearch 2.16.0, Dashboard 2.16.0

---

## Implementation Summary

### 1. Deploy Core SIEM Components
- Installed Wazuh Manager and OpenSearch Indexer
- Installed Wazuh Dashboard with SSL support
- Configured Dashboard at `https://10.0.0.229:8443`

### 2. Add and Enroll Agent (iMac)
- Downloaded and installed Wazuh agent `.pkg` on macOS
- Retrieved agent key from manager
- Successfully enrolled iMac as Agent ID `003`

### 3. Secure the Stack with Custom RBAC
- Created user `cylo-admin` in `internal_users.yml`
- Hashed password and applied via `securityadmin.sh`
- Assigned `kibana_user` role using OpenSearch Security API

### 4. Troubleshoot Version Incompatibilities
- Identified mismatch: Dashboard 2.16.0 vs. Indexer 2.8.0
- Upgraded Wazuh Indexer to 2.16.0
- Restarted services to sync the stack

### 5. Resolve Dashboard Login and Routing Issues
- Removed invalid route: `/app/wazuh`
- Set `defaultRoute: /app/discover`
- Verified Dashboard loads and agent metrics display

---

## Sample Issues Logged (Jira-style)
| Task | Status |
|------|--------|
| Deploy Wazuh Stack | ☑️ Done |
| Install iMac Agent | ☑️ Done |
| Add cylo-admin User with RBAC | ☑️ Done |
| Fix Version Mismatch | ☑️ Done |
| Restore Dashboard Access | ☑️ Done |
| Validate iMac Visibility | ☑️ Done |

---

## Technologies Used☑️
- **Wazuh**: Open-source SIEM and XDR
- **OpenSearch**: Indexer for alerts and logs
- **Jira**: Project tracking (CSV Import format)
- **GitHub**: Portfolio publishing

---

## Next Steps
- Integrate with Sigma or MITRE ATT&CK rule sets
- Add a pfSense VM for gateway and firewall logs
- Build alert triggers and response playbooks
- Automate agent enrollment via Ansible or shell scripts

---

## Author
**Cylo**  
Cybersecurity Lab Architect | Blue Team Engineer  
🖥️ support@sbaycenter.it.com

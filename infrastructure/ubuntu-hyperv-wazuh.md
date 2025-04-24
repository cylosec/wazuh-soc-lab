# Ubuntu Hyper-V Wazuh Manager Setup

## Hyper-V VM Specs
- OS: Ubuntu Server 22.04 LTS
- vCPU: 2
- RAM: 8GB
- Network: Connected to internal vSwitch

## Installation Steps
1. Download Ubuntu ISO and create VM on Hyper-V
2. Install Wazuh Manager using Wazuh installation script
3. Open required ports (1514, 1515, 9200, 55000)
4. Configure ossec.conf and validate agent connection

# Custom Sysmon Alert: Event ID 1 - Process Creation

## Overview
This document records the creation and successful implementation of a 
custom Wazuh rule to detect process creation events on a Windows endpoint 
using Sysmon Event ID 1.

## Rule Configuration
The following rule was added to `/var/ossec/etc/rules/local_rules.xml`:

```xml
<group name="sysmon_process_creation">
  <rule id="100105" level="7">
    <if_sid>92052</if_sid>
    <field name="winlog.event_id">1</field>
    <description>Custom Alert: Process created on Windows endpoint (Sysmon 
Event ID 1)</description>
    <mitre>
      <id>T1059.003</id>
    </mitre>
  </rule>
</group>


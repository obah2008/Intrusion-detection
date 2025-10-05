# Intrusion-detection
A lab project that uses Suricata to detect simulated attacks, ships alerts to Splunk for analysis, and automates safe response actions.

## Contents
- Suricata Setup
- Splunk Setup/log forwarding
- Attack Simulation (Atomic Red Team)
- automated alerting via Python
- Response Automation



## Objectives
- Configure Suricata to inspect and log endpoint network traffic.
- Forward Suricata’s EVE.JSON logs to Splunk for analysis and visualization.
- Write and tune custom Suricata rules to detect Atomic Red Team attack techniques.
- Validate detections against the MITRE ATT&CK framework.
- Build Splunk dashboards and alerts for better visibility.
- Implement basic automated responses to detections.

## Lab Setup
This lab is built on a single VM architecture, a single Ubuntu machine run on VMware

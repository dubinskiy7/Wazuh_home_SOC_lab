# Wazuh_home_SOC_lab
# 🛡️ Wazuh Home SOC Lab

## End-to-End Security Monitoring Lab

A hands-on cybersecurity project demonstrating the deployment, configuration, and integration of open-source security tools into a centralized **SIEM/XDR, firewall logging, endpoint monitoring, threat-intelligence, and network IDS environment**.

---

## 📌 About the Project

This project demonstrates the deployment and configuration of a small **Security Operations Center (SOC)** environment built in **Oracle VirtualBox**.

**Wazuh** is used as the central SIEM/XDR platform, with a Windows endpoint providing **Sysmon telemetry and File Integrity Monitoring (FIM)**, **VirusTotal** providing threat-intelligence enrichment, **pfSense** providing firewall logs, and **Suricata** providing network IDS alerts.

**Kali Linux** is used as a controlled traffic-generation system for testing and validating detections.

The main goal of the lab is to build a complete security monitoring pipeline:

**Endpoint Activity → Network Telemetry → Wazuh Analysis → Security Alerts**

---

## 🛠️ Security Infrastructure & Tech Stack

- **SIEM / XDR:** [Wazuh](https://wazuh.com/) — centralized log collection, endpoint monitoring, FIM, alerting, and analysis.
- **Endpoint Telemetry:** [Sysmon](https://learn.microsoft.com/sysinternals/downloads/sysmon) — detailed Windows process, network, and system activity.
- **Threat Intelligence:** [VirusTotal](https://www.virustotal.com/) — file-hash reputation enrichment for monitored files.
- **Firewall / Routing:** [pfSense](https://www.pfsense.org/) — firewall management and remote syslog forwarding.
- **Network IDS:** [Suricata](https://suricata.io/) — signature-based network threat detection using Emerging Threats rules and a custom ICMP rule.
- **Traffic Generation:** Kali Linux — controlled traffic used for detection testing.
- **Virtualization:** Oracle VirtualBox.
- **Monitored Endpoint:** Windows 11 Pro.
- **SIEM Server:** Ubuntu Server.

---

## ✨ Key Features & Implementations

- ☑ **Centralized Monitoring:** Deployed Wazuh Manager, Indexer, Dashboard, and Filebeat on Ubuntu Server.
- ☑ **Windows Endpoint Enrollment:** Connected a Windows 11 endpoint to the Wazuh Manager.
- ☑ **Sysmon Ingestion:** Forwarded the `Microsoft-Windows-Sysmon/Operational` event channel into Wazuh.
- ☑ **File Integrity Monitoring:** Monitored selected Windows directories for file creation, modification, and deletion.
- ☑ **VirusTotal Integration:** Enriched FIM events with file reputation data and VirusTotal permalinks.
- ☑ **pfSense Syslog Integration:** Forwarded firewall logs to Wazuh over **UDP/514**.
- ☑ **Custom pfSense Parsing:** Added a custom decoder and custom Wazuh rules for pfSense events.
- ☑ **Suricata IDS Integration:** Forwarded Suricata `eve.json` alerts from the Windows endpoint into Wazuh.
- ☑ **Emerging Threats Rules:** Loaded the `emerging-all.rules` ruleset for signature-based detection.
- ☑ **Custom Detection Rule:** Created a custom ICMP Suricata rule for predictable end-to-end testing.
- ☑ **Threat Hunting:** Verified Suricata and endpoint alerts inside the Wazuh dashboard.

---

## 📁 Project Documentation

For the complete step-by-step setup, configuration details, screenshots, testing, and project documentation:

👉 **[View Full Project Report (PDF)](./Wazuh_SOC_Home_Lab_Project.pdf)**

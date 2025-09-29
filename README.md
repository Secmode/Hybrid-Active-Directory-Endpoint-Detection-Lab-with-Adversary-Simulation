# Hybrid Active Directory Security Lab with Microsoft Defender for Endpoint and Splunk Integration
## Overview
This project simulates a real-world Security Operations Center (SOC) environment. It integrates Windows Server 2022 (Active Directory), Windows 10 endpoint protection via Microsoft Defender for Endpoint (Cloud), Splunk SIEM on Ubuntu, pfSense firewall for network segmentation, and Kali Linux for adversary simulation. Demonstrate the end-to-end deployment and integration of identity, endpoint detection, hybrid cloud, and centralized log monitoring to support modern security operations.



---

## 🔹 Skills & Tasks Demonstrated  
The lab covers a wide range of **SOC (Security Operations Center)**, including:

<p float="left">  
<code>Hybrid SOC Architecture Design</code> &nbsp;&nbsp; | &nbsp;&nbsp; <code>Active Directory & Identity Management</code> &nbsp;&nbsp; | &nbsp;&nbsp; <code>Endpoint Protection (EDR) & Cloud Onboarding</code> &nbsp;&nbsp; | &nbsp;&nbsp; <code>Firewall Configuration & Network Segmentation</code> &nbsp;&nbsp; | &nbsp;&nbsp; <code>SIEM Log Ingestion & SPL Querying</code> &nbsp;&nbsp; | &nbsp;&nbsp; <code>Adversary Simulation with Kali Linux</code> &nbsp;&nbsp; | &nbsp;&nbsp; <code>Incident Detection & Response Workflow</code> &nbsp;&nbsp; | &nbsp;&nbsp; <code>Advanced Threat Hunting</code> &nbsp;&nbsp; | &nbsp;&nbsp; <code>Monitoring & Troubleshooting</code>  | &nbsp;&nbsp; <code>Technical Documentation & Visualization</code>  
</p>
</p>


---


---

## Lab Network Architecture

| Component | Role | IP |
|-----------|------|----|
|pfSense Firewall	 | DHCP, NAT, firewall rules, internet gateway	 |192.168.0.1/24 |
| Windows Server 2022 | Domain Controller (AD DS, DNS, GPOs, OU management) | 192.168.0.16/24 |
|Windows 11 Endpoint | Domain-joined client with Defender agent onboarded| 192.168.0.100/24 |
| Ubuntu Server | Splunk SIEM (receives logs from Windows and pfSense) |192.168.0.14/24 |
|Kali Linux VM | Attacker box for brute force, lateral movement, phishing | 192.168.0.13/24 |
|Defender Cloud Portal | Cloud-based alerting and hunting (via HTTPS)	 | External (cloud) |
|SocAnalyst |SIEM analysis, running SPL queries, EDR portal, monitoring alerts | 10.0.0.2/24 |

**Tools Used:** VirtualBox, Microsoft 365 Defender Portal EDR (Cloud), Sysmon, Splunk Universal Forwarder, SPL (Search Processing Language), Advanced Hunting (KQL), Hydra, Metasploit Framework, EICAR Test File, draw.io / diagrams.net
<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/c607fa31-cbc6-45d6-8f48-4cefea799f11" />

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

## 🧱 Lab Architecture Overview

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
## Step-by-Step Setup
---

## Oracle VM VirtualBox lab with pfSense managing VM traffic
**I configured pfSense as the network gateway to manage all VM traffic, setting firewall rules to allow only web traffic (HTTP/HTTPS), enforce DNS resolution through pfSense, block all other traffic, and monitor connected devices via the DHCP leases dashboard.**
<img width="1414" height="655" alt="image" src="https://github.com/user-attachments/assets/e78949a1-763c-4c9a-a889-6f1d2b6ad843" />
<img width="1225" height="734" alt="image" src="https://github.com/user-attachments/assets/57c282ea-65a5-4d67-a720-5d7ed0b77bb5" />
<img width="1600" height="731" alt="image" src="https://github.com/user-attachments/assets/da9fecb8-041e-4901-81b1-c80d7f15c89d" />

## Active Directory Configuration
**Configured Active Directory in Windows Server 2022 by installing AD DS, creating Organizational Units (Sales, IT, Customer Service), adding users, and joining a Windows 10 VM to the domain, with screenshots showing installation, OU structure, and domain join confirmation.**
<img width="1845" height="744" alt="image" src="https://github.com/user-attachments/assets/373b6663-63e2-4e4d-9d23-e40b17ffc6f1" />
<img width="1874" height="1065" alt="image" src="https://github.com/user-attachments/assets/5bee0b04-c223-42aa-86ea-44a32bccc18b" />
<img width="1290" height="917" alt="image" src="https://github.com/user-attachments/assets/063ac0ac-3b5a-4fea-91a9-0f2b66d3ff25" />
<img width="1069" height="631" alt="image" src="https://github.com/user-attachments/assets/49310cc4-8fa9-4bb6-9ded-72e182d3a8ab" />
<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/8b0b0599-90cc-4997-bcdc-90a385090a8f" width="300"/></td>
    <td><img src="https://github.com/user-attachments/assets/91ad78ef-c672-460e-824b-66e66d0f9b8c" width="300"/></td>
    <td><img src="https://github.com/user-attachments/assets/b963dd40-f56a-491c-a535-45556b26cd88" width="300"/></td>
  </tr>
</table>
``
<img width="1511" height="815" alt="image" src="https://github.com/user-attachments/assets/8e38394b-9ed0-42f2-bc8d-1bb24b192d83" />


===============================================================================================














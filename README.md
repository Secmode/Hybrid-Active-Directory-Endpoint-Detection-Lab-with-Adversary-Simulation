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
## Oracle VM VirtualBox lab Step-by-Step Setup
---
<img width="1414" height="655" alt="image" src="https://github.com/user-attachments/assets/e78949a1-763c-4c9a-a889-6f1d2b6ad843" />


</details>

<details>
<summary>VM Network traffic Managment</summary>

## FfSense managing VM traffic
**I configured pfSense as the network gateway to manage all VM traffic, setting firewall rules to allow only web traffic (HTTP/HTTPS), enforce DNS resolution through pfSense, block all other traffic, and monitor connected devices via the DHCP leases dashboard.**
<img width="1628" height="910" alt="image" src="https://github.com/user-attachments/assets/63b5c52c-b7eb-499b-a857-d1ff6d2b3672" />
<img width="1225" height="734" alt="image" src="https://github.com/user-attachments/assets/57c282ea-65a5-4d67-a720-5d7ed0b77bb5" />
<img width="1600" height="731" alt="image" src="https://github.com/user-attachments/assets/da9fecb8-041e-4901-81b1-c80d7f15c89d" />

</details>

</details>

<details>
<summary>Window Server  and Entra ID setup</summary>

## Active Directory Configuration
**Configured Active Directory in Windows Server 2022 with DNS and hybrid management, creating OUs, users, joining a Windows 10 VM to the domain, and syncing all users to Entra ID., with screenshots showing installation, syn structure, and domain join confirmation.**
<img width="1845" height="744" alt="image" src="https://github.com/user-attachments/assets/373b6663-63e2-4e4d-9d23-e40b17ffc6f1" />
<img width="1874" height="1065" alt="image" src="https://github.com/user-attachments/assets/5bee0b04-c223-42aa-86ea-44a32bccc18b" />
<img width="1290" height="917" alt="image" src="https://github.com/user-attachments/assets/063ac0ac-3b5a-4fea-91a9-0f2b66d3ff25" />
<img width="1127" height="544" alt="Screenshot 2025-09-27 152707" src="https://github.com/user-attachments/assets/180a2550-efc4-41d9-abc7-5219be70bd09" />
<img width="1069" height="631" alt="image" src="https://github.com/user-attachments/assets/49310cc4-8fa9-4bb6-9ded-72e182d3a8ab" />
<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/8b0b0599-90cc-4997-bcdc-90a385090a8f" width="300"/></td>
    <td><img src="https://github.com/user-attachments/assets/91ad78ef-c672-460e-824b-66e66d0f9b8c" width="300"/></td>
    <td><img src="https://github.com/user-attachments/assets/b963dd40-f56a-491c-a535-45556b26cd88" width="300"/></td>
  </tr>
</table>
``
<img width="1502" height="503" alt="Screenshot 2025-09-29 233948" src="https://github.com/user-attachments/assets/18331d47-70ba-4836-b9af-aabb17123d1f" />
<img width="1901" height="863" alt="Screenshot 2025-09-28 105800" src="https://github.com/user-attachments/assets/e2807452-253e-4456-97ae-6d259aed96bc" />

<img width="1892" height="873" alt="Screenshot 2025-09-28 105931" src="https://github.com/user-attachments/assets/00cb5cd2-07d2-418d-91f2-d21cf7a0720a" />
<img width="1511" height="815" alt="image" src="https://github.com/user-attachments/assets/8e38394b-9ed0-42f2-bc8d-1bb24b192d83" />
<img width="1710" height="1011" alt="Screenshot 2025-09-29 210133" src="https://github.com/user-attachments/assets/b28a6cf8-8a42-4f31-8184-893bd1de12b6" />

</details>

</details>

<details>
<summary>SIEM Setup</summary>

## Splunk SIEM Setup
**Installed and configured Splunk SIEM with Splunk on Ubuntu Server, Universal Forwarder on Windows machines, and configured inputs for Security, System, Sysmon, Microsoft Defender, pfSense, Microsoft-Windows-Sense/Operational, and Application logs.**
<img width="1714" height="879" alt="Screenshot 2025-09-26 204850" src="https://github.com/user-attachments/assets/70a80229-2e11-41c2-9191-360ba6e52d3f" />
<img width="873" height="666" alt="Screenshot 2025-09-26 235313" src="https://github.com/user-attachments/assets/771cca41-cccf-4457-8fc6-4dfa2ddc5fc0" />
<img width="1085" height="699" alt="image" src="https://github.com/user-attachments/assets/25718baf-218a-4352-ac09-b6c0542e4543" />
<img width="1587" height="868" alt="Screenshot 2025-09-27 150338" src="https://github.com/user-attachments/assets/b3e3121c-8597-4131-acbf-3970634707fa" />
<img width="1189" height="850" alt="Screenshot 2025-09-27 121554" src="https://github.com/user-attachments/assets/65b1eb8f-9d07-4542-b7d4-46558df2f17b" />
<img width="1023" height="423" alt="image" src="https://github.com/user-attachments/assets/fb33b45b-b033-4c0c-9602-bec48fd23226" />
<img width="948" height="666" alt="image" src="https://github.com/user-attachments/assets/ae59981e-b43b-4d64-8bdd-d037c4d51944" />
<img width="721" height="646" alt="Screenshot 2025-09-28 144334" src="https://github.com/user-attachments/assets/d5d0502e-3a35-441d-9cce-5367bbd3de36" />
<img width="1887" height="662" alt="image" src="https://github.com/user-attachments/assets/53fa8d68-f8c7-4390-8d03-591a4abab5a1" />
<img width="1921" height="628" alt="Screenshot 2025-09-28 151148" src="https://github.com/user-attachments/assets/16fc8969-3c3c-4a1a-ac88-5d5454507d99" />
<img width="1903" height="504" alt="Screenshot 2025-09-28 151431" src="https://github.com/user-attachments/assets/1f382d40-e7b0-43e3-8df7-e33667177352" />

</details>

</details>

<details>
<summary>EDR Setup </summary>

## Microsoft Defender for Endpoint Integration
**Integrated Microsoft Defender for Endpoint by activating a Defender Plan 2 trial, onboarding a Windows 10 device using a local script, and validating the device in the Defender portal, documented with screenshots.**
<img width="1557" height="832" alt="Screenshot 2025-09-28 112110" src="https://github.com/user-attachments/assets/85fd1ca9-4c39-4810-92fb-480223150d5e" />
<img width="1898" height="913" alt="Screenshot 2025-09-28 121451" src="https://github.com/user-attachments/assets/eca4bfea-1362-42d3-a6f2-d2406c3cd107" />
<img width="1896" height="846" alt="Screenshot 2025-09-28 121655" src="https://github.com/user-attachments/assets/abedf677-2ac2-49e2-be0d-640e137f6c6c" />
<img width="1328" height="784" alt="Screenshot 2025-09-28 123116" src="https://github.com/user-attachments/assets/87b0b30b-c6e0-4c89-8eb4-d564e3e065e6" />
<img width="1685" height="813" alt="Screenshot 2025-09-28 123748" src="https://github.com/user-attachments/assets/e94acfac-3b7d-4fb3-ad2a-0bb713822c52" />
<img width="1900" height="720" alt="Screenshot 2025-09-28 124637" src="https://github.com/user-attachments/assets/fc360059-45ba-49c3-a4a7-a45f2252cfeb" />
<img width="1517" height="984" alt="Screenshot 2025-09-28 143205" src="https://github.com/user-attachments/assets/1ca43be0-50d6-4da4-8b29-6715c6ea42ea" />
<img width="1103" height="619" alt="Screenshot 2025-09-28 140906" src="https://github.com/user-attachments/assets/137c4b1d-0e79-422b-94d7-530ed08fffe0" />

</details>




























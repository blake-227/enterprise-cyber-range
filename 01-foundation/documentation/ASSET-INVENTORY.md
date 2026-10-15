\# Enterprise Cyber Range Asset Inventory



\## Project 1 - Core Cyber Range Foundation



This document tracks the systems currently deployed inside the enterprise cyber range.



| Asset | Operating System | IP Address | Role | Network | Status |

|---|---|---|---|---|---|

| Host Laptop | Windows 11 | 10.10.10.1 | VMware Host | VMnet2 | Active |

| KP-SOC01 | Kali Purple | 10.10.10.10 | SOC / Blue Team Workstation | VMnet2 | Active |

| WIN11-USER01 | Windows 11 Pro | 10.10.10.20 | Employee Workstation | VMnet2 | Active |

| UBUNTU-SRV01 | Ubuntu Server | 10.10.10.30 | Linux Enterprise Server | VMnet2 | Active |



\## Current Services



\### KP-SOC01

Kali Purple security workstation used for network analysis, threat hunting, incident response, detection engineering, and future purple team operations.



\### WIN11-USER01

Simulated employee workstation. Microsoft Defender and Windows Firewall are enabled.



Future monitoring will include Sysmon and centralized log collection.



\### UBUNTU-SRV01

Linux server currently running SSH on TCP port 22.



Additional server services will be introduced during future projects.



\## Network



Network Name: VMnet2



Network Type: Host-only



Subnet: 10.10.10.0/24



Internet Access: Disabled



DHCP: Disabled



Addressing: Static



\## Current Security Baseline



The environment is isolated from the Internet.



Windows Defender Firewall remains enabled.



Microsoft Defender remains enabled.



Ubuntu SSH is the currently approved remotely accessible server service.



Network reconnaissance was performed from KP-SOC01 to establish the initial host and service baseline.



All three virtual machines have a P1-CLEAN-BASELINE VMware snapshot.


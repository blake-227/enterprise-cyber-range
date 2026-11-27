<div align="center">



\# Enterprise Cyber Range



\### Enterprise Security Engineering | Red Team | Blue Team | Purple Team



An evolving enterprise cybersecurity environment designed to simulate real-world infrastructure, security operations, adversary emulation, cloud security, and automated defense.



!\[Status](https://img.shields.io/badge/Status-Active%20Development-success?style=for-the-badge)

!\[Projects](https://img.shields.io/badge/Projects-1%20%2F%20100-blue?style=for-the-badge)

!\[Phase](https://img.shields.io/badge/Phase-Foundation-purple?style=for-the-badge)



\---



!\[Kali](https://img.shields.io/badge/Kali%20Purple-557C94?style=flat-square\&logo=kalilinux\&logoColor=white)

!\[VMware](https://img.shields.io/badge/VMware-607078?style=flat-square\&logo=vmware\&logoColor=white)

!\[Windows](https://img.shields.io/badge/Windows-0078D6?style=flat-square)

!\[Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat-square\&logo=ubuntu\&logoColor=white)

!\[Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square)

!\[Python](https://img.shields.io/badge/Python-3776AB?style=flat-square\&logo=python\&logoColor=white)



\[Overview](#overview) •

\[Architecture](#architecture) •

\[Roadmap](#development-roadmap) •

\[Projects](#project-directory) •

\[Technology](#technology-stack)



</div>



\---



\## Overview



The Enterprise Cyber Range is a hands-on cybersecurity engineering environment built to replicate the infrastructure and security operations of a modern organization.



Rather than completing disconnected security labs, each project contributes to a larger enterprise environment.



The objective is to build, secure, monitor, assess, investigate, and continuously improve the same infrastructure through increasingly complex security exercises.



\### Core Objectives



| Domain | Objective |

| :--- | :--- |

| Blue Team | Security monitoring, threat hunting, and incident response |

| Red Team | Authorized penetration testing and adversary emulation |

| Purple Team | Detection validation and security control improvement |

| Cloud Security | Secure Azure infrastructure and cloud threat detection |

| Identity Security | Identity lifecycle, access governance, and privileged access |

| Detection Engineering | Develop, test, and automate security detections |

| DevSecOps | Integrate security into infrastructure and software deployment |

| Security Infrastructure | Enterprise networking, segmentation, and system hardening |



\---



\## Architecture



\### Current Environment



```mermaid

flowchart TD

&#x20;   HOST\["Windows Host | VMware Workstation"]

&#x20;   NET\["VMnet2 | 10.10.10.0/24"]



&#x20;   HOST --> NET



&#x20;   NET --> KP\["KP-SOC01<br/>Kali Purple<br/>10.10.10.10"]

&#x20;   NET --> WIN\["WIN11-USER01<br/>Windows 11<br/>10.10.10.20"]

&#x20;   NET --> UB\["UBUNTU-SRV01<br/>Ubuntu Server<br/>10.10.10.30"]



&#x20;   style KP fill:#6741a5,color:#fff

&#x20;   style WIN fill:#0078d4,color:#fff

&#x20;   style UB fill:#c74618,color:#fff

```



The current environment operates within a VMware host-only network using static IP addressing and no Internet gateway.



\[View detailed network architecture](architecture/FOUNDATION-TOPOLOGY.md)



\### Target Enterprise Architecture



```mermaid

flowchart TD

&#x20;   CORE\["Enterprise Cyber Range"]



&#x20;   CORE --> INFRA\["Enterprise Infrastructure"]

&#x20;   CORE --> CLOUD\["Cloud and Identity"]

&#x20;   CORE --> SOC\["Security Operations"]



&#x20;   INFRA --> FW\["pfSense"]

&#x20;   INFRA --> AD\["Active Directory"]

&#x20;   INFRA --> END\["Windows / Linux"]



&#x20;   CLOUD --> AZ\["Microsoft Azure"]

&#x20;   CLOUD --> IAM\["Entra ID / IAM"]

&#x20;   CLOUD --> AKS\["Kubernetes / AKS"]



&#x20;   SOC --> KP\["Kali Purple"]

&#x20;   SOC --> SIEM\["SIEM / EDR"]

&#x20;   SOC --> NSM\["Network Monitoring"]



&#x20;   CORE --> RED\["Red Team"]

&#x20;   CORE --> BLUE\["Blue Team"]

&#x20;   CORE --> PURPLE\["Purple Team"]



&#x20;   RED --> VALIDATE\["Security Validation"]

&#x20;   BLUE --> VALIDATE

&#x20;   PURPLE --> VALIDATE



&#x20;   VALIDATE --> AUTO\["Automation and Detection Engineering"]



&#x20;   style RED fill:#991b1b,color:#fff

&#x20;   style BLUE fill:#1d4ed8,color:#fff

&#x20;   style PURPLE fill:#7e22ce,color:#fff

&#x20;   style CLOUD fill:#0369a1,color:#fff

```



The target architecture represents the planned end state of the cyber range.



\---



\## Development Roadmap



| Phase | Focus | Planned Projects | Status |

| :--- | :--- | :---: | :--- |

| 01 | Core Infrastructure and Networking | 1–10 | In Progress |

| 02 | On-Premises Enterprise Security | 11–30 | Planned |

| 03 | Cloud and Identity Security | 31–50 | Planned |

| 04 | Advanced Blue, Red and Purple Team Operations | 51–75 | Planned |

| 05 | Enterprise Security Engineering and Automation | 76–100 | Planned |



\### Overall Progress



!\[Progress](https://progress-bar.xyz/1/?title=Completion\&width=500\&color=6741a5)



\*\*1 of 100 planned projects completed.\*\*



\---



\## Project Directory



| ID | Project | Category | Difficulty | Status |

| :---: | :--- | :--- | :--- | :--- |

| 01 | \[Core Cyber Range Foundation](01-foundation/) | Security Infrastructure | Easy / Medium | Complete |

| 02 | Enterprise Network Security and Segmentation | Network Security | Easy / Medium | Upcoming |



Additional projects will be added as the environment develops.



\---



\## Technology Stack



\### Currently Deployed



| Technology | Purpose |

| :--- | :--- |

| VMware Workstation Pro | Virtual infrastructure |

| Kali Purple | Security analysis workstation |

| Windows 11 Pro | Enterprise employee endpoint |

| Ubuntu Server | Enterprise Linux server |

| Nmap | Asset discovery and service enumeration |

| Wireshark | Network traffic and protocol analysis |

| Git / GitHub | Version control and technical documentation |



\### Planned Integrations



| Domain | Technologies |

| :--- | :--- |

| Networking | pfSense, Zeek, Suricata |

| Security Operations | Wazuh, Elastic, Sysmon |

| Identity | Active Directory, Entra ID, Microsoft Graph |

| Cloud | Azure, Defender for Cloud, Azure Monitor |

| Offensive Security | Kali Linux, Burp Suite, BloodHound |

| Purple Team | Atomic Red Team, CALDERA, VECTR |

| Detection | Sigma, YARA, KQL, MITRE ATT\&CK |

| Automation | Python, PowerShell, Bash, Terraform |

| DevSecOps | GitHub Actions, Docker, Kubernetes |



\---



\## Project Documentation Standard



Every completed project will include:



\- Project objectives and scope

\- Architecture and implementation details

\- Configuration procedures

\- Technical validation

\- Screenshots and supporting evidence

\- Findings and lessons learned

\- Security considerations



\---



\## Responsible Security Testing



All security testing and adversary emulation activities are performed within personally owned or explicitly authorized laboratory environments.



This repository is intended for cybersecurity education, defensive research, and professional development.



\---



<div align="center">



\*\*Build. Secure. Attack. Detect. Respond. Improve.\*\*



Enterprise Cyber Range | Continuous Development



</div>


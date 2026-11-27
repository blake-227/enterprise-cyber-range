# Enterprise Cyber Range

**Enterprise security engineering · Blue team · Red team · Purple team**

![Status](https://img.shields.io/badge/Status-Active%20Development-238636?style=for-the-badge) ![Projects](https://img.shields.io/badge/Projects-01%20%2F%20100-2563eb?style=for-the-badge) ![Phase](https://img.shields.io/badge/Phase-Foundation-7c3aed?style=for-the-badge)

A hands-on enterprise cybersecurity environment built progressively to practice infrastructure engineering, security operations, identity security, cloud defense, adversary emulation, and automated security validation.

[Architecture](README.md#range-architecture) · [Roadmap](README.md#range-roadmap) · [Projects](README.md#range-projects) · [Technology](README.md#range-technology)

---

## 01 / Overview

Each project expands the same enterprise environment rather than creating an unrelated lab. The goal is to build, secure, monitor, assess, investigate, and improve the infrastructure through increasingly complex exercises.

| Security domain | Engineering objectives |
| :--- | :--- |
| **Security infrastructure** | Virtualization, network segmentation, system hardening |
| **Blue team** | Security monitoring, threat hunting, incident response |
| **Red team** | Authorized security assessments and adversary emulation |
| **Purple team** | Detection validation and security control improvement |
| **Cloud security** | Azure infrastructure security, cloud logging and detection |
| **Identity security** | Identity lifecycle, access governance, privileged access |
| **Detection engineering** | Develop, test and automate security detections |
| **AppSec / DevSecOps** | Application, container, infrastructure and CI/CD security |

> This cyber range is an independent project. Its future identity environment will be built from scratch, separate from Northstar.

---

<a name="range-architecture"></a>

## Architecture

### Current environment — deployed

```mermaid
flowchart TD
    H["Windows host<br/>VMware Workstation"]
    N["VMnet2 · Host-only<br/>10.10.10.0/24"]
    K["KP-SOC01<br/>Kali Purple · .10"]
    W["WIN11-USER01<br/>Windows 11 · .20"]
    U["UBUNTU-SRV01<br/>Ubuntu Server · .30"]
    H --- N
    N --- K
    N --- W
    N --- U
    classDef purple fill:#6741a5,stroke:#a78bfa,color:#fff
    classDef blue fill:#1d4ed8,stroke:#60a5fa,color:#fff
    classDef orange fill:#9a3412,stroke:#fb923c,color:#fff
    class K purple
    class W blue
    class U orange
```

Three virtual machines operate on a host-only network with static IP addresses and no configured default gateway during lab testing. The Windows host adapter is `10.10.10.1`.

[View detailed foundation topology](architecture/FOUNDATION-TOPOLOGY.md) · [View asset inventory](01-foundation/documentation/ASSET-INVENTORY.md)

### Target architecture — planned end state

The following is a **logical architecture**, showing the major security domains and how they will work together. It is not a claim that these systems are already deployed.

```mermaid
flowchart TD
    EDGE["Controlled WAN / pfSense"]
    ENT["Enterprise network<br/>DMZ · users · servers · AD"]
    CLOUD["Cloud and identity<br/>Azure · Entra ID · AKS"]
    RED["Authorized test environment<br/>Kali Linux · ATT&CK exercises"]
    SOC["Security operations<br/>Kali Purple · SIEM · EDR · NSM"]
    PURPLE["Purple team validation<br/>Detect · investigate · improve · retest"]
    AUTO["Security engineering<br/>Git · Terraform · CI/CD · automation"]
    EDGE --- ENT
    EDGE --- CLOUD
    RED -->|Controlled tests| ENT
    RED -->|Controlled tests| CLOUD
    ENT -->|Telemetry| SOC
    CLOUD -->|Telemetry| SOC
    SOC --> PURPLE
    PURPLE --> AUTO
    AUTO -.->|Validated controls| ENT
    AUTO -.->|Validated controls| CLOUD
    classDef red fill:#991b1b,stroke:#f87171,color:#fff
    classDef purple fill:#6741a5,stroke:#a78bfa,color:#fff
    classDef blue fill:#1e40af,stroke:#60a5fa,color:#fff
    classDef teal fill:#115e59,stroke:#5eead4,color:#fff
    class RED red
    class SOC,PURPLE purple
    class CLOUD blue
    class AUTO teal
```

---

<a name="range-roadmap"></a>

## Development Roadmap

**Overall progress:** 1 of 100 planned projects complete.

![Completion](https://img.shields.io/badge/Overall%20completion-1%25-6741a5?style=flat-square)

| Phase | Focus | Projects | Status |
| :---: | :--- | :---: | :--- |
| 01 | Core infrastructure and networking | 1–10 | **In progress** |
| 02 | On-premises enterprise security | 11–30 | Planned |
| 03 | Cloud and identity security | 31–50 | Planned |
| 04 | Advanced blue, red and purple team operations | 51–75 | Planned |
| 05 | Enterprise security engineering and automation | 76–100 | Planned |

Difficulty increases from easy to medium, advanced, and hard as the environment develops.

---

<a name="range-projects"></a>

## Project Directory

| ID | Project | Category | Difficulty | Status |
| :---: | :--- | :--- | :--- | :--- |
| 01 | [Core Cyber Range Foundation](01-foundation/) | Security infrastructure | Easy–Medium | **Complete** |
| 02 | Enterprise Network Security and Segmentation | Network security | Easy–Medium | Upcoming |

### Featured project — Core Cyber Range Foundation

Deployed three virtual machines, established a static network baseline, configured recovery snapshots, and investigated ARP, ICMP and SSH traffic with Wireshark.

[Read the technical report](01-foundation/README.md) · [Browse supporting evidence](01-foundation/evidence/)

---

<a name="range-technology"></a>

## Technology Stack

### Currently deployed and used

![VMware](https://img.shields.io/badge/VMware-607078?style=flat-square) ![Kali Purple](https://img.shields.io/badge/Kali%20Purple-6741a5?style=flat-square&logo=kalilinux&logoColor=white) ![Windows](https://img.shields.io/badge/Windows%2011-0078D4?style=flat-square) ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat-square&logo=ubuntu&logoColor=white) ![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=flat-square&logo=wireshark&logoColor=white) ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

| Technology | Purpose |
| :--- | :--- |
| VMware Workstation Pro | Virtual infrastructure and recovery snapshots |
| Kali Purple | Security analysis workstation |
| Windows 11 Pro | Simulated enterprise employee endpoint |
| Ubuntu Server | Internal Linux server and SSH administration |
| Nmap | Asset discovery and service enumeration |
| Wireshark | Network traffic capture and analysis |
| Git / GitHub | Version control and technical documentation |

### Planned integrations

| Domain | Technologies |
| :--- | :--- |
| Networking | pfSense, Zeek, Suricata |
| Security operations | Wazuh, Elastic, Sysmon |
| Identity | Active Directory, Microsoft Entra ID, Microsoft Graph |
| Cloud | Azure, Defender for Cloud, Azure Monitor |
| Offensive security | Kali Linux, Burp Suite, BloodHound |
| Purple team | Atomic Red Team, CALDERA, VECTR |
| Detection | Sigma, YARA, KQL, MITRE ATT&CK |
| Automation | Python, PowerShell, Bash, Terraform |
| DevSecOps | GitHub Actions, Docker, Kubernetes |

---

## Project Documentation Standard

Every project documents its scope, architecture, implementation, technical validation, findings, lessons learned and supporting evidence. Completed work is distinguished from future plans.

## Responsible Security Testing

All testing is restricted to personally owned or explicitly authorized laboratory systems. The repository is intended for cybersecurity education, defensive research and professional development. Public evidence must exclude secrets, personal information and unrelated traffic.

---

**Build · Secure · Test · Detect · Respond · Improve**

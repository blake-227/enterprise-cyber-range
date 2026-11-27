# Enterprise Cyber Range | Asset Inventory

**Project 01 · Core Cyber Range Foundation**

![Baseline](https://img.shields.io/badge/Baseline-Project%2001-6741a5?style=for-the-badge) ![Virtual machines](https://img.shields.io/badge/Virtual%20machines-03-2563eb?style=for-the-badge) ![Network](https://img.shields.io/badge/Network-Host--only-238636?style=for-the-badge)

Inventory of the deployed systems, network settings and security controls at the completion of Project 1. This document establishes a reference point for future infrastructure changes and security investigations.

[Return to Project 01](../README.md) · [Network topology](../../architecture/FOUNDATION-TOPOLOGY.md) · [Main repository](../../README.md)

---

## 01 / Asset inventory

| Asset | Operating system | IP address | Role | Network | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Host laptop** | Windows 11 | `10.10.10.1` | VMware host adapter | VMnet2 | Active at baseline |
| **KP-SOC01** | Kali Purple | `10.10.10.10` | SOC / blue team workstation | VMnet2 | Active at baseline |
| **WIN11-USER01** | Windows 11 Pro | `10.10.10.20` | Employee workstation | VMnet2 | Active at baseline |
| **UBUNTU-SRV01** | Ubuntu Server | `10.10.10.30` | Enterprise Linux server | VMnet2 | Active at baseline |

The host adapter is not a fourth virtual machine. All three guest systems use the same host-only virtual network.

### Virtual machine resource allocation

| Hostname | vCPU | RAM | Virtual disk |
| :--- | ---: | ---: | ---: |
| KP-SOC01 | 4 | 4 GB | 80 GB |
| WIN11-USER01 | 2 | 4 GB | 64 GB |
| UBUNTU-SRV01 | 2 | 2 GB | 40 GB |

---

## 02 / System roles and services

| System | Current function | Planned expansion |
| :--- | :--- | :--- |
| **KP-SOC01** | Network analysis with Nmap and Wireshark | Threat hunting, incident response, detection engineering and purple team exercises |
| **WIN11-USER01** | Simulated employee endpoint with Microsoft Defender and Windows Firewall enabled | Sysmon, centralized log collection and domain integration |
| **UBUNTU-SRV01** | Linux server with SSH on TCP port 22 | Internal applications, server monitoring and additional services |

### Approved remote server service

| Asset | Service | Transport | Port | Purpose |
| :--- | :--- | :--- | ---: | :--- |
| UBUNTU-SRV01 | OpenSSH | TCP | 22 | Authorized remote administration |

This table records the intended server service baseline, not a comprehensive list of every listening port. See the reconnaissance evidence for observed services.

---

## 03 / Network configuration

| Parameter | Configuration |
| :--- | :--- |
| Virtual network | `VMnet2` |
| Network type | VMware host-only |
| Subnet | `10.10.10.0/24` |
| Subnet mask | `255.255.255.0` |
| VMware host adapter | `10.10.10.1` |
| DHCP | Disabled |
| Address assignment | Static |
| Guest default gateway | None |
| Guest Internet access | No configured Internet gateway during lab testing |

[View the foundation network topology](../../architecture/FOUNDATION-TOPOLOGY.md)

---

## 04 / Security baseline

| Security control | Baseline implementation |
| :--- | :--- |
| Network isolation | Host-only virtual network; no guest default gateway |
| Endpoint protection | Microsoft Defender enabled on WIN11-USER01 |
| Host firewall | Windows Defender Firewall enabled |
| Remote administration | SSH on UBUNTU-SRV01 |
| Asset discovery | Nmap reconnaissance from KP-SOC01 |
| Traffic analysis | ARP, ICMP and SSH investigated with Wireshark |
| Recovery | Clean VMware snapshots for all three virtual machines |

### Recovery snapshots

| System | Snapshot name |
| :--- | :--- |
| KP-SOC01 | `P1-CLEAN-BASELINE` |
| WIN11-USER01 | `P1-CLEAN-BASELINE` |
| UBUNTU-SRV01 | `P1-CLEAN-BASELINE` |

Snapshots provide rollback points for controlled testing, but are not independent backups.

---

## 05 / Supporting documentation

| Reference | Description |
| :--- | :--- |
| [Project 01 technical report](../README.md) | Deployment, validation, packet investigation and project outcome |
| [Foundation topology](../../architecture/FOUNDATION-TOPOLOGY.md) | Virtual network design and system placement |
| [Evidence directory](../evidence/) | Network discovery, service baseline and packet captures |
| [Screenshot directory](../screenshots/) | Visual evidence of protocol investigations |

---

**Baseline status:** Project 01 complete. Future changes to network zones, addresses, services and security controls should be recorded as the range expands. This environment remains independent of Northstar.

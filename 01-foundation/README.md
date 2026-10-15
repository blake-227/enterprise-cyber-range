\# Project 1 - Core Cyber Range Foundation



\## Overview



This project establishes the base infrastructure for my enterprise cybersecurity lab.



The purpose of the environment is to support future blue team, red team, purple team, cloud security, IAM, detection engineering, incident response, DevSecOps, and security automation projects.



Rather than creating separate disconnected labs, future projects will expand this environment into a simulated enterprise network.



\## Environment



The current environment contains three virtual machines running inside VMware Workstation.



KP-SOC01 serves as the Kali Purple security operations workstation.



WIN11-USER01 represents a standard enterprise employee endpoint.



UBUNTU-SRV01 represents an internal Linux server.



The systems communicate across an isolated VMware host-only network.



\## Network



Subnet



10.10.10.0/24



Systems



KP-SOC01

10.10.10.10



WIN11-USER01

10.10.10.20



UBUNTU-SRV01

10.10.10.30



VMware Host

10.10.10.1



\## Security Design



The cyber range is currently isolated from the Internet.



Static IP addressing is used so security monitoring and detection rules can reference predictable systems.



Windows Defender and Windows Firewall remain enabled.



The Ubuntu server currently exposes SSH for remote administration.



VMware snapshots provide clean recovery points before future security testing begins.



\## Skills Practiced



Virtualization



Network configuration



Static IP addressing



Linux administration



Windows administration



SSH



Network reconnaissance



Nmap



Asset discovery



Service enumeration



Security baselining



Lab documentation



\## Current Status



Project 1 foundation infrastructure is operational.



The next stages will introduce packet analysis, additional monitoring, centralized logging, Active Directory, cloud infrastructure, attack simulation, and detection engineering.


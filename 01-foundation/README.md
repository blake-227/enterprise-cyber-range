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



\## Network Traffic Investigation



Wireshark was used to capture and analyze network traffic within the isolated cyber range.



\### Findings



\- Successfully observed ARP requests and responses between Kali Purple and Windows 11.

\- Verified network connectivity through ICMP echo requests and replies.

\- Identified the TCP three-way handshake between Kali Purple and Ubuntu Server.

\- Observed SSH key exchange and encrypted application traffic over TCP port 22.

\- Established an initial network traffic baseline for future security monitoring and detection exercises.



\### Evidence



\- \[ARP Investigation](screenshots/01-arp-investigation.png)

\- \[ICMP Investigation](screenshots/02-icmp-investigation.png)

\- \[SSH Investigation](screenshots/03-ssh-investigation.png)

\- \[ARP and ICMP Packet Capture](evidence/01-arp-icmp-investigation.pcapng)

\- \[SSH Packet Capture](evidence/02-ssh-investigation.pcapng)



\## Current Status



Status: Complete



The core cyber range infrastructure has been successfully deployed, configured, documented, and tested. All three virtual machines are operational on the isolated VMnet2 network.



The environment is ready for future network security, monitoring, detection engineering, and enterprise security projects.







